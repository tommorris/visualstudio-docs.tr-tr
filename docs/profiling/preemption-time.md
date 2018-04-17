---
title: Önalım zamanı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.preemption
helpviewer_keywords:
- Concurrency Visualizer, Preemption Time
ms.assetid: 6b78f91e-a006-440c-83fb-e7368040951d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 95c313026fee449d0420543fbc139d0365a63cf8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="preemption-time"></a>Önalım Zamanı
Bu kesimler çizelgesinde Önalım kategorilere engelleme zamanı ile ilişkilendirilmiş. Bu kategori, bir iş parçacığı çıkış nedeni aşağıdakilerden biri nedeniyle anahtarlanır olduğunu anlamına gelir:  
  
-   Zamanlayıcı daha yüksek bir öncelik iş parçacığı kullanarak değiştirildi.  
  
-   İş parçacığının yürütme Zamanlayıcının süresi ve diğer iş parçacıkları yürütmek hazır.  
  
 Bu süre boyunca, bir iş parçacığı eşzamanlılık görselleştiricisi Önalım sayım çekirdek bekleme nedeni tarafından engellendi. Önalım kesimleri mantıksal çekirdek dışında bir iş parçacığı gönderildiğinde başlamalı ve o iş parçacığı yürütme devam ettiğinde bitmelidir.  
  
 Preempted bir kesim için araç ipucu önalım neden iş parçacığı ve işlem adını görüntüler. Ancak, bu işlem veya sürdü üzerinden iş parçacığı gerçekten preempted dönem çalıştığını göstermez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş Parçacıkları Görünümü](../profiling/threads-view-parallel-performance.md)