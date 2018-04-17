---
title: 'İzlenecek yol: sıfırdan MSBuild proje dosyası oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, tutorial
ms.assetid: e3acff7c-cb4e-4ae1-8be2-a871bcff847b
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b01e917d0e46c6e5a5d91473332062a75ff1e33d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-an-msbuild-project-file-from-scratch"></a>İzlenecek Yol: Sıfırdan MSBuild Proje Dosyası Oluşturma
.NET Framework hedefleyen programlama dilleri açıklar ve uygulama oluşturma işlemi denetlemek için MSBuild proje dosyalarını kullanın. MSBuild proje dosyası oluşturmak için Visual Studio kullandığınızda uygun XML dosyasına otomatik olarak eklenir. Ancak, XML nasıl düzenlendiğini anlaşılması yararlı ve bu derleme denetlemek için nasıl değiştirebilirsiniz.  
  
 C++ projesi için bir proje dosyası oluşturma hakkında daha fazla bilgi için bkz: [MSBuild (Visual C++)](/cpp/build/msbuild-visual-cpp).  
  
 Bu kılavuz temel proje dosyasını artımlı olarak, yalnızca bir metin düzenleyicisi kullanarak oluşturulacağını gösterir. İzlenecek yol aşağıdaki adımları izler:  
  
-   En az uygulama kaynak dosyası oluşturun.  
  
-   En az bir MSBuild proje dosyası oluşturun.  
  
-   PATH ortam değişkeni'MSBuild içerecek şekilde genişletir.  
  
-   Proje dosyası kullanarak uygulamayı oluşturun.  
  
-   Yapı denetlemek için özellikler ekleyin.  
  
-   Derleme özelliği değerlerini değiştirerek denetler.  
  
-   Hedefleri derleme ekleyin.  
  
-   Yapı hedefleri belirterek denetler.  
  
-   Artımlı olarak derleme.  
  
 Bu kılavuz, komut isteminde projeyi oluşturun ve sonuçları inceleyin gösterilmektedir. MSBuild ve MSBuild komut isteminde çalıştırma hakkında daha fazla bilgi için bkz: [izlenecek yol: MSBuild kullanma](../msbuild/walkthrough-using-msbuild.md).  
  
 İzlenecek yol tamamlamak için kılavuz için gerekli olan MSBuild ve Visual C# Derleyici, içerdiği için yüklü .NET Framework (sürüm 2.0, 3.5, 4.0 ve 4.5) olması gerekir.  
  
## <a name="creating-a-minimal-application"></a>En az bir uygulama oluşturma  
 Bu bölümde bir minimal Visual C# uygulama kaynak dosyası bir metin kullanarak Düzenleyicisi nasıl oluşturulacağını gösterir.  
  
#### <a name="to-create-the-minimal-application"></a>En az uygulaması oluşturmak için  
  
1.  Komut isteminde \My Documents\ veya \Desktop bu gibi bir durumda uygulaması oluşturmak istediğiniz klasöre göz atın\\.  
  
2.  Tür **md HelloWorld** \HelloWorld adlı bir alt klasör oluşturmak için\\.  
  
3.  Tür **cd HelloWorld** yeni klasör olarak değiştirmek için.  
  
4.  Not Defteri'ni veya başka bir metin Düzenleyicisi'ni başlatın ve sonra aşağıdaki kodu yazın.  
  
    ```csharp
    using System;  
  
    class HelloWorld  
    {  
        static void Main()  
        {  
    #if DebugConfig  
            Console.WriteLine("WE ARE IN THE DEBUG CONFIGURATION");  
    #endif  
  
            Console.WriteLine("Hello, world!");  
        }  
    }  
    ```  
  
5.  Bu kaynak kodu dosyasına kaydedin ve Helloworld.cs olarak adlandırın.  
  
6.  Uygulama yazarak yapı **csc helloworld.cs** komut isteminde.  
  
7.  Uygulamayı yazarak test **helloworld** komut isteminde.  
  
     **Hello, world!** iletisi görüntülenmelidir.  
  
8.  Uygulama yazarak silin **del helloworld.exe** komut isteminde.  
  
## <a name="creating-a-minimal-msbuild-project-file"></a>En az MSBuild proje dosyası oluşturma  
 En az uygulama kaynak dosyası sahip olduğunuza göre uygulamanızı oluşturmak için en az proje dosyası oluşturabilirsiniz. Bu proje dosyası aşağıdaki öğeleri içerir:  
  
-   Gereken kök `Project` düğümü.  
  
-   Bir `ItemGroup` düğümü öğesi öğeleri içerir.  
  
-   Uygulama kaynak dosyaya bir öğe öğesi.  
  
-   A `Target` düğüm uygulama oluşturmak için gereken görevleri içerir.  
  
-   A `Task` uygulamayı oluşturmak için Visual C# Derleyici başlatmak için öğesi.  
  
#### <a name="to-create-a-minimal-msbuild-project-file"></a>En az bir MSBuild proje dosyası oluşturmak için  
  
1.  Metin Düzenleyicisi'nde, bu iki satır kullanarak var olan metin değiştirin:  
  
    ```xml  
    <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    </Project>  
    ```  
  
2.  Bu Ekle `ItemGroup` düğümün bir alt öğesi olarak `Project` düğümü:  
  
    ```xml  
    <ItemGroup>  
      <Compile Include="helloworld.cs" />  
    </ItemGroup>  
    ```  
  
     Bildirim bu `ItemGroup` zaten bir öğe öğe içeriyor.  
  
3.  Ekleme bir `Target` düğümün bir alt öğesi olarak `Project` düğümü. Düğüm adı `Build`.  
  
    ```xml  
    <Target Name="Build">  
    </Target>  
    ```  
  
4.  Bu görev öğesi bir alt öğesi Ekle `Target` düğümü:  
  
    ```xml  
    <Csc Sources="@(Compile)"/>  
    ```  
  
5.  Bu proje dosyasını kaydedin ve Helloworld.csproj olarak adlandırın.  
  
 En az proje dosyanıza aşağıdaki kod benzemelidir:  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <ItemGroup>  
    <Compile Include="helloworld.cs" />  
  </ItemGroup>  
  <Target Name="Build">  
    <Csc Sources="@(Compile)"/>    
  </Target>  
</Project>  
```  
  
 Yapı hedefi görevlerinde sıralı olarak yürütülür. Bu durumda, Visual C# derleyici `Csc` yalnızca görev bir görevdir. Kaynak dosyaları derlemek için listesini bekliyor ve bu değeri tarafından belirtilen `Compile` öğesi. `Compile` Öğesi yalnızca bir kaynak dosyasını, Helloworld.cs başvuruyor.  
  
> [!NOTE]
>  Öğe öğesinde gibi .cs dosya adı uzantısına sahip tüm dosyaları başvurmak için yıldız joker karakter (*) kullanabilirsiniz:  
>   
>  `<Compile Include="*.cs" />`  
>   
>  Hata ayıklama ve seçmeli yaptığından ancak, joker karakter kullanımını önermiyoruz kaynak dosyaları eklenmiş veya silinmiş daha zor hedefleme.  
  
## <a name="extending-the-path-to-include-msbuild"></a>MSBuild dahil yolu genişletme  
 MSBuild erişebilmeniz için önce .NET Framework klasörünü içerecek şekilde PATH ortam değişkeni genişletmeniz gerekir.  
  
#### <a name="to-add-msbuild-to-your-path"></a>MSBuild yolunuzu eklemek için  
  
-   Visual Studio 2013'ten başlayarak, MSBuild.exe MSBuild klasöründe bulabilirsiniz (`%ProgramFiles%\MSBuild` bir 32 bit işletim sisteminde veya `%ProgramFiles(x86)%\MSBuild` bir 64-bit işletim sisteminde).  
  
     Komut isteminde **PATH=%PATH%;%ProgramFiles%\MSBuild ayarlamak** veya **YOLUNU ayarlama = % PATH %; % ProgramFiles (x86) %\MSBuild**.  
  
     Alternatif olarak, Visual Studio yüklüyse, kullanabileceğiniz **Visual Studio komut istemi**, MSBuild klasörünü içeren bir yolu vardır.  
  
## <a name="using-the-project-file-to-build-the-application"></a>Uygulamayı derlemek için proje dosyası kullanma  
 Şimdi uygulamayı oluşturmak için yeni oluşturduğunuz proje dosyası kullanın.  
  
#### <a name="to-build-the-application"></a>Uygulamayı yapılandırmak için  
  
1.  Komut isteminde **msbuild helloworld.csproj /t:Build**.  
  
     Bu, Helloworld proje dosyası derleme hedefi Helloworld uygulaması oluşturmak için Visual C# Derleyici çağırarak oluşturur.  
  
2.  Uygulamayı yazarak test **helloworld**.  
  
     **Hello, world!** iletisi görüntülenmelidir.  
  
> [!NOTE]
>  Ayrıntı düzeyi artırarak derleme hakkında daha fazla ayrıntı görebilirsiniz. "Ayrıntılı" için ayrıntı düzeyini ayarlamak için komut isteminde aşağıdaki komutlardan birini yazın:  
>   
>  **MSBuild helloworld.csproj /t:Build /verbosity: ayrıntılı**  
  
## <a name="adding-build-properties"></a>Yapı Özellikler ekleme  
 Daha fazla denetim yapı proje dosyasına derleme özellikleri ekleyebilirsiniz. Artık bu özellikleri ekleyin:  
  
-   Bir `AssemblyName` özelliği uygulamanın adını belirtin.  
  
-   Bir `OutputPath` özelliği uygulamayı içeren bir klasör belirtin.  
  
#### <a name="to-add-build-properties"></a>Derleme özellikleri eklemek için  
  
1.  Mevcut uygulama yazarak silin **del helloworld.exe** komut isteminde.  
  
2.  Bu proje dosyasında Ekle `PropertyGroup` öğesi açtıktan hemen sonra `Project` öğe:  
  
    ```xml  
    <PropertyGroup>  
      <AssemblyName>MSBuildSample</AssemblyName>  
      <OutputPath>Bin\</OutputPath>  
    </PropertyGroup>  
    ```  
  
3.  Bu görev yapı hedefine hemen önüne ekleyin `Csc` görevi:  
  
    ```xml  
    <MakeDir Directories="$(OutputPath)"      Condition="!Exists('$(OutputPath)')" />  
    ```  
  
     `MakeDir` Görev tarafından adlı bir klasör oluşturur `OutputPath` aynı adı taşıyan bir klasör bulunmadığından mevcut sağlanan özelliği.  
  
4.  Bu ekleme `OutputAssembly` özniteliğini `Csc` görevi:  
  
    ```xml  
    <Csc Sources="@(Compile)" OutputAssembly="$(OutputPath)$(AssemblyName).exe" />  
    ```  
  
     Bu tarafından adlı bir derleme üretmek için Visual C# derleyiciye `AssemblyName` özelliği ve tarafından adlı bir klasör koymak için `OutputPath` özelliği.  
  
5.  Değişikliklerinizi kaydedin.  
  
 Proje dosyanıza aşağıdaki kod artık benzemelidir:  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <PropertyGroup>  
    <AssemblyName>MSBuildSample</AssemblyName>  
    <OutputPath>Bin\</OutputPath>  
  </PropertyGroup>  
  <ItemGroup>  
    <Compile Include="helloworld.cs" />  
  </ItemGroup>  
  <Target Name="Build">  
    <MakeDir Directories="$(OutputPath)" Condition="!Exists('$(OutputPath)')" />  
    <Csc Sources="@(Compile)" OutputAssembly="$(OutputPath)$(AssemblyName).exe" />  
  </Target>  
</Project>  
```  
  
> [!NOTE]
>  Ters eğik çizgi eklemenizi öneririz (\\) içinde belirttiğinizde klasör adının sonunda yol ayırıcısı `OutputPath` içinde eklemek yerine öğesi `OutputAssembly` özniteliği `Csc` görev. Bu nedenle,  
>   
>  `<OutputPath>Bin\</OutputPath>`  
>   
>  `OutputAssembly=="$(OutputPath)$(AssemblyName).exe" />`  
>   
>  daha iyidir  
>   
>  `<OutputPath>Bin</OutputPath>`  
>   
>  `OutputAssembly=="$(OutputPath)\$(AssemblyName).exe" />`  
  
## <a name="testing-the-build-properties"></a>Yapı özelliklerini test etme  
 Şimdi, çıkış klasörü ve uygulama adı belirtmek için derleme özellikleri kullanılan proje dosyası kullanarak uygulama oluşturabilirsiniz.  
  
#### <a name="to-test-the-build-properties"></a>Yapı özelliklerini sınamak için  
  
1.  Komut isteminde **msbuild helloworld.csproj /t:Build**.  
  
     Bu \Bin\ klasörü oluşturur ve ardından MSBuildSample uygulaması oluşturmak için Visual C# derleyici çağırır ve \Bin\ klasöründe yerleştirir.  
  
2.  \Bin\ klasörü oluşturuldu ve MSBuildSample uygulama içerdiğini doğrulamak için aşağıdakileri yazın **dir depo**.  
  
3.  Uygulamayı yazarak test **Bin\MSBuildSample**.  
  
     **Hello, world!** iletisi görüntülenmelidir.  
  
## <a name="adding-build-targets"></a>Yapı hedefleri ekleme  
 Ardından, iki daha fazla hedefleri proje dosyasına aşağıdaki şekilde ekleyin:  
  
-   Eski dosyaları siler temiz bir hedefi.  
  
-   Kullanan bir yeniden hedef `DependsOnTargets` temiz görevi derleme görevi önce çalışacak şekilde zorlamak için öznitelik.  
  
 Birden çok hedef sahip olduğunuza göre yapı hedefi varsayılan hedef olarak ayarlayabilirsiniz.  
  
#### <a name="to-add-build-targets"></a>Yapı hedeflerini eklemek için  
  
1.  Proje dosyasında yalnızca derleme hedef sonra bu iki hedeflerde ekleyin:  
  
    ```xml  
    <Target Name="Clean" >  
      <Delete Files="$(OutputPath)$(AssemblyName).exe" />  
    </Target>  
    <Target Name="Rebuild" DependsOnTargets="Clean;Build" />  
    ```  
  
     Temiz hedef uygulamayı silmek için Delete görev çağırır. Temiz hedef ve yapı hedefi çalıştırılana kadar yeniden hedef çalışmaz. Rebuild hedef hiçbir görev olsa da, temiz hedef önce yapı hedef çalışmasına neden olur.  
  
2.  Bu ekleme `DefaultTargets` özniteliği için açılış `Project` öğe:  
  
    ```xml  
    <Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ```  
  
     Bu yapı hedefi varsayılan hedef olarak ayarlar.  
  
 Proje dosyanıza aşağıdaki kod artık benzemelidir:  
  
```xml  
<Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <PropertyGroup>  
    <AssemblyName>MSBuildSample</AssemblyName>  
    <OutputPath>Bin\</OutputPath>  
  </PropertyGroup>  
  <ItemGroup>  
    <Compile Include="helloworld.cs" />  
  </ItemGroup>  
  <Target Name="Build">  
    <MakeDir Directories="$(OutputPath)" Condition="!Exists('$(OutputPath)')" />  
    <Csc Sources="@(Compile)" OutputAssembly="$(OutputPath)$(AssemblyName).exe" />  
  </Target>  
  <Target Name="Clean" >  
    <Delete Files="$(OutputPath)$(AssemblyName).exe" />  
  </Target>  
  <Target Name="Rebuild" DependsOnTargets="Clean;Build" />  
</Project>  
```  
  
## <a name="testing-the-build-targets"></a>Yapı hedefleri test etme  
 Bu proje dosyası özelliklerini test etmek için yeni derleme hedefler alıştırma yapabilirsiniz:  
  
-   Varsayılan derleme oluşturma.  
  
-   Uygulama adı komut isteminde ayarlama.  
  
-   Başka bir uygulama oluşturulmadan önce uygulaması siliniyor.  
  
-   Uygulama, başka bir uygulama oluşturmadan siliniyor.  
  
#### <a name="to-test-the-build-targets"></a>Yapı hedefleri sınamak için  
  
1.  Komut isteminde **msbuild helloworld.csproj /p:AssemblyName Tebrikler =**.  
  
     Kullanmaz çünkü **/t** hedef açıkça ayarlamak için geçiş, MSBuild varsayılan derleme hedefi çalıştırılır. **/P** geçiş geçersiz kılmaları `AssemblyName` özelliği ve yeni değer verir `Greetings`. Bu \Bin\ klasöründe oluşturulan yeni bir uygulama, Greetings.exe, neden olur.  
  
2.  \Bin\ klasörünü MSBuildSample uygulama ve yeni Tebrikler uygulama içerdiğini doğrulamak için aşağıdakileri yazın **dir depo**.  
  
3.  Tebrikler uygulama yazarak test **Bin\Greetings**.  
  
     **Hello, world!** iletisi görüntülenmelidir.  
  
4.  Yazarak MSBuildSample uygulamayı silmek **msbuild helloworld.csproj /t: temiz**.  
  
     Bu varsayılan olan uygulamayı kaldırmak için temiz görev çalıştırır `AssemblyName` özellik değeri `MSBuildSample`.  
  
5.  Tebrikler uygulama yazarak silin **msbuild helloworld.csproj /t: temiz /p:AssemblyName Tebrikler =**.  
  
     Bu uygulamanın kaldırmak için temiz görev çalıştırır verilen **AssemblyName** özellik değeri `Greetings`.  
  
6.  \Bin\ klasör boş olduğunu doğrulamak için aşağıdakileri yazın **dir depo**.  
  
7.  Tür **msbuild**.  
  
     Proje dosyası belirtilmemiş rağmen geçerli klasörde yalnızca bir proje dosyası olduğundan MSBuild helloworld.csproj dosyası oluşturur. Bu \Bin\ klasöründe oluşturulacak MSBuildSample uygulamanın neden olur.  
  
     \Bin\ klasörünü MSBuildSample uygulama içerdiğini doğrulamak için aşağıdakileri yazın **dir depo**.  
  
## <a name="building-incrementally"></a>Artımlı şekilde derleme  
 Kaynak veya hedef bağlıdır hedef dosyalar yalnızca değiştirdiyseniz, hedef oluşturmak için MSBuild anlayabilirsiniz. MSBuild dosyasının zaman damgası, değişip değişmediğini belirlemek için kullanır.  
  
#### <a name="to-build-incrementally"></a>Artımlı olarak oluşturmak için  
  
1.  Proje dosyasında bu öznitelikler açılış yapı hedefi ekleyin:  
  
    ```  
    Inputs="@(Compile)" Outputs="$(OutputPath)$(AssemblyName).exe"  
    ```  
  
     Bu yapı hedefi olarak belirtilen girdi dosyaları bağlı olduğunu belirtir `Compile` öğesi grubu ve Çıkış hedefini uygulama dosyasının olduğunu.  
  
     Sonuçta elde edilen yapı hedef aşağıdaki kodu benzemelidir:  
  
    ```xml  
    <Target Name="Build" Inputs="@(Compile)" Outputs="$(OutputPath)$(AssemblyName).exe">  
      <MakeDir Directories="$(OutputPath)" Condition="!Exists('$(OutputPath)')" />  
      <Csc Sources="@(Compile)" OutputAssembly="$(OutputPath)$(AssemblyName).exe" />  
    </Target>  
    ```  
  
2.  Yapı hedefi yazarak test **msbuild /v:d** komut isteminde.  
  
     HelloWorld.csproj varsayılan proje dosyasıdır ve bu derleme varsayılan hedef olduğunu unutmayın.  
  
     **/V:d** anahtar oluşturma işlemi için ayrıntılı bir açıklama belirtir.  
  
     Bu satırlar görüntülenmesi gerekir:  
  
     **Tüm çıktı dosyaları giriş dosyalarına göre güncel olduğundan hedefi "Yapı" atlanıyor.**  
  
     **Giriş dosyaları: HelloWorld.cs**  
  
     **Çıkış dosyaları: BinMSBuildSample.exe**  
  
     Bu yana uygulama en son oluşturulan kaynak dosyaların hiçbiri değiştiğinden MSBuild yapı hedefi atlar.  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Derlenen bir proje dosyası aşağıdaki örnekte bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] uygulama ve çıktı dosyası adını içeren bir ileti günlüğe kaydeder.  
  
### <a name="code"></a>Kod  
  
```xml
<Project DefaultTargets = "Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <!-- Set the application name as a property -->  
    <PropertyGroup>  
        <appname>HelloWorldCS</appname>  
    </PropertyGroup>  
  
    <!-- Specify the inputs by type and file name -->  
    <ItemGroup>  
        <CSFile Include = "consolehwcs1.cs"/>  
    </ItemGroup>  
  
    <Target Name = "Compile">  
        <!-- Run the Visual C# compilation using input files of type CSFile -->  
        <CSC  
            Sources = "@(CSFile)"  
            OutputAssembly = "$(appname).exe">  
            <!-- Set the OutputAssembly attribute of the CSC task  
            to the name of the executable file that is created -->  
            <Output  
                TaskParameter = "OutputAssembly"  
                ItemName = "EXEFile" />  
        </CSC>  
        <!-- Log the file name of the output file -->  
        <Message Text="The output file is @(EXEFile)"/>  
    </Target>  
</Project>  
```  
  
### <a name="comments"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Derlenen bir proje dosyası aşağıdaki örnekte bir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] uygulama ve çıktı dosyası adını içeren bir ileti günlüğe kaydeder.  
  
### <a name="code"></a>Kod  
  
```xml  
<Project DefaultTargets = "Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <!-- Set the application name as a property -->  
    <PropertyGroup>  
        <appname>HelloWorldVB</appname>  
    </PropertyGroup>  
  
    <!-- Specify the inputs by type and file name -->  
    <ItemGroup>  
        <VBFile Include = "consolehwvb1.vb"/>  
    </ItemGroup>  
  
    <Target Name = "Compile">      
        <!-- Run the Visual Basic compilation using input files of type VBFile -->  
        <VBC  
            Sources = "@(VBFile)"  
            OutputAssembly= "$(appname).exe">  
            <!-- Set the OutputAssembly attribute of the VBC task  
            to the name of the executable file that is created -->  
            <Output  
                TaskParameter = "OutputAssembly"  
                ItemName = "EXEFile" />  
        </VBC>  
        <!-- Log the file name of the output file -->  
        <Message Text="The output file is @(EXEFile)"/>  
    </Target>  
</Project>  
```  
  
## <a name="whats-next"></a>Sonraki adım nedir?  
 Visual Studio otomatik olarak bu kılavuzda gösterilen işin çoğunu gerçekleştirebilirsiniz. Visual Studio oluşturma, düzenleme, yapı ve test MSBuild proje dosyaları için nasıl kullanılacağını öğrenmek için bkz: [izlenecek yol: MSBuild kullanma](../msbuild/walkthrough-using-msbuild.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[MSBuild genel bakış](../msbuild/msbuild.md)  
 [MSBuild Başvurusu](../msbuild/msbuild-reference.md)