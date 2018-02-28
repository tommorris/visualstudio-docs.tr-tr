---
title: IDebugBreakpointErrorEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugBreakpointErrorEvent2
helpviewer_keywords:
- IDebugBreakpointErrorEvent2
ms.assetid: adee79df-8db5-4510-a7df-c50f4dbf5e35
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 244a3d2c522d96983cf976b37ab206f2721d4e0c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugbreakpointerrorevent2"></a>IDebugBreakpointErrorEvent2
Bu arabirim oturum hata ayıklama Yöneticisi'ni (SDM) bekleyen bir kesme noktası yüklenen bir program, bir uyarı veya hata nedeniyle bağlanamadı olduğunu bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugBreakpointErrorEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 DE, kesme noktaları desteğini bir parçası olarak bu arabirimi uygular. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) arabirimi uygulanan, bu arabirimle aynı nesne üzerinde (SDM kullanan [QueryInterface](/cpp/atl/queryinterface) erişimi `IDebugEvent2` arabirimi).  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Aygıtların oluşturur ve bekleyen bir kesme noktası ayıklanacak programın bağlanamaz zaman bu olay nesnesi gönderir. Olay kullanılarak gönderilen [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) ayıklanacak programın eklendiğinde SDM tarafından sağlanan geri çağırma işlevi.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugBreakpointErrorEvent2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetErrorBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md)|Alır [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) uyarı veya hata açıklar arabirimi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir kesme noktası bağlı olduğunda, bir olay için SDM gönderilir. Kesme noktası bağlı değilse, bir `IDebugBreakpointErrorEvent2` gönderilen; Aksi takdirde, bir [IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) gönderilir.  
  
 Örneğin, ayrıştırma veya değerlendirmek bekleyen kesme noktası ile ilişkilendirilen koşulu başarısız olduğunda bir uyarı bekleyen kesme noktası şu anda bağlı gönderilir. Kesme noktası kodunu henüz yüklenmemiş değilse bu durum oluşabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)   
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)