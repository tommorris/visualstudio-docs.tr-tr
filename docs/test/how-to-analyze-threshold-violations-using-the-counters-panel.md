---
title: Visual Studio Yük testleri için Eşik ihlalleri
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
ms.openlocfilehash: fdb54122344ce91fe873d854768d0890a83f198a
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751812"
---
# <a name="how-to-analyze-threshold-violations-using-the-counters-panel-in-load-test-analyzer"></a>Nasıl yapılır: Yük Testi Düzenleyicisi'nde Sayaçlar Panelini Kullanılarak Eşik İhlallerini Çözümleme

Bir yük testi çalışırken ya da bir yük testi sonuç çözümlerken Sayaçlar panelini grafikler görünümünde ve Tablolar görünümünde Yük Testi Çözümleyicisi görülebilir. Bkz: [Grafik görünümünde yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-in-the-graphs-view.md), [yük testi sonuçlarını ve hatalarını Tablo görünümünde çözümlemek](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) ve [nasıl yapılır: yük testi sonuçlarını çözümleme için erişim](../test/how-to-access-load-test-results-for-analysis.md).

 Eşik ihlallerini belirli performans sayaçları ile ilişkili ve performans sayacı aşıldı veya ayarlanan bir eşik değeri altına düştü gösterir. Sayaçlar panelini simgeleri Eşik ihlallerini iletişim kurar.

 ![Bölmenin bilgisayar düğümünün sayacı](../test/media/ltest_compnode.png)

 Eşik ihlali simgesi başarısız sayaç kök bulunduğu ağaç düğümünden yayılır. Simge bir ağaç genişletilmemiş çünkü ağacında görünür olmayabilir sayacı ihlali kullanıcıya uyarır. Simge bir örneği görülebilir **bilgisayar düğümü** önceki çizimde Sayaç panelinde.

 Simge aşağıdakilerden biri olacaktır:

 ![Eşik ihlali yok](../test/media/icon_ltest_1.gif) Eşik ihlali yok.

 ![Kritik Eşik ihlalinin son aralığı](../test/media/icon_ltest_2.gif) Son aralıkta bir Kritik Eşik ihlali oluştu.

 ![Kritik Eşik ihlalinin önceki aralığı](../test/media/icon_ltest_3.gif) Önceki bir aralıkta bir Kritik Eşik ihlali oluştu.

 ![Uyarı eşiği ihlalinin son aralığı](../test/media/icon_ltest_4.gif) Uyarı eşiği ihlalinin son aralıkta oluştu.

 ![Uyarı eşiği ihlalinin önceki aralığı](../test/media/icon_ltest_5.gif) Uyarı eşiği ihlalinin önceki aralıkta oluştu.

## <a name="to-analyze-threshold-violations-in-the-counters-panel"></a>Sayaç panelinde Eşik ihlallerini analiz etmek için

1.  Bir yük testi tamamlandıktan sonra ya da Yük Testi Çözümleyicisi'nin araç çubuğunda, bir test sonucu yükledikten sonra seçin **grafikleri** veya **tabloları**.

     Grafik görünümü ya da Tablolar görünümünde Sayaçlar panelini görüntüler.

2.  Sayaçlar panelini görünür durumda değilse, seçin **Sayaçlar panelini Göster** araç çubuğunda.

     Eşik ihlalleri içeren herhangi bir düğüme yukarıda listelenen simgelerinden birini içerir.

3.  Bir eşik simgesi gibi içeren düğümünü **bilgisayarlar** "Bilgisayarlar düğümü eşik ihlali ile Sayaçlar panelini." başlıklı önceki resimde gösterildiği gibi düğümü Eşik ihlali olan performans sayacı ulaşana kadar düğümü genişletmek devam edin. Örneğin, başarısız bir örneğine gösterimde **Microsoft sanal makine başarısız veri yolu ağ bağdaştırıcısı**.

4.  (İsteğe bağlı) Eşik ihlali olan performans sayacı sağ tıklatın ve aşağıdaki seçeneklerden birini seçin:

    -   **Grafikte sayaç Göster**: grafikler görünümünde performans sayacı eklenir ve seçili grafik üzerinde vurgulanır. Daha fazla bilgi için bkz: [nasıl yapılır: grafiklerde sayaç ekleme ve silme](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md).

        > [!NOTE]
        > Eşik ihlali simgeleri Grafik görünümünde grafikte da gösterilebilir. Grafikte eşik ihlalinin oluştuğu veri noktasının yanındaki eşik simgesi görünür. Bunu yapmak için seçin **Gösterge Göster** seçin ve araç çubuğu açılır **Göster Eşik İhlallerini Grafikte**.

    -   **Sayaç göstergede Göster**: göstergede performans sayacı eklenir ve seçilir. Daha fazla bilgi için bkz: [yük testlerini çözümlemek için grafik görünümü göstergesini kullanma](../test/use-the-graphs-view-legend-to-analyze-load-tests.md).

    -   **Grafik ekleyin**:

    1.  **Grafik adı girin** iletişim kutusu görüntülenir.

    2.  İçinde **grafik adı** metin kutusunda, yeni bir grafik için bir ad yazın ve ardından **Tamam**.

    3.  (İsteğe bağlı) Performans sayacı tekrar sağ tıklayın ve seçin **grafikte sayaç Göster**.

         Daha fazla bilgi için bkz: [nasıl yapılır: özel grafikler oluşturma](../test/how-to-create-custom-graphs-in-load-test-results.md).

5.  (İsteğe bağlı) Tamamlanan yük testi sonuç eşik ihlali çözümleme, grafikler görünümünde yakınlaştırma özelliklerini kullanmayı göz önünde bulundurun. Daha fazla bilgi için bkz: [nasıl yapılır: üzerinde grafiğin bir bölgesine yakınlaştırma yapma](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

    > [!TIP]
    > Yük testi sırasında herhangi bir eşik ihlali algılanırsa, "Eşik ihlallerini ihlal sayısı dahil olmak üzere," başlıklı bir bağlantı Yük Testi Çözümleyicisi durum çubuğunda mevcut olacaktır. Eşik ihlalleri görüntülemek için bağlantıyı seçebilirsiniz **eşikleri** tablolar görünümünün tablo.

## <a name="see-also"></a>Ayrıca bkz.

- [Grafikler görünümünde ve Tablolar görünümünde Sayaçlar panelini kullanma](../test/counters-panel-in-load-test-analyzer.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)