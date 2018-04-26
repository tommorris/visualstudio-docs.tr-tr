---
title: 'İzlenecek yol: C# veya Visual Basic ile basit uygulama oluşturma'
ms.date: 10/03/2017
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: f84339c7-d617-4f56-bfcd-af2215c347ba
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: d0b386af06bb977a6319cf52b92806b150747ca5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-create-a-simple-application-with-c-or-visual-basic"></a>İzlenecek yol: C# veya Visual Basic ile basit uygulama oluşturma
Bu kılavuzu izleyerek araçları, iletişim kutuları ve Visual Studio ile uygulamaları geliştirirken kullanabileceğiniz tasarımcıları çoğu öğrenmeniz. Basit bir "Hello, World" uygulaması oluşturma, kullanıcı arabirimini tasarım, kodu ekleyin ve tümleşik geliştirme ortamı (IDE) çalışma hakkında bilgi edinin sırasında hatalar, hata ayıklama.

##  <a name="BKMK_ConfigureIDE"></a> IDE yapılandırın
Visual Studio ilk kez başlattığınızda, oturum açmak için istenir. Bu adım, bu kılavuz için isteğe bağlıdır. Sonraki geliştirme ayarları ve renk temasını seçmenizi ister bir iletişim kutusu gösterilebilir. Varsayılanları tutun ve seçin **Start Visual Studio**.

![Ayarları iletişim kutusu seç](../ide/media/exploreide-settings.png "exploreide ayarları")

Visual Studio'yu başlattıktan sonra aracı windows, menüleri ve araç çubukları ve ana penceresi alanı görürsünüz. Araç pencereleri yerleşik ve uygulama penceresinin sol tarafında üzerinde ile **hızlı başlatma**, menü çubuğundaki ve standart araç çubuğu üstünde. Uygulama penceresi merkezinde **başlangıç sayfası**. Bir çözüm ya da proje yüklediğinizde, düzenleyiciler ve tasarımcıları alanı görünür nerede **başlangıç sayfası** değil. Bir uygulama geliştirirken, çoğu zaman, merkezi bu alandaki harcamanız.

![Genel Ayarları uygulanmış IDE](../ide/media/exploreide-idewithgeneralsettings.png "ExploreIDE IDEwithgeneralsettings")

##  <a name="BKMK_CreateApp"></a> Basit bir uygulama oluşturma

### <a name="create-the-project"></a>Projeyi oluşturma
Visual Studio'da bir uygulama oluştururken önce bir proje ve bir çözüm oluşturursunuz. Bu örnekte, bir Windows Presentation Foundation (WPF) projesi oluşturacaksınız.

#### <a name="to-create-the-wpf-project"></a>WPF projesini oluşturmak için

1.  Yeni bir proje oluşturun. Menü çubuğunda seçin **dosya**, **yeni**, **proje...** .

     ![Menü çubuğunda, dosya, yeni seçin, proje](../ide/media/exploreide-filenewproject.png "ExploreIDE FileNewProject")

2.  Sol bölmede seçerek Visual Basic veya Visual C# WPF uygulaması şablonu seçin **yüklü**, **Visual C#**, **Windows Klasik Masaüstü**, örneğin ve ardından seçme **WPF uygulaması (.NET Framework)** Orta bölmede.  Yeni Proje iletişim kutusunun altındaki HelloWPFApp proje adı.

     ![Bir C# WPF projesi, HelloWPFApp oluşturma](../ide/media/exploreide-newprojectcsharp.png "ExploreIDE NewProjectcsharp")

Visual Studio HelloWPFApp proje ve çözüm, oluşturur ve **Çözüm Gezgini** çeşitli dosyaları gösterir. WPF Tasarımcısı, bölünmüş bir görünüm halinde MainWindow.xaml'in XAML görünümünü ve tasarım görünümünü gösterir. Fazla veya az göstermek için Bölümlendirici slayt ya da görünümün.  Yalnızca bir görsel görünümünü veya yalnızca XAML görünümünü görmek seçebilirsiniz. (Daha fazla bilgi için bkz: [Windows Forms geliştiricileri için WPF Tasarımcısı](http://msdn.microsoft.com/47ad0909-e89b-4996-b4ac-874d929f94ca).) Aşağıdaki öğeler görünür **Çözüm Gezgini**:

![Çözüm Gezgini HelloWPFApp dosyalarla yüklenen](../ide/media/exploreide-hellowpfappfiles.png "ExploreIDE HelloWPFAppFiles")

Projeyi oluşturduktan sonra özelleştirebilirsiniz. Kullanarak **özellikleri** penceresi (bulunan **Görünüm** menüsü), görüntüleyebilir ve proje öğeleri, denetimleri ve diğer öğeler bir uygulama için seçeneklerini değiştirin.

#### <a name="to-change-the-name-of-mainwindowxaml"></a>MainWindow.xaml adını değiştirmek için
Şimdi MainWindow daha belirli bir ad verin.

1. İçinde **Çözüm Gezgini**, MainWindow.xaml seçin. Görmeniz gerekir **özellikleri** , seçerseniz yoktur ancak pencere **Görünüm** menüsünü ve sonra **Özellikler penceresini** öğesi.
2. Değişiklik **dosya adı** özelliğine `Greetings.xaml`.

     ![Özellikler penceresi vurgulanmış dosya adıyla](../ide/media/exploreide-filenameinpropertieswindow.png "ExploreIDE FilenameinPropertiesWindow")

     **Çözüm Gezgini** dosyasının adı Greetings.xaml sunulmuştur ve iç içe geçmiş kod dosyası artık Greetings.xaml.vb veya Greetings.xaml.cs adlı gösterir. Bu kod dosyası birbiriyle ilişkili yakından oldukları göstermek için .xaml dosya düğümü altında yer alıyor.

### <a name="design-the-user-interface-ui"></a>Kullanıcı arabirimini (UI) tasarlama
Bu uygulamaya üç tür denetim ekleyeceğiz: TextBlock denetimi, iki RadioButton denetimi ve bir Button denetimi.

#### <a name="to-add-a-textblock-control"></a>TextBlock denetimi eklemek için

1.  Açık **araç** seçerek penceresi **Görünüm** menü ve **araç** öğesi.

2.  İçinde **araç**, genişletin **genel WPF denetimlerinin** TextBlock denetimi görmek için düğüm.

     ![Araç kutusu vurgulanmış TextBlock denetimiyle](../ide/media/exploreide-textblocktoolbox.png "ExploreIDE TextBlockToolbox")

3.  TextBlock Denetim tasarım yüzeyine seçerek eklemek **TextBlock** öğesi ve pencereyi tasarım yüzeyine sürükleyin. Merkezi Denetim penceresinin üst yakın.

Pencereniz aşağıdaki gösterime benzemelidir:

![Tebrikler formunda TextBlock denetimi](../ide/media/exploreide-greetingswithtextblockonly.png "ExploreIDE GreetingswithTextblockonly")

XAML işaretlemesi aşağıdaki gibi görünmelidir:

```xaml
<TextBlock HorizontalAlignment="Center" TextWrapping="Wrap" VerticalAlignment="Center" RenderTransformOrigin="4.08,2.312" Margin="237,57,221,238"><Run Text="TextBlock"/><InlineUIContainer><TextBlock TextWrapping="Wrap" Text="TextBlock"/>
```

#### <a name="to-customize-the-text-in-the-text-block"></a>Metin bloğu içindeki metni özelleştirmek için

1.  XAML görünümünde TextBlock için işaretleme bulun ve metin özniteliği değiştirin:

   ```xaml
   Text="Select a message option and then choose the Display button."
   ```

2.  Gerekirse TextBlock yeniden merkezi ve tuşlarına basarak yaptığınız değişiklikleri kaydetmek **Ctrl-s** veya kullanarak **dosya** menü öğesi.

Ardından, iki ekleyeceksiniz [RadioButton](/dotnet/framework/wpf/controls/radiobutton) formu denetimleri.

#### <a name="to-add-radio-buttons"></a>Radyo düğmeleri eklemek için

1.  İçinde **araç**, bulma **RadioButton** denetim.

     ![Araç kutusu penceresinde seçili RadioButton denetimi ile](../ide/media/exploreide-radiobuttontoolbox.png "ExploreIDE RadioButtonToolbox")

2.  Tasarım iki RadioButton denetimlerini yüzey seçerek eklemek **RadioButton** öğesi ve pencereyi tasarım yüzeyine sürükleyin. (Bunları seçerek ve ok tuşlarını kullanarak) Taşı düğmeleri düğmeleri TextBlock denetimi yan yana görünmesini sağlayacak şekilde.

     Pencerenizin şuna benzemesi gerekir:

     ![Tebrikler form textblock ve iki radiobuttons](../ide/media/exploreide-greetingswithradiobuttons.png "ExploreIDE Greetingswithradiobuttons")

3.  İçinde **özellikleri** değişiklik sol RadioButton denetimi için pencere **adı** özelliği (özellik üstündeki **özellikleri** penceresi) için  **HelloButton**.

     ![RadioButton Özellikler penceresini](../ide/media/exploreide-buttonproperties.png "exploreide buttonproperties")

4.  İçinde **özellikleri** değişiklik sağ RadioButton denetimi için pencere **adı** özelliğine **GoodbyeButton**ve değişikliklerinizi kaydedin.

Artık her bir RadioButton denetimi için görüntü metni ekleyebilirsiniz. Aşağıdaki yordam güncelleştirmeleri **içerik** RadioButton denetimi özelliği.

#### <a name="to-add-display-text-for-each-radio-button"></a>Her bir radyo düğmesine görüntü metni eklemek için

1.  Tasarım yüzeyine, üzerinde HelloButton farenin sağ düğmesiyle basarak HelloButton için kısayol menüsünü açın, seçin **Metni Düzenle**ve 'Hello' girin.

2.  Açık GoodbyeButton üzerinde farenin sağ düğmesiyle basarak GoodbyeButton kısayol menüsünü seçin **Metni Düzenle**ve ardından 'Goodbye' girin.

### <a name="to-set-a-radio-button-to-be-checked-by-default"></a>Varsayılan olarak denetlenmesini radyo düğmesi ayarlamak için
Bu adımda iki radyo düğmeleri biri her zaman seçilidir böylece varsayılan olarak denetlenmesini HelloButton yaparız.

XAML görünümünde HelloButton için işaretleme bulun ve ekleme bir **Taşmalar** özniteliği:

```xaml
IsChecked="True"
```

Ekleyeceksiniz son kullanıcı Arabirimi öğesi bir [düğmesini](/dotnet/framework/wpf/controls/button) denetim.

#### <a name="to-add-the-button-control"></a>Düğme denetimini eklemek için

1.  İçinde **araç**, bulma **düğmesini** denetlemek ve ardından RadioButton denetimlerini altında tasarım yüzeyi Tasarım görünümünde form sürükleyerek ekleyin.

2.  XAML Görünümü'nde değerini değiştirme **içerik** düğmesi denetiminden için `Content="Button"` için `Content="Display"`ve değişiklikleri kaydedin.

     Biçimlendirme, aşağıdaki örneğe benzemelidir:  `<Button Content="Display" HorizontalAlignment="Left" VerticalAlignment="Top" Width="75" Margin="215,204,0,0"/>`

     Pencereniz aşağıdaki gösterime benzemelidir.

     ![Tebrikler form denetimi etiketlerle](../ide/media/exploreide-greetingswithconrollabels.png "ExploreIDE Greetingswithconrollabels")

### <a name="add-code-to-the-display-button"></a>Görüntüle Düğmesine kod ekleme
Bu uygulamayı çalıştırdığında, bir kullanıcı radyo düğmesini seçer ve ardından seçer sonra bir ileti kutusu görünür **görüntü** düğmesi. Merhaba için bir ileti kutusu ve Güle Güle için bir diğer ileti kutusu görünecektir. Bu davranış oluşturmak için Greetings.xaml.vb veya Greetings.xaml.cs Button_Click olayında için kod ekleyeceksiniz.

#### <a name="add-code-to-display-message-boxes"></a>İleti kutularını görüntülemek için kod ekleme
1.  Tasarım yüzeyine çift **görüntü** düğmesi.

     Greetings.xaml.vb veya Greetings.xaml.cs açılır ve imleç Button_Click olayının içinde olur.

    ```vb
    Private Sub Button_Click_1(sender As Object, e As RoutedEventArgs)

    End Sub
    ```
    ```csharp
    private void Button_Click_1(object sender, RoutedEventArgs e)
    {

    }
    ```

2.  Aşağıdaki kodu girin:

    ```vb
    If HelloButton.IsChecked = True Then
        MessageBox.Show("Hello.")
    ElseIf GoodbyeButton.IsChecked = True Then
        MessageBox.Show("Goodbye.")
    End If

    ```
    ```csharp
    if (HelloButton.IsChecked == true)
    {
         MessageBox.Show("Hello.");
    }
    else if (GoodbyeButton.IsChecked == true)
    {
        MessageBox.Show("Goodbye.");
    }
    ```

3.  Uygulamayı kaydedin.

##  <a name="BKMK_DebugTest"></a> Hata ayıklama ve uygulamayı test etme
Ardından, uygulama hataları aramak ve her iki ileti kutuları doğru görünmesini test etmek için hata ayıklama. Aşağıdaki yönergeler size nasıl oluşturulacağı ve hata ayıklayıcıyı başlatma, ancak daha sonra okuyabilir [WPF uygulaması (WPF) oluşturma](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf) ve [hata ayıklama WPF](../debugger/debugging-wpf.md) daha fazla bilgi için.

### <a name="find-and-fix-errors"></a>Hataları bulma ve düzeltme
Bu adımda, önceki MainWindow.xaml dosya adını değiştirerek neden hata bulabilirsiniz.

#### <a name="to-start-debugging-and-find-the-error"></a>Hata ayıklamayı başlatmak ve hatayı bulmak için

1.  Hata ayıklayıcı seçerek başlayın **hata ayıklama**, ardından **hata ayıklamayı Başlat**.

     ![Hata ayıklama menüsündeki komutu hata ayıklamayı Başlat](../ide/media/exploreide-startdebugging.png "ExploreIDE StartDebugging")

     A **kesme modu** penceresi görünür ve **çıkış** penceresi gösteren bir Ioexception oluştu: Kaynak 'mainwindow.xaml' bulunamıyor.

2.  Seçerek hata ayıklayıcıyı **hata ayıklama**, **durdurma hata ayıklama**.

     ![Hata ayıklama menüsündeki komutu hata ayıklamayı durdurun](../ide/media/exploreide-stopdebugging.png "ExploreIDE StopDebugging")

Biz MainWindow.xaml bu kılavuzda başlangıcında Greetings.xaml olarak yeniden adlandırıldı ancak proje başlatamazsınız kodu hala mainwindow.xaml için bir uygulama için URI başlangıç olarak başvuruyor.

#### <a name="to-specify-greetingsxaml-as-the-startup-uri"></a>Başlangıç URI'si olarak Greetings.xaml öğesini belirtmek için

1.  İçinde **Çözüm Gezgini**, App.xaml (C# projesinde) veya Application.xaml dosyasını (Visual Basic projesinde) açın.

2.  Değişiklik `StartupUri="MainWindow.xaml"` için `StartupUri="Greetings.xaml"`ve değişiklikleri kaydedin.

Hata ayıklayıcı yeniden Başlat (basın **F5**). Uygulamanın Greetings penceresini görmeniz gerekir. Artık hata ayıklamayı durdurmak için uygulama penceresini kapatın.

### <a name="to-debug-with-breakpoints"></a>Kesme noktaları ile hata ayıklamak için
Bazı kesme noktaları ekleyerek hata ayıklama sırasında kodu test edebilirsiniz. Seçerek kesme noktaları ekleyebilirsiniz **hata ayıklama**, **kesme**, kesmenin istediğiniz sol kenar kod satırı yanındaki düzenleyicinin tıklayarak veya basarak **F9**.

#### <a name="to-add-breakpoints"></a>Kesme noktaları eklemek için

1.  Greetings.xaml.vb veya Greetings.xaml.cs açın ve aşağıdaki satırı seçin: `MessageBox.Show("Hello.")`

2.  Bir kesme noktası menüden seçerek eklemek **hata ayıklama**, ardından **kesme**.

     ![Hata Ayıklama menüsünde kesme komutu geçiş](../ide/media/exploreide-togglebreakpoint.png "ExploreIDE ToggleBreakpoint")

     Düzenleyici penceresinin en sol kenar boşluğunda, kod satırının yanında kırmızı bir daire görünür.

3.  Aşağıdaki satırı seçin: `MessageBox.Show("Goodbye.")`.

4.  Basın **F9** bir kesme noktası eklemek için anahtar ve tuşuna basarak **F5** hata ayıklama başlatılamıyor.

5.  İçinde **Tebrikler** penceresinde, seçin **Hello** radyo düğmesine ve ardından **görüntü** düğmesi.

     Satır `MessageBox.Show("Hello.")` sarı olarak vurgulanır. IDE otomobil, Yereller ve izleme altındaki windows birlikte sol tarafında yerleştirilen ve çağrı yığını, kesme noktaları, komut, hemen ve çıktı windows birlikte sağ tarafta sabitlenir.

6.  Menü çubuğunda seçin **hata ayıklama**, **Step Out**.

     Uygulama yürütme devam eder ve "Hello" sözcüğünü içeren bir ileti kutusu görünür.

7.  Seçin **Tamam** kapatmak için ileti kutusu düğmesinde.

8.  İçinde **Tebrikler** penceresinde, seçin **güle güle** radyo düğmesine ve ardından **görüntü** düğmesi.

     Satır `MessageBox.Show("Goodbye.")` sarı olarak vurgulanır.

9. Seçin **F5** hata ayıklama devam etmek için anahtarı. İleti kutusu göründüğünde seçin **Tamam** kapatmak için ileti kutusu düğmesinde.

10. Hata ayıklamayı durdurmak için uygulama penceresini kapatın.

11. Menü çubuğunda seçin **hata ayıklama**, **devre dışı bırakmak tüm kesme noktaları**.

### <a name="build-a-release-version-of-the-application"></a>Uygulamanın yayın sürümünü oluşturma
 Her şeyi çalıştığını doğruladıktan, uygulamanın yayın derlemesi hazırlayabilirsiniz.

#### <a name="to-clean-the-solution-files-and-build-a-release-version"></a>Çözüm dosyalarını temizlemek ve yayın sürümünü oluşturmak için

1.  Ana menüde seçin **yapı**, **temiz çözüm** Ara dosyaları ve önceki yapıları sırasında oluşturulan çıkış dosyaları silmek için. Bu gerekli değildir, ancak hata ayıklama yapı çıkışları temizler.

     ![Yapı menüsünde çözümü Temizle komutunu](../ide/media/exploreide-cleansolution.png "ExploreIDE CleanSolution")

2.  HelloWPFApp yapı yapılandırmasını değiştirme **hata ayıklama** için **sürüm** (yazacaktır "Hata ayıklama" şu anda) araç çubuğundaki açılan denetimi kullanarak.

     ![Seçili sürümle standart araç](../ide/media/exploreide-releaseversion.png "ExploreIDE ReleaseVersion")

3.  Seçerek çözümü derleme **yapı**, ardından **yapı çözümü**.

     ![Build menüsünden yapı çözümü komutu](../ide/media/exploreide-buildsolution.png "ExploreIDE BuildSolution")

Tebrikler, bu izlenecek yolu tamamladınız! Çözüm ve proje dizini altında yerleşik .exe bulabilirsiniz (...\HelloWPFApp\HelloWPFApp\bin\Release\\). Daha fazla örnek keşfetmek, bkz: [Visual Studio örnekleri](../ide/visual-studio-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio 2017 yenilikler](../ide/whats-new-in-visual-studio.md)
- [Visual Studio ile Geliştirmeye Başlama](../ide/get-started-developing-with-visual-studio.md)
- [Üretkenlik İpuçları](../ide/productivity-tips-for-visual-studio.md)
