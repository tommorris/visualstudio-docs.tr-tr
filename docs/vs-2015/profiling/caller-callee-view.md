---
title: Arayan-Aranan görünümü | Microsoft Docs
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
- vs.performance.view.callercallee
helpviewer_keywords:
- profiling tools, reports, Caller/Callee view
- profiling tools, Caller/Callee view
- performance reports, Caller/Callee view
- Caller/Callee view
ms.assetid: d3511bcf-cce0-4cbe-aecb-b94c7c80ad1b
caps.latest.revision: 37
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a28f0184d126781c43540d447cd75cd905e15d40
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634391"
---
# <a name="callercallee-view"></a>Arayan/Aranan görünümü
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [arayan-Aranan görünümü](https://docs.microsoft.com/visualstudio/profiling/caller-callee-view).  
  
Arayan/Aranan görünümü seçili işlev ve üst ve alt işlevleri için profil bilgilerini görüntüler. Arayan/Aranan görünümü üç Kılavuzlar içerir:  
  
 **Geçerli işlev** Orta Kılavuz ve bunun görüntülenen bilgi seçili işlev için profil oluşturmayı gösterir. Değerler, toplanan tüm işlev çağrıları profil oluşturma çalışması içerir.  
  
 **Geçerli işlevi çağırmış işlevler** üst kılavuz görüntülenir ve çağıran (üst) işlevi'öğesinden gelen çağrılar tarafından oluşturulan değerleri seçili (geçerli) işlevinin sayısını gösterir.  
  
 **Geçerli işlev tarafından çağrılan işlevler** alt kılavuz ve bunun görüntülenen geçerli işlev tarafından alt işlev çağrıldığında çağrılan (alt) işlevleri için seçili işlev bilgileri profil oluşturma gösterilmektedir.  
  
 Çağıran/çağrılan Görünümü'nde kullanılabilir olan sütunlarda veri toplamak için kullanılan profil oluşturma yöntemine (örnekleme veya Araçlar) bağlıdır ve .NET bellek verileri profil oluşturma çalışmasında toplanan açmasa da Çalıştır.  
  
 Rapor görünümü Orta kısmındaki geçerli işlevin herhangi bir görünümün diğer iki bölümü listelenen işlevlerin çift tıklayarak gereken farklı işlevi seçebilirsiniz. Rapor görünümü, değişiklikleri yansıtacak şekilde otomatik olarak güncelleştirilir.  
  
 Sütun adları tıklayarak verileri yeniden sıralayabilirsiniz. Ek sütunları çağıran/çağrılan görünümü eklenebilir. Daha fazla bilgi için [nasıl yapılır: rapor görünümü sütunlarını özelleştirme](../profiling/how-to-customize-report-view-columns.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arayan / Aranan görünümü - örnekleme verileri](../profiling/caller-callee-view-sampling-data.md)   
 [Arayan/Aranan görünümü - izleme verileri](../profiling/caller-callee-view-instrumentation-data.md)   
 [Arayan/Aranan görünümü - .NET bellek izleme verileri](../profiling/caller-callee-view-net-memory-instrumentation-data.md)   
 [Arayan/Aranan görünümü - .NET bellek örnekleme verileri](../profiling/caller-callee-view-dotnet-memory-sampling-data.md)   
 [Arayan / Aranan görünümü - çakışma verileri](../profiling/caller-callee-view-contention-data.md)



