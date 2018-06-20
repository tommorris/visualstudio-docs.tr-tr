---
title: CodeLens ile kod değişikliklerini ve diğer geçmişi bulma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 02f0c8dd142f9517dcaef3a40d613d43b8e650a3
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238401"
---
# <a name="find-code-changes-and-other-history-with-codelens"></a>CodeLens ile kod değişikliklerini ve diğer geçmişi bulma

CodeLens kodunuzu ne olduğunu bulun sırada üzerindeki çalışmanızı odaklanmalarını sağlar&ndash;düzenleyiciden ayrılmadan. Başvurular paylaştırılabilen bir kod, kod, bağlantılı hatalar, iş öğelerini, kod gözden geçirme ve birim testleri değişiklikler bulabilirsiniz.

> [!NOTE]
> CodeLens yalnızca Visual Studio Enterprise ve Visual Studio Professional sürümlerinde kullanılabilir. Visual Studio Community Edition'da kullanılabilir değil.

Nerede ve nasıl kodunuzun tek tek parçaları çözümünüz içinde kullanılan bakın:

![Kod düzenleyicisinde CodeLens göstergeleri](../ide/media/codelens-overview.png)

Düzenleyiciden ayrılmadan kodunuzu değişiklikler hakkında ekibinize başvurun:

![CodeLens - ekibinizin başvurun](../ide/media/codelens-contact-info.png)

Bakın veya CodeLens kapatıp açmak istediğiniz göstergeleri seçmek için Git **Araçları** > **seçenekleri** > **metin düzenleyici**  >  **Tüm diller** > **CodeLens**.

## <a name="find-references-to-your-code"></a>Kodunuzu başvuruları Bul

C# veya Visual Basic kodu başvuruları bulabilirsiniz.

1. Seçin **başvuruları** göstergesi veya tuşuna **Alt**+**2**.

   ![CodeLens başvuruları](../ide/media/codelens-view-references.png)

   > [!NOTE]
   > Göstergenin gösteriyorsa **0 başvuruları**, C# veya Visual Basic kodundan başvuru içermeyen. Ancak, olabilir başvuruları diğer öğeler gibi *.xaml* ve *.aspx* dosyaları.

2. Başvuru kodu görmek için listenin başvurusunda üzerinden fare.

   ![CodeLens - gözlem başvurusu](../ide/media/codelens-peek-reference.png)

3. Başvuru içeren dosyayı açmak için başvuru çift tıklatın.

### <a name="code-maps"></a>Kod haritaları

Kod ve kendi başvurular arasındaki ilişkileri görmek için [bir kod Haritası oluşturma](../modeling/map-dependencies-across-your-solutions.md). Kod Haritası kısayol menüsünden seçin **Göster tüm başvuruları**.

![CodeLens - kod Haritası başvurular](../ide/media/codelensmappedreferences.png)

## <a name="a-namefind-code-historyfind-changes-in-your-code"></a><a name="find-code-history"/>Kodunuzda değişiklikleri Bul

Kodunuzu neler olduğunu öğrenmek için kodun geçmiş inceleyin. Ya da diğer dalların kullanılabilirliği etkilenmeden değişiklikleri kodunuzu nasıl etkileyebileceğini daha iyi anlayabilirsiniz şekilde kodunuza birleştirilmiş önce değişiklikleri gözden geçirin.

İhtiyacın var:

- Visual Studio Enterprise veya Visual Studio Professional

- Team Foundation Server 2013 veya üzeri, Visual Studio Team Services veya Git

- [Skype Kurumsal](/skypeforbusiness/), veya Lync 2010 veya üzeri, kod düzenleyicisinden ekibinize başvurun

Team Foundation sürüm denetimi (TFVC'yi) veya Git ile depolanan C# veya Visual Basic kod için sınıf ve yöntem düzeylerinde CodeLens ayrıntıları alın (*kod öğe düzeyinde* göstergeleri). Git deponuz TfGit içinde barındırılıyorsa, TFS iş öğelerine bağlantılar da alın.

![Öğe düzeyinde göstergeleri kod](../ide/media/codelens-element-level-indicators.png)

İçin dosya türlerini dışında *.cs* veya *.vb*, CodeLens ayrıntıları tek bir yerde dosyanın tamamı için pencerenin alt kısmında aldığınız (*dosya düzeyinde* göstergeleri).

![Dosya düzeyinde CodeLens göstergeleri](../ide/media/almcodelensfilelevelindicators.png)

### <a name="code-element-level-indicators"></a>Öğe düzeyinde göstergeleri kod

Öğe düzeyinde göstergeleri kodunuzu değiştirdiğiniz kimin ve ne değişiklikler görmenize izin kodu yapılır. C# ve Visual Basic kodu için kod öğe düzeyinde göstergeleri kullanılabilir.

Team Foundation Server ya da Visual Studio Team Services Team Foundation sürüm denetimi (TFVC'yi) kullandığınızda, gördükleri şudur:

![CodeLens: TFVC'yi kodunuzda Get değişiklik geçmişi](../ide/media/codelens-code-changes.png)

Varsayılan süre son 12 ay değeridir. Team Foundation Server'da kodunuzu depolanıyorsa çalıştırarak zaman aralığını değiştirebilirsiniz [TFSConfig komut](/tfs/server/ref/command-line/tfsconfig-cmd) ile [Codeındex komutu](../ide/codeindex-command.md) ve **/indexHistoryPeriod**bayrağı.

Önce birden fazla bir yıldan dahil olmak üzere tüm değişiklikleri ayrıntılı bir geçmişini görmek için seçin **tüm dosya değişiklikleri göstermek**:

![Tüm kod değişikliklerini göster](../ide/media/codelens-show-all-file-changes.png)

**Geçmişi** penceresi açılır:

![Geçmiş penceresini tüm kod değişiklikleri](../ide/media/codelenscodechangeshistory.png)

Olduğunda, dosyalarınızı Git deposunda ve kod öğe düzeyinde yapılan değişiklikler göstergesi seçtiğiniz gördüğünüz budur:

![CodeLens: Git kodunuzda Get değişiklik geçmişi](../ide/media/codelens-code-changes-git.png)

### <a name="file-level-indicators"></a>Dosya düzeyinde göstergeleri

Pencerenin altındaki dosya düzeyinde göstergeleri içinde dosyanın tamamı için değişiklikleri bulun:

![CodeLens: kod dosya ayrıntıları alın.](../ide/media/codelens-file-level.png)

> [!NOTE]
> Dosya düzeyinde göstergeleri C# ve Visual Basic dosyaları için kullanılabilir değil.

Bir değişiklik hakkında daha fazla bilgi almak için bu öğeyi sağ tıklatın. TFVC'yi veya Git kullanmanıza bağlı olarak, dosya sürümlerini karşılaştırın, ayrıntılarını görüntülemek ve değişiklik izleme, seçili dosya sürümünü alın ve bu değişikliği yazarı e-posta seçenekleri vardır. Bu ayrıntılar bazıları görünür **Takım Gezgini**.

Kimin kodunuzu zaman içinde değişmesi de görebilirsiniz. Bu düzenleri ekibinizin değişiklikleri bulmanıza ve bunların etkisini değerlendirmenize yardımcı olabilir.

![CodeLens: kod değişiklik geçmişi bir grafik bakın.](../ide/media/codelens.png)

### <a name="find-changes-in-your-current-branch"></a>Değişiklikler, geçerli dal Bul

Ekibinizin birden çok dal, örneğin bir ana dala ve kararlı kod çiğnemekten riskini azaltmak için bir alt geliştirme dalı olabilir.

![CodeLens: kodunuzu zaman dallandırılmış Bul](../ide/media/codelensfirstbranchconceptual.png)

Kodunuzu kaç kişinin değişti ve kaç tane değişiklikleri ana dala tuşlarına basarak yapılan bulabilirsiniz **Alt**+**6**:

![CodeLens: kaç tane değişiklik dalınızda Bul](../ide/media/codelens-branch-changes.png)

### <a name="find-when-your-code-was-branched"></a>Kodunuzu zaman dallandırılmış Bul

Kodunuzu dallandırılmış zaman bulmak için alt dala kodunuzda gidin. Ardından, seçin **değişiklikleri** göstergesi veya tuşuna**Alt**+**6**:

![CodeLens: kodunuzu zaman dallandırılmış Bul](../ide/media/codelens-first-branch.png)

### <a name="find-incoming-changes-from-other-branches"></a>Dala gelen değişikliklerden Bul

![CodeLens: kod değişikliklerinden başka dallarda da bulma](../ide/media/codelensbranchchangecheckinconceptual.png)

Gelen değişiklikleri görüntüleyebilirsiniz. Aşağıdaki ekran görüntüsünde, hata düzeltme "Geliştirme" dalında yapıldı:

![CodeLens: başka bir dalda kontrol Değiştir](../ide/media/codelens-branch-changes-dev.png)

Geçerli dalı ("ana") ayrılmadan değişiklik gözden geçirebilirsiniz:

![CodeLens: bkz. başka bir daldan gelen değiştirme](../ide/media/codelens-branch-changes-main.png)

### <a name="find-when-changes-got-merged"></a>Değişiklikleri birleştirilmiş olduğunda Bul

Böylece hangi değişikliklerin dalınızda dahil edilen belirleyebilir zaman değişiklikleri birleştirilmiş, görebilirsiniz:

![CodeLens - dallar arasında birleştirilmiş değişiklikler](../ide/media/codelensbranchmergedconceptual.png)

Örneğin, ana dala kodunuzda şimdi "Geliştirme" şube ve hata düzeltme vardır:

![CodeLens - dallar arasında birleştirilmiş değişiklikler](../ide/media/codelens-branch-merged.png)

### <a name="compare-an-incoming-change-with-your-local-version"></a>Gelen bir değişiklik yerel sürümünüz ile karşılaştırın

Yerel sürümünüz gelen bir değişiklikle tuşlarına basarak karşılaştırmak **Shift**+**F10**, ya da değişiklik çift tıklatarak.

![CodeLens: yerel gelen değişikliğiyle karşılaştırma](../ide/media/codelens-branch-incoming-change-menu.png)

### <a name="branch-icons"></a>Dal simgeler

Simge **şube** sütun söyler, şube nasıl ilişkili olduğunu içinde çalışırken dal.

|**Simgesi**|**Değişiklik geldiği:**|
|--------------|-----------------------------------------|
|![CodeLens: geçerli dal simgesinden değiştirme](../ide/media/codelensbranchcurrenticon.png)|Geçerli dalı|
|![CodeLens: üst şube simgesinden değiştirme](../ide/media/codelensbranchparenticon.png)|Ana dal|
|![CodeLens: alt şube simgesinden değiştirme](../ide/media/codelensbranchchildicon.png)|Bir alt dal|
|![CodeLens: Eş şube simgesinden değiştirme](../ide/media/codelensbranchpeericon.png)|Bir eş dal|
|![CodeLens: dal daha fazla koyma simgesinden değiştirme](../ide/media/codelensbranchfurtherawayicon.png)|Bir dal daha üst, alt ya da eş koyma|
|![CodeLens: üst simgesinden birleştirme](../ide/media/codelensbranchmergefromparenticon.png)|Ana dal gelen alt dala birleştirme|
|![CodeLens: alt şube simgesinden birleştirme](../ide/media/codelensbranchmergefromchildicon.png)|Alt dala gelen birleştirme ana dala|
|![CodeLens: ilişkisiz şube simgesinden birleştirme](../ide/media/codelensbranchmergefromunrelatedicon.png)|İlişkisiz bir şube (temelsiz birleştirme) gelen birleştirme|

## <a name="linked-work-items"></a>Bağlantılı iş öğeleri

Bağlantılı iş öğelerini seçerek bulma **iş öğelerini** göstergesi basarak veya **Alt**+**8**.

![CodeLens - belirli bir kod Bul iş öğeleri](../ide/media/codelens-work-items.png)

## <a name="linked-code-reviews"></a>Bağlantılı kod gözden geçirme

Bağlantılı kod incelemeleri seçerek Bul **incelemeleri** göstergesi. Klavyeyi kullanmak için basılı **Alt** anahtar ve tuşuna basın **sol ok** veya **sağ ok** gösterge seçeneklerini gidin.

![CodeLens - Görünüm Kodu isteklerini gözden geçirme](../ide/media/codelens-code-reviews.png)

## <a name="linked-bugs"></a>Bağlantılı hataları

Seçerek bağlantılı hataları bulmaya **hataları** göstergesi basarak veya **Alt**+**7**.

![CodeLens - değişiklik kümesine bağlı Bul hataları](../ide/media/codelens-bugs-changesets.png)

## <a name="contact-the-owner-of-an-item"></a>Bir öğenin sahibiyle iletişime geçin

Bir öğenin yazarı seçerek bulmak **yazarlar** göstergesi basarak veya **Alt**+**5**.

![Bir öğenin sahibiyle iletişime geçin](../ide/media/codelens-contact-item-owner.png)

Kişi Seçenekleri görmek için bir öğe için kısayol menüsünü açın. Lync veya Skype Kurumsal yüklü varsa, bu seçenekleri bakın:

![Bir öğe için kişi seçenekleri](../ide/media/codelens-item-contact-menu.png)

## <a name="associated-unit-tests"></a>İlişkili birim testleri

C# veya Visual Basic kodu açmadan mevcut birim testleri bulabilir **Test Gezgini**.

1. İlişkili uygulama kodu gidin [birim test kodu](../test/unit-test-your-code.md).

2. Henüz yapmadıysanız, CodeLens test Göstergeleri yüklemek için uygulamanızı oluşturun. Emin olun [keşfi tarafından oluşturulan derlemeleri](../test/test-explorer-faq.md#3-assembly-based-discovery-is-no-longer-working-for-my-project-how-do-i-turn-it-back-on) açıktır.

3. Kod için testleri tuşlarına basarak gözden **Alt**+**3**.

     ![CodeLens - seçin Kod düzenleyicisinde test durumu](../ide/media/codelens-choose-test-indicator.png)

4. Bir uyarı simgesi görürseniz ![Uyarı simgesi](../ide/media/codelenstestwarningicon.png), testleri henüz çalıştırmak henüz, böylece bunları çalıştırın.

     ![CodeLens - görünüm birim testleri henüz çalışmayabilir](../ide/media/codelens-tests-not-yet-run.png)

5. Bir testin tanımı gözden geçirmek için kod dosyası düzenleyicisinde açmak için CodeLens göstergesi penceresinde test öğesini çift tıklatın.

     ![CodeLens - birim testi tanımına gidin](../ide/media/codelens-unit-test-definition.png)

6. Testin sonuçlarını gözden geçirmek için test durum göstergesi seçin (![test başarısız simgesi](../ide/media/codelenstestfailedicon.png) veya ![geçirilen test simgesi](../ide/media/codelenstestpassedicon.png)), veya basın **Alt**+**1**.

     ![CodeLens - bkz: birim sınama sonucu](../ide/media/codelens-unit-test-result.png)

7. Bu test kaç kişinin değiştirilmesi, kimin bu test değiştirilmiş veya bu test için kaç tane değişikliklerin yapıldığı görmek için [, kodun geçmişi Bul](#find-code-history) ve bağlantılı öğeler.

## <a name="keyboard-shortcuts"></a>Klavye kısayolları

Göstergeleri seçmek üzere klavyeyi kullanmak için basılı **Alt** seçmek istediğiniz anahtar ilgili sayı tuşlarını görüntülemek, ardından göstergesini karşılık gelen sayıyı tuşuna basın.

![Klavye erişim numaraları](../ide/media/codelens-alt-keys.png)

> [!NOTE]
> Seçilecek **incelemeleri** göstergesi, tuşunu basılı tutun **Alt** gitmek için sol ve sağ ok tuşlarını kullanırken.

## <a name="q--a"></a>Soru - Yanıt

### <a name="q-how-do-i-turn-codelens-off-or-on-or-choose-which-indicators-to-see"></a>S: nasıl CodeLens kapatma veya açma, veya görmek için hangi göstergeleri seçin?

**Y:** göstergeleri kapalı veya açık başvurular göstergesi dışında kapatabilirsiniz. Git **Araçları** > **seçenekleri** > **metin düzenleyici** > **tüm diller**  >  **CodeLens**.

Göstergeleri açık olduğunda, CodeLens seçenekleri göstergelerini açabilirsiniz.

![CodeLens - dışı bırakma göstergeleri](../ide/media/codelensturnoffonindicatorsfromcode.png)

CodeLens dosya düzeyinde göstergeleri açıp Düzenleyicisi penceresinin alt kısmında Köşeli Çift Ayraca simgeleri kullanarak kapatabilirsiniz.

![Dosya düzeyinde göstergeleri açma veya kapatma](../ide/media/codelensfilelevelonandoff.png)

### <a name="q-where-is-codelens"></a>S: CodeLens nerede?

**Y:** yöntemi, sınıf, dizin oluşturucu ve özellik düzeyinde C# ve Visual Basic kodu CodeLens görünür. Tüm dosya türleri için dosya düzeyinde CodeLens görünür.

- CodeLens açık olduğundan emin olun. Git **Araçları** > **seçenekleri** > **metin düzenleyici** > **tüm diller**  >  **CodeLens**.

- Kodunuzu TFS'de depolanıyorsa, kod dizinini kullanarak açık olduğundan emin olun [Codeındex komutu](../ide/codeindex-command.md) ile [TFS Config komutunu](/tfs/server/ref/command-line/tfsconfig-cmd).

- TFS ilişkili göstergeler yalnızca iş öğeleri koda bağlandığında ve bağlantılı iş öğelerini açmak için izniniz olduğunda görünür. Sahip olduğunuzu onaylamak [ekip üye izinleri](/vsts/work/scale/multiple-teams).

- Uygulama kodu birim testleri sahip olmadığında birim testi göstergeleri görünmüyor. Test durumu göstergeleri test projesinde otomatik olarak görüntülenir. Birim testleri uygulama kodunuz var, ancak test göstergeleri görünmüyor biliyorsanız, çözümü oluşturma deneyin (**Ctrl**+**Shift**+**B**).

### <a name="q-why-dont-i-see-the-work-item-details-for-a-commit"></a>Bir yürütme iş öğesi ayrıntılarını neden göremiyorum?

**Y:** CodeLens TFS'de iş öğeleri bulamadığından bu durum oluşabilir. Olanlar sahip takım projesine bağlı olduğunuzu denetleyin, çalışma öğeleri ve bu görmek için izinlere sahip iş öğeleri. İş öğesi ayrıntılarını ayrıca değil yürütme açıklama TFS'de iş öğesi kimlikleri hakkında yanlış bilgi olup olmadığını gösterilmeyebilir.

### <a name="q-why-dont-i-see-the-skype-indicators"></a>Skype göstergeleri neden göremiyorum?

**Y:** Skype göstergeleri Skype Kurumsal içine oturum açtınız değil, yüklemediyseniz veya desteklenen bir yapılandırma yok görünmez. Ancak, e-posta göndermeye devam edebilir:

![CodeLens - kişi değişiklik posta sahibi](../ide/media/codelenscodesendmailchangesetnolync1.png)

**Hangi Skype ve Lync yapılandırmaları desteklenir?**

- Skype Kurumsal (32 bit veya 64 bit)

- Lync 2010 veya daha sonra tek başına (32 bit veya 64 bit), ancak değil Lync Basic 2013 ile Windows 8.1

CodeLens Lync farklı sürümlerine sahip desteklemiyor veya Skype yüklü. Bunlar, Visual Studio'nun tüm yerelleştirilmiş sürümleri için yerelleştirilmiş olabilir değil.

### <a name="q-how-do-i-change-the-font-and-color-for-codelens"></a>S: CodeLens için yazı tipi ve renk nasıl değiştirebilirim?

**Y:** Git **Araçları** > **seçenekleri** > **ortam** > **yazı tiplerini ve renkleri**.

![CodeLens - yazı tipi ve renk ayarlarını değiştir](../ide/media/codelensoptionsfontscolorssettings.png)

Klavyeyi kullanmak için:

1. Tuşuna **Alt**+**T**+**O** açmak için **seçenekleri** iletişim kutusu.

2. Basın **yukarı ok** veya **aşağı ok** gitmek için **ortam** düğümü tuşuna basarak **sol ok** düğümü genişletmek için.

3. Tuşuna **aşağı ok** gitmek için **yazı tiplerini ve renkleri**.

4. Basın **sekmesini** gitmek için **ayarlarını göster** listelemek ve tuşuna basarak **aşağı ok** seçmek için **CodeLens**.

### <a name="q-can-i-move-the-codelens-heads-up-display"></a>S: CodeLens ekran göstergesi görüntüsünü taşıyabilir miyim?

**Y:** Evet, seçin ![yerleştirme simgesi](../ide/media/codelensdockwindow.png) CodeLens bir pencere olarak sabitlemek için.

![CodeLens göstergesi penceresinde düğmesini yerleştirme](../ide/media/codelensselectdockwindow.png)

![Yerleşik CodeLens başvuruları penceresi](../ide/media/codelensreferencesdockedwindow.png)

### <a name="q-how-do-i-refresh-the-indicators"></a>S: Göstergeleri nasıl yenileyebilirim?

**Y:** Bu gösterge üzerinde bağlıdır:

- **Başvuruları**: kod değiştiğinde bu gösterge otomatik olarak güncelleştirir. Varsa **başvuruları** göstergesi ayrı bir pencerede yerleşik, gösterge Yenile'yi **yenileme**:

     ![CodeLens başvuruları düğmesini Yenile](../ide/media/codelensviewreferencesdocked.png)

- **Takım**: Bu göstergeler Yenile'yi **CodeLens ekip göstergelerini yenileme** sağ tıklatma menüsünden:

     ![CodeLens ekip göstergelerini menü öğesi Yenile](../ide/media/codelensrefreshindicatorsfromcode.png)

- **Test**: [Bul kodunuz için birim testleri](#Find-unit-tests-for-your-code) yenilemek için **Test** göstergesi.

### <a name="q-whats-local-version"></a>S: "Yerel sürümü" nedir?

**Y:** **yerel sürümü** ok yerel bir dosya sürümünüzde en son değişiklik gösterir. Üstüne veya altına sunucunun daha yeni değişiklik olduğunda, göründükleri **yerel sürümü** bağlı olarak değişiklik kümelerini sıralamak için kullanılan sırayı oku.

### <a name="q-can-i-manage-how-codelens-processes-code-to-show-history-and-linked-items"></a>S: CodeLens geçmişi ve bağlantılı öğeler göstermek için kod nasıl işlediği yönetebilirim?

**Y:** Evet. Kodunuzu TFS'de ise [Codeındex komutu](../ide/codeindex-command.md) ile [TFS Config komutunu](/tfs/server/ref/command-line/tfsconfig-cmd).

### <a name="q-my-codelens-test-indicators-no-longer-appear-in-my-file-when-i-first-open-my-solution-how-can-i-load-them"></a>S: çözümüme'ı ilk kez açtığınızda my CodeLens test göstergeleri my dosyasında artık görünür. Bunları nasıl yüklenmesi miyim?

**Y:** dosyanızda yüklemek için CodeLens test göstergeleri almak için projenizi yeniden derleyin. Emin olun [keşfi tarafından oluşturulan derlemeleri](../test/test-explorer-faq.md#3-assembly-based-discovery-is-no-longer-working-for-my-project-how-do-i-turn-it-back-on) açıktır. Kod dosyaları yüklendiğinde performansı artırmak için Visual Studio artık test göstergeleri için kaynak bilgileri getirir. Sonra bir derleme veya içinde çift tıklayarak bir teste gittiğinizde test göstergeleri yüklenir **Test Gezgini**.

## <a name="see-also"></a>Ayrıca bkz.

- [Kod Düzenleyicisi özellikleri](../ide/writing-code-in-the-code-and-text-editor.md)
