---
title: "Ekleme ve bir programa ayırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines, attaching to programs
- debug engines, detaching from programs
ms.assetid: 79dcbb9b-c7f8-40fc-8a00-f37fe1934f51
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 71f678852b4d16d0b7c6f150abae03c6c4cdcad4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="attaching-and-detaching-to-a-program"></a>Ekleme ve bir programa ayırma
Hata ayıklayıcı ekleme yöntemleri ve uygun öznitelikler olaylarla doğru sırasını gönderilmesi gerekir.  
  
## <a name="sequence-of-methods-and-events"></a>Yöntemleri ve olayların sırası  
  
1.  Oturum hata ayıklama Yöneticisi'ni (SDM) çağırır [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) yöntemi.  
  
     Hata ayıklama (DE) altyapısı işlem modelini temel alan `IDebugProgramNodeAttach2::OnAttach` yöntemi ne olacağını belirler aşağıdaki yöntemlerden birini döndürür.  
  
     Varsa `S_FALSE` döndürülür, hata ayıklama altyapısı başarıyla bağlı programa. Aksi takdirde, [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md) yöntemi ekleme işlemi tamamlamak için çağrılır.  
  
     Varsa `S_OK` döndürülür DE olan SDM aynı işlemde yüklenecek. SDM aşağıdaki görevleri gerçekleştirir:  
  
    1.  Çağrıları [GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) DE altyapısı bilgi almak için.  
  
    2.  DE birlikte oluşturur.  
  
    3.  Çağrıları [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md).  
  
2.  DE gönderir bir [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) ile SDM için bir `EVENT_SYNC` özniteliği.  
  
3.  DE gönderir bir [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) ile SDM için bir `EVENT_SYNC` özniteliği.  
  
4.  DE gönderir bir [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) ile SDM için bir `EVENT_SYNC_STOP` özniteliği.  
  
 Bir programdan ayırma basit, iki adımlı işlem aşağıdaki gibidir:  
  
1.  SDM çağrıları [ayırma](../../extensibility/debugger/reference/idebugprogram2-detach.md).  
  
2.  DE gönderir bir [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arama hata ayıklayıcı olayları](../../extensibility/debugger/calling-debugger-events.md)