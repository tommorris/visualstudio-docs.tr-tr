---
title: ProjectType öğesi (Visual Studio şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectType
helpviewer_keywords:
- ProjectType element [Visual Studio project templates]
ms.assetid: ccf9d83f-c7f3-49c7-a31f-e1f22bec004c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bb16116994648ec70c770af7ca4932cd1443bd30
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31137888"
---
# <a name="projecttype-element-visual-studio-templates"></a>ProjectType Öğesi (Visual Studio Şablonları)
Böylece belirtilen grubunda altında görüntülenen proje şablonu kategorilere ayıran **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu.  
  
> [!WARNING]
>  Proje şablonları, Visual Studio 2012'den itibaren C++ için desteklenir. C++, Visual Studio 2010 ve önceki sürümlerinde desteklenmez.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<ProjectType >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<ProjectType> CSharp/VisualBasic/VC/Web </ProjectType>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Aşağıdaki bölümlerde öznitelik, alt öğeler ve üst öğeler açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Şablon kategorilere ayırır ve nasıl ya da görüntüler tanımlar **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu.|  
  
## <a name="text-value"></a>Metin Değeri  
 Bir metin değeri gereklidir.  
  
 Bu değer, proje şablonu türünü oluşturur ve aşağıdaki değerlerden birini içermelidir belirtir:  
  
-   `CSharp`: Belirtir şablon oluşturduğu bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] proje veya öğesi.  
  
-   `VisualBasic`: Belirtir şablon oluşturduğu bir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] proje veya öğesi.  
  
-   `Web`: Belirtir şablonu bir Web projesi veya öğesi oluşturur. Varsa `ProjectType` öğe içeriyorsa bu değer, proje ve öğe dilinin tanımlanan [ProjectSubType öğesi (Visual Studio şablonları)](../extensibility/projectsubtype-element-visual-studio-templates.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `ProjectType` gerekli bir alt öğesidir `TemplateData`.  
  
 Değeri `ProjectType` öğesi belirttiğinden şablonu içinde bulunduğu **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu. Örneğin, bir şablonla bir `ProjectType` değerini `CSharp` altında görünür **Visual C#** düğümünde **yeni proje** iletişim kutusu.  
  
 Bir şablon alt kullanarak belirtilebilir [ProjectSubType](../extensibility/projectsubtype-element-visual-studio-templates.md) öğesi.  
  
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
 [ProjectSubType Öğesi (Visual Studio Şablonları)](../extensibility/projectsubtype-element-visual-studio-templates.md)