---
title: Visual Studio için çok dosyalı öğe şablonları oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 01/02/2018
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio templates, creating multi-file item templates
- multi-file item templates
- item templates, creating multi-file item templates
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: fc494f7fa3134984ccb2330e835332fb3e711c19
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-create-multi-file-item-templates"></a>Nasıl yapılır: çok dosyalı öğe şablonları oluşturma

Öğe şablonları yalnızca bir öğe belirtebilirsiniz, ancak bazen öğesi birden fazla dosyadan oluşur. Örneğin, bir Windows Forms öğesi şablonu aşağıdaki üç dosyalar gerektirir:

- Form kodunu içeren bir dosya

- Form için tasarımcı bilgileri içeren bir dosya

- Form için gömülü kaynaklar içeren bir dosya

Çok dosyalı öğe şablonları öğesi oluşturulduğunda doğru dosya uzantılarını kullanılmasını sağlamak için parametreleri gerektirir. Kullanarak bir çok dosyalı öğe şablonu oluşturursanız **şablonu Dışarı Aktarma Sihirbazı**bu parametreleri otomatik olarak oluşturulur ve başka düzenleme gereklidir.

## <a name="to-create-a-multi-file-item-template-by-using-the-export-template-wizard"></a>Şablonu Dışarı Aktarma Sihirbazı'nı kullanarak çok dosyalı öğe şablonu oluşturmak için

Tek Dosyalı öğe şablonu olduğu gibi aynı şekilde çok dosyalı öğe şablonu oluşturabilirsiniz. Bkz: [nasıl yapılır: öğe şablonları oluşturma](../ide/how-to-create-item-templates.md). Üzerinde **vermek öğesi seçin** Sayfa Sihirbazı'nın bağımlı dosyaları (örneğin, bir Windows Forms form) sahip bir dosya seçin. Sihirbaz otomatik olarak şablonda tasarımcı ve kaynak dosyaları gibi tüm bağımlı dosyaları içerir.

## <a name="to-manually-create-a-multi-file-item-template"></a>Çok dosyalı öğe şablonu el ile oluşturmak için

1. El ile tek dosyalı öğe şablonu oluşturun, ancak çok dosyalı öğe oluşturduğunu her dosyayı eklemek gibi öğe şablonu oluşturun.

1. İçinde *.vstemplate* XML dosyasında, ekleme bir `ProjectItem` öğesi her kişi için dosya ve ekleme bir `TargetFileName` özniteliği bu öğeye. Değerini `TargetFileName` özniteliğini *$fileinputname$. FileExtension*, burada *FileExtension* şablona dahil dosyasının dosya uzantısıdır. Örneğin:

    ```xml
    <ProjectItem TargetFileName="$fileinputname$.vb">
        Form1.vb
    </ProjectItem>
    <ProjectItem TargetFileName="$fileinputname$.Designer.vb">
        Form1.Designer.vb
    </ProjectItem>
    <ProjectItem TargetFileName="$fileinputname$.resx">
        Form1.resx
    </ProjectItem>
    ```

     > [!NOTE]
     > Bu şablondan türetilen bir öğe projeye eklendiğinde, dosya adları, kullanıcının girdiği adından elde **Yeni Öğe Ekle** iletişim kutusu.

1. Şablonunuzda eklenmesi, seçime sağ tıklayın ve seçin dosyaları seçin **göndermek** > **sıkıştırılmış (daraltılmış) klasör**.

   Seçtiğiniz dosyalar halinde sıkıştırılmış bir *.zip* dosyası.

1. Kopya *.zip* kullanıcı öğesi şablonu konumu dosyasına. Varsayılan olarak, dizindir *%USERPROFILE%\Documents\Visual Studio \<sürüm\>\Templates\ItemTemplates*. Daha fazla bilgi için bkz: [nasıl yapılır: şablonları bulma ve düzenleme](../ide/how-to-locate-and-organize-project-and-item-templates.md).

1. Visual Studio'yu kapatın ve tekrar açın.

1. Yeni bir proje oluşturun veya var olan bir projeyi açın ve ardından **proje** > **Yeni Öğe Ekle** veya basın **Ctrl** +  **Shift**+**A**.

   Çok dosyalı öğe şablonu görünür **Yeni Öğe Ekle** iletişim kutusu.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir Windows Forms şablon gösterir. Bir öğe bu şablona dayalı olarak oluşturulduğunda oluşturulan üç dosyaların adlarını girdiğiniz ad ile eşleşir **Yeni Öğe Ekle** iletişim kutusu.

```xml
<VSTemplate Version="2.0.0" Type="Item"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>Multi-file Item Template</Name>
        <Icon>Icon.ico</Icon>
        <Description>An example of a multi-file item template</Description>
        <ProjectType>VisualBasic</ProjectType>
    </TemplateData>
    <TemplateContent>
        <ProjectItem TargetFileName="$fileinputname$.vb" SubType="Form">
            Form1.vb
        </ProjectItem>
        <ProjectItem TargetFileName="$fileinputname$.Designer.vb">
            Form1.Designer.vb
        </ProjectItem>
        <ProjectItem TargetFileName="$fileinputname$.resx">
            Form1.resx
        </ProjectItem>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>Ayrıca bkz.

[Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)  
[Nasıl yapılır: öğe şablonları oluşturma](../ide/how-to-create-item-templates.md)  
[Şablon parametreleri](../ide/template-parameters.md)  
[Nasıl yapılır: şablonda parametreleri ikame etme](../ide/how-to-substitute-parameters-in-a-template.md)