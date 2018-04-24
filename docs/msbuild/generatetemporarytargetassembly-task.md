---
title: GenerateTemporaryTargetAssembly görevi | Microsoft Docs
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
- build process [WPF MSBuild], XAML page refers to a locally declared type
- GenerateTemporaryTargetAssembly task [WPF MSBuild]
- GenerateTemporaryTargetAssembly task [WPF MSBuild], parameters
- creating an assembly [WPF MSBuild], XAML page refers to a locally declared type
ms.assetid: 92b6539c-6897-45e0-8989-0c234bbfe782
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: efaeed873630113382630421258338e6624e14ee
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="generatetemporarytargetassembly-task"></a>GenerateTemporaryTargetAssembly Görevi
<xref:Microsoft.Build.Tasks.Windows.GenerateTemporaryTargetAssembly> Görev oluşturursa bütünleştirilmiş en az bir [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] projesinde sayfasına başvuruda bu projede yerel olarak bildirilen bir türü. Oluşturulan derleme oluşturma işlemi tamamlandıktan sonra ya da oluşturma işlemi başarısız olursa kaldırılır.  
  
## <a name="task-parameters"></a>Görev parametreleri  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AssemblyName`|Gerekli **dize** parametresi.<br /><br /> Proje için oluşturulur ve ayrıca geçici olarak oluşturulan hedef derlemenin adını derleme kısa adını belirtir. Örneğin bir proje oluşturur, bir [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)] yürütülebilir dosyanın adı olan **WinExeAssembly.exe**, **AssemblyName** parametre değerine sahip **WinExeAssembly**.|  
|`CompileTargetName`|Gerekli **dize** parametresi.<br /><br /> Adını belirtir. [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)] derlemeler kaynak kodu dosyaları oluşturmak için kullanılan hedef. İçin tipik bir değer **CompileTargetName** olan **CoreCompile**.|  
|`CompileTypeName`|Gerekli **dize** parametresi.<br /><br /> Tarafından belirtilen hedef tarafından gerçekleştirilen derleme türünü belirtir. **CompileTargetName** parametresi. İçin **CoreCompile** hedefidir, bu değer **derleme**.|  
|`CurrentProject`|Gerekli **dize** parametresi.<br /><br /> Tam yolunu belirtir [!INCLUDE[TLA2#tla_msbuild](../msbuild/includes/tla2sharptla_msbuild_md.md)] geçici hedef derleme gerektiren projesi için proje dosyası.|  
|`GeneratedCodeFiles`|İsteğe bağlı **ITaskItem []** parametresi.<br /><br /> Tarafından oluşturulan dile özgü yönetilen kod dosyaların listesini belirtir [MarkupCompilePass1](../msbuild/markupcompilepass1-task.md) görev.|  
|`IntermediateOutputPath`|Gerekli **dize** parametresi.<br /><br /> Geçici hedef derlemesi için oluşturulan dizini belirtir.|  
|`MSBuildBinPath`|Gerekli **dize** parametresi.<br /><br /> Konumunu belirten **MSBuild.exe**, geçici hedef derlemeyi derlemek için gereklidir.|  
|`ReferencePath`|İsteğe bağlı **ITaskItem []** parametresi.<br /><br /> Derlemeler, listesini geçici hedef bütünleştirilmiş koda derlenmiş türleri tarafından başvurulan yolu ve dosya adını belirtir.|  
|`ReferencePathTypeName`|Gerekli **dize** parametresi.<br /><br /> Derleme hedefi tarafından kullanılan parametre belirtir (**CompileTargetName**) derleme başvurularını listesi belirten parametre (**ReferencePath**). Uygun değer **ReferencePath**.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tarafından çalıştırılan ilk biçimlendirmesi derleme geçişi [MarkupCompilePass1](../msbuild/markupcompilepass1-task.md), derler [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosyaları ikili biçimi. Bu nedenle, derleyici tarafından kullanılan türlerini içeren başvurulan bir derleme listesi gerekir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosyaları. Ancak, bir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dosyasını kullanır aynı proje tanımlanan bir türü, proje oluşturulana kadar bu proje için karşılık gelen bir derleme oluşturulmaz. Bu nedenle, bir derleme başvurusu ilk biçimlendirmesi derleme geçişi sırasında sağlanamaz.  
  
 Bunun yerine, **MarkupCompilePass1** dönüştürülmesi erteler [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] türlerine ikinci biçimlendirme derleme aynı projede başvuruları içeren dosyaları geçirmek, tarafından yürütüldüğü [MarkupCompilePass2](../msbuild/markupcompilepass2-task.md). Önce **MarkupCompilePass2** olan yürütülen, geçici bir derleme oluşturulur. Bu derleme tarafından kullanılan türler içerir [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] , biçimlendirme derleme geçişi ertelenmiş dosyaları. Oluşturulan derlemesine başvuru için sağlanan **MarkupCompilePass2** ertelenmiş derleme izin vermek için çalıştığında [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] ikili biçimine dönüştürülecek dosyaları.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çünkü geçici bir derleme oluşturur `Page1.xaml` aynı projede türüne bir başvuru içeriyor.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask  
    TaskName="Microsoft.Build.Tasks.Windows.GenerateTemporaryTargetAssembly"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="GenerateTemporaryTargetAssemblyTask">  
    <GenerateTemporaryTargetAssembly  
      AssemblyName="WPFMSBuildSample"  
      CompileTargetName="CoreCompile"  
      CompileTypeName="Compile"  
      CurrentProject="FullBuild.proj"  
      GeneratedCodeFiles="obj\debug\app.g.cs;obj\debug\Page1.g.cs;obj\debug\Page2.g.cs"  
      ReferencePath="c:\windows\Microsoft.net\Framework\v2.0.50727\System.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationCore.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationFramework.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\WindowsBase.dll"  
      IntermediateOutputPath=".\obj\debug\"  
      MSBuildBinPath="$(MSBuildBinPath)"  
      ReferencePathTypeName="ReferencePath"/>  
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