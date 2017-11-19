---
title: IPropertyProxyProvider | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IPropertyProxyProvider
helpviewer_keywords: IPropertyProxyProvider interface
ms.assetid: 52e9f7fc-6fe0-4d23-890b-5673dca8c3cb
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: de400fc9e5b631a7ccffb0547fa693a8bf0ac419
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ipropertyproxyprovider"></a>IPropertyProxyProvider
Bu arabirim görüntülemek ve nesnenin verileri değiştirmek için bir proxy arabirimi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IPropertyProxyProvider : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 İfade değerlendirici (EE) bu arabirimi uygulayan aynı nesne üzerinde uygulayan [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) arabirimi türü görselleştiriciler EE'ın desteklenmesi bir parçası olarak.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Çağrı [QueryInterface](/cpp/atl/queryinterface) üzerinde bir `IDebugProperty3` bu arabirimi sağlamak için arabirim.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 `IPropertyProxyProvider` Arabirimini uygulayan aşağıdaki yöntemi:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md)|Bir nesne üzerinde verileri görüntülemek için bir özellik proxy arabirimi alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 EE uygulaması bu arabirimi uygulayan rağmen [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) genellikle tarafından işlenen [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md). Bkz: [Visualizing ve veri görüntüleme](../../../extensibility/debugger/visualizing-and-viewing-data.md) IEEVisualizerService arabirimi edinme hakkında ayrıntılar için.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)   
 [Türü Görselleştirici ve özel Görüntüleyicisi](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)   
 [Görselleştirme ve verileri görüntüleme](../../../extensibility/debugger/visualizing-and-viewing-data.md)