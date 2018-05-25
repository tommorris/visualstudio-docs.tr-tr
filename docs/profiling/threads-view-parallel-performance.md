---
title: İş Parçacıkları görünümü (paralel performans) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.threadblocking
helpviewer_keywords:
- Concurrency Visualizer, Threads View (Parallel Performance)
ms.assetid: 2e441103-a266-407b-88c3-fb58716257a3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e63e208d0442b50d30ffd9e286dd92de4bb17610
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/24/2018
---
# <a name="threads-view-parallel-performance"></a>İş Parçacıkları görünümü (paralel performans)
**İş parçacıkları görünümü** en ayrıntılı ve zengin eşzamanlılık görselleştiricisi görünümde (seçin **Çözümle** > **eşzamanlılık görselleştiricisi** başlatmak için Eşzamanlılık görselleştiricisi). Bu görünümü kullanarak, iş parçacıkları yürütme veya eşitleme, g/ç veya başka bir nedenle nedeniyle engelleme olup olmadığını belirleyebilirsiniz.  
  
 Profil Çözümleme sırasında her bir uygulama iş parçacığı için tüm işletim sistemi bağlamı anahtar olayları eşzamanlılık görselleştiricisi inceler. İçerik Geçişi, bunlar gibi birçok nedeniyle oluşabilir:  
  
-   Bir iş parçacığı bir eşitleme temel engellendi.  
  
-   Bir iş parçacığı Zamanlayıcının süresi dolar.  
  
-   Bir iş parçacığı engelleme bir g/ç isteği yapar.  
  
 Bir iş parçacığı yürütülmesi durdurulduğunda iş parçacıkları görünümü bir kategori her bağlamı anahtara atar. Kategoriler görünümü sol alt kısmında göstergede gösterilir. Eşzamanlılık görselleştiricisi içerik anahtarı olayları için iyi bilinen engelleme API'leri iş parçacığının çağrı yığını arayarak kategorilere ayırır. Çağrı yığını eşleşme, tarafından sağlanan bekleme nedeni yoksa [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)] kullanılır. Ancak, [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)] kategori bir uygulama ayrıntılarını temel olabilir ve kullanıcı amacı yansıtmayabilir. Örneğin, [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)] eşitleme yerine yerel ince Okuyucu-Yazıcı kilit g/ç olarak engellemede bekleme nedeni bildirir. Çoğu durumda, içerik anahtarı olayları karşılık çağrı yığınları inceleyerek engelleme olay kök nedenini tanımlayabilirsiniz.  
  
 İş Parçacıkları görünümü, iş parçacıkları arasında bağımlılıkları da gösterir. Örneğin, bir eşitleme nesnesinde engellenmiş iş parçacığı belirlerseniz, onu engeli kaldırılmış iş parçacığı için bakabilirsiniz ve diğerinde engeli kaldırılmış, o iş parçacığı noktasında çağrı yığını faaliyete inceleyebilirsiniz.  
  
 İş parçacığı çalıştırırken, eşzamanlılık görselleştiricisi örnekleri toplar. İş Parçacıkları görünümü'nde hangi kod yürütme segment sırasında bir veya daha fazla iş parçacıkları tarafından yürütülen analiz edebilirsiniz. Ayrıca, raporları ve engelleme çağrı yığını ağaç yürütme profil raporları inceleyebilirsiniz.  
  
## <a name="usage"></a>Kullanım  
 İş Parçacıkları görünümü kullanabileceğiniz bazı yöntemler şunlardır:  
  
-   Uygulama kullanıcı arabirimi (UI) belirli yürütme aşamaları sırasında yanıt vermiyor neden nedenleri tanımlayın.  
  
-   Eşitleme, g/ç, sayfa hataları ve diğer olayları engelleme harcadığı süre miktarını belirleyin.  
  
-   Sistem üzerinde çalışan başka işlemler girişime derecesini tanımlayın.  
  
-   Paralel yürütme için Yük Dengeleme sorunları tanımlayın.  
  
-   (Daha fazla mantıksal çekirdekler kullanılabilir olduğunda Örneğin, bir paralel uygulama performansını iyileştirmez neden) yetersiz ya da yok ölçeklenebilirlik nedenlerini belirleyin.  
  
-   İçinde paralelleştirme yardımcı olmak için bu uygulamada eşzamanlılık derecesini anlayın.  
  
-   Çalışan iş parçacıkları ve yürütme kritik yolları arasında bağımlılıklar anlayın.  
  
## <a name="examine-specific-time-intervals-and-threads"></a>Belirli zaman aralıkları ve iş parçacıkları inceleyin  
 İş Parçacıkları görünümü zaman çizelgesi gösterir. Yakınlaştırma ve kaydırma belirli aralıklarla ve iş parçacıkları, uygulamanızın incelemek için zaman çizelgesi içinde. X ekseni üzerinde saat ve ekseninde birden fazla kanal:  
  
-   Sistem, bir kanalı için okuma ve yazma için bir tane her disk için iki g/ç kanalı.  
  
-   İşlemdeki her bir iş parçacığı için bir kanal.  
  
-   İzlemede işaret olayları olup olmadığına işaret kanalları. İşaretçi kanalları, başlangıçta bu olayları üretilen iş parçacığı kanalları altında görüntülenir.  
  
-   GPU kanalları.  
  
 İş Parçacıkları görünümü bir çizimi şöyledir:  
  
 ![İş Parçacıkları görünümü](../profiling/media/threadsviewnarrowing.png "ThreadsViewNarrowing")  
İş Parçacıkları Görünümü  
  
 Başlangıçta, böylece ana uygulama iş parçacığı ilk iş parçacığı, oluşturuldukları sıraya göre sıralanır. İş parçacıkları (örneğin, çoğu yürütme bugüne tarafından) başka bir ölçüte göre sıralamak için görünümünün sol üst köşesinde sıralama seçeneğini kullanabilirsiniz.  
  
 İş adlarını sol sütununda ve ardından seçerek gerçekleştirmiyorsanız iş parçacığı gizleyebilirsiniz **Seçili iş parçacığı Gizle** araç çubuğunda. Kendi istatistikleri ilgisiz olduğundan ve raporların clog tamamen engellenmiş iş parçacıklarının Gizle öneririz.  
  
 , Etkin göstergede gizlemek için ek iş parçacığı tanımlamak için seçin **başına iş parçacığı Özet** raporlamak **Profil raporu** sekmesi. Bu, şu anda seçili zaman aralığı için iş parçacıklarının durumunu gösteren yürütme çözümleme grafiği görüntüler. Bazı yakınlaştırma düzeylerinde bazı iş parçacıkları görüntülenmeyebilir. Bu durumda, üç nokta sağdaki görüntülenir.  
  
 Saat ve bazı iş parçacıkları bir aralık içinde seçtikten sonra Performans Analizi başlatabilirsiniz.  
  
## <a name="analysis-tools"></a>Analiz Araçları  
 Bu bölümde, raporlar ve diğer çözümleme araçları açıklanmaktadır.  
  
### <a name="thread-blocking-details"></a>İş parçacığı engelleme ayrıntıları  
 Bir iş parçacığı üzerinde belirli bir bölgede engelleme olay hakkında bilgi almak için bir araç ipucu görüntülemek için bu bölge fare işaretçisini. Varsa kategori, bölge başlangıç saati, engelleme süresi ve bir engelleme API gibi bilgileri içerir. Engelleme bölge seçerseniz, yığın zaman içinde bu noktada ipucunda görüntülenen aynı bilgileriyle birlikte alt bölmesinde görüntülenir. Çağrı yığını inceleyerek, iş parçacığı engelleme olay temel nedenini belirleyebilirsiniz. Ek işlem ve iş parçacığı bilgileri segment seçme ve geçerli sekme inceleyerek bulabilirsiniz.  
  
 Bir yol yürütme birden çok engelleme olay olabilir. Sorunlu alanları daha hızlı bulabilmeniz için bu engelleme kategoriye göre inceleyebilirsiniz. Yalnızca engelleme kategorilerden birini soldaki göstergede seçin.  
  
### <a name="dependencies-between-threads"></a>İş parçacıkları arasında bağımlılıkları  
 Engellenen bir iş parçacığı yapmak ve öğrenmek çalışıyordu belirleyebilmesi eşzamanlılık görselleştiricisi, işlemdeki iş parçacıklarını arasındaki bağımlılıkları gösterebilir hangi, diğer iş parçacığını yürütmek etkin. Hangi iş parçacığının başka bir iş parçacığı engellemesini belirlemek için ilgili engelleme segmenti seçin. Eşzamanlılık görselleştiricisi engellemesini kaldırma iş parçacığı belirlerseniz engellemesini kaldırma iş parçacığı ve engelleme segment izleyen yürütülmekte segmenti arasında bir çizgi çizer. Ayrıca, **Unblocking yığın** sekmesi ilgili çağrı yığını gösterir.  
  
### <a name="thread-execution-details"></a>İş parçacığı yürütme ayrıntıları  
 Bir iş parçacığı zaman çizelgesi grafikte, ne zaman kodu yürütülmekte olan yeşil kesimleri gösterir. Bir yürütme kesimi hakkında daha fazla bilgi alabilirsiniz.  
  
 Bir yürütme kesiminde bir noktaya seçtiğinizde, eşzamanlılık görselleştiricisi ilgili çağrı yığınında sürede o noktanın arar ve ardından seçilen noktaya yukarıda siyah bir şapka yürütme kesimdeki görüntüler ve çağrı yığını görüntüler  **Geçerli yığın** sekmesi. Yürütme kesimindeki birden çok noktası seçebilirsiniz.  
  
> [!NOTE]
>  Eşzamanlılık görselleştiricisi yürütme kesimindeki bir seçim çözümleyebilmesi olmayabilir. Kesimin süre değerinden bir milisaniyelik genellikle, bu oluşur.  
  
 Tüm Seçili zaman aralığı (görünür) iş parçacıklarında etkinleştirilmiş bir yürütme profili almak istediğinizi seçin **yürütme** düğmesi etkin göstergede.  
  
### <a name="timeline-graph"></a>Zaman Çizelgesi grafiği  
 Zaman Çizelgesi grafik işlem ve ana bilgisayardaki tüm fiziksel disk aygıtları tüm iş parçacıklarının etkinliğini gösterir. Ayrıca, GPU etkinlik ve işaret olayları görüntüler.  Daha fazla ayrıntı görüntülemek ya da daha uzun bir zaman aralığı görüntülemek için çıkış için yakınlaştırabilirsiniz. Kategoriler, başlangıç zamanlarını, süreleri ve çağrı yığını durumları hakkında bilgi almak için grafiği noktalarında öğesini de seçebilirsiniz.  
  
 Zaman Çizelgesi grafiğinde bir renk belirli bir zamanda bir iş parçacığı durumunu gösterir. Örneğin, yeşil kesimleri yürütülmekte kırmızı parçaları için eşitleme engellendi sarı kesimleri etkisiz ve mor kesimleri aygıt g/ç bağlı. Paralel bir döngüden veya eş zamanlı görevleri dahil olan iş parçacıkları arasında iş bakiyesini incelemek için bu görünümü kullanın. Bir iş parçacığı diğerlerinden daha uzun sürüyorsa, iş dengesiz olabilir. İş parçacıkları arasında eşit şekilde daha fazla iş dağıtarak programınızı performansını artırmak için bu bilgileri kullanın.  
  
 Yalnızca tek bir iş parçacığı (bir noktada yürütme süresi içinde) yeşil, uygulama tam eşzamanlılık sistemde yararlanarak olması değil. İş parçacığı ve engelleme arasında zamana bağlı ilişkileri arasındaki bağımlılıkları incelemek için zaman çizelgesi grafik kullanabilirsiniz ve engellenmiş iş parçacığı sayısı. İş parçacığı yeniden düzenlemek için bir iş parçacığı seçin ve araç çubuğunda yukarı seçin veya aşağı düğmesini. İş parçacığı gizlemek için bunları seçin ve ardından **Gizle iş parçacığı** düğmesi.  
  
### <a name="profile-reports"></a>Profil raporları  
 Zaman Çizelgesi bir zaman çizelgesi profili ve çeşitli raporlar için sekmeler bulunduğu bir bölme grafiktir. İş Parçacıkları görünümü değiştikçe raporları otomatik olarak güncelleştirilir. Güncelleştirmeleri hesaplanırken büyük izlemeleri için raporları bölmesinde kullanılamıyor olabilir. Her rapor iki filtre ayarlamalar vardır: gürültü azaltma ve sadece kendi kodumu. Çağrı ağacı girişleri az zamanın nerede harcandığına filtrelemek için gürültü azaltma kullanın. Varsayılan filtre değeri, 2 yüzde olmakla birlikte yüzde 99 yüzde 0 ' ayarlayabilirsiniz. Kodunuz için yalnızca çağrı ağacı görüntülemek için seçin **sadece kendi kodumu** onay kutusu. Tüm çağrı ağaçları görüntülemek için işaretini kaldırın.  
  
#### <a name="profile-report"></a>Profil raporu  
 Bu sekme etkin göstergesi girdileri karşılık raporları gösterir. Bir raporu görüntülemek için girişleri birini seçin.  
  
#### <a name="current-stack"></a>Geçerli yığın  
 Bu sekme seçilen noktaya çağrı yığını zaman çizelgesi grafikte bir iş parçacığı kesimindeki gösterir. Çağrı yığınları programınıza ilgili etkinlik gösterilecek atılır.  
  
#### <a name="unblocking-stack"></a>Yığın engellemesini kaldırma  
 Seçili iş parçacığı hangi iş parçacığı engellemesini görmek ve hangi kod satırında seçmek için **Unblocking yığın** sekmesi.  
  
#### <a name="execution"></a>Yürütme  
 Yürütme rapor yürütme uygulama harcanan sürenin dökümünü gösterir.  
  
 Yürütme saati harcanır kod satırı bulmak için arama ağacını genişletin ve ardından, çağrı ağacı girişi için kısayol menüsünden seçin **kaynağı görüntüle** veya **çağrısı siteleri görünümünü**. **Kaynak görüntülemek** yürütülen kod satırını bulur. **Çağrı siteleri görüntülemek** yürütülen kod satırı ile adlı kod satırını bulur. Yalnızca tek bir çağrı site varsa, kendi satırlık bir kod vurgulanır. Birden çok arama siteleri varsa görünür ve ardından iletişim kutusunda istediğiniz birini seçebilirsiniz **kaynak Git** çağrısı site kodu vurgulamak için düğmesi. Genellikle en örnekleri, en uzun süre ya da her ikisini de içeren çağrı siteyi bulmak en kullanışlıdır. Daha fazla bilgi için bkz: [yürütme Profil raporu](../profiling/execution-profile-report.md).  
  
#### <a name="synchronization"></a>Eşitleme  
 Eşitleme rapor eşitleme blokları, her çağrı yığını sürelerinin engelleme toplama sorumlu olan çağrıları gösterir. Daha fazla bilgi için bkz: [eşitleme zamanı](../profiling/synchronization-time.md).  
  
#### <a name="io"></a>G/Ç  
 G/ç rapor g/ç blokları, her çağrı yığını sürelerinin engelleme toplama sorumlu olan çağrıları gösterir. Daha fazla bilgi için bkz: [g/ç zamanı (iş parçacıkları görünümü)](../profiling/i-o-time-threads-view.md).  
  
#### <a name="sleep"></a>Uyku  
 Uyku raporda uyku blokları, her çağrı yığını sürelerinin engelleme toplama sorumlu olan çağrıları gösterilir. Daha fazla bilgi için bkz: [uyku zaman](../profiling/sleep-time.md).  
  
#### <a name="memory-management"></a>Bellek yönetimi  
 Bellek yönetimi raporu, bellek yönetimi blokları, her çağrı yığını sürelerinin engelleme toplama birlikte oluştuğu çağrıları gösterilir. Aşırı disk belleği veya atık toplama sorunları olan alanları belirlemek için bu bilgileri kullanın.  Daha fazla bilgi için bkz: [bellek yönetimi zamanı](../profiling/memory-management-time.md).  
  
#### <a name="preemption"></a>Önalım  
 Önalım rapor burada geçerli işlem ve geçerli işlemdeki iş parçacıklarının yerine tek tek iş parçacıkları sistem işlemleri etkisiz örnekleri gösterir. İşlemler ve için önalım en sorumlu olan iş parçacıkları tanımlamak için bu bilgileri kullanın. Daha fazla bilgi için bkz: [Önalım zamanı](../profiling/preemption-time.md).  
  
#### <a name="ui-processing"></a>UI işleme  
 UI işleme rapor her çağrı yığını sürelerinin engelleme toplama birlikte blokları işleme için kullanıcı Arabirimi sorumlu çağrıları gösterir. Daha fazla bilgi için bkz: [UI işleme zamanı](../profiling/ui-processing-time.md).  
  
#### <a name="per-thread-summary"></a>İş parçacığı özeti  
 Bu sekme ren kodlu sütun görünümü toplam süre, her iş parçacığı Çalıştır harcanan, engellenmiş, g/ç ve diğer durumlar gösterir. Sütunları altındaki etiketlenir. Bu sekme, zaman çizelgesi grafikte yakınlaştırma düzeyini ayarladığınızda, otomatik olarak güncelleştirilir. Bazı yakınlaştırma düzeylerinde bazı iş parçacıkları görüntülenmeyebilir. Bu durumda, üç nokta sağdaki görüntülenir. İstediğiniz iş parçacığı görünmüyorsa, başka bir iş parçacığı gizleyebilirsiniz. Daha fazla bilgi için bkz: [iş parçacığı özet raporu başına](../profiling/per-thread-summary-report.md).  
  
#### <a name="disk-operations"></a>Disk işlemleri  
 İş parçacığı disk g/ç bunlar (örneğin, yüklenen DLL'ler) işlemdeki, hangi dosyaların kaç bayt okuma işlemleri, geçerli işlemin ve diğer bilgileri adına katılan ve bu sekme hangi işlemlerin gösterir. Özellikle, işlem bağlı g/ç görünüyor, dosyaları yürütme sırasında erişirken harcanan zamanı değerlendirmek için bu raporu kullanın. Daha fazla bilgi için bkz: [Disk işlemleri raporu](../profiling/disk-operations-report-threads-view.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Eşzamanlılık görselleştiricisi](../profiling/concurrency-visualizer.md)