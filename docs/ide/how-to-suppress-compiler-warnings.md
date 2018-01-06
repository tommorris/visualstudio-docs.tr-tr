---
title: "Nasıl yapılır: Derleyici uyarılarını gizleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31827b17-f933-413d-b28a-b19f903b64ca
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d97695cae08352ea213ba02008ab99bef7f61c47
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-suppress-compiler-warnings"></a>Nasıl yapılır: Derleyici Uyarılarını Gizleme
Derleyici uyarıları içerecek şekilde istemediğiniz bir veya daha fazla tür belirterek bir derleme günlüğü declutter. Örneğin, bazı gözden geçirmek için bu tekniği ancak tüm yapı günlük ayrıntı Normal, ayrıntılı veya tanılama olarak ayarlandığında, otomatik olarak oluşturulan bilgileri kullanabilirsiniz. Ayrıntı hakkında daha fazla bilgi için bkz: [nasıl yapılır: görünümü, kaydetme ve yapı günlük dosyalarını Yapılandır](../ide/how-to-view-save-and-configure-build-log-files.md).  
  
### <a name="to-suppress-specific-warnings-for-visual-c-or-f"></a>Visual C# veya F # için belirli uyarıları gizlemek için #
  
1.  İçinde **Çözüm Gezgini**, uyarıları bastırma projesini seçin.  
  
2.  Menü çubuğunda seçin **Görünüm**, **özellik sayfaları**.  
  
3.  Seçin **yapı** sayfası.  
  
4.  İçinde **uyarıları bastırma** kutusunda gizlemek istediğiniz uyarıların hata kodlarını noktalı virgülle ayırarak belirtin ve çözümü yeniden derleyin.  
  
### <a name="to-suppress-specific-warnings-for-visual-c"></a>Visual C++ için belirli uyarıları gizlemek için  
  
1.  İçinde **Çözüm Gezgini**, projeyi seçin veya kaynak uyarıları bastırma istediğiniz dosyası.  
  
2.  Menü çubuğunda seçin **Görünüm**, **özellik sayfaları**.  
  
3.  Seçin **yapılandırma özellikleri** kategorisi seçin **C/C++** kategorisi ve ardından **Gelişmiş** sayfası.  
  
4.  Aşağıdaki adımlardan birini uygulayın:  
  
    -   İçinde **belirli uyarıları devre dışı** kutusunda, noktalı virgülle ayrılmış gizlemek istediğiniz uyarıların hata kodlarını belirtin.  
  
    -   İçinde **belirli uyarıları devre dışı** kutusunda, seçin **Düzenle** daha fazla seçenek görüntülemek için.  
  
5.  Seçin **Tamam** düğmesine tıklayın ve ardından çözümü yeniden derleyin.  
  
## <a name="suppressing-warnings-for-visual-basic"></a>Visual Basic için uyarıları gizleme  
 Projesi için .vbproj dosyasını düzenleyerek, Visual Basic'te belirli derleyici uyarıları gizleyebilirsiniz. Aynı zamanda [derleme sayfası, Proje Tasarımcısı](../ide/reference/compile-page-project-designer-visual-basic.md) kategoriye göre uyarıları gizlemek için. Daha fazla bilgi için bkz: [yapılandırma uyarılarını Visual Basic'te](../ide/configuring-warnings-in-visual-basic.md).  
  
#### <a name="to-suppress-specific-warnings-for-visual-basic"></a>Visual Basic'te belirli uyarıları gizlemek için  
  
1.  İçinde **Çözüm Gezgini**, uyarıları bastırma projesini seçin.  
  
2.  Menü çubuğunda seçin **proje**, **projeyi**.  
  
3.  İçinde **Çözüm Gezgini**projesi için kısayol menüsünü açın ve ardından **Düzenle***ProjectName***.vbproj**.  
  
     Proje dosyası Kod Düzenleyicisi'nde açılır.  
  
4.  Bulun `<NoWarn></NoWarn>` sahip oluşturmakta yapı yapılandırma öğesi.  
  
     Aşağıdaki örnekte gösterildiği `<NoWarn></NoWarn>` x x86 hata ayıklama yapı yapılandırması kalın metin öğesinde platform:  
  
    ```  
    <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|x86' ">  
        <PlatformTarget>x86</PlatformTarget>  
        <DebugSymbols>true</DebugSymbols>  
        <DebugType>full</DebugType>  
        <Optimize>false</Optimize>  
        <OutputPath>bin\Debug\</OutputPath>  
        <DefineDebug>true</DefineDebug>  
        <DefineTrace>true</DefineTrace>  
        <ErrorReport>prompt</ErrorReport>  
        <NoWarn></NoWarn>  
        <WarningLevel>1</WarningLevel>  
      </PropertyGroup>  
    ```  
  
5.  Bir veya daha fazla uyarı numaraları değeri olarak ekleme `<NoWarn>` öğesi. Birden çok uyarı numaralarını belirtirseniz, aşağıdaki örnekte gösterildiği gibi bir virgül ile ayırın.  
  
    ```  
    <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|x86' ">  
        <PlatformTarget>x86</PlatformTarget>  
        <DebugSymbols>true</DebugSymbols>  
        <DebugType>full</DebugType>  
        <Optimize>false</Optimize>  
        <OutputPath>bin\Debug\</OutputPath>  
        <DefineDebug>true</DefineDebug>  
        <DefineTrace>true</DefineTrace>  
        <ErrorReport>prompt</ErrorReport>  
        <NoWarn>40059,42024</NoWarn>  
        <WarningLevel>1</WarningLevel>  
      </PropertyGroup>  
    ```  
  
6.  .Vbproj dosyasındaki değişiklikleri kaydedin.  
  
7.  Menü çubuğunda seçin **proje**, **projeyi yeniden yükle**.  
  
8.  Menü çubuğunda seçin **yapı**, **çözümü yeniden derle**.  
  
     **Çıkış** penceresi artık belirttiğiniz uyarıları gösterir.  
  
 Daha fazla bilgi için bkz: [/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: uygulama oluşturma](../ide/walkthrough-building-an-application.md)   
 [Nasıl yapılır: görüntüleme, kaydetme ve derleme günlüğü dosyalarını yapılandırma](../ide/how-to-view-save-and-configure-build-log-files.md)   
 [Derleme ve Oluşturma](../ide/compiling-and-building-in-visual-studio.md)
