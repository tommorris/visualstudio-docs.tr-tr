---
title: C# ve Visual Studio'da ASP.NET Core kullanmaya başlama
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
ms.openlocfilehash: 40aba1d8847b405c3e80f0d6890471f0e2065a86
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089457"
---
# <a name="get-started-with-c-and-aspnet-in-visual-studio"></a>C# ve Visual Studio'da ASP.NET kullanmaya başlama

Visual Studio kullanarak ASP.NET Core ile C# geliştirme için Bu öğreticide, bir C# ASP.NET Core web uygulaması oluşturma, kodu ekleyin, IDE özelliklerinden bazıları keşfedin ve uygulamayı çalıştırın.

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

## <a name="before-you-begin"></a>Başlamadan önce

Burada, bazı temel kavramları tanıtmak için bir hızlı sık sorulan sorular verilmiştir.

### <a name="what-is-c"></a>C# nedir?

[C#](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework) , güçlü ve öğrenmek kolay olması için tasarlanmış bir tür kullanımı uyumlu ve nesne odaklı programlama dilidir.

### <a name="what-is-aspnet-core"></a>ASP.NET çekirdeği nedir?

ASP.NET Core web uygulamaları ve Hizmetleri gibi internet'e bağlı uygulamaları oluşturmak için açık kaynaklı ve platformlar arası bir çerçevedir. ASP.NET Core uygulamaları .NET Core veya .NET Framework üzerinde çalışabilir. Geliştirme ve ASP.NET Core uygulamaları platformlar arası Windows, Mac ve Linux üzerinde çalıştırın. ASP.NET Core olduğundan, açık kaynak [GitHub](https://github.com/aspnet/home).

### <a name="what-is-visual-studio"></a>Visual Studio nedir?

Visual Studio, geliştiriciler için üretkenlik araçları'nın bir tümleşik geliştirme paketidir. Bunu, programları ve uygulamaları oluşturmak için kullanabileceğiniz bir program olarak düşünün.

## <a name="start-developing"></a>Geliştirmeye başlayın

Geliştirmeye başlamak hazır mısınız? Gidelim!

### <a name="create-a-project"></a>Proje oluşturma

İlk olarak, bir ASP.NET Core projesi oluşturacaksınız. Proje türü herhangi bir şey bile eklediğiniz önce ihtiyacınız vardır tüm şablonu dosyalarıyla birlikte verilir.

1. Visual Studio 2017'ni açın.

2. Üst menü çubuğundan seçin **dosya** > **yeni** > **proje**.

3. İçinde **yeni proje** iletişim kutusunun sol bölmesinde **Visual C#**, genişletin **Web**ve ardından **.NET Core**. Orta bölmede seçin **ASP.NET çekirdek Web uygulaması**, dosya adı *MyCoreApp*ve ardından **Tamam**.

   ![Visual Studio IDE'de yeni proje iletişim kutusundaki ASP.NET Core Web uygulaması proje şablonu](../ide/media/new-project-csharp-aspnet-mycoreapp.png)

#### <a name="add-a-workload-optional"></a>(İsteğe bağlı) bir iş yükü ekleme

Görmüyorsanız, **ASP.NET çekirdek Web uygulaması** proje şablonu, alabilirsiniz, ekleyerek **ASP.NET ve web geliştirme** iş yükü. Bu iş yükü bağlı olarak Visual Studio 2017 güncelleştirmeleri makinenize yüklü iki aşağıdaki yollardan biriyle ekleyebilirsiniz.

##### <a name="option-1-use-the-new-project-dialog-box"></a>Seçenek 1: Yeni Proje iletişim kutusunu kullanın

1. Seçin **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu.

   ![Yeni Proje iletişim kutusundan açık Visual Studio yükleyicisi bağlantıyı seçin](../ide/media/vs-open-visual-studio-installer-generic.png)

2. Visual Studio yükleyicisi başlatır. Seçin **ASP.NET ve web geliştirme** iş yükü ve ardından **Değiştir**.

   ![Visual Studio yükleyicisi .NET core platformlar arası geliştirme iş yükü](../ide/media/asp-dot-net-web-dev-workload.png)

##### <a name="option-2-use-the-tools-menu-bar"></a>Seçenek 2: araçlar menü çubuğu'nu kullanın

1. İşyeri dışında iptal **yeni proje** iletişim kutusuna ve üst menü çubuğundan seçin **Araçları** > **alma araçları ve özelliklerinin**.

2. Visual Studio yükleyicisi başlatır. Seçin **ASP.NET ve web geliştirme** iş yükü ve ardından **Değiştir**.

#### <a name="add-a-project-template"></a>Bir proje şablonu Ekle

1. İçinde **çekirdek yeni bir ASP.NET Web uygulaması** iletişim kutusunda, seçin **Web uygulaması (Model-View-Controller)** proje şablonu.

2. Seçin **ASP.NET Core 2.0** üstteki açılan menüden. (Görmüyorsanız **ASP.NET Core 2.0** listesinde izleyerek yükleyin **karşıdan** iletişim kutusunun üstündeki yanında sarı çubuğu görüntülenmelidir bağlantıyı.) Seçin **Tamam**.

   ![Yeni ASP.NET çekirdek Web uygulaması iletişim kutusu](../ide/media/new-project-csharp-aspnet-web-app-mvc.png)

### <a name="about-your-solution"></a>Çözümünüzü hakkında

Bu çözüm, bir uygulamayı üç ana bileşenlerine ayırır Model-View-Controller (MVC) tasarım örüntüsü aşağıdaki gibidir:

* **Modelleri** uygulama verilerini temsil eden sınıfları içerir. Modeli sınıflarını doğrulama mantığını bu verilere iş kurallarını zorunlu tutmak için kullanın. Genellikle, model nesneleri alabilir ve model durumu bir veritabanında depolar.
* **Görünümler** uygulamanın kullanıcı arabirimini (UI) görüntüleyen bileşenlerdir. Genellikle, bu UI model verileri görüntüler.
* **Denetleyicileri** tarayıcı istekleri işlemek sınıfları içerir. Bunlar, model verileri almak ve bir yanıt döndürür görünüm şablonları çağırın. Bir MVC uygulamasında, görünüm yalnızca bilgileri görüntüler; Denetleyici işler ve kullanıcı girişini ve etkileşimini yanıt verir.

MVC örüntüsü, test ve güncelleştirmek geleneksel tek yapılı uygulamalar kolay uygulamalar oluşturmanıza yardımcı olur.

### <a name="tour-your-solution"></a>Çözümünüzü turu

 1. Proje şablonu bir çözüm adlı tek bir ASP.NET Core projeyle oluşturur **MyCoreApp**. İçeriğini kullanıma sunmak için proje düğümünü genişletin.

    ![Visual Studio'da ASP.NET Çözüm Gezgini](../ide/media/csharp-aspnet-solution-explorer-mycoreapp.png)

 2. Açık *HomeController.cs* dosya **denetleyicileri** klasör.

     ![Visual Studio Çözüm Gezgini'nde HomeController.cs dosyasında](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

 3. Görünüm *HomeController.cs*

     ![Visual Studio kod penceresinde HomeController.cs](../ide/media/csharp-aspnet-home-controller-code.png)

 4. Projeyi de sahip bir **görünümleri** her denetleyiciye eşleme diğer klasörleri içeren klasörü (biri yanı sıra **paylaşılan** görünümler). Örneğin, görünüm CSHTML dosyası (HTML uzantı) için */ev/hakkında* yolu adresindeki olacaktır *Views/Home/About.cshtml*. Bu dosyayı açın.

     ![Visual Studio'da Çözüm Gezgini'nde About.cshtml dosyası](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

 5. Bu CSHTML dosyası standart etiketleri ve satır içi C# bir bileşimine dayalı HTML oluşturmak için Razor sözdizimini kullanır.

     ![Visual Studio kod penceresinde About.cshtml](../ide/media/csharp-aspnet-about-cshtml-code.png)

   >[!NOTE]
   > Bunun hakkında daha fazla bilgi edinmek için [C# ve ASP.NET Razor sözdizimini kullanarak kullanmaya başlama](/aspnet/web-pages/overview/getting-started/introducing-razor-syntax-c) sayfası.

 6. Çözüm de içeren bir *wwwroot* web siteniz için kök klasör. Statik içerik, CSS, görüntüler ve JavaScript kitaplıklarını gibi doğrudan site dağıtıldığında olması istersiniz yollarında koyabilirsiniz.

     ![Visual Studio'da Çözüm Gezgini'ndeki Wwwroot klasörüne](../ide/media/csharp-aspnet-solution-wwwroot.png)

 7. Proje, kendi paketleri ve çalışma zamanında uygulama yönetmek için hizmet yapılandırma dosyalarını, çeşitli vardır. Örneğin, varsayılan uygulama [yapılandırma](/aspnet/core/fundamentals/configuration) depolanan *appsettings.json*. Ancak, bazı/tüm ortam başına temelinde, bu ayarları gibi sağlayarak kılabilirsiniz bir *appsettings. Development.JSON* dosya **geliştirme** ortamı.

     ![Visual Studio'da Çözüm Gezgini'nde yapılandırma dosyaları](../ide/media/csharp-aspnet-solution-explorer-config-files.png)

## <a name="run-and-debug-the-application"></a>Çalıştırın ve uygulamada hata ayıklama

1. Seçin **IIS Express** oluşturmak ve uygulama hata ayıklama modunda çalıştırmak için IDE'de düğmesi. (Alternatif olarak, basın **F5**, veya seçin **hata ayıklama > hata ayıklamayı Başlat** menü çubuğundan.)

   ![Visual Studio'da IIS Express düğmesini seçin](../ide/media/csharp-aspnet-iis-express-button.png)

  > [!NOTE]
  > Bildiren bir hata iletisi alırsanız **web sunucusuna 'IIS Express' bağlanılamıyor**, Visual Studio'yu kapatın ve kullanarak açmak **yönetici olarak çalıştır** sağ tıklatın veya bağlam menüsünden seçeneği. Daha sonra uygulamayı yeniden çalıştırın.

2. Visual Studio bir tarayıcı penceresi başlatır. Seçin **hakkında**.

   ![Uygulamanız için tarayıcı penceresinde hakkında seçin](../ide/media/csharp-aspnet-browser-page.png)

 Başka şeylerin **hakkında** sayfasını tarayıcıda işler kümesinde metin *HomeController.cs* dosya.

   ![Hakkında sayfasında metin görüntüleme](../ide/media/csharp-aspnet-browser-page-about.png)

3. Bir tarayıcı penceresi açın ve geri dönüş için Visual Studio tutun. Açık *Controllers/HomeController.cs* zaten açık değilse.

   ![Visual Studio'da Çözüm Gezgini'nden HomeController.cs dosyasını açın](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

4. İlk satırında bir kesme noktası belirleyerek **hakkında** yöntemi. Bunu yapmak için kenar boşluğunda tıklatın veya satır ve tuşuna imleci ayarlamak **F9**.

  Bu satırı bazı veri kümelerinin de **ViewData** CSHTML sayfanın işlenmeden koleksiyonu *Views/Home/About.cshtml*.

   ![About.cshtml hakkında yönteminde ilk satırında bir kesme noktası ayarlayın.  ](../ide/media/csharp-aspnet-home-controller-code-set-breakpoint.png)

5. Tarayıcı ve yenileme için iade **hakkında** sayfası. Bu, Visual Studio'da kesme noktası tetikler.

6. Visual Studio'da üzerinden fare **ViewData** üye onun verilerini görüntüleyebilirsiniz.

   ![Daha fazla bilgi görmek için hakkında yöntemi ViewData üyesi görüntüleyin](../ide/media/csharp-aspnet-home-controller-view-breakpoint-info.png)

7. Eklemek için kullanılan yöntemin aynısını kullanarak uygulama kesme noktası kaldırın.

8. Açık *Views/Home/About.cshtml*.

   ![Çözüm Gezgini'nde About.cshtml seçin](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

9. Metin değiştirme **"ek"** için **"değiştirildi"** ve dosyayı kaydedin.

   !["Değiştir"okur metne ek"okur metin değiştirildi"](../ide/media/csharp-aspnet-about-cshtml-code-change.png)

10. Güncelleştirilmiş metni görmek için tarayıcı penceresine dönün. (Değiştirdiğiniz metin görmüyorsanız, tarayıcıyı yenileyin.)

    ![Değiştirilen metni görmek için tarayıcı penceresini yenileyin](../ide/media/csharp-aspnet-browser-page-about-changed.png)

11. Seçin **durdurma hata ayıklama** hata ayıklamasını durdurmak için araç çubuğu düğmesinden. (Alternatif olarak, basın **Shift**+**F5**, veya seçin **hata ayıklama** > **durdurma hata ayıklama** menü çubuğundan.)

   ![Araç çubuğundaki Durdur hata ayıklama düğmesini seçin](../ide/media/csharp-aspnet-stop-debugging.png)

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticiyi tamamlamak Tebrikler! C# ASP.NET Core ve Visual Studio IDE hakkında biraz öğrenilen umuyoruz. Ortak sunucu üzerinde çalışan uygulama görmek için aşağıdaki düğmesini seçin.

> [!div class="nextstepaction"]
> [Uygulama Azure App Service'e dağıtma](..//deployment/quickstart-deploy-to-azure.md)

Model-View-Controller (MVC) çerçevesi ASP.NET Core kullanarak öğreticiyi izleyerek hakkında da bilgi alabilirsiniz [ASP.NET Core MVC ve Visual Studio ile çalışmaya başlama](/aspnet/core/tutorials/first-mvc-app/start-mvc?tabs=aspnetcore2x).
