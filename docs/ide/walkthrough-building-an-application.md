---
title: 'İzlenecek yol: bir uygulama oluşturma'
ms.date: 09/25/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ccafe38714df4d3851e0f81de0f2b03e9d72db52
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-build-an-application"></a>İzlenecek yol: bir uygulama oluşturma

Bu kılavuzu izleyerek daha Visual Studio ile uygulamalar derlerken yapılandırabileceğiniz çeşitli seçenekler öğrenmeniz. Özel derleme yapılandırması oluşturma, belirli uyarı iletileri Gizle ve örnek uygulaması derleme çıktı bilgilerini artar.

## <a name="install-the-sample-application"></a>Örnek uygulamayı yükle

Karşıdan [WPF uygulamalarını giriş](https://code.msdn.microsoft.com/Introduction-to-Building-b8d16419) örnek. C# veya Visual Basic seçin. .Zip dosyasını indirdiği sonra projeyi ayıklayın ve açın **ExpenseItIntro.sln** Visual Studio kullanarak dosya.

## <a name="create-a-custom-build-configuration"></a>Özel derleme yapılandırması oluşturma

Bir çözüm oluşturduğunuzda, hata ayıklama ve yayın derleme yapılandırmaları ve varsayılan platform hedeflerine çözüm için otomatik olarak tanımlanır. Ardından, bu yapılandırmalar özelleştirebilir veya kendinizinkini oluşturun. Derleme yapılandırmaları yapı türü belirtin. Bu yapılandırma için bir uygulama hedefler işletim sistemi yapı platformları belirtin. Daha fazla bilgi için bkz: [derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md), [yapı platformlarını anlama](../ide/understanding-build-platforms.md), ve [nasıl yapılır: ayarlama hata ayıklama ve yayın yapılandırmaları](../debugger/how-to-set-debug-and-release-configurations.md).

Değiştirebilir veya yapılandırmaları ve platform ayarları kullanarak oluşturma **Configuration Manager** iletişim kutusu. Bu yordamda, test etmek için bir yapı yapılandırması oluşturacaksınız.

### <a name="to-create-a-build-configuration"></a>Yapı yapılandırması oluşturmak için

1. Açık **Configuration Manager** iletişim kutusu.

   ![Menüsü, Configuration Manager komutu yapı](../ide/media/buildwalk_configurationmanagerdialogbox.png "BuildWalk_ConfigurationManagerDialogBox")

1. İçinde **etkin çözüm yapılandırması** listesinde, seçin  **\<yeni... \>**.

1. İçinde **yeni çözüm yapılandırması** iletişim kutusunda, yeni yapılandırma adı `Test`, varolan bir hata ayıklama yapılandırmasından ayarları kopyalayın ve ardından **Tamam** düğmesi.

   ![Yeni çözüm yapılandırması iletişim kutusu](../ide/media/buildwalk_newsolutionconfigdlgbox.png "BuildWalk_NewSolutionConfigDlgBox")

1. İçinde **etkin çözüm platformu** listesinde, seçin  **\<yeni... \>**.

1. İçinde **yeni çözüm platformu** iletişim kutusunda, seçin **x64**ve ayarları x86 kopyalama platform.

   ![Yeni çözüm platformu iletişim kutusu](../ide/media/buildwalk_newsolutionplatform.png "BuildWalk_NewSolutionPlatform")

1. Seçin **Tamam** düğmesi.

   Etkin çözüm yapılandırmasını testine x64 için ayarlanmış etkin çözüm platformu ile değiştirildi.

   ![Configuration Manager ile Test yapılandırması](../ide/media/buildwalk_configmanagertestconfig.png "BuildWalk_ConfigManagerTestconfig")

1. Seçin **Kapat**.

Hızlı bir şekilde doğrulamak veya kullanarak etkin çözüm yapılandırmasını değiştirmek **çözüm yapılandırmaları** listesini **standart** araç.

![Çözüm yapılandırma seçeneği standart araç](../ide/media/buildwalk_standardtoolbarsolutioncongfig.png "BuildWalk_StandardToolbarSolutionCongfig")

## <a name="build-the-application"></a>Uygulama oluşturma

Ardından, özel yapı yapılandırması çözümüyle yapı.

### <a name="to-build-the-solution"></a>Çözümü derlemek için

-   Menü çubuğunda seçin **yapı** > **yapı çözümü**.

    **Çıkış** penceresi yapı sonuçlarını görüntüler. Yapı başarılı oldu.

## <a name="hide-compiler-warnings"></a>Derleyici uyarılarını gizleme

Sonraki biz derleyici tarafından üretilen bir uyarı neden olan bazı kodlar eklemeniz.

1. C# projesinde, açık **ExpenseReportPage.xaml.cs** dosya. İçinde **ExpenseReportPage** yöntemi, aşağıdaki kodu ekleyin: `int i;`.

    VEYA

    Visual Basic projesinde açmak **ExpenseReportPage.xaml.vb** dosya. Özel Oluşturucuda **ortak Sub New...** , aşağıdaki kodu ekleyin: `Dim i`.

1. Çözümü oluşturun.

**Çıkış** penceresi yapı sonuçlarını görüntüler. Yapı başarılı oldu ancak uyarılar oluşturuldu:

![Çıktı penceresi Visual Basic](../ide/media/buildwalk_vbbuildoutputwnd.png "BuildWalk_VBBuildOutputWnd")

![Çıktı penceresi Visual C&#35;](../ide/media/buildwalk_csharpbuildoutputwnd.png "BuildWalk_CsharpBuildOutputWnd")

Geçici olarak derleme sırasında belirli uyarı iletileri Gizle yerine, bunları yapı çıktıda karmaşıklığa.

### <a name="to-hide-a-specific-c-warning"></a>Belirli bir C# uyarı gizleme

1. İçinde **Çözüm Gezgini**, üst düzey proje düğümünü seçin.

1. Menü çubuğunda seçin **Görünüm**, **özellik sayfaları**.

     **Proje Tasarımcısı** açar.

1. Seçin **yapı** sayfasında, daha sonra **uyarıları bastırma** kutusunda, uyarı numarasını belirtin **0168**.

     ![Derleme sayfası, Proje Tasarımcısı](../ide/media/buildwalk_csharpsupresswarnings.png "BuildWalk_CsharpSupressWarnings")

     Daha fazla bilgi için bkz: [derleme sayfası, Proje Tasarımcısı (C#)](../ide/reference/build-page-project-designer-csharp.md).

1. Çözümü oluşturun.

     **Çıkış** penceresi yalnızca derleme için Özet bilgiler görüntüler.

     ![Çıktı penceresi, Visual C&#35; uyarıları yapı](../ide/media/buildwalk_visualcsharpbuildwarnings.png "BuildWalk_VisualCsharpBuildWarnings")

### <a name="to-suppress-all-visual-basic-build-warnings"></a>Tüm Visual Basic derleme uyarıları gizlemek için

1. İçinde **Çözüm Gezgini**, üst düzey proje düğümünü seçin.

1. Menü çubuğunda seçin **Görünüm**, **özellik sayfaları**.

     **Proje Tasarımcısı** açar.

1. Üzerinde **derleme** sayfasında, **tüm uyarıları devre dışı bırakmak** onay kutusu.

     ![Derle sayfası, Proje Tasarımcısı](../ide/media/buildwalk_vbsupresswarnings.png "BuildWalk_VBSupressWarnings")

     Daha fazla bilgi için bkz: [yapılandırma uyarılarını Visual Basic'te](../ide/configuring-warnings-in-visual-basic.md).

1. Çözümü oluşturun.

 **Çıkış** penceresi yalnızca derleme için Özet bilgiler görüntüler.

 ![Çıktı penceresi, Visual Basic derleme uyarıları](../ide/media/buildwalk_visualbasicbuildwarnings.png "BuildWalk_VisualBasicBuildWarnings")

 Daha fazla bilgi için bkz: [nasıl yapılır: Derleyici uyarılarını bastırma](../ide/how-to-suppress-compiler-warnings.md).

## <a name="display-additional-build-details-in-the-output-window"></a>Ek derleme ayrıntılarını çıkış penceresinde görüntüle

Derleme işlemi hakkında ne kadar bilgi görünür değiştirebilirsiniz **çıkış** penceresi. Yapı ayrıntı genellikle ayarlanmış çok az; yani **çıkış** penceresi, yüksek öncelikli uyarı veya hata yanı sıra oluşturma işlemi yalnızca bir özetini görüntüler. Kullanarak derleme hakkında daha fazla bilgi görüntüleyebilirsiniz [Seçenekler iletişim kutusu, projeler ve çözümler, derleme ve çalıştırma](../ide/reference/options-dialog-box-projects-and-solutions-build-and-run.md).

> [!IMPORTANT]
> Daha fazla bilgi görüntülemek, yapı tamamlamak için daha uzun sürer.


### <a name="to-change-the-amount-of-information-in-the-output-window"></a>Çıktı penceresinde bilgi miktarını değiştirmek için

1. Açık **seçenekleri** iletişim kutusu.

     ![Araçlar menüsündeki Seçenekler](../ide/media/exploreide-toolsoptionsmenu.png "ExploreIDE ToolsOptionsmenu")

1. Seçin **projeler ve çözümler** kategorisi ve ardından **derleme ve çalıştırma** sayfası.

1. İçinde **MSBuild Proje yapı çıktı ayrıntı** listesinde, seçin **Normal**ve ardından **Tamam** düğmesi.

1. Menü çubuğunda seçin **yapı**, **temiz çözüm**.

1. Çözümü derlemek ve bilgileri gözden geçirin **çıkış** penceresi.

     Yapı başlatıldığı zamanı (başında bulunur) ve dosyaları işlenmiş olan sıra yapı bilgileri içerir. Bu bilgiler, Visual Studio derleme sırasında çalışan gerçek derleyici sözdizimi de içerir.

     Örneğin, derlemede C#, [/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn) seçeneği, diğer üç uyarıları yanı sıra bu konunun önceki kısımlarında belirtilen 1762, uyarı kod listeler.

     Visual Basic derlemede [/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn) hiçbir uyarıların görünmesi için dışlamak için belirli uyarılar dahil değildir.

    > [!TIP]
    > İçeriğini arama **çıkış** görüntü penceresini **Bul** Ctrl + F tuşlarına seçerek iletişim kutusu.

Daha fazla bilgi için bkz: [nasıl yapılır: görünümü, kaydetme ve yapı günlük dosyalarını Yapılandır](../ide/how-to-view-save-and-configure-build-log-files.md).

## <a name="create-a-release-build"></a>Yayın derlemesi oluşturma

Aktarma için optimize edilmiş örnek uygulama sürümünü oluşturabilirsiniz. Yayın derlemesi için derleme koparılan önce yürütülebilir bir ağ paylaşımına kopyalandığını belirtirsiniz.

Daha fazla bilgi için bkz: [nasıl yapılır: yapı çıktı dizinini değiştirme](../ide/how-to-change-the-build-output-directory.md) ve [oluşturma ve temizleme projeler ve çözümler Visual Studio'da](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md).

### <a name="to-specify-a-release-build-for-visual-basic"></a>Yayın derlemesi için Visual Basic belirtmek için

1. Açık **Proje Tasarımcısı**.

     ![Görünüm menüsü, özellik sayfaları komutu](../ide/media/buildwalk_viewpropertypages.png "BuildWalk_ViewPropertyPages")

1. Seçin **derleme** sayfası.

1. İçinde **yapılandırma** listesinde, seçin **sürüm**.

1. İçinde **Platform** listesinde, seçin **x86**.

1. İçinde **yapı çıkış yolu** kutusunda, bir ağ yolu belirtin.

     Örneğin, belirtebilirsiniz \\\myserver\builds.

    > [!IMPORTANT]
    > Belirttiğiniz ağ paylaşımı güvenilir bir konumdayken olmayabilir uyarı iletisi kutusu görünebilir. Belirttiğiniz konuma güveniyorsanız seçin **Tamam** ileti kutusunda düğme.

1. Uygulamayı oluşturun.

     ![Build menüsünden yapı çözümü komutu](../ide/media/exploreide-buildsolution.png "ExploreIDE BuildSolution")

### <a name="to-specify-a-release-build-for-c"></a>Yayın derlemesi C# ' ta belirtmek için #

1. Açık **Proje Tasarımcısı**.

     ![Görünüm menüsü, özellik sayfaları komutu](../ide/media/buildwalk_viewpropertypages.png "BuildWalk_ViewPropertyPages")

1. Seçin **yapı** sayfası.

1. İçinde **yapılandırma** listesinde, seçin **sürüm**.

1. İçinde **Platform** listesinde, seçin **x86**.

1. İçinde **çıkış yolu** kutusunda, bir ağ yolu belirtin.

     Örneğin, belirtebilirsiniz \\\myserver\builds.

    > [!IMPORTANT]
    > Belirttiğiniz ağ paylaşımı güvenilir bir konumdayken olmayabilir uyarı iletisi kutusu görünebilir. Belirttiğiniz konuma güveniyorsanız seçin **Tamam** ileti kutusunda düğme.

1. Üzerinde **standart araç**, çözüm yapılandırmaları ayarlamak **sürüm** ve çözüm platformları **x86**.

1. Uygulamayı oluşturun.

     ![Build menüsünden yapı çözümü komutu](../ide/media/exploreide-buildsolution.png "ExploreIDE BuildSolution")

   Yürütülebilir dosya, belirttiğiniz ağ yolunu kopyalanır. Kendi yol \\\myserver\builds\\*FileName*.exe.

Tebrikler: Bu kılavuzda başarıyla tamamladınız.

## <a name="see-also"></a>Ayrıca bkz.

- [İzlenecek Yol: Proje Derleme (C++)](/cpp/ide/walkthrough-building-a-project-cpp)
- [ASP.NET Web uygulaması projesi ön derleme genel bakış](http://msdn.microsoft.com/b940abbd-178d-4570-b441-52914fa7b887)
- [İzlenecek Yol: MSBuild Kullanma](../msbuild/walkthrough-using-msbuild.md)