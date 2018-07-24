---
title: Yük testi Visual Studio'da Sayaçlar panelini kullanarak hataları çözümleme
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Load Test Analyzer, counters panel
ms.assetid: 981b4f1e-505a-4078-a06d-58ae17d996b4
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: e7ccd21e5432003de7ec3b03bf94716802846bd4
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39204342"
---
# <a name="how-to-analyze-errors-using-the-counters-panel"></a>Nasıl yapılır: Sayaçlar panelini kullanarak hataları çözümleme

**Sayaçları** masasıdır grafikler görünümünde ve Tablolar görünümünde görünür **Yük Testi Çözümleyicisi** bir yük testi çalışırken ya da bir yük testi sonucu çözümlerken. Daha fazla bilgi için [Çözümle yük testi sonuçlarını grafik görünümünde](../test/analyze-load-test-results-in-the-graphs-view.md), [yük testi sonuçlarını ve hatalarını Tablo görünümünde çözümlemek](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) ve [nasıl yapılır: erişim yük testi sonuçlarını analiz](../test/how-to-access-load-test-results-for-analysis.md).

 **Hataları** düğümünde **sayaçları** paneli Yük testi sırasında algılanan tüm hataları içerir. **Hataları** düğümü çeşitli hatalar özgü birkaç alt kategorisi hata düğümü içerir. Örneğin, **özel durumları** ve **HTTP hataları**.

 ![Bölmenin hata düğümü sayaç](../test/media/ltest_errornode.png)

## <a name="to-analyze-errors-in-the-counters-panel"></a>Sayaçlar paneli hatalarını çözümlemek için

1.  Bir yük testi tamamlandıktan sonra veya Yük Testi Çözümleyicisi'nin araç çubuğunda, bir test sonucunu seçin **grafikleri** veya **tabloları**.

     **Sayaçları** grafikler görünümü veya Tablo görünümü panelini görüntüler.

2.  Varsa **sayaçları** paneli görünür değilse, seçin **Sayaçlar panelini Göster** araç.

3.  Genişletin **hataları** ve hata kategorisi veya analiz etmek istediğiniz bir hata alt kategorisi seçin.

4.  Hataya sağ tıklayın ve aşağıdaki seçeneklerden birini seçin:

    -   **Grafik üzerinde sayaç Göster**: grafikler Görünümü'nde hata eklenir ve seçili grafik üzerinde vurgulanır. Daha fazla bilgi için [nasıl yapılır: grafiklerde sayaç ekleme ve silme](../test/how-to-add-and-delete-counters-on-graphs-in-load-test-results.md).

    -   **Gösterge üzerinde sayaç Göster**: hata eklenir ve göstergede seçilir. Daha fazla bilgi için [yük testlerini çözümlemek için grafik görünümü göstergesini kullanma](../test/use-the-graphs-view-legend-to-analyze-load-tests.md).

    -   **Graf ekleme**:

    1.  **Grafik adı girin** iletişim kutusu görüntülenir.

    2.  İçinde **grafik adı** metin kutusuna yeni grafik için bir ad yazın ve ardından **Tamam**.

    3.  (İsteğe bağlı) Hata tekrar sağ tıklayıp **grafik üzerinde sayaç Göster**.

         Daha fazla bilgi için [nasıl yapılır: özel grafikler oluşturma](../test/how-to-create-custom-graphs-in-load-test-results.md).

5.  (İsteğe bağlı) Tamamlanan yük testi sonucu bir hata analiz Grafiklerde yakınlaştırma özelliklerini kullanmayı düşünün. Daha fazla bilgi için [nasıl yapılır: grafiğin bir bölgesine yakınlaştırmak](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

    > [!TIP]
    > Yük testi çalıştırması sırasında herhangi bir hata algılandı, hataları bulunan sayı başlıklı bir bağlantı mevcut **Yük Testi Çözümleyicisi** durum çubuğu. Tüm hataları görüntülemek için bağlantıyı seçebilirsiniz **hataları** tablolar görünümünün tablo.

## <a name="see-also"></a>Ayrıca bkz.

- [Grafikler görünümünde ve Tablolar görünümünde Sayaçlar panelini kullanma](../test/counters-panel-in-load-test-analyzer.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)