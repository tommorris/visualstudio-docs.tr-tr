---
title: "Visual Studio yük testlerini çözümlemek için gösterge görüntüleme grafikleri kullanma | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Load Test Analyzer, graphs view legend
- load tests, graphs view legend
ms.assetid: 0f6ba8e4-1343-419c-8a9f-240cf50efed7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 967cc1c854689ba034077d25f61cea74d1f082a2
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="using-the-graphs-view-legend-to-analyze-load-tests"></a>Yük Testlerini Çözümlemek için Grafik Görünümü Göstergesini Kullanma

Yük Testi Çözümleyicisinin Grafik görünümünde seçili grafik ile ilişkili her performans sayacı bilgileri görüntüleyen bir gösterge paneli içerir.

![Graphs view legend](../test/media/load_viewlegend.png "Load_ViewLegend")

Aşağıdaki bilgiler, gösterge içinde yer alır:

-   **Grafikte Göster:** belirtmek için onay kutularını kullanın olup olmadığını belirli bir sayaç çizgi gibi **kullanıcı yükü** veya **Hatası/sn**, grafikte çizilir. Çizgi grafikte çizilmesini istiyorsanız onay kutusunu seçin. Çizim satırını Grafikten kaldırmak için bir onay kutusunu temizleyin. Bir çizim çizgisi kaldırıldığında, sayacın istatistikleri göstergede görüntülenmeye devam eder.

-   **Aralık:** bu sütun performans sayacının y ekseni aralığını görüntüler. Varsayılan olarak, bu değeri otomatik olarak örnek veri değişikliklerinin aralığı olarak ayarlar. Otomatik olarak ayarlanan bir aralık her zaman en büyük değerden daha büyük 10 sonraki gücünü olur; Bu olumsuz katları içerir. Bir grafik çeşitli sayaçları, her biri farklı bir aralık içerebilir. Bu nedenle, y ekseni herhangi belirli aralığıyla etiketli değil, ancak bunun yerine her sayaç için toplam aralığın bir yüzdesini temsil eden 0-100 değerleri ile etiketlenir. Örneğin, 1000 aralığı olan bir sayaç için bir veri noktasının y ekseni üzerinde 60 sayaç için 600 değerine karşılık gelir.

    > [!NOTE]
    > Belirli bir değere aralığı kilitleyerek otomatik aralık değeri ayarlamayı kapatabilirsiniz kapatabilirsiniz. Aralık kilitlendiğinde aralığı aşan tüm değerler grafiğin üst kısmında belirtilen en fazla değer olarak görüntülenir. Kullanım **Çizim Seçenekleri** belirli bir değer aralığı kilitlemek için iletişim kutusu. Daha fazla bilgi için bkz: [nasıl yapılır: Grafikleme sayaçları için çizim seçenekleri belirleme](../test/how-to-specify-plot-options-for-graphing-counters.md).

-   **Sayaç:** adlı dört sütun **sayaç**, **örneği**, **kategori**, ve **bilgisayar** birlikte benzersiz olarak Performans sayacı tanımlayın.

-   **Renk:** **renk** sütun performans sayacı için çizilen çizgi rengi ve çizgi stilini gösterir. Kullanım **Çizim Seçenekleri** iletişim kutusu, bir performans sayacının grafikte rengini veya çizgi stilini değiştirin. **Çizim Seçenekleri** iletişim kutusu gösterge kısayol menüsünden kullanılabilir. Daha fazla bilgi için bkz: [nasıl yapılır: Grafikleme sayaçları için çizim seçenekleri belirleme](../test/how-to-specify-plot-options-for-graphing-counters.md).

-   **İstatistikleri:** **Min**, **Max**, **Avg** ve **son** sütunlar performans istatistiklerini gösterir sayacı. Bu değerler grafiğin görünür bölgesi üzerinde görüntülenen verilere karşılık gelir. Örneğin, bir çalışma bölgesine yakınlaştırma, gösterge istatistikleri yalnızca yakınlaştırılmış alan için değerleri yansıtır. "Son" sütunu üzerinde en son tamamlanan örnekleme aralığı performans sayacı değeri.

    > [!NOTE]
    > Yük testi çalışırken son sütun yalnızca Yük Testi Çözümleyicisi'nin göstergesinde görüntüler.

     Daha fazla bilgi için bkz: [nasıl yapılır: üzerinde grafiğin bir bölgesine yakınlaştırma yapma](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

Öğenin göstergede seçerek aşağıdakileri yapar:

-   Hem göstergeyi hem de grafiği kaldırılacak öğe sağlar. Ya da öğeyi sağ tıklatın ve seçin **silmek**, veya basın **silmek** anahtarı.

-   Çizilen çizgi grafikte vurgular.

-   Seçilen öğe için verileri görüntülemek veri kılavuzu neden olur.

-   Size erişim sağlar **Çizim Seçenekleri** sayaç için iletişim kutusu.

> [!TIP]
> Kullanabileceğiniz **Grafik Seçenekleri açılan** Yük Testi Çözümleyicisinin araç çubuğu ve Seç düğmesini **Göstergeyi Göster** göstermek veya gizlemek için **gösterge** ile ilişkili paneli Grafik görünümü.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: sayaçları grafiğe aktarmak için çizim seçenekleri belirleme](../test/how-to-specify-plot-options-for-graphing-counters.md)
- [Nasıl yapılır: üzerinde grafiğin bir bölgesine yakınlaştırma yapma](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)
- [Grafik görünümünde yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-in-the-graphs-view.md)