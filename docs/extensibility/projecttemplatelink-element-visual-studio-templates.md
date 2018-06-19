---
title: ProjectTemplateLink öğesi (Visual Studio şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectTemplateLink
helpviewer_keywords:
- <ProjectTemplateLink> element [Visual Studio Templates]
- ProjectTemplateLink element [Visual Studio Templates]
ms.assetid: b0449111-8b48-45a1-a031-ea24b765e969
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 10ebc56e03a6582ab37126097db5f79ed9c5f2a5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31143595"
---
# <a name="projecttemplatelink-element-visual-studio-templates"></a>ProjectTemplateLink Öğesi (Visual Studio Şablonları)
Birden fazla projeli bir şablonda, tek bir projenin .vstemplate dosyasının yolunu belirtir.  
  
 \<VSTemplate >  
 \<TemplateContent >  
 \<ProjectCollection >  
 \<ProjectTemplateLink >  
-veya-  
\<VSTemplate >  
 \<TemplateContent >  
 \<ProjectCollection >  
 \<SolutionFolder >  
 \<ProjectTemplateLink >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<ProjectTemplateLink ProjectName="Name">  
    PathToTemplateFile  
</ProjectTemplateLink>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Aşağıdaki bölümlerde öznitelik, alt öğeler ve üst öğeler açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`ProjectName`|İsteğe bağlı öznitelik.<br /><br /> Birden fazla projeli bir şablonda, her bir proje için adı belirtir. **Yeni proje** iletişim kutusu, tek tek projelerine adları atayamazsınız.|  
|`CopyParameters`|Ana grup şablonundaki tüm değişkenlerin bağlı şablonların her birine kopyalanmasını sağlar.<br /><br /> Bir önek bağlantılı şablonlarındaki parametrelere sahip `"$ext_*$"`. Örneğin, üst grup şablonu varsa parametresi `$projectname$` bir değere sahip **ExampleProject1**yürütülecek, kendi dönüş bağlantılı şablonunu alır, bir parametre alması `$ext_projectname$`, kopyasınıolduğu`$projectname$`üst grup şablondan parametresi.<br /><br /> Bu durum, bağlı şablonların, yalnızca üst grup şablonunda rahatlıkla oluşturulabilecek bazı ortak parametreleri paylaşmasına olanak sağlar.<br /><br /> Bu öznitelik isteğe bağlıdır ve otomatik olarak için varsayılanları `false` zaman onu dahil değildir.<br /><br /> Visual Studio 2013 güncelleştirme 2 kullanıma sunuldu. Doğru ürün sürümü başvuru için bkz: [Visual Studio 2013 güncelleştirme 2 SDK teslim başvuran derlemeler](http://msdn.microsoft.com/en-us/42b65c3e-e42b-4c39-98c8-bea285f25ffb).|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[ProjectCollection](../extensibility/projectcollection-element-visual-studio-templates.md)|Birden fazla projeli şablonların içeriğini ve düzenini belirtir.|  
|[SolutionFolder](../extensibility/solutionfolder-element-visual-studio-templates.md)|Birden fazla projeli şablonlardaki projeleri gruplandırır.|  
  
## <a name="text-value"></a>Metin Değeri  
 Bir metin değeri gereklidir.  
  
 Bu metin, şablonun .vstemplate dosyasının yolunu belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Birden fazla projeli şablonlar, iki veya daha fazla proje için kapsayıcı olarak davranır. `ProjectTemplateLink` Öğesi şablonda projelerden biri için .vstemplate dosyanın konumunu belirtmek için kullanılır. Birden çok proje şablonu .vstemplate dosya içeriyor `ProjectTemplateLink` şablondaki her proje öğesi. Birden çok proje şablonları hakkında daha fazla bilgi için bkz: [nasıl yapılır: birden çok proje şablonları oluşturma](../ide/how-to-create-multi-project-templates.md).  
  
## <a name="example"></a>Örnek  
 Bu örnekte, basit bir çoklu proje kök .vstemplate dosyası gösterilmektedir. Bu örnekte, iki proje şablonu içeren `My Windows Application` ve `My Class Library`. `ProjectName` Özniteliği `ProjectTemplateLink` öğesi adını ayarlar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bu proje atamak için. Varsa `ProjectName` özniteliği yok, .vstemplate dosyasının adı proje adı olarak kullanılır.  
  
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
            <ProjectTemplateLink ProjectName="My Class Library" CopyParameters="true">  
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