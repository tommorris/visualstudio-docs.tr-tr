---
title: Visual Studio'da kodunuzu test etmek için UI otomasyonunu kullanma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
f1_keywords:
- vs.codedUITest
- vs.codedUITest.recorder
- vs.codedUITest.testbuilder
- vs.codedUITest.addAssertions
- vs.codedUITest.createdialog
helpviewer_keywords:
- automated tests, testing UI interface
- coded UI test
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 72b97eb0c6ed496da29acb65ddc07b9f25f58b7d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="use-ui-automation-to-test-your-code"></a>Kodunuzu Test Etmek için UI Otomasyonunu Kullanma

Uygulamanız kendi kullanıcı arabirimi (UI) üzerinden sürücü otomatikleştirilmiş testleri olarak bilinen *kodlanmış UI testleri* (CUITs). Bu testler, kullanıcı Arabirimi denetimlerini işlevsel test edilmesini içerir. Bunlar, kullanıcı arabirimiyle dahil olmak üzere tüm uygulama düzgün çalıştığını doğrulamak olanak tanır. Doğrulama veya diğer mantığı kullanıcı arabiriminde, örneğin, bir web sayfasındaki olduğu kodlanmış UI testleri özellikle yararlı olur. Bunlar ayrıca sık varolan el ile testi otomatik hale getirmek için kullanılır.

Aşağıdaki çizimde gösterildiği gibi tipik geliştirme deneyimi biri, başlangıçta yalnızca uygulamanızı (F5) ve burada şeyler düzgün çalıştığını doğrulamak için kullanıcı Arabirimi denetimlerini tıklatın olabilir. Uygulamayı el ile test etmek devam gerekmemesi Kodlanmış testi oluşturmaya karar verebilirsiniz. Uygulamanızı test edilmekte belirli işlevi bağlı olarak kod işlevsel bir test ya da olabilir veya UI düzeyinde sınama içermeyebilir bir tümleştirme test yazabilirsiniz. Yalnızca bazı iş mantığı doğrudan erişim sağlamak istiyorsanız, birim testi kodu. Ancak, belirli koşullar altında çeşitli UI denetimlerinin uygulamanızda sınama dahil etmek yararlı olabilir. Kodlanmış UI testi ilk (F5), bu kod karmaşası uygulamanızın işlevselliğini etkilemez doğrulama senaryo, otomatik hale getirebilirsiniz.

![Uygulama geliştirme sırasında test etme](../test/media/cuit_overview.png)

Kodlanmış UI testi oluşturmak kolaydır. Test CUIT Oluşturucusu arka planda çalışırken, yalnızca test el ile gerçekleştirin. Ne değerleri belirli alanlarında görünmesini de belirtebilirsiniz. CUIT Test Oluşturucusu eylemlerinizi kaydeder ve bunları kod oluşturur. Test oluşturulduktan sonra eylemlerin sırasını değiştirmenize olanak tanır özelleştirilmiş bir düzenleyicide düzenleyebilirsiniz.

Microsoft Test Yöneticisi'nde kaydedilmiş olan bir test çalışması varsa, bunun yerine, kod, oluşturabilirsiniz. Daha fazla bilgi için bkz: [kaydı ve play geri el ile testler](/vsts/manual-test/getting-started/record-play-back-manual-tests).

Özelleştirilmiş CUIT Test derleyicisini ve düzenleyici oluşturma ve ana becerilerinizi test yerine kodlama yoğunlaşmıştır olsa bile kodlanmış UI testlerini düzenleme kolaylaştırır. Ancak, böylece kopyalayıp uyarlamak basit bir geliştirici misiniz ve testini daha gelişmiş bir biçimde genişletmek istiyorsanız kodu yapılandırılmıştır. Örneğin, bir Web sitesindeki bir şey satın almak için bir test kaydetmek ve çok sayıda öğe satın bir döngü eklemek için oluşturulan kodu girin.

**Gereksinimler**

- Visual Studio Enterprise

Hangi platformlar ve yapılandırmaları desteklenir kodlanmış UI testleri tarafından daha fazla bilgi için bkz: [kodlanmış UI testleri için desteklenen platformları](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md).

## <a name="create-coded-ui-tests"></a>Kodlanmış UI testleri oluşturma

1. Yükleme **kodlanmış UI testi** bileşeni.

   Henüz yapmadıysanız, yükleme **kodlanmış UI testi** Visual Studio'nun bileşen. Başlatma **Visual Studio yükleyicisi** seçerek **Araçları** > **alma araçları ve özelliklerinin**. İçinde **Visual Studio yükleyicisi**, seçin **bileşenleri tek tek** sekmesini tıklatın ve sonra aşağı kaydırarak **hata ayıklama ve test** bölümü. Seçin **kodlanmış UI testi** bileşeni ve ardından **Değiştir**.

   ![Kodlanmış UI test bileşeni](media/coded-ui-test-component.png)

1. Kodlanmış UI testi projesi oluşturun.

   Kodlanmış UI testleri bir kodlanmış UI test projesinin içinde yer almalıdır. Kodlanmış UI test projesi zaten sahip değilseniz, birini oluşturun. Seçin **dosya** > **yeni** > **proje** açmak için **yeni proje** iletişim kutusu. Kategoriler sol bölmesinde **yüklü** > **Visual Basic** *veya* **Visual C#**  >   **Test**. Seçin **kodlanmış UI Test projesi** şablonu ve ardından **Tamam**.

   ![Yeni Proje iletişim kutusuna kodlanmış UI testi proje şablonu](media/coded-ui-test-project-template.png)

2. Kodlanmış UI testi dosyanıza ekleyin.

     Kodlanmış UI proje oluşturduysanız, ilk CUIT dosyası otomatik olarak eklenir. Başka bir test dosyası eklemek için kodlanmış UI test projesinin kısayol menüsünden açmak **Çözüm Gezgini**ve ardından **Ekle** > **kodlanmış UI testi**.

     İçinde **kodlanmış UI testi için kodu oluştur** iletişim kutusunda, seçin **kayıt Eylemler, UI eşlemesini düzenle veya onaylar ekleme**.

     ![Kodlanmış UI test iletişim kutusu için kod oluşturma](media/generate-code-for-coded-ui-test.png)

     Kodlanmış UI Test derleyicisini görüntülenir.

     ![Kodlanmış UI Test derleyicisini](../test/media/codedui_testbuilder.png)

3. Bir dizi eylemi kaydedin.

     **Kaydı başlatmak için**, seçin **kaydı** simgesi. Gerekli ise, uygulama başlatma dahil olmak üzere, uygulamanızda test etmek istediğiniz eylemleri gerçekleştirin. Örneğin, bir web uygulamasını test ediyorsanız, bir tarayıcı başlatmak, web sitesine gidin ve uygulamaya oturum açın.

     **Kaydı Duraklat için**, gelen posta ile mücadele etmek varsa örnek seçebilir **duraklatma**.

    > [!WARNING]
    > Masaüstünde gerçekleştirilen tüm eylemler kaydedilir. Kayıt eklenmesini hassas verileri açabilir Eylemler gerçekleştiriyorsanız duraklatma.

     **Eylemler silmek için** yanlışlıkla kaydettiğiniz, seçin **düzenleme eylemleri**.

     **Kodu oluşturmak için** , eylemlerinizi çoğaltmak, seçin **kodu oluştur** simgesi ve türü bir ad ve açıklama için kodlanmış UI test yöntemi.

4. Metin kutuları gibi UI alanlarındaki değerleri doğrulayın.

     Seçin **eklemek onaylar** kodlanmış UI Test derleyicisini içinde ve çalışan uygulamanızda bir kullanıcı Arabirimi denetim'i seçin. Örneğin, görüntülenen özellikler listesinde, bir özellik seçin **metin** metin kutusu. Kısayol menüsünden seçin **onay Ekle**. Karşılaştırma işleci, karşılaştırma değeri ve hata iletisi iletişim kutusunda seçin.

     Onaylama işlemi penceresini kapatın ve seçin **kodu oluştur**.

     ![Kodlanmış UI testi öğesi hedefleme](../test/media/codedui_1.png "CodedUI_1")

    > [!TIP]
    > Eylemlerini kaydederek ve değerleri doğrulama arasında geçiş yapar. Her bir dizi eylem veya Doğrulamalar sonunda kod oluşturur. İsterseniz, yeni eylemleri ve Doğrulamalar daha sonra eklemeniz mümkün olacaktır.

     Daha fazla ayrıntı için bkz: [denetimleri, doğrulama özelliklerini](#VerifyingCodeUsingCUITGenerateAssertions).

5. Oluşturulan test kodunu görüntüleyin.

     Oluşturulan kod görüntülemek için UI Test derleyicisini penceresini kapatın. Kod içinde her adımın verdiğiniz adlarını görebilirsiniz. Kod, oluşturduğunuz CUIT dosyasıdır:

    ```csharp
    [CodedUITest]
    public class CodedUITest1
    { ...
      [TestMethod]
      public void CodedUITestMethod1()
      {
          this.UIMap.AddTwoNumbers();
          this.UIMap.VerifyResultValue();
          // To generate more code for this test, select
          // "Generate Code" from the shortcut menu.
      }
    }
    ```

6. Daha fazla eylemleri ve onayları ekleyin.

   İmleci test yönteminde uygun bir noktasına yerleştirin ve ardından kısayol menüsünden seçin **kodlanmış UI testi için kod üret**. Bu noktada yeni kod eklenir.

7. Test eylemleri ve onayları ayrıntılarını düzenleyin.

     UIMap.uitest açın. Bu dosya kodlanmış UI testi Burada, kaydettiğiniz eylemleri herhangi bir dizi Düzenle yanı sıra onayları Düzen Düzenleyicisi'nde açılır.

     ![Kodlanmış UI Test Düzenleyicisi'ni](../test/media/cuit_editor_edit.png "CUIT_Editor_edit")

     Daha fazla bilgi için bkz: [kodlanmış UI Test Düzenleyicisi'ni kullanarak düzenleme kodlanmış UI testlerini](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).

8. Testi çalıştırın.

   Test Gezgini kullanma veya test yönteminde kısayol menüsünü açın ve ardından **Testleri Çalıştır**. Testleri çalıştırma hakkında daha fazla bilgi için bkz: [Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md) ve *çalıştırmak için ek seçenekler kodlanmış UI testleri* içinde [sonraki nedir?](#VerifyCodeUsingCUITWhatsNext) adresindeki bölüm Bu konuda sonu.

Bu konunun geri kalan bölümlerinde, bu yordamdaki adımları hakkında daha fazla ayrıntı sağlar.

Daha ayrıntılı bir örnek için bkz: [izlenecek yol: oluşturma, düzenleme ve kodlanmış UI testini sürdürme](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md). Kılavuzda oluşturmak, düzenlemek ve kodlanmış UI testi korumak nasıl yapılacağını göstermek üzere basit bir Windows Presentation Foundation (WPF) uygulaması oluşturacaksınız. İzlenecek yol çeşitli zamanlama sorunları ve yeniden düzenlemeyi denetleme tarafından kırılan testleri düzeltmeye ilişkin çözümler sağlar.

### <a name="start-and-stop-the-application-under-test"></a>Test altındaki uygulama durdurup başlatın

Uygulama, tarayıcı veya veritabanı her test için ayrı ayrı durdurmak ve başlatmak istemiyorsanız, aşağıdakilerden birini yapın:

- Uygulamanızı test altında başlatmak için eylemleri kaydetmek istemiyorsanız, seçmeden önce uygulamanızın başlamalıdır **kaydı** simgesi.

- Bir test sonunda test çalıştığı işlem sonlandırıldı. Uygulamanızı test başladıysanız, uygulama genellikle kapatır.  Test çıktığında uygulamanız kapatmak için eklemek istemiyorsanız, bir *.runsettings* dosya çözümünüze ve kullanmak `KeepExecutorAliveAfterLegacyRun` seçeneği. Daha fazla bilgi için bkz: [.runsettings dosyasını kullanarak birim testlerini yapılandırma](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).

- Tarafından tanımlanan bir test başlatma yöntemi Ekle bir `[TestInitialize]` her test yönteminin başlangıcında kod çalışır özniteliği. Örneğin, uygulamayı TestInitialize yönteminden başlatmak.

- Tarafından tanımlanan temizleme yöntemi Ekle bir `[TestCleanup]` her test yönteminin sonunda kodu çalıştıran özniteliği. Örneğin, uygulamayı kapatmak için bu yöntem TestCleanup yönteminden çağrılabilir.

### <a name="validate-the-properties-of-ui-controls"></a>Kullanıcı Arabirimi denetimlerini doğrula

Kullanabileceğiniz **kodlanmış UI Test oluşturucusunu** bir kullanıcı arabirimi (UI) denetim eklemek için <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> testiniz için ya da bir onaylama UI denetim için kullandığı bir doğrulama yöntemi için kod oluşturmak için.

Onaylamaları için kullanıcı Arabirimi denetimlerini oluşturmak için seçin **eklemek onaylar** aracı kodlanmış UI Test derleyicisini ve doğrulamak istediğiniz test altındaki uygulama denetimine doğru sürükleyin. Denetim kutusu özetlenmektedir, fareyi bırakın. Denetim sınıfı kodu hemen oluşturulan `UIMap.Designer.cs` dosyası.

![Kodlanmış UI testi öğesi hedefleme](../test/media/codedui_1.png "CodedUI_1")

Bu denetim için özellikleri artık listelenen **eklemek onaylar** iletişim kutusu.

Belirli bir denetim için gezinme başka bir yolu oku seçmektir **(<<)** görünümünü genişletmek için **UI denetim eşlemesi**. Bir üst, eşdüzey veya alt denetim bulmak için harita üzerinde herhangi bir yere tıklayın ve ağaç taşımak için ok tuşlarını kullanın.

![Kodlanmış UI testi özellikleri](../test/media/codedui_2.png "CodedUI_2")

> [!TIP]
> Uygulamanızda bir denetim seçin ya da denetim UI denetim eşlemesindeki görmüyorum herhangi bir özellik görmüyorsanız, denetimi uygulama kodunda benzersiz bir kimlik olduğunu doğrulayın. Benzersiz kimliği, bir HTML kimliği öznitelik veya bir WPF UId olabilir.

Ardından, özelliği doğrulayın ve ardından istediğiniz UI denetimi için kısayol menüsünden açmak **onay Ekle**. İçinde **onay Ekle** iletişim kutusunda **karşılaştırıcı** örneğin değerinizi <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A>ve değeri değerinizi içinde yazın **karşılaştırma değeri**.

![Kodlanmış UI testi onaylar](../test/media/codedui_3.png "CodedUI_3")

Testiniz için tüm onayları eklendiğinde seçin **Tamam**.

Onayları kodunu oluşturmak ve denetimi UI eşlemesine eklemek için tercih **kodu oluştur** simgesi. Kodlanmış UI test yönteminiz için bir ad ve açıklamalar yöntemi olarak eklenecek yöntemi için bir açıklama yazın. Seçin **ekleme ve oluşturma**. Ardından, seçin **kapatmak** kapatmak için simgesini **kodlanmış UI Test derleyicisini**. Aşağıdaki kodu benzer bir kod oluşturur. Örneğin, girdiğiniz adı ise `AssertForAddTwoNumbers`, kod aşağıdaki gibi görünür:

- Kodlanmış UI test dosyanız test yöntemine AssertForAddTwoNumbers assert yöntemine bir çağrı ekler:

    ```csharp
    [TestMethod]
    public void CodedUITestMethod1()
    {
        this.UIMap.AddTwoNumbers();
        this.UIMap.AssertForAddTwoNumbers();
    }
    ```

     Onaylar ve adımları sırasını değiştirmek için ya da yeni test yöntemleri oluşturmak için bu dosyayı düzenleyebilirsiniz. Daha fazla kod eklemek için yer imleci test yöntemi ve kısayol menüsünde seçin **kodlanmış UI testi için kod üret**.

- Adlı bir yöntem ekler `AssertForAddTwoNumbers` UI eşlemenize (UIMap.uitest). Bu dosya kodlanmış UI testi onaylar düzenleyebileceğiniz Düzenleyicisi'nde açılır.

     ![Düzen assert kodlanmış UI Test Düzenleyicisi'ni kullanarak](../test/media/cuit_editor_assert.png "CUIT_Editor_assert")

     Daha fazla bilgi için bkz: [kodlanmış UI Test Düzenleyicisi'ni kullanarak düzenleme kodlanmış UI testlerini](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).

     Oluşturulan kod onaylama yönteminin içinde UIMap.Designer.cs de görüntüleyebilirsiniz. Ancak, bu dosyayı düzenlemeniz değil. Kodu uyarlanmış bir sürümünü yapmak istiyorsanız, yöntemleri UIMap.cs gibi başka bir dosyaya kopyalayın, yöntemleri yeniden adlandırın ve bunları düzenleyin.

    ```csharp
    public void AssertForAddTwoNumbers()
    {
        ...
    }
    ```

#### <a name="select-a-hidden-control-using-the-keyboard"></a>Klavyeyi kullanarak gizli bir denetim seçin

Seçmek istediğiniz denetim odağı kaybettiğinde ve kodlanmış UI Test Oluşturucusu'ndan eklemek onaylar Aracı'nı seçtiğinizde kaybolur varsa:

Bazı durumlarda, denetimleri ekleme ve bunların özelliklerini doğrulayın, klavye kullanmanız gerekebilir. Örneğin, bir bağlam menüsü denetimi kullanan kodlanmış bir UI testi kaydetmeye çalıştığınızda denetiminde menü öğeleri listesi odak kaybeder ve kodlanmış UI Test oluşturucusunu ekleme onaylar Aracı'nı seçmek çalıştığınızda kaybolur. Bu, burada Internet Explorer'da bağlam menüsünde odağı kaybettiğinde ve ekleme onaylar aracıyla seçmeye çalışırsanız kaybolur aşağıdaki çizimde gösterilmiştir.

![CodedUITest&#95;SelectControlKeyboard](../test/media/codeduitest_selectcontrolkeyboard.png "CodedUITest_SelectControlKeyboard")

UI denetim seçmek için klavyeyi kullanmak için Denetim fareyle üzerine gelerek. Ardından basılı **Ctrl** anahtarı ve **ı** aynı zamanda anahtar. Tuşları serbest bırakın. Denetim kodlanmış UT Test Oluşturucusu tarafından kaydedilir.

> [!WARNING]
> Microsoft Lync kullanırsanız, kodlanmış UI Test derleyicisini başlamadan önce Lync kapatmanız gerekir. Microsoft Lync uğratan ile **Ctrl + ı** klavye kısayolu.

#### <a name="manually-record-mouse-hovers"></a>El ile kayıt fare gezinen

Bir denetim fare gidildiğinde kaydedemez varsa:

Bazı durumlarda, kullanılmakta olan belirli bir denetim kodlanmış bir UI testi el ile kayıt fare vurgulu olayları için klavyeyi kullanma gerektirebilir. Örneğin, bir Windows formu veya bir Windows Presentation Foundation (WPF) uygulamasını test ettiğinizde olabilir özel kod. Veya, bir kullanıcı üzerine geldiğinde genişleyen bir ağaç düğümü gibi bir denetim üzerine getirildiğinde için tanımlanan özel davranış olabilir. Bu gibi durumlarda sınamak için el ile kodlanmış UI Test tuşlarına basarak denetimin üzerine getirildiğinde Oluşturucu klavye tuşlarını önceden tanımlanmış bildirim sahip.

Kodlanmış UI testi gerçekleştirdiğinizde, denetimin üzerine gelin. Tuşuna basın ve Ctrl, basılı klavyenizde kaydırma ve R tuşlarını basılı tutarak. Tuşları serbest bırakın. Fare vurgulu olay kodlanmış UT Test Oluşturucusu tarafından kaydedilir.

![CodedUI&#95;vurgulu](../test/media/codedui_hover.png "CodedUI_Hover")

Test yöntemi oluşturduktan sonra aşağıdaki örneğe benzer bir kod UIMap.Desinger.cs dosyasına eklenecek:

```csharp
// Mouse hover '1' label at (87, 9)
Mouse.Hover(uIItem1Text, new Point(87, 9));
```

#### <a name="configure-mouse-hover-keyboard-assignments"></a>Fare vurgulu klavye atamalarını yapılandırın

Fare vurgulu olaylarını yakalamak için anahtar atama başka bir yerde my ortamında kullanılıyorsa:

Gerekirse, varsayılan atama, klavye, **Ctrl**+**Shift**+**R** kodlanmış UI testlerinde fare vurgulu olayları uygulamak için kullanılır farklı anahtarlara kullanacak şekilde yapılandırılabilir.

> [!WARNING]
> Normal koşullar altında fare vurgulu olayları klavye atamalarını değiştirmek olmamalıdır. Klavye atama yeniden atama dikkatli olun. Tercih ettiğiniz zaten başka bir yerde Visual Studio ya da test edilen uygulamanın içinde kullanımda olabilir.

Klavye atamalarını değiştirmek için aşağıdaki yapılandırma dosyası değiştirin:

*% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CodedUITestBuilder.exe.config*

Yapılandırma dosyasında değerlerini değiştirmek `HoverKeyModifier` ve `HoverKey` anahtarları klavye atamalarını değiştirmek için:

```xml
<!-- Begin : Background Recorder Settings -->
<!-- HoverKey to use. -->
<add key="HoverKeyModifier" value="Control, Shift"/>
<add key="HoverKey" value="R"/>
```

#### <a name="set-implicit-mouse-hovers-for-the-web-browser"></a>Örtük fare gezinen web tarayıcısının ayarlayın

Kayıt sorunları yaşıyorsanız, fare bir Web sitesinde gezinen:

Belirli bir denetime geldiğinizde birçok Web sitesi bu ek ayrıntılar göstermek için genişletir. Genellikle, bu Masaüstü uygulamaları menülerde gibi arayın. Bu genel bir desen olduğundan, Web'e gözatma için örtük gezinen kodlanmış UI testleri etkinleştirin. Örneğin, Internet Explorer'da, kayıt gezinen, bir olay tetiklenir. Bu olaylar için yedek gezinen kaydedilen yol açabilir. Bu nedenle, örtük gezinen ile kaydedilir `ContinueOnError` kümesine `true` UI testi yapılandırma dosyası. Bu kayıttan yürütmenin vurgulu olay başarısız olursa devam etmesini sağlar.

Örtük gezinen bir Web tarayıcısında kaydını etkinleştirmek için yapılandırma dosyasını açın:

*% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CodedUITestBuilder.exe.config*

Yapılandırma dosyası anahtar olduğunu doğrulayın `RecordImplicitiHovers` kümesine bir değerine `true` aşağıdaki örnekte gösterildiği gibi:

```xml
<!--Use this to enable/disable recording of implicit hovers.-->
<add key="RecordImplicitHover" value="true"/>
```

## <a name="customize-the-coded-ui-test"></a>Kodlanmış UI testi özelleştirme

Kodlanmış UI testi oluşturduktan sonra Visual Studio aşağıdaki araçlardan birini kullanarak düzenleyebilirsiniz:

- **Kodlanmış UI Test derleyicisini:** kodlanmış UI Test derleyicisini ek denetimleri ve doğrulama testlerinizi eklemek için kullanın. Bölümüne bakın [denetimler ekleme ve bunların özelliklerini doğrulama](#VerifyingCodeUsingCUITGenerateAssertions) bu konuda.

- **Kodlanmış UI Test Düzenleyicisi:** kodlanmış UI Test Düzenleyicisi'ni kolayca kodlanmış UI testleri değiştirmenize olanak tanır. Kodlanmış UI Test Düzenleyicisi'ni kullanarak bulun, görüntülemek ve test yöntemlerinizi düzenleyin. Ayrıca, kullanıcı Arabirimi eylemlerini ve UI denetim eşlemesindeki ilişkili denetimlerini düzenleyebilirsiniz. Daha fazla bilgi için bkz: [kodlanmış UI Test Düzenleyicisi'ni kullanarak düzenleme kodlanmış UI testlerini](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).

- **Kod Düzenleyicisi:**

    - Bölümünde açıklandığı gibi denetimler için kod testinizde el ile eklemeniz [kodlama kullanıcı Arabirimi denetim eylemleri ve özelliklerini](#VerifyingCodeCUITActionsandProperties) bölümüne bakın.

    - Kodlanmış UI testi oluşturduktan sonra veri güdümlü olacak şekilde değiştirebilirsiniz. Daha fazla bilgi için bkz: [veri-odaklı kodlanmış UI testi oluşturma](../test/creating-a-data-driven-coded-ui-test.md).

    - İçinde kodlanmış bir UI Testi kayıttan, kaybolur ve benzeri için ilerleme çubuğu oluşmasına görünmesi için bir pencere gibi belirli olaylar için beklenecek test söyleyebilirsiniz. Bunu yapmak için uygun UITestControl.WaitForControlXXX() yöntemini ekleyin. Kullanılabilir yöntemleri tam bir listesi için bkz: [yapmadan kodlanmış UI testleri beklemek için belirli olayları sırasında kayıttan yürütme](../test/making-coded-ui-tests-wait-for-specific-events-during-playback.md). Bir denetim WaitForControlEnabled yöntemini kullanarak etkin olmasını bekler kodlanmış bir UI testi örneği için bkz: [izlenecek yol: oluşturma, düzenleme ve kodlanmış bir UI testi koruma](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md).

    - Kodlanmış UI testleri bazı Internet Explorer 9 ve Internet Explorer 10 dahil HTML5 denetimler için destek içerir. Daha fazla bilgi için bkz: [kodlanmış UI testlerinde HTML5 denetimleri kullanma](../test/using-html5-controls-in-coded-ui-tests.md).

    - Kodlanmış UI testi Kılavuzu kodlama:

       - [Kodlanmış UI Testinin Anatomisi](../test/anatomy-of-a-coded-ui-test.md)

       - [Kodlanmış UI Testleri için En İyi Yöntemler](../test/best-practices-for-coded-ui-tests.md)

       - [Birden Çok UI Eşlemesi Bulunan Büyük Uygulamaları Sınama](../test/testing-a-large-application-with-multiple-ui-maps.md)

       - [Kodlanmış UI Testleri ve Eylem Kayıtları için Desteklenen Yapılandırmalar ve Platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)

### <a name="the-generated-code"></a>Oluşturulan kod

Seçtiğinizde **kodu oluştur**, birkaç kod parçalarını oluşturulur:

- **Test yöntemi satırda.**

    ```csharp
    [CodedUITest]
    public class CodedUITest1
    { ...
      [TestMethod]
      public void CodedUITestMethod1()
      {
          this.UIMap.AddTwoNumbers();
          // To generate more code for this test, select
          // "Generate Code" from the shortcut menu.      }
    }
    ```

     Daha fazla kaydedilmiş eylemleri ve Doğrulamalar eklemek için bu yöntemi, sağ tıklayın. Ayrıca, el ile genişletmek veya kodunu değiştirmek için de düzenleyebilirsiniz. Örneğin, bazı kodları bir döngüde içine aldığınız.

     Ayrıca, yeni test yöntemleri ekleyin ve kod bunları aynı şekilde ekleyin. Her bir test yöntemi olmalıdır `[TestMethod]` özniteliği.

- **UIMap.uitest içindeki bir yöntemi**

     Bu yöntem, kaydettiğiniz eylemleri ya da, doğrulanmış değeri ayrıntılarını içerir. Bu kod UIMap.uitest açarak düzenleyebilirsiniz. Silebilir veya yeniden düzenlemeniz kaydedilmiş eylemler bir özelleştirilmiş Düzenleyicisi'nde açar.

     UIMap.Designer.cs içinde oluşturulan yöntemi de görüntüleyebilirsiniz. Bu yöntem testi çalıştırdığınızda kaydettiğiniz eylemleri gerçekleştirir.

    ```csharp
    // File: UIMap.Designer.cs
    public partial class UIMap
    {
      /// <summary>
      /// Add two numbers
      /// </summary>
      public void AddTwoNumbers()
      { ...   }
    }
    ```

    > [!WARNING]
    > Daha fazla testleri oluşturduğunuzda, yeniden oluşturulacak olduğundan, bu dosyayı düzenleme yapmamanız gerekir.

     Bu yöntemlerin uyarlanmış sürümleri için kopyalayarak yapabileceğiniz *UIMap.cs*. Örneğin, bir test yöntemi çağırabilirsiniz parametreli bir sürüm yapabilirsiniz:

    ```csharp
    // File: UIMap.cs
    public partial class UIMap // Same partial class
    {
      /// <summary>
      /// Add two numbers - parameterized version
      /// </summary>
      public void AddTwoNumbers(int firstNumber, int secondNumber)
      { ...   // Code modified to use parameters.
      }
    }
    ```

- **UIMap.uitest bildirimlerinde**

    Bu bildirimler, test tarafından kullanılan UI denetimleri uygulamanın temsil eder. Tarafından oluşturulan kodu bunlar denetimleri çalışır ve bunların özelliklerine erişmek için kullanılır.

    Kendi kodunuzu yazarsanız, ayrıca bunları kullanabilirsiniz. Örneğin, bir Web uygulamasında bir köprü seçin, metin kutusuna bir değer yazın veya dal ve bir alandaki bir değere göre farklı test eylemleri test yönteminize olabilir.

    Birden çok kodlanmış UI testleri ve birden çok UI haritası nesneleri ve büyük uygulamaları sınama kolaylaştırmak için dosyaları ekleyebilirsiniz. Daha fazla bilgi için bkz: [birden çok UI eşlemesi bulunan büyük uygulamaları sınama](../test/testing-a-large-application-with-multiple-ui-maps.md).

Oluşturulan kodun hakkında daha fazla bilgi için bkz: [kodlanmış UI testinin anatomisi](../test/anatomy-of-a-coded-ui-test.md).

### <a name="code-ui-control-actions-and-properties"></a>Kullanıcı Arabirimi denetim eylemleri ve özelliklerini kod

UI test denetimleri ile çalışırken kodlanmış UI testleri, iki bölüme ayrılır: Eylemler ve özellikler.

- İlk bölümü UI test denetimleri üzerinde gerçekleştirebileceğiniz eylemler oluşur. Örneğin, kodlanmış UI testleri bir UI testi denetimi fare tıklamaları benzetimini yapmak veya bir UI testi denetimini etkilemek için klavyede yazılan anahtarları benzetimi.

- İkinci bölümü, almak ve bir UI testi denetimde özelliklerini ayarlamak sağlamadan oluşur. Örneğin, kodlanmış UI testleri öğelerinin sayısı elde edebilirsiniz bir `ListBox`, veya bir `CheckBox` seçili duruma.

**UI Test denetiminin eylemler erişme**

UI test denetimlerinde fare tıklamaları veya klavye eylemleri gibi eylemleri gerçekleştirmek için yöntemleri kullanın <xref:Microsoft.VisualStudio.TestTools.UITesting.Mouse> ve <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard> sınıfları:

- Bir tıklatma bir UI testi denetimde gibi Fare yönelimli bir eylem gerçekleştirmek için kullandığınız <xref:Microsoft.VisualStudio.TestTools.UITesting.Mouse.Click%2A>.

     `Mouse.Click(buttonCancel);`

- Gibi bir düzenleme denetimine yazarak bir klavye odaklı eylemi gerçekleştirmek için kullandığınız <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard.SendKeys%2A>.

     `Keyboard.SendKeys(textBoxDestination, @"C:\Temp\Output.txt");`

**UI Test denetiminin özelliklerine erişme**

Almak ve UI denetimi belirli özellik değerlerini ayarlamak için doğrudan almak veya değerlerin bir denetimin özelliklerini ayarlamak veya kullanabileceğiniz <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.GetProperty%2A?displayProperty=fullName> ve <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.SetProperty%2A?displayProperty=fullName> yöntemleri kullanılarak almak veya ayarlamak istediğiniz belirli özelliğinin adı.

<xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.GetProperty%2A> ardından uygun atanabilecek bir nesne döndürür <xref:System.Type>. <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.SetProperty%2A> bir nesne için özellik değeri kabul eder.

#### <a name="to-get-or-set-properties-from-ui-test-controls-directly"></a>Almak veya özellikler UI test denetimlerinden doğrudan ayarlamak için

Öğesinden türetilen denetimleri ile <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl>, gibi [HTML liste](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.uitesting.htmlcontrols.htmllist.aspx) veya [WinComboBox](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.uitesting.wincontrols.wincombobox.aspx), get veya doğrudan özellik değerlerine ayarlayın. Aşağıdaki kod bazı örnekler gösterilmektedir:

 ```csharp
 int i = myHtmlList.ItemCount;
 myWinCheckBox.Checked = true;
 ```

#### <a name="to-get-properties-from-ui-test-controls"></a>UI test denetimlerinden özellikleri almak için

- Bir özellik değeri denetimden almak için <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.GetProperty%2A>.

- Almak üzere denetimin özelliğini belirtmek için uygun dize kullanın `PropertyNames` her denetim için parametre olarak sınıfında <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.GetProperty%2A>.

- <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.GetProperty%2A> uygun veri türünü, ancak bu dönüş değeri olarak atandığında döndürür bir <xref:System.Object>. Dönüş <xref:System.Object> sonra uygun türe gerekir.

     Örnek:

     `int i = (int)GetProperty(myHtmlList.PropertyNames.ItemCount);`

#### <a name="to-set-properties-for-ui-test-controls"></a>UI özelliklerini ayarlamak için denetimleri testi

- Bir denetimde bir özelliğini ayarlamak için kullanın <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.SetProperty%2A>.

- Ayarlamak için denetimin özelliğini belirtmek için uygun dize kullanın `PropertyNames` sınıfı ilk parametre olarak <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.SetProperty%2A>, ikinci parametre olarak özellik değerine sahip.

     Örnek:

     `SetProperty(myWinCheckBox.PropertyNames.Checked, true);`

### <a name="debug"></a>Hata ayıklama

Kodlanmış UI test günlüklerini kullanarak kodlanmış UI testlerini analiz edebilirsiniz. Kodlanmış UI test günlüklerini filtresi ve kayıt kodlanmış UI testi hakkında önemli bilgiler çalıştırır. Günlükleri biçimi hızla hatalarını ayıklamanıza olanak tanır. Daha fazla bilgi için bkz: [çözümleme kodlanmış UI testleri kullanarak kodlanmış UI Test günlüklerini](../test/analyzing-coded-ui-tests-using-coded-ui-test-logs.md).

## <a name="whats-next"></a>Sonraki adım nedir?

**Kodlanmış UI testleri çalıştırmak için ek seçenekler:** bu konunun önceki kısımlarında açıklandığı gibi doğrudan Visual Studio'dan kodlanmış UI testleri çalıştırabilirsiniz. Ayrıca, Microsoft Test Yöneticisi'nden veya Team Foundation Build otomatikleştirilmiş UI testleri çalıştırabilirsiniz. Kodlanmış UI testleri otomatik, bunları, diğer otomatikleştirilmiş testleri farklı olarak çalıştırdığınızda, masaüstü ile etkileşimine izin sahiptirler.

- [Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md)

- [Yapı işleminizin testleri çalıştırma](/vsts/build-release/test/getting-started-with-continuous-testing)

- [Nasıl yapılır: Masaüstü ile etkileşimi olan testleri çalıştırmak için Test aracınızı ayarlama](http://msdn.microsoft.com/Library/3a94dd07-6d17-402c-ae8f-7947143755c9)

**Özel denetimler için destek ekleyen:** kodlanmış UI Test Çerçevesi olası her UI desteklemez ve test etmek istediğiniz kullanıcı arabirimini desteklemiyor olabilir. Örneğin, Microsoft Excel için kodlanmış UI testi UI hemen oluşturulamıyor. Ancak, özel bir denetim destekleyecek kodlanmış UI Test Çerçevesi uzantısı oluşturabilirsiniz.

- [Denetimlerinizin Kodlanmış UI Testlerini Etkinleştirme](../test/enable-coded-ui-testing-of-your-controls.md)

- [Kodlanmış Kullanıcı Arabirimi Testlerini ve Eylem Kayıtlarını Microsoft Excel'i Desteklemek için Genişletme](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)

Kodlanmış UI testleri genellikle el ile testleri otomatikleştirmek için kullanılır. El ile testleri hakkında daha fazla bilgi için bkz: [Microsoft Test Yöneticisi ile el ile testleri çalıştırma](/vsts/manual-test/mtm/run-manual-tests-with-microsoft-test-manager). Otomatikleştirilmiş testleri hakkında daha fazla bilgi için bkz: [Visual Studio Test Araçları](../test/improve-code-quality.md).

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>
- [Kod Kalitesini Geliştirme](../test/improve-code-quality.md)
- [İzlenecek yol: Kodlanmış Bir UI Testi Oluşturmak Düzenlemek ve Sürdürmek](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)
- [Kodlanmış UI Testinin Anatomisi](../test/anatomy-of-a-coded-ui-test.md)
- [Kodlanmış UI Testleri için En İyi Yöntemler](../test/best-practices-for-coded-ui-tests.md)
- [Birden Çok UI Eşlemesi Bulunan Büyük Uygulamaları Sınama](../test/testing-a-large-application-with-multiple-ui-maps.md)
- [Kodlanmış UI Test Düzenleyicisi'ni Kullanarak Kodlanmış UI Testlerini Düzenleme](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md)
- [Kodlanmış UI Testleri ve Eylem Kayıtları için Desteklenen Yapılandırmalar ve Platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
- [Visual Studio 2010'dan Kodlanmış UI Testlerini Yükseltme](../test/upgrading-coded-ui-tests-from-visual-studio-2010.md)