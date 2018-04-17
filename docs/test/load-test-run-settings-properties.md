---
title: Visual Studio Yük testi çalıştırma ayarları | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, run settings
ms.assetid: de10dabb-02ed-403b-9e6f-0b735524988c
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 498c581d1918fbd4565f821bf516a5301534d733
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="load-test-run-settings-properties"></a>Yük Testi Çalıştırma Ayarları Özellikleri

Bir yük testi çalıştırma ayarlarını çeşitli süresi test, sonuç koleksiyonu ayrıntı düzeyi ve test çalıştığında toplanan sayaç kümeleri dahil olmak üzere diğer ayarları belirleyin. Oluşturun ve her yük testi için birden çok çalışma ayarları depolamak ve testi çalıştırdığınızda kullanmak için belirli bir ayar seçin. Yeni Yük Testi Sihirbazı'nı kullanarak, yük testi oluşturduğunuzda, yük testi için bir ilk çalıştırma ayarı eklenir.

 Aşağıdaki tablo yük testi çalıştırma ayarlarını için çeşitli özellikleri açıklar. Belirli yük testi gereksinimlerini karşılamak için bu özellikleri değiştirebilirsiniz.

 Daha fazla bilgi için bkz: [yük testi çalıştırma ayarları yapılandırma](../test/configure-load-test-run-settings.md).

## <a name="general-properties"></a>Genel Özellikler

|Özellik|Tanım|
|--------------|----------------|
|**Açıklama**|Çalışma ayarları açıklaması.|
|**Tür başına en fazla hata**|Yük testi için kaydedilecek tür başına hatası sayısı.<br /><br /> İçin varsa, ancak bunun yapılması ayrıca boyutunu ve yük testi sonuç işleme süresi artacaktır bu sayıyı artırabilirsiniz.|
|**Bildirilen en büyük İstek URL'leri**|Benzersiz Web performans testi sayısı, bu yük testi sonuçlarında bildirmek URL'leri isteyin.<br /><br /> İçin varsa, ancak bunun yapılması ayrıca boyutunu ve yük testi sonuç işleme süresi artacaktır bu sayıyı artırabilirsiniz.|
|**En fazla Eşik ihlalleri**|Bu yük testi için kaydedilecek eşik ihlallerini maksimum sayısı.<br /><br /> İçin varsa, ancak bunun yapılması ayrıca boyutunu ve yük testi sonuç işleme süresi artacaktır bu sayıyı artırabilirsiniz.|
|**Uygulama etki alanında birim testleri çalıştırma**|Yük testi birim testlerini içerdiğinde her birimi derleme olup olmadığını test belirleyen bir Boolean değeri ayrı uygulama etki alanında çalıştırılır. True varsayılan ayardır.<br /><br /> Birim testleri düzgün çalışması için bir ayrı uygulama etki alanı ya da app.config dosyası gerektirmiyorsa, birim testleri daha hızlı bu özelliğin değeri ayarlayarak çalışabilir `False`.|
|**Ad**|Göründüğü gibi çalışma ayarı adı **çalıştırma ayarları** düğümünün **Yük Testi Düzenleyicisi**.|
|**Doğrulama düzeyi**|Bu, bir yük testinde çalışacak doğrulama kuralının en üst düzey tanımlar. Doğrulama kuralları Web başarım testi istekleri ile ilişkilendirilir. Her doğrulama kuralı bir ilişkili doğrulama düzeyi vardır: **yüksek**, **orta**, veya **düşük**. Bu yük testi çalışma ayarı yük testinde Web performans testi çalıştırırken kuralları çalışır hangi doğrulama belirtmeniz gerekecektir. Örneğin, bu ayar çalıştırırsanız ayarlanır **orta**, tüm doğrulama kurallarını olarak işaretlenmiş **orta**, veya **düşük** çalıştırılır.|

## <a name="logging-properties"></a>Günlüğe kaydetme özellikleri

|Özellik|Tanım|
|--------------|----------------|
|**En fazla Test günlükleri**|Yük testi için kaydetmek için test günlüklerinin en fazla sayısını belirtir. Maksimum sayısı için girilen değer test günlüklerinin ulaşıldığında, yük testi günlükleri toplamayı durdurur. Bu nedenle, günlükleri, test, son başında toplanacaktır. Yük testi tamamlanana kadar çalışmaya devam eder.|
|**Tamamlanan testler için günlük sıklığını Kaydet**|Test günlüğüne yazılır sıklığını belirtir. Bir sınama girilen her sayısı dışı test günlüğe kaydedilecek sayıyı belirtir. Örneğin, on değerini girmek onuncu, 20, otuzuncu ve benzeri test günlüğüne yazılacağını belirtir. Değerin 0 olarak ayarlanması, hiçbir test günlüklerinin kaydedilecek belirtir.<br /><br /> Daha fazla bilgi için bkz: [nasıl yapılır: Test günlüklerinin hangi sıklıkla kaydedileceğini belirtin](../test/how-to-specify-how-frequently-test-logs-are-saved.md)|
|**Test hatası üzerinde günlük kaydetme**|Belirleyen bir Boolean değeri olup olmadığını test günlüklerinin bir yük testinde test başarısız olursa kaydettiyseniz. Varsayılan, `True` değeridir.<br /><br /> Daha fazla bilgi için bkz: [nasıl yapılır: Test başarısızlıklarının Test günlüklerine kaydedilip kaydedilmediği belirleme](../test/how-to-specify-if-test-failures-are-saved-to-test-logs.md)|

 Daha fazla bilgi için bkz: [yük testi günlüğü ayarlarını değiştirme](../test/modify-load-test-logging-settings.md).

## <a name="results-properties"></a>Sonuçları Özellikleri

|Özellik|Tanım|
|--------------|----------------|
|**Depolama türü**|Bir yük testinde elde edilen performans sayaçlarını depolama yolu. Seçenekler şunlardır:<br /><br /> -   **Veritabanı** -olan bir SQL veritabanında gerektiren bir **Yük Testi Sonuçları Deposu**.<br />-   **Hiçbiri**.|
|**Zamanlama Ayrıntıları Depolama**|Bu ayrıntılandıran depolanır belirlemek için kullanılan **Yük Testi Sonuçları Deposu**. Üç değerler kullanılabilir:<br /><br /> -   **AllIndividualDetails** - toplamak ve her bir test, işlem ve sayfa çalıştırılmış veya yük testi sırasında verilen bireysel zamanlama değerlerini depolamak **Yük Testi Sonuçları Deposu**. Yük Testi Çözümleyicisi'nde sanal kullanıcı etkinlik grafiği kullanmak istiyorsanız gereklidir.<br />     Daha fazla bilgi için bkz: [Ayrıntılar görünümünde sanal kullanıcı etkinliğini çözümleme](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md).<br />-   **Hiçbiri** -herhangi bir zamanlama değerleri toplamaz. Visual Studio 2013 güncelleştirme 4 ve üzeri sürümler için varsayılan değer budur.<br />-   **StatisticsOnly** - toplamak ve her bir test, işlem ve yürütülen veya yük testi sırasında verilen sayfa için bireysel zamanlama değerlerini depolamak yerine yalnızca istatistikleri depolamak **Yük Testi Sonuçları Deposu**.<br /><br /> Daha fazla bilgi için bkz: [nasıl yapılır: zamanlama ayrıntıları depolama özelliğini belirtme](../test/how-to-specify-the-timing-details-storage-property-for-a-load-test.md).|

## <a name="sql-tracing-properties"></a>SQL izleme özellikleri

|Özellik|Tanım|
|--------------|----------------|
|**İzlenen SQL işlemlerinin en düşük süre**|Milisaniye cinsinden SQL izleme tarafından Yakalanacak SQL işlemi en az süresi. Örneğin, bu, yük altında yavaş SQL işlemlerini bulmaya çalışıyorsanız hızlı bir şekilde tamamlamak işlemleri yoksay sağlar.|
|**SQL izleme bağlanma dizesi**|İzlenecek veritabanına erişmek için kullanılan bağlantı dizesi.|
|**SQL izleme dizini**|SQL izleme dosyası izleme sona erdikten sonra nereye yerleştirilir konumu. Bu dizin, SQL Server için yazma izinlerine sahip ve denetleyici için okuma izni.|
|**SQL izleme etkin**|Bu SQL işlemleri izlemesini sağlar. Varsayılan değer `False` şeklindedir.|

## <a name="test-iterations-properties"></a>Test Yinelemeleri özellikleri

|Özellik|Tanım|
|--------------|----------------|
|**Test yinelemeleri**|Yük testi tamamlanmadan önce çalıştırmak için tek tek testlerin toplam sayısını belirtir. Bu özellik yalnızca özelliği "Test Yinelemeleri Kullan" olduğunda geçerlidir `True`.|
|**Test Yinelemeleri Kullan**|Kullanım Test Yinelemeleri ise `True`, tek tek sınamalar içinde yük testi tamamlandı sayısı "Test Yinelemeleri" özelliği tarafından belirtilen sayıya ulaşana kadar yük testi çalışır. Bu durumda olan zaman tabanlı ayarları süresi, çalışma süresi ve bekleme süresini sıcak göz ardı edilir. "Test Yinelemeleri Kullan" ise `False`, tüm zamanlama ayarları uygulamak ve "Test Yinelemeleri" göz ardı edilir.|

 Daha fazla bilgi için bkz: [nasıl yapılır: bir çalıştırma ayarında Test yineleme sayısı belirtin](../test/how-to-specify-the-number-of-test-iterations-in-a-load-test.md).

## <a name="timing-properties"></a>Zamanlama özellikleri

|Özellik|Tanım|
|--------------|----------------|
|**Bekleme süresi**|Test bekleme süresi süre ss biçiminde ifade edilir. Yük testi tamamlandığında, bir yük testi içinde bireysel testler hala çalışıyor. Bekleme süresi boyunca, bu testler tamamlanmadan veya bekleme süresinin sonuna ulaşılana kadar devam edebilirsiniz. Varsayılan olarak, hiçbir bekleme süresi yoktur ve yük testi çalıştırma süresi ayarına göre bittiğinde tek tek testlerin sonlandırılır.|
|**Çalışma süresini**|Ss biçiminde test uzunluğu.|
|**Örnekleme hızı**|Aralığı ss biçiminde performans sayacı değerlerini yakalamak.<br /><br /> Daha fazla bilgi için bkz: [nasıl yapılır: örnek hızı belirtme](../test/how-to-specify-the-sample-rate-for-a-load-test.md).|
|**Yarı süresini ayarlama**|Test başına ve veri örnekleri ss biçiminde kaydedilen başlattığınızda arasındaki süre. Bu örnek değerleri kaydetmeden önce belirli bir yük düzeyine ulaşmak için sanal kullanıcılara adım yükleme için sık kullanılır. Isınma süresi sona erdikten içinde gösterilmeden önce yakalanan örnek değerler **Yük Testi Çözümleyicisi**.|

## <a name="webtest-connections-properties"></a>Web testini bağlantıları özellikleri

|Özellik|Tanım|
|--------------|----------------|
|**Web testini bağlantı modeli**|Bu Web sunucusu bir yük testi içinde Web performans testleri için yük testi aracısından bağlantıları kullanımını denetler. Üç Web performans testi bağlantı modeli seçenekleri kullanılabilir:<br /><br /> - **Kullanıcı başına bağlantı** modeli gerçek bir tarayıcı kullanarak bir kullanıcıyı davranışını taklit eder. Internet Explorer 6 veya Internet Explorer 7 benzetimli Web performans testine çalıştıran her bir sanal kullanıcı Web sunucusu bir veya iki adanmış bağlantıyı kullanır. Web performans testinde ilk istek verildiğinde, ilk bağlantı kurulur. Bir sayfa birden fazla bağımlı istek içerdiğinde, ikinci bir bağlantı kullanılabilir. Bu istekler, iki bağlantıları kullanarak paralel olarak verilir. Bu bağlantılar Web performans testinde sonraki istekleri için yeniden kullanılır. Web performans testi tamamlandığında bağlantı kapatılır. Bu model için bir dezavantajı aracı bilgisayarda açık tutulan bağlantı sayısı (iki kullanıcı yükünün katı kadar) yüksek olabilir olmasıdır. Sonuç olarak, bu yüksek bağlantı sayısını desteklemek için gereken kaynakları tek bir yük testi aracısından kullanıcı yükünü sınırlayabilir. Internet Explorer 8 benzetimli, altı eşzamanlı bağlantı desteklenir.<br />- **Bağlantı havuzu** model, birden çok sanal Web performans testi kullanıcıları arasında Web sunucusuna bağlantılar paylaşarak yük test aracısı kaynaklardaki tasarrufu yapar. Kullanıcı yükü bağlantı havuzu boyutundan daha büyükse farklı sanal kullanıcılar tarafından çalıştırılan Web performans testleri bağlantıyı paylaşır. Bu, bir Web performans testini başka bir Web performans testi bağlantı kullanırken bir isteği bildirmeden önce beklemek zorunda kalabilirler anlamına gelebilir. Yük testi performans sayacı Ortalama bağlantı bekleme süresi bir isteğin izlenen göndermeden önce bir Web performans testi ortalama süre bekler. Bu sayı, bir sayfa için ortalama yanıt süresi küçük olmalıdır. Değilse, bağlantı havuzu boyutu büyük olasılıkla çok küçük.<br />- **Bağlantı başına Test yineleme** modeli, her bir test yineleme için adanmış bağlantılar kullanımını belirtir.|
|**Web testini bağlantı havuzu boyutu**|Bu yük test aracısı ile Web sunucusu arasında bağlantı sayısını belirtir. Bu yalnızca geçerlidir **bağlantı havuzu** modeli.|

##  <a name="LoadTestRunSettingsHowToChange"></a> Çalışma ayarı özelliklerini değiştirme
 Yük testi farklı koşullar altında çalıştırabilmeniz için daha fazla yük testinizle farklı özellik ayarları için çalışma ayarları ekleyebilirsiniz. Örneğin, yeni bir test ayarı ekleyin ve farklı bir örnek hızı kullanabilir veya bir artık çalışma süresini belirtin. Aynı anda yalnızca bir çalışma ayarı kullanabilirsiniz ve etkin olarak işaretleyerek kullanmak için ayarı çalıştırılacağı belirtmeniz gerekir. Bir örnek için bkz: [nasıl yapılır: yük testi için etkin çalışma ayarı seçin](../test/how-to-select-the-active-run-setting-for-a-load-test.md).

### <a name="to-change-run-settings"></a>Çalıştırma ayarlarını değiştirmek için

1.  Bir yük testi açın.

2.  Genişletme **çalıştırma ayarları** klasör.

3.  Seçin bir **çalıştırma ayarları** düğümü.

4.  Üzerinde **Görünüm** menüsünde seçin **Özellikler penceresini**.

     **Özellikler penceresini** görüntülenir ve seçilen çalışma ayarı özellikleri görüntülenir.

5.  Kullanım **Özellikler penceresini** çalıştırma ayarlarını değiştirmek için. Örneğin, çalışma süresini **00:05:00** beş dakika için testinizi çalıştırmak için.

    > [!NOTE]
    > Çalışma ayarları özelliklerini ve açıklamalarının tam listesi için bkz: [yük testi çalıştırma ayarı özellikleri](../test/load-test-run-settings-properties.md).

6.  Özellikleri değiştirme işiniz bittiğinde, yük testlerini kaydedin. Üzerinde **dosya** menüsünde seçin **kaydetmek**.

> [!NOTE]
> Sayaç kümesi eşlemeleri çalıştırma ayarları, aynı zamanda bir parçasıdır. Daha fazla bilgi için bkz: [sayaç kümelerini ve eşik kurallarını bilgisayarlar için bir yük testinde belirtme](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi çalıştırma ayarlarını yapılandırma](../test/configure-load-test-run-settings.md)