---
title: C# ve Visual Studio'da ASP.NET Core ile çalışmaya başlama
ms.custom: ''
ms.date: 06/27/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 9df1cbae3b0233a8711ab6a287513d89670df4d4
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39177376"
---
# <a name="get-started-with-c-and-aspnet-in-visual-studio"></a>C# ve Visual Studio'da ASP.NET kullanmaya başlama

Visual Studio kullanarak ASP.NET Core ile C# geliştirme için Bu öğreticide, bir C# ASP.NET Core web uygulaması oluşturma, kodu ekleyin, bazı IDE özelliklerini ve uygulamayı çalıştırın.

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

## <a name="before-you-begin"></a>Başlamadan önce

İşte bazı temel kavramlara tanıtmak için hızlı bir SSS.

### <a name="what-is-c"></a>C# nedir?

[C#](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework) sağlam ve öğrenmesi kolay olacak şekilde tasarlanan bir tür kullanımı uyumlu ve nesne yönelimli programlama dilidir.

### <a name="what-is-aspnet-core"></a>ASP.NET Core nedir?

ASP.NET Core web uygulamaları ve hizmetler gibi İnternet'e bağlı uygulamalar oluşturmaya yönelik açık kaynaklı ve platformlar arası bir çerçevedir. .NET Core veya .NET Framework üzerinde ASP.NET Core uygulamaları çalıştırabilirsiniz. Geliştirin ve Windows, Mac ve Linux'ta ASP.NET Core uygulamaları platformlar arası çalıştırın. ASP.NET Core, açık kaynak konumunda [GitHub](https://github.com/aspnet/home).

### <a name="what-is-visual-studio"></a>Visual Studio nedir?

Visual Studio geliştiricileri için üretkenlik aracından oluşan bir tümleşik geliştirme paketidir. Bunu, programları ve uygulamaları oluşturmak için kullanabileceğiniz bir program olarak düşünün.

## <a name="start-developing"></a>Geliştirmeye başlayın

Geliştirmeye başlamak hazır mısınız? Gidelim!

### <a name="create-a-project"></a>Proje oluşturma

İlk olarak, bir ASP.NET Core projesi oluşturacaksınız. Proje türü bile herhangi bir şey ekledik önce ihtiyacınız olacak tüm şablon dosyaları ile birlikte gelir.

1. Visual Studio 2017'yi açın.

2. Üstteki menü çubuğundan seçin **dosya** > **yeni** > **proje**.

3. İçinde **yeni proje** iletişim kutusunun sol bölmesinde, **Visual C#**, genişletin **Web**ve ardından **.NET Core**. Orta bölmede seçin **ASP.NET Core Web uygulaması**, dosya adı *MyCoreApp*ve ardından **Tamam**.

   ![Visual Studio IDE'de yeni proje iletişim kutusundaki ASP.NET Core Web uygulaması proje şablonu](../ide/media/new-project-csharp-aspnet-mycoreapp.png)

#### <a name="add-a-workload-optional"></a>(İsteğe bağlı) bir iş yükü Ekle

Görmüyorsanız **ASP.NET Core Web uygulaması** proje şablonu, alabilirsiniz, ekleyerek **ASP.NET ve web geliştirme** iş yükü. Bu iş yükü, makinenizde yüklü Visual Studio 2017 güncelleştirmeleri bağlı olarak iki aşağıdaki yollardan biriyle ekleyebilirsiniz.

##### <a name="option-1-use-the-new-project-dialog-box"></a>Seçenek 1: Yeni Proje iletişim kutusunu kullanın.

1. Seçin **açık Visual Studio yükleyicisi** sol bölmesinde bağlantıyı **yeni proje** iletişim kutusu.

   ![Yeni Proje iletişim kutusundan açık Visual Studio yükleyicisi bağlantıyı seçin](../ide/media/vs-open-visual-studio-installer-generic.png)

2. Visual Studio Yükleyicisi'ni başlatır. Seçin **ASP.NET ve web geliştirme** iş yükü ve ardından **Değiştir**.

   ![.NET core çoklu platform geliştirme iş yükünü Visual Studio yükleyicisi](../ide/media/asp-dot-net-web-dev-workload.png)

##### <a name="option-2-use-the-tools-menu-bar"></a>2. seçenek: araçlar menü çubuğunu kullanın.

1. / İptal **yeni proje** iletişim kutusu ve üst menü çubuğundan seçin **Araçları** > **araçları ve özellikleri Al**.

2. Visual Studio Yükleyicisi'ni başlatır. Seçin **ASP.NET ve web geliştirme** iş yükü ve ardından **Değiştir**.

#### <a name="add-a-project-template"></a>Bir proje şablonu Ekle

1. İçinde **yeni ASP.NET Core Web uygulaması** iletişim kutusunda **Web uygulaması (Model-View-Controller)** proje şablonu.

2. Seçin **ASP.NET Core 2.0** üstteki açılan menüden. (Görmüyorsanız **ASP.NET Core 2.0** listesinde izleyerek yükleyin **indirme** iletişim kutusunun üst kısmındaki sarı çubuk gözükeceğini bağlantıyı.) Seçin **Tamam**.

   ![Yeni ASP.NET Core Web uygulaması iletişim kutusu](../ide/media/new-project-csharp-aspnet-web-app-mvc.png)

### <a name="about-your-solution"></a>Çözümünüzü hakkında

Bu çözüm, bir uygulamayı üç ana bileşene ayırır Model-View-Controller (MVC) mimari deseni izler:

* **Modelleri** uygulama verilerini temsil eden sınıfları içerir. Model sınıfları, veriler için iş kuralları zorlamak için doğrulama mantığını kullanın. Genellikle, model nesneleri alabilir ve model durumu bir veritabanında depolar.
* **Görünümleri** uygulamanın kullanıcı arabirimini (UI) görüntüleyen bileşenlerdir. Genellikle, bu UI model verileri görüntüler.
* **Denetleyicileri** tarayıcı istekleri işleyen sınıflar içerir. Bunlar, model verileri almak ve bir yanıt döndüreceğini görünüm şablonları arayın. Bir MVC uygulamasında, görünüm yalnızca bilgileri görüntüler; Denetleyici, işler ve kullanıcı girişini ve etkileşimini yanıt verir.

MVC örüntüsü, geleneksel tek yapılı uygulamaları kolay test etme ve güncelleştirme uygulamalar oluşturmanıza yardımcı olur.

### <a name="tour-your-solution"></a>Çözümünüzü turuna katılın

 1. Proje şablonu, bir çözüm ile adlı bir tek bir ASP.NET Core projesi oluşturur. **MyCoreApp**. İçeriğini göstermek için proje düğümünü genişletin.

    ![Visual Studio'da ASP.NET Çözüm Gezgini](../ide/media/csharp-aspnet-solution-explorer-mycoreapp.png)

 2. Açık *HomeController.cs* dosya **denetleyicileri** klasör.

     ![Visual Studio'daki Çözüm Gezgini'nde HomeController.cs dosyasında](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

 3. Görünüm *HomeController.cs*

     ![Visual Studio kod penceresinde HomeController.cs](../ide/media/csharp-aspnet-home-controller-code.png)

 4. Proje de sahip bir **görünümleri** her denetleyici için harita diğer klasörler içeren klasörü (biri yanı sıra **paylaşılan** görünümleri). Örneğin, görünüm CSHTML dosyası (HTML uzantı) için */Home/About* yolu konumunda olacak *Views/Home/About.cshtml*. Bu dosyayı açın.

     ![Visual Studio'daki Çözüm Gezgini'nde About.cshtml dosyasında](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

 5. Bu CSHTML dosyasını birleşimi standart etiketleri ve satır içi C# dayalı HTML oluşturmak için Razor sözdizimini kullanır.

     ![Visual Studio kod penceresinde About.cshtml](../ide/media/csharp-aspnet-about-cshtml-code.png)

   >[!NOTE]
   > Bunun hakkında daha fazla bilgi edinmek için [C# ve Razor sözdizimini kullanan ASP.NET kullanmaya başlama](/aspnet/web-pages/overview/getting-started/introducing-razor-syntax-c) sayfası.

 6. Çözüm ayrıca içeren bir *wwwroot* Web siteniz için kök klasör. Statik içerik, CSS, görüntü ve JavaScript kitaplıkları gibi doğrudan site dağıtıldığında olması istersiniz yollarında koyabilirsiniz.

     ![Visual Studio'daki Çözüm Gezgini'nde Wwwroot klasörü](../ide/media/csharp-aspnet-solution-wwwroot.png)

 7. Proje, paketleri ve uygulama çalışma zamanında yönetmek için hizmet yapılandırma dosyalarının birçok vardır. Örneğin, varsayılan uygulama [yapılandırma](/aspnet/core/fundamentals/configuration) depolanan *appsettings.json*. Ancak, tüm/bazı ortam başına temelinde, bu ayarları gibi sağlayarak kılabilirsiniz bir *appsettings. Development.JSON* dosya **geliştirme** ortam.

     ![Visual Studio'daki Çözüm Gezgini'nde yapılandırma dosyaları](../ide/media/csharp-aspnet-solution-explorer-config-files.png)

## <a name="run-and-debug-the-application"></a>Çalıştırın ve uygulamanın hatasını ayıklama

1. Seçin **IIS Express** oluşturmak ve uygulamayı hata ayıklama modunda çalıştırmak için IDE'de düğmesi. (Alternatif olarak, basın **F5**, ya da seçin **hata ayıklama > hata ayıklamayı Başlat** menü çubuğundan.)

   ![Visual Studio'da IIS Express düğmeyi seçin](../ide/media/csharp-aspnet-iis-express-button.png)

  > [!NOTE]
  > Bildiren bir hata iletisi alırsanız **web sunucusu için 'IIS Express' bağlanılamıyor**, Visual Studio'yu kapatın ve ardından kullanarak açın **yönetici olarak çalıştır** sağ tıklayın veya bağlam menüsünde seçenek. Ardından, uygulamayı yeniden çalıştırın.

2. Visual Studio, bir tarayıcı penceresi açar. Seçin **hakkında**.

   ![Uygulamanız için tarayıcı penceresinde hakkında seçin](../ide/media/csharp-aspnet-browser-page.png)

 Başka şeylerin yanında **hakkında** sayfasını tarayıcıda işler ayarlanmış olan metin *HomeController.cs* dosya.

   ![Hakkında sayfasında metin görüntüleme](../ide/media/csharp-aspnet-browser-page-about.png)

3. Tarayıcı penceresi açın ve geri dönüş için Visual Studio tutun. Açık *Controllers/HomeController.cs* zaten açık değilse.

   ![Visual Studio'da Çözüm Gezgini'nden HomeController.cs dosyasını açın](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

4. İlk satırında bir kesme noktası ayarlamak **hakkında** yöntemi. Bunu yapmak için kenar boşluğunda tıklayın veya imleci satır ve ENTER tuşuna ayarlamak **F9**.

  Bu satırı bazı veri kümelerine **ViewData** CSHTML sayfa işlenir koleksiyonu *Views/Home/About.cshtml*.

   ![About.cshtml hakkında yöntemin ilk satırında bir kesme noktası ayarlayın.  ](../ide/media/csharp-aspnet-home-controller-code-set-breakpoint.png)

5. İade tarayıcı ve yenileme **hakkında** sayfası. Bu, Visual Studio'da kesme noktası tetikler.

6. Visual Studio'da üzerine gelip **ViewData** üye onun verilerini görüntüleyebilirsiniz.

   ![Daha fazla bilgi görmek için hakkında yöntemi ViewData üyesi görüntüleyin](../ide/media/csharp-aspnet-home-controller-view-breakpoint-info.png)

7. Uygulama kesme noktası eklemek için kullanılan yöntemin aynısını kullanarak kaldırın.

8. Açık *Views/Home/About.cshtml*.

   ![Çözüm Gezgini'nde About.cshtml seçin](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

9. Metni Değiştir **"ek"** için **"değiştirildi"** ve dosyayı kaydedin.

   !["Değişiklik"okuyan metne ek"yazan metnin değiştirildi"](../ide/media/csharp-aspnet-about-cshtml-code-change.png)

10. Güncelleştirilen metin görmek için tarayıcı penceresine dönün. (Değiştirilen metni görmüyorsanız, tarayıcıyı yenileyin.)

    ![Değiştirilen metni görmek için tarayıcı penceresini yenilemeniz](../ide/media/csharp-aspnet-browser-page-about-changed.png)

11. Seçin **hata ayıklamayı Durdur** hata ayıklamayı durdurmak için araç çubuğundan düğme. (Alternatif olarak, basın **Shift**+**F5**, ya da seçin **hata ayıklama** > **hata ayıklamayı Durdur** menü çubuğundan.)

   ![Araç çubuğundaki hata ayıklamayı Durdur düğmesini seçin.](../ide/media/csharp-aspnet-stop-debugging.png)

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticiyi tamamlamak Tebrikler! C#, ASP.NET Core ve Visual Studio IDE hakkında biraz öğrenilen umuyoruz. Ortak bir sunucu üzerinde çalışan uygulamayı görmek için aşağıdaki düğmeyi seçin.

> [!div class="nextstepaction"]
> [Uygulamayı Azure App Service'e dağıtma](..//deployment/quickstart-deploy-to-azure.md)

Öğreticiyi izleyerek ASP.NET Core Model-View-Controller (MVC) çerçevesini kullanma hakkında da bilgi edinebilirsiniz [ASP.NET Core MVC ve Visual Studio ile çalışmaya başlama](/aspnet/core/tutorials/first-mvc-app/start-mvc?tabs=aspnetcore2x).
