---
title: "Test Windows UWP ve 8.1 Phone uygulamalarını Visual Studio'da kodlanmış UI testleriyle | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- uwp
author: gewarren
ms.openlocfilehash: 60515eb6d7dde34562895d357a7802592c20aecb
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="test-windows-uwp-and-81-phone-apps-with-coded-ui-tests"></a>Kodlanmış UI testleriyle Windows UWP ve 8.1 Phone uygulamalarını test etme

Bu kılavuz, mobil cihaz veya Öykünücüler çalıştırılan UWP uygulamaları ve XAML tabanlı Phone 8.1 uygulamaları için UI testleri oluşturmak için kullanın.

## <a name="create-a-simple-windows-phone-app"></a>Basit bir Windows Phone uygulaması oluşturma

1.  Visual C# veya Visual Basic şablonu kullanarak boş bir Windows Phone uygulama için yeni bir proje oluşturun.

     ![Yeni bir Windows Phone uygulaması oluşturma](../test/media/cuit_phone_app_newproject.png "CUIT_Phone_App_NewProject")

2.  Çözüm Gezgini'nde MainPage.xaml açın. Araç Kutusu'ndan bir düğmeyi ve textbox denetimi tasarım yüzeyine sürükleyin.

     ![Contols eklemek için MainPage.xaml](../test/media/cuit_phone_app_addcontrols.png "CUIT_Phone_App_AddControls")

3.  Düğme denetimi özellikleri penceresinde adı.

     ![Düğme denetimi adı](../test/media/cuit_phone_namebutton.png "CUIT_Phone_NameButton")

4.  Textbox denetimi olarak adlandırın.

     ![Textbox denetimi adı](../test/media/cuit_phone_nametesxtbox.png "CUIT_Phone_NameTesxtBox")

5.  Tasarımcı yüzeyinde düğme denetimi çift tıklayın ve aşağıdaki kodu ekleyin:

    ```csharp
    private void button_Click_1(object sender, RoutedEventArgs e)
    {
        this.textBox.Text = this.button.Name;
    }

    ```

    ```vb
    Public NotInheritable Class MainPage
        Inherits Page

        Private Sub button_Click(sender As Object, e As RoutedEventArgs) Handles Button.Click
            Me.textBox.Text = Me.button.Name
        End Sub
    End Class
    ```

6.  Windows Phone uygulamanızı öykünücüde çalıştırma ve çalıştığından emin olmak için F5 tuşuna basın.

     ![Windows Phone çalıştıran uygulama](../test/media/cuit_phone_runapp.png "CUIt_Phone_RunApp")

7.  Öykünücü çıkın.

## <a name="deploy-the-windows-phone-app"></a>Windows Phone dağıtmak uygulama

1.  Kodlanmış UI testi bir uygulamanın denetimleri eşleyebilirsiniz önce uygulamayı dağıtma gerekir.

     ![Windows Phone dağıtmak uygulama](../test/media/cuit_phone_deploy.png "CUIT_Phone_Deploy")

     Öykünücü başlatır. Uygulamayı test etmek için kullanıma sunulmuştur.

     ![Öykünücüsünde dağıtılan uygulama](../test/media/cuit_phone_deployed.png "CUIT_Phone_Deployed")

     Kodlanmış UI testi oluştururken çalıştıran öykünücüsü tutun.

## <a name="create-a-coded-ui-test-for-the-windows-phone-app"></a>Windows Phone uygulama için kodlanmış UI testi oluşturma

[Kodlanmış UI testleri Evrensel Windows Platformu (UWP) uygulamaları için nasıl oluşturulur?](#uwpapps)

1.  Windows Phone Uygulama çözüme yeni bir kodlanmış UI test projesi ekleyin.

     ![Windows Phone için yeni kodlanmış UI testi oluşturmak](../test/media/cuit_phone_newproject.png "CUIT_Phone_NewProject")

2.  Çapraz hedef aracını kullanarak UI eşlemesini düzenlemek bu seçeneği seçin.

     ![Kodlanmış UI test çapraz şunu kullanarak Oluştur&#45;artı aracı. ] (../test/media/cuit_phone_howgencodedialog.png "CUIT_Phone_HowGenCodeDialog")

3.  Uygulama seçmek için artı şeklindeki aracını kullanın, sonra uygulamanın değerini kopyalayın **Automationıd** daha sonra testinde uygulamayı başlatmak için kullanılan özellik.

     ![Uygulamanın Automationıd değerini kopyalayın](../test/media/cuit_phone_getautomationid.png "CUIT_Phone_GetAutomationId")

4.  Öykünücü uygulamayı başlatın ve düğme denetimi seçmek için artı şeklindeki aracını kullanın. Ardından düğme denetimi UI denetim eşlemesine ekleyin.

     ![Çapraz kullanmak&#45;denetimleri eşlemek için artı aracı](../test/media/cuit_phone_mapbuttoncontrol.png "CUIT_Phone_MapButtonControl")

5.  Textbox denetimi UI denetim eşlemesine eklemek için önceki adımı yineleyin.

     ![Çapraz kullanmak&#45;artı aracı ve harita textbox denetimi](../test/media/cuit_phone_maptextboxcontrol.png "CUIT_Phone_MapTextBoxControl")

6.  UI denetim eşlemesi değişiklikler için kod oluşturmak için kod oluşturur.

     ![Kod Oluşturucu Oluşturma](../test/media/cuit_phone_generatecode.png "CUIT_Phone_GenerateCode")

7.  Textbox denetimi seçin ve ardından artı şeklindeki aracını kullanın **metin** özelliği.

     ![Metin özelliği seçin](../test/media/cuit_phone_textproperty.png "CUIT_Phone_TextProperty")

8.  Bir onaylama ekleyin. Bu testte değerin doğru olduğunu doğrulamak için kullanılır.

     ![Onaylama işlemi test eklemek](../test/media/cuit_phone_addassertion.png "CUIT_Phone_AddAssertion")

9. Ekleyin ve assert yöntemi için kod oluşturur.

     ![Onaylama işlemi kodunu oluşturmak](../test/media/cuit_phone_generatecodeassertion.png "CUIT_Phone_GenerateCodeAssertion")

10. **Visual C#**

     Çözüm Gezgini'nde assert yöntemini ve denetimler için yeni eklenen kodu görmek için UIMap.Designer.cs dosyasını açın.

     **Visual Basic**

     Çözüm Gezgini'nde CodedUITest1.vb dosyasını açın. Codeduıtestmethod1() test yöntemi kodu, otomatik olarak eklenen onay yöntemi çağrısı sağ `Me.UIMap.AssertMethod1()` ve **Tanıma Git**. Assert yöntemini ve denetimler için eklenen kod görüntüleyebilmeniz Bu kod düzenleyicisinde UIMap.Designer.vb dosyasını açar.

    > [!WARNING]
    > UIMap.Designer.cs veya UIMap.Designer.vb dosyasını doğrudan değiştirmeyin. Bunu yaparsanız, değişiklikleri dosyaya test üretilen her zaman üzerine yazılır.

     **Assert yöntemi**

    ```csharp
    public void AssertMethod1()
    {
        #region Variable Declarations
        XamlEdit uITextBoxEdit = this.UIApp1Window.UITextBoxEdit;
        #endregion

        // Verify that the 'Text' property of 'textBox' text box equals 'button'
        Assert.AreEqual(this.AssertMethod1ExpectedValues.UITextBoxEditText, uITextBoxEdit.Text);
    }
    ```

    ```vb
    Public Sub AssertMethod1()
        Dim uITextBoxEdit As XamlEdit = Me.UIApp1Window.UITextBoxEdit

        'Verify that the 'Text' property of 'textBox' text box equals 'button'
        Assert.AreEqual(Me.AssertMethod1ExpectedValues.UITextBoxEditText, uITextBoxEdit.Text)
    End Sub
    ```

     **Denetimler**

    ```csharp
    #region Properties
    public virtual AssertMethod1ExpectedValues AssertMethod1ExpectedValues
    {
        get
        {
            if ((this.mAssertMethod1ExpectedValues == null))
            {
                this.mAssertMethod1ExpectedValues = new AssertMethod1ExpectedValues();
            }
            return this.mAssertMethod1ExpectedValues;
        }
    }

    public UIApp1Window UIApp1Window
    {
        get
        {
            if ((this.mUIApp1Window == null))
            {
                this.mUIApp1Window = new UIApp1Window();
            }
            return this.mUIApp1Window;
        }
    }
    #endregion

    #region Fields
    private AssertMethod1ExpectedValues mAssertMethod1ExpectedValues;

    private UIApp1Window mUIApp1Window;
    #endregion
    ```

    ```vb
    #Region "Properties"
    Public ReadOnly Property UIButtonButton() As XamlButton
        Get
            If (Me.mUIButtonButton Is Nothing) Then
                Me.mUIButtonButton = New XamlButton(Me)
                Me.mUIButtonButton.SearchProperties(XamlButton.PropertyNames.AutomationId) = "button"
            End If
            Return Me.mUIButtonButton
        End Get
    End Property

    Public ReadOnly Property UITextBoxEdit() As XamlEdit
        Get
            If (Me.mUITextBoxEdit Is Nothing) Then
                Me.mUITextBoxEdit = New XamlEdit(Me)
                Me.mUITextBoxEdit.SearchProperties(XamlEdit.PropertyNames.AutomationId) = "textBox"
            End If
            Return Me.mUITextBoxEdit
        End Get
    End Property
    #End Region

    #Region "Fields"
    Private mUIButtonButton As XamlButton

    Private mUITextBoxEdit As XamlEdit
    #End Region
    ```

11. Çözüm Gezgini'nde Codeduıtest1.cs veya CodedUITest1.vb dosyasını açın. Test çalışması için gerekli eylemleri CodedUTTestMethod1 yöntemi için kod artık ekleyebilirsiniz. Kod eklemek için Uımap'a eklenen denetimleri kullanın:

    1.  Daha önce kopyaladığınız panoya Otomasyon kimliği özelliğini kullanarak Windows Phone uygulamasını başlatın:

        ```csharp
        XamlWindow myAppWindow = XamlWindow.Launch("ed85f6ff-2fd1-4ec5-9eef-696026c3fa7b_cyrqexqw8cc7c!App");
        ```

        ```vb
        XamlWindow.Launch("ed85f6ff-2fd1-4ec5-9eef-696026c3fa7b_cyrqexqw8cc7c!App");
        ```

    2.  Düğme denetimi dokunmak hareketi ekleyin:

        ```csharp
        Gesture.Tap(this.UIMap.UIApp1Window.UIButtonButton);
        ```

        ```vb
        Gesture.Tap(Me.UIMap.UIApp1Window.UIButtonButton)
        ```

    3.  Uygulama başlatıldıktan sonra otomatik olarak oluşturulan assert yöntemi çağrısı geldiğini doğrulamak ve hareketi düğmesine dokunun:

        ```csharp
        this.UIMap.AssertMethod1();
        ```

        ```vb
        Me.UIMap.AssertMethod1()
        ```

     Kod eklendikten sonra Codeduıtestmethod1 test yöntemi aşağıdaki gibi görünmelidir:

    ```csharp
    [TestMethod]
    public void CodedUITestMethod1()
    {
        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.

        // Launch the app.
        XamlWindow myAppWindow = XamlWindow.Launch("ed85f6ff-2fd1-4ec5-9eef-696026c3fa7b_cyrqexqw8cc7c!App");

        // Tap the button.
        Gesture.Tap(this.UIMap.UIApp1Window.UIButtonButton);

        this.UIMap.AssertMethod1();
    }
    ```

    ```vb
    <CodedUITest>
    Public Class CodedUITest1

        <TestMethod()>
        Public Sub CodedUITestMethod1()
            '
            ' To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
            '
            ' Launch the app.
            XamlWindow.Launch("ed85f6ff-2fd1-4ec5-9eef-696026c3fa7b_cyrqexqw8cc7c!App")

            '// Tap the button.
            Gesture.Tap(Me.UIMap.UIApp1Window.UIButtonButton)

            Me.UIMap.AssertMethod1()
        End Sub
    ```

## <a name="run-the-coded-ui-test"></a>Kodlanmış UI testi çalıştırma

1.  Test yapı ve test Gezgini kullanarak testi çalıştırın.

     ![Derleme ve Test Gezgini'ni kullanarak test çalıştırma](../test/media/cuit_phone_runtestexplorer.png "CUIT_Phone_RunTestExplorer")

     Windows Phone uygulamasını başlatır, eylem düğmesi tamamlandı dokunun ve özellik doldurulur ve assert yöntemi kullanılarak doğrulandı textbox's metin.

     ![Çalışan Windows Phone test](../test/media/cuit_phone_runtestexplorerrunning.png "CUIT_Phone_RunTestExplorerRunning")

     Test tamamlandıktan sonra test Gezgini testini geçtiğini onaylar.

     ![Test Gezgini sonuçları](../test/media/cuit_phone_runtestexplorerresults.png "CUIT_Phone_RunTestExplorerResults")

##  <a name="TestingPhoneAppsCodedUI_DataDriven"></a> Kullanım veri tabanlı kodlanmış UI testleri Windows Phone uygulamalarını
 Farklı koşullarda test etmek için kodlanmış UI testi birden çok kez farklı veri kümeleriyle çalıştırılabilir.

 Windows Phone için veri tabanlı kodlanmış UI testleri, bir test yöntemi DataRow özniteliği kullanılarak tanımlanır. Aşağıdaki örnek, x ve y değerleri 1 ve 2 ilk yinelemeyi ve -1 -2 testinin ikinci yineleme için için kullanın.

```
[DataRow(1, 2, DisplayName = "Add positive numbers")]
[DataRow(-1, -2, DisplayName = "Add negative numbers")]
[TestMethod]
public void DataDrivingDemo_MyTestMethod(int x, int y)

```

## <a name="q--a"></a>Soru - Yanıt

### <a name="q-do-i-have-to-deploy-the-windows-phone-app-in-the-emulator-in-order-to-map-ui-controls"></a>S: kullanıcı Arabirimi denetimlerini eşlemek için öykünücüsü Windows Phone Uygulama dağıtmak sahip?
 **A**: Evet, bir öykünücü çalışıyor olmalıdır ve uygulama için dağıtılacağını kodlanmış UI test derleyicisini gerektirir. Aksi takdirde, hiçbir çalışan öykünücünüze bulunamadı belirten bir hata iletisi durum oluşturur.

###  <a name="TestingPhoneAppsCodedUI_EmulatorDevice"></a> S: testleri yalnızca öykünücüsünde yürütülebilir ya da fiziksel bir aygıtı kullanabilir miyim?
 **A**: her iki seçenek desteklenir. Test yürütmesi için hedef öykünücüsü türünü değiştirme veya aygıt aygıt araç çubuğunda seçerek seçilir. Cihaz seçiliyse, telefon mavi aygıt makinenin USB bağlantı noktalarından birine bağlı olması gerekir.

 ![Öykünücü sürümü veya physcial aygıtı seçin](../test/media/cuit_phone_testtarget.png "CUIT_Phone_TestTarget")

### <a name="q-why-dont-i-see-the-option-to-record-my-coded-ui-test-in-the-generate-code-for-a-coded-ui-test-dialog"></a>Kodlanmış UI testi iletişim oluşturmak kodunda my kodlanmış UI testini kaydetme seçeneği neden göremiyorum?
 **A**: kaydetme seçeneği, Windows Phone uygulamaları için desteklenmiyor.

### <a name="q-can-i-create-a-coded-ui-test-for-my-windows-phone-apps-based-on-winjs-silverlight-or-html5"></a>S: kodlanmış UI testi WinJS, Silverlight veya HTML5 göre my Windows Phone uygulamaları için oluşturabilirim?
 **A**: Hayır, yalnızca temel XAML uygulamaları desteklenmez.

### <a name="q-can-i-create-coded-ui-tests-for-my-windows-phone-apps-on-a-system-that-is-not-running-windows-81-or-windows-10"></a>S: kodlanmış UI testleri için Windows Phone uygulamalarım Windows 8.1 veya Windows 10 çalıştırmayan bir sistemde oluşturabilirim?
 **A**: Hayır, kodlanmış UI Test proje şablonları yalnızca Windows 8.1 ve Windows 10 kullanılabilir. Otomasyon için evrensel Windows Platformu (UWP) uygulamaları oluşturmak için Windows 10 gerekir.

<a name="uwpapps"></a>
### <a name="q-how-do-i-create-coded-ui-tests-for-universal-windows-platform-uwp-apps"></a>S: Evrensel Windows Platformu (UWP) uygulamaları için kodlanmış UI testleri nasıl oluşturulur?
 **A**: Burada test UWP uygulamanızı platformuna bağlı olarak kodlanmış UI test projesi şu yollardan biriyle oluşturun:

-   Yerel makine üzerinde çalışan bir UWP uygulaması bir UWP uygulaması gibi çalışır. Bu test için kullanmanız gerekir **kodlanmış UI Test projesine (Windows)** şablonu. Yeni bir proje oluşturduğunuzda, bu şablonu bulmak için Git **Windows**, **Evrensel** düğümü. Veya gitmek **Windows**, **Windows 8**, **Windows** düğümü.

-   Mobil cihaz veya öykünücü üzerinde çalışan bir UWP uygulaması bir telefon uygulaması gibi çalışır. Bu test için kullanmanız gerekir **kodlanmış UI Test projesine (Windows Phone)** şablonu. Yeni bir proje oluşturduğunuzda, bu şablonu bulmak için Git **Windows**, **Evrensel** düğümü. Veya gitmek **Windows**, **Windows 8**, **Windows Phone** düğümü.

 Projesi oluşturduktan sonra bir test yazma önceki ile aynı kalır.

### <a name="q-can-i-select-controls-that-are-outside-the-emulator"></a>S: öykünücü dışında denetimleri seçin?
 **A**: Hayır, oluşturucu bunları algılamaz.

### <a name="q-can-i-use-the-coded-ui-test-builder-to-map-controls-using-a-physical-phone-device"></a>S: kodlanmış UI test derleyicisini kullanarak fiziksel telefon cihaz denetimleri eşlemek için kullanabilir miyim?
 **A**: uygulamanızı öykünücü dağıttıysanız Hayır, oluşturucu yalnızca kullanıcı Arabirimi öğeleri eşleyebilirsiniz.

### <a name="q-why-cant-i-modify-the-code-in-the-uimapdesigner-file"></a>S: neden UIMap.Designer dosyasındaki kodu değiştirilemez?
 **A**: UIMap - Kodlanmış UI Test derleyicisini kullanarak kod oluşturma her zaman UIMapDesigner.cs dosyasında yaptığınız herhangi bir kod değişikliğinin üzerine yazılır. Kayıtlı bir yöntemi değiştirmeniz gerekiyorsa, yöntemi UIMap.cs dosyasına kopyalayıp yeniden adlandırmanız gerekir. UIMap.cs dosyası, UIMapDesigner.cs dosyasındaki yöntemleri ve özellikleri geçersiz kılmak için kullanılabilir. Kodlanmış UITest.cs dosyasındaki orijinal yönteme başvuruyu kaldırıp yeniden adlandırılan yöntem adıyla değiştirmelisiniz.

### <a name="q-can-i-run-a-coded-ui-test-on-my-windows-phone-app-from-the-command-line"></a>S: kodlanmış UI testi Windows Phone Uygulamam komut satırından çalıştırabilirim?
 **A**: Evet, runsettings dosya hedef cihaz test yürütmesi için belirtmek için kullanın. Örneğin:

 **vstest.Console.exe "pathToYourCodedUITestDll" /settings:devicetarget.runsettings**

 Örnek runsettings dosyası:

```
<?xml version="1.0" encoding="utf-8"?>
<RunSettings>
<MSPhoneTest>
<!--to specify test execution on device, use a TargetDevice option as follows-->
<TargetDevice>Device</TargetDevice>
<!--to specify an emulator instead, use a TargetDevice option like below-->
<!--<TargetDevice>Emulator 8.1 WVGA 4 inch 512MB</TargetDevice>-->
</MSPhoneTest>
</RunSettings>
```

### <a name="q-what-are-the-differences-between-coded-ui-tests-for-xaml-based-uwp-apps-and-windows-phone-apps"></a>S: XAML tabanlı UWP uygulamalar için kodlanmış UI testleri ve Windows Phone uygulamaları arasındaki farklar nelerdir?
 **A**: bazı temel farklılıklar şunlardır:

|Özellik|UWP uygulamaları|Windows Phone uygulamaları|
|-------------|------------------------|------------------------|
|Testleri çalıştırmak için hedef|Yerel veya uzak bilgisayar. Testleri çalıştırmak için otomatikleştirilmiş bir test çalışması kullandığınızda, uzak bilgisayarlara belirtilebilir.|Öykünücü veya aygıt. Bakın, [s: testleri yalnızca öykünücü üzerinde çalıştırılabilir ya da fiziksel bir aygıtı kullanabilir miyim?](#TestingPhoneAppsCodedUI_EmulatorDevice) bu konuda.|
|Komut satırından yürütme|Ayarlar dosyası hedef belirtmek için gerekli değildir.|Runsettings dosyası hedef belirtmek için gereklidir.|
|Kabuk denetimleri için özelleştirilmiş sınıfları|<xref:Microsoft.VisualStudio.TestTools.UITesting.DirectUIControls.DirectUIControl>|<xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl>|
|XAML uygulama WebView denetiminde|Html * kullanırsanız desteklenen özelleştirilmiş HTML öğeleri ile etkileşim kurmak için sınıflar. Bkz: <xref:Microsoft.VisualStudio.TestTools.UITesting.HtmlControls>.|Desteklenmez.|
|MTM otomatikleştirilmiş testleri yürütün|Desteklenen.|Desteklenmez.|
|Veri temelli testleri|Bkz: [verilere testleri](../test/creating-a-data-driven-coded-ui-test.md) dış veri kaynakları kullanarak ve veri kaynağı kullanma hakkında bilgi için bir test yöntemi özniteliği.|Bir test yöntemi DataRow özniteliğini kullanarak belirtilen satır içi verilerdir. Bkz: [kullanım veri tabanlı kodlanmış UI testleri Windows Phone uygulamalarını](#TestingPhoneAppsCodedUI_DataDriven) bu konuda.|

 UWP uygulamalar için kodlanmış UI testleri hakkında daha fazla bilgi için bkz: [kodlanmış UI testleri ile Test Windows UWP uygulamaları](../test/test-windows-store-8-1-apps-with-coded-ui-tests.md).

## <a name="external-resources"></a>Dış kaynaklar
 Microsoft Visual Studio uygulama yaşam döngüsü yönetimi blog: [XAML tabanlı Windows Phone uygulamaları test etmek için kodlanmış UI kullanarak](http://blogs.msdn.com/b/visualstudioalm/archive/2014/04/05/using-coded-ui-to-test-xaml-based-windows-phone-apps.aspx?PageIndex=2#comments)

## <a name="see-also"></a>Ayrıca bkz.

- [Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](../test/use-ui-automation-to-test-your-code.md)
