---
title: Visual Studio'da derleme sürecinde kod oluşturma
ms.date: 03/22/2018
ms.topic: conceptual
helpviewer_keywords:
- text templates, build tasks
- text templates, transforming by using msbuild
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 1d08aafd31d93c7a07d57dcd5b831b8ae41a6c17
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="code-generation-in-a-build-process"></a>Derleme sürecinde kod oluşturma

[Metin dönüştürmeyi](../modeling/code-generation-and-t4-text-templates.md) parçası olarak çağrılabilir [derleme işlemi](http://msdn.microsoft.com/Library/a971b0f9-7c28-479d-a37b-8fd7e27ef692) , bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözümü. Metin dönüştürme için özelleştirilmiş yapı görevleri vardır. T4 yapı görevleri tasarım zamanı metin şablonlarını çalıştırır ve aynı zamanda çalışma zamanı (önişlenmiş) metin şablonlarını derler.

Kullandığınız oluşturma motoruna bağlı olarak, yapı görevleri farklı işlevleri yerine getirebilirler. Visual Studio çözümü yapılandırdığınızda, bir metin şablonuna Visual Studio API (EnvDTE) erişebilirsiniz [hostspecific = "true"](../modeling/t4-template-directive.md) özniteliği olarak ayarlanmış. Ancak, çözüm komut satırından derlerken veya Visual Studio aracılığıyla server yapı başlattığınızda doğru değil. Bu durumlarda, yapı MSBuild tarafından oluşturulur ve farklı bir T4 ana bilgisayar kullanılır.

MSBuild bir metin şablonu oluşturduğunuzda, proje dosyası adları gibi şeyleri aynı şekilde erişemeyeceğiniz anlamına gelir. Ancak, [yapı parametreleri kullanarak ortam bilgi metin şablonları ve yönerge işlemcileri aktarmak](#parameters).

##  <a name="buildserver"></a> Makinelerinizi yapılandırın

Derleme görevleri geliştirme bilgisayarınızda etkinleştirmek için Visual Studio için modelleme SDK'sını yükleyin.

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

Varsa [yapı sunucunuz](http://msdn.microsoft.com/Library/788443c3-0547-452e-959c-4805573813a9) bir bilgisayar üzerinde çalışan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] olan yüklü değil, aşağıdaki dosyaları yapı bilgisayara geliştirme makinenizden kopyalayın. En son sürüm numaraları yerine ' *'.

-   $(ProgramFiles)\MSBuild\Microsoft\VisualStudio\v*.0\TextTemplating

    -   Microsoft.VisualStudio.TextTemplating.Sdk.Host.*.0.dll

    -   Microsoft.TextTemplating.Build.Tasks.dll

    -   Microsoft.TextTemplating.targets

-   $(ProgramFiles) \Microsoft Visual Studio *.0\VSSDK\VisualStudioIntegration\Common\Assemblies\v4.0

    -   Microsoft.VisualStudio.TextTemplating.*.0.dll

    -   Microsoft.VisualStudio.TextTemplating.Interfaces.*.0.dll (several files)

    -   Microsoft.VisualStudio.TextTemplating.VSHost.*.0.dll

-   $(ProgramFiles) \Microsoft Visual Studio *.0\Common7\IDE\PublicAssemblies\

    -   Microsoft.VisualStudio.TextTemplating.Modeling.*.0.dll

## <a name="to-edit-the-project-file"></a>Projeyi dosyasını düzenlemek için

Bazı özelliklerini Msbuild'de yapılandırmak için proje dosyasını düzenlemeniz gerekir.

Çözüm Gezgini'nde seçin **Unload** projenizin bağlam menüsünden. Bu .csproj veya .vbproj dosyasını XML düzenleyicisinde düzenlemenize olanak tanır.

Düzenlemeyi tamamladığınızda seçin **yeniden**.

## <a name="import-the-text-transformation-targets"></a>Metin dönüştürmeyi hedefleri alma

.Vbproj veya .csproj dosyasında şöyle bir satır bulun:

`<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />`

\- veya -

`<Import Project="$(MSBuildToolsPath)\Microsoft.VisualBasic.targets" />`

Bu satırın ardından, Metin Şablon Oluşturma almayı ekleyin:

```xml
<!-- Optionally make the import portable across VS versions -->
  <PropertyGroup>
    <!-- Get the Visual Studio version - defaults to 10: -->
    <VisualStudioVersion Condition="'$(VisualStudioVersion)' == ''">10.0</VisualStudioVersion>
    <!-- Keep the next element all on one line: -->
    <VSToolsPath Condition="'$(VSToolsPath)' == ''">$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v$(VisualStudioVersion)</VSToolsPath>
  </PropertyGroup>

<!-- This is the important line: -->
  <Import Project="$(VSToolsPath)\TextTemplating\Microsoft.TextTemplating.targets" />
```

## <a name="transform-templates-in-a-build"></a>Derleme şablonları dönüştürme

Dönüştürme görevini kontrol etmek için proje dosyanızın içine ekleyebileceğiniz bazı özellikler vardır:

-   Dönüştürme görevini her yapı başlangıcında çalıştır:

    ```xml
    <PropertyGroup>
        <TransformOnBuild>true</TransformOnBuild>
    </PropertyGroup>
    ```

-   Salt okunur dosyaların üzerine yaz (ör. kullanıma alınmamış oldukları için): 

    ```xml
    <PropertyGroup>
        <OverwriteReadOnlyOutputFiles>true</OverwriteReadOnlyOutputFiles>
    </PropertyGroup>
    ```

-   Her şablonu her zaman dönüştür:

    ```xml
    <PropertyGroup>
        <TransformOutOfDateOnly>false</TransformOutOfDateOnly>
    </PropertyGroup>
    ```

     Varsayılan olarak, T4 MSBuild görevi, kendi şablon dosyasından ya da içerdiği dosyaların herhangi birinden veya şablon ya da kullandığı yönerge işlemcisi tarafından önceden okunmuş herhangi bir dosyadan eski ise, bir çıktı dosyası oluşturur. Bunun, Visual Studio'da bulunan ve yalnızca şablon ve çıktı dosyası tarihlerini karşılaştıran Tüm Şablonları Dönüştür komutu tarafından kullanılandan daha güçlü bir bağımlılık testi olduğuna dikkat edin.

 Projenizde yalnızca metin dönüştürmeleri gerçekleştirmek için TransformAll görevini çağırın:

 `msbuild myProject.csproj /t:TransformAll`

 Belirli metin şablonu dönüştürmek için:

 `msbuild myProject.csproj /t:Transform /p:TransformFile="Template1.tt"`

 TransformFile içinde joker karakterler kullanabilirsiniz:

 `msbuild dsl.csproj /t:Transform /p:TransformFile="GeneratedCode\**\*.tt"`

## <a name="source-control"></a>Kaynak denetimi

Kaynak denetim sistemi ile yerleşik herhangi bir tümleştirme yoktur. Ancak, örneğin oluşturulmuş bir dosyayı kullanıma almak ve iade etmek için, kendi uzantılarınızı ekleyebilirsiniz. Varsayılan olarak, metin dönüştürme görevi salt okunur işaretli bir dosyanın üzerine yazmaktan kaçınır ve bu tür bir dosyayla karşılaşıldığında Visual Studio hata listesinde bir hata günlüğe kaydedilir ve görev başarısız olur.

 Salt okunur dosyaların üzerine yazılması gerektiğini belirtmek için bu özelliği ekleyin:

 `<OverwriteReadOnlyOutputFiles>true</OverwriteReadOnlyOuputFiles>`

 Son işleme adımını özelleştirmediğiniz sürece, herhangi bir dosyanın üzerine yazıldığında, hata listesinde bir uyarı günlüğe kaydedilir.

## <a name="customize-the-build-process"></a>Derleme süreci özelleştirme

Oluşturma işleminde diğer görevlerden önce metin dönüştürme gerçekleşir. Özellikleri ayarlayarak önce ve dönüştürme sonra çağrılan görevleri tanımlayabilirsiniz `$(BeforeTransform)` ve `$(AfterTransform)`:

```xml
<PropertyGroup>
    <BeforeTransform>CustomPreTransform</BeforeTransform>
    <AfterTransform>CustomPostTransform</AfterTransform>
  </PropertyGroup>
  <Target Name="CustomPreTransform">
    <Message Text="In CustomPreTransform..." Importance="High" />
  </Target>
  <Target Name="CustomPostTransform">
    <Message Text="In CustomPostTransform..." Importance="High" />
  </Target>
```

İçinde `AfterTransform`, dosyaların listelerini başvurabilir:

-   GeneratedFiles - işlem tarafından yazılan dosyaların listesi. Varolan salt okunur dosyaların üzerine yazan bu dosyalar için, %(GeneratedFiles.ReadOnlyFileOverwritten) doğru olacaktır. Bu dosyalar kaynak denetiminden denetlenebilir.

-   NonGeneratedFiles - üzerine yazılmamış, salt okunur dosyaların listesi.

Örneğin, GeneratedFiles'ı kullanıma almak için bir görev tanımlarsınız.

## <a name="outputfilepath-and-outputfilename"></a>OutputFilePath ve OutputFileName

Bu özellikler yalnızca MSBuild tarafından kullanılır. Visual Studio'da kod üretimi etkilemez. Bunlar, oluşturulan çıktı dosyasını farklı bir klasör veya dosyaya yeniden yönlendirir. Hedef klasörün zaten bulunması gerekir.

```xml
<ItemGroup>
  <None Include="MyTemplate.tt">
    <Generator>TextTemplatingFileGenerator</Generator>
    <OutputFilePath>MyFolder</OutputFilePath>
    <LastGenOutput>MyTemplate.cs</LastGenOutput>
  </None>
</ItemGroup>
```

 Yeniden yönlendirmek için yararlı bir klasörü `$(IntermediateOutputPath).`

 Dosya adını belirtir ve çıktısını alırsanız, şablonlardaki çıktı yönergesinde belirtilen uzantıdan öncelikli olur.

```xml
<ItemGroup>
  <None Include="MyTemplate.tt">
    <Generator>TextTemplatingFileGenerator</Generator>
    <OutputFileName>MyOutputFileName.cs</OutputFileName>
    <LastGenOutput>MyTemplate.cs</LastGenOutput>
  </None>
</ItemGroup>
```

 Dönüştürme tüm kullanarak ya da tek bir dosya oluşturucu çalıştırılırken VS içinde şablonları da dönüştürüyorsanız çıkışdosyaadı ya da OutputFilePath belirterek önerilmez. Dönüştürme işlemini nasıl tetiklediğinizde bağlı olarak, farklı dosya yolları elde edebilirsiniz. Bu çok kafa karıştırıcı olabilir.

## <a name="add-reference-and-include-paths"></a>Başvuru ekleme ve yolları içerir

Ana bilgisayar, şablonlarda başvurulan derlemeler için arama yaptığı varsayılan bir grup yola sahiptir. Bu gruba ekleme yapmak için:

```xml
<ItemGroup>
    <T4ReferencePath Include="$(VsIdePath)PublicAssemblies\" />
    <!-- Add more T4ReferencePath items here -->
</ItemGroup>
```

Ekleme kodu dosyalarının aranacağı klasörleri ayarlamak için, noktalı virgülle ayrılmış bir liste sağlayın. Genellikle varolan klasör listesine eklersiniz.

```xml
<PropertyGroup>
    <IncludeFolders>
$(IncludeFolders);$(MSBuildProjectDirectory)\Include;AnotherFolder;And\Another</IncludeFolders>
</PropertyGroup>
```

##  <a name="parameters"></a> Şablonlara yapı bağlam verileri geçirmek

Proje dosyasında parametre değerlerini ayarlayabilirsiniz. Örneğin, geçirebilirsiniz [yapı](../msbuild/msbuild-properties.md) özellikleri ve [ortam değişkenleri](../msbuild/how-to-use-environment-variables-in-a-build.md):

```xml
<ItemGroup>
  <T4ParameterValues Include="ProjectFolder">
    <Value>$(ProjectDir)</Value>
    <Visible>false</Visible>
  </T4ParameterValues>
</ItemGroup>
```

 Bir metin şablonuna ayarlamak `hostspecific` şablon yönergesi. Kullanım [parametresi](../modeling/t4-parameter-directive.md) yönergesi değerlerini almak için:

```
<#@template language="c#" hostspecific="true"#>
<#@ parameter type="System.String" name="ProjectFolder" #>
The project folder is: <#= ProjectFolder #>
```

Bir yönerge işlemcisi içinde çağırabilirsiniz [ITextTemplatingEngineHost.ResolveParameterValue](https://msdn.microsoft.com/library/microsoft.visualstudio.texttemplating.itexttemplatingenginehost.resolveparametervalue.aspx):

```csharp
string value = Host.ResolveParameterValue("-", "-", "parameterName");
```

```vb
Dim value = Host.ResolveParameterValue("-", "-", "parameterName")
```

> [!NOTE]
> `ResolveParameterValue` verileri alır `T4ParameterValues` MSBuild kullandığınızda. Visual Studio kullanarak şablon dönüştürdüğünüzde, parametrelerin varsayılan değerleri olacaktır.

##  <a name="msbuild"></a> Derlemede Proje Özellikleri'ni kullanın ve yönergeleri içerir

Visual Studio makrosu $(SolutionDir) gibi Msbuild'de çalışmıyor. Bunun yerine, proje özelliklerini kullanabilirsiniz.

Proje özelliği tanımlamak için .csproj veya .vbproj dosyanızı düzenleyin. Bu örnek adlı bir özelliğini tanımlar `myLibFolder`:

```xml
<!-- Define a project property, myLibFolder: -->
<PropertyGroup>
    <myLibFolder>$(MSBuildProjectDirectory)\..\libs</myLibFolder>
</PropertyGroup>

<!-- Tell the MSBuild T4 task to make the property available: -->
<ItemGroup>
    <T4ParameterValues Include="myLibFolder">
      <Value>$(myLibFolder)</Value>
    </T4ParameterValues>
  </ItemGroup>
```

Artık derlemede ve ekleme yönergelerinde proje özelliklerini kullanabilirsiniz:

```
<#@ assembly name="$(myLibFolder)\MyLib.dll" #>
<#@ include file="$(myLibFolder)\MyIncludeFile.t4" #>
```

 Bu yönergeler, hem MSBuild içinde hem de Visual Studio ana bilgisayarlarında T4parameterValues değerlerini alır.

## <a name="q--a"></a>Soru - Yanıt

 **Yapı sunucunun şablonlarında dönüştürmek neden istiyor? Kodumda iade önce ı zaten Visual Studio şablonları dönüştürüldüğünde.**

 Eklenen bir dosya veya başka bir dosya şablon tarafından okuma güncelleştirirseniz, Visual Studio otomatik olarak dönüşüm dosyası değil. Yapı parçası emin getirir şablonları dönüştürme bu her şeyi güncel olduğundan.

 **Diğer seçenekleri var. metin şablonları dönüştürme için nelerdir?**

-   [TextTransform yardımcı programı](../modeling/generating-files-with-the-texttransform-utility.md) komut içinde kullanılabilir. Çoğu durumda, MSBuild kullanmak daha kolay olur.

-   [Bir VS Uzantısında Metin Dönüştürmeyi Çağırma](../modeling/invoking-text-transformation-in-a-vs-extension.md)

-   [Tasarım zamanı metin şablonları](../modeling/design-time-code-generation-by-using-t4-text-templates.md) Visual Studio tarafından dönüştürülür.

-   [Çalıştırma zamanı metin şablonları](../modeling/run-time-text-generation-with-t4-text-templates.md) uygulamanızda çalışma zamanında dönüştürülür.

## <a name="see-also"></a>Ayrıca bkz.

- T4 MSbuild şablonundaki rehber oldukça kullanışlıdır: $(VSToolsPath)\TextTemplating\Microsoft.TextTemplating.targets
- [T4 Metin Şablonu Yazma](../modeling/writing-a-t4-text-template.md)
- [Oleg Sych: T4:MSBuild tümleştirme anlama](http://www.olegsych.com/2010/04/understanding-t4-msbuild-integration/)
- [!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]