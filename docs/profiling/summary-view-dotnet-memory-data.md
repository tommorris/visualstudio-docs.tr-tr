---
title: Özet görünümü - .NET bellek verileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Summary view
ms.assetid: 0cb317c3-0ae6-4531-aaa8-447576eec037
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 1df9005224a583dae06774a4394bcd68bdd1621c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="summary-view---net-memory-data"></a>Özet görünümü - .NET bellek verileri
Özet görünümü .NET işlevleri ve en fazla belleği tahsis türleri ve profil çalıştırmak çoğu kez oluşturulan türleri hakkındaki bilgileri görüntüler. Bildirim bağlantıları ve rapor listeler açıklaması dahil olmak üzere daha fazla bilgi için bkz: [özeti görünümü](../profiling/summary-view.md).  
  
## <a name="timeline-graph"></a>Zaman Çizelgesi grafiği  
 Özet görünümü zaman çizelgesi grafiğinde profil oluştu zamanla profili uygulama tarafından işlemci (CPU) kullanımını gösterir. Seçilen zaman aralığı görünümüne filtrelemek için zaman çizelgesi grafik kullanabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Özet zaman çizelgesi filtre rapor görünümleri](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
## <a name="functions-allocating-most-memory"></a>Çoğu bellek ayırma işlevleri  
 Profil oluşturma çalıştırmada belleğin bayt en fazla sayıda ayrılan işlevleri listeler.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|İşlevin adı.|  
|**Bayt %**|Bu işlev tarafından çağrıldı alt işlev veya bu işlevi tarafından ayrılan çalıştırmak profil tüm ayrılmış bayt yüzdesi.|  
  
## <a name="types-with-most-memory-allocated"></a>Ayrılan en fazla belleği türleriyle  
 Profil çalıştırmak için en fazla sayıda belleğin bayt ayrılan türlerini listeler.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|Tür adı.|  
|**Bayt %**|Bu tür için ayrılan çalıştırmak profil tüm ayrılmış bayt yüzdesi.|  
  
## <a name="types-with-most-instances"></a>Çoğu durumda türleriyle  
 Çalıştırma profili oluşturma sırasında en çok kez oluşturulan türlerini listeler. vardı  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|Tür adı.|  
|**Örnekleri %**|Profil çalıştırdığınızda oluşturulan toplam sayı of.NET nesneleri yüzdesi, bu türdeki örneklerin yoktu.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özet görünümü](../profiling/summary-view-sampling-data.md)   
 [Özet Görünümü](../profiling/summary-view-instrumentation-data.md)