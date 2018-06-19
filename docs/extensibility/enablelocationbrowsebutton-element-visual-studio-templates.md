---
title: EnableLocationBrowseButton öğesi (Visual Studio şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#EnableLocationBrowseButton
helpviewer_keywords:
- EnableLocationBrowseButton [Visual Studio project templates]
ms.assetid: a12d10d8-af49-482a-af77-e084fd07a47d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7d3573a1359cf7cc6347ede28b5361b01bbb7efb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126852"
---
# <a name="enablelocationbrowsebutton-element-visual-studio-templates"></a>EnableLocationBrowseButton Öğesi (Visual Studio Şablonları)
Belirtir olup olmadığını **Gözat** düğmesi kullanılabilir **yeni proje** iletişim kutusunda, böylece kullanıcıların kolayca yeni bir proje kaydettiğiniz yere varsayılan dizini değiştirebilirsiniz.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<EnableLocationBrowseButton >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<EnableLocationBrowseButton> true/false </EnableLocationBrowseButton>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Gerekli öğe.<br /><br /> Şablon kategorilere ayırır ve nasıl ya da görüntüler tanımlar **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu.|  
  
## <a name="text-value"></a>Metin Değeri  
 Bir metin değeri gereklidir.  
  
 Metin ya da olmalıdır `true` veya `false`, görüntüleme gerekip gerekmediğini belirten **Gözat** düğmesini **yeni proje** iletişim kutusu.  
  
## <a name="remarks"></a>Açıklamalar  
 `EnableLocationBrowseButton` İsteğe bağlı bir öğedir. Varsayılan değer `true`, görüntüleyen **Gözat** düğmesini **yeni proje** iletişim kutusu.  
  
 İçinde **yeni proje** iletişim kutusu, **konumu** metin kutusuna yeni bir proje kaydettiğiniz yere dizini belirtir. **Gözat** düğme görüntüleyerek bu dizin değiştirmenize yardımcı olur **proje konumu** bilgisayarınızdan kullanılabilir farklı bir dizin kolayca gitmesini sağlar, iletişim kutusu ve ardından yeni proje kaydedildiği dizini olarak seçin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek için meta veriler gösterilmektedir bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] Windows uygulaması.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic starter kit</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <EnableLocationBrowseButton>false</EnableLocationBrowseButton>  
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
 [Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)