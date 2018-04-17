---
title: Yerel öğeler görüntüleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, displaying locals
ms.assetid: 62264cec-845b-4233-aed7-0b038fa79250
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 03a3f08498e8b046b02defd32083677b7f39e7e5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="displaying-locals"></a>Yerel öğeler görüntüleme
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Her zaman yürütme yöntemi, içeren yöntemi olarak da bilinen veya geçerli yöntemi bağlamında gerçekleştirilir. Yürütme duraklatır, Visual Studio hata ayıklama altyapısı yerel değişkenler listesini almak için (DE) ve bağımsız değişkenler, topluca yöntemi Yereller adlı çağırır. Visual Studio bu Yereller ve değerlerini görüntüler **Yereller** penceresi.  
  
 Yerel öğeler görüntülemek için DE çağırır [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) yöntemi EE ait olan bir değerlendirme bağlamı, simge sağlayıcısı (SP), geçerli yürütme adresi ve bir bağlayıcı nesnesi sağlar. Daha fazla bilgi için bkz: [değerlendirme bağlamı](../../extensibility/debugger/evaluation-context.md). Çağrı başarılı olursa, `IDebugExpressionEvaluator::GetMethodProperty` yöntemi döndürür bir [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) geçerli yürütme adresini içeren yöntemi temsil eden nesne.  
  
 DE çağrıları [EnumChildren](../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) almak için bir [IEnumDebugPropertyInfo2](../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) , yalnızca Yereller döndürmek için filtre ve listesini oluşturmak için numaralandırılmış nesnesini [DEBUG_PROPERTY_INFO](../../extensibility/debugger/reference/debug-property-info.md)yapıları. Her yapısı adını, türünü ve yerel değerini içerir. Türü ve değerine biçimlendirilmiş dizeler, görüntülemek için uygun olarak depolanır. Adını, türünü ve değerini genellikle birlikte tek satırda görüntülenen **Yereller** penceresi.  
  
> [!NOTE]
>  **QuickWatch** ve **izleme** windows ayrıca değişkenleri ada, değere ve türü aynı biçiminde görüntüler. Ancak, bu değerleri çağırarak elde edilen [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) yerine `IDebugProperty2::EnumChildren`.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Örnek Yerel Öğeler Uygulaması](../../extensibility/debugger/sample-implementation-of-locals.md)  
 Yerel öğeler uygulama işlemi boyunca size adım adım örnekler kullanır.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Değerlendirme Bağlamı](../../extensibility/debugger/evaluation-context.md)  
 Hata ayıklama altyapısı (DE) ifade değerlendiricisi (EE) aradığında, bu üç bağımsız değişken geçtiğini açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir CLR ifade değerlendiricisi yazma](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)