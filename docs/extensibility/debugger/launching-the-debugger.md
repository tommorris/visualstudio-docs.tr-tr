---
title: Hata ayıklayıcıyı başlatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], launching the debugger
- debugger [Debugging SDK], launching
ms.assetid: f24da1a1-f923-48b4-989f-18a22b581d1b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2606e0f6c7d5dfe17e4c82528c36b3f7cdc26c5e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31108936"
---
# <a name="launching-the-debugger"></a>Hata ayıklayıcıyı başlatma
Hata ayıklayıcıyı başlatma yöntemleri ve bunların uygun öznitelikler olaylarla doğru sırasını gönderilmesi gerekir.  
  
## <a name="sequences-of-methods-and-events"></a>Dizileri yöntemleri ve olayları  
  
1.  Oturum hata ayıklama Yöneticisi'ni (SDM) seçerek adlı **hata ayıklama** menüsüne ve ardından seçme **Başlat**. Bkz: [bir Program başlatma](../../extensibility/debugger/launching-a-program.md) daha fazla bilgi için.  
  
2.  SDM çağrıları [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) yöntemi.  
  
3.  Hata ayıklama (DE) altyapısı işlem modelini temel alan `IDebugProgramNodeAttach2::OnAttach` yöntemi ne olacağını belirler aşağıdaki yöntemlerden birini döndürür.  
  
     Varsa `S_FALSE` döndürülür, hata ayıklama (DE) altyapısıdır belirten sanal makine yüklenecek.  
  
     -veya-  
  
     Varsa `S_OK` döndürülür DE olan yüklenecek işlemdeki SDM biri. SDM sonra aşağıdaki görevleri gerçekleştirir:  
  
    1.  Çağrıları [GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) DE altyapısı bilgi almak için.  
  
    2.  DE birlikte oluşturur.  
  
    3.  Çağrıları [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md).  
  
4.  DE gönderir bir [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) ile SDM için bir `EVENT_SYNC` özniteliği.  
  
5.  DE gönderir bir [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) ile SDM için bir `EVENT_SYNC` özniteliği.  
  
6.  DE gönderir bir [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) ile SDM için bir `EVENT_SYNC` özniteliği.  
  
7.  DE gönderir bir [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) ile SDM için bir `EVENT_SYNC` özniteliği.  
  
8.  DE gönderir bir [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) ile SDM için bir `EVENT_SYNC` özniteliği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arama hata ayıklayıcı olayları](../../extensibility/debugger/calling-debugger-events.md)   
 [Program Başlatma](../../extensibility/debugger/launching-a-program.md)