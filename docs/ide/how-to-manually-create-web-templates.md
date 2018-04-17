---
title: Visual Studio için Web şablonları oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 01/02/2018
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio templates, Web
- templates [Visual Studio], Web
- Web templates [Visual Studio]
- project templates [Visual Studio], Web
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: dca5d5439b18fdb377dfe530af81331dd6e5c3fa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-manually-create-web-templates"></a>Nasıl yapılır: Web şablonlarını elle oluşturma

Bir Web şablonu oluşturma şablonları diğer tür oluşturmaktan daha farklıdır. Web projesi şablonları görünür olduğundan **yeni Web sitesi Ekle** iletişim kutusu ve Web proje öğelerini kategorilere ayrılabilir programlama dili tarafından .vstemplate dosyası şablonu Web şablon olarak belirtin ve programlama tanımlayın dili.

> [!NOTE]
> Web şablonları, bir boş .webproj dosyası içermeli ve .vstemplate dosyasında başvurulmalıdır `File` özniteliği `Project` öğesi. Web projeleri gerektirmez rağmen bir. \*proj proje dosyası, düzgün çalışabilmesi Web şablonu için bu saplama dosyası oluşturmak için gerekli.

### <a name="to-manually-create-a-web-template"></a>El ile bir Web şablonu oluşturmak için

1. Bir Web projesi oluşturun.

1. Değiştirin veya projenin dosyaları silin veya yeni dosyalar projeye ekleyin.

1. Bir XML dosyası oluşturun ve projenizin ile aynı dizinde .vstemplate dosya adı uzantısı ile kaydedin. Visual Studio'da projeye eklemeyin.

1. Proje şablonu meta verilerini sağlamak için .vstemplate XML dosyasını düzenleyin. Daha fazla bilgi için bkz: [aşağıdaki örnek](#example).

1. Bulun `ProjectType` .vstemplate dosya ve metin değerini kümesi öğesinde `Web`.

1. Aşağıdaki `ProjectType` öğesi ekleme bir `ProjectSubType` öğesi ve şablon programlama diline metin değeri ayarlayın. Programlama dili aşağıdaki değerlerden biri olabilir:

    - CSharp
    - Visualbasic'tir

    Örneğin:

    ```xml
    <TemplateData>
        ...
        <ProjectType>Web</ProjectType>
        <ProjectSubType>CSharp</ProjectSubType>
        ...
    </TemplateData>
    ```

1. Seçin (Bu içerir .vstemplate dosyası) şablonunuzu dosyalarında seçimi sağ tıklatın ve seçin **göndermek** > **sıkıştırılmış (daraltılmış) klasör**. Dosyalar bir .zip dosyasına sıkıştırılır.

1. .Zip şablon dosyası, Visual Studio Proje şablonu dizininde yerleştirin. Varsayılan olarak, bu %USERPROFILE%\Documents\Visual Studio dizindir \<sürüm\>\ProjectTemplates.

## <a name="example"></a>Örnek

Aşağıdaki örnek bir Web projesi şablonu için bir temel .vstemplate dosyası gösterir:

```xml
<VSTemplate Version="2.0.0" Type="Project"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">>
    <TemplateData>
        <Name>MyWebProjecStarterKit</Name>
        <Description>A simple Web template</Description>
        <Icon>icon.ico</Icon>
        <ProjectType>Web</ProjectType>
        <ProjectSubType>CSharp</ProjectSubType>
        <DefaultName>WebSite</DefaultName>
    </TemplateData>
    <TemplateContent>
        <Project File="WebApplication.webproj">
            <ProjectItem>icon.ico</ProjectItem>
            <ProjectItem OpenInEditor="true">Default.aspx</ProjectItem>
            <ProjectItem>Default.aspx.cs</ProjectItem>
        </Project>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>Ayrıca bkz.

[Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)  
[Visual Studio Şablon Şeması Başvurusu (genişletilebilirliği)](../extensibility/visual-studio-template-schema-reference.md)