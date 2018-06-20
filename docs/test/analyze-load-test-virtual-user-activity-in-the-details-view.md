---
title: Visual Studio yükleme testi sanal kullanıcı etkinliğini çözümleme
ms.date: 10/03/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.monitor.activitychart
helpviewer_keywords:
- virtual user activity chart
- load test, virtual user activity chart
ms.assetid: 63f4bd42-3cfb-4eee-af68-e8334976539e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 5ab42b66fca32dc5325ce0cb4d78fbb53df8b90f
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36233801"
---
# <a name="analyzing-load-test-virtual-user-activity-in-the-details-view-of-the-load-test-analyzer"></a>Yük Testi Çözümleyicisinin Ayrıntılar görünümünde Yük Testi Sanal Kullanıcı etkinliğini çözümleme

**Sanal Kullanıcı Etkinlik Grafiği**

 ![Sanal Kullanıcı Etkinlik Grafiği](../test/media/virtual_actchart.png)

 **Ayrıntıları** görüntülemek görüntüler **Sanal Kullanıcı Etkinlik Grafiği**, yük testi sırasında tek tek sanal kullanıcıların ne yaptığını görsel olarak çözümlemek için kullanılır. **Sanal Kullanıcı Etkinlik Grafiği** kullanıcı etkinliği desenleri görmek, yük desenleri, yavaş veya başarısız testleri ilişkilendirmenizi ve diğer sanal kullanıcı etkinliği ile ilgili istekleri görmenizi sağlar. **Sanal Kullanıcı Etkinlik Grafiği** CPU kullanımını, saniye başına isteklerdeki bırakmaları belirlemenize yardım edebilir ve hangi testleri veya sayfaları çalışan bırakmaları ve ani sırasında.

> [!NOTE]
> Kullanmak istediğiniz yük testini çalıştırmadan önce **sanal kullanıcı etkinlik ayrıntıları grafiği**, doğrulamanız gerekir **zamanlama ayrıntıları depolama** özelliği ayarlanmış  **AllIndividualDetails** yük Performans Testi Düzenleyicisini kullanarak seçeneği. Daha fazla bilgi için bkz: [nasıl yapılır: sanal kullanıcı etkinlik grafiğini etkinleştirmek için tüm ayrıntıların toplanmasını yapılandırma](../test/how-to-configure-load-tests-to-collect-full-details.md).

 **Ayrıntılar gösterge paneli**

 ![Ayrıntılar gösterge paneli](../test/media/ltest_detailslegend.png)

 Ayrıntılar gösterge paneli görünür **Sanal Kullanıcı Etkinlik Grafiği**. Ayrıntılar gösterge bölmesi testleri, sayfalar ve işlemleri birkaç farklı ölçütlere göre filtrelemenize olanak sağlar. Örneğin, bazı testleri görünümden kaldırabilir veya tüm başarılı testleri kaldırabilir veya belirli hataları ile başarısız olan testleri kaldırın. Günlükleri olmayan tüm testleri de kaldırabilirsiniz.

 Tüm başarısız testler kırmızı renkte görüntüleyen başarısız oldu, testleri vurgulayın. Ayrıca test günlükleri olan testleri vurgulu hale getirebilirsiniz. Günlük içeren testler yeşil renkte.

 **Sonuçlar Panelini filtreleme**

 ![Filtre sonuçlar paneli](../test/media/ltest_filterresults.png)

 Filtre sonuçlar paneli görünür **Sanal Kullanıcı Etkinlik Grafiği**. Filtre sonuçlar paneli aşağıdakilere göre filtreleyebilirsiniz:

-   **Yalnızca günlüğe sahip sonuçları göster** yalnızca test test günlükleri bunlarla ilişkilendirilmiş olan sonuçlarını görüntüler.

-   **Başarılı sonuçları göster** başarılı sonuçlarını görüntüler.

-   **Sonuçları hatalarla Göster** hata ayıklamaya yardımcı olabilecek hatalı sonuçları görüntüler.

## <a name="tasks"></a>Görevler

|Görevler|İlgili Konular|
|-----------|-----------------------|
|**Sanal Kullanıcı Etkinlik Grafiği kullanmak üzere yük testlerini yapılandırma:** sanal kullanıcı etkinlik verilerini görüntülemek istediğiniz bir yük testi çalıştırmadan önce yük testleri özelliği ayarlarınızı ilk yapılandırmanız gerekir.|-   [Nasıl yapılır: sanal kullanıcı etkinlik grafiğini etkinleştirmek için tüm ayrıntıların toplanmasını yapılandırma](../test/how-to-configure-load-tests-to-collect-full-details.md)|
|**Yük testi:** bir yük testi oluşturdunuz ve sanal kullanıcı etkinlik verilerini toplama etkinleştirmek için yapılandırdıktan sonra sipariş Kime görünümünde tamamlanana kadar test çalıştırmalısınız **Sanal Kullanıcı Etkinlik Grafiği**.||
|**Sanal kullanıcı etkinlik verileri içeren yük testi sonuçlarını görüntüleyin:** yük testlerini yapılandırılmış, oluşturuldu ve çalışması tamamlandıktan sonra kullanarak sanal kullanıcı etkinlik verilerini görüntüleyebilirsiniz **Sanal Kullanıcı Etkinlik Grafiği** .|-   [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)<br />-   [Nasıl yapılır: bir yük testi sırasında sanal kullanıcıların ne yaptıklarını çözümleme](../test/how-to-analyze-virtual-user-activity-during-a-load-test.md)|
|**Yük testlerinde performans sorunlarını yalıtma:** kullanabileceğiniz **Sanal Kullanıcı Etkinlik Grafiği** yük testlerini performans sorunları gidermeye yardımcı olmak için.|-   [İzlenecek yol: sorunları yalıtmak için sanal kullanıcı etkinlik grafiğini kullanma](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)|

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Yük testi sonuçlarını ve hatalarını Tablo görünümünde analiz eder.](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)