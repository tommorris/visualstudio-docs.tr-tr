---
title: Engelleme zamanı Profil raporu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.report.blocking
helpviewer_keywords:
- Concurrency Visualizer, Blocking Time Profile Report
ms.assetid: 3bc45af0-3ba6-4fa3-a336-be8e9ae95107
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c18e3124bb602b65d087a2acf74a7107b754708
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="blocking-time-profile-report"></a>Engelleme Zamanı Profil Raporu
Profil raporları engelleme zaman veri toplama için engelleme her kategori (örneğin "G/ç" veya "Eşitleme") belirli çağrı yığınları sağlar. Önalım rapor önalım örnek sayısı ile birlikte geçerli işlem etkisiz işlemleri listeler. Engelleme Profil raporu oluşturmak için aracı engelleme API çağrıları toplar ve çağrı yığınları ağacına birikir. Bu raporlarda gösterilen verileri geçerli zaman aralığı, gizli iş parçacıkları ve uygulanabilir aşağıdaki iki filtre olarak değişir:  
  
-   Sadece kendi kodumu seçili ise, bir düzey altındaki kullanıcı kodu artı kullanıcı kodu sahip yığın çerçeveleri sunulur.  
  
-   Gürültü azaltma değeri ayarlarsanız, belirtilen sıklığı atlanır daha az sahip yığınları Harmanlanmış.  
  
 Engelleme zamanı harcanan kod satırı bulmak için herhangi bir çağrı ağacı giriş genişletin. Bir giriş için kaynak satırı, kısayol menüsünde bulmak için seçin **kaynağı görüntüle**. Bu bir kısayol menüsünde adlı kod satırını bulun tercih **çağrısı siteleri görünümünü**. Yalnızca tek bir çağrı site kullanılabilir komut çağrısı site kodunu vurgulanan satırı bağlanır. Birden çok arama siteleri varsa, komutu bir girişi seçin ve ardından bir iletişim kutusu açılır **kaynak Git** düğmesi vurgulanan çağrısı site bulunamıyor. Genellikle en örnekleri, en uzun süre ya da her ikisini de içeren çağrı siteyi kaynak kodunu görüntülemek en kullanışlıdır.  
  
## <a name="blocking-time-report-columns"></a>Engelleme zamanı Rapor sütunları  
 Aşağıdaki tabloda her engelleme süresi raporu sütunlarını gösterir.  
  
|Sütun adı|Açıklama|  
|-----------------|-----------------|  
|Ad|İşlev adı her düzeyi için çağrı yığını.|  
|Örnekler|Görünür zaman aralığı için engelleme çağrının örneği sayısı.|  
|Kapsayıcı engelleme süresi|Bu çağrı yığını ağacı düzey için toplanan tüm yığınları için harcanan süre engelleme toplam. Bu işlev için özel engelleme süresi ve tüm alt düğümleri için özel engelleme süresi toplamı (bunlar dahil) sayıdır.|  
|Özel engelleme süresi|Bu sırasında harcanan toplam engelleme süresini çağrı yığını en düşük düzeyde işlevdir. Yüksek bir özel engelleme süresine sahip bir benzersiz çağrı yığını girişi işlevi ilgi olabilir.|  
|API/Wait kategorisi|Yalnızca en düşük düzeyde çağrı yığını işlevler için gösterilir. Engelleme çağrısı imza tanınan burada engelleme API adı sağlanır. İmza tanınmıyorsa çekirdek tarafından bildirilen bilgiler sağlanır.|  
|Ayrıntılar|İşlev tam adı. Kullanılabilir olduğunda bu satır sayısını içerir.|  
  
### <a name="synchronization"></a>Eşitleme  
 Eşitleme rapor eşitleme ve her çağrı yığını sürelerinin engelleme toplama engelleme kesimleri sorumlu olan çağrıları gösterir. Daha fazla bilgi için bkz: [eşitleme zamanı](../profiling/synchronization-time.md)  
  
### <a name="sleep"></a>Uyku  
 Uyku raporda uyku harcanan zamanın öznitelikli zaman ve birleşik engelleme her çağrı yığınının engellemek için sorumlu çağrıları gösterilir. Daha fazla bilgi için bkz: [uyku zaman](../profiling/sleep-time.md).  
  
### <a name="io"></a>G/Ç  
 G/ç rapor g/ç ve her çağrı yığını sürelerinin engelleme toplama engelleme kesimleri sorumlu olan çağrıları gösterir. Daha fazla bilgi için bkz: [g/ç zamanı (iş parçacıkları görünümü)](../profiling/i-o-time-threads-view.md).  
  
### <a name="memory-management"></a>Bellek Yönetimi  
 Bellek yönetimi raporu bellek yönetimi işlemleri ve her çağrı yığını sürelerinin engelleme toplama engelleme kesimleri sorumlu olan çağrıları gösterilir. Daha fazla bilgi için bkz: [bellek yönetimi zamanı](../profiling/memory-management-time.md).  
  
### <a name="preemption"></a>Önalım  
 Önalım raporu geçerli işlem örneklerinin sayısını birlikte etkisiz işlemleri listeler.  Geçerli işlem iş parçacığı yerine belirli iş parçacıkları görünümü ve iş parçacığı başına önalım örneği dökümünü görüntülemek için her işlem genişletebilirsiniz. Önalım işleminizi üzerinde genellikle uygulanan işletim sistemi tarafından bir sorun kodunuzda tarafından değil çünkü bu engelleme rapor diğerlerinden daha az bir uyarıdır. Daha fazla bilgi için bkz: [Önalım zamanı](../profiling/preemption-time.md).  
  
### <a name="ui-processing"></a>UI işleme  
 Rapor UI işleme UI işleme blokları ve her çağrı yığını sürelerinin engelleme toplama engelleme kesimleri engellemek için sorumlu çağrıları gösterilir. Daha fazla bilgi için bkz: [UI işleme zamanı](../profiling/ui-processing-time.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş Parçacıkları Görünümü](../profiling/threads-view-parallel-performance.md)