---
title: "Proje öğesi (Visual Studio şablonları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#Project
helpviewer_keywords:
- Project element [Visual Studio Templates]
- <Project> element [Visual Studio Templates]
ms.assetid: 1da15ea6-26e2-462b-a03e-584ef4996579
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e6fd8881d484f35a0183d83d1b540fc2249e9c4f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="project-element-visual-studio-templates"></a>Project Öğesi (Visual Studio Şablonları)
Dosya veya dizinlerin projeye eklemek için belirtir.  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<Proje >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Project  
    File="MyProject.proj"  
    TargetFileName="MyTargetProject.proj"  
    ReplaceParameters="true/false">  
    IgnoreProjectParameter="$myCustomParameter$"  
        ...  
</Project>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Aşağıdaki bölümlerde öznitelik, alt öğeler ve üst öğeler açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`File`|Gerekli öznitelik.<br /><br /> Proje dosyası adını şablon .zip dosyası belirtir.|  
|`ReplaceParameters`|İsteğe bağlı öznitelik.<br /><br /> Proje dosyası bir proje şablonu oluşturduğunuzda, değiştirilmesi gereken parametre değerleri içerip içermediğini belirten bir Boole değeri. Varsayılan değer `false`.|  
|`TargetFileName`|İsteğe bağlı öznitelik.<br /><br /> Bir proje şablonu oluşturulduğunda, proje dosyası adını belirtir.|  
|`IgnoreProjectParameter`|İsteğe bağlı öznitelik.<br /><br /> Geçerli çözüme proje eklenmesi gerekip gerekmediğini belirtir. Varsa özel parametresinin değeri "$*myCustomParameter*$" var. parametre değiştirme dosyası projeye oluşturulur, ancak şu anda açık çözümün bir parçası eklenmedi.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Klasör](../extensibility/folder-element-visual-studio-project-templates.md)|İsteğe bağlı öğe.<br /><br /> Projeye eklemek için bir klasör belirtir.|  
|[ProjectItem](../extensibility/projectitem-element-visual-studio-project-templates.md)|İsteğe bağlı öğe.<br /><br /> Bir projeye eklemek için dosyayı belirtir.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Gerekli öğe.|  
  
## <a name="remarks"></a>Açıklamalar  
 `Project`bir isteğe bağlı bir alt öğenin `TemplateContent`.  
  
 `Project` Öğesi için kısa bir proje kullanılır ve bu nedenle, yalnızca proje şablonlarını geçerli değil.  
  
 `Project`öğeleri olabilir [klasörü](../extensibility/folder-element-visual-studio-project-templates.md) alt öğeleri veya [ProjectItem](../extensibility/projectitem-element-visual-studio-project-templates.md) alt öğeleri ancak değil her ikisinin bir karışımıyla `Folder` ve `ProjectItem` alt öğeleri.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]kullanıcı tarafından girilen adına dayalı proje dosyası adı otomatik olarak yeniden adlandırır **yeni proje** iletişim kutusu. Kullanım `TargetFileName` şablonla oluşturulan proje dosyalarını için bir alternatif dosya adı sağlamak istiyorsanız özniteliği.  
  
## <a name="example"></a>Örnek  
 Meta veriler için bir proje şablonu için aşağıdaki örnekte bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] uygulama.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic starter kit</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyStarterKit.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [ProjectItem öğesi (Visual Studio Proje şablonları)](../extensibility/projectitem-element-visual-studio-project-templates.md)   
 [Folder Öğesi (Visual Studio Proje Şablonları)](../extensibility/folder-element-visual-studio-project-templates.md)