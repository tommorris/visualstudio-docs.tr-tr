---
title: Başlatmadan sonra Başlangıç olaylarını gönderme | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], startup events
ms.assetid: 306ea0b4-6d9e-4871-8d8d-a4032d422940
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 21b98fccac32b50e6aec643a7b69832e65d53dd8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686535"
---
# <a name="sending-startup-events-after-a-launch"></a>Başlatmadan Sonra Başlangıç Olaylarını Gönderme
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [gönderme başlangıç olayları sonra bir başlatma](https://docs.microsoft.com/visualstudio/extensibility/debugger/sending-startup-events-after-a-launch).  
  
Programın hata ayıklama altyapısı (DE) bağlandıktan sonra hata ayıklama oturumu başlatma olay serisi olarak gönderir.  
  
 Hata ayıklama oturumu gönderildi başlangıç olayları aşağıdakileri içerir:  
  
-   Bir altyapı oluşturma olayı.  
  
-   Bir program oluşturma olayı.  
  
-   Oluşturma ve modül yükleme olayları iş parçacığı.  
  
-   Kod yüklenmiş ve çalıştırılmaya hazır olduğunda, ancak herhangi bir kod yürütülmeden önce gönderilen bir yük tamamlama olayı  
  
    > [!NOTE]
    >  Bu olay devam ettirildiğinde, genel değişkenler başlatılır ve başlangıç yordamları çalıştırın.  
  
-   Diğer olası iş parçacığı oluşturma ve modül yükleme olayları.  
  
-   Program, ana girdi noktası gibi ulaştı sinyalleri bir giriş noktası olayı **ana** veya `WinMain`. Zaten çalışan bir programa DE bağlanıyorsa bu olay genellikle gönderilmez.  
  
 Programlı olarak DE oturum hata ayıklama Yöneticisi (SDM) ilk kez gönderir bir [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) bir altyapı oluşturma olayı temsil eder, arabirim, arkasından bir [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) , bir program oluşturma olayı temsil eder.  
  
 Bu genellikle bir veya daha fazla takip [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) iş parçacığı oluşturma olayları ve [IDebugModuleLoadEvent2](../../extensibility/debugger/reference/idebugmoduleloadevent2.md) Modül yükleme olayları.  
  
 Yüklenmiş ve çalıştırılmaya hazır kodudur, ancak herhangi bir kod yürütülmeden önce DE SDM gönderir. bir [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) yük tamamlama olayı. Son olarak, program zaten çalışmıyorsa DE gönderdiği bir [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) program, ana girdi noktası sınırına ulaştı ve hata ayıklama için hazır olarak giriş noktası olayı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yürütme denetimi](../../extensibility/debugger/control-of-execution.md)   
 [Hata Ayıklama Görevleri](../../extensibility/debugger/debugging-tasks.md)

