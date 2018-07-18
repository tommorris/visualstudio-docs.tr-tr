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
ms.openlocfilehash: ba6a5b666777e692fe2c214f165c0bc1da7fee9d
ms.sourcegitcommit: 893c09d58562c378a4ba057bf2a06bde1c80df90
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2018
ms.locfileid: "35676742"
---
# <a name="how-to-view-web-page-response-time-in-a-load-test-using-the-load-test-analyzer"></a>Nasıl yapılır: Yük Testi Çözümleyicisi Kullanarak Bir Yük Testinde Web Sayfası Yanıt Süresini Görüntüleme

Her Web sayfasının yüklenmesi için geçen süreyi olarak da bilinen *yanıt süresi*. Web performans testi oluşturduğunuzda, Web performans testinde Web sayfası her istek için yanıt süresi hedefi ayarlayabilirsiniz.

Bir yük testi içinde Web performans testinizi yoğunluk altında çalıştırırsanız, her sayfa için aşağıdaki bilgileri analiz etmek mümkün olacaktır:

-   Sayfa için ortalama yanıt süresi.

-   Sayfanın yanıt süresi hedefi karşılayan test yinelemeleri yüzdesi.

-   Tablo veya grafik görünümünde Yük Testi Çözümleyicisi'nde kullanarak Web sayfası yanıt sürelerini analiz edebilirsiniz:

-   Tablo görünümünde Web sayfası yanıt sürelerini analiz etme

-   Grafik görünümünde Web sayfası yanıt sürelerini analiz etme

## <a name="view-response-time-data-in-a-table"></a>Bir tablodaki görünümü yanıt süresi verilerini

### <a name="to-view-response-time-data-in-a-table"></a>Bir tablodaki yanıt süresi verilerini görüntülemek için

1.  Yük Testi Çözümleyicisi'nde seçin **tabloları** araç çubuğundaki tablo kılavuzunu görüntülendiğinden emin olun.

2.  İçinde **tablo** aşağı açılan liste kutusunda **sayfaları**.

3.  Veriler her sayfa için kılavuz görüntülenir. Normalde, aşağıdaki sütunlar görüntülenir.

    |Sütun başlığı|Açıklama|
    |-|-|
    |**Sayfa**|Web sayfasının adı.|
    |**Senaryo**|Senaryonun adı. Birden fazla senaryo Web performans testiniz varsa önemlidir.|
    |**Test**|Web performans testi adı. Yük testinize birden fazla Web performans testiniz varsa önemlidir.|
    |**Ağ**|Ağ türü.<br /><br /> Varsayılan olarak, bu verileri toplanmaz. İçinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** düğümünün değiştirmek için çalışma ayarı düğümünü seçin. İçinde **özellikleri** penceresinde için **Zamanlama Ayrıntıları Deposu** özelliği, select **AllIndividualDetails**.|
    |**Toplam**|Web sayfası için yapılan isteklerinin toplam sayısı. Tüm yinelemeler yük testinde toplamdır.|
    |**Dosyaya Kaydet**|Ortalama sayfa yanıt süresi.<br /><br /> Varsayılan olarak, bu verileri toplanmaz. İçinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** düğümünün değiştirmek için çalışma ayarı düğümünü seçin. İçinde **özellikleri** penceresinde için **Zamanlama Ayrıntıları Deposu** özelliği, select **AllIndividualDetails**.|
    |**Min**|En küçük sayfa yanıt süresi.<br /><br /> Varsayılan olarak, bu verileri toplanmaz. İçinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** düğümünün değiştirmek için çalışma ayarı düğümünü seçin. İçinde **özellikleri** penceresinde için **Zamanlama Ayrıntıları Deposu** özelliği, select **AllIndividualDetails**.|
    |**ORTANCA**|Ortalama sayfa yanıt süresi.<br /><br /> Varsayılan olarak, bu verileri toplanmaz. İçinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** düğümünün değiştirmek için çalışma ayarı düğümünü seçin. İçinde **özellikleri** penceresinde için **Zamanlama Ayrıntıları Deposu** özelliği, select **AllIndividualDetails**.|
    |**%90**|Yanıt süresi için 90. yüzdebirlik. Bu, %90 sayfa bu sayıdan daha hızlı yanıt ve %10 sayfalarının daha yavaş yanıt verdiğini gösterir.<br /><br /> Varsayılan olarak, bu verileri toplanmaz. İçinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** düğümünün değiştirmek için çalışma ayarı düğümünü seçin. İçinde **özellikleri** penceresinde için **Zamanlama Ayrıntıları Deposu** özelliği, select **AllIndividualDetails**.|
    |**%95**|95. yüzdebirlik için yanıt süresi. Bu %95 sayfa bu sayıdan daha hızlı yanıt ve %5 sayfalarının daha yavaş yanıt verdiğini gösterir.|
    |**% 99**|99. yüzdebirlik dilimde için yanıt süresi. Bu sayfaları %99 bu sayıdan daha hızlı yanıt ve %1 sayfalarının daha yavaş yanıt verdiğini gösterir.<br /><br /> Varsayılan olarak, bu verileri toplanmaz. İçinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** düğümünün değiştirmek için çalışma ayarı düğümünü seçin. İçinde **özellikleri** penceresinde için **Zamanlama Ayrıntıları Deposu** özelliği, select **AllIndividualDetails**.|
    |**en fazla**|En fazla sayfa yanıt süresi.<br /><br /> Varsayılan olarak, bu verileri toplanmaz. İçinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** düğümünün değiştirmek için çalışma ayarı düğümünü seçin. İçinde **özellikleri** penceresinde için **Zamanlama Ayrıntıları Deposu** özelliği, select **AllIndividualDetails**.|
    |**Std sapma**|Varsayılan olarak, standart sapma verileri toplanmaz. İçinde bu verileri toplamak için **Yük Testi Düzenleyicisi**altında **çalıştırma ayarları** düğümünün değiştirmek için çalışma ayarı düğümünü seçin. İçinde **özellikleri** penceresinde için **Zamanlama Ayrıntıları Deposu** özelliği, select **AllIndividualDetails**.|
    |**Sayfa saati**|Web sayfası için yapılan tüm istekleri için ortalama yanıt süresi.|
    |**Hedef**|Sayfa saati hedefi. Bu sayfa için sabit bir değerdir. **Not:** sayfa saati hedefi, Web performans testinde istek için hedef yalnızca tanımlanmış olduğunda görüntülenir.|
    |**% Toplantı hedefi**|Web sayfası için yanıt süresi hedefi karşılayan yapılan isteklerin yüzdesi.|

 Daha fazla bilgi için [yük testi sonuçlarını çözümleme ve hataları Tablo görünümünde](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

## <a name="view-response-time-data-in-a-graph"></a>Grafik görünümü yanıt süresi verilerini

Yanıt süresi verilerini nasıl Yük testiniz sırasında zamanla değişeceğini görmek için bir grafik de görüntüleyebilirsiniz. Test çalışırken (örneğin, adım yükü düzenini kullanıyorsanız), yük düzeni artarsa bu özellikle yararlıdır. Daha fazla bilgi için [modeli sanal kullanıcı etkinlikleri için yük desenlerini düzenleme](../test/edit-load-patterns-to-model-virtual-user-activities.md).

### <a name="to-view-response-time-data-in-a-graph"></a>Bir yanıt süresi verilerini görüntülemek için

1.  Yük Testi Çözümleyicisi'nde seçin **grafikleri** araç çubuğundaki graf görüntülendiğinden emin olun.

2.  İçinde **sayaçları** penceresi içinde ilginizi senaryo düğümünü genişletin (örneğin, `Scenario1`).

3.  Web performans testi, ilgilendiğiniz düğümünü genişletin.

4.  Düğümü genişletmek **sayfaları**.

5.  Hangi ilgilendiğiniz sayfayı düğümünü genişletin.

6.  Sağ **% toplantı hedefi sayfaları** seçip **grafik üzerinde sayaç Göster**.

     Verileri grafiğe eklenir.

7.  (İsteğe bağlı) Ort için önceki adımı yineleyin Sayfa süresi, sayfa yanıt süresi hedefi ve toplam sayfa sayısı.

    > [!NOTE]
    > Sayfa yanıt süresi hedefi sabittir.

 Daha fazla bilgi için [Grafik görünümünde yük testi sonuçlarını analiz](../test/analyze-load-test-results-in-the-graphs-view.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçlarını ve hatalarını Tablo görünümünde çözümleyin](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)
- [Nasıl yapılır: yük testi sonuçları analize erişme](../test/how-to-access-load-test-results-for-analysis.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)