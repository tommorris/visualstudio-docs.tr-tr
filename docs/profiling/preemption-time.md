---
title: Önalım zamanı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: 7ac7152ec663a0a7b7bbbeee5c30a38885623cb9
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35254765"
---
# <a name="preemption-time"></a>Önalım zamanı
Bu kesimler çizelgesinde Pre-emption kategorilere engelleme zamanı ile ilişkilendirilmiş. Bu kategori, bir iş parçacığı çıkış nedeni aşağıdakilerden biri nedeniyle anahtarlanır olduğunu anlamına gelir:  
  
-   Zamanlayıcı daha yüksek bir öncelik iş parçacığı kullanarak değiştirildi.  
  
-   İş parçacığının yürütme Zamanlayıcının süresi ve diğer iş parçacıkları yürütmek hazır.  
  
 Bu süre boyunca, bir iş parçacığı eşzamanlılık görselleştiricisi Pre-emption sayım çekirdek bekleme nedeni tarafından engellendi. Pre-emption kesimleri mantıksal çekirdek dışında bir iş parçacığı gönderildiğinde başlamalı ve o iş parçacığı yürütme çıktığında bitmelidir.  
  
 Araç İpucu biterse bir kesim için pre-emption neden iş parçacığı ve işlem adını görüntüler. Ancak, bu işlem veya sürdü üzerinden iş parçacığı gerçekten preempted dönem çalıştığını göstermez.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [İş Parçacıkları Görünümü](../profiling/threads-view-parallel-performance.md)