---
title: "Kod değişikliklerini ve diğer geçmişi CodeLens ile bulma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: a1123d1c557f6e7f01eb98e668b4f13785ee6893
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="find-code-changes-and-other-history-with-codelens"></a>CodeLens ile kod değişikliklerini ve diğer geçmişi bulma

Kodunuzu - düzenleyiciden ayrılmadan ne olduğunu bulun sırada üzerindeki çalışmanızı odaklanmalarını. References ve kod, bağlantılı hatalar, iş öğelerini, kod gözden geçirme ve birim testleri değişiklikler bulun.

> [!NOTE]
> CodeLens yalnızca Visual Studio Enterprise ve Visual Studio Professional sürümlerinde kullanılabilir. Visual Studio Community Edition'da kullanılabilir değil.  

Nerede ve nasıl kodunuzun tek tek parçaları çözümünüz içinde kullanılan bakın:  

![Kod düzenleyicisinde CodeLens göstergeleri](../ide/media/codelensoverview.png "CodeLensOverview")  

Düzenleyiciden ayrılmadan kodunuzu değişiklikler hakkında ekibinize başvurun:  

![CodeLens &#45; Ekibinize başvurun](../ide/media/codelensovervew2.png "CodeLensOvervew2")  

Bakın veya CodeLens kapatıp açmak istediğiniz göstergeleri seçmek için Git **Araçları**, **seçenekleri**, **metin düzenleyici**, **tüm diller** , **CodeLens**.  

## <a name="FindReferences"></a>Kodunuzu başvuruları Bul

İhtiyacınız vardır:

-  Visual Studio Enterprise veya Visual Studio Professional

-  C# veya Visual Basic kodu

Seçin **başvuruları** göstergesi (**Alt + 2**). Görürseniz **0 başvuruları**, C# veya Visual Basic kodundan başvuru içermeyen. Bu XAML ve ASPX dosyaları gibi diğer öğeleri başvurularından içermez.

![CodeLens &#45; Başvuruları göstergesi seçin](../ide/media/codelensviewreferenceslist.png "CodeLensViewReferencesList")  

Başvuru kodu görmek için başvuru üstünde fareyi hareket ettirin.  

![CodeLens &#45; Başvuru peek](../ide/media/codelensviewreferencespeekreference.png "CodeLensViewReferencesPeekReference")  

Başvuru içeren dosyayı açmak için başvuru çift tıklatın.  

Bu kod ve kendi başvurular arasındaki ilişkileri görmek için [bir kod Haritası oluşturma](../modeling/map-dependencies-across-your-solutions.md) ve **Göster tüm başvuruları** kod Haritası kısayol menüsünde.

![CodeLens &#45; Kod Haritası başvurular](../ide/media/codelensmappedreferences.png "CodeLensMappedReferences")  

## <a name="FindCodeHistory"></a>Kodunuzu 's geçmişi ve bağlantılı öğeler Bul

Kodunuzu neler olduğunu öğrenmek için kodun geçmişini gözden geçirin. Ya da diğer dalların kullanılabilirliği etkilenmeden değişiklikleri kodunuzu nasıl etkileyebileceğini daha iyi anlayabilirsiniz şekilde kodunuza birleştirilmiş önce değişiklikleri gözden geçirin.

İhtiyacınız vardır:

- Visual Studio Enterprise veya Visual Studio Professional

- Team Foundation Server 2013 veya üzeri, Visual Studio Team Services veya Git

- [Lync 2010 veya üzeri ya da Skype Kurumsal](https://technet.microsoft.com/office/dn788773), kod düzenleyicisinden ekibinize başvurun

Team Foundation sürüm denetimi (TFVC'yi) veya Git ile depolanan C# veya Visual Basic kod için sınıf ve yöntem düzeylerinde CodeLens ayrıntıları alın (*kod öğe düzeyinde* göstergeleri). Git deponuz TfGit içinde barındırılıyorsa, TFS iş öğelerine bağlantılar da alın.  

![Kod öğesi &#45; düzeyi göstergeleri](../ide/media/codelenselementlevelindicators.png "CodeLensElementLevelIndicators")  

Tüm diğer Visual Studio düzenleyicisinde açabileceğiniz dosya türlerinde, CodeLens tek bir yerde dosyanın tamamı için pencerenin alt kısmında ayrıntıları (*dosya düzeyinde* göstergeleri).

![Dosya &#45; düzeyi CodeLens göstergeleri](../ide/media/almcodelensfilelevelindicators.png "ALMCodeLensFileLevelIndicators")  

Göstergeleri seçmek üzere klavyeyi kullanmak için basılı **ALT** ilgili sayı tuşlarını görüntülemek için anahtar.  

![Klavye erişim numaraları görmek için ALT tuşuna basın](../ide/media/codelensaltkeyindicators.png "CodeLensAltKeyIndicators")  

### <a name="find-changes-in-your-code"></a>Kodunuzda değişiklikleri Bul

Kim, C# veya Visual Basic kodu değiştirildi ve bunlar kodu öğe düzeyinde göstergeleri yapılan değişiklikleri bulun. Team Foundation Server ya da Visual Studio Team Services Team Foundation sürüm denetimi (TFVC'yi) kullandığınızda, gördükleri budur.  

![CodeLens: Get değişiklik geçmişini TFVC'yi kodunuzda için](../ide/media/codelenscodechanges.png "CodeLensCodeChanges")  

Varsayılan süre son 12 ay değeridir. Team Foundation Server'da kodunuzu depolanırsa, bu çalıştırarak değiştirebilirsiniz [TFSConfig komut](/vsts/tfs-server/command-line/tfsconfig-cmd) ile [Codeındex komutu](../ide/codeindex-command.md) ve **/indexHistoryPeriod** bayrağı.

Önce birden fazla bir yıldan dahil olmak üzere tüm değişiklikleri ayrıntılı bir geçmişini görmek için seçin **tüm dosya değişiklikleri göstermek**.  

![Tüm kod değişiklikleri göstermek](../ide/media/codelensshowsallchanges.png "CodeLensShowsAllChanges")  

Bu değişiklik geçmişi penceresini açar.  

![Tüm kod değişiklikleri Geçmişi penceresini](../ide/media/codelenscodechangeshistory.png "CodeLensCodeChangesHistory")  

Olduğunda, dosyalarınızı Git deposunda ve kod öğe düzeyinde değişiklikleri göstergesi seçtiğiniz gördüğünüz budur.  

![CodeLens: Get değişiklik geçmişini Git kodunuzda için](../ide/media/codelenscodechangesgit.png "CodeLensCodeChangesGit")  

Pencerenin altındaki dosya düzeyinde göstergeleri değişiklikleri (C# ve Visual Basic dosyaları dışında) tüm bir dosyayı bulun.  

![CodeLens: kod dosyası ayrıntılara](../ide/media/codelensfilelevel.png "CodeLensFileLevel")  

Bir değişiklik hakkında daha fazla bilgi almak için bu öğeyi sağ tıklatın. TFVC'yi veya Git kullanmanıza bağlı olarak bir dizi dosya sürümlerini karşılaştırın, ayrıntılarını görüntülemek ve değişiklik izleme, seçili dosya sürümünü alın ve bu değişikliği yazarı e-posta seçenekleri alın. Bu ayrıntılar bazıları Takım Gezgini'nde görünür.  

Kimin kodunuzu zaman içinde değişmesi de görebilirsiniz. Bu düzenleri ekibinizin değişiklikleri bulmanıza ve bunların etkisini değerlendirmenize yardımcı olabilir.  

![CodeLens: Bkz: kod değişikliklerini geçmiş bir grafik olarak](../ide/media/codelens.png "CodeLens")  

#### <a name="find-changes-in-your-current-branch"></a>Değişiklikler, geçerli dal Bul

Birden çok dal - ana dala ve bir alt geliştirme - kararlı kod çiğnemekten riskini azaltmak için takımınızın olduğunu varsayın:  

![CodeLens: kodunuzu zaman dallandırılmış Bul](../ide/media/codelensfirstbranchconceptual.png "CodeLensFirstBranchConceptual")  

Kodunuzu kaç kişinin değişti ve kaç tane değişiklik yapıldı bulun (**Alt + 6**), ana dal:  

![CodeLens: kaç tane dalınızda değişiklikleri Bul](../ide/media/codelensbranchchanges.png "CodeLensBranchChanges")  

#### <a name="find-when-your-code-was-branched"></a>Kodunuzu zaman dallandırılmış Bul

Alt dala kodunuzda Örneğin, geliştirme şube buraya gidin. Değişiklikleri göstergesi seçin (**Alt + 6**):  

![CodeLens: kodunuzu zaman dallandırılmış Bul](../ide/media/codelensfirstbranchscreenshot.png "CodeLensFirstBranchScreenshot")  

#### <a name="find-incoming-changes-from-other-branches"></a>Dala gelen değişikliklerden Bul

![CodeLens: Kod değişikliklerini diğer dalları Bul](../ide/media/codelensbranchchangecheckinconceptual.png "CodeLensBranchChangeCheckinConceptual")  

.. geliştirme bu hata düzeltme dal burada biçiminde yazarsınız:

![CodeLens: Başka bir dala değişikliği iade](../ide/media/codelensbranchchangedevscreenshot.png "CodeLensBranchChangeDevScreenshot")  

Bu değişiklik, geçerli dalı (ana) ayrılmadan gözden geçirebilirsiniz:  

![CodeLens: başka bir daldan gelen değişikliği görmek](../ide/media/codelensbranchchangemainscreenshot.png "CodeLensBranchChangeMainScreenshot")  

#### <a name="find-when-changes-got-merged"></a>Değişiklikleri birleştirilmiş olduğunda Bul

Hangi değişikliklerin dalınızda dahil edilen görebilmeniz için:  

![CodeLens &#45; Birleştirilmiş dalları arasındaki değişiklikleri](../ide/media/codelensbranchmergedconceptual.png "CodeLensBranchMergedConceptual")  

Örneğin, ana dala kodunuzda artık geliştirme dalındaki hata düzeltmesi sahiptir:  

![CodeLens &#45; Birleştirilmiş dallar arasında chagnes](../ide/media/codelensbranchmergedscreenshot.png "CodeLensBranchMergedScreenshot")  

#### <a name="compare-an-incoming-change-with-your-local-version-shift--f10"></a>Gelen bir değişiklik, yerel sürümü (SHIFT + F10) ile karşılaştırın

![CodeLens: yerel gelen değişikliğiyle karşılaştırma](../ide/media/codelensbranchincomingchangemenu.png "CodeLensBranchIncomingChangeMenu")  

Ayrıca, değişiklik çift tıklatabilirsiniz.

#### <a name="what-do-the-icons-mean"></a>Simgeler ne anlama geliyor?

|**Simgesi**|**Değişiklik alınacağı yeri?**|  
|--------------|-----------------------------------------|  
|![CodeLens: Geçerli dal simgesinden değiştirme](../ide/media/codelensbranchcurrenticon.png "CodeLensBranchCurrentIcon")|Geçerli dalı|  
|![CodeLens &#45; Ana dal simgesinden değiştirme](../ide/media/codelensbranchparenticon.png "CodeLensBranchParentIcon")|Ana dal|  
|![CodeLens: Değiştirme alt şube simgesinden](../ide/media/codelensbranchchildicon.png "CodeLensBranchChildIcon")|Bir alt dal|  
|![CodeLens &#45; Değiştirme eş şube simgesinden](../ide/media/codelensbranchpeericon.png "CodeLensBranchPeerIcon")|Bir eş dal|  
|![CodeLens &#45; Değiştirme şube daha fazla koyma simgesinden](../ide/media/codelensbranchfurtherawayicon.png "CodeLensBranchFurtherAwayIcon")|Bir dal daha üst, alt ya da eş koyma|  
|![CodeLens: üst simgesinden birleştirme](../ide/media/codelensbranchmergefromparenticon.png "CodeLensBranchMergeFromParentIcon")|Ana dal gelen alt dala birleştirme|
|![CodeLens: alt şube simgesinden birleştirme](../ide/media/codelensbranchmergefromchildicon.png "CodeLensBranchMergeFromChildIcon")|Alt dala gelen birleştirme ana dala|  
|![CodeLens: ilişkisiz şube simgesinden birleştirme](../ide/media/codelensbranchmergefromunrelatedicon.png "CodeLensBranchMergeFromUnrelatedIcon")|İlişkisiz bir şube (temelsiz birleştirme) gelen birleştirme|  

### <a name="find-linked-work-items"></a>Bağlantılı iş öğelerini bulma

![CodeLens &#45; İş öğeleri için özel kod Bul](../ide/media/codelensworkitems.png "CodeLensWorkItems")  

### <a name="find-linked-code-reviews"></a>Bağlantılı kod incelemeleri Bul

![CodeLens &#45; Kod gözden geçirme istekleri görüntülemek](../ide/media/codelenscodereviews.png "CodeLensCodeReviews")  

### <a name="find-linked-bugs"></a>Bağlantılı hataları bulma

![CodeLens &#45; Değişiklik kümesine bağlı Bul hataları](../ide/media/codelensbugschangesets.png "CodeLensBugsChangesets")  

### <a name="contact-the-owner-of-an-item"></a>Bir öğenin sahibiyle iletişime geçin

![Bir öğe sahibine başvurun](../ide/media/codelenscontactitemowner.png "CodeLensContactItemOwner")  

Kişi Seçenekleri görmek için bir öğe için kısayol menüsünü açın. Lync veya Skype Kurumsal yüklü varsa, bu seçenekleri bakın:  

![Bir öğe için seçenekleri başvurun](../ide/media/codelensitemcontactmenu.png "CodeLensItemContactMenu")  

##  <a name="FindRunUnitTests"></a>Kodunuz için birim testleri bulma

Mevcut kodunuz için birim testleri hakkında daha fazla Test Gezgini açmadan öğrenin. İhtiyacınız vardır:  

-   Visual Studio Enterprise veya Visual Studio Professional  
  
-   C# veya Visual Basic kodu  
  
-   A [birim testi projesi](../test/unit-test-your-code.md) olan uygulama kodunuz için birim testleri  
  
1.  Birim testlerini içeren uygulama koduna gidin.  
  
2.  Bu kod için testleri gözden geçirin (**Alt + 3**).  
  
     ![CodeLens &#45; Kod düzenleyicisinde test durumu seçin](../ide/media/codelenschoosetestindicator.png "CodeLensChooseTestIndicator")  
  
3.  Bir uyarı simgesi görürseniz ![CodeLens &#45; Birim testleri çalıştırma henüz uyarı](../ide/media/codelenstestwarningicon.png "CodeLensTestWarningIcon"), testleri çalıştırın.  
  
     ![CodeLens &#45; Birim testleri henüz çalıştırmamanız görüntülemek](../ide/media/codelenstestsnotyetrun.png "CodeLensTestsNotYetRun")  
  
4.  Bir testin tanımı gözden geçirmek için kod dosyası düzenleyicisinde açmak için CodeLens göstergesi penceresinde test öğesini çift tıklatın.  
  
     ![CodeLens &#45; Birim testi tanımının gidin](../ide/media/codelensunittestdefinition.png "CodeLensUnitTestDefinition")  
  
5.  Testin sonuçları gözden geçirin. Test durum göstergesi seçin (![CodeLens &#45; Birim testi başarısız simgesi](../ide/media/codelenstestfailedicon.png "CodeLensTestFailedIcon") veya ![CodeLens &#45; Birim testi geçirilen simgesi](../ide/media/codelenstestpassedicon.png "CodeLensTestPassedIcon")), veya basın **Alt + 1**.  
  
     ![CodeLens &#45; Birim test sonucu bkz](../ide/media/codelensunittestresult.png "CodeLensUnitTestResult")  
  
6.  Bu test kaç kişinin değiştirilmesi, kimin bu test değiştirilmiş veya bu test için kaç tane değişikliklerin yapıldığı görmek için [, kodun geçmişi ve bağlantılı öğeler Bul](#FindCodeHistory).

##  <a name="QA"></a>SORU- CEVAP

###  <a name="ChangeOrTurnOff"></a>S: CodeLens nasıl kapatma veya açma? Veya görmek için hangi göstergeleri seçin?

**Y:** göstergeleri kapalı veya açık başvurular göstergesi dışında kapatabilirsiniz. Git **Araçları**, **seçenekleri**, **metin düzenleyici**, **tüm diller**, **CodeLens**.  
  
 Göstergeleri açık olduğunda, CodeLens seçenekleri göstergelerini açabilirsiniz.  
  
 ![CodeLens &#45; Kapatma veya göstergelerini](../ide/media/codelensturnoffonindicatorsfromcode.png "CodeLensTurnOffOnIndicatorsFromCode")  
  
 CodeLens dosya düzeyinde göstergeleri açıp Düzenleyicisi penceresinin alt kısmında Köşeli Çift Ayraca simgeleri kullanarak kapatabilirsiniz.  
  
 ![Bırakma dosya &#45; düzeyi göstergeleri açma ve kapatma](../ide/media/codelensfilelevelonandoff.png "CodeLensFileLevelOnAndOff")  
  
###  <a name="NoIndicators"></a>S: CodeLens nerede?

**Y:** yöntemi, sınıf, dizin oluşturucu ve özellik düzeyinde C# ve Visual Basic kodu CodeLens görünür. Tüm dosya türleri için dosya düzeyinde CodeLens görünür.

- CodeLens açık olduğundan emin olun. Git **Araçları**, **seçenekleri**, **metin düzenleyici**, **tüm diller**, **CodeLens**.  

- Kodunuzu TFS'de depolanıyorsa, kod dizinini kullanarak açık olduğundan emin olun [Codeındex komutu](../ide/codeindex-command.md) ile [TFS Config komutunu](/vsts/tfs-server/command-line/tfsconfig-cmd).

- TFS ilişkili göstergeler yalnızca iş öğeleri koda bağlandığında ve bağlantılı iş öğelerini açmak için izniniz olduğunda görünür. [Ekip üyesi izinlere sahip olduğunuzu doğrulayın](/vsts/work/scale/multiple-teams).

- Uygulama kodu birim testleri sahip olmadığında birim testi göstergeleri görünmüyor. Test durumu göstergeleri test projesinde otomatik olarak görüntülenir. Birim testleri uygulama kodunuz var, ancak test göstergeleri görünmüyor biliyorsanız, çözümü oluşturma deneyin (**Ctrl + Shift + B**).

### <a name="q-why-dont-i-see-the-work-item-details-for-a-commit"></a>Bir yürütme iş öğesi ayrıntılarını neden göremiyorum?

**Y:** CodeLens TFS'de iş öğeleri bulamadığından bu durum oluşabilir. Olanlar sahip takım projesine bağlı olduğunuzu denetleyin iş öğelerini ve görmek için izinlere sahip olanlar iş öğeleri. Yürütme açıklama TFS'de iş öğesi kimlikleri hakkında yanlış bilgi varsa, bu da gerçekleşebilir.  

###  <a name="NoLync"></a>Lync veya Skype göstergeleri neden göremiyorum?

**Y:** bunlar görünmez Lync veya Skype Kurumsal oturum açtınız değil, bunların yüklü yoksa veya desteklenen bir yapılandırma yok. Ancak posta göndermeye devam edebilir:  

![CodeLens &#45; Kişi değişiklik sahibi tarafından posta](../ide/media/codelenscodesendmailchangesetnolync1.png "CodeLensCodeSendMailChangesetNoLync1")  

 **Hangi Lync ve Skype yapılandırmaları desteklenir?**

-   Skype Kurumsal (32 bit veya 64 bit)  

-   Lync 2010 veya daha sonra tek başına (32 bit veya 64 bit), ancak değil Lync Basic 2013 ile Windows 8.1  

CodeLens Lync farklı sürümlerine sahip desteklemiyor veya Skype yüklü. Bunlar, Visual Studio'nun tüm yerelleştirilmiş sürümleri için yerelleştirilmiş olabilir değil.  

### <a name="q-how-do-i-change-the-font-and-color-for-codelens"></a>S: CodeLens için yazı tipi ve renk nasıl değiştirebilirim?

**Y:** Git **Araçları**, **seçenekleri**, **ortam**, **yazı tiplerini ve renkleri**.  

![CodeLens &#45; Yazı tipi ve renk ayarlarını değiştir](../ide/media/codelensoptionsfontscolorssettings.png "CodeLensOptionsFontsColorsSettings")  

Klavyeyi kullanmak için:

1.  Tuşuna **Alt + T + O** açmak için **seçenekleri** kutusu.  

2.  Basın **yukarı ok** veya **aşağı ok** gitmek için **ortam** düğümü tuşuna basarak **sol ok** düğümü genişletmek için.  

3.  Tuşuna **aşağı ok** gitmek için **yazı tiplerini ve renkleri**.  

4.  Basın **sekmesini** gitmek için **ayarlarını göster** listelemek ve tuşuna basarak **aşağı ok** seçmek için **CodeLens**.  

### <a name="q-can-i-move-the-codelens-heads-up-display"></a>S: CodeLens ekran göstergesi görüntüsünü taşıyabilir miyim?

**Y:** Evet, seçin ![CodeLens &#45; Bir pencere olarak yerleştirme](../ide/media/codelensdockwindow.png "CodeLensDockWindow") CodeLens bir pencere olarak sabitlemek için.  

![CodeLens göstergesi penceresini yerleştirme](../ide/media/codelensselectdockwindow.png "CodeLensSelectDockWindow")  

![Yerleşik CodeLens başvuruları penceresi](../ide/media/codelensreferencesdockedwindow.png "CodeLensReferencesDockedWindow")  

### <a name="q-how-do-i-refresh-the-indicators"></a>S: Göstergeleri nasıl yenileyebilirim?

**Y:** Bu gösterge üzerinde bağlıdır:  

-   **Başvuruları**: kod değiştiğinde bu gösterge otomatik olarak güncelleştirir. Bu gösterge ayrı bir pencerede yerleşik varsa, gösterge el ile burada yenileme:  

     ![CodeLens &#45; Pencere olarak Yerleştir](../ide/media/codelensviewreferencesdocked.png "CodeLensViewReferencesDocked")  

-   **Takım**: Burada Bu göstergeler el ile yenileme:  

     ![CodeLens &#45; Göstergeleri yenileme](../ide/media/codelensrefreshindicatorsfromcode.png "CodeLensRefreshIndicatorsFromCode")  

-   **Test**: [Bul kodunuz için birim testleri](#FindRunUnitTests) Bu gösterge yenilenecek.  

###  <a name="LocalVersion"></a>S: "Yerel sürümü" nedir?

**Y:** **yerel sürümü** ok yerel sürümünüzde bu dosyanın en son değişiklik gösterir. Üstüne veya altına sunucunun daha yeni değişiklik olduğunda, göründükleri **yerel sürümü** bağlı olarak değişiklik kümelerini sıralamak için kullanılan sırayı oku.

### <a name="q-can-i-manage-how-codelens-processes-code-to-show-history-and-linked-items"></a>S: CodeLens geçmişi ve bağlantılı öğeler göstermek için kod nasıl işlediği yönetebilirim?

**Y:** Evet, kodunuzu TFS'de ise, kullan [Codeındex komutu](../ide/codeindex-command.md) ile [TFS Config komutunu](/vsts/tfs-server/command-line/tfsconfig-cmd).

## <a name="see-also"></a>Ayrıca bkz.

[Kod Düzenleyicisi'nde yazma](../ide/writing-code-in-the-code-and-text-editor.md)