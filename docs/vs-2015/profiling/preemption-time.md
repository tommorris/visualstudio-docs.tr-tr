---
title: Önalım zamanı | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.preemption
helpviewer_keywords:
- Concurrency Visualizer, Preemption Time
ms.assetid: 6b78f91e-a006-440c-83fb-e7368040951d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 614b049bf7aa881ce4454d8f832190b0391ff342
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695985"
---
# <a name="preemption-time"></a>Önalım Zamanı
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Önalım zamanı](https://docs.microsoft.com/visualstudio/profiling/preemption-time).  
  
Bu segmentlerde faaliyet zaman çizelgesi Önalım kategorilere ayrılır engelleme zamanı ile ilişkilidir. Bu kategori, bir iş parçacığı çıkış aşağıdaki nedenlerden biri nedeniyle geçiş, gelir:  
  
-   Zamanlayıcı daha yüksek öncelikli iş parçacığı kullanarak değiştirildi.  
  
-   İş parçacığının yürütme kuantum süresi doldu ve diğer iş parçacıklarını yürütmek hazır.  
  
 Bu süre boyunca, bir iş parçacığı eşzamanlılık görselleştiricisi Önalım sayılıyor bir çekirdek bekleme nedeni tarafından engellendi. Önalım segmentler mantıksal çekirdek dışında bir iş parçacığı gönderildiğinde ve yürütme iş parçacığı devam ettiğinde bitmelidir.  
  
 Araç İpucu preempted kesimin önalım neden iş parçacığı ve işlem adını görüntüler. Ancak, bu üstlenmesinden iş parçacığı ve işlem gerçekten preempted dönem çalıştığını göstermez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş Parçacıkları Görünümü](../profiling/threads-view-parallel-performance.md)



