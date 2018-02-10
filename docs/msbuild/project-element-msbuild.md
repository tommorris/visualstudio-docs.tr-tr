---
title: "Proje öğesi (MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Project
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ToolsVersion attribute [MSBuild]
- <Project> element [MSBuild]
- Project element [MSBuild]
ms.assetid: d1cda56a-dbef-4109-9201-39e962e3f653
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: bf347f135368b2452170e7ebfa9c987ed19adf77
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="project-element-msbuild"></a>Proje Öğesi (MSBuild)
Gerekli kök öğesinin bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası.  

## <a name="syntax"></a>Sözdizimi  

```  
<Project InitialTargets="TargetA;TargetB"  
         DefaultTargets="TargetC;TargetD"  
         TreatAsLocalProperty="PropertyA;PropertyB"  
         ToolsVersion=<version number>
         Sdk="name[/version]"
         xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Sdk... />
    <Choose>... </Choose>  
    <PropertyGroup>... </PropertyGroup>  
    <ItemGroup>... </ItemGroup>  
    <Target>... </Target>  
    <UsingTask.../>  
    <ProjectExtensions>... </ProjectExtensions>  
    <Import... />  
</Project>  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  

|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`DefaultTargets`|İsteğe bağlı öznitelik.<br /><br /> Varsayılan hedef veya hedef belirtilen yapı giriş noktası olarak hedefler. Noktalı virgülle (;) birden çok hedefi olan ayrılmış.<br /><br /> Varsayılan hedef yok ya da belirtilmişse, `DefaultTargets` özniteliği veya [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] komut satırı altyapısı yürütür ilk hedef sonra proje dosyasında [alma](../msbuild/import-element-msbuild.md) öğeleri değerlendirilir.|  
|`InitialTargets`|İsteğe bağlı öznitelik.<br /><br /> İlk hedef veya belirtilen hedefleri önce çalıştırılacak hedefleri `DefaultTargets` özniteliği veya komut satırında. Noktalı virgülle (;) birden çok hedefi olan ayrılmış.|  
|`Sdk`|İsteğe bağlı öznitelik. <br /><br /> Örtük oluşturmak için kullanılacak isteğe bağlı bir sürüm ve SDK adını .proj dosyasına eklenen deyimleri içeri aktarın. Hiçbir sürüm belirtilmezse, MSBuild varsayılan sürüm çözümlemeye çalışır.  Örneğin, `<Project Sdk="Microsoft.NET.Sdk" />` veya `<Project Sdk="My.Custom.Sdk/1.0.0" />`.|  
|`ToolsVersion`|İsteğe bağlı öznitelik.<br /><br /> MSBuild araç takımı sürümü $(MSBuildBinPath) ve $(MSBuildToolsPath) için değerleri belirlemek için kullanır.|  
|`TreatAsLocalProperty`|İsteğe bağlı öznitelik.<br /><br /> Genel olarak kabul edilebilir olmaz özellik adları. Bu öznitelik, belirli komut satırı özelliklerini bir proje veya hedefleri dosyasını ve tüm sonraki almalar ayarlama özelliği değerler önlemiş olursunuz. Noktalı virgülle (;) birden çok özelliklerdir ayrılmış.<br /><br /> Normalde, genel özellikler proje veya hedefleri dosyasında ayarlanan özellik değerlerini geçersiz kılar. Özellik listelenmişse `TreatAsLocalProperty` değer, genel özellik değerini değil geçersiz bu dosyayı ve sonraki tüm içeri aktarmalar ayarlanmış olan özellik değerlerini. Daha fazla bilgi için bkz: [nasıl yapılır: farklı seçeneklerle aynı kaynak dosyaları derleme](../msbuild/how-to-build-the-same-source-files-with-different-options.md). **Not:** genel özelliklerini kullanarak bir komut isteminde set **/property** (veya **/p**) geçin. Ayrıca ayarlayın veya birden çok proje derleme alt projeler için genel özellikleri kullanarak değiştirme `Properties` MSBuild görevi özniteliğidir. Daha fazla bilgi için bkz: [MSBuild görevi](../msbuild/msbuild-task.md).|  
|`Xmlns`|İsteğe bağlı öznitelik.<br /><br /> Belirtildiğinde, `xmlns` özniteliği "http://schemas.microsoft.com/developer/msbuild/2003" değerine sahip olmalıdır.|  

### <a name="child-elements"></a>Alt Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Seçin](../msbuild/choose-element-msbuild.md)|İsteğe bağlı öğe.<br /><br /> Bir grubu seçmek için alt öğeler değerlendirir `ItemGroup` öğeleri ve/veya `PropertyGroup` değerlendirmek için öğeleri.|  
|[İçeri aktarma](../msbuild/import-element-msbuild.md)|İsteğe bağlı öğe.<br /><br /> Başka bir proje dosyasını içeri aktarmak bir proje dosyası sağlar. Sıfır veya daha fazla olabilir `Import` proje öğelerinde.|  
|[ItemGroup](../msbuild/itemgroup-element-msbuild.md)|İsteğe bağlı öğe.<br /><br /> Grouping öğesi tek tek öğelerin. Öğelerini belirtilen kullanarak [öğesi](../msbuild/item-element-msbuild.md) öğesi. Sıfır veya daha fazla olabilir `ItemGroup` proje öğelerinde.|  
|[ProjectExtensions](../msbuild/projectextensions-element-msbuild.md)|İsteğe bağlı öğe.<br /><br /> Kalıcı olmayan bir yol sağlar[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] bilgilerinde bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası. Sıfır veya bir olabilir `ProjectExtensions` proje öğelerinde.|  
|[PropertyGroup](../msbuild/propertygroup-element-msbuild.md)|İsteğe bağlı öğe.<br /><br /> Grouping öğesi için ayrı ayrı özellikler. Özellikleri kullanarak belirtilen [özelliği](../msbuild/property-element-msbuild.md) öğesi. Sıfır veya daha fazla olabilir `PropertyGroup` proje öğelerinde.|
|[Sdk](../msbuild/sdk-element-msbuild.md)|İsteğe bağlı öğe.<br /><br /> Başvurular bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] SDK projesi.  Bu öğe, alternatif Sdk özniteliği olarak kullanılabilir.|  
|[Hedef](../msbuild/target-element-msbuild.md)|İsteğe bağlı öğe.<br /><br /> Görevler için bir dizi içeren [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] sıralı olarak yürütülecek. Görevler belirtilen kullanarak [görev](../msbuild/task-element-msbuild.md) öğesi. Sıfır veya daha fazla olabilir `Target` proje öğelerinde.|  
|[UsingTask](../msbuild/usingtask-element-msbuild.md)|İsteğe bağlı öğe.<br /><br /> Görevleri kaydetmek için bir yol sağlar [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Sıfır veya daha fazla olabilir `UsingTask` proje öğelerinde.|  

### <a name="parent-elements"></a>Üst Öğeler  
 Yok.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: derleme için önce hangi hedefin belirtme](../msbuild/how-to-specify-which-target-to-build-first.md)   
 [Komut satırı başvurusu](../msbuild/msbuild-command-line-reference.md)   
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)   
 [MSBuild](../msbuild/msbuild.md)
