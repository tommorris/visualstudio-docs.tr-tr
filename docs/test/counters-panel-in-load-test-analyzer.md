---
title: Visual Studio yük testlerini çözümlemek için sayaç paneli
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, counters panel
ms.assetid: e1a388d7-5d33-4631-931a-5653ac4aefdc
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: fd87cdb912b7e2dcf13476bab610935db5ca4fd7
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36304780"
---
# <a name="use-the-counters-panel-in-graphs-view-and-tables-view"></a>Grafikler görünümünde ve Tablolar görünümünde Sayaçlar panelini kullanma

**Sayaçları** bir yük testi çalışırken ya da bir yük testi sonuç çözümlerken paneli grafikler görünümünde ve Tablolar görünümünde Yük Testi Çözümleyicisi görünür. Daha fazla bilgi için bkz: [Çözümle yük testi sonuçları grafikler görünümünde](../test/analyze-load-test-results-in-the-graphs-view.md), [analiz yük testi sonuçlarını ve hatalarını Tablo görünümünde](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) ve [nasıl yapılır: erişim yük testi sonuçlarını çözümlemeiçin](../test/how-to-access-load-test-results-for-analysis.md).

**Sayaçları** paneli Yük testi sırasında toplanan tüm performans sayaçlarının yapılandırılmış bir görünümünü görüntüler. Göster veya gizle **sayaçları** seçerek paneli **Sayaçlar panelini Göster** üzerinde **Yük Testi Çözümleyicisi** araç.

Sayaçları ve yaprak düğümlerin çizilebilir performans sayacı örnekleri olduğu bir ağaç yapısında düzenlenir.

Sayaçlar panelini aşağıdaki özellikleri sağlar:

-   Eşik ihlali bilgileri iletişim kurar.

-   Seçimi Grafikleme sayaçları.

-   Tüm performans sayaçlarının yapılandırılmış ağaç görünümünde yük testi ile aşağıdaki birincil dalları çalıştırması sırasında toplanan:

    -   **Genel:** her test aracısı ve tüm yük testi için performans sayacı verilerini Özet içerir.

    -   **Senaryo adı:** adlarıyla yük testi senaryosu performans sayacı ağacında etiketli dalları belirli yük testi senaryosuna ile ilişkili tüm yük testi sayaç örnekleri içerir. Çoğu yük testi sayacı bir senaryo dalında iç içe geçmiştir.

         Bir senaryo dalı Web performans testi düğümlerini içerir. Web performans testi düğümleri içeren sayfaları, istekleri ve işlem düğümleri. Bu yapı herhangi bir yaprak düğümün grafiğe eklenebilir bir performans sayacı ' dir.

    -   **Bilgisayarlar:** bilgisayar tarafından gruplandırılmış olan tüm olmayan yük testi sayacı örneklerini içerir. Bilgisayarlar dalı seçili test ayarlarını roller bölümünde belirtilen yük test denetleyicisi ile ilişkili olan her bilgisayar için bir düğüm içeriyor. Daha fazla bilgi için bkz: [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md).

         Her bilgisayar düğümünün o bilgisayardan toplanan performans sayacı kategorileri kümesini içerir. Kategoriler, sayaçları içerir ve performans sayacı örneği adları sayaçlar içerir.

    -   **Hata:** yük testi sırasında algılanan tüm hataları içerir. Hata düğümü birçok alt kategori hata düğümlerini içerir. Alt kategoriler, çeşitli hatalar, örneğin, özel durumlar ve HTTP hataları özgüdür.

### <a name="scenario-name-node-in-counters-panel"></a>Sayaç panelinde Senaryo adı düğümü

|Sayaç paneli|Açıklama|
|-|-|
|![Bölmenin Senaryo adı düğümü sayacı](../test/media/ltest__namenode.png)|1. Yük testi Scenario1 ile ilişkili tüm performans sayaçları, bu düğüm altında görünür.<br />2. Bir senaryoya ait tüm testler senaryo düğümünün altında bulunur. Etiket test adını gösterir.<br />3. Bir test düğümü altındaki yaprak düğümler yük testi test çalışması sayaçları, sayaç için örnek adı test adı olduğu ' dir.<br />4. Tüm Web performans testi dalında ile ilişkili test sayfası örnekleri yükleyin. Bu düğümde yük testi Senaryo1 IBuyBrowse Web performans testinde Login GET (Raporlama adı) sayfayla ilişkili örnekleri ayak tüm yük testi burada bulunur.<br />5. Bir sayfa düğümü altındaki yaprak düğümler yük test sayfası sayaçları.<br />6. Tüm örnekleri bir Web performans testi ile ilişkili bir Web performans testi dalında bulunan testi istekleri sayacı yük. Bu düğümde tüm örnekleri oturum açma (Raporlama adı) yük testi burada yer alan Scenario1 o IBuyBrowse Web performans testinde GET isteği ile ilişkili istek.<br />7. Bir istek düğümü altındaki yaprak düğümler yük testi isteği sayaçları.<br />8. Web performans testi ile ilişkili tüm yük testi işlem sayacı örnekleri, bir Web performans testi dalında yer alır. Bu düğümde tüm işlem sayacı örnekleri yük testi Scenraio1 IBuyBrowse Web performans testinde, adlandırılmış Transaction1 burada bulunur işlem ile ilişkilendirin.<br />9. Bir işlem düğümünde yaprak düğümlerin yük testi işlem sayaçları.<br />10. Birim testi düğümü.|

## <a name="tasks"></a>Görevler

|Görevler|İlgili Konular|
|-----------|-----------------------|
|**Daha fazla performans sayacı grafik görünümünde bir grafik ekleyin:** içinde **sayaçları** Masası ekleyebileceğiniz farklı veri türleri bir yük testi grafiğine grafik üzerinde daha fazla performans sayaçlarını ekleyerek.|-   [Nasıl yapılır: ekleme ve grafiklerde sayaç silme](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)|
|**İhlal edildiğini yük testinde belirtilen eşikleri çözümleyin:** **sayaçları** paneli sonra tablolar ve grafikler daha fazla çözümleme için ekleyebileceğiniz Eşik ihlallerini temsil eden simgeleri görüntüler.|-   [Nasıl yapılır: Sayaçlar panelini kullanarak Eşik ihlallerini çözümleme](../test/analyze-threshold-rule-violations-in-load-tests.md)|
|**Yük testi sırasında algılanan hataları çözümleyin:** **sayaçları** paneli hata kategorileri ve alt kategorileri için grafikleri hataları eklemek için kullanabileceğiniz HTTP hataları gibi içeren bir hata düğümü içerir Daha fazla çözümleme.|-   [Nasıl yapılır: Sayaçlar panelini kullanarak hataları çözümleme](../test/how-to-analyze-errors-using-the-counters-panel.md)|

## <a name="performance-counter-sampling-interval-considerations"></a>Performans sayacı örnekleme aralığı hakkında önemli noktalar

İçin bir değer seçin **örnek hızı** özelliğinde yük testi çalıştırma ayarları yük testlerini uzunluğuna göre. Varsayılan değer olarak beş saniye gibi daha küçük bir örnek hızı yük testi sonuçları veritabanında daha fazla alan gerektirir. Uzun yük testleri için örnek hızı artırma topladığınız veri miktarını azaltır. Daha fazla bilgi için bkz: [nasıl yapılır: örnek hızı belirtme](../test/how-to-specify-the-sample-rate-for-a-load-test.md).

Örnek hızları ilgili bazı kurallar şunlardır:

|Yük Test süresi|Örnek hızı önerilir|
|------------------------|-----------------------------|
|\< 1 saat|5 saniye|
|1 - 8 saatte bir|15 saniye|
|8 - 24 saat|30 saniye|
|> 24 saat|60 saniye|

## <a name="considerations-for-including-timing-details-to-collect-percentile-data"></a>Yüzdelik veri toplamak için zamanlama ayrıntılarını dahil dikkat edilmesi gereken noktalar

Yük testi adlı Düzenleyicisi'nde çalışma ayarlarında bir özellik yok **zamanlama ayrıntıları depolama**. Varsa **zamanlama ayrıntıları depolama** özelliğinin etkin olduğundan ve her bir bireysel test, işlem ve sayfa yük testi sırasında yürütme süresi yük testi sonuçları deposunda saklanır. Bu testler, işlemleri ve sayfalar tablolarda Yük Testi Çözümleyicisi gösterilecek 90 ve 95 yüzdelik veri sağlar.

Etkinleştirme için iki seçenek vardır **zamanlama ayrıntıları depolama** çalışma ayarları özelliklerini özelliğinde: **StatisticsOnly** ve **AllIndividualDetails**. Her iki seçenek için tüm tek tek sınamalar, sayfalar ve işlemleri zaman aşımına ve bireysel zamanlama verisinden yüzdelik veri hesaplanır. İle farktır **StatisticsOnly** seçeneğini yüzdelik veri hesaplanır hemen veri deposundan silinen bireysel zamanlama. Bu zamanlama ayrıntıları kullandığınızda, deposunda gereken alan miktarını azaltır. Ancak, İleri düzey kullanıcılar SQL araçlarını kullanarak zamanlama ayrıntı verilerini diğer yollarla işlemek isteyebilirsiniz. Bu durumda, ise **AllIndividualDetails** zamanlama ayrıntı verileri bu işlem için kullanılabilir olmasını sağlamak seçeneği kullanılmalıdır. Ayrıca, özelliği ayarlamak, **AllIndividualDetails**, kullanarak sanal kullanıcı etkinliğini çözümleme sonra **sanal kullanıcı etkinlik** grafik yük testi sonra Yük Testi Çözümleyicisi çalıştırma tamamlandı. Daha fazla bilgi için bkz: [Ayrıntılar görünümünde sanal kullanıcı etkinliğini çözümleme](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md).

Yük testi sonuçları havuzu zamanlama ayrıntıları verileri depolamak için gereken alanı özellikle daha uzun yük testleri için büyük olabilir. Yük testi çalıştırma tamamlanana kadar bu veri yükleme testi aracısında depolandığı için aynı zamanda, yük testi sonuçları havuzu yük testi sonunda bu verileri depolamak için daha uzun zamandır. Yük testi sona erdiğinde, veri depoya depolanır. Varsayılan olarak, **zamanlama ayrıntıları depolama** özelliği etkin hale getirilir. Sınama ortamınız için bir sorun varsa ayarlamak isteyebilirsiniz **zamanlama ayrıntıları depolama** için **hiçbiri**.

Daha fazla bilgi için bkz: [nasıl yapılır: zamanlama ayrıntıları depolama özelliğini belirtme](../test/how-to-specify-the-timing-details-storage-property-for-a-load-test.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)