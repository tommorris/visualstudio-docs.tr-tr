---
title: Yük Testi Çözümleyicisinin Grafik Görünümünde Yük Testi Sonuçlarını Çözümleme
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.monitor.graph.view
helpviewer_keywords:
- graphs, analyzing load tests
- load tests, graphs in Load Test Viewer
- Load Test Viewer, graphs
- load tests, results graphs
- load tests, using graphs
- load test results, graphs
ms.assetid: 4a919cd8-541c-40ee-be3b-352fabc56140
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 5540eb31d764e82cb0c6cd46eb63cb893559a70f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31973160"
---
# <a name="analyze-load-test-results-in-the-graphs-view-of-the-load-test-analyzer"></a>Yük Testi Çözümleyicisinin Grafik görünümünde yük testi sonuçlarını çözümleme

Bir yük testi sonuçlarını farklı bölmelerde veri olarak görüntülenir.

Grafik olarak test sonuçlarını görüntülemek için seçin **grafikleri** yük testi araç çubuğunda. Her bir grafik en üstünde bir aşağı açılan listesinde görüntülenen grafik ada sahip bir panelinde görüntülenir. Farklı bir grafik panelinde görüntülemek için listeden farklı bir grafik adı seçin.

En fazla dört grafik aynı anda paneller görüntülenebilir. Panel düzeni araç çubuğu düğmesini kullanarak farklı paneli düzeni arasında geçiş yapabilirsiniz.

Birkaç yerleşik grafik sağlanır. Yerleşik kullanabilirsiniz grafikleri olduğu gibi veya bunları özelleştirebilirsiniz. Ayrıca, kendi grafiklerinizi oluşturabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: grafiklerde sayaç ekleme ve silme](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md) ve [nasıl yapılır: özel grafikler oluşturma](../test/how-to-create-custom-graphs-in-load-test-results.md).

## <a name="built-in-graphs"></a>Yerleşik grafikleri

Aşağıdaki tabloda yük testi sonuçlarını analiz etmek kullanılabilir olan yerleşik grafikleri listeler.

|Grafik adı|Açıklama|
|----------------|-----------------|
|Anahtar göstergeleri|Temel yönlerini açıklayan sayaçları kullanıcı yük, üretilen iş ve yanıt süresi gibi performansını test edin.|
|Test yanıt süresi|Çalıştırmak için zaman testleri miktarını hakkındaki verileri alın.|
|Sayfa yanıt süresi|Yük testi sırasında erişilen Web sayfaları için ortalama yanıt süresi.|
|Test sisteminde|Hangi uygulamanın çalışmalarını test bilgisayarlar hakkında bilgi. Bu, bellek kullanımı, işlemci, fiziksel disk, işlemleri hakkındaki verileri içerir.<br /><br /> Varsayılan olarak, yalnızca kullanılabilir MBayt ve işlemci süresi sayaçları toplanır.|
|Denetleyicisi ve aracıları|Yükleme testlerinin bilgisayarlar hakkında bilgi. Bu, bellek kullanımı, işlemci, fiziksel disk, işlemleri hakkındaki verileri içerir.<br /><br /> Varsayılan olarak yalnızca kullanılabilir MBayt ve işlemci zamanı sayaçları toplanır.|
|İşlem yanıt süresi|Yük testi sırasında gerçekleştirilen işlemler için ortalama yanıt süresi.|

 Hem çalışma zamanında hem de test çalıştıktan sonra grafikte farklı sayaçları görüntüleyebilirsiniz.

> [!NOTE]
> Yalnızca yanıt süresi performans sayaçlarının bir otomatik olarak oluşturulan yanıt süresi grafiğe eklenebilir.

 Sayaç bilgileri hem grafik hem de grafiklerin altındaki göstergede görüntüler. Grafik bir bölüm ayrıca yakınlaştırabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: üzerinde grafiğin bir bölgesine yakınlaştırma yapma](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

## <a name="counters-displayed-in-graphs"></a>Grafiklerde Görüntülenen Sayaçlar

 Grafik görüntüleme *sayaçları*. İkinci ve ortalama test süresi başına testleri gibi bir yük testi sırasında toplanan verileri sayaçları bakın. Sayaçları hakkında daha fazla bilgi için bkz: [sayaç kümelerini ve eşik kurallarını bilgisayarlar için bir yük testinde belirtme](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md).

 Gösterge grafiklerde gösterilen sayaçları için yük testi hakkında yararlı veri birkaç sütunlarını gösterir. Grafikteki herhangi bir veri görüntülemeyi devre dışı bırakmak için gösterge satırda onay kutusunu temizleyin.

 Gösterge şu sütunları içerir:

|Sayaç|Sayaç adı|
|-------------|-----------------------------|
|Örnek|Sayaç örneğinin adı.|
|Kategori|Sayacı kategori adı.|
|Bilgisayar|Sayaç toplanan bilgisayarın adı.|
|Renk|Grafikte çizgi rengi.|
|Aralık|Bu sayaç için grafikte 100 tarafından temsil edilen sayıyı belirtir. Örneğin, 10.000 üst değeri olan bir aralığı için 10.000 grafik üstündeki 100 etiket temsil eder.|
|Min.|Milisaniye cinsinden sayaç için minimum değeri gösterir.|
|Maks.|Sayacın milisaniye cinsinden en büyük değeri gösterir.|
|Ortalama|Milisaniye cinsinden sayacının ortalama değeri gösterir.|
|Son|Milisaniye cinsinden en son örnekleme aralığı sırasında sayaç değerini gösterir.|

## <a name="tasks"></a>Görevler

|Görevler|İlgili Konular|
|-----------|-----------------------|
|**Grafik gösterge kullanarak özelleştirme:** grafik görünümü göstergesi, grafik ile ilişkili her performans sayacı için daha fazla bilgi görüntüler. Gösterge, performans sayaçlarını kaldırmak, performans sayaçlarını grafikte vurgulamak ve çizim seçenekleri özelleştirmek için kullanabilirsiniz.|-   [Yük testlerini çözümlemek için grafik görünümü göstergesini kullanma](../test/use-the-graphs-view-legend-to-analyze-load-tests.md)|
|**Grafiklerde sayaç görüntülemek:** farklı türde veriler bir yük testi sonuçları grafiği sayaçlarını grafiğe sağ koyarak ekleyebilirsiniz.|-   [Nasıl yapılır: grafiklerde sayaç ekleme ve silme](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)|
|**Grafikler üzerinde yakınlaştırma:** bir yük testi tamamladıktan sonra yakınlaştırma ve kaydırma grafiğin bir bölgesine yakınlaştırma çubuklarını kullanabilirsiniz. Yakınlaştırma tarafından ince ayrıntılı olarak yürütülen bir yük testi sırasında oluşturulan veri inceleyebilirsiniz.|-   [Nasıl yapılır: üzerinde grafiğin bir bölgesine yakınlaştırma yapma](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)|
|**Grafikleri döşeme:** yük testi sonuç grafikleri birkaç desenleri hiçbirinde düzenleyebilirsiniz. En fazla dört grafikleri döşeme.||
|**Performans sayacı çizimleri grafiklerde görünümünü değiştirme:** grafiklerde performans sayaçları için çizim satırları seçeneklerini değiştirebilirsiniz. Bu renk ve çizgi stilini içerir. Ayrıca, otomatik olarak veya el ile performans sayacını çizmek için kullanmak istediğiniz aralığı belirtin olup olmadığını belirtebilirsiniz.|-   [Nasıl yapılır: sayaçları grafiğe aktarmak için çizim seçenekleri belirleme](../test/how-to-specify-plot-options-for-graphing-counters.md)|
|**Özel grafikler oluşturma:** yük testi sonuçlarını hakkındaki belirli bilgileri görüntülemek grafikleri tasarlayabilirsiniz. Özel bir grafik grafiği görüntüler yük testi sayaçlarını belirleyerek tasarlayın.|-   [Nasıl yapılır: özel grafikler oluşturma](../test/how-to-create-custom-graphs-in-load-test-results.md)|
|**Grafikte performans sayaçları verileri dışarı aktarma:** grafik verilerini grafikleri görünümündeyken Yük Testi Çözümleyicisi araç çubuğundaki Grafik verilerini dışarı aktar Excel düğmesini kullanarak Microsoft Excel'e dışarı aktarabilirsiniz.||

## <a name="related-tasks"></a>İlgili görevleri

 [Yük testi sonuçlarını ve hatalarını Tablo görünümünde analiz eder.](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)

 [Nasıl yapılır: yük testi sonuçlarını çözümleme için erişim](../test/how-to-access-load-test-results-for-analysis.md)

 [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: grafiklerde sayaç ekleme ve silme](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md)
- [Nasıl yapılır: özel grafikler oluşturma](../test/how-to-create-custom-graphs-in-load-test-results.md)
- [Nasıl yapılır: üzerinde grafiğin bir bölgesine yakınlaştırma yapma](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)