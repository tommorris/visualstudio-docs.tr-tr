---
title: "Kodunuzu test etmek için UI otomasyonunu kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codedUITest
- vs.codedUITest.recorder
- vs.codedUITest.testbuilder
- vs.codedUITest.addAssertions
- vs.codedUITest.createdialog
helpviewer_keywords:
- automated tests, testing UI interface
- coded UI test
ms.assetid: ad9e3eaa-ab86-436e-95b8-dc20eb1f8b2a
caps.latest.revision: "85"
ms.author: douge
manager: douge
ms.openlocfilehash: af6cb2319ffb851e91ff87d7e998eeb25315e9fc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="use-ui-automation-to-test-your-code"></a>Kodunuzu Test Etmek için UI Otomasyonunu Kullanma
Uygulamanız kendi kullanıcı arabirimi (UI) üzerinden sürücü otomatikleştirilmiş testleri olarak bilinen *kodlanmış UI testleri* (CUITs). Bu testler, kullanıcı Arabirimi denetimlerini işlevsel test edilmesini içerir. Bunlar, kullanıcı arabirimiyle dahil olmak üzere tüm uygulama düzgün çalıştığını doğrulamak olanak tanır. Doğrulama veya diğer mantığı kullanıcı arabiriminde, örneğin, bir web sayfasındaki olduğu kodlanmış UI testleri özellikle yararlı olur. Bunlar ayrıca sık varolan el ile testi otomatik hale getirmek için kullanılır.  
  
 Aşağıdaki çizimde gösterildiği gibi tipik geliştirme deneyimi biri, başlangıçta yalnızca uygulamanızı (F5) ve burada şeyler düzgün çalıştığını doğrulamak için kullanıcı Arabirimi denetimlerini tıklatın olabilir. Uygulamayı el ile test etmek devam gerekmemesi Kodlanmış testi oluşturmaya karar verebilirsiniz. Uygulamanızı test edilmekte belirli işlevi bağlı olarak kod işlevsel bir test ya da olabilir veya UI düzeyinde sınama içermeyebilir bir tümleştirme test yazabilirsiniz. Yalnızca bazı iş mantığı doğrudan erişim sağlamak istiyorsanız, birim testi kodu. Ancak, belirli koşullar altında çeşitli UI denetimlerinin uygulamanızda sınama dahil etmek yararlı olabilir. Kodlanmış UI testi ilk (F5), bu kod karmaşası uygulamanızın işlevselliğini etkilemez doğrulama senaryo, otomatik hale getirebilirsiniz.  
  
 ![Uygulama geliştirme sırasında test](../test/media/cuit_overview.png "CUIT_Overview")  
  
 Kodlanmış UI testi oluşturmak kolaydır. Test CUIT Oluşturucusu arka planda çalışırken, yalnızca test el ile gerçekleştirin. Ne değerleri belirli alanlarında görünmesini de belirtebilirsiniz. CUIT Test Oluşturucusu eylemlerinizi kaydeder ve bunları kod oluşturur. Test oluşturulduktan sonra eylemlerin sırasını değiştirmenize olanak tanır özelleştirilmiş bir düzenleyicide düzenleyebilirsiniz.  
  
 Microsoft Test Yöneticisi'nde kaydedilmiş olan bir test çalışması varsa, bunun yerine, kod, oluşturabilirsiniz. Daha fazla bilgi için bkz: [kaydı ve play geri el ile testler](/devops-test-docs/test/record-and-play-back-manual-tests).  
  
 Özelleştirilmiş CUIT Test derleyicisini ve düzenleyici oluşturma ve ana becerilerinizi test yerine kodlama yoğunlaşmıştır olsa bile kodlanmış UI testlerini düzenleme kolaylaştırır. Ancak, böylece kopyalayıp uyarlamak basit bir geliştirici misiniz ve testini daha gelişmiş bir biçimde genişletmek istiyorsanız kodu yapılandırılmıştır. Örneğin, bir Web sitesindeki bir şey satın almak için bir test kaydetmek ve çok sayıda öğe satın bir döngü eklemek için oluşturulan kodu girin.  
  
 **Gereksinimler**  
  
-   Visual Studio Enterprise  
  
 Hangi platformlar ve yapılandırmaları desteklenir kodlanmış UI testleri tarafından daha fazla bilgi için bkz: [kodlanmış UI testleri ve eylem kayıtları için desteklenen yapılandırmalar ve platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md).  
  
 **Bu konudaki**  
  
-   [Kodlanmış UI testleri oluşturma](#VerifyingCodeUsingCUITCreate)  
  
    -   [Main yordamı](#VerifyingCodeUsingCUITCreate)  
  
    -   [Başlatma ve durdurma uygulama](#starting)  
  
    -   [Kullanıcı Arabirimi denetimlerini doğrulanıyor](#VerifyingCodeUsingCUITGenerateAssertions)  
  
-   [Kodlanmış UI testi özelleştirme](#VerifyingCodeCUITModify)  
  
    -   [Oluşturulan kod](#generatedCode)  
  
    -   [Kullanıcı Arabirimi denetim eylemleri ve özelliklerini kodlama](#actions)  
  
    -   [Hata ayıklama](#debugging)  
  
-   [Sırada ne var?](#VerifyCodeUsingCUITWhatsNext)  
  
##  <a name="VerifyingCodeUsingCUITCreate"></a>Kodlanmış UI testleri oluşturma  
  
1.  **Kodlanmış UI testi projesi oluşturun.**  
  
     Kodlanmış UI testleri bir kodlanmış UI test projesinin içinde yer almalıdır. Kodlanmış UI test projesi zaten sahip değilseniz, birini oluşturun. İçinde **Çözüm Gezgini**, çözüm kısayol menüsünden seçin **Ekle**, **yeni proje** seçin **Visual Basic** veya **Visual C#**. Ardından, seçin **Test**, **kodlanmış UI testi**.  
  
    -   *Görmüyorum **kodlanmış UI testi** proje şablonları.*  
  
         Kodlanmış UI testleri desteklemiyor Visual Studio sürümünü kullanıyor olabilirsiniz. Kodlanmış UI testleri oluşturmak için Visual Studio Enterprise kullanmanız gerekir.  
  
2.  **Kodlanmış UI testi dosyanıza ekleyin.**  
  
     Kodlanmış UI proje oluşturduysanız, ilk CUIT dosyası otomatik olarak eklenir. Başka bir test dosyası eklemek için kodlanmış UI test projesinin kısayol menüsünü açın, işaret **Ekle**ve ardından **kodlanmış UI testi**.  
  
     ![Kodlanmış UI testi oluşturmak](../test/media/codedui_create.png "CodedUI_Create")  
  
     İçinde **kodlanmış UI testi için kodu oluştur** iletişim kutusunda, seçin **kayıt Eylemler, UI eşlemesini düzenle veya onaylar ekleme**.  
  
     ![Kayıt eylemleri seçin](../test/media/codedui_codegendialogb.png "CodedUI_CodeGenDialogB")  
  
     Kodlanmış UI Test derleyicisini görünür ve Visual Studio en aza indirilir.  
  
     ![Kodlanmış UI Test derleyicisini](../test/media/codedui_testbuilder.png "CodedUI_TestBuilder")  
  
3.  **Bir dizi eylemi kaydetmek**.  
  
     **Kaydı başlatmak için**, seçin **kaydı** simgesi. Gerekli ise, uygulama başlatma dahil olmak üzere, uygulamanızda test etmek istediğiniz eylemleri gerçekleştirin.  
  
     Örneğin, bir web uygulamasını test ediyorsanız, bir tarayıcı başlatmak, web sitesine gidin ve uygulamaya oturum açın.  
  
     **Kaydı Duraklat için**, gelen posta ile mücadele etmek varsa örnek seçebilir **duraklatma**.  
  
    > [!WARNING]
    >  Masaüstünde gerçekleştirilen tüm eylemler kaydedilir. Kayıt eklenmesini hassas verileri açabilir Eylemler gerçekleştiriyorsanız duraklatma.  
  
     **Eylemler silmek için** yanlışlıkla kaydettiğiniz, seçin **düzenleme eylemleri**.  
  
     **Kodu oluşturmak için** , eylemlerinizi çoğaltmak, seçin **kodu oluştur** simgesi ve türü bir ad ve açıklama için kodlanmış UI test yöntemi.  
  
4.  **Metin kutuları gibi UI alanlarındaki değerleri doğrulayın**.  
  
     Seçin **eklemek onaylar** kodlanmış UI Test derleyicisini içinde ve çalışan uygulamanızda bir kullanıcı Arabirimi denetim'i seçin. Örneğin, görüntülenen özellikler listesinde, bir özellik seçin **metin** metin kutusu. Kısayol menüsünden seçin **onay Ekle**. Karşılaştırma işleci, karşılaştırma değeri ve hata iletisi iletişim kutusunda seçin.  
  
     Onaylama işlemi penceresini kapatın ve seçin **kodu oluştur**.  
  
     ![Kodlanmış UI testi öğesi hedefleme](../test/media/codedui_1.png "CodedUI_1")  
  
    > [!TIP]
    >  Eylemlerini kaydederek ve değerleri doğrulama arasında geçiş yapar. Her bir dizi eylem veya Doğrulamalar sonunda kod oluşturur. İsterseniz, yeni eylemleri ve Doğrulamalar daha sonra eklemeniz mümkün olacaktır.  
  
     Daha fazla ayrıntı için bkz: [denetimleri, doğrulama özelliklerini](#VerifyingCodeUsingCUITGenerateAssertions).  
  
5.  **Oluşturulan test kodu görüntülemek**.  
  
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
  
6.  **Daha fazla eylemleri ve onayları eklemek**.  
  
     İmleci test yönteminde uygun bir noktasına yerleştirin ve ardından kısayol menüsünden seçin **kodlanmış UI testi için kod üret**. Bu noktada yeni kod eklenir.  
  
7.  **Test eylemleri ve onayları ayrıntılarını Düzenle**.  
  
     UIMap.uitest açın. Bu dosya kodlanmış UI testi Burada, kaydettiğiniz eylemleri herhangi bir dizi Düzenle yanı sıra onayları Düzen Düzenleyicisi'nde açılır.  
  
     ![Kodlanmış UI Test Düzenleyicisi'ni](../test/media/cuit_editor_edit.png "CUIT_Editor_edit")  
  
     Daha fazla bilgi için bkz: [kodlanmış UI Test Düzenleyicisi'ni kullanarak düzenleme kodlanmış UI testlerini](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).  
  
8.  **Test çalışmasını**.  
  
     Test Gezgini kullanma veya test yönteminde kısayol menüsünü açın ve ardından **Testleri Çalıştır**. Testleri çalıştırma hakkında daha fazla bilgi için bkz: [Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md) ve *çalıştırmak için ek seçenekler kodlanmış UI testleri* içinde [sonraki nedir?](#VerifyCodeUsingCUITWhatsNext) adresindeki bölüm Bu konuda sonu.  
  
 Bu konunun geri kalan bölümlerinde, bu yordamdaki adımları hakkında daha fazla ayrıntı sağlar.  
  
 Daha ayrıntılı bir örnek için bkz: [izlenecek yol: oluşturma, düzenleme ve kodlanmış UI testini sürdürme](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md). Kılavuzda oluşturmak, düzenlemek ve kodlanmış UI testi korumak nasıl yapılacağını göstermek üzere basit bir Windows Presentation Foundation (WPF) uygulaması oluşturacaksınız. İzlenecek yol çeşitli zamanlama sorunları ve yeniden düzenlemeyi denetleme tarafından kırılan testleri düzeltmeye ilişkin çözümler sağlar.  
  
###  <a name="starting"></a>Başlatma ve durdurma test altındaki uygulama  
 *My uygulama, tarayıcı veya veritabanı her test için ayrı ayrı durdurmak ve başlatmak istediğiniz yok. Nasıl kaçının?*  
  
-   ![Prerequsite](../test/media/prereq.png "önkoşul") test altındaki uygulamanızı başlatmak için eylemleri kaydetmek istemiyorsanız, seçmeden önce uygulamanızın başlamalıdır **kaydı** simgesi.  
  
-   ![Prerequsite](../test/media/prereq.png "önkoşul")test sonunda test çalıştığı işlem sonlandırıldı. Uygulamanızı test başladıysanız, uygulama genellikle kapatır.  Çıktığında uygulamanız kapatmak için test istemiyorsanız, çözümünüz ve kullanmak için .runsettings dosyasını eklemelisiniz `KeepExecutorAliveAfterLegacyRun` seçeneği. Daha fazla bilgi için bkz: [.runsettings dosyasını kullanarak birim testlerini yapılandırma](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).  
  
-   ![Prerequsite](../test/media/prereq.png "önkoşul") her test yönteminin başlangıcında kod çalışır [TestInitialize] özniteliği tarafından tanımlanan bir test başlatma yöntemi ekleyebilirsiniz. Örneğin, uygulamayı TestInitialize yönteminden başlatmak.  
  
-   ![Prerequsite](../test/media/prereq.png "önkoşul") her test yönteminin sonunda kodu çalıştıran [TestCleanup] özniteliği tarafından tanımlanan bir test temizleme yöntemi ekleyebilirsiniz. Örneğin, uygulamayı kapatmak için bu yöntem TestCleanup yönteminden çağrılabilir.  
  
###  <a name="VerifyingCodeUsingCUITGenerateAssertions"></a>Kullanıcı Arabirimi denetimlerini doğrulanıyor  
 Kullanabileceğiniz **kodlanmış UI Test oluşturucusunu** bir kullanıcı arabirimi (UI) denetim eklemek için <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> testiniz için ya da bir onaylama UI denetim için kullandığı bir doğrulama yöntemi için kod oluşturmak için.  
  
 Onaylamaları için kullanıcı Arabirimi denetimlerini oluşturmak için seçin **eklemek onaylar** aracı kodlanmış UI Test derleyicisini ve doğrulamak istediğiniz test altındaki uygulama denetimine doğru sürükleyin. Denetim kutusu özetlenmektedir, fareyi bırakın. Denetim sınıfı kodu hemen oluşturulan `UIMap.Designer.cs` dosyası.  
  
 ![Kodlanmış UI testi öğesi hedefleme](../test/media/codedui_1.png "CodedUI_1")  
  
 Bu denetim için özellikleri artık listelenen **eklemek onaylar** iletişim kutusu.  
  
 Belirli bir denetim için gezinme başka bir yolu oku seçmektir **(<<)** görünümünü genişletmek için **UI denetim eşlemesi**. Bir üst, eşdüzey veya alt denetim bulmak için harita üzerinde herhangi bir yere tıklayın ve ağaç taşımak için ok tuşlarını kullanın.  
  
 ![Kodlanmış UI testi özellikleri](../test/media/codedui_2.png "CodedUI_2")  
  
-   *Herhangi bir özellik uygulamamda denetim seçtiğim ya da denetim UI denetim eşlemesindeki ifadesini görmüyorsanız bkz yok.*  
  
     Uygulama kodunda doğrulamak istediğiniz denetim bir HTML kimliği öznitelik veya bir WPF UId gibi benzersiz bir kimliği olmalı. Bu kimlikleri eklemek için uygulama kodu güncelleştirmeniz gerekebilir.  
  
 Ardından, özelliği doğrulayın ve ardından istediğiniz UI denetimi için kısayol menüsünden açmak **onay Ekle**. İçinde **onay Ekle** iletişim kutusunda **karşılaştırıcı** örneğin değerinizi <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A>ve değeri değerinizi içinde yazın **karşılaştırma değeri**.  
  
 ![Kodlanmış UI testi onaylar](../test/media/codedui_3.png "CodedUI_3")  
  
 Testiniz için tüm onayları eklendiğinde seçin **Tamam**.  
  
 Onayları kodunu oluşturmak ve denetimi UI eşlemesine eklemek için tercih **kodu oluştur** simgesi. Kodlanmış UI test yönteminiz için bir ad ve açıklamalar yöntemi olarak eklenecek yöntemi için bir açıklama yazın. Seçin **ekleme ve oluşturma**. Ardından, seçin **kapatmak** kapatmak için simgesini **kodlanmış UI Test derleyicisini**. Aşağıdaki kodu benzer bir kod oluşturur. Örneğin, girdiğiniz adı ise `AssertForAddTwoNumbers`, kod aşağıdaki gibi görünür:  
  
-   Kodlanmış UI test dosyanız test yöntemine AssertForAddTwoNumbers assert yöntemine bir çağrı ekler:  
  
    ```  
    [TestMethod]  
    public void CodedUITestMethod1()  
    {  
        this.UIMap.AddTwoNumbers();  
        this.UIMap.AssertForAddTwoNumbers();  
    }  
    ```  
  
     Onaylar ve adımları sırasını değiştirmek için ya da yeni test yöntemleri oluşturmak için bu dosyayı düzenleyebilirsiniz. Daha fazla kod eklemek için yer imleci test yöntemi ve kısayol menüsünde seçin **kodlanmış UI testi için kod üret**.  
  
-   Adlı bir yöntem ekler `AssertForAddTwoNumbers` UI eşlemenize (UIMap.uitest). Bu dosya kodlanmış UI testi onaylar düzenleyebileceğiniz Düzenleyicisi'nde açılır.  
  
     ![Düzen assert kodlanmış UI Test Düzenleyicisi'ni kullanarak](../test/media/cuit_editor_assert.png "CUIT_Editor_assert")  
  
     Daha fazla bilgi için bkz: [kodlanmış UI Test Düzenleyicisi'ni kullanarak düzenleme kodlanmış UI testlerini](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).  
  
     Oluşturulan kod onaylama yönteminin içinde UIMap.Designer.cs de görüntüleyebilirsiniz. Ancak, bu dosyayı düzenlemeniz değil. Kodu uyarlanmış bir sürümünü yapmak istiyorsanız, yöntemleri UIMap.cs gibi başka bir dosyaya kopyalayın, yöntemleri yeniden adlandırın ve bunları düzenleyin.  
  
    ```  
    public void AssertForAddTwoNumbers()  
    {  
        ...  
    }  
    ```  
  
 *Seçmek istediğiniz denetim odağı kaybettiğinde ve kodlanmış UI Test Oluşturucusu'ndan eklemek onaylar Aracı'nı seçmek çalıştığınızda kaybolur. Denetim nasıl seçer?*  
 **Klavyeyi kullanarak gizli bir denetim seçme**  
  
 Bazen, [denetimler ekleme ve bunların özelliklerini doğrulama](#VerifyingCodeUsingCUITGenerateAssertions), klavye kullanmanız gerekebilir. Örneğin, bir bağlam menüsü denetimi kullanan kodlanmış bir UI testi kaydetmeye çalıştığınızda denetiminde menü öğeleri listesi odak kaybeder ve kodlanmış UI Test oluşturucusunu ekleme onaylar Aracı'nı seçmek çalıştığınızda kaybolur. Bu, Internet Explorer'da bağlam menüsünde burada ve odak kaybeder eklemek onaylar aracıyla seçmeye çalışırsanız kayboluyor aşağıdaki çizimde gösterilmiştir.  
  
 ![CodedUITest &#95; SelectControlKeyboard](../test/media/codeduitest_selectcontrolkeyboard.png "CodedUITest_SelectControlKeyboard")  
  
 UI denetim seçmek için klavyeyi kullanmak için Denetim fareyle üzerine gelerek. Ardından basılı **Ctrl** anahtarı ve **ı** aynı zamanda anahtar. Tuşları serbest bırakın. Denetim kodlanmış UT Test Oluşturucusu tarafından kaydedilir.  
  
> [!WARNING]
>  Microsoft Lync kullanırsanız, kodlanmış UI Test derleyicisini başlamadan önce Lync kapatmanız gerekir. Microsoft Lync uğratan ile **Ctrl + ı** klavye kısayolu.  
  
 *Bir denetim fare gidildiğinde kayıt yapamazsınız. Bu geçici bir yolu var mı?*  
 **El ile kayıt fare gezinen**  
  
 Bazı durumlarda, kullanılmakta olan belirli bir denetim kodlanmış bir UI testi el ile kayıt fare vurgulu olayları için klavyeyi kullanma gerektirebilir. Örneğin, bir Windows formu veya bir Windows Presentation Foundation (WPF) uygulamasını test ettiğinizde olabilir özel kod. Veya, bir kullanıcı üzerine geldiğinde genişleyen bir ağaç düğümü gibi bir denetim üzerine getirildiğinde için tanımlanan özel davranış olabilir. Bu gibi durumlarda sınamak için el ile kodlanmış UI Test tuşlarına basarak denetimin üzerine getirildiğinde Oluşturucu klavye tuşlarını önceden tanımlanmış bildirim sahip.  
  
 Kodlanmış UI testi gerçekleştirdiğinizde, denetimin üzerine gelin. Tuşuna basın ve Ctrl, basılı klavyenizde kaydırma ve R tuşlarını basılı tutarak. Tuşları serbest bırakın. Fare vurgulu olay kodlanmış UT Test Oluşturucusu tarafından kaydedilir.  
  
 ![CodedUI &#95; Vurgulu](../test/media/codedui_hover.png "CodedUI_Hover")  
  
 Test yöntemi oluşturduktan sonra aşağıdaki örneğe benzer bir kod UIMap.Desinger.cs dosyasına eklenecek:  
  
```csharp  
// Mouse hover '1' label at (87, 9)  
Mouse.Hover(uIItem1Text, new Point(87, 9));  
  
```  
  
 *Fare vurgulu olaylarını yakalamak için anahtar atama başka bir yerde my ortamda kullanılıyor. Varsayılan anahtar atama değiştirebilir miyim?*  
 **Fare vurgulu klavye atamalarını yapılandırma**  
  
 Gerekirse, Ctrl + Shift + kodlanmış UI testlerinde fare vurgulama olayları uygulamak için kullanılan R varsayılan klavye atamasının farklı anahtarları kullanmak için yapılandırılabilir.  
  
> [!WARNING]
>  Normal koşullar altında fare vurgulu olayları klavye atamalarını değiştirmek olmamalıdır. Klavye atama yeniden atama dikkatli olun. Tercih ettiğiniz zaten başka bir yerde Visual Studio ya da test edilen uygulamanın içinde kullanımda olabilir.  
  
 Klavye atamalarını değiştirmek için aşağıdaki yapılandırma dosyasını değiştirmeniz gerekir:  
  
 `<drive letter:>\Program Files (x86)\Microsoft Visual Studio 11.0\Common7\IDE\CodedUITestBuilder.exe.config`  
  
 Yapılandırma dosyasında değerlerini değiştirmek `HoverKeyModifier` ve `HoverKey` anahtarları klavye atamalarını değiştirmek için:  
  
```  
<!-- Begin : Background Recorder Settings -->  
<!-- HoverKey to use. -->  
<add key="HoverKeyModifier" value="Control, Shift"/>  
<add key="HoverKey" value="R"/>  
  
```  
  
 *Fare gezinen bir Web sitesinde kaydı sorunlar yaşıyorum. Bir düzeltme bu için çok var?*  
 **Web tarayıcısı ayarı örtük fare gezinen**  
  
 Belirli bir denetime geldiğinizde birçok Web sitesi bu ek ayrıntılar göstermek için genişletir. Genellikle, bu Masaüstü uygulamaları menülerde gibi arayın. Bu genel bir desen olduğundan, Web'e gözatma için örtük gezinen kodlanmış UI testleri etkinleştirin. Örneğin, Internet Explorer'da, kayıt gezinen, bir olay tetiklenir. Bu olaylar için yedek gezinen kaydedilen yol açabilir. Bu nedenle, örtük gezinen ile kaydedilir `ContinueOnError` kümesine `true` UI testi yapılandırma dosyası. Bu kayıttan yürütmenin vurgulu olay başarısız olursa devam etmesini sağlar.  
  
 Örtük gezinen bir Web tarayıcısında kaydını etkinleştirmek için yapılandırma dosyasını açın:  
  
 `<drive letter:>\Program Files (x86)\Microsoft Visual Studio 11.0\Common7\IDE\CodedUITestBuilder.exe.config`  
  
 Yapılandırma dosyası anahtar olduğunu doğrulayın `RecordImplicitiHovers` kümesine bir değerine `true` aşağıdaki örnekte gösterildiği gibi:  
  
```  
<!--Use this to enable/disable recording of implicit hovers.-->  
<add key="RecordImplicitHover" value="true"/>  
  
```  
  
##  <a name="VerifyingCodeCUITModify"></a>Kodlanmış UI testi özelleştirme  
 Kodlanmış UI testi oluşturduktan sonra Visual Studio aşağıdaki araçlardan birini kullanarak düzenleyebilirsiniz:  
  
-   **Kodlanmış UI Test derleyicisini:** kodlanmış UI Test derleyicisini ek denetimleri ve doğrulama testlerinizi eklemek için kullanın. Bölümüne bakın [denetimler ekleme ve bunların özelliklerini doğrulama](#VerifyingCodeUsingCUITGenerateAssertions) bu konuda.  
  
-   **Kodlanmış UI Test Düzenleyicisi:** kodlanmış UI Test Düzenleyicisi'ni kolayca kodlanmış UI testleri değiştirmenize olanak tanır. Kodlanmış UI Test Düzenleyicisi'ni kullanarak bulun, görüntülemek ve test yöntemlerinizi düzenleyin. Ayrıca, kullanıcı Arabirimi eylemlerini ve UI denetim eşlemesindeki ilişkili denetimlerini düzenleyebilirsiniz. Daha fazla bilgi için bkz: [kodlanmış UI Test Düzenleyicisi'ni kullanarak düzenleme kodlanmış UI testlerini](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).  
  
-   **Kod Düzenleyicisi:**  
  
    -   Bölümünde açıklandığı gibi denetimler için kod testinizde el ile eklemeniz [kodlama kullanıcı Arabirimi denetim eylemleri ve özelliklerini](#VerifyingCodeCUITActionsandProperties) bölümüne bakın.  
  
    -   Kodlanmış UI testi oluşturduktan sonra veri güdümlü olacak şekilde değiştirebilirsiniz. Daha fazla bilgi için bkz: [veri-odaklı kodlanmış UI testi oluşturma](../test/creating-a-data-driven-coded-ui-test.md).  
  
    -   İçinde kodlanmış bir UI Testi kayıttan, kaybolur ve benzeri için ilerleme çubuğu oluşmasına görünmesi için bir pencere gibi belirli olaylar için beklenecek test söyleyebilirsiniz. Bunu yapmak için uygun UITestControl.WaitForControlXXX() yöntemini ekleyin. Kullanılabilir yöntemleri tam bir listesi için bkz: [yapmadan kodlanmış UI testleri beklemek için belirli olayları sırasında kayıttan yürütme](../test/making-coded-ui-tests-wait-for-specific-events-during-playback.md). Bir denetim WaitForControlEnabled yöntemini kullanarak etkin olmasını bekler kodlanmış bir UI testi örneği için bkz: [izlenecek yol: oluşturma, düzenleme ve kodlanmış bir UI testi koruma](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md).  
  
    -   Kodlanmış UI testleri bazı Internet Explorer 9 ve Internet Explorer 10 dahil HTML5 denetimler için destek içerir. Daha fazla bilgi için bkz: [kodlanmış UI testlerinde HTML5 denetimleri kullanma](../test/using-html5-controls-in-coded-ui-tests.md).  
  
    -   **Kodlanmış UI testi Kılavuzu kodlama:**  
  
        -   [Kodlanmış UI testinin anatomisi](../test/anatomy-of-a-coded-ui-test.md)  
  
        -   [Kodlanmış UI testleri için en iyi yöntemler](../test/best-practices-for-coded-ui-tests.md)  
  
        -   [Birden çok UI eşlemesi bulunan büyük uygulamaları sınama](../test/testing-a-large-application-with-multiple-ui-maps.md)  
  
        -   [Kodlanmış UI testleri ve eylem kayıtları için desteklenen yapılandırmalar ve platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)  
  
###  <a name="generatedCode"></a>Oluşturulan kod  
 Seçtiğinizde **kodu oluştur**, birkaç kod parçalarını oluşturulur:  
  
-   **Test yöntemi satırda.**  
  
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
  
-   **UIMap.uitest içindeki bir yöntemi**  
  
     Bu yöntem, kaydettiğiniz eylemleri ya da, doğrulanmış değeri ayrıntılarını içerir. Bu kod UIMap.uitest açarak düzenleyebilirsiniz. Silebilir veya yeniden düzenlemeniz kaydedilmiş eylemler bir özelleştirilmiş Düzenleyicisi'nde açar.  
  
     Checked UIMap.Designer.cs içinde de oluşturulan yöntemi görüntüleyin. Bu yöntem testi çalıştırdığınızda kaydettiğiniz eylemleri gerçekleştirir.  
  
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
    >  Daha fazla testleri oluşturduğunuzda, yeniden oluşturulacak olduğundan, bu dosyayı düzenleme yapmamanız gerekir.  
  
     Bu yöntemlerin uyarlanmış sürümleri için UIMap.cs kopyalayarak yapabilirsiniz. Örneğin, bir test yöntemi çağırabilirsiniz parametreli bir sürüm yapabilirsiniz:  
  
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
  
-   **UIMap.uitest bildirimlerinde**  
  
     Bu bildirimler, test tarafından kullanılan UI denetimleri uygulamanın temsil eder. Tarafından oluşturulan kodu bunlar denetimleri çalışır ve bunların özelliklerine erişmek için kullanılır.  
  
     Kendi kodunuzu yazarsanız, ayrıca bunları kullanabilirsiniz. Örneğin, bir Web uygulamasında bir köprü seçin, metin kutusuna bir değer yazın veya dal ve bir alandaki bir değere göre farklı test eylemleri test yönteminize olabilir.  
  
     Birden çok kodlanmış UI testleri ve birden çok UI haritası nesneleri ve büyük uygulamaları sınama kolaylaştırmak için dosyaları ekleyebilirsiniz. Daha fazla bilgi için bkz: [birden çok UI eşlemesi bulunan büyük uygulamaları sınama](../test/testing-a-large-application-with-multiple-ui-maps.md).  
  
 Oluşturulan kodun hakkında daha fazla bilgi için bkz: [kodlanmış UI testinin anatomisi](../test/anatomy-of-a-coded-ui-test.md).  
  
###  <a name="actions"></a>Kullanıcı Arabirimi denetim eylemleri ve özelliklerini kodlama  
 UI test denetimleri ile çalışırken kodlanmış UI testleri, iki bölüme ayrılır: Eylemler ve özellikler.  
  
-   İlk bölümü UI test denetimleri üzerinde gerçekleştirebileceğiniz eylemler oluşur. Örneğin, kodlanmış UI testleri bir UI testi denetimi fare tıklamaları benzetimini yapmak veya bir UI testi denetimini etkilemek için klavyede yazılan anahtarları benzetimi.  
  
-   İkinci bölümü, almak ve bir UI testi denetimde özelliklerini ayarlamak sağlamadan oluşur. Örneğin, kodlanmış UI testleri öğelerinin sayısı elde edebilirsiniz bir `ListBox`, veya bir `CheckBox` seçili duruma.  
  
 **UI Test denetiminin eylemler erişme**  
  
 UI test denetimlerinde fare tıklamaları veya klavye eylemleri gibi eylemleri gerçekleştirmek için yöntemleri kullanın <xref:Microsoft.VisualStudio.TestTools.UITesting.Mouse> ve <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard> sınıfları:  
  
-   Bir tıklatma bir UI testi denetimde gibi Fare yönelimli bir eylem gerçekleştirmek için kullandığınız <xref:Microsoft.VisualStudio.TestTools.UITesting.Mouse.Click%2A>.  
  
     `Mouse.Click(buttonCancel);`  
  
-   Gibi bir düzenleme denetimine yazarak bir klavye odaklı eylemi gerçekleştirmek için kullandığınız <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard.SendKeys%2A>.  
  
     `Keyboard.SendKeys(textBoxDestination, @"C:\Temp\Output.txt");`  
  
 **UI Test denetiminin özelliklerine erişme**  
  
 Almak ve UI denetimi belirli özellik değerlerini ayarlamak için doğrudan almak veya değerlerin bir denetimin özelliklerini ayarlamak veya kullanabileceğiniz <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.GetProperty%2A?displayProperty=fullName> ve <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.SetProperty%2A?displayProperty=fullName> yöntemleri kullanılarak almak veya ayarlamak istediğiniz belirli özelliğinin adı.  
  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.GetProperty%2A>ardından uygun atanabilecek bir nesne döndürür <xref:System.Type>. <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.SetProperty%2A>bir nesne için özellik değeri kabul eder.  
  
##### <a name="to-get-or-set-properties-from-ui-test-controls-directly"></a>Almak veya özellikler UI test denetimlerinden doğrudan ayarlamak için  
  
-   T:Microsoft.VisualStudio.TestTools.UITesting.HtmlControls.HtmlList veya T: gibi t:Microsoft.VisualStudio.TestTools.UITesting.UITestControl'dan öğesinden türetilen denetimlerle Microsoft.VisualStudio.TestTools.UITesting.WinControls.WinComboBox, almak ya da özellik değerlerine doğrudan, aşağıdaki gibi ayarlayın:  
  
    ```  
    int i = myHtmlList.ItemCount;  
    myWinCheckBox.Checked = true;  
    ```  
  
##### <a name="to-get-properties-from-ui-test-controls"></a>UI test denetimlerinden özellikleri almak için  
  
-   Bir özellik değeri denetimden almak için <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.GetProperty%2A>.  
  
-   Almak üzere denetimin özelliğini belirtmek için uygun dize kullanın `PropertyNames` her denetim için parametre olarak sınıfında <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.GetProperty%2A>.  
  
-   <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.GetProperty%2A>uygun veri türünü, ancak bu dönüş değeri olarak atandığında döndürür bir <xref:System.Object>. Dönüş <xref:System.Object> sonra uygun türe gerekir.  
  
     Örnek:  
  
     `int i = (int)GetProperty(myHtmlList.PropertyNames.ItemCount);`  
  
##### <a name="to-set-properties-for-ui-test-controls"></a>UI özelliklerini ayarlamak için denetimleri testi  
  
-   Bir denetimde bir özelliğini ayarlamak için kullanın <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.SetProperty%2A>.  
  
-   Ayarlamak için denetimin özelliğini belirtmek için uygun dize kullanın `PropertyNames` sınıfı ilk parametre olarak <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.SetProperty%2A>, ikinci parametre olarak özellik değerine sahip.  
  
     Örnek:  
  
     `SetProperty(myWinCheckBox.PropertyNames.Checked, true);`  
  
###  <a name="debugging"></a>Hata ayıklama  
 Kodlanmış UI test günlüklerini kullanarak kodlanmış UI testlerini analiz edebilirsiniz. Kodlanmış UI test günlüklerini filtresi ve kayıt kodlanmış UI testi hakkında önemli bilgiler çalıştırır. Günlükleri biçimi hızla hatalarını ayıklamanıza olanak tanır. Daha fazla bilgi için bkz: [çözümleme kodlanmış UI testleri kullanarak kodlanmış UI Test günlüklerini](../test/analyzing-coded-ui-tests-using-coded-ui-test-logs.md).  
  
##  <a name="VerifyCodeUsingCUITWhatsNext"></a>Sonraki adım nedir?  
 **Kodlanmış UI testleri çalıştırmak için ek seçenekler:** bu konunun önceki kısımlarında açıklandığı gibi doğrudan Visual Studio'dan kodlanmış UI testleri çalıştırabilirsiniz. Ayrıca, otomatikleştirilmiş UI testleri çalıştırabilirsiniz [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)], veya [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)]. Kodlanmış UI testleri otomatik, bunları, diğer otomatikleştirilmiş testleri farklı olarak çalıştırdığınızda, masaüstü ile etkileşimine izin sahiptirler.  
  
-   [Nasıl yapılır: Microsoft Visual Studio'dan testler çalıştırma](http://msdn.microsoft.com/Library/1a1207a9-2a33-4a1e-a1e3-ddf0181b1046)  
  
-   [Otomatikleştirilmiş testleri Microsoft Test Yöneticisi'nde çalıştırma](http://msdn.microsoft.com/en-us/0632f265-63fe-4859-a413-9bb934c66835)  
  
-   [Nasıl yapılır: yapılandırma ve uygulamanızı oluşturduktan sonra zamanlanmış testleri çalıştırma](http://msdn.microsoft.com/en-us/32acfeb1-b1aa-4afb-8cfe-cc209e6183fd)  
  
-   [Yapı işleminizin testleri çalıştırma](http://msdn.microsoft.com/Library/d05743a1-c5cf-447e-bed9-bed3cb595e38)  
  
-   [Komut satırından otomatikleştirilmiş testleri](/devops-test-docs/test/running-automated-tests-from-the-command-line)  
  
-   [Nasıl yapılır: Masaüstü ile etkileşimi olan testleri çalıştırmak için Test aracınızı ayarlama](http://msdn.microsoft.com/Library/3a94dd07-6d17-402c-ae8f-7947143755c9)  
  
-   [&#91; kullanımdan &#93; Yük testlerinde kodlanmış UI testleri kullanma](/devops-test-docs/test_notintoc/using-coded-ui-tests-in-load-tests)  
  
 **Özel denetimler için destek ekleyen:** kodlanmış UI Test Çerçevesi olası her UI desteklemez ve test etmek istediğiniz kullanıcı arabirimini desteklemiyor olabilir. Örneğin, hemen kodlanmış UI testi için UI oluşturamazsınız [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)]. Ancak, özel bir denetim destekleyecek kodlanmış UI Test Çerçevesi uzantısı oluşturabilirsiniz.  
  
-   [Denetimlerinizin kodlanmış UI testlerini etkinleştirme](../test/enable-coded-ui-testing-of-your-controls.md)  
  
-   [Kodlanmış UI testleri ve Eylem kayıtlarını Microsoft Excel'i desteklemek için genişletme](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)  
  
 Kodlanmış UI testleri genellikle el ile testleri otomatikleştirmek için kullanılır. Ek yönergeler için bkz: [Visual Studio 2012 - bölüm 5 ile sürekli teslimat için test etme: Sistem testlerini otomatikleştirme](http://go.microsoft.com/fwlink/?LinkID=255196). El ile testleri hakkında daha fazla bilgi için bkz: [&#91; kullanımdan &#93; Microsoft Test Yöneticisi'ni kullanarak el ile Test çalışmaları oluşturma](/devops-test-docs/test_notintoc/creating-manual-test-cases-using-microsoft-test-manager). Otomatikleştirilmiş Sistem testleri hakkında daha fazla bilgi için bkz: [oluşturma otomatikleştirilmiş testleri Microsoft Test Yöneticisi kullanarak](http://msdn.microsoft.com/en-us/7b5075ee-ddfe-411d-b1d4-94283550a5d0).  
  
## <a name="external-resources"></a>Dış Kaynaklar  
  
### <a name="guidance"></a>Kılavuz  
 [Visual Studio 2012 - bölüm 2 ile sürekli teslimat için test etme: birim testi: iç test etme](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
 [Visual Studio 2012 - bölüm 5 ile sürekli teslimat için test etme: Sistem testlerini otomatikleştirme](http://go.microsoft.com/fwlink/?LinkID=255196)  
  
### <a name="faq"></a>SSS  
 [SSS - 1 kodlanmış UI testleri](http://go.microsoft.com/fwlink/?LinkID=230576)  
  
 [Kodlanmış UI testleri ile ilgili SSS -2](http://go.microsoft.com/fwlink/?LinkID=230578)  
  
### <a name="forum"></a>Forum  
 [Visual Studio UI Otomasyon (CodedUI içerir) test etme](http://go.microsoft.com/fwlink/?LinkID=224497)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap>   
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>   
 [Kod kalitesini geliştirme](../test/improve-code-quality.md)   
 [İzlenecek yol: Oluşturma, düzenleme ve kodlanmış UI testi sürdürme](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)   
 [Kodlanmış UI testinin anatomisi](../test/anatomy-of-a-coded-ui-test.md)   
 [Kodlanmış UI testleri için en iyi yöntemler](../test/best-practices-for-coded-ui-tests.md)   
 [Birden çok UI eşlemesi bulunan büyük uygulamaları sınama](../test/testing-a-large-application-with-multiple-ui-maps.md)   
 [Kodlanmış UI Test Düzenleyicisi'ni kullanarak kodlanmış UI testlerini düzenleme](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md)   
 [Kodlanmış UI testleri ve eylem kayıtları için desteklenen yapılandırmalar ve platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)   
 [Visual Studio 2010'dan kodlanmış UI testlerini yükseltme](../test/upgrading-coded-ui-tests-from-visual-studio-2010.md)   
 [Varolan eylem kaydından kodlanmış UI testi oluşturma](/devops-test-docs/test/generating-a-coded-ui-test-from-an-existing-action-recording)
