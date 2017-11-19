---
title: "İzlenecek yol: Oluşturma, düzenleme ve kodlanmış UI testi sürdürme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7c25ba7-5c9c-455b-9242-701cda56f90c
caps.latest.revision: "41"
ms.author: douge
manager: douge
ms.openlocfilehash: e7c6e2ed36593a55548ec182c147f00ae447a500
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="walkthrough-creating-editing-and-maintaining-a-coded-ui-test"></a>İzlenecek yol: Kodlanmış Bir UI Testi Oluşturmak Düzenlemek ve Sürdürmek
Bu yönergede kodlanmış UI testinin nasıl oluşturulduğunu, düzenlendiğini ve korunduğunu göstermek üzere basit bir Windows Presentation Foundation (WPF) oluşturacaksınız. İzlenecek yol çeşitli zamanlama sorunları ve yeniden düzenlemeyi denetleme tarafından kırılan testleri düzeltmeye ilişkin çözümler sağlar.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu örnek için şunlar gerekir:  
  
-   Visual Studio Enterprise  
  
### <a name="create-a-simple-wpf-application"></a>Basit WPF Uygulaması Oluşturma  
  
1.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
     **Yeni proje** iletişim kutusu görüntülenir.  
  
2.  İçinde **yüklü** bölmesini genişletin **Visual C#**ve ardından **Windows Masaüstü**.  
  
3.  Orta bölmede hedef framework aşağı açılan liste değerine ayarlandığını doğrulayın **.NET Framework 4.5**.  
  
4.  Orta bölmede seçin **WPF uygulaması** şablonu.  
  
5.  İçinde **adı** metin kutusunda, **SimpleWPFApp**.  
  
6.  Projeyi kaydetmek için bir klasör seçin. İçinde **konumu** metin kutusuna, klasörün adını yazın.  
  
7.  Seçin **Tamam**.  
  
     Visual Studio için WPF Tasarımcısı açılır ve projenin MainWindow öğesini görüntüler.  
  
8.  Araç kutusu açık değilse, açın. Seçin **Görünüm** menüsünde ve ardından **araç**.  
  
9. Altında **tüm WPF denetimleri** bölümünde, sürükleyin bir **düğmesini**, **onay kutusunu** ve **ProgressBar** tasarımında MainWindow üzerine denetimi Yüzey.  
  
10. Düğme denetimini seçin. Özellikler penceresinde değerini değiştirin **adı** özelliğinden \<No Name > button1 için. Değeri değiştirme **içerik** Başlat düğmesi özelliğine.  
  
11. ProgressBar denetimini seçin. Özellikler penceresinde değer değeri için değiştirme **adı** özelliğinden \<No Name > progressBar1 için. Değeri değiştirme **maksimum** özelliğinden **100** için **10000**.  
  
12. Onay kutusu denetimini seçin. Özellikler penceresinde değerini değiştirin **adı** özelliğinden \<No Name > checkBox1 ve Temizle **IsEnabled** özelliği.  
  
     ![Basit WPF uygulaması](../test/media/codedui_wpfapp.png "CodedUI_WPFApp")  
  
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
  
### <a name="verify-the-wpf-application-runs-correctly"></a>WPF Uygulamasının Düzgün Çalıştığını Doğrulama  
  
1.  Üzerinde **hata ayıklama** menüsünde, select **hata ayıklamayı Başlat** veya basın **F5**.  
  
2.  Onay kutusu denetimi devre dışı bırakıldığını dikkat edin. Seçin **Başlat**.  
  
     Birkaç saniye içinde ilerleme çubuğu tam %100 bitmiş olmalıdır.  
  
3.  Onay kutusu denetimi artık seçebilirsiniz.  
  
4.  SimpleWPFApp Uygulamasını Kapatın.  
  
### <a name="create-and-run-a-coded-ui-test-for-simplewpfapp"></a>SimpleWPFApp için Kodlanmış Kullanıcı Arabirimi Testi Oluşturma ve Çalıştırma  
  
1.  Daha önce oluşturduğunuz SimpleWPFApp uygulamasını bulun. Varsayılan olarak, uygulama C:\Users yer alacağı\\< kullanıcı adı\>\Documents\Visual Studio \<sürüm > \Projects\SimpleWPFApp\SimpleWPFApp\bin\Debug\SimpleWPFApp.exe  
  
2.  SimpleWPFApp uygulaması için bir masaüstü kısayolu oluşturun. SimpleWPFApp.exe sağ tıklatın ve seçin **kopya**. Masaüstünüzde sağ tıklatın ve seçin **Kısayol Yapıştır**.  
  
    > [!TIP]
    >  Uygulamaya bir kısayol eklenmesi, uygulamayı hızlıca başlatmanızı sağladığından uygulamanız açısından Kodlanmış UI testleri ekleyip değiştirmenizi kolaylaştırır.  
  
3.  Çözüm Gezgini'nde çözüme sağ tıklayın, seçin **Ekle** ve ardından **yeni proje**.  
  
     **Yeni Proje Ekle** iletişim kutusu görüntülenir.  
  
4.  İçinde **yüklü** bölmesini genişletin **Visual C#**ve ardından **Test**.  
  
5.  Orta bölmede seçin **kodlanmış UI Test projesi** şablonu.  
  
6.  Seçin **Tamam**.  
  
     Çözüm Gezgini'nde yeni kodlanmış UI test projesi adlı **CodedUITestProject1** çözümünüze eklenir.  
  
     **Kodlanmış UI testi için kodu oluştur** iletişim kutusu görüntülenir.  
  
7.  Seçin **kayıt Eylemler, UI eşlemesini düzenle veya onaylar ekleme** seçeneği ve seçin **Tamam**.  
  
     Kodlanmış UI Test derleyicisini UIMap - görünür ve Visual Studio penceresinin en aza indirilir.  
  
     İletişim kutusundaki seçenekler hakkında daha fazla bilgi için bkz: [kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate).  
  
8.  Seçin **kaydı başlatmak** üzerinde UIMap - Kodlanmış UI Test derleyicisini.  
  
     ![Kaydı başlatmak](../test/media/cuit_builder_record.png "CUIT_Builder_Record")  
  
     Gerekirse ile gelen posta dağıtılacak varsa, örneğin kayıt duraklatabilirsiniz.  
  
     ![Duraklatma](../test/media/cuit_.png "CUIT_")  
  
    > [!WARNING]
    >  Masaüstünde gerçekleştirilen tüm eylemler kaydedilir. Kayıt eklenmesini hassas verileri açabilir Eylemler gerçekleştiriyorsanız duraklatma.  
  
9. Masaüstü kısayolunu kullanarak SimpleWPFApp başlatın.  
  
     Önceki gibi onay kutusu denetimi devre dışı bırakıldığını dikkat edin.  
  
10. SimpleWPFApp üzerinde seçin **Başlat**.  
  
     Birkaç saniye içinde ilerleme çubuğu tam %100 bitmiş olmalıdır.  
  
11. Şu anda etkin onay kutusu denetimini kontrol edin.  
  
12. SimpleWPFApp uygulamasını kapatın.  
  
13. UIMap - Kodlanmış UI Test derleyicisini seçin **kodu oluştur**.  
  
14. Yöntem adı türündeki **SimpleAppTest** ve **Ekle ve Üret**. Birkaç saniye içinde Kodlanmış UI testi görünür ve Çözüm'e eklenir.  
  
15. UIMap - Kodlanmış UI Test derleyicisini kapatın.  
  
     Kod Düzenleyicisi'nde CodedUITest1.cs dosyası görüntülenir.  
  
16. Projeyi kaydedin.  
  
### <a name="run-the-coded-ui-test"></a>Kodlanmış UI Testi Çalıştırma  
  
1.  Gelen **TEST** menüsünde seçin **Windows** ve ardından **Test Gezgini**.  
  
2.  Gelen **yapı** menüsünde seçin **yapı çözümü**.  
  
3.  Codeduıtest1.cs dosyasında bulun **CodedUITestMethod** yöntemi, sağ tıklatın ve seçin **Testleri Çalıştır**, ya da Test Gezgini'nden testi çalıştırın.  
  
     Kodlanmış UI testi çalışırken, SimpleWPFApp görülebilir. Bir önceki yordamda yaptığınız adımları oluşturur. Ancak, onay kutusu denetimi onay kutusunu seçmek test çalıştığında, Test Sonuçları penceresi testin başarısız olduğunu gösterir. Bu onay kutusunu seçmek test çalışması nedeniyle ancak ilerleme çubuğu % 100 tamamlandı olana kadar onay kutusu denetimi devre dışı uyumlu değil. Bunu düzeltmek ve çeşitli kullanarak benzer sorunlar `UITestControl.WaitForControlXXX()` kullanılabilir yöntemleri kodlanmış UI testi. Sonraki yordam kullanılarak göstermek `WaitForControlEnabled()` bu testin başarısız olmasına neden olan sorunu gidermek için yöntem. Daha fazla bilgi için bkz: [yapmadan kodlanmış UI testleri beklemek için belirli olayları sırasında kayıttan yürütme](../test/making-coded-ui-tests-wait-for-specific-events-during-playback.md).  
  
### <a name="edit-and-rerun-the-coded-ui-test"></a>Kodlanmış Kullanıcı Arabirimi Testini Düzenleme ve Yeniden Çalıştırma  
  
1.  Test Gezgini penceresinde, başarısız olan test seçin ve **StackTrace** bölümünde, ilk bağlantısını seçin **UIMap.SimpleAppTest()**.  
  
2.  Kodda vurgulanan hata noktasını içeren UIMap.Designer.cs dosyası açılır:  
  
    ```csharp  
  
    // Select 'CheckBox' check box  
    uICheckBoxCheckBox.Checked = this.SimpleAppTestParams.UICheckBoxCheckBoxChecked;  
    ```  
  
3.  Bu sorunu düzeltmek için bu satırı kullanarak açın devam etmeden önce etkinleştirilmesi onay kutusu denetimi bekleyin kodlanmış UI testi yapabilirsiniz `WaitForControlEnabled()` yöntemi.  
  
    > [!WARNING]
    >  UIMap.Designer.cs dosyasını değiştirmeyin. UIMap - Kodlanmış UI Test Oluşturucusu kullanarak kodu her oluşturduğunuzda, UIMapDesigner.cs dosyasında yaptığınız herhangi bir kod değişikliğinin üzerine yazılır. Kayıtlı bir yöntemi değiştirmeniz gerekiyorsa, yöntemi UIMap.cs dosyasına kopyalayıp yeniden adlandırmanız gerekir. UIMap.cs dosyası, UIMapDesigner.cs dosyasındaki yöntemleri ve özellikleri geçersiz kılmak için kullanılabilir. Kodlanmış UITest.cs dosyasındaki orijinal yönteme başvuruyu kaldırıp yeniden adlandırılan yöntem adıyla değiştirmelisiniz.  
  
4.  Çözüm Gezgini'nde bulun **UIMap.uitest** kodlanmış UI test projenizdeki.  
  
5.  Kısayol menüsünü açın **UIMap.uitest** ve **açık**.  
  
     Kodlanmış UI testi kodlanmış UI Test Düzenleyicisi'nde görüntülenir. Şimdi, görüntüleyebilir ve kodlanmış UI testi düzenleyebilirsiniz.  
  
6.  İçinde **UI eylem** test kodu ne zaman üzerine olmayacaktır özel kod işlevselliği kolaylaştırmak için UIMap.cs veya UIMap.vb dosyasına taşımak istediğiniz test yöntemi (SimpleAppTest) yeniden derlenmesi bölmesinde seçin.  
  
7.  Seçin **taşıma kodu** kodlanmış UI Test Düzenleyicisi araç çubuğunda.  
  
8.  Microsoft Visual Studio iletişim kutusu görüntülenir. Yöntem UIMap.uitest dosyasından UIMap.cs dosyasına taşınması için ve artık kodlanmış UI Test Düzenleyicisi'ni kullanarak yöntemi düzenlemenin mümkün olmayacağı konusunda uyarır. Seçin **Evet**.  
  
     Test yöntemi UIMap.uitest dosyasından kaldırılır ve artık UI Eylemler bölmesinde görüntülenmez. Taşınan test dosyasını düzenlemek için Çözüm Gezgini'nden UIMap.cs dosyasını açın.  
  
9. Üzerinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] araç seçin **kaydetmek**.  
  
     Test yöntemi güncelleştirmeleri UIMap.Designer dosyasında kaydedilir.  
  
    > [!CAUTION]
    >  Yöntemi taşıdığınızda Kodlanmış UI Test Düzenleyicisi'ni kullanarak artık düzenleyemezsiniz. Özel kodunuzu eklemeli ve Kod Düzenleyicisi'ni kullanarak korumalısınız.  
  
10. Yönteminden yeniden adlandırma `SimpleAppTest()` için`ModifiedSimpleAppTest()`  
  
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
  
13. Codeduıtest1.cs dosyasında bulun **CodedUITestMethod** yöntemi ya da çıkışı açıklama veya SimpleAppTest() yöntemine referansı yeniden adlandırın ve yeni ModifiedSimpleAppTest() ile değiştirin:  
  
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
  
16. Bu süre kodlanmış UI testi başarılı bir şekilde test tüm adımları tamamlandıktan ve **geçti** Test Gezgini penceresinde görüntülenir.  
  
### <a name="refactor-a-control-in-the-simplewpfapp"></a>SimpleWPFApp içinde Denetimi Yeniden Düzenleme  
  
1.  MainWindow.xaml dosyasındaki Tasarımcı'da düğme denetimini seçin.  
  
2.  Özellikler penceresini üstünde değiştirmek **adı** button1 özellik değerindeki buttonA.  
  
3.  Üzerinde **yapı** menüsünde seçin **yapı çözümü**.  
  
4.  Test Gezgini içinde çalıştırma **Codeduıtestmethod1**.  
  
     Kodlanmış UI testi button1 olarak UIMap öğesinde başlangıçta eşlenen düğme denetimini konumlandıramadığından test başarısız olur. Yeniden düzenleme kodlanmış UI testlerini bu anlamda etkileyebilir.  
  
5.  Test Gezgini penceresinde içinde **StackTrace** bölümünde, ilk bağlantı seçin **UIMpa.ModifiedSimpleAppTest ()**.  
  
     UIMap.cs dosyasını açar. Hata noktası kodda vurgulanır:  
  
    ```csharp  
  
    // Click 'Start' button  
    Mouse.Click(uIStartButton, new Point(27, 10));  
    ```  
  
     Bu yordamda daha önce kod satırı kullanılarak bildirim `UiStartButton`, yeniden düzenlenmeden önce UIMap adı değil.  
  
     Sorunu düzeltmek için UIMap'e yeniden işlenmiş denetimi Kodlanmış UI Test Oluşturucusu kullanarak ekleyebilirsiniz. Sonraki yordamda gösterildiği gibi testin kodu kodu kullanacak şekilde güncelleştirebilirsiniz.  
  
### <a name="map-refactored-control-and-edit-and-rerun-the-coded-ui-test"></a>Yeniden Düzenlenmiş Denetimi Eşleme ve Kodlanmış UI Testini Düzenleme ve Yeniden Çalıştırma  
  
1.  Codeduıtest1.cs dosyasındaki içinde **Codeduıtestmethod1()** yöntemi, dosyaya sağ tıklayın, **kodlanmış UI testi için kodu oluştur** ve ardından **kullanım kodlanmış UI Test derleyicisini**.  
  
     UIMap - Kodlanmış UI Test derleyicisini görüntülenir.  
  
2.  Daha önce oluşturduğunuz masaüstü kısayolunu kullanarak, daha önce oluşturduğunuz SimpleWPFApp uygulamasını çalıştırın.  
  
3.  UIMap - Kodlanmış UI Test derleyicisini, artı aracını sürükleyin **Başlat** SimpleWPFApp düğmesinde.  
  
     **Başlat** düğmesi mavi bir kutu içine ve kodlanmış UI Test derleyicisini Seçili denetim verileri işlemek için birkaç saniye sürer ve denetimlerin özelliklerini görüntüler. Dikkat **AutomationUId** adlı **buttonA**.  
  
4.  Denetimin özelliklerinden, UI Denetim Eşlemesi'ni genişletmek için sol üst köşedeki oku seçin. Dikkat **Uıstartbutton1** seçilir.  
  
5.  Araç çubuğunda seçin **UI denetim eşlemesine denetim eklemek**.  
  
     Pencerenin altındaki durumunu görüntüleyerek eylemi doğrular **Seçili denetim UI denetim eşlemesine eklendi**.  
  
6.  UIMap - Kodlanmış UI Test derleyicisini seçin **kodu oluştur**.  
  
     Kodlanmış UI Test derleyicisini - oluşturmak kodu görünür Not yeni bir yöntem gereklidir ve kod değişiklikleri UI denetim eşlemesi için yalnızca oluşturulur gösteren bir ile.  
  
7.  Seçin **oluşturmak**.  
  
8.  SimpleWPFApp.exe uygulamasını kapatın.  
  
9. UIMap - Kodlanmış UI Test derleyicisini kapatın.  
  
     UIMap - Kodlanmış UI Test derleyicisini ermesini işlemin UI denetimi için birkaç saniye değişiklikleri eşleyin.  
  
10. Çözüm Gezgini'nde, UIMap.Designer.cs dosyasını açın.  
  
11. UIMap.Designer.cs dosyasında Uıstartbutton1 özelliği bulunamadı. Bildirim `SearchProperties` ayarlanır `"buttonA"`:  
  
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
  
12. UIMap.cs dosyasında bir oluşturucu ekleyin ve belirtin `SearchProperties` özelliği `UIStartButton` kullanmak için özelliği `AutomationID` değeriyle özelliği`"buttonA":`  
  
    ```csharp  
  
    public UIMap()  
            {  
                this.UIMainWindowWindow.UIStartButton.SearchProperties[WpfButton.PropertyNames.AutomationId] = "buttonA";  
            }  
  
    ```  
  
13. Üzerinde **yapı** menüsünde seçin **yapı çözümü**.  
  
14. Test Gezgini Codeduıtestmethod1 çalıştırın.  
  
     Bu kez, kodlanmış UI testi testteki tüm adımları başarıyla tamamlar.  Test Sonuçları penceresinde durumunu görürsünüz **geçti**.  
  
## <a name="external-resources"></a>Dış Kaynaklar  
  
### <a name="videos"></a>Videolar  
 ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo") [kodlanmış UI testleri-DeepDive-Episode1-GettingStarted](http://go.microsoft.com/fwlink/?LinkID=230573)  
  
 ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo") [kodlanmış UI testleri-DeepDive-Episode2-MaintainenceAndDebugging](http://go.microsoft.com/fwlink/?LinkID=230574)  
  
 ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo") [kodlanmış UI testleri-DeepDive-Episode3-HandCoding](http://go.microsoft.com/fwlink/?LinkID=230575)  
  
### <a name="hands-on-lab"></a>Laboratuvarda eller  
 [MSDN sanal laboratuvarı: Visual Studio 2010 ile kodlanmış UI testleri oluşturma giriş](http://go.microsoft.com/fwlink/?LinkID=22508)  
  
### <a name="faq"></a>SSS  
 [SSS - 1 kodlanmış UI testleri](http://go.microsoft.com/fwlink/?LinkID=230576)  
  
 [Kodlanmış UI testleri ile ilgili SSS -2](http://go.microsoft.com/fwlink/?LinkID=230578)  
  
### <a name="forum"></a>Forum  
 [Visual Studio UI Otomasyon (CodedUI içerir) test etme](http://go.microsoft.com/fwlink/?LinkID=224497)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kodunuzu test etmek için UI otomasyonunu kullanma](../test/use-ui-automation-to-test-your-code.md)   
 [WPF Tasarımcısı ile çalışmaya başlama](http://msdn.microsoft.com/en-us/18e61d03-b96a-4058-a166-8ec6b3f6116b)   
 [Kodlanmış UI testleri ve eylem kayıtları için desteklenen yapılandırmalar ve platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)   
 [Kodlanmış UI Test Düzenleyicisi'ni kullanarak kodlanmış UI testlerini düzenleme](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md)
