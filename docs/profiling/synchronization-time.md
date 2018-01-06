---
title: "Eşitleme zamanı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.threads.timeline.synchronization
helpviewer_keywords: Concurrency Visualizer, Synchronization Time
ms.assetid: affa04cc-8bba-4848-9301-b19846d3c2cb
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8252bc569ef17725570b5222afa12a59c387c278
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="synchronization-time"></a>Eşitleme Zamanı
Bu kesimler çizelgesinde eşitlemesi kategorilere kez engelleme ile ilişkilendirilir. Bir iş parçacığı eşitleme engellendi olarak işaretlendiğinde, bunlardan birini kapsanır:  
  
-   İş parçacığı yürütülmesi iyi bilinen iş parçacığı eşitleme API çağrıda gibi neden olmuş olabilir `EnterCriticalSection()` veya `WaitForSingleObject()`.  
  
-   API eşleştirme algoritması tamamen kapsamlı olamaz ve eşitleme olan ilkel engelleyen bir temel çekirdek ulaşıldığı çağrı çerçevede yığın çünkü sonunda bu nedenle diğer kategorilere eşleştirilebilir bazı API'leri de görünebilir Bu kategoriyi eşlenmiş.  
  
 Bir iş parçacığı engelleme olayı temel nedeni anlamak için profil raporları ve engelleme çağrı yığınları dikkatle inceleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş Parçacıkları Görünümü](../profiling/threads-view-parallel-performance.md)