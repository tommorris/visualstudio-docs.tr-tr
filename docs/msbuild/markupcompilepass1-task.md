---
title: MarkupCompilePass1 görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- converting XAML to binary format [WPF MSBuild]
- MarkupCompilePass1 task [WPF MSBuild], parameters
- converting XAML projects to compiled binary format [WPF MSBuild]
- MarkupCompilePass1 task [WPF MSBuild], converting XAML to binary format
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0abf8f5b2c77281325853f744f54513fb897ecc6
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31574954"
---
# <a name="markupcompilepass1-task"></a>MarkupCompilePass1 Görevi

<xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> Görev dönüştürür yerelleştirilemeyen [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] proje dosyalarını derlenmiş ikili biçime.

## <a name="task-parameters"></a>Görev parametreleri

|Parametre|Açıklama|
|---------------|-----------------|
|`AllGeneratedFiles`|İsteğe bağlı **ITaskItem []** çıkış parametresi.<br /><br /> Tarafından oluşturulan dosyaların tam bir listesini içeren <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> görev.|
|`AlwaysCompileMarkupFilesInSeparateDomain`|İsteğe bağlı **Boolean** parametresi.<br /><br /> Ayrı bir görevin çalıştırılıp çalıştırılmayacağını belirtir <xref:System.AppDomain>. Bu parametre döndürürse **false**, görev aynı şekilde çalışır <xref:System.AppDomain> olarak [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)] ve daha hızlı çalışır. Parametre döndürürse **true**, ikinci bir görev çalıştırır <xref:System.AppDomain> üzerinden olan [!INCLUDE[TLA2#tla_msbuild](../msbuild/includes/tla2sharptla_msbuild_md.md)] ve daha yavaş çalışır.|
|`ApplicationMarkup`|İsteğe bağlı **ITaskItem []** parametresi.<br /><br /> Uygulama tanımı adını belirtir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosya.|
|`AssembliesGeneratedDuringBuild`|İsteğe bağlı **String []** parametresi.<br /><br /> Oluşturma işlemi sırasında değiştirmek derlemelerine başvurular belirtir. Örneğin, bir Visual Studio çözümü derlenmiş çıktısını başka bir projeye başvuruda bulunan bir proje içerebilir. Bu durumda, ikinci proje derlenmiş çıktısı eklenerek **AssembliesGeneratedDuringBuild** parametresi.<br /><br /> Not: **AssembliesGeneratedDuringBuild** parametresi, eksiksiz bir yapı çözümü tarafından oluşturulan derlemelerin başvurular içermelidir.|
|`AssemblyName`|Gerekli **dize** parametresi.<br /><br /> Proje için oluşturulan derleme kısa adını belirtir. Örneğin, bir proje oluşturuyorsa bir [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)] yürütülebilir dosyanın adı olan **WinExeAssembly.exe**, **AssemblyName** parametre değerine sahip **WinExeAssembly**.|
|`AssemblyPublicKeyToken`|İsteğe bağlı **dize** parametresi.<br /><br /> Ortak anahtar belirteci, derleme için belirtir.|
|`AssemblyVersion`|İsteğe bağlı **dize** parametresi.<br /><br /> Derlemenin sürüm numarasını belirtir.|
|`ContentFiles`|İsteğe bağlı **ITaskItem []** parametresi.<br /><br /> Gevşek içerik dosyalarının listesini belirtir.|
|`DefineConstants`|İsteğe bağlı **dize** parametresi.<br /><br /> Belirleyen geçerli değeri **DefineConstants**, tutulur. hedef derleme oluşturma etkiler; Bu parametre değiştirdiyseniz, hedef derlemesindeki genel API'si değiştirilebilir ve derlenmesini [!INCLUDE[TLA2#tla_titlexaml](../msbuild/includes/tla2sharptla_titlexaml_md.md)] yerel türleri başvuru dosyaları etkilenebilir.|
|`ExtraBuildControlFiles`|İsteğe bağlı **ITaskItem []** parametresi.<br /><br /> Bir yeniden oluşturma olup olmadığını kontrol dosyaların bir listesini belirtir zaman tetiklenir <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> görev yeniden çalıştırır; bunlardan biri değişiklikleri dosyalarının ise yeniden tetiklenir.|
|`GeneratedBamlFiles`|İsteğe bağlı **ITaskItem []** çıkış parametresi.<br /><br /> Oluşturulan dosyaların listesini içeren [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ikili biçimi.|
|`GeneratedCodeFiles`|İsteğe bağlı **ITaskItem []** çıkış parametresi.<br /><br /> Oluşturulan yönetilen kod dosyalarının listesini içerir.|
|`GeneratedLocalizationFiles`|İsteğe bağlı **ITaskItem []** çıkış parametresi.<br /><br /> Her biri için oluşturulan yerelleştirme dosyaların listesini içeren yerelleştirilebilir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosya.|
|`HostInBrowser`|İsteğe bağlı **dize** parametresi.<br /><br /> Oluşturulan derleme olup olmadığını belirten bir [!INCLUDE[TLA#tla_xbap](../msbuild/includes/tlasharptla_xbap_md.md)]. Geçerli seçenekler şunlardır: **true** ve **false**. Varsa **doğru**, kod tarayıcı barındırmasını desteklemek için oluşturulur.|
|`KnownReferencePaths`|İsteğe bağlı **String []** parametresi.<br /><br /> Oluşturma işlemi sırasında değiştirmeyin derlemelerine başvurular belirtir. Bulunan bütünleştirilmiş kodları bulunur [!INCLUDE[TLA#tla_gac](../msbuild/includes/tlasharptla_gac_md.md)], bir [!INCLUDE[TLA#tla_netframewk](../misc/includes/tlasharptla_netframewk_md.md)] yükleme dizinini ve benzeri.|
|`Language`|Gerekli **dize** parametresi.<br /><br /> Derleyici destekleyen yönetilen dilini belirtir. Geçerli seçenekler şunlardır: **C#**, **VB**, **JScript**, ve **C++**.|
|`LanguageSourceExtension`|İsteğe bağlı **dize** parametresi.<br /><br /> Oluşturulan yönetilen kod dosyasının uzantıya eklenmiş uzantısını belirtir:<br /><br /> `<Filename>.g<LanguageSourceExtension>`<br /><br /> Varsa **LanguageSourceExtension** parametresi ile belirli bir değere ayarlı değil, bir dil için varsayılan kaynak dosya adı uzantısı kullanılır: **.vb** için [!INCLUDE[TLA#tla_visualb](../msbuild/includes/tlasharptla_visualb_md.md)], **.csharp** için [!INCLUDE[TLA#tla_cshrp](../data-tools/includes/tlasharptla_cshrp_md.md)].|
|`LocalizationDirectivesToLocFile`|İsteğe bağlı **dize** parametresi.<br /><br /> Her kaynak için yerelleştirme bilgisi oluşturmak nasıl belirtir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosya. Geçerli seçenekler şunlardır: **hiçbiri**, **CommentsOnly**, ve **tüm**.|
|`OutputPath`|Gerekli **dize** parametresi.<br /><br /> Dizini içinde belirtir oluşturulan yönetilen kod dosyaları ve [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ikili biçimi dosyaları oluşturulur.|
|`OutputType`|Gerekli **dize** parametresi.<br /><br /> Project tarafından oluşturulan derleme türünü belirtir. Geçerli seçenekler şunlardır: **winexe**, **exe**, **Kitaplığı**, ve **netmodule**.|
|`PageMarkup`|İsteğe bağlı **ITaskItem []** parametresi.<br /><br /> Bir listesini belirtir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosyaları işleme.|
|`References`|İsteğe bağlı **ITaskItem []** parametresi.<br /><br /> Kullanılan türlerini içeren bir derleme dosyalarını başvurular listesini belirtir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosyaları.|
|`RequirePass2ForMainAssembly`|İsteğe bağlı **Boolean** çıkış parametresi.<br /><br /> Proje yerelleştirilemeyen içerip içermediğini gösterir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ana derlemeye katıştırılmış yerel türleri başvuru dosyaları.|
|`RequirePass2ForSatelliteAssembly`|İsteğe bağlı **Boolean** çıkış parametresi.<br /><br /> Proje yerelleştirilebilir içerip içermediğini gösterir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ana derlemede katıştırılmış yerel türleri başvuru dosyaları.|
|`RootNamespace`|İsteğe bağlı **dize** parametresi.<br /><br /> Projesi içinde olan sınıfları için kök ad alanını belirtir. **RootNamespace** oluşturulmuş bir yönetilen kod varsayılan ad alanı da kullanılan dosyası karşılık gelen [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosya içermez `x:Class` özniteliği.|
|`SourceCodeFiles`|İsteğe bağlı **ITaskItem []** parametresi.<br /><br /> Geçerli projenin kod dosyaları listesini belirtir. Listenin oluşturulan dile özgü yönetilen kod dosyaları içermez.|
|`UICulture`|İsteğe bağlı **dize** parametresi.<br /><br /> UI kültürü için uydu derlemesi içinde belirten oluşturulan [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] gömülü ikili biçimi dosyalar. Varsa **UICulture** ayarlı değil, oluşturulan [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ikili biçimi dosyaları ana derlemede katıştırılmış.|
|`XAMLDebuggingInformation`|İsteğe bağlı **Boolean** parametresi.<br /><br /> Zaman **true**, tanılama bilgilerini oluşturulur ve derlenmiş dahil [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] hata ayıklama yardımcı olmak için.|

## <a name="remarks"></a>Açıklamalar

<xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> Görev genellikle derler [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ikili biçime ve kod dosyaları oluşturur. Varsa bir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosyayı aynı projesinde tanımlanan tür başvuruları içeren, kendi derleme ikili biçime tarafından ertelenmiş **MarkupCompilePass1** ikinci bir işaretleme derleme geçişine ( **MarkupCompilePass2**). Bu tür dosyaları başvurulan yerel olarak tanımlı türler derlenmiş kadar beklemeniz gerekir çünkü ertelenmiş kendi derleme olması gerekir. Ancak, bir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosya sahip bir `x:Class` özniteliği <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass1> için dile özgü kod dosyası oluşturur.

A [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosyasıdır kullanmak öğeler içeriyorsa, yerelleştirilebilir `x:Uid` özniteliği:

```xml
<Page x:Class="WPFMSBuildSample.Page1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Uid="Page1Uid"
    >
  ...
</Page>
```

A [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosyaya başvuruda bulunan yerel olarak tanımlanan bir türü, bildirir, bir [!INCLUDE[TLA#tla_xml](../msbuild/includes/tlasharptla_xml_md.md)] kullanan ad alanı `clr-namespace` bir ad alanı geçerli projedeki başvurmak için değer:

```xml
<Page x:Class="WPFMSBuildSample.Page1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:localNamespace="clr-namespace:WPFMSBuildSample"
    >
    <Grid>
      <Grid.Resources>
        <localNameSpace:LocalType x:Key="localType" />
      </Grid.Resources>
      ...
    </Grid>
</Page>
```

Varsa [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosya yerelleştirilebilir veya yerel olarak tanımlanan bir türü başvuruyor, ikinci bir biçimlendirme derleme geçişi gereklidir çalışmasını gerektiren [GenerateTemporaryTargetAssembly](../msbuild/generatetemporarytargetassembly-task.md) ve ardından [ MarkupCompilePass2](../msbuild/markupcompilepass2-task.md).

## <a name="example"></a>Örnek

Aşağıdaki örnekte, üç dönüştürmek gösterilmiştir `Page` [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ikili biçimi dosyaları dosyaları. `Page1` bir tür için bir başvuru içeriyor `Class1`, projenin kök ad alanı ve bu nedenle, bu biçimlendirme derleme geçişi ikili biçimi dosyalarında dönüştürülmedi. Bunun yerine, [GenerateTemporaryTargetAssembly](../msbuild/generatetemporarytargetassembly-task.md) yürütülür ve tarafından izlenen [MarkupCompilePass2](../msbuild/markupcompilepass2-task.md).

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <UsingTask 
    TaskName="Microsoft.Build.Tasks.Windows.MarkupCompilePass1" 
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />
  <Target Name="MarkupCompilePass1Task">
    <MarkupCompilePass1 
      AssemblyName="WPFMSBuildSample"
      Language="C#"
      OutputType="WinExe"
      OutputPath="obj\Debug\"
      ApplicationMarkup="App.xaml"
      PageMarkup="Page1.xaml;Page2.xaml;Page3.xaml"
      SourceCodeFiles="Class1.cs"
      References="c:\windows\Microsoft.net\Framework\v2.0.50727\System.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationCore.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationFramework.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\WindowsBase.dll" />
  </Target>
</Project>
```

## <a name="see-also"></a>Ayrıca Bkz.

[WPF MSBuild Başvurusu](../msbuild/wpf-msbuild-reference.md)  
[Görev başvurusu](../msbuild/wpf-msbuild-task-reference.md)  
[MSBuild Başvurusu](../msbuild/msbuild-reference.md)  
[Görev başvurusu](../msbuild/msbuild-task-reference.md)  
[WPF uygulaması (WPF) oluşturma](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)  
[WPF XAML Tarayıcı Uygulamalarına Genel Bakış](/dotnet/framework/wpf/app-development/wpf-xaml-browser-applications-overview)