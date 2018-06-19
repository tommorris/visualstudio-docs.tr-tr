---
title: Visual Studio'da bir web performansı ve yük testi projesi oluşturma
ms.date: 03/14/2018
ms.topic: quickstart
helpviewer_keywords:
- load testing, quickstart
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 4349220f650eef98ee765c1e7dbacb69263fe845
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31976721"
---
# <a name="quickstart-create-a-load-test-project"></a>Hızlı Başlangıç: yük testi projesi oluşturma

Bu 10 dakikalık quickstart oluşturmak ve Visual Studio'da bir Web performansı ve yük testi projesi çalıştırmak öğreneceksiniz. Yük testleri Web performans veya çok sayıda kullanıcı aynı anda bir sunucuya erişirken benzetimini yapmak için birim testleri yürütün.

> [!IMPORTANT]
> Web performans ve yük testi projelerini yalnızca Visual Studio 2017 Enterprise Edition'da kullanılabilir.

## <a name="install-the-load-testing-component"></a>Bileşen sınama yükleyin

Yoksa zaten Web performansı ve yük test etme araçları bileşeninin yüklü değilse, Visual Studio yükleyicisi yüklemeniz gerekir.

1. Visual Studio yükleyicisi Windows Başlat menüsünden açmak. Ayrıca Visual Studio'dan içinde erişebildiğinizi **yeni proje** iletişim kutusu veya seçerek **Araçları** > **alma araçları ve özelliklerinin...**  menü çubuğundan.

1. Visual Studio yükleyicisinde seçin **bileşenleri tek tek** sekmesini tıklatın ve doğru aşağı kaydırın **hata ayıklama ve test** bölümü. Seçin **Web performansı ve Yük Test Etme Araçları**.

   ![Web performans ve yük test etme araçları bileşeni](media/web-perf-load-testing-tools-component.png)

1. Seçin **Değiştir** düğmesi.

   Web performans ve yük test etme araçları bileşeni yüklenir.

## <a name="create-a-load-test-project"></a>Bir yük testi projesi oluşturma

Bu bölümde, bir C# yük testi projesi oluşturacağız. İsterseniz, ayrıca bir Visual Basic yük testi projesi oluşturabilirsiniz.

1. Visual Studio'yu açın ve seçin **dosya** > **yeni** > **proje...**  menü çubuğundan.

   **Yeni proje** iletişim kutusu açılır.

1. İçinde **yeni proje** iletişim kutusunda, genişletin **yüklü** ve **Visual C#** ve ardından **Test** kategorisi. Seçin **Web performansı ve yük testi projesi** şablonu.

   ![Web performans ve yük testi proje şablonu](media/web-perf-load-test-project-template.png)

1. Varsayılan adı kullanın ve ardından istemiyorsanız, bir proje adı **Tamam**.

   Visual Studio projesi oluşturur ve dosyaları görüntüler **Çözüm Gezgini**. Proje adlı bir Web testi dosyası başlangıçta içeriyor *WebTest1.webtest*.

## <a name="add-a-load-test-to-the-project"></a>Bir yük testi projeye ekleyin

1. Sağ tıklatma menüsünden veya bağlam menüsü, proje düğümünün **Çözüm Gezgini**, seçin **Ekle** > **yük testi...** .

   **Yeni Yük Testi Sihirbazı** açar.

1. Seçin **şirket içi yük testi** seçeneğini ve ardından **sonraki**. Bulut tabanlı yük testi hakkında daha fazla bilgiyi [burada](/vsts/load-test/get-started-simple-cloud-load-test).

   ![Yeni Yük Testi Sihirbazı - ilk sayfa](media/load-test-wizard-page-1.png)

1. Seçin **sonraki** adımına ulaşana kadar Sihirbazı aracılığıyla **bir yük testi senaryosuna testleri ekleme ve test karışımını düzenleme** sayfası. Seçin **Ekle** düğmesi.

   **Testler Ekle** iletişim kutusu açılır.

1. Altında **kullanılabilir testler**seçin **WebTest1'i**ve ardından taşımanız için sağ oka **seçili testleri** kutusu. Seçin **Tamam** düğmesi.

   ![Testleri iletişim kutusu ekleme](media/add-tests-dialog-box.png)

1. Geri **Yeni Yük Testi Sihirbazı**, seçin **son** düğmesi.

   Yük testi projeye eklenir ve yük testi dosya Düzenleyicisi penceresinde açılır.

## <a name="run-the-load-test"></a>Yük testi çalıştırma

Değil oldukça yapın, ancak şimdi çalıştırmak yine de bir yük testi oluşturduk.

Sağ tıklatma menüsünden veya düzenleyicide açık yük testi bağlam menüsünü seçin **yük testi Çalıştır**.

![Yük testi menü çalıştırın](media/run-load-test.png)

Yük testi çalışmaya başlar. **Test sonuçları** penceresi gösterir test ediyor ve Yük Testi Çözümleyicisi Düzenleyicisi penceresinde görüntülenir. Varsayılanları kabul gerekiyorsa, beş dakika olmalıdır test, tamamlandıktan sonra Düzenleyicisi'nde bir özeti gösterilir. Seçebileceğiniz **grafikleri**, **tabloları**, veya **ayrıntı** yük testi sonuçlarını hakkında farklı bilgi almak için.

![Yük Testi Çözümleyicisi penceresini](media/load-test-analyzer.png)

## <a name="next-steps"></a>Sonraki adımlar

Basit yük testi projesi oluşturduğunuza göre sonraki adım senaryoları, sayaç kümeleri, yapılandırma ve çalıştırma ayarlarını olmaktır.

> [!div class="nextstepaction"]
> [Test ayarlarını düzenleme](edit-load-tests.md)