---
title: 'Nasıl yapılır: Etki Alanına Özgü bir Dilde Standart Menü Komutunu Değiştirme'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- .vsct files, adding commands to a domain-specific language
- Domain-Specific Language, adding custom commands
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: daa44f17fcf0eb61f5c4ce6c1bfada685a20f45e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31951836"
---
# <a name="how-to-modify-a-standard-menu-command-in-a-domain-specific-language"></a>Nasıl yapılır: Etki Alanına Özgü bir Dilde Standart Menü Komutunu Değiştirme

Bazı, DSL otomatik olarak tanımlanan standart komutlar davranışını değiştirebilirsiniz. Örneğin, değiştirebileceği **Kes** böylece hassas bilgileri dışlar. Bunu yapmak için bir komut kümesi sınıftaki yöntemleri geçersiz kılın. Bu sınıfların CommandSet.cs dosyasında DslPackage proje tanımlanan ve türetilmiş <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet>.

> [!NOTE]
> Kendi menü komutlarını oluşturmak istiyorsanız, bkz: [nasıl yapılır: bir komut için kısayol menüsü ekleme](../modeling/how-to-add-a-command-to-the-shortcut-menu.md).

## <a name="what-commands-can-you-modify"></a>Hangi komutların, değişiklik yapabilirsiniz?

### <a name="to-discover-what-commands-you-can-modify"></a>Bulmak için hangi komutları değiştirebilirsiniz

1.  İçinde `DslPackage` proje, açık `GeneratedCode\CommandSet.cs`. Bu C# dosyasına Çözüm Gezgini'nde temsilcisine bulunabilir `CommandSet.tt`.

2.  Sınıflar bu dosyada adları ile biten Bul "`CommandSet`", örneğin `Language1CommandSet` ve `Language1ClipboardCommandSet`.

3.  Her komut kümesi sınıfında yazın "`override`" bir boşluk bırakarak. IntelliSense geçersiz kılabilirsiniz yöntemlerinin listesini gösterir. Her komut adları başlamak yöntemleri çifti olan "`ProcessOnStatus`"ve"`ProcessOnMenu`".

4.  Hangi komutun sınıfları Ayarla Not değiştirmek istediğiniz komutu içerir.

5.  Dosyayı düzenlemeleriniz kaydetmeden kapatın.

    > [!NOTE]
    > Genellikle, oluşturulan dosyaları düzenleme yapmamanız gerekir. Tüm düzenlemeleri oluşturulan dosyaları açtığında kaybolur.

## <a name="extend-the-appropriate-command-set-class"></a>Uygun komut kümesi sınıfını genişletir

Komut kümesi sınıfı kısmi bildirimini içeren yeni bir dosya oluşturun.

### <a name="to-extend-the-command-set-class"></a>Set sınıfı komutu genişletmek için

1.  Çözüm Gezgini'nde, DslPackage proje GeneratedCode klasörünü açın ve CommandSet.tt altında arayın ve oluşturulan dosya CommandSet.cs açın. Ad alanı ve orada tanımlanan ilk sınıfın adını not edin. Örneğin, görebilirsiniz:

     `namespace Company.Language1`

     `{ ...  internal partial class Language1CommandSet : ...`

2.  İçinde **DslPackage**, adında bir klasör oluşturun **özel kod**. Bu klasörde adlı yeni bir sınıf dosyası oluşturma `CommandSet.cs`.

3.  Yeni dosyasında, aynı ad alanına ve oluşturulan kısmi sınıf ada sahip bir kısmi bildirimini yazma. Örneğin:

    ```
    using System;
    using System.Collections.Generic;
    using System.ComponentModel.Design;
    namespace Company.Language1 /* Make sure this is correct */
    { internal partial class Language1CommandSet { ...
    ```

     **Not** yeni dosyası oluşturmak için sınıfı dosya şablonu kullandıysanız, ad alanı ve sınıf adı düzeltmeniz gerekir.

## <a name="override-the-command-methods"></a>Komut yöntemlerini geçersiz kılın

Çoğu komutların ilişkili iki yöntem vardır: bir ad yöntemiyle ister `ProcessOnStatus`... komutu görünür ve etkin olup olmayacağını belirler. Kullanıcı Diyagramı sağ tıklatır her adlı hızla yürütün ve hiçbir değişiklik. `ProcessOnMenu`... kullanıcı komutu tıklar ve komutunun işlevi gerçekleştirmesi gereken zaman çağrılır. Bir ya da bu yöntemlerin her ikisi de geçersiz kılma isteyebilirsiniz.

### <a name="to-change-when-the-command-appears-on-a-menu"></a>Komut bir menüsünde göründüğünde değiştirmek için

ProcessOnStatus... geçersiz kılma yöntemi. Bu yöntem görünür ayarlamanız gerekir ve onun parametresi MenuCommand özelliklerini etkin. Genellikle komutu şu anda arar. Komut seçilen öğeleri için geçerlidir ve ayrıca komut kendi geçerli durumunda uygulanabilir olup olmadığını belirlemek için özellikleri bakmak olup olmadığını belirlemek için CurrentSelection.

Genel bir kılavuz olarak görünür özelliği hangi öğeleri tarafından seçilen belirlenmesi. Komutu siyah veya gri menüsünde görüntülenip görüntülenmeyeceğini belirler, etkin özellik Seçimi geçerli durumuna bağlıdır.

Aşağıdaki örnek kullanıcı birden fazla şekil seçildiğinde Sil menü öğesini devre dışı bırakır.

> [!NOTE]
> Bu yöntem komutu bir tuş vuruşu kullanılabilir olup olmadığını etkilemez. Örneğin, Sil menü öğesini devre dışı bırakma komutunu Delete tuşuyla çağrılan engellemez.

```csharp
/// <summary>
/// Called when user right-clicks on the diagram or clicks the Edit menu.
/// </summary>
/// <param name="command">Set Visible and Enabled properties.</param>
protected override void ProcessOnStatusDeleteCommand (MenuCommand command)
{
  // Default settings from the base method.
  base.ProcessOnStatusDeleteCommand(command);
  if (this.CurrentSelection.Count > 1)
  {
    // If user has selected more than one item, Delete is greyed out.
    command.Enabled = false;
  }
}
```

İyi ilk temel yöntemi çağırmak için tüm durumlarda ve ayarlar ile bir kaygınız ile mücadele etmek için bir uygulamadır.

ProcessOnStatus yöntemi oluşturma, silme veya gerekir deposundaki öğeleri güncelleştirme.

### <a name="to-change-the-behavior-of-the-command"></a>Komut davranışını değiştirmek için

ProcessOnMenu... geçersiz kılma yöntemi. Aşağıdaki örnek, kullanıcının bile Delete tuşunu kullanarak aynı anda birden fazla öğe silmesi engeller.

```csharp
/// <summary>
/// Called when user presses Delete key
/// or clicks the Delete command on a menu.
/// </summary>
protected override void ProcessOnMenuDeleteCommand()
{
  // Allow users to delete only one thing at a time.
  if (this.CurrentSelection.Count <= 1)
  {
    base.ProcessOnMenuDeleteCommand();
  }
}
```

Kod oluşturma, silme veya öğeleri veya bağlantılar, güncelleştirme gibi deposuna değişiklikler yaparsa bir işlem içinde bunu yapmanız gerekir. Daha fazla bilgi için bkz: [oluşturma ve güncelleştirme model öğelerini nasıl](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md).

### <a name="write-the-code-of-the-methods"></a>Yöntemlerin kodunu yazma

Aşağıdaki parçaları bu yöntemleri içinde sık yararlı olur:

-   `this.CurrentSelection`. Kullanıcı sağ şekli şekilleri ve bağlayıcıların bu listede her zaman dahil edilir. Kullanıcı diyagramı boş bir bölümünü tıklarsa, diyagram listesi yalnızca üyesidir.

-   `this.IsDiagramSelected()` - `true` Kullanıcı diyagramı boş bir kısmına tıkladıysanız.

-   `this.IsCurrentDiagramEmpty()`

-   `this.IsSingleSelection()` -Kullanıcı birden çok şekil seçmediğiniz

-   `this.SingleSelection` -Şekil veya kullanıcı sağ diyagramı

-   `shape.ModelElement as MyLanguageElement` -bir şekli tarafından temsil edilen model öğesi.

Nesneler ve bağlantılar oluşturma ve öğesi başka bir öğe gidin hakkında daha fazla bilgi için bkz: [gezinme ve Program kodundaki bir modeli güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md).

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.ComponentModel.Design.MenuCommand>
- [Etki Alanına Özgü Dili Özelleştirmek için Kod Yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md)
- [Nasıl yapılır: Kısayol Menüsüne Komut Ekleme](../modeling/how-to-add-a-command-to-the-shortcut-menu.md)
- [VSPackage’ların Kullanıcı Arabirimi Öğeleri Eklemesi](../extensibility/internals/how-vspackages-add-user-interface-elements.md)
- [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [VSCT XML Şeması Başvurusu](../extensibility/vsct-xml-schema-reference.md)
- [VMSDK - hattı diyagramları örnek. Kapsamlı DSL özelleştirme](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)
- [Örnek kod: hattı diyagramları](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)
