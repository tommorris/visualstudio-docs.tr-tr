---
title: "Özet görünümü - .NET bellek verileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Summary view
ms.assetid: 0cb317c3-0ae6-4531-aaa8-447576eec037
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: c0223950fb5082c84de8026cb07778d1f7381a33
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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