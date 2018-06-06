---
title: Visual Studio'da kodlanmış UI testi oluşturma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: fd6d3bc8dbe1ec92fd2802e6cc2b88956d74e854
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751656"
---
# <a name="walkthrough-create-edit-and-maintain-a-coded-ui-test"></a>İzlenecek yol: Oluşturma, düzenleme ve kodlanmış UI testi koru

Bu kılavuzda, oluşturmak, düzenlemek ve kodlanmış bir UI sınamak için bir Windows Presentation Framework (WPF) uygulaması korumak nasıl öğreneceksiniz. İzlenecek yol çeşitli zamanlama sorunları bozuk testleri düzeltme ve denetimleri yeniden düzenleme için çözümleri sağlar.

## <a name="create-a-wpf-app"></a>Bir WPF uygulaması oluşturma

1.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.

     **Yeni proje** iletişim kutusu görüntülenir.

2.  İçinde **yüklü** bölmesini genişletin **Visual C#** ve ardından **Windows Masaüstü**.

3.  Orta bölmede hedef framework aşağı açılan liste değerine ayarlandığını doğrulayın **.NET Framework 4.5**.

4.  Orta bölmede seçin **WPF uygulaması** şablonu.

5.  İçinde **adı** metin kutusunda, **SimpleWPFApp**.

6.  Projeyi kaydetmek için bir klasör seçin. İçinde **konumu** metin kutusuna, klasörün adını yazın.

7.  Seçin **Tamam**.

     Visual Studio için WPF Tasarımcısı açılır ve projenin MainWindow öğesini görüntüler.

8.  Araç kutusu açık değilse, açın. Seçin **Görünüm** menüsünde ve ardından **araç**.

9. Altında **tüm WPF denetimleri** bölümünde, sürükleyin bir **düğmesini**, **onay kutusunu** ve **ProgressBar** tasarımında MainWindow üzerine denetimi Yüzey.

10. Düğme denetimini seçin. Özellikler penceresinde değerini değiştirin **adı** özelliğinden \<No Name > button1 için. Değeri değiştirme **içerik** Başlat düğmesi özelliğine.

11. ProgressBar denetimini seçin. Özellikler penceresinde değerini değiştirin **adı** özelliğinden \<No Name > progressBar1 için. Değeri değiştirme **maksimum** özelliğinden **100** için **10000**.

12. Onay kutusu denetimini seçin. Özellikler penceresinde değerini değiştirin **adı** özelliğinden \<No Name > checkBox1 ve Temizle **IsEnabled** özelliği.

     ![Basit WPF uygulaması](../test/media/codedui_wpfapp.png)

13. Düğme denetimi click olay işleyicisi eklemek için çift tıklayın.

     MainWindow.xmal.cs, yeni button1_Click yönteminde imleç ile Kod Düzenleyicisi'nde görüntülenir.

14. MainWindow sınıfının en üstünde bir temsilci ekleyin. Temsilci ilerleme çubuğu için kullanılacaktır. Temsilci eklemek için aşağıdaki kodu ekleyin:

    ```csharp
    public partial class MainWindow : Window
    {
            private delegate void ProgressBarDelegate(System.Windows.DependencyProperty dp, Object value);

        public MainWindow()
        {

            InitializeComponent();
        }
    ```

15. button1_Click yöntemine aşağıdaki kodu ekleyin:

    ```csharp
    private void button1_Click(object sender, RoutedEventArgs e)
    {
        double progress = 0;

        ProgressBarDelegate updatePbDelegate =
            new ProgressBarDelegate(progressBar1.SetValue);

        do
        {
            progress ++;

            Dispatcher.Invoke(updatePbDelegate,
                System.Windows.Threading.DispatcherPriority.Background,
                new object[] { ProgressBar.ValueProperty, progress });
            progressBar1.Value = progress;
        }
        while (progressBar1.Value != progressBar1.Maximum);

        checkBox1.IsEnabled = true;
    }
    ```

16. Dosyayı kaydedin.

### <a name="run-the-wpf-app"></a>WPF uygulama çalıştırma

1.  Üzerinde **hata ayıklama** menüsünde, select **hata ayıklamayı Başlat** veya basın **F5**.

2.  Onay kutusu denetimi devre dışı bırakıldığını dikkat edin. Seçin **Başlat**.

     Birkaç saniye içinde ilerleme çubuğu tam %100 bitmiş olmalıdır.

3.  Onay kutusu denetimi artık seçebilirsiniz.

4.  SimpleWPFApp Uygulamasını Kapatın.

## <a name="create-a-shortcut-to-the-wpf-app"></a>WPF uygulamasına bir kısayol oluşturma

1.  Daha önce oluşturduğunuz SimpleWPFApp uygulamasını bulun.

2.  SimpleWPFApp uygulaması için bir masaüstü kısayolu oluşturun. Sağ *SimpleWPFApp.exe* ve **kopya**. Masaüstünüzde sağ tıklatın ve seçin **Kısayol Yapıştır**.

    > [!TIP]
    > Bir uygulamanın kısayolunu eklemek veya uygulama hızla başlamanıza izin verdiğinden, uygulamanız için kodlanmış UI testleri değiştirmek kolaylaştırır.

## <a name="create-a-coded-ui-test-for-simplewpfapp"></a>SimpleWPFApp için kodlanmış UI testi oluşturma

1. İçinde **Çözüm Gezgini**, çözüme sağ tıklayın, seçin **Ekle** ve ardından **yeni proje**.

     **Yeni Proje Ekle** iletişim kutusu görüntülenir.

1. İçinde **yüklü** bölmesini genişletin **Visual C#** ve ardından **Test**.

1. Orta bölmede seçin **kodlanmış UI Test projesi** şablonu.

   > [!NOTE]
   > Görmüyorsanız, **kodlanmış UI Test projesine** şablonu, gereken [kodlanmış UI test bileşeni](../test/use-ui-automation-to-test-your-code.md#install-the-coded-ui-test-component).

1. Seçin **Tamam**.

     Yeni kodlanmış UI test projesi adlı **CodedUITestProject1** çözümünüze eklenir.

     **Kodlanmış UI testi için kodu oluştur** iletişim kutusu görüntülenir.

1. Seçin **kayıt Eylemler, UI eşlemesini düzenle veya onaylar ekleme** seçeneği ve seçin **Tamam**.

     **UIMap - Kodlanmış UI Test derleyicisini** iletişim kutusu belirir ve Visual Studio penceresinin en aza indirilir.

     İletişim kutusundaki seçenekler hakkında daha fazla bilgi için bkz: [kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md).

1. Seçin **Başlat kaydı** üzerinde **UIMap - Kodlanmış UI Test derleyicisini** iletişim.

     ![Kaydı Başlat](../test/media/cuit_builder_record.png)

     Gerekirse ile gelen posta dağıtılacak varsa, örneğin kayıt duraklatabilirsiniz.

     ![Duraklatma](../test/media/cuit_.png)

    > [!WARNING]
    > Masaüstünde gerçekleştirilen tüm eylemler kaydedilir. Kayıt eklenmesini hassas verileri açabilir Eylemler gerçekleştiriyorsanız duraklatma.

1. Masaüstü kısayolunu kullanarak SimpleWPFApp başlatın.

     Önceki gibi onay kutusu denetimi devre dışı bırakıldığını dikkat edin.

1. SimpleWPFApp üzerinde seçin **Başlat**.

     Birkaç saniye içinde ilerleme çubuğu tam %100 bitmiş olmalıdır.

1. Şu anda etkin onay kutusu denetimini kontrol edin.

1. SimpleWPFApp uygulamasını kapatın.

1. Üzerinde **UIMap - Kodlanmış UI Test derleyicisini** iletişim kutusunda, seçin **kodu oluştur**.

1. İçinde **yöntem adı** kutusuna **SimpleAppTest** ve **Ekle ve Üret**. Birkaç saniye içinde kodlanmış UI testi görünür ve çözüme eklendi.

1. Kapat **UIMap - Kodlanmış UI Test derleyicisini**.

     *Codeduıtest1.cs* dosyası Kod Düzenleyicisi'nde görüntülenir.

1. Projeyi kaydedin.

### <a name="run-the-test"></a>Testi çalıştırma

1. Gelen **Test** menüsünde seçin **Windows** ve ardından **Test Gezgini**.

2. Gelen **yapı** menüsünde seçin **yapı çözümü**.

3. İçinde *Codeduıtest1.cs* dosya, bulun **CodedUITestMethod** yöntemi, sağ tıklatın ve seçin **Testleri Çalıştır**, ya testten **Test Gezgini**.

   Kodlanmış UI testi çalışırken, SimpleWPFApp görülebilir. Bir önceki yordamda yaptığınız adımları oluşturur. Ancak, test çalıştığında onay kutusu denetimi için onay kutusunu işaretleyin **Test sonuçları** penceresi, test başarısız olduğunu gösterir. Bu onay kutusunu seçmek test çalışması nedeniyle ancak ilerleme çubuğu % 100 tamamlandı olana kadar onay kutusu denetimi devre dışı uyumlu değil. Bunu düzeltmek ve çeşitli kullanarak benzer sorunlar `UITestControl.WaitForControlXXX()` kullanılabilir yöntemleri kodlanmış UI testi. Sonraki yordam kullanılarak göstermek `WaitForControlEnabled()` bu testin başarısız olmasına neden olan sorunu gidermek için yöntem. Daha fazla bilgi için bkz: [yapmadan kodlanmış UI testleri beklemek için belirli olayları sırasında kayıttan yürütme](../test/making-coded-ui-tests-wait-for-specific-events-during-playback.md).

## <a name="edit-and-rerun-the-coded-ui-test"></a>Düzenle ve kodlanmış UI testi yeniden çalıştırın

1.  İçinde **Test Gezgini** penceresinde, başarısız olan test seçin ve **StackTrace** bölümünde, ilk bağlantısını seçin **UIMap.SimpleAppTest()**.

2.  *UIMap.Designer.cs* dosyasını açar kodda vurgulanan hata noktasını içeren:

    ```csharp
    // Select 'CheckBox' check box
    uICheckBoxCheckBox.Checked = this.SimpleAppTestParams.UICheckBoxCheckBoxChecked;
    ```

3.  Bu sorunu düzeltmek için bu satırı kullanarak açın devam etmeden önce etkinleştirilmesi onay kutusu denetimi bekleyin kodlanmış UI testi yapabilirsiniz `WaitForControlEnabled()` yöntemi.

    > [!WARNING]
    > Değişiklik yapmayın *UIMap.Designer.cs* dosya. Kod kullanarak oluşturduğunuz her zaman üzerine yaptığınız değişiklikler herhangi bir kod **UIMap - Kodlanmış UI Test derleyicisini**. Kayıtlı bir yöntemi değiştirmeniz gerekiyorsa, kopyalayın *UIMap.cs* dosya ve yeniden adlandırın. *UIMap.cs* dosya, yöntemleri ve özellikleri geçersiz kılmak için kullanılabilir *UIMapDesigner.cs* dosya. Özgün yönteminde referansı kaldırmalısınız *CodedUITest.cs* dosya ve adlandırılan yöntem adıyla değiştirin.

4.  İçinde **Çözüm Gezgini**, bulun *UIMap.uitest* kodlanmış UI test projenizdeki.

5.  Kısayol menüsünü açın *UIMap.uitest* ve **açık**.

     Kodlanmış UI testi kodlanmış UI Test Düzenleyicisi'nde görüntülenir. Şimdi, görüntüleyebilir ve kodlanmış UI testi düzenleyebilirsiniz.

6.  İçinde **UI eylem** bölmesinde, taşımak istediğiniz test yöntemi (SimpleAppTest) seçin *UIMap.cs* veya *UIMap.vb* dosya. Yöntemi için farklı bir dosya taşıma test kodu derlenmiştir yükleyen üzerine olmaz eklenmesi özel kod sağlar.

7.  Seçin **taşıma kodu** düğmesini **kodlanmış UI Test Düzenleyicisi'ni** araç.

8.  Microsoft Visual Studio iletişim kutusu görüntülenir. Yöntem gelen taşınır sizi uyarır *UIMap.uitest* dosya *UIMap.cs* dosya ve, artık kodlanmış UI Test Düzenleyicisi'ni kullanarak yöntemini Düzenle olması. Seçin **Evet**.

     Test yöntemi kaldırılır *UIMap.uitest* dosya ve artık UI Eylemler bölmesinde görüntülenir. Taşınan test dosyasını düzenlemek için açın *UIMap.cs* dosya **Çözüm Gezgini**.

9. Visual Studio araç çubuğunda seçin **kaydetmek**.

     Test yöntemi güncelleştirmeler kaydedilir *UIMap.Designer* dosya.

    > [!WARNING]
    > Yöntemi taşıdığınızda Kodlanmış UI Test Düzenleyicisi'ni kullanarak artık düzenleyemezsiniz. Özel kodunuzu eklemeli ve Kod Düzenleyicisi'ni kullanarak korumalısınız.

10. Yönteminden yeniden adlandırma `SimpleAppTest()` için `ModifiedSimpleAppTest()`

11. Aşağıdaki kullanım deyimini dosyaya ekleyin:

    ```csharp
    using Microsoft.VisualStudio.TestTools.UITesting.WpfControls;
    ```

12. Aşağıdakileri ekleyin `WaitForControlEnabled()` yöntemi soruna neden olan kod satırı ile daha önce tanımlanan önce:

    ```csharp
    uICheckBoxCheckBox.WaitForControlEnabled();

    // Select 'CheckBox' check box
    uICheckBoxCheckBox.Checked = this.SimpleAppTestParams.UICheckBoxCheckBoxChecked;
    ```

13. İçinde *Codeduıtest1.cs* dosya, bulun **CodedUITestMethod** yöntemi ya da çıkışı açıklama veya SimpleAppTest() yöntemine referansı yeniden adlandırın ve ardından yeni değiştirin ModifiedSimpleAppTest():

    ```csharp
    [TestMethod]
            public void CodedUITestMethod1()
            {
                // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
                // For more information on generated code, see http://go.microsoft.com/fwlink/?LinkId=179463
                //this.UIMap.SimpleAppTest();
                this.UIMap.ModifiedSimpleAppTest();
            }
    ```

14. Üzerinde **yapı** menüsünde seçin **yapı çözümü**.

15. Sağ **CodedUITestMethod** yöntemi ve select **Testleri Çalıştır**.

16. Bu süre kodlanmış UI testi başarılı bir şekilde test tüm adımları tamamlandıktan ve **geçti** görüntülenen **Test Gezgini** penceresi.

## <a name="refactor-a-control-in-simplewpfapp"></a>SimpleWPFApp denetiminde yeniden Düzenle

1.  İçinde *MainWindow.xaml* dosyasını Tasarımcısı'nda düğme denetimi seçin.

2.  Üstündeki **özellikleri** penceresinde, değişiklik **adı** özellik değerinden **button1** için **buttonA**.

3.  Üzerinde **yapı** menüsünde seçin **yapı çözümü**.

4.  İçinde **Test Gezgini**, çalışma **Codeduıtestmethod1**.

     Kodlanmış UI testi button1 olarak UIMap öğesinde başlangıçta eşlenen düğme denetimini konumlandıramadığından test başarısız olur. Yeniden düzenleme kodlanmış UI testlerini bu anlamda etkileyebilir.

5.  İçinde **Test Gezgini**, **StackTrace** bölümünde, ilk bağlantı seçin **UIMpa.ModifiedSimpleAppTest ()**.

     *UIMap.cs* dosyasını açar. Hata noktası kodda vurgulanır:

    ```csharp
    // Click 'Start' button
    Mouse.Click(uIStartButton, new Point(27, 10));
    ```

     Bu yordamda daha önce kod satırı kullanılarak bildirim `UiStartButton`, yeniden düzenlenmeden önce UIMap adı değil.

     Sorunu gidermek için yeniden düzenlenmiş denetimi Uımap'a kullanarak ekleyebileceğiniz **kodlanmış UI Test derleyicisini**. Sonraki yordamda gösterildiği gibi testin kodu kodu kullanacak şekilde güncelleştirebilirsiniz.

## <a name="map-refactored-control-rerun-the-test"></a>İşlenmiş denetimini yeniden çalıştırın test eşleme

1.  İçinde *Codeduıtest1.cs* dosyasında **Codeduıtestmethod1()** yöntemi, dosyaya sağ tıklayın, **kodlanmış UI testi için kodu oluştur** ve ardından **kullanın Kodlanmış UI Test derleyicisini**.

     **UIMap - Kodlanmış UI Test derleyicisini** görüntülenir.

2.  Daha önce oluşturduğunuz masaüstü kısayolunu kullanarak, daha önce oluşturduğunuz SimpleWPFApp uygulamasını çalıştırın.

3.  Üzerinde **UIMap - Kodlanmış UI Test derleyicisini** iletişim kutusunda, artı aracını sürükleyin **Başlat** SimpleWPFApp düğmesinde.

     **Başlat** düğmesi mavi bir kutu içine alınır. **Kodlanmış UI Test derleyicisini** Seçili denetimi için verileri işlemek ve denetim özelliklerini görüntülemek için birkaç saniye sürer. Dikkat değerini **AutomationUId** olan **buttonA**.

4.  Denetimin özelliklerinden, UI Denetim Eşlemesi'ni genişletmek için sol üst köşedeki oku seçin. Dikkat **Uıstartbutton1** seçilir.

5.  Araç çubuğunda seçin **UI denetim eşlemesine denetim eklemek**.

     Pencerenin altındaki durumunu görüntüleyerek eylemi doğrular **Seçili denetim UI denetim eşlemesine eklendi**.

6.  Üzerinde **UIMap - Kodlanmış UI Test derleyicisini** iletişim kutusunda, seçin **kodu oluştur**.

     **Kodlanmış UI Test derleyicisini - kodu oluştur** bir not yeni bir yöntem gereklidir ve bu kodu değişiklikleri UI denetim eşlemesi için yalnızca oluşturulur belirten bir iletişim kutusu görüntülenir.

7.  Seçin **oluşturmak**.

8.  SimpleWPFApp Uygulamasını Kapatın.

9. Kapat **UIMap - Kodlanmış UI Test derleyicisini**.

10. İçinde **Çözüm Gezgini**, açık *UIMap.Designer.cs* dosya.

11. UIMap.Designer.cs dosyasında bulun **Uıstartbutton1** özelliği. Bildirim `SearchProperties` ayarlanır `"buttonA"`:

    ```csharp
    public WpfButton UIStartButton1
            {
                get
                {
                    if ((this.mUIStartButton1 == null))
                    {
                        this.mUIStartButton1 = new WpfButton(this);
                        #region Search Criteria
                        this.mUIStartButton1.SearchProperties[WpfButton.PropertyNames.AutomationId] = "buttonA";
                        this.mUIStartButton1.WindowTitles.Add("MainWindow");
                        #endregion
                    }
                    return this.mUIStartButton1;
                }
            }
    ```

     Şimdi yeni eşlenen denetimi kullanmak için kodlanmış kullanıcı arabirimini değiştirebilirsiniz. Önceki yordamda işaret edildiği gibi, kodlanmış UI testindeki herhangi bir yöntemi ya da özelliği geçersiz kılmak istiyorsanız, bunu UIMap.cs dosyasında yapmalısınız.

12. İçinde *UIMap.cs* dosya, bir oluşturucu ekleyin ve belirtmek `SearchProperties` özelliği `UIStartButton` kullanmak için özelliği `AutomationID` özelliği değeri ile `"buttonA":`

    ```csharp
    public UIMap()
            {
                this.UIMainWindowWindow.UIStartButton.SearchProperties[WpfButton.PropertyNames.AutomationId] = "buttonA";
            }
    ```

13. Üzerinde **yapı** menüsünde seçin **yapı çözümü**.

14. İçinde **Test Gezgini**, çalışma **Codeduıtestmethod1**.

     Bu kez, kodlanmış UI testi testteki tüm adımları başarıyla tamamlar. İçinde **Test sonuçlarını** penceresinde gördüğünüz durumunu **geçti**.

## <a name="videos"></a>Videolar

![video bağlantı](../data-tools/media/playvideo.gif) [kodlanmış UI testleri ile çalışmaya başlama](http://go.microsoft.com/fwlink/?LinkID=230573)

![video bağlantı](../data-tools/media/playvideo.gif) [, Bakım ve hata ayıklama kodlanmış UI testleri](http://go.microsoft.com/fwlink/?LinkID=230574)

![video bağlantı](../data-tools/media/playvideo.gif) [elle kodlama kodlanmış UI testleri](http://go.microsoft.com/fwlink/?LinkID=230575)

## <a name="faq"></a>SSS

[Kodlanmış UI testleri ile ilgili SSS](https://social.msdn.microsoft.com/Forums/en-US/3a74dd2c-cef8-4923-abbf-7a91f489e6c4/faqs?forum=vsautotest)

## <a name="see-also"></a>Ayrıca bkz.

- [Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](../test/use-ui-automation-to-test-your-code.md)
- [Kodlanmış UI Testleri ve Eylem Kayıtları için Desteklenen Yapılandırmalar ve Platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
- [Kodlanmış UI Test Düzenleyicisi'ni Kullanarak Kodlanmış UI Testlerini Düzenleme](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md)
