---
title: MSBuild görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#MSBuild
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild task [MSBuild]
- MSBuild, MSBuild task
ms.assetid: 76577f6c-7669-44ad-a840-363e37a04d34
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 04b76df9a174bcbc03269e42ce37b1103c3bfd2f
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31575929"
---
# <a name="msbuild-task"></a>MSBuild Görevi
Derlemeler [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] başka projelerden [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projesi.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `MSBuild` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`BuildInParallel`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, belirtilen projeleri `Projects` parametresi mümkünse paralel olarak oluşturulur. Varsayılan değer `false`.|  
|`Projects`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Derleme için proje dosyalarını belirtir.|  
|`Properties`|İsteğe bağlı `String` parametresi.<br /><br /> Genel özellikleri olarak alt projeye uygulamak için özellik ad/değer çifti noktalı virgülle ayrılmış listesi. Bu parametre belirttiğinizde, onu sahip özellikler ayarını işlevsel olarak eşdeğerdir **/property** ile derlerken geçiş [MSBuild.exe](../msbuild/msbuild-command-line-reference.md). Örneğin:<br /><br /> `Properties="Configuration=Debug;Optimize=$(Optimize)"`<br /><br /> Geçirdiğiniz zaman özellikleri projeye `Properties` parametresi [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası zaten yüklenmiş olsa bile projeye yeni bir örneğini oluşturur. Proje yeni bir örneğini oluştururken [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] farklı genel özellikleri sahip ve projeye diğer örnekleri ile paralel oluşturulabilen farklı bir proje olarak değerlendirir. Örneğin, bir sürüm yapılandırmasında bir hata ayıklama yapılandırması aynı zamanda oluşturabilir.|  
|`RebaseOutputs`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, hedef göreli yollar öğeleriniz yerleşik projelerden yollarına göre arama projesi olacak şekilde ayarlanmış çıktı. Varsayılan değer `false`.|  
|`RemoveProperties`|İsteğe bağlı `String` parametresi.<br /><br /> Kaldırmak için genel özellikler kümesini belirtir.|  
|`RunEachTargetSeparately`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] görev çağırır geçirilen listesindeki her hedefi [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] bir seferde bir yerine aynı zamanda. Bu parametre ayarını `true` daha önce çağrılan hedefleri başarısız olsa bile izleyen hedefler çağrılan güvence altına alır. Aksi halde, bir derleme hatası tüm sonraki hedefleri çağrılmasını durdurur. Varsayılan değer `false`.|  
|`SkipNonexistentProjects`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, disk üzerinde var olmadığından proje dosyalarını atlanacak. Aksi takdirde, bu tür projeleri hataya neden olur.|  
|`StopOnFirstFailure`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`biri projeleri oluşturmak, başarısız olduğunda, daha fazla proje oluşturulacak. Şu anda bu paralel (ile birden çok işlemciler için) oluştururken desteklenmiyor.|  
|`TargetAndPropertyListSeparators`|İsteğe bağlı `String[]` parametresi.<br /><br /> Hedefleri ve özellik olarak listesini belirtir `Project` öğe meta verisi). Ayırıcılar önce işleme atlanmamış olacaktır. Örneğin % 3B (bir atlatmalı ';') bir atlanmamış gibi değerlendirilir ';'.|  
|`TargetOutputs`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` salt okunur çıktı parametresi.<br /><br /> Yerleşik hedefleri çıkışları tüm proje dosyalarından döndürür. Yalnızca belirtilen hedefleri çıkışlarından döndürülür, bu hedefleri bağımlı hedeflerde bulunabilir olmayan herhangi bir çıkış.<br /><br /> `TargetOutputs` Parametresi, aşağıdaki meta verileri de içerir:<br /><br /> -   `MSBuildSourceProjectFile`[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Çıkışları ayarlamak hedef içeren proje dosyası.<br />-   `MSBuildSourceTargetName`: Çıkışları ayarlayın hedef. **Not:** her proje dosyasından çıkışları tanımlamak veya ayrı olarak hedeflemek için çalıştırmak istiyorsanız, `MSBuild` her bir proje dosyası veya hedef için ayrı ayrı görev. Çalıştırırsanız `MSBuild` yalnızca tüm proje dosyalarını oluşturmak için tüm hedefleri çıkışları bir diziye toplanır sonra görev.|  
|`Targets`|İsteğe bağlı `String` parametresi.<br /><br /> Hedef veya proje dosyaları oluşturmak için hedeflerin belirtir. Hedef adlarının bir listesini ayırmak için noktalı virgül kullanın. Hiçbir hedef belirtilirse `MSBuild` görev, proje dosyasında belirtilen varsayılan hedefler yerleşiktir. **Not:** hedefleri tüm proje dosyalarını gerçekleşmelidir. Yapmazsanız, bir derleme hatası oluşur.|  
|`ToolsVersion`|İsteğe bağlı `String` parametresi.<br /><br /> Belirtir `ToolsVersion` bu göreve geçirilen projeler derleme yapılırken kullanılacak.<br /><br /> Sağlayan bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] farklı bir sürümünü hedefleyen bir projeyi derlemek için görev [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] projede belirtilenden. Geçerli değerler `2.0`, `3.0` ve `3.5`. Varsayılan değer `3.5`.|  
|`UnloadProjectsOnCompletion`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, proje işlemi tamamlandıktan sonra kaldırılır.|  
|`UseResultsCache`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, önbelleğe alınan sonuç, varsa, döndürülür. TheMSBuild görevi çalıştırırsanız, sonuç bir kapsamda (ProjectFileName, GlobalProperties) önbelleğe alınır [TargetNames]<br /><br /> Yapı öğeleri listesi olarak|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
 Kullanmaktan farklı olarak [yürütme görevi](../msbuild/exec-task.md) MSBuild.exe başlatmak için bu görev aynı kullanır [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] alt projeleri oluşturmak üzere işlem. Atlanabilir zaten oluşturulmuş hedefler üst ve alt yapı arasında paylaşılır. Bu görev ayrıca olduğundan daha hızlıdır yeni [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] işlem oluşturulur.  
  
 Bu görev, sadece proje dosyalarını olmakla kalmayıp çözüm dosyalarını işleyebilir.  
  
 Gerekli herhangi bir yapılandırma [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] yapılandırma uzak içeriyorsa bile aynı anda oluşturmak projeleri etkinleştirmek için (örneğin, bağlantı noktaları, protokoller, zaman aşımları, yeniden deneme ve benzeri), altyapı kullanarak yapılandırılabilir hale getirilmesi gereken bir yapılandırma dosyası. Mümkün olduğunda, yapılandırma öğeleri olarak görev parametreler üzerinde belirtilmesi gerekir `MSBuild` görev.  
  
 ' Den başlayarak [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 3.5, çözüm projeleri tüm yapıların alt projeler şimdi yüzey TargetOutputs.  
  
## <a name="passing-properties-to-projects"></a>Projelere Özellikleri Geçirme  
 Sürümlerinde [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] öncesinde [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] farklı geçirme 3.5, listelenen farklı projelere özelliklerini ayarlar [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] öğesi zor. Özellikler öznitelik kullandıysanız [MSBuild görevi](../msbuild/msbuild-task.md), kendi ayarı tüm, toplu sürece oluşturulan projeleri uygulandı sonra [MSBuild görevi](../msbuild/msbuild-task.md) ve koşullu farklı sağlanan Özellikler öğesi listesindeki her proje için.  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 3.5, ancak, iki yeni meta veri öğeleri, Özellikler ayrılmış ve farklı özellikler farklı geçirmek için esnek bir şekilde sağlayan AdditionalProperties projeleri eklenmesini sağlar kullanılarak oluşturulan [MSBuild görevi](../msbuild/msbuild-task.md).  
  
> [!NOTE]
>  Bu yeni meta veri öğeleri yalnızca projeleri özniteliğinde geçirilen öğe için geçerli olan [MSBuild görevi](../msbuild/msbuild-task.md).  
  
## <a name="multi-processor-build-benefits"></a>Birden Çok İşlemcili Derlemenin Avantajları  
 Bu yeni meta kullanmanın başlıca avantajlarından biri durum, çok işlemcili bir sistemde projelerinizi paralel yapı oluşur. Meta veriler, tüm projeleri tek bir araya getirmek sağlar [MSBuild görevi](../msbuild/msbuild-task.md) arama herhangi toplu işleme gerçekleştirmek zorunda veya koşullu olmadan [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] görevler. Ve yalnızca tek bir çağırdığınızda [MSBuild görevi](../msbuild/msbuild-task.md), tüm projeleri öznitelikte listelenen projeleri paralel olarak oluşturulacak. (Yalnızca, ancak, `BuildInParallel=true` özniteliktir mevcut [MSBuild görevi](../msbuild/msbuild-task.md).) Daha fazla bilgi için bkz: [yapı paralel olarak birden çok proje](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md).  
  
## <a name="properties-metadata"></a>Özellikler Meta Verisi  
 Kullanarak birden çok çözüm dosyalarını oluştururken ortak bir senaryodur [MSBuild görevi](../msbuild/msbuild-task.md), yalnızca farklı bir yapı yapılandırmalarını kullanarak. Çözüm a1 oluşturmak isteyebilir hata ayıklama yapılandırması ve çözüm a2 kullanarak sürüm Yapılandırması'nı kullanarak. İçinde [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 2.0, bu proje dosyası aşağıdaki gibi görünecektir:  
  
> [!NOTE]
>  Aşağıdaki örnekte, "..." ek çözüm dosyalarını temsil eder.  
  
### <a name="aproj"></a>a.proj  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="Build">  
        <MSBuild Projects="a1.sln..." Properties="Configuration=Debug"/>  
        <MSBuild Projects="a2.sln" Properties="Configuration=Release"/>  
    </Target>  
</Project>  
```  
  
 Özellik meta verileri kullanarak, ancak, tek bir kullanmak için bunu basitleştirebilirsiniz [MSBuild görevi](../msbuild/msbuild-task.md)tarafından aşağıda gösterildiği gibi:  
  
### <a name="aproj"></a>a.proj  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <ProjectToBuild Include="a1.sln...">  
            <Properties>Configuration=Debug</Properties>  
        </ProjectToBuild>  
        <ProjectToBuild Include="a2.sln">  
            <Properties>Configuration=Release</Properties>  
        </ProjectToBuild>  
    </ItemGroup>  
    <Target Name="Build">  
        <MSBuild Projects="@(ProjectToBuild)"/>  
    </Target>  
</Project>  
```  
  
 \- veya -  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <ProjectToBuild Include="a1.sln..."/>  
        <ProjectToBuild Include="a2.sln">  
            <Properties>Configuration=Release</Properties>  
        </ProjectToBuild>  
    </ItemGroup>  
    <Target Name="Build">  
        <MSBuild Projects="@(ProjectToBuild)"   
          Properties="Configuration=Debug"/>  
    </Target>  
</Project>  
```  
  
## <a name="additionalproperties-metadata"></a>AdditionalProperties Meta Verisi  
 Burada oluşturduğunuz iki çözüm dosyalarını kullanarak aşağıdaki senaryoyu göz önünde bulundurun [MSBuild görevi](../msbuild/msbuild-task.md), her iki sürüm Yapılandırması'nı kullanarak, ancak bir x86 kullanarak mimarisi ve diğer IA64 mimarisi kullanarak. İçinde [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 2.0, birden çok örneğini oluşturmanız gerekir [MSBuild görevi](../msbuild/msbuild-task.md): biri ile x86 yayın Yapılandırması'nı kullanarak Projeyi derlemek için diğer ile IA64 yayın Yapılandırması'nı kullanarak mimarisi Mimari. Proje dosyası aşağıdaki gibi görünür:  
  
### <a name="aproj"></a>a.proj  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="Build">  
        <MSBuild Projects="a1.sln..." Properties="Configuration=Release;   
          Architecture=x86"/>  
        <MSBuild Projects="a2.sln" Properties="Configuration=Release;   
          Architecture=ia64"/>  
    </Target>  
</Project>  
```  
  
 AdditionalProperties meta verileri kullanarak, tek bir kullanmak için bunu basitleştirebilirsiniz [MSBuild görevi](../msbuild/msbuild-task.md) aşağıdaki kullanarak:  
  
### <a name="aproj"></a>a.proj  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <ProjectToBuild Include="a1.sln...">  
            <AdditionalProperties>Architecture=x86  
              </AdditionalProperties>  
        </ProjectToBuild>  
        <ProjectToBuild Include="a2.sln">  
            <AdditionalProperties>Architecture=ia64  
              </AdditionalProperties>  
        </ProjectToBuild>  
    </ItemGroup>  
    <Target Name="Build">  
        <MSBuild Projects="@(ProjectToBuild)"   
          Properties="Configuration=Release"/>  
    </Target>  
</Project>  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `MSBuild` tarafından belirtilen projeleri oluşturmak üzere görev `ProjectReferences` öğe koleksiyonu. Sonuçta elde edilen hedef çıkarır depolanır `AssembliesBuiltByChildProjects` öğe koleksiyonu.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <ProjectReferences Include="*.*proj" />  
    </ItemGroup>  
  
    <Target Name="BuildOtherProjects">  
        <MSBuild  
            Projects="@(ProjectReferences)"  
            Targets="Build">  
            <Output  
                TaskParameter="TargetOutputs"  
                ItemName="AssembliesBuiltByChildProjects" />  
        </MSBuild>  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)