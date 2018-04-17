---
title: Microsoft Word'ü kullanarak bir Visual Studio Yük testi başarım raporunu oluşturmak | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, reporting
- load tests, creating Word reports
ms.assetid: 3b864c75-2699-48c1-a2b4-9651f108c267
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 6b7c48d46cfb795c4eb5f61cc970676816d568a0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-manually-create-a-load-test-performance-report-using-microsoft-word"></a>Nasıl yapılır: Microsoft Word Kullanılarak bir Yük Testi Başarım Raporunu El ile Oluşturma

Grafik görünümü ve kopyalayıp yapıştırarak Yük Test sonuçları Özet görünümü verilerini Microsoft Word yük testi raporları el ile oluşturabilirsiniz. Özet görünümü sunulur ve grafikler görünümünde veriler kopyalandığında HTML biçiminde uygulanır.

> [!TIP]
> Microsoft Word için Ayrıntılar görünümden ekran görüntüleri ve Tablolar görünümünde düz metni kopyalayın, ancak HTML biçiminde uygulanmaz ve biçimlendirme ve düzenleme ek gerektirir.

> [!TIP]
> Düzenlenmiş Microsoft Excel raporları otomatik olarak de oluşturabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: oluşturmak yük testi performans raporları kullanarak Microsoft Excel](../test/how-to-create-load-test-performance-reports-using-microsoft-excel.md).

## <a name="copy-summary-view-data"></a>Özet görünümü veri kopyalama

1.  Yük testi sonuçlarında Özet görünümü şu anda görüntülenmiyorsa tıklatın **Özet** araç.

2.  Özet görünümü sağ tıklayın ve **Tümünü Seç**.

3.  Özet görünümü sağ tıklayın ve **kopya**. Bu panoya HTML biçiminde Özet görünümü verileri işler.

4.  Microsoft Word'de Özet görünümü verileri istenilen yere yapıştırın.

5.  Şimdi değiştirmek, biçimlendirme ve raporlama ihtiyaçlarınızı karşılamak için kopyalanan içeriğin yönlerini silin.

## <a name="copy-graph-view-data"></a>Grafik görünümü verilerini kopyalama

1.  Yük testi sonuçlarında grafikleri görünüm şu anda görüntülenmiyorsa seçin **grafikleri** araç.

2.  (İsteğe bağlı) Aşağıdaki çizimde gösterildiği gibi Microsoft Word belgesine kopyalamak istediğiniz belirli grafikte yakınlaştırma. Daha fazla bilgi için bkz: [nasıl yapılır: üzerinde grafiğin bir bölgesine yakınlaştırma yapma](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

     ![Grafik görünümü yakınlaştırma denetimi](../test/media/ltest_zoomcontrol.png "LTest_ZoomControl")

3.  Microsoft Word belgeniz kopyalamak istediğiniz grafik üzerinde sağ tıklatıp **kopya**.

4.  Microsoft Word'de grafik ve istenen konumu ilişkili tablo verileri yapıştırın.

    > [!WARNING]
    > Uzak Masaüstü üzerinden grafiği kopyalayın ve grafik ile ilişkili tablo bilgileri kopyalanmadığından başka bir makineye yapıştırın ve grafik görüntüsü. Graf görüntüsü, kopyalandığı makinedeki geçici dizinde depolanır ve ikinci makine o dizine başvuramaz.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçlarını raporlama Test karşılaştırmaları veya eğilim analizleri için](../test/compare-load-test-results.md)
- [Nasıl yapılır: Microsoft Excel kullanarak yük testi başarım raporları oluşturma](../test/how-to-create-load-test-performance-reports-using-microsoft-excel.md)