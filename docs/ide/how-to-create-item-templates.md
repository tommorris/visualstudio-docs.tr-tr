---
title: Visual Studio için öğe şablonları oluşturma
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- item templates [Visual Studio], creating
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 342b7ebd17280c47296fae43c6541a5e969ad5f3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-item-templates"></a>Nasıl yapılır: öğe şablonları oluşturma

Bu makalede kullanarak bir öğe şablonu oluşturmak gösterilmiştir **şablonu Dışarı Aktarma Sihirbazı**. Şablonunuzu birden çok dosya oluşacak olup [nasıl yapılır: çok dosyalı öğe şablonları oluşturma](../ide/how-to-create-multi-file-item-templates.md).

## <a name="to-add-a-user-item-template-to-the-add-new-item-dialog-box"></a>Yeni Öğe Ekle iletişim kutusu için bir kullanıcı öğesi şablonu eklemek için

1. Projesi oluşturun veya bir Visual Studio'da açın.

1. Projeye bir öğe ekleyin ve isterseniz değiştirin.

1. Parametre değiştirme burada gerçekleşeceğini belirtmek için kod dosyasını değiştirin. Daha fazla bilgi için bkz: [nasıl yapılır: şablonda parametreleri ikame etme](../ide/how-to-substitute-parameters-in-a-template.md).

1. Üzerinde **proje** menüsünde seçin **şablonu dışarı aktar**.

1. Üzerinde **şablon türünü seç** sayfasında, **öğe şablonu**öğeyi içeren projeyi seçin ve ardından **sonraki**.

1. Üzerinde **vermek öğesi seçin** sayfasında, bir şablon oluşturmak ve ardından istediğiniz öğeyi seçin **sonraki**.

1. Üzerinde **seçin öğesi başvurularını** sayfasında, şablona dahil, ve ardından derleme başvurularını seçin **sonraki**.

1. Üzerinde **şablon seçenekleri** sayfa, şablon adı ve isteğe bağlı bir açıklama, simge görüntüsü ve Önizleme görünümü girin ve ardından **son**.

    Şablon dosyaları eklenir bir *.zip* dosya ve sihirbazda belirtilen dizine kopyalanır. Varsayılan konum *%USERPROFILE%\Documents\Visual Studio \<sürüm\>\My dışa aktarılan şablonları*.

1. Seçeneğini seçmediyseniz **otomatik olarak şablon Visual Studio'ya içeri** içinde **şablonu Dışarı Aktarma Sihirbazı**, dışarı aktarılan şablonu bulun. Ardından, kullanıcı öğesi şablon dizinine kopyalayın. Varsayılan konum *%USERPROFILE%\Documents\Visual Studio \<sürüm\>\Templates\ItemTemplates*.

1. Visual Studio'yu kapatın ve tekrar açın.

1. Yeni bir proje oluşturun veya var olan bir projeyi açın ve ardından **proje** > **Yeni Öğe Ekle** veya basın **Ctrl** +  **Shift**+**A**.

   Öğe şablonu görünür **Yeni Öğe Ekle** iletişim kutusu. Açıklama eklediyseniz **şablonu Dışarı Aktarma Sihirbazı**, açıklama iletişim kutusunun sağ tarafında görünür.

## <a name="to-enable-the-item-template-to-be-used-in-a-universal-windows-app-project"></a>Öğe şablonu, bir evrensel Windows uygulaması proje ile kullanılmak üzere etkinleştirmek için

Sihirbaz temel bir şablon oluşturmak için işin çoğunu yapar, ancak birçok durumda el ile değiştirmeniz gerekir. *.vstemplate* şablon verdikten sonra dosya. Örneğin, görünmesi öğe istiyorsanız **Yeni Öğe Ekle** iletişim bir evrensel Windows uygulama projesi için fazladan birkaç adım gerçekleştirmeniz gerekir.

1. Bir öğe şablonu dışarı aktarmak için önceki bölümdeki adımları izleyin.

1. Extract *.zip* oluşturulan ve açık dosya *.vstemplate* dosyasını Visual Studio'da.

1. C# Evrensel Windows projesi için aşağıdaki XML içinde eklemek `<TemplateData>` öğe:

   ```xml
   <TemplateID>Microsoft.CSharp.Class</TemplateID>
   ```

1. Visual Studio'da Kaydet *.vstemplate* dosya ve kapatın.

1. Kopyalama ve yapıştırma *.vstemplate* geri dosya *.zip* dosyası.

     Varsa **dosya Kopyala** seçin iletişim kutusu görüntülenirse, **Kopyala ve Değiştir** seçeneği.

Bir evrensel Windows projesi için bu şablona dayalı bir öğe artık ekleyebilirsiniz **Yeni Öğe Ekle** iletişim kutusu.

## <a name="to-enable-templates-for-specific-project-subtypes"></a>Belirli bir proje alt türleri için şablonlar etkinleştirmek için

Şablonunuz için yalnızca belirli proje alt türleri, Windows, Office, veritabanı veya Web gibi yalnızca görünmelidir belirtebilirsiniz.

1. Bulun `ProjectType` öğesinde *.vstemplate* öğesi şablon dosyası.

1. Ekleme bir [ProjectSubType](../extensibility/projectsubtype-element-visual-studio-templates.md) öğesi hemen sonra `ProjectType` öğesi.

1. Öğesinin metin değeri aşağıdaki değerlerden birine ayarlayın:

    - Windows
    - Office
    - Veritabanı
    - Web

Örneğin: `<ProjectSubType>Database</ProjectSubType>`.

Aşağıdaki örnek, bir öğe şablonu için gösterir **Office** projeleri.

```xml
<VSTemplate Version="2.0.0" Type="Item" Version="2.0.0">
   <TemplateData>
      <Name>Class</Name>
      <Description>An empty class file</Description>
      <Icon>Class.ico</Icon>
      <ProjectType>CSharp</ProjectType>
      <ProjectSubType>Office</ProjectSubType>
      <DefaultName>Class.cs</DefaultName>
   </TemplateData>
   <TemplateContent>
      <ProjectItem>Class1.cs</ProjectItem>
   </TemplateContent>
</VSTemplate>
```

## <a name="to-manually-create-an-item-template-without-using-the-export-template-wizard"></a>Şablonu Dışarı Aktar Sihirbazı'nı kullanmadan bir öğe şablonu el ile oluşturmak için

Bazı durumlarda bir öğe şablonu sıfırdan el ile oluşturmak isteyebilirsiniz.

1. Proje ve proje öğesi oluşturun.

1. Bir şablon olarak kaydedilecek hazır olana kadar proje öğesi değiştirin.

1. Parametre değiştirme, varsa herhangi bir yere gerçekleştiği belirtmek için kod dosyasını değiştirin. Parametre değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: şablonda parametreleri ikame etme.](../ide/how-to-substitute-parameters-in-a-template.md)

1. Bir XML dosyası oluşturun ve onunla kaydedin bir *.vstemplate* proje öğesi dosyası ile aynı dizinde dosya uzantısı.

1. Düzen *.vstemplate* öğesi şablon meta verilerini sağlamak için XML dosyası. Daha fazla bilgi için bkz: [Şablon Şeması Başvurusu (genişletilebilirlik)](../extensibility/visual-studio-template-schema-reference.md) ve önceki bölümdeki örnek.

1. Kaydet *.vstemplate* dosya ve kapatın.

1. İçinde **Windows Explorer**, şablonunuzda dahil etmek istediğiniz dosyaları seçin. Seçime sağ tıklayın ve seçin **göndermek** > **sıkıştırılmış (daraltılmış) klasör**. Seçtiğiniz dosyalar halinde sıkıştırılmış bir *.zip* dosyası.

1. Kopya *.zip* dosya ve kullanıcı öğesi şablonu konumda yapıştırın. Visual Studio 2017 ' varsayılan dizinidir *%USERPROFILE%\Documents\Visual Studio 2017\Templates\ItemTemplates*. Daha fazla bilgi için bkz: [nasıl yapılır: Proje ve öğe şablonları bulma ve düzenleme](../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)
- [Nasıl yapılır: çok dosyalı öğe şablonları oluşturma](../ide/how-to-create-multi-file-item-templates.md)
- [Visual Studio Şablon Şeması Başvurusu (genişletilebilirliği)](../extensibility/visual-studio-template-schema-reference.md)
