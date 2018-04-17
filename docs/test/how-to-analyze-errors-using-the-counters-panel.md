---
title: Yük testi Visual Studio'da Sayaçlar panelini kullanarak hataları çözümleme | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Load Test Analyzer, counters panel
ms.assetid: 981b4f1e-505a-4078-a06d-58ae17d996b4
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 2705120f5cf0e13e94369140c256bd3c7ae1466b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-analyze-errors-using-the-counters-panel"></a>Nasıl yapılır: Sayaçlar Panelini Kullanarak Hataları Çözümleme

Bir yük testi çalışırken ya da bir yük testi sonuç çözümlerken Sayaçlar panelini grafikler görünümünde ve Tablolar görünümünde Yük Testi Çözümleyicisi görülebilir. Daha fazla bilgi için bkz: [Grafik görünümünde yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-in-the-graphs-view.md), [yük testi sonuçlarını çözümleme ve hataları Tablo görünümünde](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) ve [nasıl yapılır: erişim yük testi sonuçlarını çözümlemeiçin](../test/how-to-access-load-test-results-for-analysis.md).

 **Hataları** Sayaçlar panelini düğümünde yük testi sırasında algılanan tüm hataları içerir. Hata düğümü farklı tür hatalara özgü çeşitli alt kategori hata düğümlerini içerir. Örneğin, **özel durumları** ve **HTTP hataları**.

 ![Sayaç bölmenin hata düğümü](../test/media/ltest_errornode.png "LTest_ErrorNode")

## <a name="to-analyze-errors-in-the-counters-panel"></a>Sayaçlar panelini hatalarını çözümlemek için

1.  Bir yük testi tamamlandıktan sonra ya da Yük Testi Çözümleyicisi'nin araç çubuğunda, bir test sonucu yükledikten sonra seçin **grafikleri** veya **tabloları**.

     **Sayaçları** paneli grafikler görünümünde veya tabloları görünüm olarak görüntüler.

2.  Sayaçlar panelini görünür durumda değilse, seçin **Sayaçlar panelini Göster** araç çubuğunda.

3.  Genişletme **hataları** ve bir hata kategorisi veya analiz etmek istediğiniz bir hata alt kategori seçin.

4.  Hata sağ tıklayın ve aşağıdaki seçeneklerden birini seçin:

    -   **Grafikte sayaç Göster**: Grafik Görünümü'nde hata eklenir ve seçili grafik üzerinde vurgulanır. Daha fazla bilgi için bkz: [nasıl yapılır: grafiklerde sayaç ekleme ve silme](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md).

    -   **Sayaç göstergede Göster**: hata eklenir ve göstergede seçilir. Daha fazla bilgi için bkz: [yük testlerini çözümlemek için grafik görünümü göstergesini kullanma](../test/use-the-graphs-view-legend-to-analyze-load-tests.md).

    -   **Grafik ekleyin**:

    1.  **Grafik adı girin** iletişim kutusu görüntülenir.

    2.  İçinde **grafik adı** metin kutusunda, yeni bir grafik için bir ad yazın ve ardından **Tamam**.

    3.  (İsteğe bağlı) Hata tekrar sağ tıklayın ve seçin **grafikte sayaç Göster**.

         Daha fazla bilgi için bkz: [nasıl yapılır: özel grafikler oluşturma](../test/how-to-create-custom-graphs-in-load-test-results.md).

5.  (İsteğe bağlı) Tamamlanan yük testi sonuç hata analiz ediyorsanız Grafiklerde yakınlaştırma özelliklerini kullanmayı düşünün. Daha fazla bilgi için bkz: [nasıl yapılır: üzerinde grafiğin bir bölgesine yakınlaştırma yapma](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

    > [!TIP]
    > Yük Testi Çözümleyicisi durum çubuğunda bulunması sayı dahil hata bulundu, yük testi sırasında başlıklı bir bağlantı hatalarını algılanırsa. Tüm hataları görüntülemek için bağlantıyı seçebilirsiniz **hataları** tablolar görünümünün tablo.

## <a name="see-also"></a>Ayrıca bkz.

- [Grafikler görünümünde ve Tablolar görünümünde Sayaçlar panelini kullanma](../test/counters-panel-in-load-test-analyzer.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)