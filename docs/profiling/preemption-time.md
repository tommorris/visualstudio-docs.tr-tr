---
title: "Önalım zamanı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.threads.timeline.preemption
helpviewer_keywords: Concurrency Visualizer, Preemption Time
ms.assetid: 6b78f91e-a006-440c-83fb-e7368040951d
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 447229fd3eeb0ded2b8d6ec56716c4ec95c36661
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="preemption-time"></a>Önalım Zamanı
Bu kesimler çizelgesinde Önalım kategorilere engelleme zamanı ile ilişkilendirilmiş. Bu kategori, bir iş parçacığı çıkış nedeni aşağıdakilerden biri nedeniyle anahtarlanır olduğunu anlamına gelir:  
  
-   Zamanlayıcı daha yüksek bir öncelik iş parçacığı kullanarak değiştirildi.  
  
-   İş parçacığının yürütme Zamanlayıcının süresi ve diğer iş parçacıkları yürütmek hazır.  
  
 Bu süre boyunca, bir iş parçacığı eşzamanlılık görselleştiricisi Önalım sayım çekirdek bekleme nedeni tarafından engellendi. Önalım kesimleri mantıksal çekirdek dışında bir iş parçacığı gönderildiğinde başlamalı ve o iş parçacığı yürütme devam ettiğinde bitmelidir.  
  
 Preempted bir kesim için araç ipucu önalım neden iş parçacığı ve işlem adını görüntüler. Ancak, bu işlem veya sürdü üzerinden iş parçacığı gerçekten preempted dönem çalıştığını göstermez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş Parçacıkları görünümü](../profiling/threads-view-parallel-performance.md)