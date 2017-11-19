---
title: "Başlangıç olayları başlatma gönderme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], startup events
ms.assetid: 306ea0b4-6d9e-4871-8d8d-a4032d422940
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0620821ec908deed2c57ddfefb40763a48fd2074
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sending-startup-events-after-a-launch"></a>Başlangıç olayları başlatma gönderme
Hata ayıklama altyapısı (DE) programına bağlandıktan sonra geri hata ayıklama oturumu için başlangıç olayları bir dizi gönderir.  
  
 Hata ayıklama oturumu gönderilen başlangıç olayları aşağıdakileri içerir:  
  
-   Bir altyapı oluşturma olay.  
  
-   Bir program oluşturma olayı.  
  
-   Oluşturma ve modülü yük olaylarını iş parçacığı.  
  
-   Kodu yüklenmiş ve çalıştırılmaya hazır olduğunda, ancak herhangi bir kod yürütülmeden önce gönderilen bir yükleme tam olayı  
  
    > [!NOTE]
    >  Bu olay devam ettirildiğinde, genel değişkenler başlatılır ve başlangıç yordamları çalıştırma.  
  
-   Olası diğer iş parçacığı oluşturma ve modül yük olaylar.  
  
-   Program kendi ana giriş noktası gibi ulaştı sinyalleri bir giriş noktası olay **ana** veya `WinMain`. DE zaten çalışan bir program bağlanıyorsa bu olay genellikle gönderilmez.  
  
 Programlı olarak DE oturum hata ayıklama Yöneticisi'ni (SDM) ilk kez gönderir bir [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) altyapısı oluşturma olaya temsil eder, arabirim arkasından bir [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) , bir program oluşturma olayı temsil eder.  
  
 Bu genellikle bir veya daha fazla izlenir [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) iş parçacığı oluşturma olayları ve [IDebugModuleLoadEvent2](../../extensibility/debugger/reference/idebugmoduleloadevent2.md) modülü yük olaylarını.  
  
 Kod yüklenmiş ve çalıştırılmaya hazır olduğundan, ancak herhangi bir kod yürütülmeden önce DE SDM gönderir bir [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) yük complete olayını. Son olarak, program zaten çalışmıyorsa DE gönderir bir [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) program kendi ana giriş noktası ulaştı ve hata ayıklama için hazır sinyal giriş noktası olay.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yürütme denetimi](../../extensibility/debugger/control-of-execution.md)   
 [Hata ayıklama görevleri](../../extensibility/debugger/debugging-tasks.md)