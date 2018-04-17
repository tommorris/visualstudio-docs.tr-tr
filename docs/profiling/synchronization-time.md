---
title: Eşitleme zamanı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.synchronization
helpviewer_keywords:
- Concurrency Visualizer, Synchronization Time
ms.assetid: affa04cc-8bba-4848-9301-b19846d3c2cb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c6d30e0f32c21149bd51236dd7a6c23a1e48b85c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="synchronization-time"></a>Eşitleme Zamanı
Bu kesimler çizelgesinde eşitlemesi kategorilere kez engelleme ile ilişkilendirilir. Bir iş parçacığı eşitleme engellendi olarak işaretlendiğinde, bunlardan birini kapsanır:  
  
-   İş parçacığı yürütülmesi iyi bilinen iş parçacığı eşitleme API çağrıda gibi neden olmuş olabilir `EnterCriticalSection()` veya `WaitForSingleObject()`.  
  
-   API eşleştirme algoritması tamamen kapsamlı olamaz ve eşitleme olan ilkel engelleyen bir temel çekirdek ulaşıldığı çağrı çerçevede yığın çünkü sonunda bu nedenle diğer kategorilere eşleştirilebilir bazı API'leri de görünebilir Bu kategoriyi eşlenmiş.  
  
 Bir iş parçacığı engelleme olayı temel nedeni anlamak için profil raporları ve engelleme çağrı yığınları dikkatle inceleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş Parçacıkları Görünümü](../profiling/threads-view-parallel-performance.md)