---
title: "Nasıl yapılır: birden çok proje şablonu oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio templates, creating multi-project templates
- project templates, creating multi-project templates
- multi-project templates
ms.assetid: 8c7f7065-137e-40ad-868d-37e007270efd
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9d4ffd6c3aa23ebc2b801de2d581876ff5afd480
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-multi-project-templates"></a>Nasıl Yapılır: Birden Çok Proje Şablonu Oluşturma
Birden fazla projeli şablonlar, iki veya daha fazla proje için kapsayıcı olarak davranır. Ne zaman bir proje bir birden çok proje şablonu temel alarak oluşturulur **yeni proje** iletişim kutusu, şablondaki her proje çözüme eklenir.  
  
 Birden çok proje şablonu bir .zip dosyasına sıkıştırılmış aşağıdaki öğeleri şunları içermelidir:  
  
-   Tüm birden çok proje şablonu için bir kök .vstemplate dosya. Bu kök .vstemplate dosya meta verileri içerir, **yeni proje** iletişim kutusu görüntüler ve bu şablonda projeler için .vstemplate dosyaları nerede bulacağını belirler. Bu dosya .zip dosyasının kök dizininde olması gerekir.  
  
-   Tam proje şablonu için gerekli dosyaları içeren bir veya daha fazla klasörler. Bu proje için tüm kod dosyaları ve proje için .vstemplate dosyası içerir.  
  
 Örneğin, iki proje içeren birden çok proje şablonu .zip dosyası, aşağıdaki dosyaları ve dizinleri sahip olabilir:  
  
 MultiProjectTemplate.vstemplate  
  
 \Project1\Project1.vstemplate  
  
 \Project1\Project1.vbproj  
  
 \Project1\Class.vb  
  
 \Project2\Project2.vstemplate  
  
 \Project2\Project2.vbproj  
  
 \Project2\Class.vb  
  
 Birden çok proje şablonu için kök .vstemplate dosyası tek proje şablondan aşağıdaki yollarla farklıdır:  
  
-   `Type` Özniteliği `VSTemplate` ögesinin değeri `ProjectGroup`. Örneğin:  
  
    ```  
    <VSTemplate Version="2.0.0" Type="ProjectGroup"  
        xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    ```  
  
-   `TemplateContent` Öğesi içeren bir `ProjectCollection` bir veya daha fazla olan öğeyi `ProjectTemplateLink` yolları dahil projelerinin .vstemplate dosyaları tanımlayan öğeleri. Örneğin:  
  
    ```  
    <TemplateContent>  
        <ProjectCollection>  
            <ProjectTemplateLink>  
                Project1\Project1.vstemplate  
            </ProjectTemplateLink>  
            <ProjectTemplateLink>  
                Project2\Project2.vstemplate  
            </ProjectTemplateLink>  
        </ProjectCollection>  
    </TemplateContent>  
    ```  
  
 Birden çok proje şablonu de normal şablonları farklı şekilde davranır. Birden çok proje şablonu aşağıdaki benzersiz özelliklere sahiptir:  
  
-   Birden çok proje şablonu tek tek projelerinde adlarıyla atanamaz **yeni proje** iletişim kutusu. Bunun yerine, kullanın `ProjectName` özniteliği `ProjectTemplateLink` öğesi her proje için ad belirtin. Daha fazla bilgi için aşağıdaki bölümde ilk örnekte bakın.  
  
-   Birden çok proje şablonu, farklı dillerde yazılmış projeleri içerebilir, ancak tüm şablonu yalnızca tarafından bir kategorideki kullanarak yerleştirilebileceği `ProjectType` öğesi.  
  
### <a name="to-create-a-multi-project-template"></a>Birden çok proje şablonu oluşturmak için  
  
1.  Birden çok proje şablona dahil edilecek projeleri oluşturun.  
  
2.  .Vstemplate dosyaları her proje için oluşturursunuz. Daha fazla bilgi için bkz: [nasıl yapılır: Proje şablonları oluşturma](../ide/how-to-create-project-templates.md).  
  
3.  Bir kök .vstemplate dosyası, birden çok proje şablonu için meta verileri içerecek şekilde oluşturun. Daha fazla bilgi için aşağıdaki bölümde ilk örnekte bakın.  
  
4.  Dosya ve klasörlerin şablonunuzda dahil, seçime sağ tıklayın, seçin **göndermek için**ve ardından **sıkıştırılmış (daraltılmış) klasör**. Dosya ve klasörlerin bir .zip dosyasına sıkıştırılır.  
  
5.  .Zip şablon dosyası içine [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje şablonu dizini. Varsayılan olarak, bu \My Documents\Visual Studio dizindir *sürüm*\Templates\ProjectTemplates\\.  
  
## <a name="example"></a>Örnek  
 Bu örnek, bir temel birden çok proje kök .vstemplate dosyası gösterir. Bu örnekte, iki proje şablonu içeren `My Windows Application` ve `My Class Library`. `ProjectName` Özniteliği `ProjectTemplateLink` öğesi adını ayarlar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bu proje atamak için. Varsa `ProjectName` özniteliği yok, .vstemplate dosyasının adı proje adı olarak kullanılır.  
  
```  
<VSTemplate Version="2.0.0" Type="ProjectGroup"  
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
  
## <a name="example"></a>Örnek  
 Bu örnekte `SolutionFolder` projeleri iki gruplara ayırmak için öğesi `Math Classes` ve `Graphics Classes`. Şablon ikisi her çözüm klasörüne yerleştirilir dört projeleri içerir.  
  
```  
<VSTemplate Version="2.0.0" Type="ProjectGroup"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>Multi-Project Template Sample</Name>  
        <Description>An example of a multi-project template</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>VisualBasic</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectCollection>  
            <SolutionFolder Name="Math Classes">  
                <ProjectTemplateLink ProjectName="MathClassLib1">  
                    MathClassLib1\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
                <ProjectTemplateLink ProjectName="MathClassLib2">  
                    MathClassLib2\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
            </SolutionFolder>  
            <SolutionFolder Name="Graphics Classes">  
                <ProjectTemplateLink ProjectName="GraphicsClassLib1">  
                    GraphicsClassLib1\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
                <ProjectTemplateLink ProjectName="GraphicsClassLib2">  
                    GraphicsClassLib2\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
            </SolutionFolder>  
        </ProjectCollection>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [Nasıl yapılır: Proje şablonları oluşturma](../ide/how-to-create-project-templates.md)   
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [SolutionFolder öğesi (Visual Studio şablonları)](../extensibility/solutionfolder-element-visual-studio-templates.md)   
 [ProjectTemplateLink öğesi (Visual Studio şablonları)](../extensibility/projecttemplatelink-element-visual-studio-templates.md)