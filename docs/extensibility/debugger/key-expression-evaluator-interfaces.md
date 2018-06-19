---
title: İfade değerlendirici arabirimleri anahtar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, interfaces
ms.assetid: 1cac9aa3-0867-4e12-a16e-1e90abbc0fb6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fe0c592c65e2c6ab7429cef44a830325a834ecdc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31103854"
---
# <a name="key-expression-evaluator-interfaces"></a>Anahtar ifade değerlendiricisi arabirimleri
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Değerlendirme bağlamı birlikte bir ifade değerlendiricisi (EE) yazarken aşağıdaki arabirimleriyle tanımanız gerekir.  
  
## <a name="interface-descriptions"></a>Arabirim açıklamaları  
  
-   [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)  
  
     Tek bir yönteme sahip [GetAddress](../../extensibility/debugger/reference/idebugaddress-getaddress.md), hangi veri yapısı alır geçerli yürütme noktası temsil eder. Bu veri yapısını (DE) hata ayıklama altyapısı geçirir üç bağımsız değişken biri [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) bir ifade değerlendirmek için bir yöntem. Bu arabirim, genellikle simgesi sağlayıcı tarafından uygulanır.  
  
-   [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)  
  
     Sahip [bağlamak](../../extensibility/debugger/reference/idebugbinder-bind.md) geçerli bir simge değerini içeren bellek alanını alır yöntemi. Tarafından temsil edilen her iki içeren yöntemi, verilen bir [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) nesne ve tarafından temsil edilen simgenin kendisine, bir [IDebugField](../../extensibility/debugger/reference/idebugfield.md) nesnesi `IDebugBinder::Bind` simge değerini döndürür. `IDebugBinder` Genel DE tarafından uygulanır.  
  
-   [IDebugField](../../extensibility/debugger/reference/idebugfield.md)  
  
     Basit veri türünü temsil eder. Diziler ve yöntemleri gibi daha karmaşık türleri için kullanmak türetilen [IDebugArrayField](../../extensibility/debugger/reference/idebugarrayfield.md) ve [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) arabirimleri, sırasıyla. [IDebugContainerField](../../extensibility/debugger/reference/idebugcontainerfield.md) yöntemleri veya sınıflar gibi diğer simgelerini içeren sembolleri temsil eden başka bir önemli türetilmiş arabirimidir. `IDebugField` Arabirimi (ve türevleri) simgesi sağlayıcı tarafından uygulanan genellikle.  
  
     Bir `IDebugField` nesne adı ve bir simgenin türünü bulmak için kullanılan ve, birlikte olabilir bir [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) nesne, kendi değerini bulmak için kullanılabilir.  
  
-   [IDebugObject](../../extensibility/debugger/reference/idebugobject.md)  
  
     Bir simge çalışma zamanı değeri gerçek BITS temsil eder. [Bağlama](../../extensibility/debugger/reference/idebugbinder-bind.md) geçen bir [IDebugField](../../extensibility/debugger/reference/idebugfield.md) bir simge temsil eder ve döndüren nesnesi bir [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) nesnesi. [GetValue](../../extensibility/debugger/reference/idebugobject-getvalue.md) yöntemi, bir bellek arabelleği simge değerini döndürür. SE genellikle bellekte bir özelliğin değerini temsil etmek için bu arabirimi uygular.  
  
-   [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md)  
  
     Bu arabirim ifade değerlendiricisi temsil eder. Anahtar yöntemi [ayrıştırma](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md), döndüren bir [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) arabirimi.  
  
-   [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md)  
  
     Bu arabirim değerlendirilecek hazır bir ayrıştırılmış ifadesi temsil eder. Anahtar yöntemi [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) IDebugProperty2 bir ifade türü ve değeri temsil eden hangi döndürür.  
  
-   [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)  
  
     Bu arabirim, bir değer ve türünü temsil eder ve bir ifade değerlendirme sonucu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Değerlendirme Bağlamı](../../extensibility/debugger/evaluation-context.md)