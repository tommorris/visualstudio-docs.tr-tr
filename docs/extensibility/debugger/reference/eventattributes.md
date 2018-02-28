---
title: EVENTATTRIBUTES | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- EVENTATTRIBUTES
helpviewer_keywords:
- EVENTATTRIBUTES enumeration
ms.assetid: 04db10f7-df31-4464-98e8-b3777428179e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 0d9238caf15c94aaf658d97fa8866c6ff43de687
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="eventattributes"></a>EVENTATTRIBUTES
Olay özniteliklerini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
typedef DWORD EVENTATTRIBUTES;  
```  
  
```csharp  
public enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
```  
  
## <a name="members"></a>Üyeler  
 EVENT_ASYNCHRONOUS  
 Zaman uyumsuz bir olaydır ve olay yanıt gerekli olduğunu gösterir.  
  
 EVENT_SYNCHRONOUS  
 Olay zaman uyumlu olduğunu gösterir; yoluyla Yanıtla [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md).  
  
 EVENT_STOPPING  
 Bu durdurma olay olduğunu gösterir. İle birlikte `EVENT_ASYNCHRONOUS` veya `EVENT_SYNCHRONOUS`.  
  
 EVENT_ASYNC_STOP  
 Zaman uyumsuz durdurma olay gösterir. Şu anda bu tür bir olay. Bu bayrak yalnızca bir yer tutucudur.  
  
 EVENT_SYNC_STOP  
 Zaman uyumlu durdurma olay gösterir (bir birleşimini `EVENT_SYNCHRONOUS` ve `EVENT_STOPPING`). Durdurma olay gönderdiğinde, bu değer hata ayıklama altyapısı (DE) tarafından kullanılır. Yanıt için bir çağrı yoluyla yapılan [yürütme](../../../extensibility/debugger/reference/idebugprogram2-execute.md), [adım](../../../extensibility/debugger/reference/idebugprogram2-step.md), veya [devam](../../../extensibility/debugger/reference/idebugprogram2-continue.md).  
  
 EVENT_IMMEDIATE  
 IDE hemen ve eşzamanlı olarak gönderilen bir olay gösterir. Bu bayrak gibi diğer bayraklar birlikte `EVENT_ASYNCHRONOUS`, `EVENT_SYNCHRONOUS`, veya `EVENT_SYNC_STOP` olay ve yanıt mekanizmasını (varsa) bilinir olgu türünü belirtmek için.  
  
 EVENT_EXPRESSION_EVALUATION  
 Olay bir ifade değerlendirme sonucudur.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu değerleri iletilen `dwAttrib` parametresinin [olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) yöntemi.  
  
 Bu değerlerin Bitsel ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)   
 [Olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)