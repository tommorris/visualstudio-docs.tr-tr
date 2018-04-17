---
title: Yük testi sonuçlarını ve hatalarını Visual Studio'da çözümleme | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.monitor.pageresult
- vs.test.load.dialog.column
- vs.test.load.monitor.requestresult
- vs.test.load.monitor.testresult
- vs.test.load.monitor.table.view
- vs.test.load.monitor.agentresult
- vs.test.load.monitor.transactionresult
helpviewer_keywords:
- tables, Load Test Viewer options
- load test results, tables
- load tests, Load Test Viewer
- data [Visual Studio ALM], load test tables
- Load Test Viewer, tables
- load tests, results tables
ms.assetid: 0a84bda3-6051-45eb-9c7f-d57419e1f97d
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 1ef22fcdfeb1b3ccf0005940ca2f7201545482f8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="analyze-load-test-results-and-errors-in-the-tables-view-of-the-load-test-analyzer"></a>Yük testi sonuçlarını ve hatalarını Yük Testi Çözümleyicisinin Tablo görünümünde analiz eder.

Yük testi sonuçlarını görüntülediğinizde, verileri çözümlemek için farklı yollar sağlar farklı bölmeleri görüntüleyebilirsiniz. Bu zaman içinde nasıl değiştiğini görmek için bir grafik olarak verilerini görüntüleyebilir veya verileri ayrıntılı tablolar olarak görüntüleyebilirsiniz.

Tablo görünümüne geçiş yapmak için tercih **tabloları** yük testi araç çubuğunda. Farklı tablolar arasında geçiş yapmak için kullanın **tablo** tablo kılavuz yukarıda araç çubuğundaki aşağı açılan listesinde. Tablo görünümünde, aynı anda en fazla dört tabloları görüntüleyebilirsiniz. Daha fazla bilgi için bkz: [döşeme yük testi tabloları](../test/analyze-load-test-results-and-errors-in-the-tables-view.md#tile-load-test-tables) bu konuda.

Performans sayaçları için bir tabloda gösterilen Çoğu sayısal değer tüm yük testi toplu. Adlandırılmış sütunlar **son** istisnadır ve en son örnekleme aralığından değeri temsil eder.

> [!NOTE]
> Adlandırılmış sütunlar **son** yalnızca bir yük testi yürütülürken kullanılabilir. Bir yük testi tamamlandıktan sonra bu sütunlar kullanılamaz.

 Çoğu tabloları sıralamak istediğiniz sütunun başlığını seçerek sıralayabilirsiniz. Varsayılan olarak, bazı tablolar kullanılabilir tüm sütunları görüntüleme. Sütunlar kullanılabiliyorsa tablolar, sütunlar ekleyebilirsiniz. Sütun eklemek için tabloyu sağ tıklatın ve ardından **Sütun Ekle/Kaldır**.

> [!NOTE]
> Ek analiz için Excel gibi diğer uygulamalara tablodan veri kopyalayabilirsiniz.

## <a name="the-load-test-tables"></a>Yük testi tabloları

 Aşağıdaki tabloda yükleme testi çalışmalarını çözümlemek için kullanılabilir olan tabloları listeler.

|Tablo adı|Açıklama|
|----------------|-----------------|
|Hatalar|Yük testi sırasında oluşan hataların listesini görüntüler. Daha fazla bilgi için bkz: [hataları Table](../test/analyze-load-test-results-and-errors-in-the-tables-view.md#the-errors-table) Bu konu başlığı ve [yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md).|
|Sayfaları|Yük testi sırasında erişilen sayfalar listesini görüntüler. Bu tablodaki bazı verileri, yalnızca bir yük testi tamamlandıktan sonra kullanılabilir. Daha fazla bilgi için bkz: [nasıl yapılır: Görünümü Web sayfası yanıt](../test/how-to-view-web-page-response-time-in-a-load-test.md).|
|istekleri|Bir yük testi sırasında verilen bireysel isteklere ilişkin ayrıntıları görüntüler. Bu, tüm HTTP istekleri ve resimler gibi bağımlı istekleri içerir. Daha fazla bilgi için bkz: [istekleri Table](../test/analyze-load-test-results-and-errors-in-the-tables-view.md#the-requests-table) bu konuda.|
|SQL izleme|SQL izleme sonuçlarını görüntüler. Bu tablo yalnızca bir yük testi tamamlandıktan sonra ve yalnızca SQL izleme test sırasında kullanıldıysa mevcuttur. Daha fazla bilgi için bkz: [SQL izleme veri tablosu](../test/analyze-load-test-results-and-errors-in-the-tables-view.md#the-sql-trace-data-table) bu konuda.|
|Testler|Tek tek testlerin görüntüler ayrıntılarını bir yük testi sırasında çalıştırın. Daha fazla bilgi için bkz: [testleri Table](../test/analyze-load-test-results-and-errors-in-the-tables-view.md#the-tests-table) bu konuda.|
|Eşikleri|Yük testi çalıştırması sırasında gerçekleşen eşik kuralı ihlallerini listesini görüntüler. Daha fazla bilgi için bkz: [eşik kuralı ihlallerini çözümleme](../test/analyze-threshold-rule-violations-in-load-tests.md).|
|İşlemler|Yük testi sırasında oluşan işlemleri listesini görüntüler. Daha fazla bilgi için bkz: [işlemleri Table](../test/analyze-load-test-results-and-errors-in-the-tables-view.md#the-transactions-table) bu konuda.|
|Aracılar|Yalnızca yük testlerini test denetleyicisi ve test aracıları kullanıyorsa görüntüler. Yük testi sırasında kullanılan aracıların listesini görüntüler. Aracılar tablosu kaç aracı test ve bu istekleri kaç tanesinin başarısız istekleri içerir. Ayrıca, aracılar tablosu aracı test yük testleri test karışımında ve bu, testleri sayısını içeren kaç tanesinin başarısız.|
|Test Ayrıntıları|Yük testi için test karışımını dahil testler için ayrıntılarını görüntüler. Ayrıntılar test, test, senaryoyu test başlatıldığı zamanı, testin çalışması için geçen süre ve test geçirilen ya da başarısız olmuşsa gösteren test sonucu uzunluğu adını içerir. Test başarısız olursa, bir bağlantı bulunur **ayrıntıları** sütun. Web Performans Testi Düzenleyicisi başarısız isteğin vurgulandığı alacak bağlantı seçebilirsiniz.|

## <a name="collect-percentile-data"></a>Yüzdelik veri toplamak

 Bazı yük testi tabloları ağ öykünmesine dayanan gruplara ayrılmış yüzde birlik verileri ve yanıt sürelerini içeren ek sütunlar içerebilir. Varsayılan olarak, bu veriler toplanmaz. Yüzdelik veriler yalnızca bir veritabanına sonuçları kaydettiğinizde ve yerel olarak değil kaydettiğinizde kullanılabilir. Daha fazla bilgi için bkz: [yük testi sonuçları havuzu yük testi sonuçlarını yönetme](../test/manage-load-test-results-in-the-load-test-results-repository.md). Ayrıca, içinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** belirli çalışmaya değiştirmek için ayarı düğümü düğümünü seçin. İçinde **özellikleri** penceresinde için **zamanlama ayrıntıları depolama** özelliği, select **StatisticsOnly** veya **AllIndividualDetails**. Daha fazla bilgi için bkz: [nasıl yapılır: Görünümü Web sayfası yanıt](../test/how-to-view-web-page-response-time-in-a-load-test.md).

## <a name="the-requests-table"></a>İstekler tablosu

 **İstekleri** tablosu bir yük testi sırasında verilen bireysel isteklere ayrıntılarını görüntüler. Bu, tüm HTTP istekleri ve resimler gibi bağımlı istekleri içerir. Bir istek birçok testleri ve senaryoları dahil olduğundan tablo test ve senaryoya göre istekleri listeler.

 Aşağıdaki tablo sütunları listeler **istekleri** tablosu:

|Sütun|Açıklama|Varsayılan olarak görünür|
|------------|-----------------|------------------------|
|**İstek**|İstek URL'si. Örneğin, home.html veya turuncu arrow.gif.|Evet|
|**Senaryo**|Senaryo adı.|Evet|
|**Test**|Test adı.|Evet|
|**Toplam**|Yük testi sırasında verilen bu Web performans testi isteği toplam sayısı çalıştırın. Toplam, başarılı ve başarısız istekleri içerir, ancak Web sunucusuna verilmediğinden önbelleğe alınan istekleri içermez.|Evet|
|**Geçirilen**|İsteği yayınlandı ve geçirilen sayısı.|Hayır|
|**Başarısız**|İsteği yayınlandı ve başarısız sayısı. Bu sütunda yer alan girişleri köprü olarak gösteriliyor. Hataları ayrı ayrı bir listesini görüntülemek için herhangi bir köprüye seçebilirsiniz **yük testi hataları** iletişim kutusu. Daha fazla bilgi için bkz: [yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md).|Evet|
|**Önbelleğe alınmış**|Toplam istek önbelleğe alınma sayısı.|Hayır|
|**İsteği/sn**|Yük testi sırasında isteğin saniye başına oranı.|Hayır|
|**Geçirilen/sn**|Bu istek, geçirilen bu isteğin örnekleri için yük testi sırasında saniye başına oranı.|Hayır|
|**Saniye başına başarısız oldu**|Bu istek, bu isteğin başarısız örnekleri için yük testi sırasında saniye başına oranı.|Hayır|
|**İlk bayta kalan süre**|Yanıt ilk baytını almak için geçen ortalama süre istek Web sunucusuna gönderilen zamandan itibaren ölçülür. Saniye birimleridir.|Hayır|
|**Yanıt süresi**|Tüm isteğine yanıt olarak, almak için geçen ortalama süre istek Web sunucusuna gönderilen zamandan itibaren ölçülür. Saniye birimleridir.|Evet|
|**İçerik uzunluğu**|İstek yanıtı içeriğini ortalama uzunluğu. Bayt birimleridir.|Evet|

## <a name="the-tests-table"></a>Testler tablosu

 **Testleri** tablo bir yük testi sırasında tek tek testleri çalıştırmak için ayrıntıları görüntüler. Bir test birçok senaryoda dahil edilebilir çünkü tablo testleri test ve senaryoya göre listeler.

 Aşağıdaki tablo sütunları listeler **testleri** tablo.

|Sütun|Açıklama|Varsayılan olarak görünür|
|------------|-----------------|------------------------|
|**Test**|Test adı.|Evet|
|**Senaryo**|Senaryo adı.|Evet|
|**Toplam**|Test senaryosunda çalıştırılma toplam sayısı. Bu testin başarılı ve başarısız sayısını içerir.|Evet|
|**Geçirilen**|Test senaryosunda çalıştırın ve geçirilen sayısı.|Evet|
|**Başarısız**|Test senaryosunda çalıştırılma ve başarısız olma sayısı. Bu sütunda yer alan girişleri köprü olarak gösteriliyor. Hataları ayrı ayrı bir listesini görüntülemek için herhangi bir köprüye seçebilirsiniz **yük testi hataları** iletişim kutusu. Daha fazla bilgi için bkz: [yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md).|Evet|
|**Testleri/sn**|Test yük testi sırasında saniye başına oranı.|Evet|
|**Geçirilen/sn**|Bu test, geçirilen bu test örnekleri için yük testi sırasında saniye başına oranı.|Hayır|
|**Saniye başına başarısız oldu**|Bu test, başarısız bu test örnekleri için yük testi sırasında saniye başına oranı.|Hayır|
|**Test süresi**|Test yük testi sırasında ortalama yürütme süresi. Saniye birimleridir.|Evet|
|**% 90 test süresi**|Test süresi 90 yüzdelik değer.|Hayır|
|**% 95 test süresi**|Test süresi için 95 yüzdelik değer.|Evet|
|**İstekleri ve Test**|Varsa bir Web performans testinde istekleri ortalama sayısı sınayın.|Hayır|

## <a name="the-transactions-table"></a>İşlemler tablosu

 **İşlemleri** tablo bir yük testi çalıştırması sırasında gerçekleşen işlemlerin bir listesini görüntüler. Bir Web performans testinde tanımlanan işlemlere ya da bir birim testi içinde tanımlanan zamanlayıcılar işlemleri bakın. İşlem, veritabanı işlemleri için başvurmuyor.

 Aşağıdaki tablo sütunları listeler **işlemleri** tablo.

> [!NOTE]
> Tüm sütunları görüntülemek için etkin çalışma ayarı ile ilişkilendirilen zamanlama ayrıntıları depolama özelliğini etkinleştirmeniz gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: zamanlama ayrıntıları depolama özelliğini belirtme](../test/how-to-specify-the-timing-details-storage-property-for-a-load-test.md).

|Sütun|Açıklama|Zamanlama Ayrıntıları olmadan görünür|
|------------|-----------------|------------------------------------|
|**İşlem**|İşlem adı.|Evet|
|**Senaryo**|Senaryo adı.|Evet|
|**Test**|Test adı.|Evet|
|**Toplam**|Yük testi sırasında verilen işlemlerin toplam sayısı.|Evet|
|**İşlem süresi**|Yük testi sırasında işlem yürütme süresi. Web performans testleri için süresi hesaplamadaki dahil düşünün. Saniye birimleridir.|Hayır|
|**Yanıt süresi**|Çalıştıran bir yük testinde Web performans testi işlemi için yanıt süresi. Yanıt süresi düşünme içermez, yanıt süresi işlem süresi'nden farklı işlem sırasında oluşan zaman. Saniye birimleridir.|Hayır|
|**Ortalama İşlem süresi**|Ortalama işlem süresi. Bu süre düşünme sürelerini içerir. Örneğin, üç istekleri sahip ve her bir Düşünme süresi içeriyorsa, bu kez içerecektir olanlar düşünme sürelerini ve çalıştırmak için gerçek süre ister.|Hayır|
|**Ortalama Yanıt süresi**|Yük testi Web performans testi işlemde için ortalama yanıt süresi. Yanıt süresi düşünme içermez, yanıt süresi işlem süresi'nden farklı işlem sırasında oluşan zaman. Saniye birimleridir.|Hayır|
|**Min yanıt süresi**|Düşünme sürelerini içermez.|Hayır|
|**En büyük yanıt süresi**|Düşünme sürelerini içermez.|Hayır|
|**Ortalama yanıt süresi**|Düşünme sürelerini içermez.|Hayır|
|**% 90 yanıt süresi**|İşlem süresi 90 yüzdelik değer. Düşünme sürelerini içermez. **Not:** bu Visual Studio Team System 2008 Test Yükleme kullanılan Aracısı'ndan, farklı **% 90 işlem süresi** değeri.|Hayır|
|**% 95 yanıt süresi**|İşlem süresi için 95 yüzdelik değer. Düşünme sürelerini içermez. **Not:** bu Visual Studio Team System 2008 Test Yükleme kullanılan Aracısı'ndan, farklı **% 95 işlem süresi** değeri.|Hayır|
|**% 99 yanıt süresi**|İşlem süresi için 99 yüzdelik değer. Düşünme sürelerini içermez.|Hayır|
|**Std Dev yanıt süresi**|Düşünme sürelerini içermez.|Hayır|

## <a name="the-errors-table"></a>Hatalar tablosu

 Bir yük testi çalıştırdığınızda oluşan hataları çözümleyebilirsiniz. Hataları çözümleme ve testlerinizi ayarlama yük test işlemi önemli bir parçasıdır. Herhangi bir hata oluştuysa, bir **hataları** köprü yük testi durum çubuğunda görünür ve oluşan hataların sayısını belirtir. Hatalar tablosunu görüntülemek için köprü seçin.

 Hataları, yükleme sırasında oluşan hataları test grupları türüne ve alt hatanın tarafından tablo. Ayrıca bir **toplam** oluşan tüm hataların toplam sayısını belirten tablodaki satır.

 Hataları tablo şu sütunları içerir:

|Sütun|Açıklama|Varsayılan olarak görünür|
|------------|-----------------|------------------------|
|Tür|Hata türü. Örneğin, HTTP hatası.|Evet|
|SubType|Hatanın alt türü. Örneğin, LoadTestException.|Evet|
|Sayısı|Yük testi sırasında gerçekleşen bu tür hataların sayısı. Bu sütunda yer alan girişleri köprü olarak gösteriliyor. Hataları ayrı ayrı bir listesini görüntülemek için herhangi bir köprüye seçebilirsiniz.|Evet|
|Son ileti|Hatayı açıklayan ileti. Örneğin, 404 - NotFound.|Evet|

 Daha fazla bilgi için bkz: [yük testi tabloları ile çalışma](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

### <a name="drilling-down-to-the-error-list"></a>Hata listesinde ayrıntıya gitmek

Hataları tablosu hatalarını türüne ve alt hata türüne göre gruplandırır. Tek tek hataların tablosunu görüntülemek için görüntü **yük testi hataları** iletişim kutusu. İletişim kutusunu görüntülemek için bir köprü seçin **sayısı** hatalar tablosunun sütun. İletişim kutusunu doldurulur hataları tablosunda bir satırı sağ tıklayıp seçerek görüntüleyebilirsiniz **hataları**.

> [!NOTE]
> Yalnızca ilk 1.000 örnekleri hata türüne ve alt birleşiminden toplanır. Görüntülediğinizde **yük testi hataları** iletişim kutusu, en fazla ilk 1.000 örnekleri hata görürsünüz.

**Yük testi hataları** tablo şu sütunları içerir:

|Sütun|Açıklama|
|------------|-----------------|
|**Saat**|Hatanın gerçekleştiği süre boyunca yük test edin.|
|**Aracı**|Hatanın gerçekleştiği Aracı bilgisayarın adı. Test denetleyicileri ve test aracılarını kullanarak yük testlerini çalıştırdığınızda, bu önemlidir. Daha fazla bilgi için bkz: [yüklemek ve test aracılarını yapılandırma](../test/lab-management/install-configure-test-agents.md).|
|**Test**|Web performans adını test hangi hata oluştu.|
|**Senaryo**|Hatanın gerçekleştiği senaryonun adı.|
|**İstek**|Hata meydana geldiği istek URL'si.|
|**Türü**|Hata türü. Örneğin, HTTP hatası.|
|**Alt türü**|Hatanın alt türü. Örneğin, LoadTestException.|
|**Metin**|Hata iletisinin metni. Örneğin, 404 - NotFound.|
|**Yığını**|Bu sütundaki boş veya word girişler **yığın** köprü olarak biçimlendirilir. Hata yığını izlemesi görüntülemek için köprüye seçebilirsiniz.|
|**Ayrıntıları**|Bu sütundaki boş veya word girişler **TestLog** köprü olarak biçimlendirilir. Bu bağlantıyı yük testindeki hataları ayırmanıza yardımcı olabilir. Örneğin, seçme **TestLog** bir Web performans testi istek hatasını bağlantıdaki Web Performans Testi Sonuçları Görüntüleyicisi'ndeki Web performans testi sonuçları açın ve istek hatası vurgulayın.|

> [!NOTE]
> Tablo, sütun başlıklarının seçerek sıralayabilirsiniz.

## <a name="the-sql-trace-data-table"></a>SQL izleme veri tablosu

Daha sonra çözümlemek için bir yük testi sırasında SQL izleme verilerini toplayabilir. İzleme verilerini toplamak yavaş çalışan sorguları ve saklı yordamlar SQL Server veritabanında sınanan tanımlamanıza olanak sağlar.

SQL izleme etkinleştirilirse, izleme verilerini içeren yük testi sırasında bir dosya oluşturulur. Bu veriler yük testi sonuçları deposu test çalıştırması sonunda otomatik olarak kaydedilir ve izleme dosyası silinir. İzleme verilerini analiz **SQL İzleme** yük testlerini tamamlandıktan sonra tablo.

### <a name="to-view-sql-trace-data"></a>SQL izleme verilerini görüntülemek için

1. Yük Testi Çözümleyicisi'nde seçin **tabloları** tablo kılavuzunun görüntülendiğinden emin olmak için araç çubuğunda.

2. İçinde **tablo** aşağı açılan liste kutusunda **SQL İzleme**.

3. Çalışma sırasında toplanan izleme verilerini kılavuzda görüntülenir. Tablo en yavaş üst süreye göre sıralanmış yavaş çalışan SQL işlemleri listeler. Genellikle, **süresi** incelemek için ilk sütun bir sütundur. Veri milisaniye cinsinden gösterilir.

   Görüntülenen sütunlar aşağıdaki gibidir:

    - Event sınıfı

    - Süre

    - CPU

    - Okur

    - Yazma

    - TextData

    - StartTime

    - EndTime

   Bu sütunlarda belirtilen verilerden farklı SQL olaylarını izlemek isterseniz, Visual Studio'dan ayrı SQL Profiler aracını kullanarak kendi özel SQL izleme ayarlayabilirsiniz.

## <a name="tile-load-test-tables"></a>Yük testi tabloları döşeme

Yük testi sonuçlarını görüntülediğinizde, ayrıntılı tablolar olarak verilerini görüntüleyebilir. Tablo görünümüne geçiş yapmak için tercih **tabloları** yük testi araç çubuğunda. Kullanılabilir tabloların hataları, sayfalar, istekleri, SQL izleme, testleri, eşikleri ve işlemleri ' dir. Daha fazla bilgi için bkz: [yük testi tabloları ile çalışma](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

Tablo görünümünde, aynı anda en fazla dört tabloları çakışmadan görüntüleyebilirsiniz.

### <a name="to-tile-tables"></a>Tabloları döşeme

1. Yük Testi Çözümleyicisi araç çubuğunda seçin **tabloları**.

     Tablo görünümü açılır. Varsayılan düzen iki yatay bölmedir.

2. Yük Testi Çözümleyicisi araç çubuğunda düzeni düğmesini seçin ve ardından aşağıdaki seçeneklerden birini seçin:

    - Bir paneli

    - İki yatay bölme

    - Üç yatay bölme

    - Dört yatay bölme

3. Farklı tablolar arasında geçiş yapmak için her panelinde Tablo Kılavuz yukarıdaki açılır listeyi kullanın.

    > [!NOTE]
    > Aynı tabloda birden fazla panelinde görüntülenemiyor. Zaten başka bir panelinde görüntülenen bir tabloya bir bölmede görüntülenen tablo değiştirirseniz, tablolar bölmelere geçiş yapar.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Nasıl yapılır: yük testi sonuçlarını çözümleme için erişim](../test/how-to-access-load-test-results-for-analysis.md)
- [Grafik görünümünde yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-in-the-graphs-view.md)
- [Eşik kuralı ihlallerini çözümleme](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Yük testi sonuçları havuzu yük testi sonuçlarını yönetme](../test/manage-load-test-results-in-the-load-test-results-repository.md)
- [Yük Testi Sonuçları Özeti genel bakış](../test/load-test-results-summary-overview.md)