---
title: "Kodlanmış UI testleri kodlanmış UI Test Düzenleyicisi'ni kullanarak düzenleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codedUItest.testeditor
helpviewer_keywords: coded UI test, Coded UI Test Editor
ms.assetid: 76435c4b-593e-43a3-a9fe-709a7f9f5e0f
caps.latest.revision: "40"
ms.author: douge
manager: douge
ms.openlocfilehash: 637bf6a6e52943e2eae247bbe5a40e10c2d3742d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="editing-coded-ui-tests-using-the-coded-ui-test-editor"></a>Kodlanmış UI Test Düzenleyicisi'ni Kullanarak Kodlanmış UI Testlerini Düzenleme
Kodlanmış UI Test Düzenleyicisi'ni kolayca kodlanmış UI testleri değiştirmenize olanak tanır. Kodlanmış UI Test Düzenleyicisi'ni kullanarak bulun, görüntülemek ve test yöntemleri ve UI eylemlerini özelliklerini düzenleyin. Ayrıca, görüntülemek ve bunların karşılık gelen denetimleri düzenlemek için kullanıcı Arabirimi denetim eşlemesi kullanabilirsiniz.  
  
 **Gereksinimler**  
  
-   Visual Studio Enterprise  
  
## <a name="why-should-i-do-this"></a>Neden bunu yapmam gerekir?  
 Kodlanmış UI Test Düzenleyicisi'ni kullanarak daha hızlı ve kod düzenleyicisini kullanarak kodlanmış UI test yöntemlerinizi kod düzenleme daha etkilidir. Kodlanmış UI Test Düzenleyicisi ile hızla bulup UI eylemlerini ve denetimleri ile ilgili özellik değerlerini değiştirmek için araç ve kısayol menüleri kullanabilirsiniz. Örneğin, aşağıdaki komutları gerçekleştirmek için kodlanmış UI Test Düzenleyicisi araç kullanabilirsiniz:  
  
 ![UI Test Düzenleyicisi](../test/media/uitesteditor.png "UITestEditor")  
  
1.  [Bul](../ide/finding-and-replacing-text.md) UI eylemlerini ve denetimlerini bulmanıza yardımcı olur.  
  
2.  [Silme](#CodedUITestEditor_DeleteUIActions) istenmeyen UI eylemlerini kaldırır.  
  
3.  **Yeniden Adlandır** test yöntemleri ve denetimler için adlar değiştirir.  
  
4.  **Özellikler** seçili öğe için Özellikler penceresini açar.  
  
5.  [Yeni bir yöntemi bölme](#CodedUITestEditor_SplitMethods) UI eylemlerini modülarize etmek olanak tanır.  
  
6.  [Kod taşıma](#CodedUITestEditor_MoveMethods) test yöntemlerinizi özel kod ekler.  
  
7.  [Gecikme önce Ekle](#CodedUITestEditor_InsertDelay) milisaniye cinsinden belirtilen bir UI eyleminden önce bir duraklama ekler.  
  
8.  [UI denetimi bulun](#CodedUITestEditor_LocateUIControl) test altında uygulamanın kullanıcı arabiriminde denetimin konumunu tanımlar.  
  
9. [Tüm bulun](#CodedUITestEditor_LocateDecendants) yardımcı doğrulamak için denetim özelliği ve uygulamanın denetimleri önemli bir değişiklik.  
  
## <a name="how-do-i-do-this"></a>Bunu nasıl yaparım?  
 İçinde [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], kodlanmış UI test projenizdeki kodlanmış UI testi ilişkide UIMap.uitest dosyası açılırken otomatik olarak görüntüler kodlanmış UI testi kodlanmış UI Test Düzenleyicisi'nde. Aşağıdaki yordamlar nasıl sonra bulun ve test yöntemleri ve UI eylemlerini ve Düzenleyicisi araç ve kısayol menülerini kullanarak denetim özelliklerini düzenleme açıklar.  
  
## <a name="open-a-coded-ui-test"></a>Kodlanmış UI testi  
 Görüntüleme ve düzenleme, Visual C# ve Visual Basic tabanlı kodlanmış UI testi kodlanmış UI Test Düzenleyicisi'ni kullanarak.  
  
 ![Bağlam menüsü düzenleme ile kodlanmış UI Test derleyicisini](../test/media/editcodeduitest.png "EditCodedUITest")  
  
 Çözüm Gezgini'nde için kısayol menüsünü açın **UIMap.uitest** ve **açmak**. Kodlanmış UI testi kodlanmış UI Test Düzenleyicisi'nde görüntülenir. Şimdi, görüntüleyin ve kaydedilen yöntemler, eylemleri ve kodlanmış UI testi karşılık gelen denetimlerinde düzenleyin.  
  
> [!TIP]
>  Bir yöntemin bulunan bir UI eyleminden seçtiğinizde **UI eylemlerini** bölmesinde, ilgili denetim vurgulanmış. UI eylem veya denetim özelliklerini de değiştirebilirsiniz.  
  
 *Görmüyorum* kodlanmış UI Test Düzenleyicisi'ni.  
 Visual Studio Enterprise sürümünü 2012'den önceki kullanıyor. Kodlanmış UI Test Düzenleyicisi'ni de bir MSDN aboneliğiniz ile Visual Studio 2010 Özellik Paketi 2'de kullanılabilir. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Microsoft Visual Studio 2010 Feature Pack 2](http://go.microsoft.com/fwlink/?LinkID=204119).  
  
##  <a name="CodedUITestEditor_EditActionAndControlProperties"></a>UI eylem özelliklerini ve bunların karşılık gelen denetim özelliklerini değiştir  
 Kodlanmış UI Test Düzenleyicisi'ni kullanarak hızlı bir şekilde bulun ve tüm UI eylemlerini test yöntemlerinizi görüntüleyin. Düzenleyicide UI eylemi seçtiğinizde, ilgili denetim otomatik olarak vurgulanır. Benzer şekilde, bir denetim seçerseniz, ilişkili UI eylemlerini vurgulanır. Bir UI eyleminden veya bir denetim seçin, ardından ile karşılık gelen özelliklerini değiştirmek için Özellikler penceresini kullanın çok kolaydır.  
  
 ![UI eylem özelliklerini](../test/media/codeduiedituiaction.png "CodedUIEditUIAction")  
UI eylem özelliklerini düzenleme  
  
 UI eylem özelliklerini değiştirmek için **UI eylem** bölmesinde UI eylem özelliklerini, select düzenlemek istediğiniz bir UI eyleminden içeren test yöntemi genişletin ve ardından Özellikler penceresini kullanarak özelliklerini değiştirin.  
  
 Örneğin, bir sunucu kullanılamaz ve Web tarayıcınız ile ilişkili bir UI eyleminden sahip belirten **'http://Contoso1/default.aspx' Web sayfasına gidin**, URL'ye değişebilir `'http://Contoso2/default.aspx'`.  
  
 ![Denetim Özellikleri](../test/media/codeduitestcontrolprop.png "CodedUITestControlProp")  
Denetim özelliklerini düzenleme  
  
 Bir denetimin özelliklerini değiştirme UI eylemlerini aynı şekilde yapılır. İçinde **UI denetim eşlemesi** bölmesinde, düzenlemek ve Özellikler penceresini kullanarak özelliklerini değiştirmek için istediğiniz denetimi seçin.  
  
 Örneğin, bir geliştirici değişmiş olabilecek **(ID)** "idSubmit" "idLogin" test uygulaması için kaynak kodundaki düğme denetimi özelliği İle **(ID)** özelliği, uygulama içinde değiştirilen kodlanmış UI testi düğme denetimi bulmak mümkün olmaz ve başarısız olur. Bu durumda, tester açabilirsiniz **arama özellikleri** toplama ve değişiklik **kimliği** Geliştirici uygulamada kullanılan yeni değerle eşleşecek şekilde özelliği. Tester da değiştirebilir **kolay ad** özellik değerine "Gönderme" den "Oturum aç." Bu değişiklik yaparak, ilişkili UI eylem kodlanmış UI Test Düzenleyicisi'nde "Seç 'Gönder' düğmesinden" şekilde güncelleştirilir "Seç 'Oturum açma' düğmesini."  
  
 Değişikliklerinizi tamamladıktan sonra değişiklikleri UIMap.Designer dosyasına seçerek kaydetmek **kaydetmek** üzerinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] araç.  
  
 *Başka ne bilebilirim?*  
 **İpuçları**  
  
-   ![İpucu](../test/media/tip.png "İpucu") Özellikler penceresini görüntülenmiyorsa basılı **Alt** tuşuna sırada **Enter**, veya alternatif olarak basın **F4** .  
  
-   ![İpucu](../test/media/tip.png "İpucu") yaptığınız özellik değişiklikleri geri almak için seçin **geri** gelen **Düzenle** menüsü veya Ctrl + Z tuşlarına basın.  
  
-   ![İpucu](../test/media/tip.png "İpucu") kullanabileceğiniz **Bul** Bul ve Değiştir aracı Visual Studio'da açmak için kodlanmış UI Test Düzenleyicisi araç çubuğu düğmesi. Kodlanmış UI Test Düzenleyicisi'nde bir UI eyleminden bulmak için bulma denetimi sonra kullanabilirsiniz. Örneğin, bulmayı deneyebilirsiniz "tıklatın 'Oturum açma' düğmesini." Bu, büyük testlerinde yararlı olabilir. Bul ve Değiştir aracında kodlanmış UI Test Düzenleyicisi'nde değiştir işlevselliği kullanamayacağınızı unutmayın. Denetim Bul daha fazla bilgi için bkz: [bulma ve değiştirme metnini](../ide/finding-and-replacing-text.md).  
  
-   ![İpucu](../test/media/tip.png "İpucu") bazı durumlarda, bu denetimleri test altında uygulamanın kullanıcı arabiriminde bulunduğu görselleştirmek zor olabilir. Kodlanmış UI Test Düzenleyicisi yeteneklerini UI denetim eşlemesinde listelenen bir denetim seçin ve test altındaki uygulama konumuna görünümünde biridir. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Test altındaki uygulamada bir kullanıcı Arabirimi denetim bulma](#CodedUITestEditor_LocateUIControl) bulunduğu daha aşağıda bu konuda.  
  
-   ![İpucu](../test/media/tip.png "İpucu") düzenlemek istediğiniz denetimi içeren kapsayıcı denetimi genişletmek gerekli olabilir. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Bir denetim ve alt öğeleri bulma](#CodedUITestEditor_LocateDecendants) bulunduğu daha aşağıda bu konuda.  
  
##  <a name="CodedUITestEditor_DeleteUIActions"></a>İstenmeyen UI eylemlerini silme  
 Kodlanmış UI testinizde istenmeyen UI eylemlerini kolayca kaldırabilirsiniz.  
  
 ![UI eylemi silmek](../test/media/codeduideleteuiaction.png "CodedUIDeleteUIAction")  
  
 İçinde **UI eylem** bölmesinde, silmek istediğiniz UI eylem içeren test yöntemi genişletin. UI eylemi için kısayol menüsünü açın ve seçin **silmek**.  
  
##  <a name="CodedUITestEditor_SplitMethods"></a>İki ayrı yöntemlerin içine bölme test yöntemi  
 Bir test yöntemi daraltın veya UI eylemlerini modülarize etmek için bölebilirsiniz. Örneğin, testinizi UI eylemlerini tek test yöntemiyle iki kapsayıcı denetimleri olabilir. UI eylemlerini daha iyi bir kapsayıcı karşılık gelen iki yöntem de modularized olabilir.  
  
 ![Test yöntemi Splt](../test/media/codeduitestsplitmethod1.png "CodedUITestSplitMethod1")  
  
 ![İki test yöntemleri](../test/media/codeduitestsplitmethod2.png "CodedUITestSplitMethod2")  
  
 İçinde **UI eylem** bölmesinde, iki ayrı yöntemlerin içine bölme ve başlamak için yeni bir test yöntemi istediğiniz UI eylem seçmek için istediğiniz test yöntemi genişletin. Ya da UI eylem için kısayol menüsünü açın ve ardından **yeni bir yöntemi bölme**, veya seçin **yeni bir yöntemi bölme** kodlanmış UI Test Düzenleyicisi araç çubuğunda. Yeni bir test yöntemi UI Eylemler bölmesinde görünür. Eylem bölme burada belirttiğiniz Başlangıç UI eylemlerini içerir.  
  
 Tamamlandıktan sonra yöntemi bölme Kaydet değişiklikleri UIMap.Designer dosyasına seçerek **kaydetmek** üzerinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] araç.  
  
 *Başka ne bilebilirim?*  
 **Önemli sorunlar**  
  
-   ![Uyarı simgesi](../test/media/caution.gif "dikkat") **Uyarı:** bir yöntemi bölme de yine de bu UI istiyorsanız oluşturmak üzere olduğunuz yeni yöntemini çağırmak için varolan bir yöntemi çağırır herhangi bir kodu değiştirmeniz gerekir dahil edilen eylemler. Bir yöntemi bölme, Microsoft Visual Studio iletişim kutusu görüntülenir. Ayrıca oluşturmakta olduğunuz yeni yöntemini çağırmak için varolan yöntemini çağırır herhangi bir kod değiştirmelisiniz sizi uyarır. Seçin **Evet**.  
  
 **İpuçları**  
  
-   ![İpucu](../test/media/tip.png "İpucu") bölme geri seçin **geri** gelen **Düzenle** menüsü veya Ctrl + Z tuşlarına basın.  
  
-   ![İpucu](../test/media/tip.png "İpucu") yeni yöntemi yeniden adlandırabilirsiniz. UI Eylemler bölmesinde seçin ve Seç **yeniden adlandırma** kodlanmış UI Test Düzenleyicisi araç çubuğu düğmesi.  
  
     veya  
  
     Yeni test yöntemi ve seçmek için kısayol menüsünü açın **yeniden adlandırma**.  
  
     Microsoft Visual Studio iletişim kutusu görüntülenir. Yönteme başvuran herhangi bir kod değiştirmelisiniz sizi uyarır. Seçin **Evet**.  
  
##  <a name="CodedUITestEditor_MoveMethods"></a>Test yöntemi özelleştirme kolaylaştırmak için UIMap dosyaya Taşı  
 Test yöntemlerinizi birinin karar verirseniz, kodlanmış UI test özel kod gerektirir, UIMap.cs ya da UIMap.vb dosyasına taşımanız gerekir. Aksi takdirde, kodlanmış UI testi derlenmiştir her kodunuzu üzerine yazılır. Yöntem taşımayın, özel kodunuzu test derlenmiştir her zaman üzerine yazılır.  
  
 İçinde **UI eylem** bölmesi, select test kodu ne zaman üzerine olmayacaktır özel kod işlevselliği kolaylaştırmak için UIMap.cs veya UIMap.vb dosyasına taşımak istediğiniz test yöntemi yeniden derlenebileceğini gösterir. Ardından, seçin **taşıma kodu** kodlanmış UI Test Düzenleyicisi araç çubuğunda düğmesini veya test yöntemi için kısayol menüsünü açın ve seçin **taşıma kodu**. Test yöntemi UIMap.uitest dosyasından kaldırılır ve artık UI Eylemler bölmesinde görüntülenmez. Taşıdığınız test dosyasını düzenlemek için Çözüm Gezgini'nde UIMap.cs veya UIMap.vb dosyasını açın.  
  
 Tamamlandıktan sonra yöntemi taşıma Kaydet değişiklikleri UIMap.Designer dosyasına seçerek **kaydetmek** üzerinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] araç.  
  
 *Başka ne bilebilirim?*  
 **Önemli sorunlar**  
  
-   ![Uyarı simgesi](../test/media/caution.gif "dikkat") **Uyarı:** bir yöntem taşınamaz, artık bunu kodlanmış UI Test düzenleyicisini kullanarak düzenleyebilirsiniz. Özel kodunuzu eklemeli ve Kod Düzenleyicisi'ni kullanarak korumalısınız. Bir yöntem taşıdığınızda, Microsoft Visual Studio iletişim kutusu görüntülenir. Bu, yöntemi UIMap.cs UIMap.uitest dosyasından taşınır veya UIMap.vb dosyasını, artık kodlanmış UI Test Düzenleyicisi'ni kullanarak yöntemini düzenlemeniz mümkün olmayacaktır sizi uyarır. Seçin **Evet**.  
  
 **İpuçları**  
  
-   ![İpucu](../test/media/tip.png "İpucu") taşıma geri seçin **geri** gelen **Düzenle** menüsü veya Ctrl + Z tuşlarına basın. Ancak, daha sonra elle kodu UIMap.cs veya UIMap.vb dosyasından kaldırmanız gerekir.  
  
##  <a name="CodedUITestEditor_LocateUIControl"></a>Test altındaki uygulamada bir kullanıcı Arabirimi denetim bulma  
 Bazı durumlarda, denetimleri test altında uygulamanın kullanıcı arabiriminde bulunduğu görselleştirmek zor olabilir. Kodlanmış UI Test Düzenleyicisi yeteneklerini UI denetim eşlemesinde listelenen bir denetim seçin ve test altındaki uygulama konumuna görünümünde biridir. Kullanarak **UI denetimi bulun** test altındaki uygulama özelliği de denetime yaptığınız arama özelliği değişiklikleri doğrulamak için kullanılabilir.  
  
 ![UI denetim bulun](../test/media/codeduilocatecontrol.png "CodedUILocateControl")  
  
 ![Uygulamayı test altında bulunan denetim](../test/media/codeduilocatecontrol2.png "CodedUILocateControl2")  
  
 İçinde **UI denetim eşlemesi** uygulama içinde bulmak istediğiniz denetim testiyle ilişkili bölmesinde seçin. Ardından, denetimi için kısayol menüsünü açın ve ardından **UI denetimi bulun**. Test edilmekte olan uygulamada denetimi ile mavi kenarlık atanmış.  
  
 *Başka ne bilebilirim?*  
 **Önemli sorunlar**  
  
-   ![Uyarı simgesi](../test/media/caution.gif "dikkat") **Uyarı:** UI denetimi bulun önce test ile ilişkili uygulamayı çalıştığını doğrulayın.  
  
 **İpuçları**  
  
-   ![İpucu](../test/media/tip.png "İpucu") alternatif olarak, kullanabileceğiniz **bulun tüm** bir kapsayıcı altında tüm denetimler doğru bulunduğu olduğunu doğrulamak için seçeneği. Bu seçenek bir sonraki bölümde açıklanmıştır.  
  
##  <a name="CodedUITestEditor_LocateDecendants"></a>Bir denetim ve alt öğeleri bulma  
 Bir kapsayıcı altında tüm denetimler test altında uygulamanın kullanıcı arabiriminde doğru bulunabilir doğrulayabilirsiniz. Bu kapsayıcıda yapılan arama özellik değişiklikleri doğrulamaya yardımcı olabilir. Ayrıca, olduysa önemli değişiklikler test altında uygulamanın kullanıcı arabiriminde, var olan denetim arama özellikleri hala doğru olduğunu doğrulayabilirsiniz.  
  
 ![Tüm alt denetimleri bulun](../test/media/codeduilocateall.png "CodedUILocateAll")  
  
 ![Bulunan tüm denetimler](../test/media/codeduilocateall2.png "CodedUILocateAll2")  
  
 İçinde **UI denetim eşlemesi** bölmesinde bulun ve için tüm bağımlı öğelerini görüntülemek istediğiniz kapsayıcı denetimi seçin. Ardından, denetimi için kısayol menüsünü açın ve seçin **bulun tüm**. Kapsayıcı denetimi ve tüm alt denetimlerinden kodlanmış UI Test Düzenleyicisi'nde yeşil bir onay işareti veya 'X' kırmızı ile işaretlenmiştir. Bu işaretler denetimleri test altındaki uygulama başarıyla bulunan varsa size bildirmek.  
  
 *Başka ne bilebilirim?*  
 **Önemli sorunlar**  
  
-   ![Uyarı simgesi](../test/media/caution.gif "dikkat") **Uyarı:** UI denetimleri konumlandırma önce test ile ilişkili uygulamayı çalıştığını doğrulayın.  
  
##  <a name="CodedUITestEditor_InsertDelay"></a>Bir UI eyleminden önce gecikme ekleme  
 Bazı durumlarda, oluşmasına kayboluyor için ilerleme çubuğu görünmesi bir pencere gibi belirli olaylar için bekleyin ve benzeri test yapmak isteyebilirsiniz. Kodlanmış UI Test Düzenleyicisi'ni kullanarak bunu bir UI eyleminden önce gecikme ekleyerek gerçekleştirebilirsiniz. Gecikme olmasını istediğiniz kaç saniye belirtebilirsiniz.  
  
 ![Bir UI eyleminden önce gecikme ekleme](../test/media/codeduidelay.png "CodedUIDelay")  
  
 ![5 saniye ile eklenen gecikme](../test/media/codeduidealy2.png "CodedUIDealy2")  
  
 İçinde **UI eylem** bölmesinde, önce bir gecikme eklemek istediğiniz UI eylem içeren test yöntemi genişletin. UI eylemi seçin. Ardından, UI eylemi için kısayol menüsünü açın ve seçin **gecikme önce Ekle**. Bir gecikme eklenen ve aşağıdaki metinle seçili UI eyleminden önce vurgulanır: **Eylemler arasındaki kullanıcı gecikmesini 1 saniye bekleyin**. Özellikler penceresinde değerini değiştirin **gecikme** milisaniye istenen sayıda özellik.  
  
 Tamamlandıktan sonra gecikme ekleme Kaydet değişiklikleri UIMap.Designer dosyasına seçerek **kaydetmek** üzerinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] araç.  
  
 *Başka ne bilebilirim?*  
 **Notlar**  
  
-   ![Prerequsite](../test/media/prereq.png "önkoşul") belirli bir denetim bir UI eyleminden önce kullanılabilir olduğundan emin olmak gerekiyorsa, uygun UITestControl.WaitForControlXXX() kullanarak test yönteminiz için özel kod eklemeyi düşünmelisiniz yöntem. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Kayıttan yürütme sırasında testleri bekleme belirli olaylar için kodlanmış UI yapma](../test/making-coded-ui-tests-wait-for-specific-events-during-playback.md).  
  
 **İpuçları**  
  
-   ![İpucu](../test/media/tip.png "İpucu") Özellikler penceresini görüntülenmiyorsa tuşunu Enter tuşuna basın veya bunun yerine, F4 tuşuna basılı tutarak Alt.  
  
## <a name="external-resources"></a>Dış kaynaklar  
  
### <a name="guidance"></a>Kılavuz  
 [Visual Studio 2012 - bölüm 2 ile sürekli teslimat için test etme: birim testi: iç test etme](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
### <a name="faq"></a>SSS  
 [SSS - 1 kodlanmış UI testleri](http://go.microsoft.com/fwlink/?LinkID=230576)  
  
 [Kodlanmış UI testleri ile ilgili SSS -2](http://go.microsoft.com/fwlink/?LinkID=230578)  
  
### <a name="forum"></a>Forum  
 [Visual Studio UI Otomasyon (CodedUI içerir) test etme](http://go.microsoft.com/fwlink/?LinkID=224497)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kodunuzu test etmek için UI otomasyonunu kullanma](../test/use-ui-automation-to-test-your-code.md)   
 [Kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate)   
 [Verileri çalışan kodlanmış UI testi oluşturma](../test/creating-a-data-driven-coded-ui-test.md)   
 [Varolan eylem kaydından kodlanmış UI testi oluşturma](/devops-test-docs/test/generating-a-coded-ui-test-from-an-existing-action-recording)   
 [İzlenecek yol: Oluşturma, düzenleme ve kodlanmış UI testi sürdürme](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)
