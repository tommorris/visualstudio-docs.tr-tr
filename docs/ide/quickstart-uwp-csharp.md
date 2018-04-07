---
title: "Hızlı Başlangıç: Visual Studio'da XAML ve C# ile ilk Evrensel Windows platformu uygulamanızı oluşturma | Microsoft Docs"
ms.custom: ''
ms.date: 04/04/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: quickstart
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 7caba5278ec415aec036c501d4911bcd5c7f3c77
ms.sourcegitcommit: 3724338a5da5a6d75ba00452b0a607388b93ed0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2018
---
# <a name="quickstart-create-your-first-universal-windows-platform-application-in-visual-studio-with-xaml-and-c35"></a>Hızlı Başlangıç: Visual Studio'da XAML ve C ile ilk Evrensel Windows platformu uygulamanızı oluşturma&#35;

Bu 5-10 dakikalık bir giriş Visual Studio tümleşik geliştirme ortamı (IDE), herhangi bir Windows 10 aygıtta çalışan bir "Hello World" uygulaması oluşturacaksınız. Bunu yapmak için bir evrensel Windows Platformu (UWP) proje şablonu, Genişletilebilir uygulama biçimlendirme dili (XAML) ve C# programlama dili kullanmanız.

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) ücretsiz yüklemek için sayfa.

## <a name="create-a-project"></a>Proje oluşturma

İlk olarak, bir evrensel Windows platformu projesi oluşturun. Proje türü herhangi bir şey bile eklediğiniz önce gereken tüm şablonu dosyalarıyla birlikte gelen!

1. Visual Studio 2017'ni açın.

2. Üst menü çubuğundan seçin **dosya** > **yeni** > **proje...** .

3. Sol bölmesinde **yeni proje** iletişim kutusunda, genişletin **Visual C#**ve ardından **Windows Evrensel**. Orta bölmede seçin **boş uygulama (Evrensel Windows)**. Sonra proje adı *HelloWorld* ve **Tamam**.

   ![Visual Studio IDE'de yeni proje iletişim kutusunda Windows Evrensel proje şablonu](../ide/media/new-project-csharp-uwp-helloworld.png)

   > [!NOTE]
   > Görmüyorsanız, **boş uygulama (Evrensel Windows)** proje şablonu, tıklatın **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu.<br><br>![Yeni Proje iletişim kutusundan açık Visual Studio yükleyicisi bağlantısına tıklayın](../ide/media/vb-open-visual-studio-installer-hello-world.png)<br><br>Visual Studio yükleyicisi başlatır. Seçin **Evrensel Windows platformu geliştirme** iş yükü ve ardından **Değiştir**.<br><br>![Evrensel Windows platformu geliştirme iş yükü Visual Studio yükleyicisi](../ide/media/uwp-dev-workload.png)

4. Zaman **yeni evrensel Windows platformu projesi** seçin iletişim kutusu görüntülenirse, **Tamam**.

   ![Varsayılan hedef sürüm ve yeni evrensel Windows platformu projesi iletişim kutusunda en düşük sürüm ayarlarını kabul edin](../ide/media/new-uwp-project-target-minver-dialog.png)

  > [!NOTE]
  > Bu ilk kez kullanıyorsanız, bir UWP uygulaması oluşturmak için Visual Studio kullandığınız bir **ayarları** iletişim kutusu görünebilir. Seçin **geliştirici modunu**ve ardından **Evet**.<br><br>
 ![UWP Ayarları iletişim kutusunda geliştirici modunu etkinleştir](../ide/media/enable-developer-mode.png)<br><br>Visual Studio sizin için ek bir geliştirici modu paket yükler. Paket yükleme tamamlandığında kapat **ayarları** iletişim kutusu.

## <a name="create-the-application"></a>Uygulama oluşturma

Geliştirmeye başlamak için zamanı. Düğme denetimi ekleyin eylem düğme ekleme ve nasıl göründüğünü görmek için "Hello World" uygulamayı başlatın.

### <a name="add-a-button-to-the-design-canvas"></a>Tasarım tuvale düğme ekleme

1. İçinde **Çözüm Gezgini**, çift **MainPage.xaml** bölünmüş görünümünü açın.

  ![MainPage.xaml Çözüm Gezgini'nden açın ](../ide/media/uwp-solution-explorer-MainPage-xaml.png)

  İki bölme vardır: **XAML Tasarımcısı**, bir tasarım tuvali içerir ve **XAML Düzenleyicisi'ni**, burada ekleyebilir veya kodu değiştirin.    

  ![XAML Düzenleyicisi'ni XAML Tasarımcısı bölmesinde](../ide/media/uwp-xaml-editor.png)

2. Seçin **araç** araç uçarak çıkış penceresini açmak için.

  ![Araç kutusu uçarak çıkış penceresini açmak için araç'e tıklayın](../ide/media/uwp-toolbox.png)

  (Araç seçeneği görmüyorsanız, menü çubuğundan açabilirsiniz. Bunu yapmak için seçin **Görünüm** > **araç**. Veya basın **Ctrl**+**Alt**+**X**.)

3. Tıklatın **PIN** araç kutusu pencere sabitlemek için simge.

  ![Araç kutusu pencere sabitlemek için PIN simgesine tıklayın](../ide/media/uwp-toolbox-autohide.png)

4. Tıklatın **düğmesini** denetlemek ve tasarım tuvale sürükleyin.

   ![Düğme denetimi tıklatın ve tasarım tuvale sürükleyin](../ide/media/uwp-toolbox-add-button-control.png)

  XAML Düzenleyicisi'nde kod bakarsanız, düğme vardır, çok eklendiğini görürsünüz:

  ![Düğme denetimi tıklatın ve tasarım tuvale sürükleyin](../ide/media/uwp-xaml-control-code-window.png)

### <a name="add-a-label-to-the-button"></a>Etiket düğme ekleme

1. XAML Düzenleyicisi'nde düğmesi içerik değeri "Düğmesinden" için "Hello World!" değiştirin

   ![Hello World düğmesi içerik değerini değiştirin](../ide/media/uwp-change-button-text-in-xaml-code-window.png)

2. XAML Tasarımcısı'nda düğmesi, çok değiştiğine dikkat edin.

   ![Düğme Hello World tasarım tuvalde değişir.](../ide/media/uwp-button-text-change-in-design-canvas.png)

### <a name="add-an-event-handler"></a>Olay işleyici ekleme

"Olay işleyicisi" ses karmaşık, ancak bir olay gerçekleştiğinde çağrılan kod için başka bir ad değil. Bu durumda, "Hello World!" için bir eylem ekler düğme.

1. Düğme denetimi tasarım tuval üzerinde çift tıklatın.

2.  Olay işleyicisini düzenleme *MainPage.xaml.cs*, arka plan kod sayfası.

 Şeyler ilginç nereden budur. Varsayılan olay işleyicisini şöyle görünür:

   ![Varsayılan Button_Click olay işleyicisi ](../ide/media/uwp-button-click-code.png)

 Şuna benzer şekilde, değiştirelim:

    ![Yeni zaman uyumsuz Button_Click olay işleyicisi ](../ide/media/uwp-add-hello-world-async-code.png)

  Kopyalama ve yapıştırma için kod aşağıdaki gibidir:

  ```C#
  private async void Button_Click(object sender, RoutedEventArgs e)
         {
             MediaElement mediaElement = new MediaElement();
             var synth = new Windows.Media.SpeechSynthesis.SpeechSynthesizer();
             Windows.Media.SpeechSynthesis.SpeechSynthesisStream stream = await synth.SynthesizeTextToStreamAsync("Hello, World!");
             mediaElement.SetSource(stream, stream.ContentType);
             mediaElement.Play();
         }
  ```

#### <a name="what-did-we-just-do"></a>Biz yalnızca ne?

Kod bir konuşma Birleştirici nesnesi oluşturmak için bazı Windows API'larını kullanır ve söylemek için bazı metinleri sağlar. (SpeechSynthesis kullanma hakkında daha fazla bilgi için bkz: <xref:System.Speech.Synthesis>.)

## <a name="run-the-application"></a>Uygulamayı çalıştırın

Oluşturun, dağıtın ve ne göründüğünü ve benzer görmek için "Hello World" UWP uygulamasını başlatmak için zaman yapılır. İşte nasıl.

1. Seçin **yerel makine** uygulamayı başlatmak için.

   ![Başlatmak ve UWP uygulamanızın hatalarını ayıklama için yerel makineye tıklayın](../ide/media/uwp-start-or-debug.png "başlatmak ve UWP uygulamanızın hatalarını ayıklama için yerel makine tıklatın")

   (Alternatif olarak, seçebileceğiniz **hata ayıklama** > **hata ayıklamayı Başlat** menü çubuğu veya tuşuna **F5** uygulamanızı başlatmak için.)

2. En kısa sürede bir giriş ekranı kaybolur sonra hangi görünür uygulamanızı görüntüleyin. Uygulama şuna benzer görünmelidir:

   ![Bir UWP uygulaması "Hello World"](../ide/media/uwp-hello-world-app.png)

3. Tıklatın **Hello World** düğmesi.

 Windows 10 cihaz tam anlamıyla söyleyin, "Hello, World!"

4. Uygulamayı kapatmak için tıklatın **durdurma hata ayıklama** araç çubuğu düğmesi. (Alternatif olarak, seçin **hata ayıklama** > **hata ayıklamayı durdurun** menü çubuğunu ya basın **Shift**+**F5**.)

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıç Tamamlanıyor Tebrikler! UWP ve Visual Studio IDE hakkında bazı temel konuları öğrendiğinize göre umuyoruz. Daha fazla bilgi için aşağıdaki eğitici devam edin:

> [!div class="nextstepaction"]
> [Bir kullanıcı arabirimi oluşturma](/windows/uwp/design/basics/xaml-basics-ui)
