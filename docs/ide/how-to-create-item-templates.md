---
title: "Visual Studio için öğe şablonları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: item templates [Visual Studio], creating
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8fd5d7fba092df5accfaad9d26cfc05f196981ba
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2018
---
# <a name="how-to-create-item-templates"></a>Nasıl yapılır: öğe şablonları oluşturma

Bu konuda kullanarak bir öğe şablonu oluşturmak nasıl gösterilmektedir **şablonu Dışarı Aktarma Sihirbazı**. Şablonunuzu birden çok dosya oluşacak olup [nasıl yapılır: çok dosyalı öğe şablonları oluşturma](../ide/how-to-create-multi-file-item-templates.md).

## <a name="to-add-a-user-item-template-to-the-add-new-item-dialog-box"></a>Yeni Öğe Ekle iletişim kutusu için bir kullanıcı öğesi şablonu eklemek için

1. Projesi oluşturun veya bir Visual Studio'da açın.

1. Projeye bir öğe ekleyin ve isterseniz değiştirin.

1. Parametre değiştirme burada gerçekleşeceğini belirtmek için kod dosyasını değiştirin. Daha fazla bilgi için bkz: [nasıl yapılır: şablonda parametreleri ikame etme](../ide/how-to-substitute-parameters-in-a-template.md).

1. Üzerinde **proje** menüsünde seçin **şablonu dışarı aktar...** .

1. Üzerinde **şablon türünü seç** sayfasında, **öğe şablonu**öğeyi içeren projeyi seçin ve ardından **sonraki**.

1. Üzerinde **vermek öğesi seçin** sayfasında, bir şablon oluşturmak ve ardından istediğiniz öğeyi seçin **sonraki**.

1. Üzerinde **seçin öğesi başvurularını** sayfasında, şablona dahil, ve ardından derleme başvurularını seçin **sonraki**.

1. Üzerinde **şablon seçenekleri** sayfa, şablon adı ve isteğe bağlı bir açıklama, simge görüntüsü ve Önizleme görünümü girin ve ardından **son**.

    Şablon dosyalarını bir .zip dosyasına eklendi ve sihirbazda belirtilen dizine kopyalanır. Varsayılan konumu %USERPROFILE%\Documents\Visual Studio: \<sürüm\>\My dışa aktarılan şablonları.

1. Seçeneğini seçmediyseniz **otomatik olarak şablon Visual Studio'ya içeri** içinde **şablonu Dışarı Aktarma Sihirbazı**, dışarı aktarılan şablonu bulun ve kullanıcı öğesi şablon dizinine kopyalayın. Varsayılan konumu %USERPROFILE%\Documents\Visual Studio: \<sürüm\>\Templates\ItemTemplates.

1. Visual Studio'yu kapatın ve tekrar açın.

1. Yeni bir proje oluşturun veya var olan bir projeyi açın ve ardından **proje** > **Yeni Öğe Ekle...**  veya basın **Ctrl** + **Shift** + **A**.

   Öğe şablonu görünür **Yeni Öğe Ekle** iletişim kutusu. Açıklama eklediyseniz **şablonu Dışarı Aktarma Sihirbazı**, açıklama iletişim kutusunun sağ tarafında görünür.

## <a name="to-enable-the-item-template-to-be-used-in-a-universal-windows-app-project"></a>Öğe şablonu, bir evrensel Windows uygulaması proje ile kullanılmak üzere etkinleştirmek için

Sihirbaz temel bir şablon oluşturmak için işin çoğunu yapar ancak birçok durumda şablon verdikten sonra .vstemplate dosyasını el ile değiştirmeniz gerekir. Örneğin, görünmesi öğe istiyorsanız **Yeni Öğe Ekle** iletişim bir evrensel Windows uygulama projesi için fazladan birkaç adım gerçekleştirmeniz gerekir.

1. Bir öğe şablonu dışarı aktarmak için önceki bölümdeki adımları izleyin.

1. Oluşturulan .zip dosyasını ayıklayın ve Visual Studio'da .vstemplate dosyasını açın.

1. C# Evrensel Windows projesi için aşağıdaki XML içinde eklemek `<TemplateData>` öğe:

   ```xml
   <TemplateID>Microsoft.CSharp.Class</TemplateID>
   ```

1. Visual Studio'da .vstemplate dosyayı kaydedin ve kapatın.

1. .Vstemplate dosyasına .zip dosyasını kopyalayıp yeniden açın.

     Varsa **dosya Kopyala** seçin iletişim kutusu görüntülenirse, **Kopyala ve Değiştir** seçeneği.

Bir evrensel Windows projesi için bu şablona dayalı bir öğe artık ekleyebilirsiniz **Yeni Öğe Ekle** iletişim kutusu.

## <a name="to-enable-templates-for-specific-project-subtypes"></a>Belirli bir proje alt türleri için şablonlar etkinleştirmek için

Şablonunuz için yalnızca belirli proje alt türleri, Windows, Office, veritabanı veya Web gibi yalnızca görünmelidir belirtebilirsiniz.

1. ProjectType öğesi öğe şablonu .vstemplate dosyasını bulun.

1. Ekleme bir [ProjectSubType](../extensibility/projectsubtype-element-visual-studio-templates.md) ProjectType öğesi hemen sonra öğesi.

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

## <a name="to-manually-create-an-item-template-without-using-the-export-template-wizard"></a>Şablonu Dışarı Aktarma Sihirbazı'nı kullanmadan bir öğe şablonu el ile oluşturmak için

Bazı durumlarda bir öğe şablonu sıfırdan el ile oluşturmak isteyebilirsiniz.

1. Proje ve proje öğesi oluşturun.

1. Bir şablon olarak kaydedilecek hazır olana kadar proje öğesi değiştirin.

1. Parametre değiştirme, varsa herhangi bir yere gerçekleştiği belirtmek için kod dosyasını değiştirin. Parametre değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: şablonda parametreleri ikame.](../ide/how-to-substitute-parameters-in-a-template.md)

1. Bir XML dosyası oluşturun ve proje öğesi dosyası ile aynı dizinde .vstemplate dosya uzantısıyla kaydedin.

1. Öğe şablon meta verilerini sağlamak için .vstemplate XML dosyasını düzenleyin. Daha fazla bilgi için bkz: [Şablon Şeması Başvurusu (genişletilebilirlik)](../extensibility/visual-studio-template-schema-reference.md) ve önceki bölümdeki örnek.

1. .Vstemplate dosyayı kaydedin ve kapatın.

1. Windows Gezgini'nde, şablona dahil, seçime sağ tıklayın veya seçmek için istediğiniz dosyaları seçin **göndermek** > **sıkıştırılmış (daraltılmış) klasör**. Seçtiğiniz dosyaların bir .zip dosyasına sıkıştırılır.

1. .Zip dosyasını kopyalayın ve kullanıcı öğesi şablonu konumda yapıştırın. Visual Studio 2017 içinde %USERPROFILE%\Documents\Visual Studio 2017\Templates\ItemTemplates varsayılan dizinidir. Daha fazla bilgi için bkz: [nasıl yapılır: bulun ve düzenleme proje ve öğe şablonları](../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="see-also"></a>Ayrıca bkz.

[Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)  
[Nasıl Yapılır: Çok Dosyalı Şablonlar Oluşturma](../ide/how-to-create-multi-file-item-templates.md)  
[Visual Studio Şablon Şeması Başvurusu (genişletilebilirliği)](../extensibility/visual-studio-template-schema-reference.md)
