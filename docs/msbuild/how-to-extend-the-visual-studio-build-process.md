---
title: "Nasıl yapılır: Visual Studio derleme işlemini genişletme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, overriding predefined targets
- MSBuild, overriding DependsOn properties
- MSBuild, extending Visual Studio builds
- MSBuild, DependsOn properties
ms.assetid: cb077613-4a59-41b7-96ec-d8516689163c
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 8e9605bff5726de107019c9204c76e6e82b8d9f1
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-extend-the-visual-studio-build-process"></a>Nasıl Yapılır: Visual Studio Derleme İşlemini Genişletme
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Derleme süreci tarafından bir dizi tanımlanmış [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyanıza içe aktarılan .targets dosyaları. Microsoft.Common.targets, içeri aktarılan bu dosyalardan birini oluşturma işlemi birkaç noktalarında özel görevleri çalıştırmak izin vermek için genişletilebilir. Bu konuda genişletmek için kullanabileceğiniz iki yöntem açıklanmaktadır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] derleme işlemi:  
  
-   Microsoft.Common.targets içinde tanımlanan belirli önceden tanımlanmış hedefleri geçersiz kılma.  
  
-   Microsoft.Common.targets içinde tanımlanan "DependsOn" özelliklerini geçersiz kılma.  
  
## <a name="overriding-predefined-targets"></a>Önceden tanımlanmış hedefleri geçersiz kılma  
 Microsoft.Common.targets dosya önce ve sonra derleme sürecindeki ana hedefleri bazıları adlı önceden tanımlanmış boş hedefleri kümesini içerir. Örneğin, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] çağrıları `BeforeBuild` ana önce hedef `CoreBuild` hedef ve `AfterBuild` sonra hedef `CoreBuild` hedef. Varsayılan olarak, Microsoft.Common.targets boş hedeflerini hiçbir şey yapma, ancak Microsoft.Common.targets içe aktaran bir proje dosyasında istediğiniz hedefler tanımlayarak kendi varsayılan davranışı geçersiz kılabilirsiniz. Bunu yaparak, kullanabilirsiniz [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] yapı işlemi üzerinde daha fazla denetime görevler.  
  
#### <a name="to-override-a-predefined-target"></a>Önceden tanımlanmış bir hedef geçersiz kılmak için  
  
1.  Önceden tanımlanmış bir hedef geçersiz kılmak istediğiniz Microsoft.Common.targets olarak belirleyin. Güvenli bir şekilde kılabilirsiniz hedefleri tam listesi için aşağıdaki tabloya bakın.  
  
2.  Hemen önce hedef veya proje dosyanızı sonunda hedefleri tanımlayın `</Project>` etiketi. Örneğin:  
  
    ```xml  
    <Project>  
        ...  
        <Target Name="BeforeBuild">  
            <!-- Insert tasks to run before build here -->  
        </Target>  
        <Target Name="AfterBuild">  
            <!-- Insert tasks to run after build here -->  
        </Target>  
    </Project>  
    ```  
  
3.  Proje dosyası oluşturun.  
  
 Aşağıdaki tabloda tüm hedefleri güvenle kılabilirsiniz Microsoft.Common.targets içinde gösterir.  
  
|Hedef Adı|Açıklama|  
|-----------------|-----------------|  
|`BeforeCompile`, `AfterCompile`|Bu hedeflerde birinde eklenen görevler önce veya çekirdek derleme yapıldıktan sonra çalışır. Çoğu özelleştirmeleri iki bu hedeflerde birinde yapılır.|  
|`BeforeBuild`, `AfterBuild`|Bu hedeflerde birinde eklenen görevler önce veya sonra yapı bir şey çalışır. **Not:** `BeforeBuild` ve `AfterBuild` hedefleri çoğu proje dosyalarını sonunda açıklamalarında zaten tanımlanır. Bu proje dosyanızı öncesi ve sonrası yapı olayları kolayca eklemenize olanak sağlar.|  
|`BeforeRebuild`, `AfterRebuild`|Görevleri daha önce çalıştırılması bu hedeflerde birinde eklenebilir veya çekirdek yeniden oluşturduktan sonra işlevi çağrılır. Microsoft.Common.targets hedef yürütme sırası: `BeforeRebuild`, `Clean`, `Build`ve ardından `AfterRebuild`.|  
|`BeforeClean`, `AfterClean`|Önce bu hedeflerde birinde eklenen görevleri çalıştırmak veya çekirdek sonra temiz işlevi çağrılır.|  
|`BeforePublish`, `AfterPublish`|Görevleri daha önce çalıştırılması bu hedeflerde birinde eklenebilir veya çekirdek yayımladıktan sonra işlevi çağrılır.|  
|`BeforeResolveReference`, `AfterResolveReferences`|Önce ya da derleme başvurularını çözüldükten sonra bu hedeflerde birinde eklenen görevlerini çalıştırın.|  
|`BeforeResGen`, `AfterResGen`|Bu hedeflerde birinde eklenen görevler önce veya kaynakları oluşturulduktan sonra çalışır.|  
  
## <a name="overriding-dependson-properties"></a>"DependsOn" özelliklerini geçersiz kılma  
 Önceden tanımlanmış hedefleri geçersiz kılma derleme işlemini genişletme için kolay bir yolu olmadığını ancak, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] hedefleri tanımını ardışık olarak değerlendirilir projenizin hedefleri geçersiz kılma alır başka bir projeye önlemek için bir yolu yoktur önceden geçersiz. Bunu, örneğin, son `AfterBuild` diğer tüm projeleri içeri aktarıldığını, derleme sırasında kullanılan bir olacaktır sonra proje dosyasında tanımlanmış hedefi.  
  
 Kullanılan "DependsOn" özelliklerini geçersiz kılma hedefleri istenmeyen geçersiz kılmaları karşı önleyebilirsiniz `DependsOnTargets` Microsoft.Common.targets dosya boyunca öznitelikleri. Örneğin, `Build` hedef içeren bir `DependsOnTargets` öznitelik değerini `"$(BuildDependsOn)"`. Göz önünde bulundurun:  
  
```xml  
<Target Name="Build" DependsOnTargets="$(BuildDependsOn)"/>  
```  
  
 Bu XML parçası önce belirten `Build` hedef çalıştırabilir, tüm hedefleri belirtilen `BuildDependsOn` özelliği ilk çalıştırmalısınız. `BuildDependsOn` Özelliği olarak tanımlanır:  
  
```xml  
<PropertyGroup>  
    <BuildDependsOn>  
        BeforeBuild;  
        CoreBuild;  
        AfterBuild  
    </BuildDependsOn>  
</PropertyGroup>  
```  
  
 Adlı başka bir özellik bildirerek bu özellik değeri geçersiz kılabilirsiniz `BuildDependsOn` proje dosyanızı sonunda. Önceki ekleyerek `BuildDependsOn` özelliği yeni özelliğinde yeni hedefler başında ve hedef listesinin sonuna ekleyebilirsiniz. Örneğin:  
  
```xml  
<PropertyGroup>  
    <BuildDependsOn>  
        MyCustomTarget1;  
        $(BuildDependsOn);  
        MyCustomTarget2  
    </BuildDependsOn>  
</PropertyGroup>  
  
<Target Name="MyCustomTarget1">  
    <Message Text="Running MyCustomTarget1..."/>  
</Target>  
<Target Name="MyCustomTarget2">  
    <Message Text="Running MyCustomTarget2..."/>  
</Target>  
```  
  
 Proje dosyalarınızı alma projeler yaptığınız özelleştirmeleri yazmadan bu özellikleri geçersiz kılabilirsiniz.  
  
#### <a name="to-override-a-dependson-property"></a>"DependsOn" özelliği geçersiz kılmak için  
  
1.  Önceden tanımlanmış bir "DependsOn" özelliği, geçersiz kılmak istediğiniz Microsoft.Common.targets olarak belirleyin. Yaygın olarak geçersiz kılınan "DependsOn" özelliklerinin bir listesi için aşağıdaki tabloya bakın.  
  
2.  Özellik veya özellikleri proje dosyanızı sonunda başka bir örneğini tanımlar. Örneğin özgün özelliği dahil `$(BuildDependsOn)`, yeni özelliğinde.  
  
3.  Önce veya sonra özellik tanımını özel hedeflerinizi tanımlayın.  
  
4.  Proje dosyası oluşturun.  
  
### <a name="commonly-overridden-dependson-properties"></a>Yaygın olarak geçersiz kılınan "DependsOn" özellikleri  
  
|Özellik adı|Açıklama|  
|-------------------|-----------------|  
|`BuildDependsOn`|Önce veya sonra tüm derleme işlemi özel hedefleri eklemek istiyorsanız, geçersiz kılmak için özellik.|  
|`CleanDependsOn`|Derleme işlemi özel çıktısını temizleme istiyorsanız, geçersiz kılmak için özellik.|  
|`CompileDependsOn`|Özel işlemler önce veya sonra derleme adımı eklemek istiyorsanız, geçersiz kılmak için özellik.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Integration](../msbuild/visual-studio-integration-msbuild.md)   
 [MSBuild kavramları](../msbuild/msbuild-concepts.md)   
 [. Hedef dosyaları](../msbuild/msbuild-dot-targets-files.md)