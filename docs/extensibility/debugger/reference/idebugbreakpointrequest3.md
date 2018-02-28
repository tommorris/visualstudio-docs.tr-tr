---
title: IDebugBreakpointRequest3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugBreakpointRequest3
helpviewer_keywords:
- IDebugBreakpointRequest3
ms.assetid: 8a042beb-b319-48e3-b3c8-9c8336ab371b
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: acccf830983239f81ba5c896c848ec13007c5d6f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugbreakpointrequest3"></a>IDebugBreakpointRequest3
Bu arabirim oluşturmak ve herhangi bir türde kesme noktası bağlamak gereken bilgileri temsil eder. Bir uzantısıdır [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugBreakpointRequest3 : IDebugBreakpointRequest2  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Oturum hata ayıklama Yöneticisi'ni (SDM) genellikle bu arabirimi uygular.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Hata ayıklama altyapısı (DE) çağırarak bu arabirim erişen [QueryInterface](/cpp/atl/queryinterface) çağrıda alınan IDebugBreakpointRequest2 arabirimde [CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md).  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Kaynağından devralındı yöntemleri yanı sıra [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md), `IDebugBreakpointRequest3` arabirimi aşağıdaki yöntemi kullanıma sunar.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetRequestInfo2](../../../extensibility/debugger/reference/idebugbreakpointrequest3-getrequestinfo2.md)|Bu kesme isteği açıklar kesme noktası isteği bilgilerini alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim DE ek bilgi sağlamak için kullanılan [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) yapısı. Bu ek bilgiler DE'ın satıcı kimliği (GUID biçiminde), bir tracepoint adını ve bir kesme noktası kısıtlama adını içerir.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)