---
title: Yük testi Visual Studio'da sonuçları özeti genel bakış
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.monitor.summary.view
helpviewer_keywords:
- load test results, summary
- load tests, summary in analyzer
- load tests, results summary
- Load Test Viewer, summary
- load tests, summary in Load Test Viewer
ms.assetid: 326b6c3c-5378-452b-8ca3-ba5a06ab3d41
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 989ebc629e79194fb6cd4c900b032cb93a090977
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="load-test-results-summary-overview"></a>Yük Testi Sonuçları Özetine Genel Bakış

Bir yük testi çalıştırdıktan sonra sonuçları hızla anlamak için yük testi özetini görüntüleyebilirsiniz. Yük Testi Özeti anahtar sonuçları CD ve kolay okunur biçimde sağlar. Yük Testi Özeti ayrıca yazdırabilirsiniz. Bu proje katılımcılarına sonuçları iletişim kurarken kullanmak uygun sağlar. Daha önce çalıştırılan bir yük testine bir yük testi sonuç açtığınızda Yük Testi Özeti Ayrıca varsayılan görünümü şu şekildedir. Daha fazla bilgi için bkz: [nasıl yapılır: erişim yük testi sonuçlarını çözümleme için](../test/how-to-access-load-test-results-for-analysis.md).

 ![Özet görünümü](../test/media/ltest_summaryview.png "LTest_SummaryView")

## <a name="the-load-test-summary"></a>Yük Testi Özeti

Yük Testi Özeti bölümlere ayrılmıştır. Başlangıç bölümleri Özet üstünde görünür ve her zaman görünür. Yük testi özetini görüntülediğinizde, aşağıdaki ilk öğeler şunlardır:

- Test çalışması bilgileri

- Genel sonuçları

- Anahtar istatistiği: en yavaş 5 sayfa

- Anahtar istatistiği: en yavaş 5 test

- Anahtar istatistik: Top 5 en yavaş SQL işlemleri

    > [!NOTE]
    > Yalnızca yük testinde SQL izleme etkinleştirilirse SQL işlemleri bölümünde görüntülenir.

Kapanış bölümleri Özet sonunda görünür ve alanından tasarruf etmek için daraltılmış. Aşağıdaki öğeler Yük Testi Özeti sonunda görünür:

- Test Sonuçları

- Sonuçlar sayfası

- İşlem sonuçları

- Test kaynakları altında sistem

- Denetleyici ve aracı kaynakları

- Hatalar

## <a name="test-run-information"></a>Test çalışması bilgileri

Bilgi bölümü testi test, başlangıç ve bitiş zamanları ve testi çalıştıran Denetleyici adı dahil olmak üzere çalışma hakkında genel bilgiler içerir. Bu bölümde Ayrıca isteğe bağlı bir yük testi çalıştırdığınızda eklediğiniz Çalıştır açıklaması içerir.

## <a name="overall-results"></a>Genel sonuçları

Genel sonuçlar bölümü Özet ikinci, başarısız isteklerin toplam sayısı, ortalama yanıt süresi ve ortalama sayfa saat başına istek sayısı dahil olmak üzere test sonuçlarını içerir.

## <a name="key-statistic-top-5-slowest-pages"></a>Anahtar istatistiği: en yavaş 5 sayfa

En yavaş sayfalar bölümü ilk 5 en yavaş yük testinde içerir. URL ve ortalama sayfa yükleme süresi için her bir sayfa görüntülenir. Sayfalar, azalan sırada listelenir. Açmak için bir sayfanın URL'sini seçebilirsiniz **sayfaları** tablo ve daha fazla ayrıntı için bu sayfayı inceleyin. Daha fazla bilgi için bkz: [nasıl yapılır: Görünümü Web sayfası yanıt](../test/how-to-view-web-page-response-time-in-a-load-test.md).

Yüzdebirlik değeri **% 95 sayfa süresi (sn)** sayfaların % 95'inin bu kez saniye cinsinden tamamlandığı rapor.

## <a name="key-statistic-top-5-slowest-tests"></a>Anahtar istatistiği: en yavaş 5 test

En yavaş testler bölümü ilk 5 en yavaş yük testinde içerir. Test ve ortalama test süresi adını her test için görüntülenir. Testler, azalan sırada listelenir. Açmak için bir test adını seçebilirsiniz **testleri** tablo ve test için daha fazla ayrıntı için inceleyin. Daha fazla bilgi için bkz: [yük testi sonuçlarını çözümleme ve hataları Tablo görünümünde](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

Yüzdebirlik değeri **% 95 Test Süresi (sn)** testleri % 95'inin bu kez saniye cinsinden tamamlandığı rapor.

## <a name="key-statistic-top-5-slowest-sql-operations"></a>Anahtar istatistik: Top 5 en yavaş SQL işlemleri

Yük testi SQL izleme etkinleştirilirse, en yavaş sorgular üst 5 en yavaş yük testinde içerir. İşlem ve süreyi adını her test için görüntülenir. Süre mikrosaniye SQL Server 2005 veya milisaniye (SQL Server 2000 ve öncesi) görüntülenir. Testler, süreye göre azalan sırada listelenir. Açmak için bir işlem adını seçebilirsiniz **SQL İzleme** tablo ve daha fazla ayrıntı için bu işlemi inceleyin. Daha fazla bilgi için bkz: [SQL izleme veri tablosu](../test/analyze-load-test-results-and-errors-in-the-tables-view.md#the-sql-trace-data-table).

## <a name="test-results"></a>Test Sonuçları

Test sonuçları bölümü tüm testleri ve yük testi senaryolarında listesini içerir. Test adını senaryo, kaç kez başarısız, çalıştırdığınız sayısı ve ortalama test süresi görüntülenir. Açmak için bir test adını seçebilirsiniz **testleri** tablo ve test için daha fazla ayrıntı için inceleyin. Daha fazla bilgi için bkz: [yük testi sonuçlarını çözümleme ve hataları Tablo görünümünde](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

> [!NOTE]
> Daraltma ve bölüm başlığının sol oku seçerek bu bölümü genişletin.

## <a name="page-results"></a>Sonuçlar sayfası

Sayfa sonuçları bölümü yük testindeki tüm Web sayfalarının listesini içerir. URL, senaryo, sayısı, ortalama sayfa süresi ve testin adı görüntülenir. Açmak için bir sayfanın URL'sini seçebilirsiniz **sayfaları** tablo ve daha fazla ayrıntı için bu sayfayı inceleyin. Daha fazla bilgi için bkz: [nasıl yapılır: Görünümü Web sayfası yanıt](../test/how-to-view-web-page-response-time-in-a-load-test.md).

> [!NOTE]
> Daraltma ve bölüm başlığının sol oku seçerek bu bölümü genişletin.

## <a name="transaction-results"></a>İşlem sonuçları

İşlem sonuçları bölümü yük testindeki tüm işlemlerin listesini içerir. İşlem, senaryo, test, yanıt süresi, geçen süre ve sayı adı görüntülenir. Açmak için bir işlem adını seçebilirsiniz **işlemleri** tablo ve bu işlem için daha fazla ayrıntı için inceleyin. Daha fazla bilgi için bkz: [yük testi sonuçlarını çözümleme ve hataları Tablo görünümünde](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

> [!NOTE]
> Daraltma ve bölüm başlığının sol oku seçerek bu bölümü genişletin.

Yüzdelik değerler aşağıdaki işlem bilgilerini raporu:

-   Toplam işlemlerinin % 90 tamamlandı değerinden \<zaman > saniye.

-   Toplam işlemlerinin % 95 tamamlandı değerinden \<zaman > saniye.

## <a name="system-under-test-resources"></a>Test kaynakları altında sistem

Test kaynakları bölümü altında sistem yük üretildiği hedef bilgisayarlar kümesi olan bilgisayarların listesini içerir. Bu sayaç kümelerini aracısı veya denetleyici dışında topladığınız bilgisayarları içerir. Bilgisayar adı, % işlemci zamanı ve kullanılabilir bellek görüntülenir. Açmak için bir bilgisayar adı seçebilirsiniz **Test sisteminde** grafik ve zaman içinde kaynak kullanımını görün. Daha fazla bilgi için bkz: [Grafik görünümünde yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-in-the-graphs-view.md).

> [!NOTE]
> Daraltma ve bölüm başlığının sol oku seçerek bu bölümü genişletin.

## <a name="controller-and-agent-resources"></a>Denetleyici ve aracı kaynakları

Denetleyici ve aracı kaynakları bölümü testi çalıştırmak için kullanılan bilgisayarların listesini içerir. Bilgisayar adı, % işlemci zamanı ve kullanılabilir bellek görüntülenir. Açmak için bir bilgisayar adı seçebilirsiniz **denetleyicisi ve aracıları** grafik ve zaman içinde kaynak kullanımını görün. Daha fazla bilgi için bkz: [Grafik görünümünde yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-in-the-graphs-view.md).

> [!NOTE]
> Daraltma ve bölüm başlığının sol oku seçerek bu bölümü genişletin.

## <a name="errors"></a>Hatalar

Hatalar bölümü yük testi sırasında gerçekleşen tüm hataların listesini içerir. Türüne ve alt hata, sayı ve son ileti görüntülenir. Açmak için bir hata seçebilirsiniz **hataları** tablo ve daha fazla hata ayrıntılarını inceleyin. Daha fazla bilgi için bkz: [yük testi sonuçlarını çözümleme ve hataları Tablo görünümünde](../test/analyze-load-test-results-and-errors-in-the-tables-view.md) ve [nasıl yapılır: Sayaçlar panelini kullanarak çözümleme hataları](../test/how-to-analyze-errors-using-the-counters-panel.md).

> [!NOTE]
> Daraltma ve bölüm başlığının sol oku seçerek bu bölümü genişletin.

## <a name="printing-a-summary"></a>Bir Özet yazdırma

Yük Testi Özeti seçerek yazdırabilirsiniz **yazdırma** Özet kısayol menüsünde. Seçerek önce yazdırmayı önizleyebilirsiniz **Baskı Önizleme** Özet kısayol menüsünde. Ayrıca, doğrudan önizleme ekranından yazdırabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [Eşik kuralı ihlallerini çözümleme](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)