---
title: "MarkupCompilePass2 görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- performing second-pass markup [WPF MSBuild], MarkupCompilePass2 task
- MarkupCompilePass2 task [WPF MSBuild]
- MarkupCompilePass2 task [WPF MSBuild], parameters
ms.assetid: 1d25689a-d21f-4b05-be26-95aa0ed4fd03
caps.latest.revision: "7"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4c7e9b43436787896699fa2275a13500f751b574
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="markupcompilepass2-task"></a>MarkupCompilePass2 Görevi
<xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass2> Görevi gerçekleştirir ikinci geçiş biçimlendirmesi derleme [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] türleri aynı projede başvuru dosyaları.  
  
## <a name="task-parameters"></a>Görev parametreleri  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AlwaysCompileMarkupFilesInSeparateDomain`|İsteğe bağlı **Boolean** parametresi.<br /><br /> Ayrı bir görevin çalıştırılıp çalıştırılmayacağını belirtir <xref:System.AppDomain>. Bu parametre döndürürse **false**, görev aynı şekilde çalışır <xref:System.AppDomain> olarak [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)], ve daha hızlı çalışır. Parametre döndürürse **true**, ikinci bir görev çalıştırır <xref:System.AppDomain> üzerinden olan [!INCLUDE[TLA2#tla_msbuild](../msbuild/includes/tla2sharptla_msbuild_md.md)] ve daha yavaş çalışır.|  
|`AssembliesGeneratedDuringBuild`|İsteğe bağlı **String []** parametresi.<br /><br /> Oluşturma işlemi sırasında değiştirmek derlemelerine başvurular belirtir. Örneğin, bir [!INCLUDE[TLA#tla_visualstu2005](../msbuild/includes/tlasharptla_visualstu2005_md.md)] çözüm derlenmiş çıktısını başka bir projeye başvuruda bulunan bir proje içerebilir. Bu durumda, ikinci proje derlenmiş çıktısı eklenerek **AssembliesGeneratedDuringBuild**.<br /><br /> Not: **AssembliesGeneratedDuringBuild** eksiksiz bir yapı çözümü tarafından oluşturulan derlemelerin başvurular içermelidir.|  
|`AssemblyName`|Gerekli **dize** parametresi.<br /><br /> Proje için oluşturulan derleme kısa adını belirtir. Örneğin, bir proje oluşturuyorsa bir [!INCLUDE[TLA#tla_win](../msbuild/includes/tlasharptla_win_md.md)] yürütülebilir dosyanın adı olan **WinExeAssembly.exe**, **AssemblyName** parametre değerine sahip **WinExeAssembly**.|  
|`GeneratedBaml`|İsteğe bağlı **ITaskItem []** çıkış parametresi.<br /><br /> Oluşturulan dosyaların listesini içeren [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ikili biçimi.|  
|`KnownReferencePaths`|İsteğe bağlı **String []** parametresi.<br /><br /> Asla oluşturma işlemi sırasında değişmesi derlemelerine başvurular belirtir. Bulunan bütünleştirilmiş kodları bulunur [!INCLUDE[TLA#tla_gac](../msbuild/includes/tlasharptla_gac_md.md)], bir [!INCLUDE[TLA#tla_netframewk](../misc/includes/tlasharptla_netframewk_md.md)] yükleme dizinini ve benzeri.|  
|`Language`|Gerekli **dize** parametresi.<br /><br /> Derleyici destekleyen yönetilen dilini belirtir. Geçerli seçenekler şunlardır: **C#**, **VB**, **JScript**, ve **C++**.|  
|`LocalizationDirectivesToLocFile`|İsteğe bağlı **dize** parametresi.<br /><br /> Her kaynak için yerelleştirme bilgisi oluşturmak nasıl belirtir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosya. Geçerli seçenekler şunlardır: **hiçbiri**, **CommentsOnly**, ve **tüm**.|  
|`OutputPath`|Gerekli **dize** parametresi.<br /><br /> Dizini içinde belirtir oluşturulan [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ikili biçimi dosyaları oluşturulur.|  
|`OutputType`|Gerekli **dize** parametresi.<br /><br /> Project tarafından oluşturulan derleme türünü belirtir. Geçerli seçenekler şunlardır: **winexe**, **exe**, **Kitaplığı**, ve **netmodule**.|  
|`References`|İsteğe bağlı **ITaskItem []** parametresi.<br /><br /> Kullanılan türlerini içeren bir derleme dosyalarını başvurular listesini belirtir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosyaları. Bir başvuru: tarafından üretildi. derleme <xref:Microsoft.Build.Tasks.Windows.GenerateTemporaryTargetAssembly> önce çalıştırılması gereken görev <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass2> görev.|  
|`RootNamespace`|İsteğe bağlı **dize** parametresi.<br /><br /> Projesi içinde olan sınıfları için kök ad alanını belirtir. **RootNamespace** oluşturulmuş bir yönetilen kod varsayılan ad alanı da kullanılan dosyası karşılık gelen [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosya içermez `x:Class` özniteliği.|  
|`XAMLDebuggingInformation`|İsteğe bağlı **Boolean** parametresi.<br /><br /> Zaman **true**, tanılama bilgilerini oluşturulur ve derlenmiş dahil [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] hata ayıklama yardımcı olmak için.|  
  
## <a name="remarks"></a>Açıklamalar  
 Çalıştırmadan önce **MarkupCompilePass2**, tarafından kullanılan türleri içeren geçici bir derleme Oluştur [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] , biçimlendirme derleme geçişi ertelenmiş dosyaları. Çalıştırarak geçici derleme oluşturmak **GenerateTemporaryTargetAssembly** görev.  
  
 Oluşturulan geçici derlemesine başvuru için sağlanan <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass2> çalıştığında, izin verme [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] , derleme ilk biçimlendirme derlemede ertelenmiş dosyaları ikili biçime şimdi derlenmesi geçer.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass2> saniyenin gerçekleştirmek için görev derleme geçirin.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.MarkupCompilePass2"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="MarkupCompilePass2Task">  
    <MarkupCompilePass2   
      AssemblyName="WPFMSBuildSample"  
      Language="C#"  
      OutputType="WinExe"  
      OutputPath="obj\Debug\"  
      References=".\obj\debug\WPFMSBuildSample.exe;c:\windows\Microsoft.net\Framework\v2.0.50727\System.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationCore.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationFramework.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\WindowsBase.dll" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WPF MSBuild başvurusu](../msbuild/wpf-msbuild-reference.md)   
 [Görev başvurusu](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [WPF uygulaması (WPF) oluşturma](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)   
 [WPF XAML Tarayıcı Uygulamalarına Genel Bakış](/dotnet/framework/wpf/app-development/wpf-xaml-browser-applications-overview)