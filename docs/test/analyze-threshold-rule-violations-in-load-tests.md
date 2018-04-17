---
title: Visual Studio Yük testlerindeki eşik kuralı ihlallerini çözümleme | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.monitor.threshholdresult
helpviewer_keywords:
- load tests, thresholds
- threshold violations
- threshold counts
- load tests, threshold violations
- load test results, analyzing threshold violations
- thresholds in load tests
ms.assetid: 969ed346-cf2e-4d48-82b3-edb3e075e1c0
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 42463515a8c3da9661f22d1a39c8dd8346c63aea
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="analyzing-threshold-rule-violations-in-load-tests-using-the-load-test-analyzer"></a>Yük Testi Çözümleyicisini Kullanarak Yük Testlerindeki Eşik Kuralı İhlallerini Çözümleme

Eşik kuralları belirli bir performans sayaçları ile ilişkili olan ve bir performans sayacı aşıldı veya ayarlanan bir değeri altına düştü ihlalleri gösterir. Bir yük testi çalıştırdığınızda, önceden ayarlanmış eşik kuralları için oluşan ihlalleri çözümleyebilirsiniz.

Herhangi bir ihlal oluştuysa, bir **Eşik ihlallerini** köprü Yük Testi Çözümleyicisinin durum çubuğunda görünür ve oluşan ihlallerinin sayısını belirtir. Eşik ihlalleri tablosunu görüntülemek için köprü seçin. Eşik ihlalleri de görüntüleyebilirsiniz **sayaçları** penceresinde ve grafik.

## <a name="view-threshold-violations-in-the-table"></a>Tablodaki görünümü Eşik ihlalleri

 Eşik ihlalleri tablosu ilk 1.000 ihlali görüntüler. Aşağıdaki tablo şu sütunları içerir:

|Sütun|Açıklama|Varsayılan olarak görünür|
|------------|-----------------|------------------------|
|Zaman|İhlalin gerçekleştiği süre boyunca yük test edin.|Evet|
|Bilgisayar|Test ihlalin oluştuğu bilgisayarın adı. **Not:** donanımlarını yük testlerini çalıştırdığınızda, bu önemlidir.|Evet|
|Kategori|İhlalin oluştuğu performans sayacı kategorisi.|Evet|
|Sayaç|İhlalin oluştuğu performans sayacının adı.|Evet|
|Örnek|Performans sayacı örneği üzerinde ihlali oluştu.|Evet|
|İleti|Eşik ihlali açıklayan ileti. Örneğin, **Kritik Eşik değeri 0 5 değerini aşıyor**.|Evet|

> [!NOTE]
> Tablo, sütun başlıklarının seçerek sıralayabilirsiniz.

 Daha fazla bilgi için bkz: [yük testi sonuçlarını çözümleme ve hataları Tablo görünümünde](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

## <a name="view-threshold-violations-in-the-counters-panel"></a>Sayaç panelinde görünüm Eşik ihlalleri

 Eşik ihlallerini görüntüleyebilirsiniz **sayaçları** panelinde yük testi için performans sayaçları listeler ağacı. Simgeleri **sayaçları** Masası Eşik ihlallerini iletişim. Simge aşağıdakilerden biri olacaktır:

 Simge aşağıdakilerden biri olacaktır:

 ![Eşik ihlali yok](../test/media/icon_ltest_1.gif "Icon_LTest_1") eşik ihlali yok.

 ![Kritik Eşik ihlalinin son aralıkta](../test/media/icon_ltest_2.gif "Icon_LTest_2") son aralıkta bir Kritik Eşik ihlali oluştu.

 ![Kritik Eşik ihlalinin önceki bir aralıkta](../test/media/icon_ltest_3.gif "Icon_LTest_3") önceki aralıkta bir Kritik Eşik ihlali oluştu.

 ![Uyarı eşiği ihlalinin son aralıkta](../test/media/icon_ltest_4.gif "Icon_LTest_4") son aralıkta uyarı eşiği ihlali oluştu.

 ![Uyarı eşiği ihlalinin önceki bir aralıkta](../test/media/icon_ltest_5.gif "Icon_LTest_5") önceki bir aralıkta uyarı eşiği ihlali oluştu.

 İsteğe bağlı olarak, Eşik İhlallerini Grafikte da gösterilebilir. Grafikte eşik ihlalinin oluştuğu veri noktasının yanındaki eşik simgesi görünür.

 Sayaç ağacında belirli sayaç düğümünden kök düğümü kadar eşik ihlali simgesi yayılır. Bu bir ağaç genişletilmemiş çünkü ağacında görünür olmayabilir sayacı ihlali uyarır.

 Daha fazla bilgi için bkz: [grafikler görünümünde ve Tablolar görünümünde Sayaçlar panelini kullanarak](../test/counters-panel-in-load-test-analyzer.md).

## <a name="view-threshold-violations-on-the-graph"></a>Görünüm Eşik İhlallerini Grafikte

 Grafikte Eşik ihlallerini görüntüleyebilirsiniz. Benzer şekilde **sayaçları** paneli, simgeler Eşik İhlallerini Grafikte iletişim kurar. Grafikte eşik ihlalinin oluştuğu veri noktasının yanındaki simgeleri görüntülenir. Grafikte olmayan bir sayaçta eşik ihlali meydana gelirse, bunu grafiğe ondan sürükleyerek ekleyebilirsiniz **sayaçları** grafik paneline.

 Daha fazla bilgi için bkz: [Grafik görünümünde yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-in-the-graphs-view.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testindeki bilgisayarlar için sayaç kümelerini ve eşik kurallarını belirtme](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Yük testi sonuçlarını ve hatalarını Tablo görünümünde analiz eder.](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)