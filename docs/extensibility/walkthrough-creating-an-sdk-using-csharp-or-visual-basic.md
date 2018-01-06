---
title: "İzlenecek yol: C# veya Visual Basic kullanan bir SDK oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef96a249-5eef-402a-a8d5-d74cb49239bd
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a8b0b8452fb20b9b6da4e8ad58c221010f23c9ed
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-an-sdk-using-c-or-visual-basic"></a>İzlenecek yol: C# veya Visual Basic kullanan bir SDK oluşturma
Bu kılavuzda, Visual C# kullanarak basit bir matematik kitaplığı SDK oluşturma ve bir Visual Studio Uzantısı (VSIX) olarak SDK paketini öğreneceksiniz. Aşağıdaki yordamları tamamlamanız:  
  
-   [SimpleMath Windows çalışma zamanı bileşeni oluşturmak için](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md#createClassLibrary)  
  
-   [SimpleMathVSIX uzantı projesi oluşturmak için](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md#createVSIX)  
  
-   [Sınıf kitaplığı kullanan örnek bir uygulama oluşturmak için](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md#createSample)  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda izlemek için Visual Studio SDK'yı yüklemeniz gerekir. Daha fazla bilgi için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
##  <a name="createClassLibrary"></a>SimpleMath Windows çalışma zamanı bileşeni oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **yeni proje**.  
  
2.  Şablonları listesinde genişletin **Visual C#** veya **Visual Basic**, seçin **Windows mağazası** düğümünü ve ardından **Windows çalışma zamanı bileşeni** şablonu.  
  
3.  İçinde **adı** kutusunda, belirtin **SimpleMath**ve ardından **Tamam** düğmesi.  
  
4.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **SimpleMath** proje düğümünü ve ardından **özellikleri**.  
  
5.  Yeniden Adlandır **Class1.cs** için **Arithmetic.cs** ve aşağıdaki kodu eşleşecek şekilde güncelleştirin:  
  
     [!code-csharp[CreatingAnSDKUsingWinRT#3](../extensibility/codesnippet/CSharp/walkthrough-creating-an-sdk-using-csharp-or-visual-basic_1.cs)]
     [!code-vb[CreatingAnSDKUsingWinRT#3](../extensibility/codesnippet/VisualBasic/walkthrough-creating-an-sdk-using-csharp-or-visual-basic_1.vb)]  
  
6.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **çözüm 'SimpleMath'** düğümünü ve ardından **Configuration Manager**.  
  
     **Configuration Manager** iletişim kutusu açılır.  
  
7.  İçinde **etkin çözüm yapılandırması** listesinde, seçin **sürüm**.  
  
8.  İçinde **yapılandırma** sütun doğrulayın **SimpleMath** satır ayarlanmış **sürüm**ve ardından **Kapat** kabul et düğmesi değiştirin.  
  
    > [!IMPORTANT]
    >  SDK SimpleMath bileşen için yalnızca bir yapılandırma içerir. Bu yapılandırma yayın derlemesi olmalıdır ya da bileşen kullanan uygulamalar olmaz sertifika için geçirmeniz[!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)].  
  
9. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **SimpleMath** proje düğümünü ve ardından **yapı**.  
  
##  <a name="createVSIX"></a>SimpleMathVSIX uzantı projesi oluşturmak için  
  
1.  Kısayol menüsünde **çözüm 'SimpleMath'** düğümü seçin **Ekle**, **yeni proje**.  
  
2.  Şablonları listesinde genişletin **Visual C#** veya **Visual Basic**, seçin **genişletilebilirlik** düğümünü ve ardından **VSIX proje** Şablon.  
  
3.  İçinde **adı** kutusunda, belirtin **SimpleMathVSIX**ve ardından **Tamam** düğmesi.  
  
4.  İçinde **Çözüm Gezgini**, seçin **source.extension.vsixmanifest** öğesi.  
  
5.  Menü çubuğunda seçin **Görünüm**, **kod**.  
  
6.  Varolan XML aşağıdaki XML ile değiştirin:  
  
     [!code-xml[CreatingAnSDKUsingWinRT#1](../extensibility/codesnippet/XML/walkthrough-creating-an-sdk-using-csharp-or-visual-basic_2.xml)]
  
7.  İçinde **Çözüm Gezgini**, seçin **SimpleMathVSIX** projesi.  
  
8.  Menü çubuğunda seçin **proje**, **Yeni Öğe Ekle**.  
  
9. Listesinde **ortak öğeler**, genişletin **veri**ve ardından **XML dosyası**.  
  
10. İçinde **adı** kutusunda, belirtin `SDKManifest.xml`ve ardından **Ekle** düğmesi.  
  
11. İçinde **Çözüm Gezgini**, kısayol menüsünü açın `SDKManifest.xml`, seçin **özellikleri**ve değerini değiştirme **Include in VSIX** özelliğine**True**.  
  
12. Dosyasının içeriğini aşağıdaki XML ile değiştirin:  

    **C#**
    ```xml
    <FileList
      DisplayName="WinRT Math Library (CS)"
      MinVSVersion="11.0"
      TargetFramework=".NETCore,version=v4.5"
      AppliesTo="WindowsAppContainer"
      SupportsMultipleVersions="Error"
      MoreInfo="http://www.msdn.microsoft.com/">
    </FileList>
    ```

    **Visual Basic**
    ```xml
    <FileList
      DisplayName="WinRT Math Library (VB)"
      MinVSVersion="11.0"
      TargetFramework=".NETCore,version=v4.5"
      AppliesTo="WindowsAppContainer"
      SupportsMultipleVersions="Error"
      MoreInfo="http://www.msdn.microsoft.com/">
    </FileList>
    ```  
  
13. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **SimpleMathVSIX** seçin, proje **Ekle**ve ardından **yeni klasör**.  
  
14. Klasörünü yeniden adlandırın `references`.  
  
15. Kısayol menüsünü açın **başvuruları** klasörünü seçin **Ekle**ve ardından **yeni klasör**.  
  
16. Alt klasöre yeniden adlandırma `commonconfiguration`içindeki bir alt klasör oluşturun ve alt klasör adı `neutral`.  
  
17. İlk klasöre yeniden adlandırma bu kez önceki dört adımı yineleyin `redist`.  
  
     Projeyi şimdi aşağıdaki klasör yapısını içerir:  
  
    ```
    references\commonconfiguration\neutral  
    redist\commonconfiguration\neutral  
    ```  
  
18. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **SimpleMath** proje ve ardından **klasörünü dosya Gezgini'nde Aç**.  
  
19. İçinde **dosya Gezgini**bin\Release klasöre gidin, SimpleMath.winmd dosya için kısayol menüsünü açın ve ardından **kopya**.  
  
20. İçinde **Çözüm Gezgini**, dosyayı references\commonconfiguration\neutral klasörüne yapıştırın **SimpleMathVSIX** projesi.  
  
21. Redist\commonconfiguration\neutral klasörüne SimpleMath.pri dosya yapıştırma önceki adımı yineleyin **SimpleMathVSIX** projesi.  
  
22. İçinde **Çözüm Gezgini**, seçin **SimpleMath.winmd**.  
  
23. Menü çubuğunda seçin **Görünüm**, **özellikleri** (klavye: F4 anahtarı seçin).  
  
24. İçinde **özellikleri** penceresinde, değişiklik **yapı eylemi** özelliğine **içerik**ve ardından değiştirmek **Include in VSIX** özelliğine **Doğru**.  
  
25. İçinde **Çözüm Gezgini**, bu işlem için yineleme **SimpleMath.pri**.  
  
26. İçinde **Çözüm Gezgini**, seçin **SimpleMathVSIX** projesi.  
  
27. Menü çubuğunda seçin **yapı**, **yapı SimpleMathVSIX**.  
  
28. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **SimpleMathVSIX** proje ve ardından **klasörünü dosya Gezgini'nde Aç**.  
  
29. İçinde **dosya Gezgini**\bin\Release klasörüne gidin ve ardından yüklemek için SimpleMathVSIX.vsix çalıştırın.  
  
30. Seçin **yükleme** düğmesi, yüklemesinin tamamlanması için bekleyin ve ardından Visual Studio'yu yeniden başlatın.  
  
##  <a name="createSample"></a>Sınıf kitaplığı kullanan örnek bir uygulama oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **yeni proje**.  
  
2.  Şablonları listesinde genişletin **Visual C#** veya **Visual Basic**ve ardından **Windows mağazası** düğümü.  
  
3.  Seçin **boş uygulama** şablonu, proje adı **ArithmeticUI**ve ardından **Tamam** düğmesi.  
  
4.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **ArithmeticUI** proje ve ardından **Ekle**, **başvuru**.  
  
5.  Başvuru türleri listesinde genişletin **Windows**ve ardından **uzantıları**.  
  
6.  Ayrıntılar bölmesinde seçin **basit matematik SDK** uzantısı.  
  
     SDK'sı hakkında ek bilgiler görüntülenir. Seçebileceğiniz **daha fazla bilgi** SDKManifest.xml dosyasında bu kılavuzda daha önce belirtildiği gibi http://www.msdn.microsoft.com, açmak için bağlantı.  
  
7.  İçinde **başvuru Yöneticisi** iletişim kutusunda **basit matematik SDK** onay kutusunu işaretleyin ve ardından **Tamam** düğmesi.  
  
8.  Menü çubuğunda seçin **Görünüm**, **Nesne Tarayıcısı**.  
  
9. İçinde **Gözat** listesinde, seçin **basit matematik**.  
  
     Artık SDK'ın ne olduğunu da gözden geçirebilirsiniz.  
  
10. İçinde **Çözüm Gezgini**MainPage.xaml açın ve içeriğini aşağıdaki XAML ile değiştirin:  

    **C#**
    ```xml
    <Page
        x:Class="WinRTMathTestCS.MainPage"
        IsTabStop="False"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:WinRTMathTestCS"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="d">

        <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">
            <TextBox x:Name="_firstNumber" HorizontalAlignment="Left" Margin="414,370,0,0" TextWrapping="Wrap" Text="First Number" VerticalAlignment="Top" Height="32" Width="135" TextAlignment="Center"/>
            <TextBox x:Name="_secondNumber" HorizontalAlignment="Left" Margin="613,370,0,0" TextWrapping="Wrap" Text="Second Number" VerticalAlignment="Top" Height="32" Width="135" TextAlignment="Center"/>
            <Button Content="+" HorizontalAlignment="Left" Margin="557,301,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="-" HorizontalAlignment="Left" Margin="557,345,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="*" HorizontalAlignment="Left" Margin="557,389,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="/" HorizontalAlignment="Left" Margin="557,433,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="=" HorizontalAlignment="Left" Margin="755,367,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnResultsClick"/>
            <TextBox x:Name="_result" HorizontalAlignment="Left" Margin="809,370,0,0" TextWrapping="Wrap" Text="Result" VerticalAlignment="Top" Height="32" Width="163" TextAlignment="Center" IsReadOnly="True"/>
        </Grid>
    </Page>
    ```
    
    **Visual Basic**
    ```xml
    <Page
        x:Class="WinRTMathTest.MainPage"
        IsTabStop="False"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:WinRTMathTest"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="d">

        <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">
            <TextBox x:Name="_firstNumber" HorizontalAlignment="Left" Margin="414,370,0,0" TextWrapping="Wrap" Text="First Number" VerticalAlignment="Top" Height="32" Width="135" TextAlignment="Center"/>
            <TextBox x:Name="_secondNumber" HorizontalAlignment="Left" Margin="613,370,0,0" TextWrapping="Wrap" Text="Second Number" VerticalAlignment="Top" Height="32" Width="135" TextAlignment="Center"/>
            <Button Content="+" HorizontalAlignment="Left" Margin="557,301,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="-" HorizontalAlignment="Left" Margin="557,345,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="*" HorizontalAlignment="Left" Margin="557,389,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="/" HorizontalAlignment="Left" Margin="557,433,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="=" HorizontalAlignment="Left" Margin="755,367,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnResultsClick"/>
            <TextBox x:Name="_result" HorizontalAlignment="Left" Margin="809,370,0,0" TextWrapping="Wrap" Text="Result" VerticalAlignment="Top" Height="32" Width="163" TextAlignment="Center" IsReadOnly="True"/>
        </Grid>
    </Page>
    ```
  
11. MainPage.xaml.cs aşağıdaki kodu eşleşecek şekilde güncelleştirin:  
  
     [!code-csharp[CreatingAnSDKUsingWinRTDemoApp#2](../extensibility/codesnippet/CSharp/walkthrough-creating-an-sdk-using-csharp-or-visual-basic_5.cs)]
     [!code-vb[CreatingAnSDKUsingWinRTDemoApp#2](../extensibility/codesnippet/VisualBasic/walkthrough-creating-an-sdk-using-csharp-or-visual-basic_5.vb)]  
  
12. Uygulamayı çalıştırmak için F5 tuşuna seçin.  
  
13. Uygulamada, herhangi iki sayıyı girin, bir işlem seçin ve ardından  **=**  düğmesi.  
  
     Doğru sonucu görünür.  
  
 Başarıyla oluşturduktan ve bir uzantı SDK kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: C++ kullanarak bir SDK oluşturma](../extensibility/walkthrough-creating-an-sdk-using-cpp.md)   
 [İzlenecek yol: JavaScript kullanarak bir SDK oluşturma](http://msdn.microsoft.com/en-us/6195ff56-4a27-45fc-bd29-4b0451225f4b)   
 [Yazılık Geliştirme Seti Oluşturma](../extensibility/creating-a-software-development-kit.md)