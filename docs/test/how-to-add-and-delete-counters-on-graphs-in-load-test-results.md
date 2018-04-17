---
title: Visual Studio Yük testi sonuçlarında grafiklerde sayaç ekleme ve silme | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load test results graphs, adding counters
- load test results graph
- load test, results graph
- load test results, graphs
ms.assetid: 81536233-1962-40d9-9511-0b4633814d90
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 1ec02769cc3960b4b1b7f4dd7a04d3d78193c1e9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-and-delete-counters-on-graphs-in-load-test-results"></a>Nasıl yapılır: Yük Testi Sonuçlarındaki Grafiklerde Sayaç Ekleme ve Silme

Sayaçlar panelini performans sayaçları grafiğe eklemek için kullanabilirsiniz.

 ![Grafik eklenen sayacı](../test/media/ltest_selectcounter.png "LTest_SelectCounter")

 **Performans sayacı örnekleme aralığı hakkında önemli noktalar**

 İçin bir değer seçin **örnek hızı** özelliğinde yük testi çalıştırma ayarları yük testlerini uzunluğuna göre. Varsayılan değer olarak beş saniye gibi daha küçük bir örnek hızı yük testi sonuçları veritabanında daha fazla alan gerektirir. Uzun yük testleri için örnek hızı artırma topladığınız veri miktarını azaltır. Daha fazla bilgi için bkz: [nasıl yapılır: örnek hızı belirtme](../test/how-to-specify-the-sample-rate-for-a-load-test.md).

 Örnek hızları ilgili bazı kurallar şunlardır:

|Yük Test süresi|Örnek hızı önerilir|
|------------------------|-----------------------------|
|\< 1 saat|5 saniye|
|1 - 8 saatte bir|15 saniye|
|8 - 24 saat|30 saniye|
|> 24 saat|60 saniye|

 **Yüzdelik veri toplamak için zamanlama ayrıntılarını dahil olmak üzere dikkat edilmesi gereken noktalar**

 Yük testi adlı Düzenleyicisi'nde çalışma ayarlarında bir özellik yok **zamanlama ayrıntıları depolama**. Varsa **zamanlama ayrıntıları depolama** özelliğinin etkin olduğundan ve her bir bireysel test, işlem ve sayfa yük testi sırasında yürütme süresi yük testi sonuçları deposunda depolanır. Bu testler, işlemleri ve sayfalar tablolarda Yük Testi Çözümleyicisi gösterilecek 90 ve 95 yüzdelik veri sağlar.

 Etkinleştirme için iki seçenek vardır **zamanlama ayrıntıları depolama** çalışma ayarları özelliklerini özelliğinde adlandırılmış **StatisticsOnly** ve **AllIndividualDetails**. Her iki seçenek için tüm tek tek sınamalar, sayfalar ve işlemleri zaman aşımına ve bireysel zamanlama verisinden yüzdelik veri hesaplanır. İle farktır **StatisticsOnly** seçeneğini yüzdelik veri hesaplanır hemen veri deposundan silinen bireysel zamanlama. Bu zamanlama ayrıntıları kullandığınızda, deposunda gereken alan miktarını azaltır. Ancak, İleri düzey kullanıcılar SQL araçlarını kullanarak zamanlama ayrıntı verilerini diğer yollarla işlemek isteyebilirsiniz. Bu durumda, ise **AllIndividualDetails** zamanlama ayrıntı verileri bu işlem için kullanılabilir olmasını sağlamak seçeneği kullanılmalıdır. Ayrıca, özelliği ayarlamak, **AllIndividualDetails**, sonra da yük testi tamamlandıktan sonra Yük Testi Çözümleyicisi sanal kullanıcı etkinlik grafiğini kullanarak sanal kullanıcı etkinliğini çözümleyebilirsiniz. Daha fazla bilgi için bkz: [Ayrıntılar görünümünde sanal kullanıcı etkinliğini çözümleme](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md).

Zamanlama Ayrıntıları verileri özellikle daha uzun yük testleri için çok büyük olabilir depolamak için yük testi sonuçları deposunda gereken alan miktarı. Yük testi çalıştırma tamamlanana kadar bu veri yükleme testi aracısında depolandığı için aynı zamanda, yük testi sonuçları havuzu yük testi sonunda bu verileri depolamak için daha uzun zamandır. Yük testi sona erdiğinde, veri depoya depolanır. Varsayılan olarak, **zamanlama ayrıntıları depolama** özelliği etkin hale getirilir. Sınama ortamınız için bir sorun varsa ayarlamak isteyebilirsiniz **zamanlama ayrıntıları depolama** için **hiçbiri**.

Daha fazla bilgi için bkz: [nasıl yapılır: zamanlama ayrıntıları depolama özelliğini belirtme](../test/how-to-specify-the-timing-details-storage-property-for-a-load-test.md).

## <a name="to-display-a-particular-performance-counter-on-a-load-test-graph"></a>Bir yük testi grafiğinde belirli bir performans sayacına görüntülemek için

1.  Bir yük testi tamamlandıktan sonra ya da Yük Testi Çözümleyicisi'nin araç çubuğunda, bir test sonucu yükledikten sonra seçin **grafikleri**.

     **Sayaçları** paneli grafikler görünümünde görüntülenir.

    > [!NOTE]
    > Sayaçlar panelini görünür durumda değilse, seçin **Sayaçlar panelini Göster** araç çubuğunda.

2.  Grafik olarak görüntülenen görmek istediğiniz performans sayacı bulana kadar Sayaçlar panelini hiyerarşideki düğümleri genişletin.

     Örneğin, testleri çalıştırdığı bir bilgisayarda kullanılabilir bellek görüntülemek için öğesini genişletin **bilgisayarlar**, bilgisayar düğümünü genişletin ve ardından **bellek**. Göreceğiniz **Kullanılabilir MBayt** sayacı.

3.  Performans sayacı görüntülemek istediğiniz grafiği seçin.

4.  Performans sayacı sağ **sayaçları** panel ve seçin **grafikte sayaç Göster**.

    > [!TIP]
    > Grafikte performans sayacının verileri görüntüleme geçici olarak durdurmak için göstergede performans sayacı için onay kutusunu temizleyin. Bu grafikte eğilim çizgisini görüntülemeden hala çözümlenmesi min, max ve ortalama istatistikler sağlar. Bu sorunları çözümlerken grafiği birkaç çakışan performans sayacı çizimleri içeriyorsa yararlı olabilir. Daha fazla bilgi için bkz: [yük testlerini çözümlemek için grafik görünümü göstergesini kullanma](../test/use-the-graphs-view-legend-to-analyze-load-tests.md).

5.  Performans sayacı verilerini Grafikten kaldırmak için performans sayacı sağ tıklatın **sayaç** seçin ve gösterge sütunu **silmek**.

     \- veya -

     Veri satırına grafik seçip sağ tıklatın **silmek**.

     \- veya -

     Performans sayacı seçin **sayaç** gösterge veya veri sütunu çizgi grafikte ve tuşuna basarak **silmek** anahtarı.

    > [!NOTE]
    > Bir performans sayacı gösterge grafiği kullanarak yerleştirmeyi isteyebilirsiniz **gösterge Sayaç Ekle** komutu.

## <a name="see-also"></a>Ayrıca bkz.

- [Grafik görünümünde yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-in-the-graphs-view.md)
- [Nasıl yapılır: özel grafikler oluşturma](../test/how-to-create-custom-graphs-in-load-test-results.md)