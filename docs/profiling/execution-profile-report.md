---
title: "Yürütme Profil raporu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.cv.threads.report.execution
helpviewer_keywords: Concurrency Visualizer, Execution Profile Report
ms.assetid: c8128472-a8ed-46f4-b1c8-a25358d6f2c1
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 263ff80703a680ab799e373fad62c05ced62028f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="execution-profile-report"></a>Yürütme Profil Raporu
Yürütme Profil raporu geleneksel örnekleme profilidir. Örnekler, ne zaman bir iş parçacığı bir mantıksal çekirdeği üzerinde çalıştığından ve örnek yığınları birikmiş kümesini harmanlama tarafından tipik çağrı ağacı eşzamanlılık görselleştiricisi oluşturur dönemlerde yaklaşık her milisaniyelik alınır. Bu tablodaki verileri uygulanabilir bu filtreler ve geçerli zaman aralığı ve gizli iş parçacıkları tarafından etkilenebilir:  
  
-   Sadece kendi kodumu seçili ise, kullanıcı kodu yanı sıra, bir düzey altındaki kullanıcı kodu sahip yığın çerçeveleri gösterilir.  
  
-   Gürültü azaltma değeri ayarlarsanız, raporun dışında belirtilen sıklığı filtrelenir daha az sahip yığınları Harmanlanmış  
  
 Aşağıdaki tablo sütunları raporda gösterir.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|Ad|İşlev adı her düzeyi için çağrı yığını.|  
|Kapsayıcı örnekleri|Bu çağrı yığını ağacı düzeyi biriken tüm yığınları için toplanan örnek toplam sayısı. Bu işlev için özel kullanım örnekleri ve tüm alt düğümleri dahil sayaçları toplamını (bunlar dahil) sayıdır.|  
|Özel örnekleri|Bu işlev çağrı yığını en düşük düzeyde olduğu toplanan örnek toplam sayısı.|  
|% (Bunlar dahil)|Kapsayıcı örnekleri sütununda gösterilen toplam örnekleri yüzdesi. Yüzde iki ondalık basamağa yuvarlanır.|  
|% Özel|Özel örnekleri sütununda gösterilen toplam örnekleri yüzdesi. Yüzde iki ondalık basamağa yuvarlanır.|  
|Ayrıntılar|İşlev tam adı. Kullanılabilir olduğunda bu satır sayısını içerir.|  
  
 Bu raporu tablosu görülebilir [yürütme zamanı (iş parçacıkları görünümü)](../profiling/execution-time-threads-view.md) görünümü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş Parçacıkları Görünümü](../profiling/threads-view-parallel-performance.md)