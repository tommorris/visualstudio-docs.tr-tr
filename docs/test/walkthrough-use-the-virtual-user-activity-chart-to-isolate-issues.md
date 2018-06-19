---
title: Visual Studio Yük testleri için sanal kullanıcı etkinlik grafiğini kullanarak
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, virtual user activity chart
- virtual user activity chart, isolating performance issues
ms.assetid: d1c10fb9-cfeb-4e7f-9991-2d1e1103699e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: fedc9aebb4d57e258370179bbf820abdc8978940
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31976438"
---
# <a name="walkthrough-using-the-virtual-user-activity-chart-to-isolate-issues"></a>İzlenecek yol: Sorunları Yalıtmak İçin Sanal Kullanıcı Etkinliği Grafiğini Kullanma

Bu kılavuzda, Sanal Kullanıcı Etkinlik Grafiği yük testinizi çalıştıran tek tek sanal kullanıcılar için oluşmuş hataları yalıtmak için nasıl kullanılacağını öğreneceksiniz.

 Sanal Kullanıcı Etkinlik Grafiği yük testi ile ilişkili sanal kullanıcı etkinliğini görmenize olanak sağlar. Grafik her satırda tek bir sanal kullanıcı temsil eder. Sanal Kullanıcı Etkinlik Grafiği tam olarak ne her sanal kullanıcı test sırasında yürütülmekte olan gösterir. Bu, kullanıcı etkinlik düzenlerini görerek performans sorunlarını belirlemek, yük desenleri, yavaş veya başarısız testleri ilişkilendirmenizi ve diğer sanal kullanıcı etkinliği ile ilgili istekleri görmenizi sağlar. Sanal Kullanıcı Etkinlik Grafiği çalışması bittikten sonra yalnızca yükleme işleminden sonra kullanılabilir.

 Bu kılavuzda, aşağıdaki görevleri tamamlar:

-   Sanal Kullanıcı Aktivite Grafiği ile ilişkili aşağıdaki araçları nasıl kullanacağınız hakkında bilgi edinin:

    -   Kullanım **zaman aralığına Yakınlaştır** aracı grafiğin analiz etmek istediğiniz belirli bir süre belirtin.

    -   Kullanım **ayrıntıları gösterge** paneli ve **sonuçlarını filtreleme** sorunlarını gidermeye yardımcı olmak için grafiğe filtre uygulamak için Denetim Masası,.

-   Belirli bir sanal kullanıcı için oluşan bir hatayı analiz etmek ve sorunlu hata türü ayrıntılarını görüntülemek için Sanal Kullanıcı Aktivite Grafiği'ni kullanın.

 Daha fazla bilgi için bkz: [Ayrıntılar görünümünde sanal kullanıcı etkinliğini çözümleme](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md).

## <a name="prerequisites"></a>Önkoşullar

-   Visual Studio Enterprise

-   Bu yordamları tamamlayın:

    -   [Kayıt ve bir web performans testi](http://msdn.microsoft.com/en-us/bd0a82fd-cec0-4861-bc09-e1b0b2d258ef).

    -   [Oluşturma ve bir yük testi çalıştırma](http://msdn.microsoft.com/en-us/7041cbcf-9ab1-4579-98ff-8f296aeaded4)

## <a name="open-the-colorwebapp-solution-created-in-the-previous-walkthroughs"></a>Önceki izlenecek yollarda oluşturulmuş ColorWebApp çözümünü açın

### <a name="open-the-solution"></a>Çözümü açın

1.  Visual Studio'yu başlatın.

2.  LoadTest1.loadtest öğesini içeren ColorWebApp çözümünü açın. Bu yük testi gerçekleştirme adımları bu konunun önkoşullar bölümünde başında listelenen üç izlenecek kaynaklanır.

     Bu kılavuzda kalan adımlar ColorWebApp, ColorWebAppTest.webtest olarak adlandırılan bir Web performans testi ve LoadTest1.loadtest olarak adlandırılan bir yük testi adlı bir Web uygulaması varsayılır.

## <a name="run-the-load-test"></a>Yük testi çalıştırma
 Sanal Kullanıcı Etkinlik verilerini toplamak üzere yük testlerini çalıştırın.

### <a name="run-the-load-test-to-collect-virtual-user-activity-data"></a>Sanal Kullanıcı Etkinlik verilerini toplamak için yük testi çalıştırma

-   Yük Testi Düzenleyicisi'nde seçin **çalıştırmak** araç çubuğunda. LoadTest1 çalışmaya başlar.

## <a name="isolate-issues-in-the-virtual-user-activity-chart"></a>Sanal Kullanıcı Etkinlik Grafiği sorunlarını yalıtma

Yük testlerini çalıştırın ve sanal kullanıcı etkinlik verileri toplanan sonra verileri yük testi sonuçlarında yük kullanarak görüntüleyebileceğiniz Testi Çözümleyicisinin Ayrıntılar sanal kullanıcı etkinliği grafiğini görüntüleyin. Ayrıca, Sanal Kullanıcı Etkinlik Grafiği yük testlerini performans sorunları gidermeye yardımcı olmak için kullanabilirsiniz.

### <a name="to-use-the-virtual-user-activity-chart-in-your-load-test-results"></a>Yük testi sonuçlarında Sanal Kullanıcı Etkinlik Grafiği kullanmak için

1.  Yükleme sonrası test tamamlandıktan çalıştıran, yük testi sonuçlarını Özet sayfası Yük Testi Çözümleyicisi'nde görüntülenir. Seçin **grafikleri** araç çubuğunda.

     Grafikler görünümünde görüntülenir.

2.  Üzerinde **sayfa yanıt süresi** grafik, eşik ihlali simgelerinden birini sağ tıklatın ve seçin **Kullanıcı detayına git**.

    > [!NOTE]
    > Kullanabileceğiniz **ayrıntıları** kullanıcı etkinliği grafiğini çok açmak için Yük Testi Düzenleyicisi araç çubuğu düğmesi. Ancak, kullanırsanız **Kullanıcı detayına git** seçeneği, sanal kullanıcı etkinlik grafiği otomatik olarak yakınlaştırma grafiğe sağ tıklandığında test bölümüne.

     Ayrıntılar görünümü görüntülenir **Sanal Kullanıcı Etkinlik Grafiği** Eşik ihlallerini gerçekleştiği zaman dilimi üzerine odaklanan.

     Y ekseninde yatay çizimler ayrı ayrı sanal kullanıcıları temsil eder. X ekseni yük testi için zaman çizelgesi görüntüler.

3.  İçinde **zaman aralığına Yakınlaştır** aracı aşağıdaki **Sanal Kullanıcı Etkinlik Grafiği**, sol ayarlayın ve her ikisi de kadar sağ kaydırıcılar eşik ihlali simgesine kapatın. Bu zaman ölçeği değiştirir **Sanal Kullanıcı Etkinlik Grafiği**

4.  İçinde **ayrıntıları gösterge**, onay kutusunu seçin **(hataları vurgula)**. Eşik ihlali neden olan sanal kullanıcının vurgulanmış olduğuna dikkat edin.

5.  İçinde **sonuçlarını filtreleme** paneli, onay kutularını temizleyin **Göster başarılı sonuçları** ve **HTTP hatası** ancak bırakın **ValidationRuleError**onay kutusu seçili.

     **Sanal Kullanıcı Etkinlik Grafiği** önceki yönergelerde yapılandırılmış eşik ihlali tarafından belirtilen Red.aspx sayfasında 3 saniyeden fazla harcanan sanal kullanıcıları görüntüler.

6.  Fare işaretçisini eşik ihlali için doğrulama kuralı hatasıyla sanal kullanıcıyı temsil eden yatay çizgi üzerine bırakın.

7.  Araç İpucu ile aşağıdaki bilgiler görüntülenir:

    -   **Kullanıcı Kimliği**

    -   **Senaryo**

    -   **Test**

    -   **Sonucu**

    -   **Ağ**

    -   **Başlangıç zamanı**

    -   **Süre**

    -   **Aracı**

    -   **Test günlüğü**

8.  Dikkat **Test günlük** bir bağlantıdır. Seçin **Test günlük** bağlantı.

9. Günlükle ilişkili ColorWebTest Web performans testine Web Performans Testi Sonuçları Görüntüleyicisi'nde açar. Eşik ihlalleri oluştuğu yalıtmak bu sağlar.

     Çeşitli ayarları hem de kullanabilirsiniz **ayrıntıları gösterge** ve **sonuçlarını filtreleme** performans sorunlarını ve yükleme testlerindeki hataları yalıtmaya yardımcı olmak için paneller. Bu ayarlarla deneme ve **zaman aralığına Yakınlaştır** içinde sanal kullanıcı verilerini nasıl temsil edildiğini görmek için aracı **Sanal Kullanıcı Etkinlik Grafiği**.

## <a name="see-also"></a>Ayrıca bkz.

- [Ayrıntılar görünümünde sanal kullanıcı etkinliğini çözümleme](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [Test denetleyicileri ve test aracıları](configure-test-agents-and-controllers-for-load-tests.md)
- [Nasıl yapılır: Dağıtılmış yük testi için Test ayarı oluşturma](../test/how-to-create-a-test-setting-for-a-distributed-load-test.md)
- [Test aracılarını yükleme ve yapılandırma](../test/lab-management/install-configure-test-agents.md)
- [Test ayarlarını kullanarak tanılama bilgileri Topla](../test/collect-diagnostic-information-using-test-settings.md)