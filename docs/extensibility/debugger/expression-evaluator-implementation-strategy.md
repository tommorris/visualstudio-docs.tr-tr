---
title: "İfade değerlendirici uygulama stratejisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- expression evaluation, implementation strategy
- debug engines, implementation strategies
ms.assetid: 1bccaeb3-8109-4128-ae79-16fd8fbbaaa2
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 48b871eeccb5ff561ef4b95689f12a9f58302bc9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="expression-evaluator-implementation-strategy"></a>İfade değerlendirici uygulama stratejisi
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Bir ifade değerlendiricisi (EE) hızlı bir şekilde oluşturmak için bir yaklaşım ise ilk yerel değişkenlerde göstermek için gerekli minimum kodu uygulamak için **Yereller** penceresi. Fark yararlıdır her satırda **Yereller** penceresinde adını, türünü ve yerel bir değişkenin değerini ve tüm üç tarafından temsil edilen bir [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) nesnesi. Adını, türünü ve yerel bir değişkenin değerini öğesinden elde edilebilir bir `IDebugProperty2` çağırarak nesne kendi [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) yöntemi. Yerel değişkenler görüntüleme hakkında daha fazla bilgi için **Yereller** penceresinde bkz [görüntüleme Yereller](../../extensibility/debugger/displaying-locals.md).  
  
## <a name="discussion"></a>Tartışma  
 Uygulama ile olası uygulama dizisini başlatır [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md). [Ayrıştırma](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) ve [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) yöntemleri Yereller görüntülemek için uygulanması gerekir. Çağırma `IDebugExpressionEvaluator::GetMethodProperty` döndürür bir `IDebugProperty2` bir yöntemi temsil eden nesnesi: başka bir deyişle, bir [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) nesnesi. İçinde yöntemleri kendilerini görüntülenmez **Yereller** penceresi.  
  
 [EnumChildren](../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) yöntemin sonraki. Hata ayıklama altyapısı (DE) geçirerek yerel değişkenleri ve bağımsız değişkenler listesini almak için bu yöntemi çağırır `IDebugProperty2::EnumChildren` bir `guidFilter` bağımsız değişkeni `guidFilterLocalsPlusArgs`. `IDebugProperty2::EnumChildren`çağrıları [EnumArguments](../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) ve [EnumLocals](../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md), tek bir numaralandırma sonuçlarında birleştirme. Bkz: [görüntüleme Yereller](../../extensibility/debugger/displaying-locals.md) daha fazla ayrıntı için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir ifade değerlendiricisi uygulama](../../extensibility/debugger/implementing-an-expression-evaluator.md)   
 [Yerel Öğeleri Görüntüleme](../../extensibility/debugger/displaying-locals.md)