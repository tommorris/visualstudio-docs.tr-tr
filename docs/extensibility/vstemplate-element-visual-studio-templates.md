---
title: VSTemplate öğesi (Visual Studio şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#VSTemplate
helpviewer_keywords:
- VSTemplate element [Visual Studio project templates]
ms.assetid: f8ac561b-3b0b-4246-9ec9-118d2447e9a9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f6151dfd852a76caa1dccbae55241af89681fd81
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31141408"
---
# <a name="vstemplate-element-visual-studio-templates"></a>VSTemplate Öğesi (Visual Studio Şablonları)
Proje şablonu, öğe şablonu veya starter kit hakkında tüm meta veriler içeriyor.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<VSTemplate Type="TemplateType" Version="x.x.x">  
    <TemplateData>    </TemplateData>  
    <TemplateContent>    </TemplateContent>  
    ...  
</VSTemplate>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Type`|Şablon için bir proje şablonu veya bir öğe şablonu olarak tanımlar. Bu öznitelik değerini olabilir `Project` veya `Item`.|  
|`Version`|Şablon için bir sürüm numarasını belirtir. Şablonlarda [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] ve [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] sahip bir `Version` öznitelik değerini `3.0.0`.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Gerekli öğe.<br /><br /> Şablon kategorilere ayırır ve içinde biçimini tanımlayan veri belirtir **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu.|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Gerekli öğe.<br /><br /> Şablon içeriğini belirtir.|  
|[WizardExtension](../extensibility/wizardextension-element-visual-studio-templates.md)|İsteğe bağlı öğe.|  
|[WizardData](../extensibility/wizarddata-element-visual-studio-templates.md)|İsteğe bağlı öğe.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
 Yok.  
  
## <a name="remarks"></a>Açıklamalar  
 `VSTemplate` .Vstemplate dosyaları kök öğesinin bir öğedir.  
  
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
            <ProjectItem>Form1.cs</ProjectItem>  
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
 [Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)