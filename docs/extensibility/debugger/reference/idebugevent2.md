---
title: IDebugEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEvent2
helpviewer_keywords:
- IDebugEvent2 interface
ms.assetid: de3d714d-96fb-4e12-b66b-a75391472153
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 0d783cb13ee227e317afe9b49abedb6f53e9fa76
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugevent2"></a>IDebugEvent2
Bu arabirim, bir kesme noktasında durdurma gibi kritik hata ayıklama bilgileri ve hata ayıklama iletisi gibi kritik olmayan bilgileri iletişim kurmak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı (DE) ve özel bağlantı noktası tedarikçi diğer tüm olay arabirimleri aynı nesnede bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Kimliği'ni (IID) bağımsız değişkeni için verilen arabirimini kullanarak [olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) veya [olay](../../../extensibility/debugger/reference/idebugportevents2-event.md), oturum hata ayıklama Yöneticisi'ni (SDM) çağırır [QueryInterface](/cpp/atl/queryinterface) üzerinde `IDebugEvent2` almak için arabirimi uygun olay arabirimi.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugEvent2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md)|Bu hata ayıklama olay için özniteliklerini alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Gibi daha ayrıntılı olay arabirimleri [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md), IDebugEvent2 arabiriminden türetilen değil ancak bunun yerine aynı nesne üzerinde ayrı bir arabirimi olarak uygulanır `IDebugEvent2`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [Olay](../../../extensibility/debugger/reference/idebugportevents2-event.md)   
 [Olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)