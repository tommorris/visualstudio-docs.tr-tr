---
title: "Gözcü penceresi ifadesi değerlendirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Watch window expressions
- Watch window, expressions
- expression evaluation, Watch window expressions
ms.assetid: b07e72c7-60d3-4b30-8e3f-6db83454c348
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fb109fd91e4c295bf372b14e26bc2a75c3be6b1d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="evaluating-a-watch-window-expression"></a>Gözcü penceresi ifade değerlendirme
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Yürütme duraklatır, Visual Studio hata ayıklama altyapısı kendi izleme listesindeki her bir ifadenin geçerli değeri belirlemek için (DE) çağırır. Bir ifade değerlendiricisi (EE) kullanarak her ifade DE değerlendirir ve Visual Studio görüntüler değeriyle **izleme** penceresi.  
  
 Aşağıda, bir izleme listesi ifadesi nasıl değerlendirilir genel bir bakış verilmiştir:  
  
1.  Visual Studio çağırır DE's [GetExpressionContext](../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) ifadeleri değerlendirmek için kullanılan bir ifade bağlamı alınamadı.  
  
2.  Gözcü listesindeki her bir ifade için Visual Studio çağırır [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) ifade metni ayrıştırılmış bir ifadesine dönüştürmek için.  
  
3.  `IDebugExpressionContext2::ParseText`çağrıları [ayrıştırma](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) metin ve üretim ayrıştırma gerçek işlemlerini yapmak için bir [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) nesnesi.  
  
4.  `IDebugExpressionContext2::ParseText`oluşturur bir [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) nesne ve yerleştirmelerin `IDebugParsedExpression` içine nesne. Bu t`DebugExpression2` nesne için Visual Studio sonra döndürdü.  
  
5.  Visual Studio çağrıları [EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) ayrıştırılmış ifadesini değerlendiremedi.  
  
6.  `IDebugExpression2::EvaluateSync`Çağrı geçirir [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) gerçek değerlendirme yapmak ve üretmek için bir [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) Visual Studio'ya döndürülen nesne.  
  
7.  Visual Studio çağrıları [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) sonra izleme liste görünümünde görüntülenen ifade değeri elde etmek için.  
  
## <a name="parse-then-evaluate"></a>Ayrıştırma sonra değerlendir  
 Karmaşık bir ifade ayrıştırma değerlendirirken daha çok uzun sürebilir olduğundan, bir ifade değerlendirme işlemi iki adımdan ayrılmış olup: 1) ifade ayrıştırabilir ve 2) ayrıştırılmış ifadesini değerlendiremedi. Bu şekilde, birçok kez değerlendirme oluşabilir ancak yalnızca bir kez ayrıştırılacak ifade gerekiyor. Ara ayrıştırılmış ifade EE öğesinden döndürülen bir [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) sırayla kapsüllenmiş ve DE döndürülen nesne bir [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) nesnesi. `IDebugExpression` Nesnesi için tüm değerlendirme erteler `IDebugParsedExpression` nesnesi.  
  
> [!NOTE]
>  Bir EE Visual Studio bu varsayar olsa bile bu iki adımlı işlem bağlı olması gerekli değildir; EE ayrıştırabilir ve aynı adımda değerlendirmek zaman [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) olarak adlandırılır (MyCEE örnek, örneğin işleyişi budur). Karmaşık ifadeler dilinizi oluşturabilir, ayrıştırma adım değerlendirme adımdan ayırmak isteyebilirsiniz. Birçok ifadeleri izlerken bu Visual Studio hata ayıklayıcısında performans artırabilir gösterilir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Örnek İfade Değerlendirme Uygulaması](../../extensibility/debugger/sample-implementation-of-expression-evaluation.md)  
 İfade değerlendirme işlemi adım MyCEE örnek kullanır.  
  
 [Bir Gözcü İfadesini Değerlendirme](../../extensibility/debugger/evaluating-a-watch-expression.md)  
 Başarılı ifade ayrıştırma sonra ne olacağını açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Değerlendirme Bağlamı](../../extensibility/debugger/evaluation-context.md)  
 Hata ayıklama altyapısı (DE) ifade değerlendiricisi (EE) çağırdığında geçirilen bağımsız değişkenlerini sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir CLR ifade değerlendiricisi yazma](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)