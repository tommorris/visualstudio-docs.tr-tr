---
title: IEEVisualizerDataProvider | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEEVisualizerDataProvider
helpviewer_keywords: IEEVisualizerDataProvider interface
ms.assetid: 5fdfe6e3-b94e-4edb-acc5-41d8773d8ca5
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9ffe7e33b4652c0f0d3bd506e28d14c5b0949983
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ieevisualizerdataprovider"></a>IEEVisualizerDataProvider
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Bu arabirim türü Görselleştirici aracılığıyla bir nesnenin değerini değiştirme olanağı sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IEEVisualizerDataProvider : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 İfade değerlendirici değiştirme veri türü Görselleştirici aracılığıyla bir özellik nesnesinde desteklemek için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim oluşturmak için kullanılan [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md) çağrısıyla nesne [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md). Bkz: [Visualizing ve veri görüntüleme](../../../extensibility/debugger/visualizing-and-viewing-data.md) daha fazla ayrıntı için.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[CanSetObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-cansetobjectforvisualizer.md)|Nesne (ve daha sonra değerini) güncelleştirmek mümkün olup olmadığını belirler, bu Görselleştirici temsil eden.|  
|[GetNewObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-getnewobjectforvisualizer.md)|Nesnenin yeniden değerlendirme için bu Görselleştirici zorlar.|  
|[GetObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-getobjectforvisualizer.md)|Varolan bir nesneyi (hiçbir değerlendirme yapılır) bu Görselleştirici için alır.|  
|[SetObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-setobjectforvisualizer.md)|Bu Görselleştirici böylece Görselleştirici sunar değerini değiştirmek için nesneyi güncelleştirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Görselleştirici hizmet (tarafından temsil edilen [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md) arabirim ve tarafından döndürülen [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)) uygulama nesnesi için bir başvuru `IEEVisualizerDataProvider` arabirimi . Sonuç olarak, `IEEVisualizerDataProvider` arabirimi uygulanmadı uygulayan aynı nesne üzerinde [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) söz konusu nesne başvuru koruyorsa `IEEVisualizerService` nesnesi: bir döngüsel başvuru sonuçları ve nesneleri yok kilitlenme oluşur. Uygulamak için önerilen yaklaşımdır `IEEVisualizerDataProvider` hangi ayrı bir nesne üzerinde `IDebugProperty2` nesne temsilciler çağırmadan `IUnknown::AddRef` üzerindeki.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade değerlendirme arabirimleri](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)   
 [Görselleştirme ve verileri görüntüleme](../../../extensibility/debugger/visualizing-and-viewing-data.md)