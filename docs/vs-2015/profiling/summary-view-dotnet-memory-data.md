---
title: Özet görünümü - .NET bellek verisi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Summary view
ms.assetid: 0cb317c3-0ae6-4531-aaa8-447576eec037
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2fec21552486290dbea05c07490fabbcf38feb02
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694965"
---
# <a name="summary-view---net-memory-data"></a>Özet görünümü - .NET bellek verileri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Özet görünümü - .NET bellek verileri](https://docs.microsoft.com/visualstudio/profiling/summary-view-dotnet-memory-data).  
  
Özet görünümü .NET işlevleri ve en çok bellek ayrılmış türler ve çoğu zaman bir çalıştırma profil oluşturulan türler hakkında bilgi görüntüler. Rapor listeler ve bildirim bağlantıları açıklamasını dahil olmak üzere daha fazla bilgi için bkz. [özeti görünümünü](../profiling/summary-view.md).  
  
## <a name="timeline-graph"></a>Zaman Çizelgesi grafiği  
 Özet görünümü zaman çizelgesi grafikte, profili oluşturulan uygulamanın profil oluşturma gerçekleşen zaman tarafından işlemci (CPU) kullanımı gösterir. Seçili zaman aralığı için görünüme filtre uygulamak için zaman çizelgesi Grafiği'ni kullanabilirsiniz. Daha fazla bilgi için [nasıl yapılır: Özet zaman çizelgesinden rapor görünümlerini filtreleme](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
## <a name="functions-allocating-most-memory"></a>En çok bellek ayrılan İşlevler  
 En yüksek sayıda bayt profil oluşturma çalıştırmasını bellek ayrılan işlevler listelenir.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|İşlevin adı.|  
|**Bayt yüzdesi**|Bu işlev tarafından çağırılan bir alt işlevi veya bu işlev tarafından ayrılan profil oluşturma, tüm ayrılmış baytların yüzdesi.|  
  
## <a name="types-with-most-memory-allocated"></a>En çok bellek ayrılmış türler  
 Profil oluşturma çalışmasında kendisi için en yüksek sayıda bayt bellek ayrılan türlerini listeler.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|Tür adı.|  
|**Bayt yüzdesi**|Bu tür için ayrılan profil oluşturma, tüm ayrılmış baytların yüzdesi.|  
  
## <a name="types-with-most-instances"></a>En çok örneği olan türler  
 Profil oluşturma çalışması sırasında en çok kez oluşturulan türlerini listeler. vardı  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|Tür adı.|  
|**Örnek sayısı yüzdesi**|Çalıştıran profil oluşturulan toplam sayı of.NET nesneleri yüzdesi bu türün örneklerinin yoktu.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özet görünümü](../profiling/summary-view-sampling-data.md)   
 [Özet Görünümü](../profiling/summary-view-instrumentation-data.md)



