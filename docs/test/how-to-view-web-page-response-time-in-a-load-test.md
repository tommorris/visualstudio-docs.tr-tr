---
title: Visual Studio'da bir yük testinde sayfa yanıt süresi
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, response times
- response times in load tests
- load test results, response times
ms.assetid: e61c49f3-3161-45b1-9220-08b5459065a2
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 3f65920a1f47895ab6caf4bc84dd75c8100487a9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-view-web-page-response-time-in-a-load-test-using-the-load-test-analyzer"></a>Nasıl yapılır: Yük Testi Çözümleyicisi Kullanarak Bir Yük Testinde Web Sayfası Yanıt Süresini Görüntüleme

Her Web sayfası yüklemek gereken süreyi olarak bilinen *yanıt süresi*. Web performans testi oluşturduğunuzda, her bir Web sayfası istek için yanıt süresi hedefi Web performans testinde ayarlayabilirsiniz.

Bir yük testinde Web performans testi yoğunluk altında çalıştırırsanız, her bir sayfa için aşağıdaki bilgileri analiz edebilirsiniz olacaktır:

-   Sayfa için ortalama yanıt süresi.

-   Sayfası için yanıt süresi hedefi karşılayan test yinelemeleri yüzdesi.

-   Tablo görünümü veya grafik görünümünde Yük Testi Çözümleyicisi kullanarak Web sayfası yanıt sürelerini çözümleyebilirsiniz:

-   Web sayfası yanıt sürelerini Tablo görünümünde analiz etme

-   Web sayfası yanıt sürelerini Grafik görünümünde analiz etme

## <a name="view-response-time-data-in-a-table"></a>Görünüm yanıt zamanı verilerini bir tabloda

### <a name="to-view-response-time-data-in-a-table"></a>Bir tablodaki yanıt zamanı verilerini görüntülemek için

1.  Yük Testi Çözümleyicisi'nde seçin **tabloları** tablo kılavuzunun görüntülendiğinden emin olmak için araç çubuğunda.

2.  İçinde **tablo** aşağı açılan liste kutusunda **sayfaları**.

3.  Her bir sayfa için veri kılavuzunda görüntülenir. Genellikle aşağıdaki sütunlar görüntülenir.

    |||
    |-|-|
    |**Sayfa**|Web sayfasının adı.|
    |**Senaryo**|Senaryo adı. Web performans testinde birden fazla senaryo varsa önemlidir.|
    |**Test**|Web performans testi adı. Yükleme testinizde birden fazla Web performans testi varsa önemlidir.|
    |**Ağ**|Ağ türü.<br /><br /> Varsayılan olarak, bu veriler toplanmaz. İçinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** düğümü, değiştirilecek çalışma ayarı düğümünü seçin. İçinde **özellikleri** penceresinde için **zamanlama ayrıntıları depolama** özelliği, select **AllIndividualDetails**.|
    |**Toplam**|Web sayfası için yapılan isteklerinin toplam sayısı. Yük testi tüm yinelemelerini toplamdır.|
    |**Ave**|Ortalama sayfa yanıt süresi.<br /><br /> Varsayılan olarak, bu veriler toplanmaz. İçinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** düğümü, değiştirilecek çalışma ayarı düğümünü seçin. İçinde **özellikleri** penceresinde için **zamanlama ayrıntıları depolama** özelliği, select **AllIndividualDetails**.|
    |**Min**|En düşük sayfa yanıt süresi.<br /><br /> Varsayılan olarak, bu veriler toplanmaz. İçinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** düğümü, değiştirilecek çalışma ayarı düğümünü seçin. İçinde **özellikleri** penceresinde için **zamanlama ayrıntıları depolama** özelliği, select **AllIndividualDetails**.|
    |**ORTANCA**|Ortanca sayfa yanıt süresi.<br /><br /> Varsayılan olarak, bu veriler toplanmaz. İçinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** düğümü, değiştirilecek çalışma ayarı düğümünü seçin. İçinde **özellikleri** penceresinde için **zamanlama ayrıntıları depolama** özelliği, select **AllIndividualDetails**.|
    |**% 90**|Yanıt süresi 90 yüzdebirlik. Bu sayfa % 90'ını bu sayıdan daha hızlı yanıt verdiğini ve sayfaların % 10 daha yavaş yanıt gösterir.<br /><br /> Varsayılan olarak, bu veriler toplanmaz. İçinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** düğümü, değiştirilecek çalışma ayarı düğümünü seçin. İçinde **özellikleri** penceresinde için **zamanlama ayrıntıları depolama** özelliği, select **AllIndividualDetails**.|
    |**% 95**|Yanıt süresi için 95 yüzdebirlik. Bu sayfaların % 95 bu sayıdan daha hızlı yanıt verdiğini ve %5 sayfaların daha yavaş yanıt gösterir.|
    |**% 99**|İçin 99 yanıt süresi. Bu sayfaların % 99 bu sayıdan daha hızlı yanıt verdiğini ve %1 sayfaların daha yavaş yanıt gösterir.<br /><br /> Varsayılan olarak, bu veriler toplanmaz. İçinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** düğümü, değiştirilecek çalışma ayarı düğümünü seçin. İçinde **özellikleri** penceresinde için **zamanlama ayrıntıları depolama** özelliği, select **AllIndividualDetails**.|
    |**max**|En fazla sayfa yanıt süresi.<br /><br /> Varsayılan olarak, bu veriler toplanmaz. İçinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** düğümü, değiştirilecek çalışma ayarı düğümünü seçin. İçinde **özellikleri** penceresinde için **zamanlama ayrıntıları depolama** özelliği, select **AllIndividualDetails**.|
    |**Standart sapma**|Varsayılan olarak, standart sapma verileri toplanmaz. İçinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** düğümü, değiştirilecek çalışma ayarı düğümünü seçin. İçinde **özellikleri** penceresinde için **zamanlama ayrıntıları depolama** özelliği, select **AllIndividualDetails**.|
    |**Sayfa süresi**|Web sayfası için yapılan tüm istekleri için ortalama yanıt süresi.|
    |**Hedef**|Sayfa zamanı hedefi. Bu sayfa için sabit bir değerdir. **Not:** sayfa saati hedefi yalnızca hedef Web performans testinde istek için tanımlandığında görüntülenir.|
    |**% Toplantı hedefi**|Web sayfası için yanıt süresi hedefi karşılanan yapılan isteklerin yüzdesi.|

 Daha fazla bilgi için bkz: [yük testi sonuçlarını çözümleme ve hataları Tablo görünümünde](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

## <a name="view-response-time-data-in-a-graph"></a>Grafik görünümü yanıt zamanı verilerini

Yanıt zamanı verilerini nasıl yük testi sırasında zaman içinde değişip görmek için bir grafik görüntüleyebilirsiniz. Bu yük düzeni artar (örneğin, Adım yük düzeni kullanıyorsanız) test çalışmaları özellikle yararlıdır. Daha fazla bilgi için bkz: [modeli sanal kullanıcı etkinlikleri için yük desenlerini düzenleme](../test/edit-load-patterns-to-model-virtual-user-activities.md).

### <a name="to-view-response-time-data-in-a-graph"></a>Bir grafik olarak yanıt zamanı verilerini görüntülemek için

1.  Yük Testi Çözümleyicisi'nde seçin **grafikleri** araç çubuğunda grafik görüntülendiğinden emin olun.

2.  İçinde **sayaçları** penceresinde içinde ilgilendiğiniz senaryonun düğümünü genişletin (örneğin, `Scenario1`).

3.  İçinde ilgilendiğiniz Web performans testi düğümünü genişletin.

4.  Düğümünü **sayfaları**.

5.  İçinde ilgilendiğiniz sayfasının düğümünü genişletin.

6.  Sağ **% toplantı hedefi sayfaları** ve ardından **grafikte sayaç Göster**.

     Veri grafiğe eklenir.

7.  (İsteğe bağlı) Ort için önceki adımı yineleyin Sayfa süresi, sayfa yanıt süresi hedefi ve toplam sayfa sayısı.

    > [!NOTE]
    > Sayfa yanıt süresi hedefi sabittir.

 Daha fazla bilgi için bkz: [Grafik görünümünde yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-in-the-graphs-view.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçlarını ve hatalarını Tablo görünümünde analiz eder.](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)
- [Nasıl yapılır: yük testi sonuçlarını çözümleme için erişim](../test/how-to-access-load-test-results-for-analysis.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)