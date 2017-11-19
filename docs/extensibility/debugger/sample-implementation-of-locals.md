---
title: "Örnek Yereller uygulaması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], local variables
- expression evaluation, local variables
ms.assetid: 66a2e00a-f558-4e87-96b8-5ecf5509e04c
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c167c0a0f0a9dd0c14b92f27c0d9d862b5157072
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sample-implementation-of-locals"></a>Yerel öğeler için örnek uygulama
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Aşağıda, Visual Studio bir yöntem için yerel ifade değerlendiricisi (EE) nasıl alacağını genel bir bakış verilmiştir:  
  
1.  Visual Studio hata ayıklama altyapısının (DE) çağırır [GetDebugProperty](../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md) almak için bir [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) yerel öğeler de dahil olmak üzere yığın çerçevesi tüm özelliklerini temsil eden nesne.  
  
2.  `IDebugStackFrame2::GetDebugProperty`çağrıları [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) kesme içinde gerçekleştiği yöntemi açıklayan bir nesne elde edilir. Sembol sağlayıcısının DE sağladığı ([IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)), adres ([IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)) ve bir bağlayıcı ([IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)).  
  
3.  `IDebugExpressionEvaluator::GetMethodProperty`çağrıları [GetContainerField](../../extensibility/debugger/reference/idebugsymbolprovider-getcontainerfield.md) ile sağlanan `IDebugAddress` nesnesi bir [IDebugContainerField](../../extensibility/debugger/reference/idebugcontainerfield.md) belirtilen adresi içeren yöntemi temsil eden.  
  
4.  `IDebugContainerField` Arabirimi için sorgulanan [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) arabirimi. Bu yöntemin Yereller erişim sağlayan bu arabirimidir.  
  
5.  `IDebugExpressionEvaluator::GetMethodProperty`bir sınıf oluşturur (adlı `CFieldProperty` örnekteki) uygulayan `IDebugProperty2` yöntemin Yereller temsil etmek için arabirim. `IDebugMethodField` Nesne bu yerleştirilir `CFieldProperty` ile birlikte nesne `IDebugSymbolProvider`, `IDebugAddress` ve `IDebugBinder` nesneleri.  
  
6.  Zaman `CFieldProperty` nesne başlatılır, [GetInfo](../../extensibility/debugger/reference/idebugfield-getinfo.md) üzerinde adlı `IDebugMethodField` elde etmek için nesne bir [FIELD_INFO](../../extensibility/debugger/reference/field-info.md) yöntemi görüntülenebilecek tüm bilgileri içeren yapısı .  
  
7.  `IDebugExpressionEvaluator::GetMethodProperty`döndürür `CFieldProperty` nesnesinin bir `IDebugProperty2` nesnesi.  
  
8.  Visual Studio çağrıları [EnumChildren](../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) döndürülen üzerinde `IDebugProperty2` filtre nesnesiyle `guidFilterLocalsPlusArgs`. Bu döndürür bir [IEnumDebugPropertyInfo2](../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) yöntemin Yereller içeren nesne. Bu numaralandırma çağrıları tarafından doldurulur [EnumLocals](../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) ve [EnumArguments](../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md).  
  
9. Visual Studio çağrıları [sonraki](../../extensibility/debugger/reference/ienumdebugpropertyinfo2-next.md) elde etmek için bir [DEBUG_PROPERTY_INFO](../../extensibility/debugger/reference/debug-property-info.md) her yerel yapısı. Bu yapı işaretçi içeren bir `IDebugProperty2` yerel arabirimi.  
  
10. Visual Studio çağrıları [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) yerel'ın adını, değeri ve türünü almak her yerel için. Görüntülenen bilgileri budur **Yereller** penceresi.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [GetMethodProperty uygulama](../../extensibility/debugger/implementing-getmethodproperty.md)  
 Uygulaması açıklar [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md).  
  
 [Yerel öğeler numaralandırma](../../extensibility/debugger/enumerating-locals.md)  
 Hata ayıklama altyapısı (DE) yerel değişkenler veya bağımsız değişkenler numaralandırmak için bir çağrı nasıl yapar açıklar.  
  
 [Yerel özellikleri alınıyor](../../extensibility/debugger/getting-local-properties.md)  
 Ne DE adını, türünü ve bir veya daha fazla Yereller değerini almak için bir çağrı yapar açıklar.  
  
 [Yerel değerleri alma](../../extensibility/debugger/getting-local-values.md)  
 Değerlendirme bağlamı tarafından verilen bir bağlayıcı nesnesi hizmetlerinin gerektirir ve yerel değerini alma açıklanır.  
  
 [Yerel öğeler değerlendirme](../../extensibility/debugger/evaluating-locals.md)  
 Yerel öğeler nasıl değerlendirildiği açıklanır.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Değerlendirme bağlamı](../../extensibility/debugger/evaluation-context.md)  
 İfade değerlendirici (EE) DE çağırdığında geçirilen bağımsız değişkenlerini sağlar.  
  
 [MyCEE örnek](http://msdn.microsoft.com/en-us/624a018b-9179-402f-9d48-3aec87b48f4f)  
 Bir ifade değerlendiricisi MyC dil oluşturmak için bir uygulama yaklaşım gösterir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel öğeler görüntüleme](../../extensibility/debugger/displaying-locals.md)