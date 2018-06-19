---
title: Visual Studio şablonları düzenleme
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- project templates [Visual Studio], locations
- item templates [Visual Studio], locations
- template locations [Visual Studio]
- Visual Studio templates, organizing
- templates [Visual Studio], organizing
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 65d4940e7a7969fe28fe115ec7ef42cfdc645c9a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31948736"
---
# <a name="how-to-locate-and-organize-project-and-item-templates"></a>Nasıl yapılır: Proje ve öğe şablonları bulma ve düzenleme

Şablon dosyalarını yerleştirildiğinde, Visual Studio şablonları görünmesi için tanıdığı bir konumda **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları. Kullanıcı şablonu konumda özel alt kategoriler de oluşturabilirsiniz ve kategorileri gösterilen **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları.

## <a name="locate-templates"></a>Şablonları bulun

Yüklü Şablonlar ve kullanıcı şablonları iki farklı konumda depolanır.

### <a name="user-templates"></a>Kullanıcı Şablonları

Sıkıştırılmış eklerseniz (*.zip*) içeren dosyaya bir *.vstemplate* kullanıcı şablonu dizini şablon dosyasına görünür **yeni proje** veya  **Yeni Öğe Ekle** iletişim kutusu. Kullanıcı şablonları varsayılan olarak bulunur:

- *%USERPROFILE%\Documents\Visual studio \<sürüm\>\Templates\ProjectTemplates*

- *%USERPROFILE%\Documents\Visual studio \<sürüm\>\Templates\ItemTemplates*

Örneğin, şu dizine kullanıcı proje şablonları C# ' ta sahiptir:

- *C:\Users\UserName\Documents\Visual Studio 2017\Templates\ProjectTemplates\Visual C#*

> [!TIP]
> Kullanıcı şablonlarında konumunu ayarlayabilirsiniz **Araçları** > **seçenekleri** > **projeler ve çözümler**  >   **Konumları**.

### <a name="installed-templates"></a>Yüklü Şablonlar

Varsayılan olarak, Visual Studio ile yüklü şablonlar içinde bulunur:

- *\\< VisualStudioInstallationDirectory\>\Common7\IDE\ItemTemplates\\< programlama dili\>\\<Locale ID>*

- *\\< VisualStudioInstallationDirectory\>\Common7\IDE\ProjectTemplates\\< programlama dili\>\\<Locale ID>*

Örneğin, şu dizine (LCID 1033) İngilizce için Visual Basic öğe şablonları vardır:

- *C:\\< VisualStudioInstallationDirectory\>\Common7\IDE\ItemTemplates\VisualBasic\1033*

## <a name="organize-templates"></a>Şablonları düzenleme

Kategorileri **yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları yüklü şablon ve kullanıcı şablonu konumlarda mevcut dizin yapıları yansıtır. Kullanıcı şablonları kendi kullanıcı şablon dizinine yeni klasörler ekleyerek kategorilere ayrılabilir. **Yeni proje** ve **Yeni Öğe Ekle** iletişim kutuları, kullanıcı şablon kategorileri için yaptığınız herhangi bir değişiklik gösterir.

> [!NOTE]
> Yeni bir kategori programlama dili düzeyinde oluşturulamıyor. Yeni kategoriler yalnızca her bir dilin oluşturulabilir.

### <a name="to-create-new-user-project-template-categories"></a>Proje şablonu kategorileri yeni kullanıcı oluşturmak için

1. Kullanıcı proje şablonu dizini programlama dili klasöründe bir klasör oluşturun. Örneğin, kurmak için bir **HelloWorld** kategorisi için C# proje şablonları, aşağıdaki dizin oluştur:

    - *\%USERPROFILE%\Documents\Visual Studio \<sürüm\>\Templates\ProjectTemplates\Visual C# \HelloWorld*

1. Bu kategori için tüm şablonları bu yeni klasöre yerleştirin.

1. Üzerinde **dosya** menüsünde seçin **yeni** > **proje**.

   **HelloWorld** kategori görünür **yeni proje** iletişim kutusunda **yüklü** > **Visual C#**.

### <a name="to-create-new-user-item-template-categories"></a>Yeni kullanıcı öğesi şablon kategorileri oluşturmak için

1. Kullanıcı öğesi şablonu dizini programlama dili klasöründe bir klasör oluşturun. Örneğin, kurmak için bir **HelloWorld** kategorisi için C# öğe şablonları, aşağıdaki dizin oluştur:

    - *\%USERPROFILE%\Documents\Visual Studio \<sürüm\>\Templates\ItemTemplates\Visual C# \HelloWorld*

1. Bu kategori için tüm şablonları bu yeni klasöre yerleştirin.

1. Bir proje oluşturun veya varolan projeyi açın. Ardından **proje** menüsünde seçin **Yeni Öğe Ekle**.

   **HelloWorld** kategori görünür **Yeni Öğe Ekle** iletişim kutusunda **yüklü** > **Visual C# öğeleri**.

### <a name="display-templates-in-parent-categories"></a>Üst kategorilerdeki görüntüleme şablonları

Alt kategorileri kullanarak kendi üst kategori görüntülenecek şablonlarında etkinleştirebilirsiniz `NumberOfParentCategoriesToRollUp` öğesinde *.vstemplate* dosya. Bu adımları proje şablonları ve öğe şablonları için aynıdır.

#### <a name="to-display-templates-in-parent-categories"></a>Üst kategorilerdeki şablonları görüntülemek için

1. Bulun *.zip* şablonu içeren dosya.

1. Extract *.zip* dosyası.

1. Açık *.vstemplate* dosyasını Visual Studio'da.

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

1. Kaydet ve Kapat *.vstemplate* dosya.

1. Şablonunuzda dosyaları seçin, seçime sağ tıklayın ve **göndermek** > **sıkıştırılmış (daraltılmış) klasör**.

   Dosyalar halinde sıkıştırılmış bir *.zip* dosyası.

1. Ayıklanan şablon dosyalarını ve eski şablonu silmek *.zip* dosyası.

1. Yeni put *.zip* silinen vardı dizindeki dosyayı *.zip* dosyası.

## <a name="see-also"></a>Ayrıca bkz.

- [Şablonları özelleştirme](../ide/customizing-project-and-item-templates.md)
- [Visual Studio Şablon Şeması Başvurusu (genişletilebilirliği)](../extensibility/visual-studio-template-schema-reference.md)
- [NumberOfParentCategoriesToRollUp (Visual Studio şablonları)](../extensibility/numberofparentcategoriestorollup-visual-studio-templates.md)
- [Nasıl yapılır: Proje şablonları oluşturma](../ide/how-to-create-project-templates.md)
- [Nasıl yapılır: öğe şablonları oluşturma](../ide/how-to-create-item-templates.md)