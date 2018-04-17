---
title: Özet görünümü - izleme verileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Summary view
ms.assetid: 0a3b3a1f-e22b-4ac8-b46e-71694e9b2cf1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aab14955e24830b2b6add0d375e4c0dd76fd43ec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="summary-view---instrumentation-data"></a>Özet görünümü - izleme verileri
Özet görünümü, bir çalıştırma profil en performans pahalı işlevleri hakkında bilgi görüntüler. Bildirim bağlantıları ve rapor listeler açıklaması dahil olmak üzere daha fazla bilgi için bkz: [özeti görünümü](../profiling/summary-view.md).  
  
## <a name="timeline-graph"></a>Zaman Çizelgesi grafiği  
 Özet görünümü zaman çizelgesi grafiğinde profil oluştu zamanla profili uygulama tarafından işlemci (CPU) kullanımını gösterir. Seçilen zaman aralığı görünümüne filtrelemek için zaman çizelgesi grafik kullanabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Özet zaman çizelgesi filtre rapor görünümleri](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
## <a name="hot-path"></a>Sık kullanılan yolu  
 **Etkin yolunuzda** en uzun süre tüketilen yürütme yolunu görüntüler. İşlev için işlev ayrıntıları görüntülemek için bir işlev tıklatabilirsiniz. İçin işlevi sağ işlevi için diğer görünümleri görüntülemek ve sonra listeden bir görünümü tıklatın.  
  
 **Etkin yolunuzda** her işlevi için aşağıdaki veriler içerir:  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|İşlevin adı.|  
|**Geçen dahil süre %**|İşlev gövdesi ve adlı işlevleri yürütülen kod işlevi harcadığı profil oluşturma veri tüm zamanı yüzdesi.|  
|**Özel geçen süre %**|İşlev, işlev gövdesi içinde kod çalıştırırken harcadığı profil oluşturma veri tüm zamanı yüzdesi. İşlevi çağrıldığında işlevlerde geçen süre dahil değildir.|  
  
## <a name="functions-with-most-individual-work"></a>Ayrı ayrı çoğu iş işlevleri  
 Çoğu zaman yürütülen kod işlevinin gövdesini ve değil adlı işlevleri tüketilen işlevlerin listesi.  
  
 **En tek tek iş işlevleriyle** her işlevi için aşağıdaki veriler içerir:  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|İşlevin adı.|  
|**Özel süresi %**|İşlev, işlev gövdesi içinde kod çalıştırırken harcadığı profil oluşturma veri tüm zamanı yüzdesi. İşlevi çağrıldığında işlevlerde geçen süre dahil değildir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özet görünümü](../profiling/summary-view-sampling-data.md)   
 [Özet Görünümü](../profiling/summary-view-dotnet-memory-data.md)