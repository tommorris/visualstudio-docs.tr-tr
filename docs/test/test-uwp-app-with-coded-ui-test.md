---
title: Bir UWP uygulaması ile kodlanmış bir UI testi test etme
ms.date: 05/31/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- uwp
ms.openlocfilehash: 081c61cb0d5a2db28b04ebdd12fd53713b41363f
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34694121"
---
# <a name="create-a-coded-ui-test-to-test-a-uwp-app"></a>Kodlanmış UI sınamak için bir UWP uygulaması oluşturma

Bu makalede, bir evrensel Windows Platformu (UWP) uygulaması için kodlanmış UI testi oluşturma açıklanmaktadır.

## <a name="create-a-uwp-app-to-test"></a>Test etmek için bir UWP uygulaması oluşturma

İlk adım sınaması çalıştırmak için basit bir UWP uygulaması oluşturmaktır.

1. Visual Studio'da kullanarak yeni bir proje oluşturma **boş uygulama (Evrensel Windows)** Visual C# veya Visual Basic için şablon.

     ![Boş uygulama Evrensel Windows şablonu](../test/media/blank-uwp-app-template.png)

1. İçinde **yeni evrensel Windows platformu projesi** iletişim kutusunda **Tamam** varsayılan platform sürümleri kabul etmek için.

1. Gelen **Çözüm Gezgini**, açık *MainPage.xaml*.

   Dosya açılır **XAML Tasarımcısı**.

1. Düğme denetimi ve bir textbox denetimi sürükleyin **araç** tasarım yüzeyine.

     ![UWP uygulaması tasarlama](../test/media/toolbox-controls.png)

1. Denetimlere adlar verin. Textbox denetimi seçin ve ardından **özellikleri** penceresinde girin **textBox** içinde **adı** alan. Düğme denetimi seçin ve ardından **özellikleri** penceresinde girin **düğmesini** içinde **adı** alan.

1. Düğme denetimi çift tıklayın ve gövdesi için aşağıdaki kodu ekleyin `Button_Click` yöntemi. Bu kod metni metin kutusuna yalnızca bize kodlanmış UI testi daha sonra oluşturacağız doğrulamak için bir şey vermek için düğme denetiminin adı için yalnızca ayarlar.

   ```csharp
   this.textBox.Text = this.button.Name;
   ```

   ```vb
   Me.textBox.Text = Me.button.Name
   ```

1. Tuşuna **Ctrl**+**F5** uygulamayı çalıştırmak için. Aşağıdakine benzer bir şey görmeniz gerekir:

   ![UWP uygulama düğmesi ve metin kutusu](media/uwp-app.png)

## <a name="create-a-coded-ui-test"></a>Kodlanmış UI testi oluşturma

1. Bir test projesi çözüme eklemek için çözüme sağ tıklayın **Çözüm Gezgini** ve **Ekle** > **yeni proje**.

1. İçinde **yeni proje** iletişim kutusunda **kodlanmış UI Test projesi (Evrensel Windows)** şablonu. Şablon altında bulabilirsiniz **Windows Evrensel** kategorisi altında **Visual C#** veya **Visual Basic**.

     ![Yeni kodlanmış UI test projesi](../test/media/coded-ui-test-project-uwp-template.png)

   > [!NOTE]
   > Görmüyorsanız, **kodlanmış UI Test projesine (Evrensel Windows)** şablonu, gereken [kodlanmış UI test bileşeni](../test/use-ui-automation-to-test-your-code.md#install-the-coded-ui-test-component).

1. İçinde **kodlanmış UI testi için kod üret** iletişim kutusunda **el ile testi düzenleme**.

     ![Kodlanmış UI test iletişim kutusu için kod oluşturma](../test/media/manually-edit-the-test.png)

1. UWP uygulamanızı zaten çalışmıyorsa başlatın tuşlarına basarak **Ctrl**+**F5**.

1. Açık **kodlanmış UI Test derleyicisini** imleci yerleştirerek iletişim `CodedUITestMethod1` yöntemi ve ardından seçme **Test** > **kodlanmış UI testiiçinkoduoluştur**  >  **Kullanım kodlanmış UI Test derleyicisini**.

1. Denetimler için kullanıcı Arabirimi denetim eşlemesi ekleyin. Kullanım **kodlanmış UI Test derleyicisini** artı şeklindeki aracı UWP uygulamasında düğme denetimi seçin. İçinde **eklemek onaylar** iletişim kutusunda, genişletin **UI denetim eşlemesi** bölmesinde gerekli ve ardından **UI denetim eşlemesine denetim eklemek**.

     ![UI eşlemesine denetim ekleme](../test/media/add-control-to-ui-control-map.png)

1. Textbox denetimi UI denetim eşlemesine eklemek için önceki adımı yineleyin.

1. İçinde **kodlanmış UI Test derleyicisini** iletişim kutusunda **kodu oluştur** veya basın **Ctrl**+**G**. Ardından **Generate** değişiklikler UI denetim eşlemesi için kod oluşturmak için.

     ![UI eşlemesi için kod oluşturma](../test/media/generate-code-dialog.png)

1. Metin olarak değiştiğini doğrulamak için **düğmesini** düğmesine tıklandığında düğmesini tıklatın.

     ![Düğme denetimi TextBox değeri ayarlamak için tıklayın](../test/media/uwp-app-button-textbox.png)

1. Textbox denetiminde metni doğrulamak için onayı ifade ekleyin. Textbox denetimi seçin ve ardından artı şeklindeki aracını kullanın **metin** özelliğinde **eklemek onaylar** iletişim. Ardından, seçin **onay Ekle** veya basın **Alt**+**A**. İçinde **onaylama hatası iletisi** kutusuna **Textbox değeri olması beklenmiyor.** ve ardından **Tamam**.

     ![Çapraz hedef kutusuyla seçin ve onaylama ekleyin](../test/media/add-assertion-for-text.png)

1. Onaylama işlemi için test kodu oluşturur. İçinde **kodlanmış UI Test derleyicisini** iletişim kutusunda **kodu oluştur**. İçinde **kodu oluştur** iletişim kutusunda **Ekle ve Üret**.

     ![Textbox onaylama için kod oluşturma](../test/media/add-and-generate-assert-method.png)

   İçinde **Çözüm Gezgini**, açık *UIMap.Designer.cs* assert yöntemini ve denetimler için eklenen kod görüntülemek için.

   > [!TIP]
   > Visual Basic kullanıyorsanız, açık *CodedUITest1.vb*. Ardından `CodedUITestMethod1()` assert yöntemini çağrısı sağ tıklayın, test yöntemi kodu `Me.UIMap.AssertMethod1()` ve **Tanıma Git**. *UIMap.Designer.vb* kod düzenleyicisini ve açılır assert yöntemini ve denetimler için eklenen kod görüntüleyebilirsiniz.

    > [!WARNING]
    > Değişiklik yapmayın *UIMap.Designer.cs* veya *UIMap.Designer.vb* doğrudan dosyaları. Bunu yaparsanız, test oluşturulduğunda, değişikliklerin üzerine yazılır.

    Assert yöntemini şöyle görünür:

    ```csharp
    public void AssertMethod1()
    {
        #region Variable Declarations
        XamlEdit uITextBoxEdit = this.UIUWPAppWindow.UITextBoxEdit;
        #endregion

        // Verify that the 'Text' property of 'textBox' text box equals 'button'
        Assert.AreEqual(this.AssertMethod1ExpectedValues.UITextBoxEditText, uITextBoxEdit.Text, "Textbox value is unexpected.");
    }
    ```

    ```vb
    Public Sub AssertMethod1()
        Dim uITextBoxEdit As XamlEdit = Me.UIApp2Window.UITextBoxEdit

        'Verify that the 'Text' property of 'textBox' text box equals 'button'
        Assert.AreEqual(Me.AssertMethod1ExpectedValues.UITextBoxEditText, uITextBoxEdit.Text, "Textbox value is unexpected.")
    End Sub
    ```
1. Ardından, elde etmek ihtiyacımız **Automationıd** UWP, [uygulama](#create-a-simple-universal-windows-app) , test etmek istiyoruz. Açık pencereleri **Başlat** menü bölme uygulama için bkz. Ardından, artı şeklindeki aracı sürükleyin ![hedef simgesini](media/target-icon.png) gelen **kodlanmış UI Test derleyicisini** döşemenin uygulamanız için iletişim kutusuna. Mavi bir kutu döşeme çevreleyen, farenizi serbest bırakın.

   ![Çapraz hedef aracı](media/cross-hair-tool.png)

   **Eklemek onaylar** iletişim kutusu açılır ve görüntüler **Automationıd** uygulamanız için. Sağ **Automationıd** ve **Panoya Kopyala değeri**.

   ![Automationıd onay Ekle iletişim kutusunda](../test/media/automation-id.png)

1. Kodu UWP uygulamasını başlatmak için test yöntemine ekleyin. İçinde **Çözüm Gezgini**, açık *Codeduıtest1.cs* veya *CodedUITest1.vb*. Çağrı yukarıda `AssertMethod1`, UWP uygulamasını başlatmak için kodu ekleyin:

   ```csharp
   XamlWindow.Launch("af5ecd75-f252-45a1-9e7e-c6f1d8f054ff_0q1pp7qrjexbp!App")
   ```

   ```vb
   XamlWindow myAppWindow = XamlWindow.Launch("af5ecd75-f252-45a1-9e7e-c6f1d8f054ff_0q1pp7qrjexbp!App");
   ```

   Örnek kod Otomasyon Kimliğinde panoya önceki adımda kopyaladığınız değeri değiştirin.

   > [!IMPORTANT]
   > Karakter gibi kaldırmak için Otomasyon kimliği başlangıcını kırpma **P ~**. Bu karakterleri kırpma yok, test döndürürse bir `Microsoft.VisualStudio.TestTools.UITest.Extension.PlaybackFailureException` zaman çalışır uygulamayı başlatmak.

1. Ardından, kod düğmesini tıklatarak test yöntemine ekleyin. Sonra satırındaki `XamlWindow.Launch`, düğme denetimi dokunmak hareketi ekleyin:

   ```csharp
   Gesture.Tap(this.UIMap.UIUWPAppWindow.UIButtonButton);
   ```

   ```vb
   Gesture.Tap(Me.UIMap.UIUWPAppWindow.UIButtonButton)
   ```

   Tam kod ekledikten sonra `CodedUITestMethod1` test yöntemi aşağıdaki gibi görünmelidir:

   ```csharp
   [TestMethod]
   public void CodedUITestMethod1()
   {
       XamlWindow.Launch("af5ecd75-f252-45a1-9e7e-c6f1d8f054ff_0q1pp7qrjexbp!App");

       Gesture.Tap(this.UIMap.UIUWPAppWindow.UIButtonButton);

       // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
       this.UIMap.AssertMethod1();
   }
   ```

   ```vb
   <CodedUITest(CodedUITestType.WindowsStore)>
   Public Class CodedUITest1

       <TestMethod()>
       Public Sub CodedUITestMethod1()

           ' Launch the app.
           XamlWindow.Launch("af5ecd75-f252-45a1-9e7e-c6f1d8f054ff_0q1pp7qrjexbp!App")

           '// Tap the button.
           Gesture.Tap(Me.UIMap.UIUWPAppWindow.UIButtonButton)

           Me.UIMap.AssertMethod1()
       End Sub
   ```

1. Test projeyi oluşturun ve sonra açmak **Test Gezgini** seçerek **Test** > **Windows** > **Test Gezgini**.

1. Seçin **tümünü Çalıştır** testi çalıştırmak için.

   Uygulama açar, düğme dokunduğunuz ve textbox's **metin** özelliği doldurulur. Assert yöntemini textbox's doğrular **metin** özelliği.

   Test tamamlandıktan sonra **Test Gezgini** test geçirilen görüntüler.

   ![Geçirilen test Test Gezgini'nde görüntüler](../test/media/test-explorer-coded-ui-test-passed.png)

## <a name="q--a"></a>Soru - Yanıt

### <a name="q-why-dont-i-see-the-option-to-record-my-coded-ui-test-in-the-generate-code-for-a-coded-ui-test-dialog"></a>Kodlanmış UI testi iletişim oluşturmak kodunda my kodlanmış UI testini kaydetme seçeneği neden göremiyorum?

**A**: kaydetme seçeneği UWP uygulamaları için desteklenmiyor.

### <a name="q-can-i-create-a-coded-ui-test-for-my-uwp-apps-based-on-winjs"></a>S: kodlanmış UI testi için UWP uygulamalarım üzerinde WinJS oluşturabilirim?

**A**: Hayır, yalnızca XAML tabanlı uygulamaları desteklenmez.

### <a name="q-why-cant-i-modify-the-code-in-the-uimapdesigner-file"></a>S: neden UIMap.Designer dosyasındaki kodu değiştirilemez?

**A**: herhangi bir kod, yaptığınız değişiklikleri *UIMapDesigner.cs* dosyanın üzerine kod kullanarak oluşturduğunuz her zaman **kodlanmış UI Test derleyicisini**. Kayıtlı bir yöntemi değiştirmeniz gerekiyorsa, kopyalayın *UIMap.cs* dosya ve yeniden adlandırın. *UIMap.cs* dosya, yöntemleri ve özellikleri geçersiz kılmak için kullanılabilir *UIMapDesigner.cs* dosya. Özgün yönteminde başvurusunu kaldırın *CodedUITest.cs* dosya ve adlandırılan yöntem adıyla değiştirin.

## <a name="see-also"></a>Ayrıca bkz.

- [UI otomasyonunu kullanarak kodunuzu test etme](../test/use-ui-automation-to-test-your-code.md)
- [UWP denetimleri için benzersiz Otomasyon özelliklerini ayarlama](../test/set-a-unique-automation-property-for-windows-store-controls-for-testing.md)