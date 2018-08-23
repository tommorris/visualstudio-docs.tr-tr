---
title: EVENTATTRIBUTES | Microsoft Docs
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
- EVENTATTRIBUTES
helpviewer_keywords:
- EVENTATTRIBUTES enumeration
ms.assetid: 04db10f7-df31-4464-98e8-b3777428179e
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1a0dcc3458d6defacb76b89c65d5897361325981
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689841"
---
# <a name="eventattributes"></a>EVENTATTRIBUTES
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [EVENTATTRIBUTES](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/eventattributes).  
  
Olay öznitelikleri belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 Olay zaman uyumlu olduğunu gösterir; yoluyla yanıt [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md).  
  
 EVENT_STOPPING  
 Durdurma olay olduğunu gösterir. İle birleştirilmelidir `EVENT_ASYNCHRONOUS` veya `EVENT_SYNCHRONOUS`.  
  
 EVENT_ASYNC_STOP  
 Zaman uyumsuz durdurma olay gösterir. Şu anda bu tür bir olay. Bu bayrağı yalnızca bir yer tutucudur.  
  
 EVENT_SYNC_STOP  
 Zaman uyumlu durdurma olay gösterir (bir birleşimini `EVENT_SYNCHRONOUS` ve `EVENT_STOPPING`). Durdurma olay gönderdiğinde, bu değer bir hata ayıklama altyapısı (DE) kullanılır. Yanıt için bir çağrı yoluyla yapılan [yürütme](../../../extensibility/debugger/reference/idebugprogram2-execute.md), [adım](../../../extensibility/debugger/reference/idebugprogram2-step.md), veya [devam](../../../extensibility/debugger/reference/idebugprogram2-continue.md).  
  
 EVENT_IMMEDIATE  
 IDE hemen ve eşzamanlı olarak gönderilen bir olay gösterir. Bu bayrak, gibi diğer bayraklar birlikte `EVENT_ASYNCHRONOUS`, `EVENT_SYNCHRONOUS`, veya `EVENT_SYNC_STOP` olay ve yanıt mekanizmasını (varsa) bilinir olgu türünü belirtmek için.  
  
 EVENT_EXPRESSION_EVALUATION  
 İfade değerlendirmesinin sonucu olayıdır.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu değerleri geçirilir `dwAttrib` parametresinin [olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) yöntemi.  
  
 Bu değerler, bit düzeyinde ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)   
 [Olay](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)

