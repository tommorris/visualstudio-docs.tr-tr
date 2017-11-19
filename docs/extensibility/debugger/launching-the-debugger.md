---
title: "Hata ayıklayıcıyı başlatma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], launching the debugger
- debugger [Debugging SDK], launching
ms.assetid: f24da1a1-f923-48b4-989f-18a22b581d1b
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 23fd772b74c4caafbde37541933c38e306f9dc75
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="launching-the-debugger"></a>Hata ayıklayıcıyı başlatma
Hata ayıklayıcıyı başlatma yöntemleri ve bunların uygun öznitelikler olaylarla doğru sırasını gönderilmesi gerekir.  
  
## <a name="sequences-of-methods-and-events"></a>Dizileri yöntemleri ve olayları  
  
1.  Oturum hata ayıklama Yöneticisi'ni (SDM) seçerek adlı **hata ayıklama** menüsüne ve ardından seçme **Başlat**. Bkz: [bir Program başlatma](../../extensibility/debugger/launching-a-program.md) daha fazla bilgi için.  
  
2.  SDM çağrıları [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) yöntemi.  
  
3.  Hata ayıklama (DE) altyapısı işlem modelini temel alan `IDebugProgramNodeAttach2::OnAttach` yöntemi ne olacağını belirler aşağıdaki yöntemlerden birini döndürür.  
  
     Varsa `S_FALSE` döndürülür, hata ayıklama (DE) altyapısıdır belirten sanal makine yüklenecek.  
  
     veya  
  
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
 [Bir Program başlatma](../../extensibility/debugger/launching-a-program.md)