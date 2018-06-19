---
title: Ek başlatma tabanlı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, launching
- debug engines, attaching to programs
ms.assetid: 362f00ac-1909-4a3a-bacb-c0ceb5549816
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 892518cc92286f9415e39c96b6ed2afa8eb0d792
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31099382"
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