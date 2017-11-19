---
title: IEEVisualizerServiceProvider | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEEVisualizerServiceProvider
helpviewer_keywords: IEEVisualizerServiceProvider interface
ms.assetid: 859d1a51-1c65-4c8b-ae74-3b74b181ebcd
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4bd55bb42f902bcda7cdef1ea28a8d1c39d96f26
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ieevisualizerserviceprovider"></a>IEEVisualizerServiceProvider
> [!IMPORTANT]
>  Visual Studio 2015'te ifade değerlendiricisi uygulama bu şekilde kullanım dışıdır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricileri](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Bu arabirim için IDE türü Görselleştirici görevler işlemek için kullanılan bir Görselleştirici hizmet oluşturabilmeniz için bir yöntem erişmenizi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IEEVisualizerServiceProvider : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Visual Studio sırayla sınıf kimliklerini sağlamak için kullanılan bir Görselleştirici hizmet nesnesi oluşturmak için bu arabirimi uygular (`CLSID`s) için Visual Studio IDE türü görselleştiriciler biri.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 İfade değerlendirici (EE) çağırır [GetEEService](../../../extensibility/debugger/reference/idebugbinder3-geteeservice.md) bu arabirimi elde edilir.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)|Görselleştirici hizmeti oluşturur|  
  
## <a name="remarks"></a>Açıklamalar  
 `IEEVisualizerServiceProvider` Arabirimi uygulanması sırasında elde [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md). Bu arabirim oluşturur Görselleştirici hizmeti işlevsellik sağlamak için kullanılan bir [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) , EE uygulamak için sorumlu olan arabirim. EE de uygulamak için sorumlu olduğu bir [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md) görüntülemek ve bir özelliğin değerini değiştirmek türü görselleştiriciler arabirimi.  
  
 Bkz: [Visualizing ve veri görüntüleme](../../../extensibility/debugger/visualizing-and-viewing-data.md) bu arabirimleri nasıl etkileşim hakkında bilgi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade değerlendirme arabirimleri](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)   
 [GetEEService](../../../extensibility/debugger/reference/idebugbinder3-geteeservice.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [Görselleştirme ve verileri görüntüleme](../../../extensibility/debugger/visualizing-and-viewing-data.md)