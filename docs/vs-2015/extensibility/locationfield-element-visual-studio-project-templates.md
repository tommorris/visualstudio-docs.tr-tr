---
title: LocationField öğesi (Visual Studio Proje şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#LocationField
helpviewer_keywords:
- LocationField element [Visual Studio project templates]
ms.assetid: 6aaaa155-6ce0-4f7f-aa50-8d63d7a7c992
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ea66808097c0e62d6c36781d7f288ed06975f6e1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693300"
---
# <a name="locationfield-element-visual-studio-project-templates"></a>LocationField Öğesi (Visual Studio Proje Şablonları)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [LocationField öğesi (Visual Studio Proje şablonları)](https://docs.microsoft.com/visualstudio/extensibility/locationfield-element-visual-studio-project-templates).  
  
Belirtir olup olmadığını **konumu** metin kutusu **yeni proje** iletişim kutusu etkin, devre dışı veya gizli proje şablonu.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<LocationField >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<LocationField> Enabled/Disabled/Hidden </LocationField>  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Gerekli öğe.<br /><br /> Şablonu kategorilere ayırır ve nasıl görüntülendiğini tanımlar **yeni proje**.|  
  
## <a name="text-value"></a>Metin Değeri  
 Bir metin değeri gereklidir.  
  
 Geçerli bir metin değerleri şunlardır:  
  
-   `Enabled`, hangi belirtir **konumu** kutusunun **yeni proje** iletişim kutusu etkin.  
  
-   `Disabled`, hangi belirtir **konumu** kutusunun **yeni proje** iletişim kutusu devre dışı bırakıldı.  
  
-   `Hidden`, hangi belirtir **konumu** kutusunun **yeni proje** iletişim kutusu gizlenir.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan değer `Enabled` şeklindedir.  
  
 **Konumu** metin kutusu **yeni proje** iletişim kutusu yeni projeler kaydedilir varsayılan dizinini değiştirme olanağı sağlar.  
  
 İçinde belirtilen değerle `Location` temel proje sistemi destekliyorsa öğesi iletişim kutusu tarafından yalnızca kabul.  
  
## <a name="example"></a>Örnek  
 Meta veriler için aşağıdaki örnekte bir [!INCLUDE[csprcs](../includes/csprcs-md.md)] şablonu.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <LocationField>Disabled</LocationField>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
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

