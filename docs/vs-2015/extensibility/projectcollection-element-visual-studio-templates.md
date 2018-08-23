---
title: ProjectCollection öğesi (Visual Studio şablonları) | Microsoft Docs
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
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectCollection
helpviewer_keywords:
- <ProjectCollection> element [Visual Studio Templates]
- ProjectCollection element [Visual Studio Templates]
ms.assetid: deb27180-2035-49ed-b835-c47bb3cd2f8f
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b6ca66c8cf18c891d7f9a771495af14eb4cc9921
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688134"
---
# <a name="projectcollection-element-visual-studio-templates"></a>ProjectCollection Öğesi (Visual Studio Şablonları)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ProjectCollection öğesi (Visual Studio şablonları)](https://docs.microsoft.com/visualstudio/extensibility/projectcollection-element-visual-studio-templates).  
  
Birden fazla projeli şablonların içeriğini ve düzenini belirtir.  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<ProjectCollection >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<ProjectCollection>  
    <ProjectTemplateLink> ... </ProjectTemplateLink>  
    <SolutionFolder> ... </SolutionFolder>  
</ProjectCollection>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Aşağıdaki bölümlerde öznitelik, alt öğeler ve üst öğeler açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[ProjectTemplateLink](../extensibility/projecttemplatelink-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Bir projenin birden fazla projeli bir şablonda belirtir.|  
|[SolutionFolder](../extensibility/solutionfolder-element-visual-studio-templates.md)|İsteğe bağlı öğe.<br /><br /> Birden fazla projeli şablonlardaki projeleri gruplandırır.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Gerekli öğe.<br /><br /> Şablonu içeriğini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Birden fazla projeli şablonlar, iki veya daha fazla proje için kapsayıcı olarak davranır. `ProjectCollection` Öğe, şablonu içeren projeleri belirtmek için kullanılır. Birden fazla projeli Şablonlar hakkında daha fazla bilgi için bkz. [nasıl yapılır: Create multi-Project Templates](../ide/how-to-create-multi-project-templates.md).  
  
## <a name="example"></a>Örnek  
 Bu örnekte, basit bir çoklu proje kök .vstemplate dosyası gösterilmektedir. Bu örnekte, şablon iki proje içermektedir `My Windows Application` ve `My Class Library`. `ProjectName` Özniteliği `ProjectTemplateLink` öğesi adını ayarlar [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] bu projeye atanacak. Varsa `ProjectName` özniteliği mevcut değilse, .vstemplate dosyasının adı proje adı olarak kullanılır.  
  
```  
<VSTemplate Version="3.0.0" Type="ProjectGroup"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>Multi-Project Template Sample</Name>  
        <Description>An example of a multi-project template</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>VisualBasic</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectCollection>  
            <ProjectTemplateLink ProjectName="My Windows Application">  
                WindowsApp\MyTemplate.vstemplate  
            </ProjectTemplateLink>  
            <ProjectTemplateLink ProjectName="My Class Library">  
                ClassLib\MyTemplate.vstemplate  
            </ProjectTemplateLink>  
        </ProjectCollection>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [Nasıl Yapılır: Birden Çok Proje Şablonu Oluşturma](../ide/how-to-create-multi-project-templates.md)

