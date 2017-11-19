---
title: Programa ekleme | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debug engines, attaching to programs
ms.assetid: 9a3f5b83-60b5-4ef0-91fe-a432105bd066
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7dd4baed877bd5d0262e966edf006dea80596b47
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="attaching-to-the-program"></a>Programını ekleme
Uygun bağlantı noktası ile programlarınızı kaydettikten sonra hata ayıklayıcısı hata ayıklamak istediğiniz programın eklemelisiniz.  
  
## <a name="choosing-how-to-attach"></a>Nasıl ekleneceği seçme  
 Oturum hata ayıklama Yöneticisi'ni (SDM) ayıklanacak programın ekleme çalışır üç yolu vardır.  
  
1.  Hata ayıklama altyapıyı tarafından başlatılan program için [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) SDM yöntemi (tipik bir örnek için yorumlanan dilleri), alır [IDebugProgramNodeAttach2](../../extensibility/debugger/reference/idebugprogramnodeattach2.md) gelen arabirimi [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) için iliştirilmekte programla ilişkili nesne. SDM elde `IDebugProgramNodeAttach2` SDM arabirimini, çağırır ve ardından [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) yöntemi. `IDebugProgramNodeAttach2::OnAttach` Yöntemi döndürür `S_OK` programa eklemediniz ve diğer girişimleri programına eklemek için yapılabilir belirtmek için.  
  
2.  SDM elde [IDebugProgramEx2](../../extensibility/debugger/reference/idebugprogramex2.md) arabirim SDM çağrıları iliştirilmekte programdan [Attach](../../extensibility/debugger/reference/idebugprogramex2-attach.md) yöntemi. Bu yaklaşım bağlantı noktası sağlayıcı tarafından uzaktan başlatılan program için kullanılabilir.  
  
3.  Program aracılığıyla eklenemez, `IDebugProgramNodeAttach2::OnAttach` veya `IDebugProgramEx2::Attach` yöntemleri SDM yükler (henüz yüklü değilse) debug altyapısı çağırarak `CoCreateInstance` işlevi ve çağrıları [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md) yöntemi. Bu yaklaşım, yerel olarak bir bağlantı noktası tedarikçi tarafından başlatılan program için normaldir.  
  
     Ayrıca çağırmak özel bir bağlantı noktası tedarikçi için olası `IDebugEngine2::Attach` özel bir bağlantı noktası tedarikçi uyarlamasını yönteminde `IDebugProgramEx2::Attach` yöntemi. Genellikle bu durumda, özel bir bağlantı noktası tedarikçi uzak makinede hata ayıklama altyapısı başlatır.  
  
 Ek oturum hata ayıklama Yöneticisi'ni (SDM) çağırdığında elde [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md) yöntemi.  
  
 Ayıklanacak uygulamayla aynı işlemde sizin DE çalıştırmak sonra aşağıdaki yöntemlerinden birini uygulamalıdır [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md):  
  
-   [GetHostName](../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md),  
  
-   [GetHostPid](../../extensibility/debugger/reference/idebugprogramnode2-gethostpid.md)  
  
-   [GetProgramName](../../extensibility/debugger/reference/idebugprogramnode2-getprogramname.md)  
  
 Sonra `IDebugEngine2::Attach` yöntemi çağrıldığında, bu adımları uygulamanızda `IDebugEngine2::Attach` yöntemi:  
  
1.  Gönderme bir [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) SDM olay nesnesine. Daha fazla bilgi için bkz: [gönderme olayları](../../extensibility/debugger/sending-events.md).  
  
2.  Çağrı [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md) yöntemi [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) geçirilmedi nesne `IDebugEngine2::Attach` yöntemi.  
  
     Bu döndürür bir `GUID` program tanımlamak için kullanılır. `GUID` Nesne temsil yerel program için DE ve bunu ne zaman döndürülmelidir depolanmalıdır `IDebugProgram2::GetProgramId` yöntemi çağrıldığında `IDebugProgram2` arabirimi.  
  
    > [!NOTE]
    >  Öğesini uygularsanız `IDebugProgramNodeAttach2` arabirim, programın `GUID` geçirilir `IDebugProgramNodeAttach2::OnAttach` yöntemi. Bu `GUID` programın için kullanılan `GUID` tarafından döndürülen `IDebugProgram2::GetProgramId` yöntemi.  
  
3.  Gönderme bir [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) SDM bildirmek için olay nesnesi, yerel `IDebugProgram2` nesne program için DE temsil etmek için oluşturuldu. Ayrıntılar için bkz [gönderme olayları](../../extensibility/debugger/sending-events.md).  
  
    > [!NOTE]
    >  Bu aynı değil `IDebugProgram2` içine geçirildi nesne `IDebugEngine2::Attach` yöntemi. Daha önce geçirilen `IDebugProgram2` nesne yalnızca bağlantı noktası tarafından tanınmıyor ve ayrı bir nesnedir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ek başlatma tabanlı](../../extensibility/debugger/launch-based-attachment.md)   
 [Gönderen olaylar](../../extensibility/debugger/sending-events.md)   
 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md)   
 [IDebugProgramNodeAttach2](../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)   
 [IDebugProgramEx2](../../extensibility/debugger/reference/idebugprogramex2.md)   
 [Ekleme](../../extensibility/debugger/reference/idebugprogramex2-attach.md)   
 [Ekleme](../../extensibility/debugger/reference/idebugengine2-attach.md)