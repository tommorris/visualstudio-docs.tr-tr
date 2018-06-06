---
title: Kodlanmış UI testlerini düzenleme
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
f1_keywords:
- vs.codedUItest.testeditor
helpviewer_keywords:
- coded UI test, Coded UI Test Editor
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 88c42b710b08ca7dae8d779da3d6e093179ddca6
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34692375"
---
# <a name="edit-coded-ui-tests-using-the-coded-ui-test-editor"></a>Kodlanmış UI Test Düzenleyicisi'ni kullanarak kodlanmış UI testlerini düzenleme

Kodlanmış UI Test Düzenleyicisi'ni kolayca kodlanmış UI testleri değiştirmenize olanak tanır. Kodlanmış UI Test Düzenleyicisi'ni kullanarak bulun, görüntülemek ve test yöntemleri ve UI eylemlerini özelliklerini düzenleyin. Ayrıca, görüntülemek ve bunların karşılık gelen denetimleri düzenlemek için kullanıcı Arabirimi denetim eşlemesi kullanabilirsiniz.

**Gereksinimler**

- Visual Studio Enterprise
- Kodlanmış UI test bileşeni

## <a name="features-of-the-coded-ui-test-editor"></a>Kodlanmış UI Test Düzenleyicisi'nin özellikleri

Kodlanmış UI Test Düzenleyicisi'ni kullanarak daha hızlı ve kod düzenleyicisini kullanarak kodlanmış UI test yöntemlerinizi kod düzenleme daha etkilidir. Kodlanmış UI Test Düzenleyicisi ile hızla bulup UI eylemlerini ve denetimleri ile ilgili özellik değerlerini değiştirmek için araç ve kısayol menüleri kullanabilirsiniz. Örneğin, aşağıdaki komutları gerçekleştirmek için kodlanmış UI Test Düzenleyicisi araç kullanabilirsiniz:

![UI Test Düzenleyicisi](../test/media/uitesteditor.png)

1. [Bul](../ide/finding-and-replacing-text.md) UI eylemlerini ve denetimlerini bulmanıza yardımcı olur.

2. **Silme** istenmeyen UI eylemlerini kaldırır.

3. **Yeniden Adlandır** test yöntemleri ve denetimler için adlar değiştirir.

4. **Özellikler** açılır **özellikleri** penceresinde seçili öğe için.

5. **Yeni bir yöntemi bölme** UI eylemlerini modülarize etmek olanak tanır.

6. **Kod taşıma** test yöntemlerinizi özel kod ekler.

7. **Gecikme önce Ekle** milisaniye cinsinden belirtilen bir UI eyleminden önce bir duraklama ekler.

8. **UI denetimi bulun** test altında uygulamanın kullanıcı arabiriminde denetimin konumunu tanımlar.

9. **Tüm bulun** yardımcı doğrulamak için denetim özelliği ve uygulamanın denetimleri önemli bir değişiklik.

Açtığınızda *UIMap.uitest* dosya bağlı kodlanmış UI testi, kodlanmış UI test açılır ile **kodlanmış UI Test Düzenleyicisi**. Aşağıdaki yordamlar nasıl sonra bulun ve test yöntemleri ve UI eylemlerini ve Düzenleyicisi araç ve kısayol menülerini kullanarak denetim özelliklerini düzenleme açıklar.

## <a name="open-a-coded-ui-test"></a>Kodlanmış UI testi

Görüntüleme ve düzenleme, Visual C# ve Visual Basic tabanlı kodlanmış UI testi kullanılarak **kodlanmış UI Test Düzenleyicisi**.

![Bağlam menüsü düzenleme ile kodlanmış UI Test Oluşturucusu](../test/media/editcodeduitest.png)

İçinde **Çözüm Gezgini**, kısayol menüsünü açın *UIMap.uitest* ve **açmak**. Kodlanmış UI testi görüntülenen **kodlanmış UI Test Düzenleyicisi**. Şimdi, görüntüleyin ve kaydedilen yöntemler, eylemleri ve kodlanmış UI testi karşılık gelen denetimlerinde düzenleyin.

> [!TIP]
> Bir yöntemin bulunan bir UI eyleminden seçtiğinizde **UI eylemlerini** bölmesinde, ilgili denetim vurgulanmış. UI eylem veya denetim özelliklerini de değiştirebilirsiniz.

## <a name="modify-ui-action-and-control-properties"></a>UI eylem ve denetim özelliklerini değiştirme

Kodlanmış UI Test Düzenleyicisi'ni kullanarak hızlı bir şekilde bulun ve tüm UI eylemlerini test yöntemlerinizi görüntüleyin. Düzenleyicide UI eylemi seçtiğinizde, ilgili denetim otomatik olarak vurgulanır. Benzer şekilde, bir denetim seçerseniz, ilişkili UI eylemlerini vurgulanır. Bir UI eyleminden veya bir denetim seçin, ardından ile karşılık gelen özelliklerini değiştirmek için Özellikler penceresini kullanın çok kolaydır.

![UI eylem özelliklerini](../test/media/codeduiedituiaction.png)

UI eylem özelliklerini değiştirmek için **UI eylem** bölmesinde UI eylem özelliklerini, select düzenlemek istediğiniz bir UI eyleminden içeren test yöntemi genişletin ve ardından Özellikler penceresini kullanarak özelliklerini değiştirin.

Örneğin, bir sunucu kullanılamaz ve Web tarayıcınız ile ilişkili bir UI eyleminden sahip belirten **Web sayfasına gidin 'http://Contoso1/default.aspx'**, URL'ye değişebilir `'http://Contoso2/default.aspx'`.

![Denetim Özellikleri](../test/media/codeduitestcontrolprop.png)

Bir denetimin özelliklerini değiştirme UI eylemlerini aynı şekilde yapılır. İçinde **UI denetim eşlemesi** bölmesinde, düzenlemek ve Özellikler penceresini kullanarak özelliklerini değiştirmek için istediğiniz denetimi seçin.

Örneğin, bir geliştirici değişmiş olabilecek **(ID)** "idSubmit" "idLogin" test uygulaması için kaynak kodundaki düğme denetimi özelliği İle **(ID)** özelliği, uygulama içinde değiştirilen kodlanmış UI testi düğme denetimi bulmak mümkün olmaz ve başarısız olur. Bu durumda, tester açabilirsiniz **arama özellikleri** toplama ve değişiklik **kimliği** Geliştirici uygulamada kullanılan yeni değerle eşleşecek şekilde özelliği. Tester da değiştirebilir **kolay ad** özellik değerine "Gönderme" den "Oturum aç." Bu değişiklik yaparak, ilişkili UI eylem kodlanmış UI Test Düzenleyicisi'nde "Seç 'Gönder' düğmesinden" şekilde güncelleştirilir "Seç 'Oturum açma' düğmesini."

Değişikliklerinizi tamamladıktan sonra değişiklikleri UIMap.Designer dosyasına seçerek kaydetmek **kaydetmek** Visual Studio araç.

### <a name="tips"></a>İpuçları

- Varsa **özellikleri** penceresi görüntülenmez, basılı **Alt** tuşuna sırada **Enter**, veya basın **F4**.

- Yaptığınız özellik değişiklikleri geri almak için seçin **geri** gelen **Düzenle** menüsü veya tuşuna **Ctrl**+**Z**.

- Kullanabileceğiniz **Bul** Bul ve Değiştir aracı Visual Studio'da açmak için kodlanmış UI Test Düzenleyicisi araç çubuğu düğmesi. Kodlanmış UI Test Düzenleyicisi'nde bir UI eyleminden bulmak için bulma denetimi sonra kullanabilirsiniz. Örneğin, bulmayı deneyebilirsiniz "tıklatın 'Oturum açma' düğmesini." Bu, büyük testlerinde yararlı olabilir. Bul ve Değiştir aracında kodlanmış UI Test Düzenleyicisi'nde, değiştirme işlevi kullanamazsınız. Denetim Bul daha fazla bilgi için bkz: [bulma ve değiştirme metnini](../ide/finding-and-replacing-text.md).

- Bazı durumlarda, denetimleri test altında uygulamanın kullanıcı arabiriminde bulunduğu görselleştirmek zor olabilir. Kodlanmış UI Test Düzenleyicisi yeteneklerini UI denetim eşlemesinde listelenen bir denetim seçin ve test altındaki uygulama konumuna görünümünde biridir. Daha fazla bilgi için bkz: [Test altındaki uygulamada bir kullanıcı Arabirimi denetim bulma](#CodedUITestEditor_LocateUIControl) bulunduğu daha aşağıda bu makalede.

- Düzenlemek istediğiniz denetimi içeren kapsayıcı denetimi genişletmek gerekli olabilir. Daha fazla bilgi için bkz: [bir denetim ve alt öğeleri bulma](#CodedUITestEditor_LocateDecendants) bulunduğu daha aşağıda bu makalede.

## <a name="delete-unwanted-ui-actions"></a>İstenmeyen UI eylemlerini silme

Kodlanmış UI testinizde istenmeyen UI eylemlerini kolayca kaldırabilirsiniz.

![UI eylemini sil](../test/media/codeduideleteuiaction.png)

İçinde **UI eylem** bölmesinde, silmek istediğiniz UI eylem içeren test yöntemi genişletin. UI eylemi için kısayol menüsünü açın ve seçin **silmek**.

## <a name="split-a-test-method-into-two-separate-methods"></a>İki ayrı yöntemlerin içine bölme test yöntemi

Bir test yöntemi daraltın veya UI eylemlerini modülarize etmek için bölebilirsiniz. Örneğin, testinizi UI eylemlerini tek test yöntemiyle iki kapsayıcı denetimleri olabilir. UI eylemlerini daha iyi bir kapsayıcı karşılık gelen iki yöntem de modularized olabilir.

![Bir test yöntemi bölme](../test/media/codeduitestsplitmethod1.png)

![İki test yöntemleri](../test/media/codeduitestsplitmethod2.png)

İçinde **UI eylem** bölmesinde, iki ayrı yöntemlerin içine bölme ve başlamak için yeni bir test yöntemi istediğiniz UI eylem seçmek için istediğiniz test yöntemi genişletin. Ya da UI eylem için kısayol menüsünü açın ve ardından **yeni bir yöntemi bölme**, veya seçin **yeni bir yöntemi bölme** kodlanmış UI Test Düzenleyicisi araç çubuğunda. Yeni bir test yöntemi UI Eylemler bölmesinde görünür. Eylem bölme burada belirttiğiniz Başlangıç UI eylemlerini içerir.

Tamamlandıktan sonra yöntemi bölme Kaydet değişiklikleri UIMap.Designer dosyasına seçerek **kaydetmek** Visual Studio araç.

> [!WARNING]
> Bir yöntemi bölme, de dahil bu UI eylemlerini yine de istiyorsanız oluşturmak üzere olduğunuz yeni yöntemini çağırmak için varolan bir yöntemi çağırır herhangi bir kodu değiştirmeniz gerekir. Bir yöntemi bölme, Microsoft Visual Studio iletişim kutusu görüntülenir. Ayrıca oluşturmakta olduğunuz yeni yöntemini çağırmak için varolan yöntemini çağırır herhangi bir kod değiştirmelisiniz sizi uyarır. Seçin **Evet**.

### <a name="tips"></a>İpuçları

- Bölünmüş geri seçin **geri** gelen **Düzenle** menüsü veya tuşuna **Ctrl**+**Z**.

- Yeni yöntemi yeniden adlandırabilirsiniz. UI Eylemler bölmesinde seçin ve Seç **yeniden adlandırma** kodlanmış UI Test Düzenleyicisi araç çubuğu düğmesi.

   veya

   Yeni test yöntemi ve seçmek için kısayol menüsünü açın **yeniden adlandırma**.

   Microsoft Visual Studio iletişim kutusu görüntülenir. Yönteme başvuran herhangi bir kod değiştirmelisiniz sizi uyarır. Seçin **Evet**.

## <a name="move-a-test-method-to-the-uimap-file-to-facilitate-customization"></a>Test yöntemi özelleştirme kolaylaştırmak için UIMap dosyaya Taşı

Test yöntemlerinizi birinin karar verirseniz, kodlanmış UI test özel kod gerektirir, UIMap.cs ya da UIMap.vb dosyasına taşımanız gerekir. Aksi takdirde, kodlanmış UI testi derlenmiştir her kodunuzu üzerine yazılır. Yöntem taşımayın, özel kodunuzu test derlenmiştir her zaman üzerine yazılır.

İçinde **UI eylem** bölmesi, select test kodu ne zaman üzerine olmayacaktır özel kod işlevselliği kolaylaştırmak için UIMap.cs veya UIMap.vb dosyasına taşımak istediğiniz test yöntemi yeniden derlenebileceğini gösterir. Ardından, seçin **taşıma kodu** kodlanmış UI Test Düzenleyicisi araç çubuğunda düğmesini veya test yöntemi için kısayol menüsünü açın ve seçin **taşıma kodu**. Test yöntemi UIMap.uitest dosyasından kaldırılır ve artık UI Eylemler bölmesinde görüntülenmez. Taşıdığınız test dosyasını düzenlemek için Çözüm Gezgini'nde UIMap.cs veya UIMap.vb dosyasını açın.

Tamamlandıktan sonra yöntemi taşıma Kaydet değişiklikleri UIMap.Designer dosyasına seçerek **kaydetmek** Visual Studio araç.

> [!WARNING]
> Kodlanmış UI Test Düzenleyicisi'ni kullanarak artık bir yöntem taşınamaz düzenleyebilirsiniz. Özel kodunuzu eklemeli ve Kod Düzenleyicisi'ni kullanarak korumalısınız. Bir yöntem taşıdığınızda, Microsoft Visual Studio iletişim kutusu görüntülenir. Bu, yöntemi UIMap.cs UIMap.uitest dosyasından taşınır veya UIMap.vb dosyasını, artık kodlanmış UI Test Düzenleyicisi'ni kullanarak yöntemini düzenlemeniz mümkün olmayacaktır sizi uyarır. Seçin **Evet**.

### <a name="tips"></a>İpuçları

Taşıma geri seçin **geri** gelen **Düzenle** menüsü veya tuşuna **Ctrl**+**Z**. Ancak, daha sonra elle kodu UIMap.cs veya UIMap.vb dosyasından kaldırmanız gerekir.

## <a name="locate-a-ui-control-in-the-application-under-test"></a>Test altındaki uygulamada bir kullanıcı Arabirimi denetimini bulun

Bazı durumlarda, denetimleri test altında uygulamanın kullanıcı arabiriminde bulunduğu görselleştirmek zor olabilir. Kodlanmış UI Test Düzenleyicisi yeteneklerini UI denetim eşlemesinde listelenen bir denetim seçin ve test altındaki uygulama konumuna görünümünde biridir. Kullanarak **UI denetimi bulun** test altındaki uygulama özelliği de denetime yaptığınız arama özelliği değişiklikleri doğrulamak için kullanılabilir.

![UI denetim bulun](../test/media/codeduilocatecontrol.png)

![Uygulamayı test altında bulunan denetimi](../test/media/codeduilocatecontrol2.png)

İçinde **UI denetim eşlemesi** uygulama içinde bulmak istediğiniz denetim testiyle ilişkili bölmesinde seçin. Ardından, denetimi için kısayol menüsünü açın ve ardından **UI denetimi bulun**. Test edilmekte olan uygulamada denetimi ile mavi kenarlık atanmış.

> [!NOTE]
> Bir kullanıcı Arabirimi denetimini bulun önce test ile ilişkili uygulamayı çalıştığını doğrulayın.

### <a name="tips"></a>İpuçları

Kullanabileceğiniz **bulun tüm** bir kapsayıcı altında tüm denetimler doğru bulunduğu olduğunu doğrulamak için seçeneği. Bu seçenek bir sonraki bölümde açıklanmıştır.

## <a name="locate-a-control-and-its-descendants"></a>Bir denetim ve alt öğeleri bulun

Bir kapsayıcı altında tüm denetimler test altında uygulamanın kullanıcı arabiriminde doğru bulunabilir doğrulayabilirsiniz. Bu kapsayıcıda yapılan arama özellik değişiklikleri doğrulamaya yardımcı olabilir. Ayrıca, olduysa önemli değişiklikler test altında uygulamanın kullanıcı arabiriminde, var olan denetim arama özellikleri hala doğru olduğunu doğrulayabilirsiniz.

![Tüm alt denetimleri bulun](../test/media/codeduilocateall.png)

![Bulunan tüm denetimler](../test/media/codeduilocateall2.png)

İçinde **UI denetim eşlemesi** bölmesinde bulun ve için tüm bağımlı öğelerini görüntülemek istediğiniz kapsayıcı denetimi seçin. Ardından, denetimi için kısayol menüsünü açın ve seçin **bulun tüm**. Kapsayıcı denetimi ve tüm alt denetimlerinden kodlanmış UI Test Düzenleyicisi'nde yeşil bir onay işareti veya 'X' kırmızı ile işaretlenmiştir. Bu işaretler denetimleri test altındaki uygulama başarıyla bulunan varsa size bildirmek.

> [!NOTE]
> Kullanıcı Arabirimi denetimlerini bulma önce test ile ilişkili uygulamayı çalıştığını doğrulayın.

## <a name="insert-a-delay-before-a-ui-action"></a>Bir UI eyleminden önce gecikme ekleme

Bazı durumlarda, oluşmasına kayboluyor için ilerleme çubuğu görünmesi bir pencere gibi belirli olaylar için bekleyin ve benzeri test yapmak isteyebilirsiniz. Kodlanmış UI Test Düzenleyicisi'ni kullanarak bunu bir UI eyleminden önce gecikme ekleyerek gerçekleştirebilirsiniz. Gecikme olmasını istediğiniz kaç saniye belirtebilirsiniz.

![Bir UI eyleminden önce gecikme ekleme](../test/media/codeduidelay.png)

![5 saniye ile eklenen gecikmesi](../test/media/codeduidealy2.png)

İçinde **UI eylem** bölmesinde, önce bir gecikme eklemek istediğiniz UI eylem içeren test yöntemi genişletin. UI eylemi seçin. Ardından, UI eylemi için kısayol menüsünü açın ve seçin **gecikme önce Ekle**. Bir gecikme eklenen ve aşağıdaki metinle seçili UI eyleminden önce vurgulanır: **Eylemler arasındaki kullanıcı gecikmesini 1 saniye bekleyin**. Özellikler penceresinde değerini değiştirin **gecikme** milisaniye istenen sayıda özellik.

Tamamlandıktan sonra gecikme ekleme Kaydet değişiklikleri UIMap.Designer dosyasına seçerek **kaydetmek** Visual Studio araç.

Belirli bir denetim bir UI eyleminden önce kullanılabilir olduğundan emin olmak gerekiyorsa, uygun UITestControl.WaitForControlXXX() yöntemini kullanarak, test yöntemi için özel kod eklemeyi göz önünde bulundurmalısınız. Daha fazla bilgi için bkz: [yapmadan kodlanmış UI testleri beklemek için belirli olayları sırasında kayıttan yürütme](../test/making-coded-ui-tests-wait-for-specific-events-during-playback.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](../test/use-ui-automation-to-test-your-code.md)
- [Kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md)
- [Verilerle Çalışan Kodlanmış UI Testi Oluşturma](../test/creating-a-data-driven-coded-ui-test.md)
- [İzlenecek yol: Kodlanmış Bir UI Testi Oluşturmak Düzenlemek ve Sürdürmek](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)