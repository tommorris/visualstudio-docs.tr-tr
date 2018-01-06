---
title: "Ek başlatma tabanlı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines, launching
- debug engines, attaching to programs
ms.assetid: 362f00ac-1909-4a3a-bacb-c0ceb5549816
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d05f0b8d8fd0190391da831351b65d873eac4efc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="launch-based-attachment"></a>Ek başlatma tabanlı
Ek bir program başlatma tabanlı otomatik olarak yapılır. Program barındırma işlemi tarafından SDM başlatıldığında, başlatma tabanlı eki el ile ek yöntemi için benzer bir yol izler. Bilgi için bkz: [programını ekleme](../../extensibility/debugger/attaching-to-the-program.md).  
  
## <a name="the-attaching-process"></a>Düğmelere işlemi  
 Aşağıdaki olaylar dizisi ana farktır **Attach** gibi çağırın:  
  
1.  Gönderme bir **IDebugEngineCreateEvent2** SDM olay nesnesine. Ayrıntılar için bkz [gönderme olayları](../../extensibility/debugger/sending-events.md).  
  
2.  Çağrı `IDebugProgram2::GetProgramId` yöntemi **IDebugProgram2** arabirimi geçirilen **Attach** yöntemi.  
  
3.  Gönderme bir **IDebugProgramCreateEvent2** SDM bildirmek için olay nesnesi, yerel **IDebugProgram2** nesne program için DE temsil etmek için oluşturuldu.  
  
4.  Gönderme bir [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) yeni bir iş parçacığı başlatılan işlem için oluşturduğunuz SDM bildirmek için olay nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gerekli olayları gönderme](../../extensibility/debugger/sending-the-required-events.md)   
 [Bir Programı Hataları Ayıklanacak Şekilde Etkinleştirme](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)