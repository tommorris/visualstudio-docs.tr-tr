---
title: IPropertyProxyProvider | Microsoft Docs
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
- IPropertyProxyProvider
helpviewer_keywords:
- IPropertyProxyProvider interface
ms.assetid: 52e9f7fc-6fe0-4d23-890b-5673dca8c3cb
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d6600fd9038d01c8417818886d093b5955217d03
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695938"
---
# <a name="ipropertyproxyprovider"></a>IPropertyProxyProvider
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IPropertyProxyProvider](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ipropertyproxyprovider).  
  
Bu arabirim, görüntülemek ve nesnenin verileri değiştirmek için bir proxy arabirimi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IPropertyProxyProvider : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 İfade değerlendirici (EE) bu arabirimi uygulayan aynı nesne üzerinde uygulayan [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) tür görselleştiricileri desteğinin EE'ın bir parçası olarak arabirimi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) üzerinde bir `IDebugProperty3` arabirimi bu arabirim elde edilir.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 `IPropertyProxyProvider` Arabirimi uygulayan aşağıdaki yöntemi:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md)|Bir nesne üzerinde verileri görüntülemek için bir özellik proxy arabirimi alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 EE uygulanması bu arabirimi uygulayan rağmen [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) genellikle tarafından işlenen [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md). Bkz: [Visualizing ve verileri görüntüleme](../../../extensibility/debugger/visualizing-and-viewing-data.md) IEEVisualizerService arabirimi edinme hakkında ayrıntılar için.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel arabirimler](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)   
 [Tür görselleştiricisi ve özel Görüntüleyici](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)   
 [Verileri Görselleştirme ve Görüntüleme](../../../extensibility/debugger/visualizing-and-viewing-data.md)

