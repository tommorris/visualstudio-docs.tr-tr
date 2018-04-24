---
title: Boş zaman çizelgesi segmenti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.empty
helpviewer_keywords:
- Concurrency Visualizer, empty timeline segment
ms.assetid: f37b301f-3edc-4e56-8084-feec2dc5a9b1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f45306283d6aaa2346b121455cca398e918b66e2
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="empty-timeline-segment"></a>Boş Zaman Çizelgesi Segmenti
Eşzamanlılık görselleştiricisi, bir zaman çizelgesi boş bölümüdür nedeni de (beyaz bir arka plana sahip) kanal türüne bağlıdır.  
  
-   CPU iş parçacığı kanal için bu iş parçacığı zaman çizelgesi bu kısmı sırasında yoktu anlamına gelir. İş parçacığında düşünüyorsanız yakınlaştırma denetimini kullanarak veya yatay kaydırma yürütülen bölümünde bulabilirsiniz.  
  
-   Bir g/ç kanalı için hiçbir disk erişimi zamandaki o noktada hedef işlem adına oluştu anlamına gelir.  
  
-   DirectX kanalı için hiçbir GPU iş zaman çizelgesi bu kısmı sırasında hedef işlem adına gerçekleştirilip gerçekleştirilmediğine anlamına gelir.  
  
-   İşaretçi kanalı için hiçbir işaretçileri oluşturulan anlamına gelir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş Parçacıkları görünümü](../profiling/threads-view-parallel-performance.md)   
 [Yakınlaştırma Denetimi (İş Parçacıkları Görünümü)](../profiling/zoom-control-threads-view.md)