---
title: MSBuild ayrılmış ve tanınmış Özellikler | Microsoft Docs
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
- MSBuild, reserved properties
ms.assetid: 99333e61-83c9-4804-84e3-eda297c2478d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 682eba70f3e9182464487a5a08d37c68203259e6
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36302996"
---
# <a name="msbuild-reserved-and-well-known-properties"></a>MSBuild Ayrılmış ve Tanınmış Özellikleri
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Proje dosyası hakkındaki bilgileri depolamak önceden tanımlanmış özellikler kümesi sağlar ve [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] ikili dosyaları. Bu özellikler, diğer aynı şekilde değerlendirilir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] özellikleri. Örneğin, kullanılacak `MSBuildProjectFile` özelliği, yazdığınız `$(MSBuildProjectFile)`.  
  
 MSBuild ayrılmış ve tanınmış özellikleri önceden tanımlamayı aşağıdaki tabloda değerleri kullanır. Ayrılmış özellikler kılınamaz ancak tanınmış özellikler proje dosyasında aynı adlı ortam özellikleri, genel özellikleri veya bildirilir özellikleri kullanılarak geçersiz kılınabilir.
  
## <a name="reserved-and-well-known-properties"></a>Ayrılmış ve Tanınmış Özellikler  
 Aşağıdaki tabloda açıklanmaktadır [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] özellikleri önceden tanımlanmış.  
  
|Özellik|Ayrılmış veya Well-Known|Açıklama|
|--------------|-----------------|-----------------------------|  
|`MSBuildBinPath`|Ayrılmış|Klasör mutlak yolu burada [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] şu anda kullanılmakta olan ikili dosyalarının bulunduğu (örneğin, C:\Windows\Microsoft.Net\Framework\\*versionNumber*). Bu özellik dosyalarına başvurmanız gerekirse yararlıdır [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] dizin.<br /><br /> Bu özellik üzerinde son ters eğik çizgi eklemeyin.|  
|`MSBuildExtensionsPath`|İyi bilinen|.NET Framework 4'te tanıtılan: varsayılan değerleri arasında fark yoktur `MSBuildExtensionsPath` ve `MSBuildExtensionsPath32`. Ortam değişkeni ayarlayabilirsiniz `MSBUILDLEGACYEXTENSIONSPATH` varsayılan değerini davranışı etkinleştirmek için bir null olmayan değere `MSBuildExtensionsPath` eski sürümlerinde.<br /><br /> .NET Framework 3.5 ve önceki sürümlerde varsayılan değerini `MSBuildExtensionsPath` \Program Files\ veya \Program dosyaları (x86) klasörü altında geçerli işlem verileri bağlı olarak MSBuild alt yolunu işaret eder. Örneğin, bir 64-bit makine üzerindeki 32-bit işlem için bu özelliği \Program Files (x86) klasörüne işaret ediyor. Bir 64-bit makine üzerindeki 64-bit işlem için bu özelliği \Program Files klasörüne işaret ediyor.<br /><br /> Bu özellik üzerinde son ters eğik çizgi eklemeyin.<br /><br /> Bu konum, özel hedef dosyaları yerleştirmek için kullanışlı bir yerdir. Örneğin, hedef dosyalarınızı \Program Files\MSBuild\MyFiles\Northwind.targets yüklenebilir ve daha sonra bu XML kodunu kullanarak proje dosyalarında alınan:<br /><br /> `<Import Project="$(MSBuildExtensionsPath)\MyFiles\Northwind.targets"/>`|  
|`MSBuildExtensionsPath32`|İyi bilinen|Yolunu [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] \Program Files veya \Program Files (x86) klasörü altında alt. Bu yolu her zaman bir 32-bit makine ve \Program 32-bit \Program Files klasöründeki bir 64-bit makine (x86) dosyalarda işaret eder. Ayrıca bkz. `MSBuildExtensionsPath` ve `MSBuildExtensionsPath64`.<br /><br /> Bu özellik üzerinde son ters eğik çizgi eklemeyin.|  
`MSBuildExtensionsPath64`|İyi bilinen|Yolunu [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] \Program Files klasöründeki altında alt. Bir 64-bit makine için bu yolu her zaman \Program Files klasörüne işaret ediyor. 32-bit makine için bu yol boştur. Ayrıca bkz. `MSBuildExtensionsPath` ve `MSBuildExtensionsPath32`.<br /><br /> Bu özellik üzerinde son ters eğik çizgi eklemeyin.|  
|`MSBuildLastTaskResult`|Ayrılmış|`true` herhangi bir hata olmadan (uyarıları olsaydı bile), önceki görev tamamlandı varsa veya `false` önceki görev hatalar varsa. Bir görevde bir hata ortaya çıkarsa, genellikle, hata bu projede gerçekleşen son şeydir. Bu nedenle, bu özellik hiçbir zaman değeri `false`, bu senaryolarda dışındaki:<br /><br /> -Zaman `ContinueOnError` özniteliği [görev öğesi (MSBuild)](../msbuild/task-element-msbuild.md) ayarlanır `WarnAndContinue` (veya `true`) veya `ErrorAndContinue`.<br /><br /> -Zaman `Target` sahip bir [OnError öğesi (MSBuild)](../msbuild/onerror-element-msbuild.md) bir alt öğesi olarak.|  
|`MSBuildNodeCount`|Ayrılmış|En yüksek oluştururken kullanılan eşzamanlı işlem sayısı. İçin belirtilen değer budur **/maxcpucount** komut satırında. Belirttiyseniz **/maxcpucount** sonra bir değer belirtmeden `MSBuildNodeCount` bilgisayar işlemci sayısını belirtir. Daha fazla bilgi için bkz: [komut satırı başvurusu](../msbuild/msbuild-command-line-reference.md) ve [yapı paralel olarak birden çok proje](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md).|  
|`MSBuildProgramFiles32`|Ayrılmış|32-bit program klasörünün konumunu; Örneğin, `C:\Program Files (x86)`.<br /><br /> Bu özellik üzerinde son ters eğik çizgi eklemeyin.|  
|`MSBuildProjectDefaultTargets`|Ayrılmış|Belirtilen hedefleri tam listesi `DefaultTargets` özniteliği `Project` öğesi. Örneğin, aşağıdaki `Project` öğesi sahip olabilir bir `MSBuildDefaultTargets` özellik değerinin `A;B;C`:<br /><br /> `<Project DefaultTargets="A;B;C" >`|  
|`MSBuildProjectDirectory`|Ayrılmış|Proje dosyası bulunduğu, örneğin dizininin mutlak yolu `C:\MyCompany\MyProduct`.<br /><br /> Bu özellik üzerinde son ters eğik çizgi eklemeyin.|  
|`MSBuildProjectDirectoryNoRoot`|Ayrılmış|Değeri `MSBuildProjectDirectory` kök sürücüsünde hariç özelliği.<br /><br /> Bu özellik üzerinde son ters eğik çizgi eklemeyin.|  
|`MSBuildProjectExtension`|Ayrılmış|Nokta ile birlikte proje dosyasının dosya adı uzantısı; Örneğin, .proj.|  
|`MSBuildProjectFile`|Ayrılmış|Proje dosyasının dosya adı uzantısı dahil tam dosya adı; Örneğin, MyApp.proj.|  
|`MSBuildProjectFullPath`|Ayrılmış|Mutlak yolu ve dosya adı uzantısı dahil olmak üzere proje dosyasının tam dosya adı; Örneğin, C:\MyCompany\MyProduct\MyApp.proj.|  
|`MSBuildProjectName`|Ayrılmış|Dosya adı uzantısı olmadan proje dosyasının dosya adı; Örneğin, Uygulamam.|  
|`MSBuildRuntimeType`|Ayrılmış|Şu anda yürütülmekte çalışma zamanı türü. MSBuild 15 kullanıma sunuldu. Değer (MSBuild 15) önce tanımlanmamış `Full` MSBuild Masaüstü .NET Framework üzerinde çalıştırılan belirten `Core` MSBuild .NET Core üzerinde çalıştırılan belirten veya `Mono` MSBuild Mono üzerinde çalıştırılan belirten.|  
|`MSBuildStartupDirectory`|Ayrılmış|Klasör mutlak yolu burada [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] olarak adlandırılır. Bu özelliği kullanarak, belirli bir noktaya proje ağacında aşağıda her şeyi her dizinde dirs.proj dosyalar oluşturmadan oluşturabilirsiniz. Bunun yerine, yalnızca bir proje sahip — aşağıda gösterildiği gibi c:\traversal.proj Örneğin,:<br /><br /> `<Project ...>     <ItemGroup>         <ProjectFiles              Include="$            (MSBuildStartupDirectory)            **\*.csproj"/>     </ItemGroup>     <Target Name="build">         <MSBuild             Projects="@(ProjectFiles)"/>     </Target> </Project>`<br /><br /> Ağacındaki herhangi bir noktada oluşturmak için şunu yazın:<br /><br /> `msbuild c:\traversal.proj`<br /><br /> Bu özellik üzerinde son ters eğik çizgi eklemeyin.|  
|`MSBuildThisFile`|Ayrılmış|Dosya adı ve dosya uzantısı kısmı `MSBuildThisFileFullPath`.|  
|`MSBuildThisFileDirectory`|Ayrılmış|Dizin bölümü `MSBuildThisFileFullPath`.<br /><br /> Son ters eğik çizgi yolu içerir.|  
|`MSBuildThisFileDirectoryNoRoot`|Ayrılmış|Dizin bölümü `MSBuildThisFileFullPath`, kök sürücüsünde hariç.<br /><br /> Son ters eğik çizgi yolu içerir.|  
|`MSBuildThisFileExtension`|Ayrılmış|Dosya adı uzantısı kısmı `MSBuildThisFileFullPath`.|  
|`MSBuildThisFileFullPath`|Ayrılmış|Çalıştıran hedef içeren proje veya hedefleri dosyası mutlak yolu.<br /><br /> İpucu: Hedefleri dosyasıyla ilişkili ve özgün proje dosyasıyla ilişkili olmayan bir hedef dosya göreli bir yol belirtebilirsiniz.|  
|`MSBuildThisFileName`|Ayrılmış|Dosya adı kısmını `MSBuildThisFileFullPath`, dosya adı uzantısı olmadan.|  
|`MSBuildToolsPath`|Ayrılmış|Yükleme yolunun [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] değeriyle ilişkili sürüm `MSBuildToolsVersion`.<br /><br /> Son ters eğik çizgi yola dahil etmeyin.<br /><br /> Bu özellik değiştirilemiyor.|  
|`MSBuildToolsVersion`|Ayrılmış|Sürümü [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projeyi oluşturmak için kullanılır Toolset.<br /><br /> Not: Bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] araç takımı, görevler, hedefler ve bir uygulama oluşturmak için kullanılan araçlar oluşur. Csc.exe ve vbc.exe gibi derleyicileri araçları içerir. Daha fazla bilgi için bkz: [araç takımı (ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md), ve [standart ve özel araç takımı yapılandırmaları](../msbuild/standard-and-custom-toolset-configurations.md).|  

## <a name="names-that-conflict-with-msbuild-elements"></a>MSBuild öğeleri ile çakışan adları

Yukarıdakilerin yanı sıra kullanıcı tarafından tanımlanan özellikler, öğeleri veya öğe meta verileri için dil öğeleri kullanılamaz MSBuild karşılık gelen adları:

* VisualStudioProject
* Hedef
* PropertyGroup
* Çıkış
* ItemGroup
* UsingTask
* ProjectExtensions
* OnError
* Importgroup
* Bunu seçin
* ne zaman
* Aksi takdirde

## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild başvurusu](../msbuild/msbuild-reference.md) [MSBuild özellikleri](../msbuild/msbuild-properties.md)