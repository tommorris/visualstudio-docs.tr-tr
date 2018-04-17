---
title: İfade değerlendirici mimarisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- architecture, expression evaluators
- expression evaluators, architecture
- debugging [Debugging SDK], expression evaluators
ms.assetid: aad7c4c6-1dc1-4d32-b975-f1fdf76bdeda
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7fdcdfef67531af40027a2dfe8c731fe9ba5128f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="expression-evaluator-architecture"></a>İfade değerlendirici mimarisi
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Visual Studio hata ayıklama pakete özel dil tümleştirme, gerekli ifade değerlendiricisi (EE) arabirimler uygulama ve ortak dil çalışma zamanı simgesi sağlayıcısı (SP) ve bağlayıcı arabirimleri çağırma anlamına gelir. SP ve bağlayıcıyı, geçerli yürütme adresi ile birlikte, ifadeler değerlendirilir bağlam nesneleridir. Bu arabirimleri üretmek ve kullanma bilgileri bir EE mimarisinde temel kavramları temsil eder.  
  
## <a name="overview"></a>Genel Bakış  
  
### <a name="parsing-the-expression"></a>İfade ayrıştırma  
 Bir program ayıklarken ifadeler nedenleri ancak her zaman bir kesme (kullanıcı tarafından yerleştirilen bir kesme noktası veya bir bir özel durumdan kaynaklanan) noktasında ayıklanacak programın ne zaman durduruldu sayısı için değerlendirilir. Tarafından temsil edilen zaman Visual Studio alacağı bir yığın çerçevesi şu anda olduğu [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) arabirimi hata ayıklama altyapısından (DE). Visual Studio sonra çağırır [GetExpressionContext](../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) almak için [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) arabirimi. Bu arabirim ifadeleri değerlendirilebilir bir bağlamı temsil eder; [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) değerlendirme iş akışına giriş noktasıdır. Bu noktaya kadar tüm arabirimler DE tarafından uygulanır.  
  
 Zaman `IDebugExpressionContext2::ParseText` olduğu adlı DE kesme meydana geldiği kaynak dosyası dili ile ilişkili EE başlatır (DE ayrıca SH bu noktada oluşturur). EE tarafından temsil edilen [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md) arabirimi. Daha sonra DE çağırır [ayrıştırma](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) (metin biçiminde) ifade ayrıştırılmış bir ifadeyi dönüştürmek için değerlendirme için hazır. Bu ayrıştırılmış ifade tarafından temsil edilen [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) arabirimi. İfade genellikle ayrıştırılır ve bu noktada değerlendirilmez unutmayın.  
  
 DE uygulayan bir nesne oluşturur [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) arabirimi, yerleştirmelerin `IDebugParsedExpression` içine nesne `IDebugExpression2` nesne ve döndürür `IDebugExpression2` nesnesinin `IDebugExpressionContext2::ParseText`.  
  
### <a name="evaluating-the-expression"></a>İfade değerlendirme  
 Visual Studio ya da çağıran [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) veya [EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) ayrıştırılmış ifadesini değerlendiremedi. Bu yöntemlerin her ikisi de çağrısı [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) (`IDebugExpression2::EvaluateSync` yöntemini çağırır hemen while `IDebugExpression2::EvaluateAsync` arka plan iş parçacığı aracılığıyla yöntemini çağırır) ayrıştırılmış ifade değerlendirmek ve döndürmek için bir [ IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) ayrıştırılmış ifade türü ve değeri temsil eden arabirim. `IDebugParsedExpression::EvaluateSync` Ayrıştırılmış ifade tarafından temsil edilen bir asıl değere dönüştürmek için sağlanan SH, adresi ve bağlayıcı kullanan `IDebugProperty2` arabirimi.  
  
### <a name="for-example"></a>Örneğin  
 Çalışan bir program bir kesme noktası isabet sonra bir değişkende görüntülemek kullanıcının seçmesi **QuickWatch** iletişim kutusu. Bu iletişim kutusunda, değişkenin adını, değeri ve türünü gösterir. Kullanıcı genellikle değeri değiştirebilirsiniz.  
  
 Zaman **QuickWatch** iletişim kutusu gösterilir, incelenmesi değişkeninin adını metin olarak gönderilir [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md). Bu döndürür bir [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) ayrıştırılmış ifadesi, bu durumda temsil eden nesne, değişkeni. [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) sonra oluşturmak için çağrılan bir `IDebugProperty2` adının yanı sıra değişkenin değerini ve türünü temsil eden nesne. Görüntülenen bu bilgilerdir.  
  
 Kullanıcı değişkenin değeri olarak değiştirirse [SetValueAsString](../../extensibility/debugger/reference/idebugproperty2-setvalueasstring.md) bellekte değişkeninin değeri program çıktığında kullanılacak şekilde Değişeni yeni değerle çağrılır çalışıyor.  
  
 Bkz: [görüntüleme Yereller](../../extensibility/debugger/displaying-locals.md) değişkenlerin değerleri görüntüleme, bu işlemi hakkında daha fazla ayrıntı için. Bkz: [yerel değerin değiştirilmesi](../../extensibility/debugger/changing-the-value-of-a-local.md) bir değişkenin değeri nasıl değiştirilir hakkında daha fazla bilgi.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Değerlendirme Bağlamı](../../extensibility/debugger/evaluation-context.md)  
 DE EE çağırdığında geçirilen bağımsız değişkenlerini sağlar.  
  
 [Anahtar İfade Değerlendiricisi Arabirimleri](../../extensibility/debugger/key-expression-evaluator-interfaces.md)  
 Değerlendirme bağlamı birlikte bir EE yazarken gereken önemli arabirimler açıklanmaktadır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir CLR ifade değerlendiricisi yazma](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [Yerel öğeler görüntüleme](../../extensibility/debugger/displaying-locals.md)   
 [Yerel Bir Öğenin Değerini Değiştirme](../../extensibility/debugger/changing-the-value-of-a-local.md)