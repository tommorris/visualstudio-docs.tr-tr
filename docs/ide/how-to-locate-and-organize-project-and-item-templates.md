---
title: "Visual Studio şablonları düzenlemek | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project templates [Visual Studio], locations
- item templates [Visual Studio], locations
- template locations [Visual Studio]
- Visual Studio templates, organizing
- templates [Visual Studio], organizing
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c58bda5570be9cdb7fba7a8f90a282df7b7167a2
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="how-to-locate-and-organize-project-and-item-templates"></a>Nasıl yapılır: Proje ve öğe şablonları bulma ve düzenleme

Şablon dosyalarını yerleştirildiğinde, Visual Studio şablonları görünmesi için tanıdığı bir konumda **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları. Kullanıcı şablonu konumda özel alt kategoriler de oluşturabilirsiniz ve kategorileri gösterilen **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları.

## <a name="locate-templates"></a>Şablonları bulun

Yüklü Şablonlar ve kullanıcı şablonları iki farklı konumda depolanır.

### <a name="user-templates"></a>Kullanıcı Şablonları

Kullanıcı şablonu dizini .vstemplate dosyasına içeren bir sıkıştırılmış (.zip) dosya eklerseniz, şablon görünür **yeni proje** veya **Yeni Öğe Ekle** iletişim kutusu. Kullanıcı şablonları varsayılan olarak bulunur:

- %USERPROFILE%\Documents\Visual studio \<sürüm\>\Templates\ProjectTemplates

- %USERPROFILE%\Documents\Visual studio \<sürüm\>\Templates\ItemTemplates

Örneğin, şu dizine kullanıcı proje şablonları C# ' ta içerir:

   C:\Users\UserName\Documents\Visual Studio 2017\Templates\ProjectTemplates\Visual C# \

> [!TIP]
> Kullanıcı şablonlarında konumunu ayarlayabilirsiniz **Araçları** > **seçenekleri** > **projeler ve çözümler**  >   **Konumları**.

### <a name="installed-templates"></a>Yüklü Şablonlar

Varsayılan olarak, Visual Studio ile yüklü şablonlar içinde bulunur:

- \\*VisualStudioInstallationDirectory*\Common7\IDE\ItemTemplates\\*programlama dili*\\*yerel ayar kimliği*

- \\*VisualStudioInstallationDirectory*\Common7\IDE\ProjectTemplates\\*programlama dili*\\*yerel ayar kimliği*

Örneğin, aşağıdaki dizin (LCID 1033) İngilizce için Visual Basic öğe şablonları içerir:

   C:\\*VisualStudioInstallationDirectory*\Common7\IDE\ItemTemplates\VisualBasic\1033\

## <a name="organize-templates"></a>Şablonları düzenleme

Kategorileri **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları yüklü şablon ve kullanıcı şablonu konumlarda mevcut dizin yapıları yansıtır. Kullanıcı şablonları kendi kullanıcı şablon dizinine yeni klasörler ekleyerek kategorilere ayrılabilir. **Yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları, kullanıcı şablon kategorileri yaptığınız değişiklikleri yansıtır.

> [!NOTE]
> Yeni bir kategori programlama dili düzeyinde oluşturulamıyor. Yeni kategoriler yalnızca her bir dilin oluşturulabilir.

### <a name="to-create-new-user-project-template-categories"></a>Proje şablonu kategorileri yeni kullanıcı oluşturmak için

1. Kullanıcı proje şablonu dizini programlama dili klasöründe bir klasör oluşturun. Örneğin, kurmak için bir **HelloWorld** kategorisi için C# proje şablonları, aşağıdaki dizin oluştur:

    \%USERPROFILE%\Documents\Visual Studio \<sürüm\>\Templates\ProjectTemplates\Visual C# \HelloWorld\

1. Bu kategori için tüm şablonları bu yeni klasöre yerleştirin.

1. Üzerinde **dosya** menüsünde seçin **yeni** > **proje**.

   **HelloWorld** kategori görünür **yeni proje** iletişim kutusunda **yüklü** > **Visual C#**.

### <a name="to-create-new-user-item-template-categories"></a>Yeni kullanıcı öğesi şablon kategorileri oluşturmak için

1. Kullanıcı öğesi şablonu dizini programlama dili klasöründe bir klasör oluşturun. Örneğin, kurmak için bir **HelloWorld** kategorisi için C# öğe şablonları, aşağıdaki dizin oluştur:

    \%USERPROFILE%\Documents\Visual Studio \<sürüm\>\Templates\ItemTemplates\Visual C# \HelloWorld\

1. Bu kategori için tüm şablonları bu yeni klasöre yerleştirin.

1. Bir proje oluşturun veya varolan projeyi açın. Ardından **proje** menüsünde seçin **Yeni Öğe Ekle**.

   **HelloWorld** kategori görünür **Yeni Öğe Ekle** iletişim kutusunda **yüklü** > **Visual C# öğeleri**.

### <a name="display-templates-in-parent-categories"></a>Üst kategorilerdeki görüntüleme şablonları

Alt kategorileri kullanarak kendi üst kategori görüntülenecek şablonlarında etkinleştirebilirsiniz `NumberOfParentCategoriesToRollUp` .vstemplate dosyasındaki öğesi. Proje şablonları ve öğe şablonları için aşağıdaki adımları aynıdır.

#### <a name="to-display-templates-in-parent-categories"></a>Üst kategorilerdeki şablonları görüntülemek için

1. Şablonu içeren .zip dosyasını bulun.

1. .Zip dosyasını ayıklayın.

1. .Vstemplate dosyasını Visual Studio'da açın.

1. İçinde `TemplateData` öğesi ekleme bir `NumberOfParentCategoriesToRollUp` öğesi. Örneğin, aşağıdaki kodu üst kategori görünür, ancak bundan daha yüksek şablonu sağlar.

    ```xml
    <TemplateData>
        ...
        <NumberOfParentCategoriesToRollUp>
            1
        </NumberOfParentCategoriesToRollUp>
        ...
    </TemplateData>
    ```

1. .vstemplate dosyasını kaydedip kapatın.

1. Şablonunuzda dosyaları seçin, seçime sağ tıklayın ve **göndermek** > **sıkıştırılmış (daraltılmış) klasör**.

   Dosyalar bir .zip dosyasına sıkıştırılır.

1. Ayıklanan şablon dosyalarını ve eski şablonu .zip dosyasını silin.

1. Yeni .zip dosyasını silinen .zip dosyası olan dizinde koyun.

## <a name="see-also"></a>Ayrıca bkz.

[Şablonlarını özelleştirme](../ide/customizing-project-and-item-templates.md)  
[Visual Studio Şablon Şeması Başvurusu (genişletilebilirliği)](../extensibility/visual-studio-template-schema-reference.md)  
[NumberOfParentCategoriesToRollUp (Visual Studio Şablonları)](../extensibility/numberofparentcategoriestorollup-visual-studio-templates.md)  
[Nasıl Yapılır: Proje Şablonları Oluşturma](../ide/how-to-create-project-templates.md)  
[Nasıl Yapılır: Öğe Şablonları Oluşturma](../ide/how-to-create-item-templates.md)
