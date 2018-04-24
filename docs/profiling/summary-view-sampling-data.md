---
title: Özet görünümü - örnekleme veri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- sampling profiling method, Summary view
- Summary view
ms.assetid: 79056873-2985-40be-9112-cdbc26a65156
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6bfe40903063fc4ae412603563647a0deb39788f
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="summary-view---sampling-data"></a>Özet görünümü - örnekleme verileri
Özet görünümü, bir çalıştırma profil en performans pahalı işlevleri hakkında bilgi görüntüler. Bildirim bağlantıları ve rapor listeler açıklaması dahil olmak üzere daha fazla bilgi için bkz: [özeti görünümü](../profiling/summary-view.md).  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="timeline-graph"></a>Zaman Çizelgesi grafiği  
 Özet görünümü zaman çizelgesi grafiğinde profil oluştu zamanla profili uygulamasının işlemci (CPU) kullanım yüzdesini gösterir. Seçilen zaman aralığı görünümüne filtrelemek için zaman çizelgesi grafik kullanabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Özet zaman çizelgesi filtre rapor görünümleri](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
## <a name="hot-path"></a>Sık kullanılan yolu  
 **Etkin yolunuzda** çoğu örnekleri toplandı yürütme yolunu görüntüler. İşlev için işlev ayrıntıları görüntülemek için bir işlev tıklatabilirsiniz. İşlevi için diğer görünümleri görüntülemek için işlevi sağ tıklayın ve sonra listeden bir görünümü tıklatın.  
  
 **Etkin yolunuzda** her işlevi için aşağıdaki veriler içerir:  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|İşlevin adı.|  
|**Kapsayıcı örnekleri %**|Bu işlev veya bu işlev tarafından çağrılan işlev yürütülürken zaman oluşan tüm örneklerini yüzdesi.|  
|**Özel örnekleri %**|İşlev kodu işlev gövdesine edildi yürütülürken oluşan tüm örneklerini yüzdesi. Bu işlev tarafından çağrılan işlevlerinde toplanan örnekleri dahil edilmez.|  
  
## <a name="functions-doing-most-individual-work"></a>Ayrı ayrı çoğu çalışarak işlevleri  
 **İşlevleri yapılması en tek tek iş** çalıştırmak Profil özel örnek en büyük sayısını işlevleri görüntüler. Örnek toplanan zaman işlevi kendi kodu çalıştırıldığında özel bir örnek bir işleve atanır. Örnek toplanan zaman işlevi başka bir işlevi çağırmak, özel bir örnek bir işleve atanmadı. Çok sayıda özel örnekleri önemli zaman işlevinde harcandığını gösterir.  
  
 İşlev için işlev ayrıntıları görüntülemek için bir işlev tıklatabilirsiniz. İçin işlevi sağ işlevi için diğer görünümleri görüntülemek ve sonra listeden bir görünümü tıklatın.  
  
 **İşlevler en yapılması tek tek iş** her işlevi için aşağıdaki veriler içerir:  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Ad**|İşlevin adı.|  
|**Özel örnekleri %**|İşlev, işlev gövdesi kod yürütülmekte olan yükleyen toplanan çalıştırmak profil tüm örneklerini yüzdesi. Bu işlev çağrılan işlev yürütülürken toplanan örnek yüzdesi dışlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özet görünümü](../profiling/summary-view-dotnet-memory-data.md)   
 [Özet Görünümü](../profiling/summary-view-instrumentation-data.md)