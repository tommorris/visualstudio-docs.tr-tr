---
title: Visual Studio Yük testi sonuçlarını çözümleme | Microsoft Docs
ms.date: 10/20/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, test results
- load tests, analyzing test results
- load tests, managing test results
ms.assetid: 8a4ba300-425d-447c-91d9-c53f4345feee
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 7add3789d3c48fb405818f50efd47bb83cb9f899
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="analyze-load-test-results-using-the-load-test-analyzer"></a>Yük testi çözümleyicisini kullanarak yük testi sonuçlarını çözümleme

Engelleri bulun, hataları belirlemek ve Yük Testi Çözümleyicisi kullandığınızda, uygulamanızda geliştirmeleri ölçebilirsiniz. Bu yolla yük testi sonuçlarını çözümleyin:

-   Bir yük testi çalışırken izleyin.

-   Tamamlandıktan sonra bir yük testi analiz edin.

-   Önceki bir yük testi sonuçlarını görüntüleyin.

Paydaşlar ile paylaşmak üzere eğilim analizi için iki veya daha fazla raporlar karşılaştırmak raporlar da oluşturabilirsiniz. Bkz: [Test karşılaştırmaları veya eğilim analizleri için yük testleri sonuçları raporlama](../test/compare-load-test-results.md).

Visual Studio Enterprise veya komut satırından yük testlerini olup çalıştırın ve tek bir bilgisayara veya bir uzak makinede yük testlerini çalıştırın olup, bu görevleri tamamlayabilirsiniz.

## <a name="differences-between-analyzing-a-running-and-a-completed-load-test"></a>Bir çalışan ve tamamlanmış bir yük testi çözümlenirken arasındaki farklar

 Bir yük testi çalıştırdığınızda, Yük Testi Çözümleyicisi adını yük testlerini ve testin başlatıldığı zaman birlikte ayrı bir sekmesinde görüntüler (örneğin, **LoadTest1 [12:40 PM]**). Bir yük testi çalıştığında, daha küçük bir performans sayacı verilerini kümesi bellekte tutulur. Yük testi çalıştığında, bu veri kümesini izleyebilirsiniz. Bir yük testi tamamlandıktan sonra veritabanından veri kümesini analiz edebilirsiniz. Hangi verilerin bir yük testi çalışır ve hangi yükleme sonrasında görebilirsiniz veri test tamamlandıktan sonra görüntülenen farklar vardır. Örneğin, yüzde 90'ından ve yüzde 95'yanıt zamanı verilerini Yük testi tamamlanana kadar hesaplanmıyor. Bazı farklar da verileri çözümlemek kullanılabilen araçlar işlevindeki oluşur.

 Yük testi çalıştırdığınızda, iki görünüm mevcuttur: grafikler görünümünde ve Tablolar görünümünde. Grafik görünümü, toplanan grafik performans sayaçları sağlar. Tablo görünümü her testleri, sayfalar, işlemleri ve toplanan isteklerin hakkında bilgi sağlar. Ayrıca hataları listeleyen bir tablo elde edersiniz.

 Yük testi tamamlandığında, varsayılan olarak, Özet görünümü görüntülenir. Araç çubuğunu kullanarak Özet, grafikler, tablolar ve Ayrıntılar görünümleri arasında geçiş yapabilirsiniz. Yük Testi Çözümleyicisi yerleşik veya normal Visual Studio penceresi işleme teknikler kullanılarak kayana ayarlayın. Tamamlanan yük testi çalıştırmalarını çözümlediğinizde birden çok yük testi farklı bir yük testi çalışmalarını karşılaştırmak için aynı anda açık çözümleyiciler olabilir.

## <a name="tasks"></a>Görevler

|Görevler|İlgili Konular|
|-----------|-----------------------|
|**Yük testi sonuçlarına erişme:** Yük Testi Düzenleyicisi'nden bir yük testi çalıştırdığınızda yük testi sonuçları otomatik olarak açılır ve çalışan yük testi Yük Testi Çözümleyicisi'nde görüntülenir.|-   [Nasıl yapılır: yük testi sonuçlarını çözümleme için erişim](../test/how-to-access-load-test-results-for-analysis.md)|
|**Çözümleme Notları, yük testine ekleme:** çözümleme yaptığında yük testine yorumlar ekleyebilirsiniz. Açıklamalar yük testi sonucu ile birlikte kalıcı olarak depolanır. Aynı zamanda girdiğiniz açıklama görüntüler **açıklama** Yük Testi Düzenleyicisi'ni açın ve Test sonuçlarını yönetme iletişim kutusunda yük testi ile ilişkili sütun.<br /><br /> Daha fazla bilgi için bkz: [nasıl yapılır: erişim yük testi sonuçlarını çözümleme için](../test/how-to-access-load-test-results-for-analysis.md).<br /><br /> Ayrıca, bir Excel raporu yük test sonuçlarını oluşturduğunuzda yorumlar görüntülenir.<br /><br /> Daha fazla bilgi için bkz: [Test karşılaştırmaları veya eğilim analizleri için yük testleri sonuçlarını raporlama](../test/compare-load-test-results.md).|-   [Nasıl yapılır: tamamlanmış bir yük testi çözümlenirken açıklama ekleme](../test/how-to-add-comments-on-a-completed-load-test.md)|
|**Yük testi sonuçlarını çözümleme:** veri yük testi eriştikten sonra sonuç verileri analiz edebilirsiniz. Sonuçları hızla anlamak için yük testi özetini görüntüleyebilirsiniz. Yük Testi Özeti kısa ve kolay okunur bir biçimde anahtar sonuçlarını gösterir.<br /><br /> Yük testi özeti yazdırabilirsiniz. Bu proje katılımcılarına sonuçları iletişim kurarken kullanmak uygun sağlar.<br /><br /> Tablolar ve grafikler sonuçları kullanarak yük testi sonuçlarını ayrıntılarını analiz edebilirsiniz. Bunlar, hatalar, sayfalar, istekleri, SQL izleme, testleri, eşikleri ve işlemleri içerir.|-   [Yük Testi Sonuçları Özeti genel bakış](../test/load-test-results-summary-overview.md)<br />-   [Nasıl yapılır: Web sayfası yanıtını görüntüleme](../test/how-to-view-web-page-response-time-in-a-load-test.md)<br />-   [Eşik kuralı ihlallerini çözümleme](../test/analyze-threshold-rule-violations-in-load-tests.md)<br />-   [Grafik görünümünde yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-in-the-graphs-view.md)<br />-   [Yük testi sonuçlarını ve hatalarını Tablo görünümünde analiz eder.](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)|
|**Performans sorunlarını belirlemek için yük testi sonuçlarında sanal kullanıcı etkinliğini çözümleme:** bir yük testi sırasında sanal kullanıcıların ne yaptıklarını görselleştirmek için Sanal Kullanıcı Etkinlik Grafiği kullanabilirsiniz. Bu, bir CPU ani veya İsteği/sn bırakmaları yalıtmak ve hangi testler veya sayfaları bu ani ve düşmeye sırasında çalışan belirlemek yardımcı olabilir.|-   [Ayrıntılar görünümünde sanal kullanıcı etkinliğini çözümleme](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)|