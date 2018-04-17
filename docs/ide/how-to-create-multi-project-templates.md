---
title: Visual Studio için birden çok proje şablonu oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 01/02/2018
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio templates, creating multi-project
- project templates, multi-project
- multi-project templates
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: defffa0fcc532b7f27faa9ea0f11a13118b288dd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-multi-project-templates"></a>Nasıl yapılır: birden çok proje şablonu oluşturma

Birden fazla projeli şablonlar, iki veya daha fazla proje için kapsayıcı olarak davranır. Bir proje oluşturduğunuzda temel birden çok proje şablonu **yeni proje** iletişim kutusu, şablondaki her proje çözüme eklenir.

İki veya daha fazla proje şablonları ve kök şablon türü birden çok proje şablonu içeren `ProjectGroup`.

Birden çok proje şablonu tek proje şablonları farklı şekilde davranır. Bunlar aşağıdaki benzersiz özelliklere sahiptir:

- Birden çok proje şablonu tek tek projelerinde adlarında atanamaz **yeni proje** iletişim kutusu. Bunun yerine, kullanın `ProjectName` özniteliği `ProjectTemplateLink` öğesi .vstemplate dosyasında her proje için bir ad belirtin.

- Birden çok proje şablonu farklı diller için projeleri içerebilir, ancak bir kategorideki tüm şablonu yalnızca içine yerleştirilebilir. Şablon kategorisinde belirtin `ProjectType` .vstemplate dosyasının öğesi.

Birden çok proje şablonu bir .zip dosyasına sıkıştırılmış aşağıdaki öğeleri şunları içermelidir:

- Tüm birden çok proje şablonu için bir kök .vstemplate dosya. Bu kök .vstemplate dosya meta veriler içeriyor, **yeni proje** iletişim kutusu görüntüler ve projeler için .vstemplate dosyaları şablonda nerede bulabileceğini belirtir. Bu dosya .zip dosyasının kök dizininde olması gerekir.

- Tam proje şablonu için gerekli dosyaları içeren iki veya daha çok klasör. Bu proje için tüm kod dosyaları ve proje için .vstemplate dosyası içerir.

Örneğin, iki proje içeren birden çok proje şablonu .zip dosyası, aşağıdaki dosyaları ve dizinleri sahip olabilir:

- MultiProjectTemplate.vstemplate
- \Project1\Project1.vstemplate
- \Project1\Project1.vbproj
- \Project1\Class.vb
- \Project2\Project2.vstemplate
- \Project2\Project2.vbproj
- \Project2\Class.vb

Birden çok proje şablonu için kök .vstemplate dosyası tek proje şablondan aşağıdaki yollarla farklıdır:

- `Type` Özniteliği `VSTemplate` öğeye sahip değer `ProjectGroup` yerine `Project`. Örneğin:

    ```xml
    <VSTemplate Version="2.0.0" Type="ProjectGroup"
        xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    ```

- `TemplateContent` Öğesi içeren bir `ProjectCollection` bir veya daha fazla olan öğeyi `ProjectTemplateLink` yolları dahil projelerinin .vstemplate dosyaları tanımlayan öğeleri. Örneğin:

    ```xml
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

## <a name="to-create-a-multi-project-template-from-an-existing-solution"></a>Varolan bir çözümden birden çok proje şablonu oluşturmak için

1. Bir çözüm oluşturmak ve iki veya daha fazla proje ekleyin.

1. Bir şablona aktarılması hazır olana kadar projeleri özelleştirin.

1. Üzerinde **proje** menüsünde seçin **şablonu dışarı aktar...** .

   **Şablonu Dışarı Aktarma Sihirbazı** açar.

1. Üzerinde **şablon türünü seç** sayfasında, **proje şablonu**. Bir şablonu dışarı aktarmak ve ardından istediğiniz projesini seçin **sonraki**.

1. Üzerinde **şablon seçenekleri** sayfasında, bir ad ve isteğe bağlı bir açıklama, simge ve Önizleme görünümü şablonunuz için girin. Seçin **son**.

   Proje bir .zip dosyasına dışarı aktardığınız ve belirtilen çıkış konuma yerleştirilir.

   > [!NOTE]
   > Her proje olmalıdır ayrı ayrı bir şablonu dışarı, bu nedenle önceki adımları çözümdeki her proje için yineleyin.

1. Her proje için bir alt dizin ile şablon için bir dizin oluşturun.

1. Yeni oluşturduğunuz karşılık gelen alt her projenin .zip dosyasının içeriğini ayıklayın.

1. Temel dizinini içeren bir XML dosyası oluşturma bir **.vstemplate** dosya uzantısı. Bu dosya, birden çok proje şablonu için meta veriler içeriyor. Dosya yapısı için aşağıdaki örneğe bakın. Her projenin .vstemplate dosya için göreli yol belirttiğinizden emin olun.

1. Temel dizini seçin ve sağ tıklatın veya bağlam menüsünden **göndermek** > **sıkıştırılmış (daraltılmış) klasör**.

   Dosya ve klasörlerin bir .zip dosyasına sıkıştırılır.

1. .Zip dosyasını kullanıcı proje şablonu dizinine kopyalayın. Varsayılan olarak, bu %USERPROFILE%\Documents\Visual Studio dizindir \<sürüm\>\Templates\ProjectTemplates.

1. Visual Studio'da açın **yeni proje** iletişim kutusu ve şablonunuzu göründüğünü doğrulayın.

## <a name="two-project-example"></a>İki proje örneği

Bu örnek, bir temel birden çok proje kök .vstemplate dosyası gösterir. Bu örnekte, iki proje şablonu içeren `My Windows Application` ve `My Class Library`. `ProjectName` Özniteliği `ProjectTemplateLink` öğe projeye verilen adını belirtir.

> [!TIP]
> Varsa `ProjectName` özniteliği belirtilmezse, .vstemplate dosyasının adı proje adı olarak kullanılır.

```xml
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

## <a name="example-with-solution-folders"></a>Çözüm klasörleri örnekle

Bu örnekte `SolutionFolder` projeleri iki gruplara ayırmak için öğesi `Math Classes` ve `Graphics Classes`. Şablon ikisi her çözüm klasörüne yerleştirilir dört projeleri içerir.

```xml
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

## <a name="see-also"></a>Ayrıca bkz.

[Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)  
[Nasıl yapılır: Proje şablonları oluşturma](../ide/how-to-create-project-templates.md)  
[Visual Studio Şablon Şeması Başvurusu (genişletilebilirliği)](../extensibility/visual-studio-template-schema-reference.md)  
[SolutionFolder öğesi (Visual Studio şablonları)](../extensibility/solutionfolder-element-visual-studio-templates.md)  
[ProjectTemplateLink öğesi (Visual Studio şablonları)](../extensibility/projecttemplatelink-element-visual-studio-templates.md)
