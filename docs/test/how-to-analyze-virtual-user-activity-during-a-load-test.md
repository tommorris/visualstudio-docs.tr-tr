---
title: Visual Studio Yük testleri için sanal kullanıcı etkinliğini çözümleme
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- virtual user activity chart, viewing
ms.assetid: 8bda19b3-91c1-4daf-b6c7-09108bddadff
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: f7da7f881cf70ebfdafb3dbaaf2821471327fa81
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751240"
---
# <a name="how-to-analyze-what-virtual-users-are-doing-during-a-load-test-using-the-virtual-user-activity-chart"></a>Nasıl yapılır: Sanal Kullanıcı Etkinlik Grafiğini Kullanarak Bir Yük Testi Sırasında Sanal Kullanıcıların Ne Yaptıklarını Çözümleme

Sanal kullanıcı etkinlik grafiğini kullanarak yük testi ile ilişkili sanal kullanıcı etkinliğini görüntüleyin. Grafik her satırda tek bir sanal kullanıcı temsil eder. Sanal Kullanıcı Etkinlik Grafiği tam olarak ne her sanal kullanıcı test sırasında yürütülmekte olan gösterir. Kullanıcı etkinliği desenleri görmek, yük desenleri, yavaş veya başarısız testleri ilişkilendirmenizi ve diğer sanal kullanıcı etkinliğini istekleriyle bakın. Sanal Kullanıcı Etkinlik Grafiği, yalnızca yük testi çalışması bittikten sonra kullanılabilir.

Aşağıdaki yordamlar, sanal kullanıcı etkinlik grafiği görüntüleme, belirli bir kullanıcının etkinliğinin nasıl araştırılacağını ve filtrelemenin nasıl kullanılacağını göstermektedir.

## <a name="to-view-the-virtual-user-activity-chart-in-your-load-test-results"></a>Yük testi sonuçlarında Sanal Kullanıcı Etkinlik Grafiği görüntülemek için

1.  Sanal kullanıcı verilerini görüntülemek için öncelikle yapılandırmalısınız **Tüm Bireysel Ayrıntılar** ayarını **zamanlama ayrıntıları depolama** yük testi ile ilişkili olan özellik. Daha sonra Yük testi çalıştırın. Daha fazla bilgi için bkz: [nasıl yapılır: yapılandırma toplama tam sanal kullanıcı etkinlik grafiğini etkinleştirmek için ayrıntıları](../test/how-to-configure-load-tests-to-collect-full-details.md).

2.  Yükleme işleminden sonra test çalışmasını, test sonuçları Özet sayfası görüntülenir. Seçin **kullanıcı ayrıntı** araç çubuğunda.

     veya

     Grafik görünümü seçerek açın **grafikleri** araç çubuğunda. Bir grafiğe sağ tıklayın ve ardından **Kullanıcı detayına git**.

     Bu seçeneği kullanırsanız, sanal kullanıcı etkinlik grafiği otomatik tıklattığınız testin bir parçası yakınlaştırmalı. İşaretçinizi üzerinde yaklaşık olarak 30 ikinci işareti bulunuyorsa, örneğin, ayrıntı görünümü yaklaşık olarak 30 ikinci işareti görünümü görüntülenir **zaman aralığına Yakınlaştır** Sanal Kullanıcı Etkinlik Grafiği altındaki aracı.

     Ardından, kullanabileceğiniz Sanal Kullanıcı Etkinlik Grafiği, belirli kullanıcıları etkinliği ayrıntıları inceleyin.

## <a name="to-investigate-a-specific-users-activity-in-the-virtual-user-activity-chart"></a>Sanal Kullanıcı Etkinlik Grafiği belirli kullanıcılara etkinliğinde araştırmak için

1.  Yakınlaştırma saat dönem aracı için Sanal Kullanıcı Etkinlik Grafiği altındaki belirli bir kullanıcı hakkında ayrıntılar araştırmak istediğiniz grafik alanı seçmek için kullanın.

2.  Grafikte bir ayrıntı üzerinde gezdirin. Aşağıdaki bilgiler araç ipucunda görüntülenir dikkat edin:

    -   **Kullanıcı Kimliği**

    -   **Senaryo**

    -   **Test**

    -   **URL** (bir test veya işlem görüntülenmez)

    -   **Sonucu**

    -   **Tarayıcı** (bir test veya işlem görüntülenmez)

    -   **Ağ**

    -   **Başlangıç zamanı**

    -   **Süre**

    -   **Aracı**

    -   **Test günlüğü** (test günlüğüne bağlantı)

        > [!NOTE]
        > Uygulamanızın hata ayıklamasına yardımcı olmak üzere Test günlüğü bağlantısını seçerseniz, günlükle ilişkilendirilmiş Web testi sonucu veya birim testi sonucu açılır.

     Ardından, Sanal Kullanıcı Etkinlik Grafiği'nde filtreleme ve vurgulama işlemlerini kullanabilirsiniz.

## <a name="to-use-filtering-options-in-the-virtual-user-activity-chart"></a>Sanal Kullanıcı Etkinlik Grafiği'filtreleme seçeneklerini kullanma

1.  Ayrıntılar göstergede, ya da seçmek için aşağı açılan listeyi kullanın. **Test**, **sayfa**, veya **işlem**.

     **Ayrıntılar gösterge paneli**

     ![Ayrıntılar gösterge paneli](../test/media/ltest_detailslegend.png)

2.  Hataları, günlükleri, testler, arama ve yük testi ile ilişkili aspx sayfalar onay kutularının işaretini kaldırın veya seçin.

     Sanal Kullanıcı Etkinlik Grafiği uygun şekilde güncelleştirir.

     Sanal Kullanıcı Etkinlik Grafiği testleri, sayfalar ve işlemleri birkaç farklı ölçütlere göre filtrelemenize olanağı sağlar. Belirli testleri görünümden kaldır veya tüm başarılı testleri kaldırabilir veya belirli hataları ile başarısız olan testleri kaldırabilirsiniz. Günlükleri olmayan tüm testleri de kaldırabilirsiniz.

     Örneğin, seçebileceğiniz **(hataları vurgula)** Sepeti tüm hataları görüntüleyen seçeneği renkli kırmızı. Öğesini de seçebilirsiniz **(Vurgula günlükleri sonuçlarıyla)** grafikte yeşil renkle gösterilmiş tüm test sonuçlarını görüntüleyen seçeneği.

     **Filtre sonuçlar paneli**

     ![Filtre sonuçlar paneli](../test/media/ltest_filterresults.png)

3.  Filtre sonuçlarında seçin veya aşağıdaki filtre seçenekleri için onay kutularını temizleyin:

    -   **Yalnızca günlüğe sahip sonuçları göster** yalnızca test test günlükleri bunlarla ilişkilendirilmiş olan sonuçlarını görüntüler.

    -   **Başarılı sonuçları göster** başarılı sonuçlarını görüntüler.

    -   **Sonuçları hatalarla Göster** hata ayıklamaya yardımcı olabilecek hatalı sonuçları görüntüler.

        > [!NOTE]
        > Bölümünde listelenen hata türlerinin listesi **Göster hatalı sonuçları** düğüm daha fazla araştırılması Web Performans Testi Sonuçları Görüntüleyicisi araç çubuğunda tabloları düğmesini seçerek. Daha fazla bilgi için bkz: [yük testi sonuçlarını çözümleme ve hataları Tablo görünümünde](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

     Sanal Kullanıcı Etkinlik Grafiği uygun şekilde güncelleştirir.

## <a name="see-also"></a>Ayrıca bkz.

- [Ayrıntılar görünümünde sanal kullanıcı etkinliğini çözümleme](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [İzlenecek yol: sorunları yalıtmak için sanal kullanıcı etkinlik grafiğini kullanma](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)