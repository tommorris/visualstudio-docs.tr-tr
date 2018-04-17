---
title: Araç kutusu, HTML sekmesi | Microsoft Docs
ms.custom: ''
ms.date: 06/21/2017
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.toolbox.html
helpviewer_keywords:
- Toolbox, HTML tab
- HTML Designer, setting options
- HTML tab in Toolbox
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ff609631cec69e0d32cb74e5857cd3bb8df5ab94
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="toolbox-html-tab"></a>Araç kutusu, HTML sekmesi

**HTML** sekmesi araç, Web sayfalarını ve Web forms kullanışlıdır bileşenleri sağlar. Bu sekme görüntülemek için önce bir belgeyi HTML Tasarımcısı'nda düzenlemek için açın. Üzerinde **Görünüm** menüsünde tıklatın **araç**ve ardından **HTML** araç sekmesinde.

 Bir aracı örneği oluşturmak için **HTML** sekmesinde ya da çift aracın belgenizi geçerli ekleme noktası eklemek veya Aracı'nı seçin ve düzenleme yüzey üzerinde istenen konuma sürükleyin.

## <a name="ui-elements"></a>Kullanıcı Arabirimi öğeleri

Aşağıdaki araçlar varsayılan HTML sekmesinde bulunur.

**İşaretçi**

![ASP.NET Mobil Tasarımcı HTMLsayfası işaretçi](../../ide/reference/media/vxpointer.gif "vxPointer")

Herhangi bir araç kutusu sekmesini açar, bu aracın varsayılan olarak seçilir. Silinemiyor. İşaretçinin nesneleri Tasarım görünümü yüzeyine sürükleyin, onları yeniden boyutlandırabilir ve onları sayfa ya da form üzerinde yeniden konumlandırmak etkinleştirir. Daha fazla bilgi için bkz: [araç](../../ide/reference/toolbox.md).

**Giriş (düğme)**

![HTML web sayfasının düğmesini](../../ide/reference/media/vxbutton.gif "vxButton")

Ekler bir `input` öğesinin `type="button"`. Görüntülenen metni değiştirmek için Düzenle `name` özelliği. Varsayılan olarak, `id="Button1"` ilk düğmesi için eklenen `id="Button2"` ikinci vb. için.

Sürüklediğinizde **giriş (düğme)** Tasarım görünümü yüzeyine belgenize HTML biçimlendirmesi aşağıdaki gibi eklenir:

```html
<input id="Button1" type="button" value="Button" name="Button1">
```

**Giriş (Sıfırla)**

![HTMLpageResetButton ekran görüntüsü](../../ide/reference/media/vxreset.gif "vxReset")

Ekler bir `input` öğesinin `type="reset"`. Görüntülenen metni değiştirmek için Düzenle `name` özelliği. Varsayılan olarak, `id="Reset1"` ilk Sıfırla düğmesi, için eklenen `id="Reset2"` ikinci vb. için.

Sürüklediğinizde **giriş (Sıfırla)** Tasarım görünümü yüzeyine belgenize HTML biçimlendirmesi aşağıdaki gibi eklenir:

```html
<input id="Reset1" type="reset" value="Reset" name="Reset1">
```

**Giriş (Gönder)**

![HTMLpageToolbarSubmitButton ekran görüntüsü](../../ide/reference/media/vxsubmit.gif "vxSubmit")

Ekler bir `input` öğesinin `type="submit"`. Görüntülenen metni değiştirmek için Düzenle `name` özelliği. Varsayılan olarak, `id="Submit1"` için ilk gönderme düğmesi, eklenen `id="Submit2"` ikinci vb. için.

Sürüklediğinizde **giriş (Gönder)** Tasarım görünümü yüzeyine belgenize HTML biçimlendirmesi aşağıdaki gibi eklenir:

```html
<input id="Submit1" type="submit" value="Submit" name="Submit1">
```

**Girişi (metin)**

![HTMLpageToolbarTextField ekran görüntüsü](../../ide/reference/media/vxtextfield.gif "vxTextfield")

Ekler bir `input` öğesinin `type="text"` belgenize. Görüntülenen varsayılan metni değiştirmek için Düzenle `value` özniteliği. Varsayılan olarak, `id="Text1"` ilk metin alanı için eklenen `id="Text2"` ikinci vb. için.

Sürüklediğinizde **girişi (metin)** Tasarım görünümü yüzeyine belgenize HTML biçimlendirmesi aşağıdaki gibi eklenir:

```html
<input id="Text1" TYPE="text" value="Text Field" name="Text1">
```

> [!IMPORTANT]
>Tüm kullanıcı girişi doğrulamanız önerilir. Daha fazla bilgi için bkz: [ASP.NET Web sayfaları (Razor) siteleri uygulamasında kullanıcı girdisi doğrulama](/aspnet/web-pages/overview/ui-layouts-and-themes/validating-user-input-in-aspnet-web-pages-sites).

**Giriş (dosya)**

![HTML sayfası dosya alanı](../../ide/reference/media/vxfilefield.gif "vxFilefield")

Ekler bir `input` öğesinin `type="file"` belgenize. Varsayılan olarak, `id="File1"` ilk dosya alanı için eklenen `id="File2"` ikinci vb. için.

Sürüklediğinizde **giriş (dosya)** Tasarım görünümü yüzeyine belgenize HTML biçimlendirmesi aşağıdaki gibi eklenir:

```html
<input id="File1" type="file" name="File1">
```

> [!IMPORTANT]
> Tüm kullanıcı girişi doğrulamanız önerilir. Daha fazla bilgi için bkz: [ASP.NET Web sayfaları (Razor) siteleri uygulamasında kullanıcı girdisi doğrulama](/aspnet/web-pages/overview/ui-layouts-and-themes/validating-user-input-in-aspnet-web-pages-sites).

**Giriş (parola)**

![Visual Studio parola alanı](../../ide/reference/media/vxpassword.gif "vxPassword")

Ekler bir `input` öğesinin `type="password"`. Varsayılan olarak, `id="Password1"` ilk parola alanı için eklenen `id="Password2"` ikinci vb. için.

Sürüklediğinizde **giriş (parola)** Tasarım görünümü yüzeyine belgenize HTML biçimlendirmesi aşağıdaki gibi eklenir:

```html
<input id="Password1" type="password" name="Password1">
```

> [!IMPORTANT]
> Uygulamanızın kullanıcı adları ve parolalar gönderiyorsa, Web sitenizi iletim şifrelemek için Güvenli Yuva Katmanı (SSL) kullanmak üzere yapılandırmanız gerekir. Daha fazla bilgi için bkz: "Bağlantıları SSL ile güvenli hale getirme" [IIS Operations Guide](http://go.microsoft.com/fwlink/?linkid=47856). Ayrıca, tüm kullanıcı girişi doğrulamanız önerilir. Daha fazla bilgi için bkz: [ASP.NET Web sayfaları (Razor) siteleri uygulamasında kullanıcı girdisi doğrulama](/aspnet/web-pages/overview/ui-layouts-and-themes/validating-user-input-in-aspnet-web-pages-sites).

**Giriş (onay kutusu)**

![HTML Web sayfası araç kutusu onay kutusu seçeneği](../../ide/reference/media/vxcheckbox.gif "vxCheckbox")

Ekler bir `input` öğesinin `type="checkbox"`. Görüntülenen metni değiştirmek için Düzenle `name` özelliği. Varsayılan olarak, `id="Checkbox1"` ilk onay kutusu için eklenen `id="Checkbox2"` ikinci vb. için.

Sürüklediğinizde **giriş (onay kutusu)** Tasarım görünümü yüzeyine belgenize HTML biçimlendirmesi aşağıdaki gibi eklenir:

```html
<input id="Checkbox1" type="checkbox" name="Checkbox1">
```

**Giriş (radyo)**

![VisualStudioHTMLpageRadioButton ekran görüntüsü](../../ide/reference/media/vxradio.gif "vxRadio")

Ekler bir `input` öğesinin `type="radio"`. Görüntülenen metni değiştirmek için Düzenle `name` özelliği. Varsayılan olarak, `id="Radio1"` ilk radyo düğmesi için eklenen `id="Radio2"` ikinci vb. için.

Sürüklediğinizde **giriş (radyo)** Tasarım görünümü yüzeyine belgenize HTML biçimlendirmesi aşağıdaki gibi eklenir:

```html
<input id="Radio1" type="radio" name="Radio1">
```

**Giriş (gizli)**

![HTML sayfası gizli öğe](../../ide/reference/media/vxhidden.gif "vxhidden")

Ekler bir `input` öğesinin `type="hidden"`. Varsayılan olarak, `id="Hidden1"` ilk gizli alan için eklenen `id="Hidden2"` ikinci vb. için.

Sürüklediğinizde **giriş (gizli)** Tasarım görünümü yüzeyine belgenize HTML biçimlendirmesi aşağıdaki gibi eklenir:

```html
<input id="Hidden1" type="hidden" name="Hidden1">
```

**TextArea**

![HTMLsayfası araç çubuğu metin alanı](../../ide/reference/media/vxtextarea.gif "vxTextarea")

Ekler bir `textarea` öğesi. Metin alanını yeniden boyutlandırın veya genişletir metin, görüntü alanını görüntülemek için kendi kaydırma çubuklarını kullanın. Görüntülenen varsayılan metni değiştirmek için Düzenle `value` özniteliği. Varsayılan olarak, `id="textarea1"` olan ilk metin alanı eklenen `id=" textarea 2"` ikinci vb. için.

Sürüklediğinizde **Textarea** Tasarım görünümü yüzeyine belgenize HTML biçimlendirmesi aşağıdaki gibi eklenir:

```html
<textarea id=" textarea 1 name=" textarea 1" rows=2 cols=20></textarea> 
```

> [!IMPORTANT]
> Tüm kullanıcı girişi doğrulamanız önerilir. Daha fazla bilgi için bkz: [ASP.NET Web sayfaları (Razor) siteleri uygulamasında kullanıcı girdisi doğrulama](/aspnet/web-pages/overview/ui-layouts-and-themes/validating-user-input-in-aspnet-web-pages-sites).

**Tablo**

![HTMLpageToolbarTable ekran görüntüsü](../../ide/reference/media/vxtable.gif "vxTable")

Ekler bir `table` öğesi.

Sürüklediğinizde **tablo** Tasarım görünümü yüzeyine belgenize HTML biçimlendirmesi aşağıdaki gibi eklenir:

```html
<table cellspacing="1" width="75%" border=1> <tr><td></td></tr></table> 
```

**Görüntü**

![HTML sayfası resim öğesi](../../ide/reference/media/vximage.gif "vxImage")

Ekler bir `img` öğesi. Belirtmek için bu öğe Düzenle kendi `src` ve kendi `alt` metin.

Sürüklediğinizde **görüntü** Tasarım görünümü yüzeyine belgenize HTML biçimlendirmesi aşağıdaki gibi eklenir:

```html
<img alt="" src="">
```

**seçin**

![HTML sayfası araç kutusu açılan kutu](../../ide/reference/media/vxdropdown.gif "vxDropdown")

Bir açılır ekler `select` öğesi (olmadan bir `size` özniteliği). Varsayılan olarak, `id="select1"` ilk liste kutusu için eklenen `id="select2"` ikinci vb. için.

Sürüklediğinizde **seçin** Tasarım görünümü yüzeyine belgenize HTML biçimlendirmesi aşağıdaki gibi eklenir:

```html
<select id="select1" name="select1"><option selected></option></select>
```

Çok satırlı oluşturabilirsiniz `select` boyut özelliğinin değerini artırarak öğesi.

**Yatay çizgi**

![HTML sayfası Yatay kural öğesi](../../ide/reference/media/vxhorizontal.gif "vxHorizontal")

Ekler bir `hr` öğesi. Çizgi kalınlığını artırmak için düzenleme `size` özniteliği.

Sürüklediğinizde **yatay çizgi** Tasarım görünümü yüzeyine belgenize HTML biçimlendirmesi aşağıdaki gibi eklenir:

```html
<hr width="100%" size=1>
```

**div**

![HTML sayfası etiketi](../../ide/reference/media/vxlabel.gif "vxLabel")

Ekler bir `div` içeren öğesi bir `ms_positioning="FlowLayout"` özniteliği. Genişlik ve yükseklik dışında bu öğe bir akış düzeni paneline aynıdır. İçinde bulunan metni biçimlendirmek için `div` öğesi ekleme bir `class="stylename"` özniteliği için açılış etiketi.

Sürüklediğinizde **Div** Tasarım görünümü yüzeyine belgenize HTML biçimlendirmesi aşağıdaki gibi eklenir:

```html
<div ms_positioning="FlowLayout" style="width: 70px; position: relative; height: 15px">Label</div>
```

## <a name="see-also"></a>Ayrıca bkz.

[Araç Kutusu](../../ide/reference/toolbox.md)
