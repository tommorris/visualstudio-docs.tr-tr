---
title: "Yürütme zamanı (iş parçacıkları görünümü) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.execution
helpviewer_keywords:
- Concurrency Visualizer, Execution Time (Threads View)
ms.assetid: 80c100f8-2502-4613-bfef-4f4f2e09cc8d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 91fda110b3bf73b59d7c9d7d8ff6f7226f9ec5fa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="execution-time-threads-view"></a>Yürütme Zamanı (İş Parçacıkları Görünümü)
İş parçacığının etkin bir sistemde mantıksal çekirdek çalışma yaparken bu kesimler iş parçacıkları görünümü zaman çizelgesi yürütme zamanı temsil eder.  
  
 İş parçacığı durumu değişiklikleri çekirdek içerik anahtarı olayları algılanır. Olay izleme için Windows (ETW) örnek yığınları her milisaniyelik yakalar. Çok kısa yeşil kesimdeki hiçbir örnek alınır mümkündür. Bu nedenle, bazı kısa yürütme kesimleri hiçbir çağrı yığını gösterebilir.  
  
 Bir yürütme kesimi tıklattığınızda eşzamanlılık görselleştiricisi tıklatın konumuna yakın örnek yığını görüntüler. Bu örnek yığını konumunu siyah bir ok tarafından gösterilen ya da üzerini zaman çizelgesi ve örnek yığını düzeltme işareti görünür **geçerli** sekmesi.  
  
 Geçerli görünümdeki tüm yürütme süresini geleneksel örnekleme profili görmek için tıklatın **yürütme** görünür zaman çizelgesi profilinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yürütme Profil raporu](../profiling/execution-profile-report.md)   
 [İş Parçacıkları Görünümü](../profiling/threads-view-parallel-performance.md)