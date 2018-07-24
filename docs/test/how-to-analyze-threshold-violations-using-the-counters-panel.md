---
title: Visual Studio'da yük testleri için Eşik ihlalleri
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, threshold violations
ms.assetid: 0126d7b7-0538-4ea9-9046-6556654b3b9d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: cb64626034c8c9bf03875385a80ebc417bf05dcb
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39204069"
---
# <a name="how-to-analyze-threshold-violations-using-the-counters-panel-in-load-test-analyzer"></a>Nasıl yapılır: Yük Testi Çözümleyicisi'nde Sayaçlar panelini kullanılarak Eşik ihlallerini çözümleme

**Sayaçları** masasıdır grafikler görünümünde ve Tablolar görünümünde görünür **Yük Testi Çözümleyicisi** bir yük testi çalışırken ya da bir yük testi sonucu çözümlerken. Bkz: [analiz yük testi sonuçlarını grafik görünümünde](../test/analyze-load-test-results-in-the-graphs-view.md), [yük testi sonuçlarını ve hatalarını Tablo görünümünde çözümlemek](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) ve [nasıl yapılır: erişim yük testi sonuçlarını analiz](../test/how-to-access-load-test-results-for-analysis.md).

 Eşik ihlalleri, belirli bir performans sayaçları ile ilişkili ve performans sayacı aşıldı veya bir kümesi eşik değerinin altına düştü gösterir. Simgeleri **sayaçları** paneli iletişim Eşik ihlalleri.

 ![Bölmenin bilgisayar düğümünün sayaç](../test/media/ltest_compnode.png)

 Eşik ihlali simgesine başarısız sayaç kök bulunduğu ağaç düğümden yayılır. Simge bir ihlali nedeniyle ağaç genişletilmemiş ağaçta görünür olmayabilir sayaç için kullanıcıyı uyarır. Simge bir örneği şurada görülebilir **bilgisayar düğümü** içinde **sayaçları** önceki çizimdeki paneli.

 Simgesi aşağıdakilerden biri olabilir:

 ![Eşik ihlali yok](../test/media/icon_ltest_1.gif) Eşik ihlali yok.

 ![Kritik Eşik ihlalinin son aralığı](../test/media/icon_ltest_2.gif) Son aralıkta bir Kritik Eşik ihlali oluştu.

 ![Önceki bir aralıkta bir Kritik Eşik ihlali](../test/media/icon_ltest_3.gif) Önceki bir aralıkta bir Kritik Eşik ihlali oluştu.

 ![Uyarı eşiği ihlalinin son aralığı](../test/media/icon_ltest_4.gif) Uyarı eşiği ihlalinin son aralıkta oluştu.

 ![Uyarı eşiği ihlalinin önceki aralığı](../test/media/icon_ltest_5.gif) Önceki bir aralıkta bir uyarı eşik ihlali oluştu.

## <a name="to-analyze-threshold-violations-in-the-counters-panel"></a>Sayaçlar paneli Eşik ihlallerini analiz etmek için

1.  Bir yük testi tamamlandıktan sonra veya Yük Testi Çözümleyicisi'nin araç çubuğunda, bir test sonucunu seçin **grafikleri** veya **tabloları**.

     **Sayaçları** grafikler görünümü veya Tablo görünümü panelini görüntüler.

2.  Varsa **sayaçları** paneli görünür değilse, seçin **Sayaçlar panelini Göster** araç.

     Eşik ihlallerini içeren tüm düğümleri yukarıda listelenen simgelerden birini içerir.

3.  Bir eşiği simgesi gibi içeren düğümünü **bilgisayarlar** "Bilgisayarlar düğümü eşik ihlali ile Sayaçlar panelini." başlıklı önceki resimde gösterildiği gibi düğüm Düğüm eşik ihlali olan performans sayacı ulaşana kadar genişletmeye devam edin. Örneğin, çizim başarısız örneğini gösterir **Microsoft sanal makine başarısız Bus ağ bağdaştırıcısı**.

4.  (İsteğe bağlı) Eşik ihlali olan performans sayacı sağ tıklatın ve aşağıdaki seçeneklerden birini seçin:

    -   **Grafik üzerinde sayaç Göster**: grafikler Görünümü'nde performans sayacı eklenir ve seçili grafik üzerinde vurgulanır. Daha fazla bilgi için [nasıl yapılır: grafiklerde sayaç ekleme ve silme](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md).

        > [!NOTE]
        > Eşik ihlali simgelerinin de grafik görünümünde grafikteki gösterilebilir. Eşik ihlali gerçekleştiği veri noktasının yanındaki grafik üzerindeki eşik simgesi görünür. Bunu yapmak için **Göstergeyi Göster** seçin ve araç çubuğu üzerindeki açılan **Eşik İhlallerini Grafikte Göster**.

    -   **Gösterge üzerinde sayaç Göster**: Açıklama bölümünde performans sayacı eklenir ve seçilir. Daha fazla bilgi için [yük testlerini çözümlemek için grafik görünümü göstergesini kullanma](../test/use-the-graphs-view-legend-to-analyze-load-tests.md).

    -   **Graf ekleme**:

    1.  **Grafik adı girin** iletişim kutusu görüntülenir.

    2.  İçinde **grafik adı** metin kutusuna yeni grafik için bir ad yazın ve ardından **Tamam**.

    3.  (İsteğe bağlı) Performans sayacı tekrar sağ tıklayıp **grafik üzerinde sayaç Göster**.

         Daha fazla bilgi için [nasıl yapılır: özel grafikler oluşturma](../test/how-to-create-custom-graphs-in-load-test-results.md).

5.  (İsteğe bağlı) Tamamlanan yük testi sonucu eşik ihlali analiz Grafik görünümünde yakınlaştırma özelliklerini kullanmayı düşünün. Daha fazla bilgi için [nasıl yapılır: grafiğin bir bölgesine yakınlaştırmak](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

    > [!TIP]
    > Yük testi çalıştırması sırasında herhangi bir eşik ihlali algılanırsa, "ihlal sayısı dahil olmak üzere Eşik ihlallerini" başlıklı bir bağlantı mevcut **Yük Testi Çözümleyicisi** durum çubuğu. Tüm Eşik ihlallerini görüntülemek için bağlantıyı seçebilirsiniz **eşikleri** tablolar görünümünün tablo.

## <a name="see-also"></a>Ayrıca bkz.

- [Grafikler görünümünde ve Tablolar görünümünde Sayaçlar panelini kullanma](../test/counters-panel-in-load-test-analyzer.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)