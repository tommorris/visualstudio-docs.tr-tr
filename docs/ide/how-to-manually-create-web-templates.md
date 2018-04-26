---
title: Visual Studio için Web şablonları oluşturma
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio templates, Web
- templates [Visual Studio], Web
- Web templates [Visual Studio]
- project templates [Visual Studio], Web
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: aeaeea5ee4d1d8e65cdc13ca11192a70e0459be1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-manually-create-web-templates"></a>Nasıl yapılır: web şablonlarını elle oluşturma

Bir web şablonu oluşturma şablonları diğer tür oluşturmaktan daha farklıdır. Web projesi şablonları görünür olduğundan **yeni Web sitesi Ekle** iletişim kutusu ve programlama diline göre öğe kategorilere ayrılmış web projesi *vstemplate* dosya şablon web şablon olarak belirtmeniz gerekir ve programlama dilini tanımlar.

> [!NOTE]
> Web şablonları, boş bir içermelidir *.webproj* dosya ve onu gerekir başvuruda bulunulamıyor *vstemplate* dosyasını `File` özniteliği `Project` öğesi. Web projeleri gerektirmez rağmen bir *.proj* proje dosyası, düzgün çalışabilmesi web şablonu için bu saplama dosyası oluşturmak için gerekli.

## <a name="to-manually-create-a-web-template"></a>El ile bir web şablonu oluşturmak için

1. Bir web projesi oluşturun.

1. Değiştirin veya projenin dosyaları silin veya yeni dosyalar projeye ekleyin.

1. Bir XML dosyası oluşturun ve onunla kaydedin bir *vstemplate* projenizi ile aynı dizinde dosya adı uzantısı. Visual Studio'da projeye eklemeyin.

1. Düzen *vstemplate* proje şablonu meta verilerini sağlamak için XML dosyası. Daha fazla bilgi için bkz: [aşağıdaki örnek](#example).

1. Bulun `ProjectType` öğesinde *vstemplate* dosya ve metin değeri `Web`.

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

1. Şablonunuzda dosyaları seçin (Bu içerir *vstemplate* dosyası), seçime sağ tıklayın ve seçin **göndermek** > **sıkıştırılmış (daraltılmış) klasör**. Dosyalar halinde sıkıştırılmış bir *.zip* dosyası.

1. PUT *.zip* Visual Studio Proje şablonu dizininde şablon dosyası. Varsayılan olarak, bu dizindir *%USERPROFILE%\Documents\Visual Studio \<sürüm\>\ProjectTemplates*.

## <a name="example"></a>Örnek

Aşağıdaki örnek, temel bir gösterir *vstemplate* dosyası bir web projesi şablonu için:

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

- [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)
- [Visual Studio Şablon Şeması Başvurusu (genişletilebilirliği)](../extensibility/visual-studio-template-schema-reference.md)