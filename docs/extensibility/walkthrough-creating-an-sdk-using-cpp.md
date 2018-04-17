---
title: 'İzlenecek yol: C++ kullanarak bir SDK oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 36ea793b-3832-41a1-b906-69e680ad5e1d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 33880dc3b9c359798c47c666debc3d5564524794
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-an-sdk-using-c"></a>İzlenecek yol: C++ kullanarak bir SDK oluşturma
Bu kılavuz, bir yerel C++ matematik kitaplığı SDK, Visual Studio Uzantısı (VSIX) olarak SDK paketini oluşturma ve bir uygulama oluşturmak için kullanma gösterilmektedir. İzlenecek yol aşağıdaki adımları ayrılır:  
  
-   [Yerel ve Windows çalışma zamanı kitaplıkları oluşturmak için](../extensibility/walkthrough-creating-an-sdk-using-cpp.md#createClassLibrary)  
  
-   [NativeMathVSIX uzantı projesi oluşturmak için](../extensibility/walkthrough-creating-an-sdk-using-cpp.md#createVSIX)  
  
-   [Sınıf kitaplığı kullanan örnek bir uygulama oluşturmak için](../extensibility/walkthrough-creating-an-sdk-using-cpp.md#createSample)  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda izlemek için Visual Studio SDK'yı yüklemeniz gerekir. Daha fazla bilgi için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
##  <a name="createClassLibrary"></a> Yerel ve Windows çalışma zamanı kitaplıkları oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
2.  Şablonları listesinde genişletin **Visual C++**, **Windows Evrensel**ve ardından **DLL (Windows Evrensel uygulamaları)** şablonu. İçinde **adı** kutusunda, belirtin `NativeMath`ve ardından **Tamam** düğmesi.  
  
3.  Aşağıdaki kod eşleşecek şekilde NativeMath.h güncelleştirin.  
  
     [!code-cpp[CreatingAnSDKUsingCpp#1](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_1.h)]  
  
4.  Bu kod eşleşecek şekilde NativeMath.cpp güncelleştirin:  
  
     [!code-cpp[CreatingAnSDKUsingCpp#2](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_2.cpp)]  
  
5.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **çözüm 'NativeMath'**ve ardından **Ekle**, **yeni proje**.  
  
6.  Şablonları listesinde genişletin **Visual C++**ve ardından **Windows çalışma zamanı bileşeni** şablonu. İçinde **adı** kutusunda, belirtin `NativeMathWRT`ve ardından **Tamam** düğmesi.  
  
7.  Bu kod eşleşecek şekilde Class1.h güncelleştirin:  
  
     [!code-cpp[CreatingAnSDKUsingCpp#3](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_3.h)]  
  
8.  Bu kod eşleşecek şekilde Class1.cpp güncelleştirin:  
  
     [!code-cpp[CreatingAnSDKUsingCpp#4](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_4.cpp)]  
  
9. Menü çubuğunda seçin **yapı**, **yapı çözümü**.  
  
##  <a name="createVSIX"></a> NativeMathVSIX uzantı projesi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **çözüm 'NativeMath'**ve ardından **Ekle**, **yeni proje**.  
  
2.  Şablonları listesinde genişletin **Visual C#**, **genişletilebilirlik**ve ardından **VSIX proje**. İçinde **adı** kutusunda, belirtin **NativeMathVSIX**ve ardından **Tamam** düğmesi.
  
3.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **source.extension.vsixmanifest**ve ardından **görünümü kodu**.  
  
4.  Varolan XML değiştirmek için aşağıdaki XML kullanın.  
  
    [!code-xml[CreatingAnSDKUsingCpp#6](../extensibility/codesnippet/XML/walkthrough-creating-an-sdk-using-cpp_6.xml)]

5.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **NativeMathVSIX** proje ve ardından **Ekle**, **yeni öğe**.  
  
6.  Listesinde **Visual C# öğeleri**, genişletin **veri**ve ardından **XML dosyası**. İçinde **adı** kutusunda, belirtin `SDKManifest.xml`ve ardından **Tamam** düğmesi.  
  
7.  Dosya içeriğini değiştirmek için bu XML kullanın:  
  
     [!code-xml[CreatingAnSDKUsingCpp#5](../extensibility/codesnippet/XML/walkthrough-creating-an-sdk-using-cpp_5.xml)]  
  
8. İçinde **Çözüm Gezgini**, **NativeMathVSIX** projesi, bu klasör yapısını oluşturun:  
  
    ```  
  
    \DesignTime  
          \CommonConfiguration  
                \Neutral  
                      \Include  
          \Debug  
                \x86  
    \Redist  
          \Debug  
                \x86  
    \References  
          \CommonConfiguration  
                \Neutral  
    ```  
  
9. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **çözüm 'NativeMath'**ve ardından **klasörünü dosya Gezgini'nde Aç**.  
  
10. İçinde **dosya Gezgini**, $SolutionRoot$\NativeMath\NativeMath.h, kopyalamak ve ardından **Çözüm Gezgini**, **NativeMathVSIX** projesi, $SolutionRoot yapıştırın $\ NativeMathVSIX\DesignTime\CommonConfiguration\Neutral\Include\ klasör.  
  
     $SolutionRoot$\Debug\NativeMath\NativeMath.lib kopyalayın ve ardından $SolutionRoot$ \NativeMathVSIX\DesignTime\Debug\x86\ klasörüne yapıştırın.  
  
     $SolutionRoot$\Debug\NativeMath\NativeMath.dll kopyalayıp $SolutionRoot$ \NativeMathVSIX\Redist\Debug\x86\ klasöründe yapıştırın.  
  
     $SolutionRoot$\Debug\NativeMathWRT\NativeMathWRT.dll kopyalayıp $SolutionRoot$ \NativeMathVSIX\Redist\Debug\x86 klasöründe yapıştırın.  
  
     $SolutionRoot$\Debug\NativeMathWRT\NativeMathWRT.winmd kopyalayıp $SolutionRoot$ \NativeMathVSIX\References\CommonConfiguration\Neutral klasöründe yapıştırın.  
  
     $SolutionRoot$\Debug\NativeMathWRT\NativeMathWRT.pri kopyalayıp $SolutionRoot$ \NativeMathVSIX\References\CommonConfiguration\Neutral klasöründe yapıştırın.  
  
11. $SolutionRoot$ \NativeMathVSIX\DesignTime\Debug\x86\ klasöründe NativeMathSDK.props adlı bir metin dosyası oluşturun ve ardından aşağıdaki içeriği yapıştırın:  
  
    [!code-xml[CreatingAnSDKUsingCpp#7](../extensibility/codesnippet/XML/walkthrough-creating-an-sdk-using-cpp_7.xml)]  
  
12. Menü çubuğunda seçin **Görünüm**, **diğer pencereler**, **Özellikler penceresini** (klavye: F4 anahtarı seçin).  
  
13. İçinde **Çözüm Gezgini**seçin **NativeMathWRT.winmd** dosya. İçinde **özellikleri** penceresinde, değişiklik **yapı eylemi** özelliğine **içerik**ve ardından değiştirmek **Include in VSIX** özelliğine **Doğru**.  
  
     Bu işlem için yineleme **NativeMath.h** dosya.  
  
     Bu işlem için yineleme **NativeMathWRT.pri** dosya.  
  
     Bu işlem için yineleme **NativeMath.Lib** dosya.  
  
     Bu işlem için yineleme **NativeMathSDK.props** dosya.  
  
14. İçinde **Çözüm Gezgini**seçin **NativeMath.h** dosya. İçinde **özellikleri** penceresinde, değişiklik **Include in VSIX** özelliğine **doğru**.  
  
     Bu işlem için yineleme **NativeMath.dll** dosya.  
  
     Bu işlem için yineleme **NativeMathWRT.dll** dosya.  
  
     Bu işlem için yineleme **SDKManifest.xml** dosya.  
  
15. Menü çubuğunda seçin **yapı**, **yapı çözümü**.  
  
16. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **NativeMathVSIX** proje ve ardından **klasörünü dosya Gezgini'nde Aç**.  
  
17. İçinde **dosya Gezgini**$SolutionRoot$ \NativeMathVSIX\bin\Debug\ klasörüne gidin ve ardından yüklemeyi başlatmak için NativeMathVSIX.vsix çalıştırın.  
  
18. Seçin **yükleme** düğmesi, yüklemesinin tamamlanması için bekleyin ve ardından Visual Studio'yu başlatın.  
  
##  <a name="createSample"></a> Sınıf kitaplığı kullanan örnek bir uygulama oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
2.  Şablonları listesinde genişletin **Visual C++**, **Windows Evrensel**ve ardından **boş uygulama**. İçinde **adı** kutusunda, belirtin **NativeMathSDKSample**ve ardından **Tamam** düğmesi.  
  
3.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **NativeMathSDKSample** proje ve ardından **Ekle**, **başvuru**.  
  
4.  İçinde **Başvuru Ekle** iletişim kutusunda, başvuru türlerinin bir listesini genişletin **Evrensel Windows**ve ardından **uzantıları**. Son olarak, seçin **yerel matematik SDK** onay kutusunu işaretleyin ve ardından **Tamam** düğmesi.
  
5.  Proje özellikleri için NativeMathSDKSample görüntüler.  
  
     NativeMathSDK.props içinde tanımlanan özellikleri başvurusunu eklendiğinde uygulandı. Bunu inceleyerek doğrulamak **VC ++ dizinleri** projenin özelliğinin **yapılandırma özellikleri**.  
  
6.  İçinde **Çözüm Gezgini**MainPage.xaml açın ve ardından içeriği değiştirmek için aşağıdaki XAML kullanın:  
  
     [!code-xml[CreatingAnSDKUsingCppDemoApp#1](../extensibility/codesnippet/Xaml/walkthrough-creating-an-sdk-using-cpp_8.xaml)]  
  
7.  Bu kod eşleşecek şekilde Mainpage.xaml.h güncelleştirin:  
  
     [!code-cpp[CreatingAnSDKUsingCppDemoApp#2](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_9.h)]  
  
8. Bu kod eşleşecek şekilde MainPage.xaml.cpp güncelleştirin:  
  
     [!code-cpp[CreatingAnSDKUsingCppDemoApp#3](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_10.cpp)]  
  
9. Uygulamayı çalıştırmak için F5 tuşuna seçin.  
  
10. Uygulamada, herhangi iki sayıyı girin, bir işlem seçin ve ardından **=** düğmesi.  
  
     Doğru sonucu görünür.  
  
 Bu kılavuzda gösterilen oluşturmak ve çağırmak için bir uzantı SDK kullanma bir [!INCLUDE[wrt](../extensibility/includes/wrt_md.md)] kitaplığı ve olmayan bir[!INCLUDE[wrt](../extensibility/includes/wrt_md.md)] kitaplığı.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: C# veya Visual Basic kullanan bir SDK oluşturma](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md)   
 [Yazılık Geliştirme Seti Oluşturma](../extensibility/creating-a-software-development-kit.md)