---
title: MSBuild ile paralel olarak birden çok proje derleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- parallel project builds
- building multiple projects in parallel
- msbuild, building projects in parallel
ms.assetid: c8c9aadc-33ad-4aa1-b07d-b879e9eabda0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b904da68952cdb83c8c11094dec712861d535b73
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36302686"
---
# <a name="building-multiple-projects-in-parallel-with-msbuild"></a>MSBuild ile Paralel Olarak Birden Çok Proje Derleme
Paralel olarak çalıştırarak daha hızlı birden çok proje oluşturmak için MSBuild kullanabilirsiniz. Derlemeleri paralel olarak çalıştırmak için çok çekirdekli veya birden çok işlemci bilgisayarda aşağıdaki ayarları kullanın:  
  
-   `/maxcpucount` Geçiş komut isteminde.  
  
-   <xref:Microsoft.Build.Tasks.MSBuild.BuildInParallel%2A> MSBuild görevi görev parametresi.  
  
> [!NOTE]
>  **/Verbosity** (**/v**) komut satırı anahtarı da yapı performansı etkiler. Derleme günlüğü bilgilerinizi ayrıntı ayrıntılı olarak ayarlanırsa veya sorun giderme için kullanılan tanılama ise, yapı performansı düşebilir. Daha fazla bilgi için bkz: [yapı günlükleri alma](../msbuild/obtaining-build-logs-with-msbuild.md) ve [komut satırı başvurusu](../msbuild/msbuild-command-line-reference.md).  
  
## <a name="maxcpucount-switch"></a>/maxcpucount Anahtarı  
 Kullanırsanız `/maxcpucount` geçiş, veya `/m` kısaca, paralel olarak çalışan MSBuild.exe işlemleri belirtilen sayıda MSBuild oluşturabilirsiniz. Bu işlemler "çalışan işlemleri." olarak da bilinen olan Diğer kullanılabilir işlemci diğer projeler derleme gibi aynı anda bir projeyi derlemek kullanılabilir olan her çalışan işlemi ayrı çekirdek veya işlemci kullanır. Örneğin, bu anahtarın "4" için bir değer ayarlanması, projeyi derlemek için dört çalışan işlemler oluşturmak MSBuild neden olur.  
  
 Dahil ederseniz `/maxcpucount` MSBuild bir değer belirtmeden anahtar kullanılacağını için bilgisayar işlemci sayısı.  
  
 MSBuild 3. 5 ' sunulmuştur, bu anahtarı hakkında daha fazla bilgi için bkz: [komut satırı başvurusu](../msbuild/msbuild-command-line-reference.md).  
  
 Aşağıdaki örnekte, üç alt işlemleri kullanmak için MSBuild bildirir. Bu yapılandırma kullanırsanız, MSBuild aynı anda üç projeleri oluşturabilirsiniz.  
  
```cmd  
msbuild.exe myproj.proj /maxcpucount:3   
```  
  
## <a name="buildinparallel-task-parameter"></a>BuildInParallel Görev Parametresi  
 `BuildInParallel` İsteğe bağlı bir boolean parametre açıktır bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] görev. Zaman `BuildInParallel` ayarlanır `true` (varsayılan değeri olduğu `false`), mümkün olduğunca aynı anda sayıda projeler derlemek için birden çok alt işlemleri oluşturulur. Bunun doğru çalışması `/maxcpucount` anahtar için bir değer 1'den büyük ayarlanmalıdır ve sistem en az çift çekirdekli veya iki veya daha fazla işlemciye sahip olmanız gerekir.  
  
 Nasıl ayarlanacağı hakkında microsoft.common.targets alınan bir örnek verilmiştir `BuildInParallel` parametresi.  
  
```xml  
<PropertyGroup>  
    <BuildInParallel Condition="'$(BuildInParallel)' ==   
        ''">true</BuildInParallel>  
</PropertyGroup>  
<MSBuild  
    Projects="@(_MSBuildProjectReferenceExistent)"  
    Targets="GetTargetPath"  
    BuildInParallel="$(BuildInParallel)"  
    Properties="%(_MSBuildProjectReferenceExistent.SetConfiguration);   
        %(_MSBuildProjectReferenceExistent.SetPlatform)"  
    Condition="'@(NonVCProjectReference)'!='' and   
        ('$(BuildingSolutionFile)' == 'true' or   
        '$(BuildingInsideVisualStudio)' == 'true' or   
        '$(BuildProjectReferences)' != 'true') and     
        '@(_MSBuildProjectReferenceExistent)' != ''"  
    ContinueOnError="!$(BuildingProject)">  
    <Output TaskParameter="TargetOutputs"   
        ItemName="_ResolvedProjectReferencePaths"/>  
</MSBuild>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Projeleri derlemek için birden çok işlemci kullanma](../msbuild/using-multiple-processors-to-build-projects.md)   
 [Birden çok işlemciye duyarlı Günlükçüler yazılıyor](../msbuild/writing-multi-processor-aware-loggers.md)   
 [C++ derleme paralellik blog ayarlama](http://go.microsoft.com/fwlink/?LinkId=251457)
