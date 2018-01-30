---
title: "İzlenecek yol: uygulama oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4842955d-8959-4e4e-98b8-2358360179b3
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d24a8b0cfa54b56808e8d283534e03e607fca0c9
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="walkthrough-building-an-application"></a>İzlenecek yol: Uygulama Oluşturma

Bu kılavuzu izleyerek daha Visual Studio ile uygulamalar derlerken yapılandırabileceğiniz çeşitli seçenekler öğrenmeniz. Özel derleme yapılandırması oluşturma, belirli uyarı iletileri Gizle ve örnek uygulaması derleme çıktı bilgilerini artar.

## <a name="install-the-sample-application"></a>Örnek uygulamayı yükle

Karşıdan [WPF uygulamalarını giriş](https://code.msdn.microsoft.com/Introduction-to-Building-b8d16419) örnek. C# veya Visual Basic seçin. .Zip dosyasını indirdiği sonra projeyi ayıklayın ve açın **ExpenseItIntro.sln** Visual Studio kullanarak dosya.

## <a name="create-a-custom-build-configuration"></a>Özel derleme yapılandırması oluşturma

Bir çözüm oluşturduğunuzda, hata ayıklama ve yayın derleme yapılandırmaları ve varsayılan platform hedeflerine çözüm için otomatik olarak tanımlanır. Ardından, bu yapılandırmalar özelleştirebilir veya kendinizinkini oluşturun. Derleme yapılandırmaları yapı türü belirtin. Bu yapılandırma için bir uygulama hedefler işletim sistemi yapı platformları belirtin. Daha fazla bilgi için bkz: [derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md), [yapı platformlarını anlama](../ide/understanding-build-platforms.md), ve [nasıl yapılır: ayarlama hata ayıklama ve yayın yapılandırmaları](../debugger/how-to-set-debug-and-release-configurations.md).

Değiştirebilir veya yapılandırmaları ve platform ayarları kullanarak oluşturma **Configuration Manager** iletişim kutusu. Bu yordamda, test etmek için bir yapı yapılandırması oluşturacaksınız.

### <a name="to-create-a-build-configuration"></a>Yapı yapılandırması oluşturmak için
  
1. açık **Configuration Manager** iletişim kutusu.
  
     ![Build menu, Configuration Manager command](../ide/media/buildwalk_configurationmanagerdialogbox.png "BuildWalk_ConfigurationManagerDialogBox")  
  
2. buna **etkin çözüm yapılandırması** listesinde, seçin  **\<yeni... \>**.
  
3. buna **yeni çözüm yapılandırması** iletişim kutusunda, yeni yapılandırma adı `Test`, varolan bir hata ayıklama yapılandırmasından ayarları kopyalayın ve ardından **Tamam** düğmesi.
  
     ![New Solution Configuration Dialog Box](../ide/media/buildwalk_newsolutionconfigdlgbox.png "BuildWalk_NewSolutionConfigDlgBox")  
  
4 buna **etkin çözüm platformu** listesinde, seçin  **\<yeni... \>**.
  
5 içinde **yeni çözüm platformu** iletişim kutusunda, seçin **x64**ve ayarları x86 kopyalama platform.
  
     ![New Solution Platform Dialog Box](../ide/media/buildwalk_newsolutionplatform.png "BuildWalk_NewSolutionPlatform")  
  
6 seçin **Tamam** düğmesi.
  
 Etkin çözüm yapılandırmasını testine x64 için ayarlanmış etkin çözüm platformu ile değiştirildi.
  
 ![Configuration Manager ile Test yapılandırması](../ide/media/buildwalk_configmanagertestconfig.png "BuildWalk_ConfigManagerTestconfig")  
  
7. Seçin **Kapat**.

Hızlı bir şekilde doğrulamak veya kullanarak etkin çözüm yapılandırmasını değiştirmek **çözüm yapılandırmaları** listesini **standart** araç.
  
![Çözüm yapılandırma seçeneği standart araç](../ide/media/buildwalk_standardtoolbarsolutioncongfig.png "BuildWalk_StandardToolbarSolutionCongfig")  
  
## <a name="build-the-application"></a>Uygulama oluşturma

Ardından, özel yapı yapılandırması çözümüyle yapı.
  
### <a name="to-build-the-solution"></a>Çözümü derlemek için
  
-   Menü çubuğunda seçin **yapı**, **yapı çözümü**.
  
    **Çıkış** penceresi yapı sonuçlarını görüntüler. Yapı başarılı oldu.
  
## <a name="hide-compiler-warnings"></a>Derleyici uyarılarını gizleme

Sonraki biz derleyici tarafından üretilen bir uyarı neden olan bazı kodlar eklemeniz.

1. C# projesinde, açık **ExpenseReportPage.xaml.cs** dosya. İçinde **ExpenseReportPage** yöntemi, aşağıdaki kodu ekleyin: `int i;`.

    VEYA

    Visual Basic projesinde açmak **ExpenseReportPage.xaml.vb** dosya. Özel Oluşturucuda **ortak Sub New...** , aşağıdaki kodu ekleyin: `Dim i`.

2. Çözümü oluşturun.

**Çıkış** penceresi yapı sonuçlarını görüntüler. Yapı başarılı oldu ancak uyarılar oluşturuldu:  

 Şekil 1: Visual Basic uyarıları  
  
 ![Çıktı penceresi Visual Basic](../ide/media/buildwalk_vbbuildoutputwnd.png "BuildWalk_VBBuildOutputWnd")  
  
 Şekil 2: C# uyarıları  
  
 ![Çıktı penceresi Visual C &#35; ] (../ide/media/buildwalk_csharpbuildoutputwnd.png "BuildWalk_CsharpBuildOutputWnd")  
  
Geçici olarak derleme sırasında belirli uyarı iletileri Gizle yerine, bunları yapı çıktıda karmaşıklığa.

### <a name="to-hide-a-specific-c-warning"></a>Belirli bir C# uyarı gizleme
  
1. buna **Çözüm Gezgini**, üst düzey proje düğümünü seçin.
  
2. menü çubuğunda seçin **Görünüm**, **özellik sayfaları**.
  
     The **Project Designer** opens.
  
3. seçin **yapı** sayfasında, daha sonra **uyarıları bastırma** kutusunda, uyarı numarasını belirtin **0168**.
  
     ![Build page, Project Designer](../ide/media/buildwalk_csharpsupresswarnings.png "BuildWalk_CsharpSupressWarnings")  
  
     For more information, see [Build Page, Project Designer (C#)](../ide/reference/build-page-project-designer-csharp.md).
  
4 çözümü oluşturun.
  
     The **Output** window displays only summary information for the build.
  
     ![Output Window, Visual C&#35; Build Warnings](../ide/media/buildwalk_visualcsharpbuildwarnings.png "BuildWalk_VisualCsharpBuildWarnings")  
  
### <a name="to-suppress-all-visual-basic-build-warnings"></a>Tüm Visual Basic derleme uyarıları gizlemek için
  
1. buna **Çözüm Gezgini**, üst düzey proje düğümünü seçin.
  
2. menü çubuğunda seçin **Görünüm**, **özellik sayfaları**.
  
     The **Project Designer** opens.
  
3. üzerinde **derleme** sayfasında, **tüm uyarıları devre dışı bırakmak** onay kutusu.
  
     ![Compile page, Project Designer](../ide/media/buildwalk_vbsupresswarnings.png "BuildWalk_VBSupressWarnings")  
  
     For more information, see [Configuring Warnings in Visual Basic](../ide/configuring-warnings-in-visual-basic.md).
  
4 çözümü oluşturun.
  
 **Çıkış** penceresi yalnızca derleme için Özet bilgiler görüntüler.
  
 ![Çıktı penceresi, Visual Basic derleme uyarıları](../ide/media/buildwalk_visualbasicbuildwarnings.png "BuildWalk_VisualBasicBuildWarnings")  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: Derleyici uyarılarını bastırma](../ide/how-to-suppress-compiler-warnings.md).
  
## <a name="display-additional-build-details-in-the-output-window"></a>Ek derleme ayrıntılarını çıkış penceresinde görüntüle

Derleme işlemi hakkında ne kadar bilgi görünür değiştirebilirsiniz **çıkış** penceresi. Yapı ayrıntı genellikle ayarlanmış çok az; yani **çıkış** penceresi, yüksek öncelikli uyarı veya hata yanı sıra oluşturma işlemi yalnızca bir özetini görüntüler. Kullanarak derleme hakkında daha fazla bilgi görüntüleyebilirsiniz [Seçenekler iletişim kutusu, projeler ve çözümler, derleme ve çalıştırma](../ide/reference/options-dialog-box-projects-and-solutions-build-and-run.md).
  
> [!IMPORTANT]
>  Daha fazla bilgi görüntülemek, yapı tamamlamak için daha uzun sürer.
  
### <a name="to-change-the-amount-of-information-in-the-output-window"></a>Çıktı penceresinde bilgi miktarını değiştirmek için
  
1. açık **seçenekleri** iletişim kutusu.
  
     ![Options command on the Tools menu](../ide/media/exploreide-toolsoptionsmenu.png "ExploreIDE-ToolsOptionsmenu")  
  
2. seçin **projeler ve çözümler** kategorisi ve ardından **derleme ve çalıştırma** sayfası.
  
3. buna **MSBuild Proje yapı çıktı ayrıntı** listesinde, seçin **Normal**ve ardından **Tamam** düğmesi.
  
4 menü çubuğunda seçin **yapı**, **temiz çözüm**.
  
5 çözümü oluşturmak ve bilgileri gözden geçirin **çıkış** penceresi.
  
     The build information includes the time that the build started (located at the beginning) and the order in which files were processed. This information also includes the actual compiler syntax that Visual Studio runs during the build.
  
     For example, in the C# build, the [/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn) option lists the warning code, 1762, that you specified earlier in this topic, along with three other warnings.
  
     In the Visual Basic build, [/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn) doesn't include specific warnings to exclude, so no warnings appear.
  
    > [!TIP]
    >  You can search the contents of the **Output** window if you display the **Find** dialog box by choosing the Ctrl+F keys.
  
Daha fazla bilgi için bkz: [nasıl yapılır: görünümü, kaydetme ve yapı günlük dosyalarını Yapılandır](../ide/how-to-view-save-and-configure-build-log-files.md).
  
## <a name="create-a-release-build"></a>Yayın derlemesi oluşturma

Aktarma için optimize edilmiş örnek uygulama sürümünü oluşturabilirsiniz. Yayın derlemesi için derleme koparılan önce yürütülebilir bir ağ paylaşımına kopyalandığını belirtirsiniz.

Daha fazla bilgi için bkz: [nasıl yapılır: yapı çıktı dizinini değiştirme](../ide/how-to-change-the-build-output-directory.md) ve [oluşturma ve temizleme projeler ve çözümler Visual Studio'da](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md).

### <a name="to-specify-a-release-build-for-visual-basic"></a>Yayın derlemesi için Visual Basic belirtmek için
  
1. açık **Proje Tasarımcısı**.
  
     ![View menu, Property Pages command](../ide/media/buildwalk_viewpropertypages.png "BuildWalk_ViewPropertyPages")  
  
2. seçin **derleme** sayfası.
  
3. buna **yapılandırma** listesinde, seçin **sürüm**.
  
4 buna **Platform** listesinde, seçin **x86**.
  
5 içinde **yapı çıkış yolu** kutusunda, bir ağ yolu belirtin.
  
     For example, you can specify \\\myserver\builds.
  
    > [!IMPORTANT]
    >  A message box might appear, warning you that the network share that you've specified might not be a trusted location. If you trust the location that you've specified, choose the **OK** button in the message box.
  
6 uygulama oluşturun.
  
     ![Build Solution command on the Build menu](../ide/media/exploreide-buildsolution.png "ExploreIDE-BuildSolution")  
  
### <a name="to-specify-a-release-build-for-c"></a>Yayın derlemesi C# ' ta belirtmek için #
  
1. açık **Proje Tasarımcısı**.
  
     ![View menu, Property Pages command](../ide/media/buildwalk_viewpropertypages.png "BuildWalk_ViewPropertyPages")  
  
2. seçin **yapı** sayfası.
  
3. buna **yapılandırma** listesinde, seçin **sürüm**.
  
4 buna **Platform** listesinde, seçin **x86**.
  
5 içinde **çıkış yolu** kutusunda, bir ağ yolu belirtin.
  
     For example, you could specify \\\myserver\builds.
  
    > [!IMPORTANT]
    >  A message box might appear, warning you that the network share that you've specified might not be a trusted location. If you trust the location that you've specified, choose the **OK** button in the message box.
  
6 üzerinde **standart araç**, çözüm yapılandırmaları ayarlamak **sürüm** ve çözüm platformları **x86**.

7. uygulamayı oluşturun.
  
     ![Build Solution command on the Build menu](../ide/media/exploreide-buildsolution.png "ExploreIDE-BuildSolution")  
  
 Yürütülebilir dosya, belirttiğiniz ağ yolunu kopyalanır. Kendi yol \\\myserver\builds\\*FileName*.exe.
  
Tebrikler: Bu kılavuzda başarıyla tamamladınız.
  
## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yol: Proje Derleme (C++)](/cpp/ide/walkthrough-building-a-project-cpp)  
[ASP.NET Web uygulaması projesi ön derleme genel bakış](http://msdn.microsoft.com/b940abbd-178d-4570-b441-52914fa7b887)  
[İzlenecek Yol: MSBuild Kullanma](../msbuild/walkthrough-using-msbuild.md)
