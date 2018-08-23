---
title: IEEVisualizerServiceProvider | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IEEVisualizerServiceProvider
helpviewer_keywords:
- IEEVisualizerServiceProvider interface
ms.assetid: 859d1a51-1c65-4c8b-ae74-3b74b181ebcd
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e27eab6c3547790ca1f66181c04bba085e463c5e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634321"
---
# <a name="ieevisualizerserviceprovider"></a>IEEVisualizerServiceProvider
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IEEVisualizerServiceProvider](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ieevisualizerserviceprovider).  
  
> [!IMPORTANT]
>  Visual Studio 2015'te, bu şekilde ifade değerlendiricisi uygulama kullanım dışı bırakılmıştır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricilerini](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Bu arabirim tür görselleştiricisi görevleri için IDE işlemek için kullanılan bir görselleştiricisi hizmet oluşturabilmeniz için bir yöntem erişim sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IEEVisualizerServiceProvider : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Visual Studio sırayla sınıfı kimliklerini sağlamak için kullanılan bir Görselleştirici hizmeti nesnesi oluşturmak için bu arabirimi uygulayan (`CLSID`s), Visual Studio IDE tür görselleştiricileri.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 İfade değerlendirici (EE) çağıran [GetEEService](../../../extensibility/debugger/reference/idebugbinder3-geteeservice.md) bu arabirimi elde edilir.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)|Görselleştirici hizmeti oluşturur|  
  
## <a name="remarks"></a>Açıklamalar  
 `IEEVisualizerServiceProvider` Arabirim uygulamasını sırasında elde [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md). Bu arabirim oluşturur Görselleştirici hizmeti işlevsellik sağlamak için kullanılan bir [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) , EE uygulamak için sorumlu olan arabirim. EE de uygulamak için sorumlu olduğu bir [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md) görüntülemek ve bir özelliğin değerini değiştirmek tür görselleştiricileri arabirimi.  
  
 Bkz: [Visualizing ve verileri görüntüleme](../../../extensibility/debugger/visualizing-and-viewing-data.md) Bu arabirimler nasıl etkileşime ilişkin ayrıntılar için.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade değerlendirme arabirimleri](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)   
 [GetEEService](../../../extensibility/debugger/reference/idebugbinder3-geteeservice.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [Verileri Görselleştirme ve Görüntüleme](../../../extensibility/debugger/visualizing-and-viewing-data.md)

