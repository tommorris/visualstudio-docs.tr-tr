---
title: Folder öğesi (Visual Studio Proje şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#Folder
helpviewer_keywords:
- Folder element [Visual Studio project templates]
ms.assetid: 558e3d41-0db5-4c44-82bb-6bb87892b093
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c2ecf9c2973a5fb09cf1a217bd700882dce41626
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="folder-element-visual-studio-project-templates"></a>Folder Öğesi (Visual Studio Proje Şablonları)
Projeye eklenen bir klasörü belirtir.  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<Proje >  
 \<Klasör >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Folder Name="Project Folder">  
    <Folder> ... </Folder>  
    <ProjectItem> ... </ProjectItem>  
</Folder>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Aşağıdaki bölümlerde öznitelik, alt öğeler ve üst öğeler açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Name`|Gerekli öznitelik.<br /><br /> Proje klasörünü adı.|  
|`TargetFolderName`|İsteğe bağlı öznitelik.<br /><br /> Bir proje şablonu oluşturulduğunda klasörü verilecek ad belirtir. Bu parametre değiştirme kullanarak bir klasör adı oluşturmak için yararlı bir özniteliktir veya uluslararası bir dize içeren bir klasör adlandırma doğrudan .zip dosyası kullanılamaz.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|`Folder`|Projeye eklemek için bir klasör belirtir. `Folder` alt öğeler içerebilir `Folder` öğeleri.|  
|[ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md)|Projeye eklemek için dosyayı belirtir.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Project](../extensibility/project-element-visual-studio-templates.md)|İsteğe bağlı bir alt öğenin [TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md).|  
  
## <a name="remarks"></a>Açıklamalar  
 `Folder` İsteğe bağlı bir alt `Project`.  
  
 Proje öğeleri şablonunda klasörler halinde düzenlemek için aşağıdaki yöntemlerden herhangi birini kullanabilirsiniz:  
  
-   Klasörleri şablon .zip dosyasına eklenecek ve bunları .vstemplate dosyanın projede dosya yolunu belirterek ekleyin `ProjectItem` hiçbir öğeleri `Folder` öğeleri. Bu önerilen bir yöntemdir. Örneğin:  
  
     `...`  
  
     `<ProjectItem>\Folder\item.cs</ProjectItem>`  
  
     `<ProjectItem>Form1.cs</ProjectItem>`  
  
     `...`  
  
-   Klasörleri şablon .zip dosyasına eklenecek ve bunları .vstemplate dosyasıyla projeye ekleyin `Folder` öğeleri. Örneğin:  
  
     `...`  
  
     `<Folder name="Folder">`  
  
     `<ProjectItem>item.cs</ProjectItem>`  
  
     `</Folder>`  
  
     `<ProjectItem>Form1.cs</ProjectItem>`  
  
     `...`  
  
-   Klasörleri şablon .zip dosyasında içermemesi ancak kullanarak klasörler ekleme `TargetFileName` özniteliği `ProjectItem` öğesi. Örneğin:  
  
     `...`  
  
     `<ProjectItem TargetFileName="\Folder\item.cs">item.cs</ProjectItem>`  
  
     `<ProjectItem>Form1.cs</ProjectItem>`  
  
     `...`  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek için bir proje şablonu için meta veriler gösterilmektedir bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] Windows uygulaması.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <Folder Name="Properties">  
                <ProjectItem>AssemblyInfo.cs</ProjectItem>  
                <ProjectItem>Resources.resx</ProjectItem>  
                <ProjectItem>Resources.Designer.cs</ProjectItem>  
                <ProjectItem>Settings.settings</ProjectItem>  
                <ProjectItem>Settings.Designer.cs</ProjectItem>  
            </Folder>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [ProjectItem Öğesi (Visual Studio Öğe Şablonları)](../extensibility/projectitem-element-visual-studio-item-templates.md)