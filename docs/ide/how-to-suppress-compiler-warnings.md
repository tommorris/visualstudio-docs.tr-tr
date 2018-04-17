---
title: Visual Studio'da projeler ve NuGet paketleri için Derleyici uyarılarını gizleme | Microsoft Docs
ms.custom: ''
ms.date: 01/24/2018
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 08e224a25a30345cffc73bb5442d7fe6acd8b35b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-suppress-compiler-warnings"></a>Nasıl yapılır: Derleyici uyarılarını gizleme

Derleyici uyarıları bir veya daha fazla tür filtreleyerek bir derleme günlüğü declutter. Örneğin, Normal, ayrıntılı veya tanılama derleme günlüğü ayrıntı ayarladığınızda, oluşturulan çıktı yalnızca bir kısmını gözden geçirmek isteyebilirsiniz. Ayrıntı hakkında daha fazla bilgi için bkz: [nasıl yapılır: görünümü, kaydetme ve derleme günlüğü dosyalarını yapılandırma](../ide/how-to-view-save-and-configure-build-log-files.md).

## <a name="suppressing-specific-warnings-for-visual-c-or-f"></a>Visual C# veya F # için belirli uyarıları gizleme #

Kullanım **yapı** C# ve F # projeleri için belirli uyarıları gizlemek için özellik sayfası.

1. İçinde **Çözüm Gezgini**, uyarıları bastırma projesini seçin.

1. Menü çubuğunda seçin **Görünüm** > **özellik sayfaları**.

1. Seçin **yapı** sayfası.

1. İçinde **uyarıları bastırma** kutusunda, gizlemek istediğiniz uyarıların hata kodlarını noktalı virgülle ayırarak belirtin.

1. Çözümü yeniden derleyin.

## <a name="suppressing-specific-warnings-for-visual-c"></a>Visual C++ için belirli uyarıları gizleme

Kullanım **yapılandırma özellikleri** C++ projeleri için belirli uyarıları gizlemek için özellik sayfası.

1. İçinde **Çözüm Gezgini**, projeyi seçin veya kaynak uyarıları bastırma istediğiniz dosyası.

1. Menü çubuğunda seçin **Görünüm** > **özellik sayfaları**.

1. Seçin **yapılandırma özellikleri** kategorisi seçin **C/C++** kategorisi ve ardından **Gelişmiş** sayfası.

1. Aşağıdaki adımlardan birini uygulayın:

    - İçinde **belirli uyarıları devre dışı** kutusunda, noktalı virgülle ayrılmış gizlemek istediğiniz uyarıların hata kodlarını belirtin.

    - İçinde **belirli uyarıları devre dışı** kutusunda, seçin **Düzenle** daha fazla seçenek görüntülemek için.

1. Seçin **Tamam** düğmesine tıklayın ve ardından çözümü yeniden derleyin.

## <a name="suppressing-warnings-for-visual-basic"></a>Visual Basic için uyarıları gizleme

Visual Basic'te belirli derleyici uyarıları düzenleyerek gizleyebilirsiniz *.vbproj* proje dosyası. Tarafından uyarıları gizlemek için *kategori*, kullanabileceğiniz [derleme özellik sayfası](../ide/reference/compile-page-project-designer-visual-basic.md). Daha fazla bilgi için bkz: [Visual Basic'te uyarıları yapılandırma](../ide/configuring-warnings-in-visual-basic.md).

### <a name="to-suppress-specific-warnings-for-visual-basic"></a>Visual Basic'te belirli uyarıları gizlemek için

Bu örnek nasıl düzenleneceğini gösterir *.vbproj* belirli derleyici uyarıları gizlemek için dosya.

1. İçinde **Çözüm Gezgini**, uyarıları bastırma projesini seçin.

1. Menü çubuğunda seçin **proje** > **projeyi**.

1. İçinde **Çözüm Gezgini**projesi için sağ tıklatın veya kısayol menüsünü açın ve ardından **Düzenle** *ProjectName* **.vbproj**.

    XML proje dosyası Kod Düzenleyicisi'nde açılır.

1. Bulun `<NoWarn>` yapı yapılandırma öğesi, ile oluşturmakta olduğunuz ve değeri olarak bir veya daha fazla uyarı numaraları ekleme `<NoWarn>` öğesi. Birden çok uyarı numaralarını belirtirseniz, bunları virgül ile ayırın.

     Aşağıdaki örnekte gösterildiği `<NoWarn>` öğesi için *hata ayıklama* x x86 yapılandırmasına yapı platformuyla gizlenen iki derleyici uyarıları:

    ```xml
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

   > [!NOTE]
   > .NET core projeleri, varsayılan olarak yapı yapılandırma özelliği gruplarını içermiyor. .NET Core projesinde uyarıları gizlemek için dosyaya yapı yapılandırma bölümü el ile ekleyin. Örneğin:
   >
   > ```xml
   > <Project Sdk="Microsoft.NET.Sdk">
   >   <PropertyGroup>
   >     <OutputType>Exe</OutputType>
   >     <TargetFramework>netcoreapp2.0</TargetFramework>
   >     <RootNamespace>VBDotNetCore_1</RootNamespace>
   >   </PropertyGroup>
   >   <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">
   >     <NoWarn>42016,41999,42017</NoWarn>
   >   </PropertyGroup>
   > </Project>
   > ```

1. Değişiklikleri kaydetmek *.vbproj* dosya.

1. Menü çubuğunda seçin **proje** > **projeyi yeniden yükle**.

1. Menü çubuğunda seçin **yapı** > **çözümü yeniden derle**.

    **Çıkış** penceresi artık belirttiğiniz uyarıları gösterir.

Daha fazla bilgi için bkz: [/nowarn derleyici seçeneği](/dotnet/visual-basic/reference/command-line-compiler/nowarn) için Visual Basic komut satırı derleyicisi.

## <a name="suppressing-warnings-for-nuget-packages"></a>NuGet paketleri için uyarıları gizleme

Bazı durumlarda, projenin tamamı için yerine tek bir NuGet paketi için NuGet Derleyici uyarılarını bastırma isteyebilirsiniz. Proje düzeyinde gizlemek istemediğiniz için uyarı bir amaca hizmet eder. Örneğin, NuGet uyarıları biri, paket projenizi ile tamamen uyumlu olmayabilir bildirir. Proje düzeyinde bastırmak ve daha sonra ek bir NuGet paketi eklerseniz, uyumluluk uyarı oluşturan, hiçbir zaman anlarsınız.

### <a name="to-suppress-a-specific-warning-for-a-single-nuget-package"></a>Tek bir NuGet paketi için belirli bir uyarıyı gizlemek için

1. İçinde **Çözüm Gezgini**, derleyici uyarılarını gizleme NuGet paketi seçin.

   ![Çözüm Gezgini'nde NuGet paketi](media/nuget-package-with-warning.png)

1. Sağ tıklatın veya bağlam menüsünden seçin **özellikleri**.

1. İçinde **NoWarn** kutusunu paket özelliklerini gizlemek için bu paket için istediğiniz uyarı sayı girin. Birden fazla gizlemek istiyorsanız, uyarı sayıları ayırmak için virgül kullanın.

   ![NuGet paket özellikleri](media/nuget-properties-nowarn.png)

   Uyarı kaybolur **Çözüm Gezgini** ve **hata listesi**.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek yol: Uygulama Oluşturma](../ide/walkthrough-building-an-application.md)  
[Nasıl yapılır: Derleme Günlüğü Dosyalarını Görüntüleme, Kaydetme ve Yapılandırma](../ide/how-to-view-save-and-configure-build-log-files.md)  
[Derleme ve Oluşturma](../ide/compiling-and-building-in-visual-studio.md)
