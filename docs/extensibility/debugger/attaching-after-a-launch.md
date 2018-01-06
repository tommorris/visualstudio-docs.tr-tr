---
title: "Başlatma ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debug engines, attaching to programs
ms.assetid: 5a3600a1-dc20-4e55-b2a4-809736a6ae65
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 890023b8336f130cf3b8cfcfe640da46af9cf0d1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="attaching-after-a-launch"></a>Başlatma sonra ekleme
Bir program başlatıldıktan sonra hata ayıklama oturumu konusu program için hata ayıklama altyapısı (DE) eklemek hazırdır.  
  
## <a name="design-decisions"></a>Tasarım kararları  
 İletişim paylaşılan bir adres alanı içinde daha kolay olduğundan, hata ayıklama oturumu ve DE arasında ya da DE ve program arasındaki iletişimi kolaylaştırmak için daha fazla mantıklıdır olup olmadığını karar vermeniz gerekir. Aşağıdakiler arasında seçim yapın:  
  
-   Hata ayıklama oturumu DE arasındaki iletişimi kolaylaştırmak için daha fazla bir mantıklı, hata ayıklama oturumu DE birlikte oluşturur ve programa eklemek için DE ister. Bu hata ayıklama oturumu ve DE birlikte bir adres alanı ve çalışma zamanı ortamı ve programı başka bir araya bırakır.  
  
-   Daha sonra DE ve program arasındaki iletişimi kolaylaştırmak için daha fazla bir mantıklı, çalışma zamanı ortamı birlikte DE oluşturur. Bu, bir adres alanındaki SDM ve DE, çalışma zamanı ortamı ve programı başka bir araya bırakır. Tipik bir komut dosyası dilleri çalıştırmak için bir yorumlayıcı uygulanan bir DE budur.  
  
    > [!NOTE]
    >  Ne DE programa iliştirir uygulama bağlıdır. Aygıtların ve program arasındaki iletişim de uygulama bağlıdır.  
  
## <a name="implementation"></a>Uygulama  
 Program aracılığıyla, ne zaman oturum hata ayıklama Yöneticisi'ni (SDM) ilk alır [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) başlatılacak programı temsil eden nesne çağırır [Attach](../../extensibility/debugger/reference/idebugprogram2-attach.md) yöntemi, onu bir [ IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md) sonraki nesne geri SDM için hata ayıklama olayları geçirmek için kullanılan. `IDebugProgram2::Attach` Sonra yöntemi çağırır [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) yöntemi. Nasıl aldığı SDM hakkında daha fazla bilgi için `IDebugProgram2` arabirim için bkz: [bağlantı noktası bildiren](../../extensibility/debugger/notifying-the-port.md).  
  
 Sizin DE DE bir betik çalıştırarak yorumlayıcı parçası olduğundan, genellikle ayıklanacak program aynı adres alanında çalıştırması gerekiyorsa `IDebugProgramNodeAttach2::OnAttach` yöntemi döndürür `S_FALSE`, attach işleminin tamamlandığını gösteren.  
  
 DE SDM adres alanında çalıştırıyorsa, diğer yandan, `IDebugProgramNodeAttach2::OnAttach` yöntemi döndürür `S_OK` veya [IDebugProgramNodeAttach2](../../extensibility/debugger/reference/idebugprogramnodeattach2.md) arabirimi hiç üzerinde uygulanmadı [IDebugProgramNode2 ](../../extensibility/debugger/reference/idebugprogramnode2.md) ayıklanacak programla ilişkili nesne. Bu durumda, [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md) yöntemi ekleme işlemi tamamlamak için sonunda çağrılır.  
  
 İkinci durumda, çağırmalısınız [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md) yöntemi `IDebugProgram2` geçirilmedi nesne `IDebugEngine2::Attach` yöntemi, depolama `GUID` yerel programında nesne ve bu iade `GUID` zaman `IDebugProgram2::GetProgramId` yöntemi bu nesne üzerinde daha sonra çağrılır. `GUID` Program çeşitli hata ayıklama bileşenler genelinde benzersiz şekilde tanımlamak için kullanılır.  
  
 Durumunda unutmayın `IDebugProgramNodeAttach2::OnAttach` döndürme yöntemi `S_FALSE`, `GUID` program için kullanılacak bu yönteme geçirilen ve bu `IDebugProgramNodeAttach2::OnAttach` ayarlar yöntemi `GUID` yerel program nesne üzerinde.  
  
 DE artık program ve herhangi bir başlangıç olayı göndermeye hazır eklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Doğrudan bir programını ekleme](../../extensibility/debugger/attaching-directly-to-a-program.md)   
 [Bağlantı noktası bildirme](../../extensibility/debugger/notifying-the-port.md)   
 [Hata ayıklama görevleri](../../extensibility/debugger/debugging-tasks.md)   
 [IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)   
 [Ekleme](../../extensibility/debugger/reference/idebugprogram2-attach.md)   
 [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [IDebugProgramNodeAttach2](../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md)