---
title: IDebugEventCallback2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEventCallback2
helpviewer_keywords: IDebugEventCallback2
ms.assetid: 2c935ee0-2e22-4be0-a852-73736f33c8c9
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 165f973fa9139f281211e6b01167b3d7044166df
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugeventcallback2"></a>IDebugEventCallback2
Bu arabirim, oturum hata ayıklama Yöneticisi (SDM) hata ayıklama olayları göndermek için hata ayıklama altyapısı (DE) tarafından kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugEventCallback2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]bir hata ayıklama altyapısı olaylarını almak için bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 SDM çağırdığında bir hata ayıklama altyapısı genellikle bu arabirimin aldığı [Attach](../../../extensibility/debugger/reference/idebugprogram2-attach.md), [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md), veya [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md). Hata ayıklama altyapısı olayları SDM çağırarak gönderir [olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md).  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugEventCallback2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)|SDM olaylarına ayıklama bildirim gönderir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ancak [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) ve [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) bunlar sürmesi bir `IDebugEventCallback2` arabirimi, bu durumda değil ve arabirim işaretçisi her zaman bir null değer olacaktır. Bunun yerine, hata ayıklama altyapısı kullanmalısınız `IDebugEventCallback2` çağrısında alınan arabirimi [Attach](../../../extensibility/debugger/reference/idebugprogram2-attach.md), [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md), veya [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md).  
  
 Bir paket uyguluyorsa [IDebugEventCallback](../../../extensibility/debugger/reference/idebugeventcallback2.md) yönetilen kodda kesinlikle önerilir, <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> çağrılabilir geçirilecek çeşitli arabirimlerindeki [olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md).  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çekirdek arabirimleri](../../../extensibility/debugger/reference/core-interfaces.md)   
 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [Ekleme](../../../extensibility/debugger/reference/idebugprogram2-attach.md)   
 [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)