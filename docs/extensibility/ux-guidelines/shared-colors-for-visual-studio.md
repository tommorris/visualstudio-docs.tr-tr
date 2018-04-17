---
title: Visual Studio için renkleri paylaşılan | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 8d11b9a0-6175-4f2e-8e7f-79daee1bfd41
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b9093eef6166c86eb6e1ffdf602b4fb75841834d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="shared-colors-for-visual-studio"></a>Visual Studio için paylaşılan renkleri
Ortak Visual Studio Kabuğu öğeler kullanan kullanıcı Arabirimi tasarladığınız ya da benzer özellikleri ile tutarlı olacak şekilde arabirimi Öğenizde istediğiniz varolan belirteci adları paket tanımlama dosyaları seçin ve renkleri atamak için kullanın. Bu, kullanıcı Arabirimi ile genel Visual Studio ortamında tutarlı kalmasını ve Temalar eklenen veya güncelleştirilen zaman onu otomatik olarak güncelleştirir sağlar.  

Bu makalede, ortak kullanıcı Arabirimi öğeleri ve benzer UI oluştururken başvuran kullandıkları, belirteç adları açıklanmaktadır. Bu renk belirteçleri erişim hakkında ayrıntılı bilgi için bkz: [VSColor hizmet](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_TheVSColorService).  

Simge adları doğru kullandığınızdan emin olun:  

-   **Renk yer almayan işlevi göre belirteci adları kullanın.** Ortak paylaşılan renkleri belirli arabirim öğeleriyle ilişkilendirilen ve yalnızca aynı veya benzer özellikler için kullanılmak üzere tasarlanmıştır. Örneğin, renk olduğu gibi çünkü dönen ilerleme animasyonunun basılı açılan kutusu rengini yeniden yok. Birleşik giriş kutusu ve animasyon işlevlerini farklıdır ve rengi birleşik giriş kutusu ile ilişkilendirilmiş, artık animasyon öğesi için uygun bir renk olabilir. Renk tutarlı kullanımını kullanıcılarınızın yönlendirmek ve Karışıklığı önlemek yardımcı olur.  

-   **Arka plan ve metin renkleri doğru birlikte kullanın.** Metin ile kullanılmak üzere tasarlanmıştır arka plan renklerini ilişkili metin rengi sahip olur. Arka plan için belirtilen dışında metin renkleri kullanmayın. Bir ilişkili metin rengi değilse, bu arka plan rengi metni görüntülemek beklediğiniz tüm yüzeyini için kullanmayın. Metin ve arka plan renklerini diğer birleşimlerini okunamaz arabiriminde neden olabilir.  

-   **Konumlarına için uygun denetim renkleri kullanın.** Bazı durumlarda bazı Visual Studio denetimler ayrı kenarlık ve arka plan renklerini yok. Bunun yerine, bu arkasına yüzeyleri renkten yukarı seçin. Her zaman burada denetimi yerleştirme konumunu uygun belirteci adları kullandığınızdan emin olun.  

> [!IMPORTANT]
> "Başlangıç sayfasında" veya "Şarabıı." kategoride bulundu belirteçleri kullanmayın  

## <a name="common-shared-controls"></a>Ortak paylaşılan denetimleri

Standart bir Visual Studio komut çubuğunda, özelliğini kullandığınızda, stilde Kabuk denetimlerini erişiminiz olması. Bu ortak denetimleri yeniden şablon eklememelisiniz. Ancak, özel bir komut çubuğu yapı gerekiyorsa, özel denetimler oluşturmasına gerekebilir. Bu durumda, kullanıcı Arabirimi Visual Studio geri kalanı ile tutarlı olmasını sağlamak her aşağıdaki denetimleri için doğru belirteci adları kullandığınızdan emin olun.

### <a name="button-controls"></a>Düğme denetimleri

![Düğme denetimi kırmızı çizgi](../../extensibility/ux-guidelines/media/0303-155_buttoncontrolredline.png "0303 155_ButtonControlRedline")

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... düğmeleri için Visual Studio Temaları (açık, koyu, mavi veya bir sistem yüksek karşıtlık teması) ile tümleştirmek istediğiniz belge iyi. | Visual Studio temasını parçası olmayan özel bir arka plan karşı görüntüleyecek... düğmeleri için. |

**Düğme: standart durumu**

![Standart düğme](../../extensibility/ux-guidelines/media/03.03.Button.Standard.png "03.03.Button.Standard")<br />Standart düğmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Düğme | `CommonControls.Button` |
| Düğme kenarlığı | `CommonControls.ButtonBorder` |

**Düğme: varsayılan durumu**

![Varsayılan düğme](../../extensibility/ux-guidelines/media/03.03.Button.Default.png "03.03.Button.Default")<br />Varsayılan düğme

| Öğe | Belirteç adını: Category.color | 
| --- | --- | 
| Düğme | `CommonControls.ButtonDefault` |
| Düğme kenarlığı | `CommonControls.ButtonBorderDefault` |

**Düğmesi: devre dışı durumunu**  

![Devre dışı düğmesi](../../extensibility/ux-guidelines/media/03.03.Button.Disabled.png "03.03.Button.Disabled")<br />Devre dışı düğmesi  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Düğme | `CommonControls.ButtonDisabled` |
| Düğme kenarlığı | `CommonControls.ButtonBorderDisabled` |

**Düğme: hover durumu**  

![Vurgulu düğmesinde](../../extensibility/ux-guidelines/media/03.03.Button.hover.png "03.03.Button.hover")<br />Vurgulu düğmesine  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Düğme | `CommonControls.ButtonHover` |
| Düğme kenarlığı | `CommonControls.ButtonBorderHover` |

**Düğme: basılı durumu**  

![Basılan düğme](../../extensibility/ux-guidelines/media/03.03.Button.Pressed.png "03.03.Button.Pressed")<br />Basılan düğme  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Düğme | `CommonControls.ButtonPressed` |
| Düğme kenarlığı | `CommonControls.ButtonBorderPressed` |

**Düğme: odaklanmış durumu**  

![Odaklanmış düğmesi](../../extensibility/ux-guidelines/media/03.03.Button.Focused.png "03.03.Button.Focused")<br />Odaklanmış düğmesi  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Düğme | `CommonControls.ButtonFocused` |
| Düğme kenarlığı | `CommonControls.ButtonBorderFocused` |

### <a name="check-box-controls"></a>Onay kutusu denetimleri  
![Onay kutusu (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-161_checkboxredline.png "0303 161_CheckboxRedline")<br />Onay kutusu (kırmızı çizgi)  

| Kullanım... | Kullanmayan... |
| --- | --- |
| Belge içinde yer alan onay kutusu denetimleri için... yanı sıra. | ... hiç kullanıcı Arabirimi için bu onay kutusu denetimi değil. |

**Onay kutusu: varsayılan durumu**  

![Onay kutusu](../../extensibility/ux-guidelines/media/0303-162_checkbox.png "0303 162_Checkbox")<br />Varsayılan onay kutusu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `CommonControls.CheckBoxBackground` |
| Kenarlık | `CommonControls.CheckBoxBorder` |
| Metin | `CommonControls.CheckBoxText` |
| Karakter | `CommonControls.CheckBoxGlyph` |

**Onay kutusu: devre dışı durum**  

![Devre dışı onay kutusu](../../extensibility/ux-guidelines/media/0303-163_checkboxdisabled.png "0303 163_CheckboxDisabled")<br />Devre dışı onay kutusu  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `CommonControls.CheckBoxBackgroundDisabled` |
| Kenarlık | `CommonControls.CheckBoxBorderDisabled` |
| Metin | `CommonControls.CheckBoxTextDisabled` |
| Karakter | `CommonControls.CheckBoxGlyphDisabled` |

**Onay kutusu: vurgulu durumu**  

 ![Onay kutusu vurgulu](../../extensibility/ux-guidelines/media/0303-164_checkboxhover.png "0303 164_CheckboxHover")<br />Vurgulu onay kutusu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `CommonControls.CheckBoxBackgroundHover` |
| Kenarlık | `CommonControls.CheckBoxBorderHover` |
| Metin | `CommonControls.CheckBoxTextHover` |
| Karakter | `CommonControls.CheckBoxGlyphHover` |  

**Onay kutusu: durumu basılı**  

![Basılı onay kutusunu](../../extensibility/ux-guidelines/media/0303-165_checkboxpressed.png "0303 165_CheckboxPressed")<br />Basılı onay kutusu  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `CommonControls.CheckBoxBackgroundPressed` |
| Kenarlık | `CommonControls.CheckBoxBorderPressed` |
| Metin | `CommonControls.CheckBoxTextPressed` |
| Karakter | `CommonControls.CheckBoxGlyphPressed` |  

**Onay kutusu: durumu odaklanmış**  

![Odaklanmış onay kutusunu](../../extensibility/ux-guidelines/media/0303-166_checkboxfocused.png "0303 166_CheckboxFocused")<br />Odaklanmış onay kutusu  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `CommonControls.CheckBoxBackgroundFocused` |
| Kenarlık | `CommonControls.CheckBoxBorderFocused` |
| Metin | `CommonControls.CheckBoxTextFocused` |
| Karakter | `CommonControls.CheckBoxGlyphFocused` |

### <a name="drop-downs-and-combo-boxes"></a>Aşağı açılan listeler ve birleşik giriş kutuları
![Aşağı/birleşik açılır kutusunu (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-167_dropdowncomboboxredline.png "0303 167_DropDownComboBoxRedline")<br />Aşağı/birleşik açılır kutusunu (kırmızı çizgi)  

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... aşağı açılan listeler ve birleşik giriş kutuları belgede iyi. | aşağı açılan veya birleşik giriş kutusu olmayan... hiç kullanıcı Arabirimi için. |  
| | Komut çubuğu için... [aşağı açılan listeler](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_CommandDropDown) veya [birleşik giriş kutuları](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_CommandComboBox). |

**Aşağı açılan listeler ve birleşik giriş kutuları: varsayılan durumu**  

![Varsayılan aşağı/birleşik açılır kutusunu](../../extensibility/ux-guidelines/media/0303-168_dropdowncombobox.png "0303 168_DropDownComboBox")<br />Varsayılan aşağı/birleşik açılır kutusunu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `CommonControls.ComboBoxBackground` |
| Kenarlık | `CommonControls.ComboBoxBorder` |
| Metin | `CommonControls.ComboBoxText` |
| Ayırıcı | `CommonControls.ComboBoxSeparator` |
| Karakter | `CommonControls.ComboBoxGlyph` |
| Karakter arka plan | `CommonControls.ComboBoxGlyphBackground` |

**Aşağı açılan listeler ve birleşik giriş kutuları: devre dışı durum**  

![Devre dışı bırak-aşağı/birleşik giriş kutusu](../../extensibility/ux-guidelines/media/0303-169_dropdowncomboboxdisabled.png "0303 169_DropDownComboBoxDisabled")<br />Devre dışı bırak-aşağı/birleşik giriş kutusu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `CommonControls.ComboBoxBackgroundDisabled` |
| Kenarlık | `CommonControls.ComboBoxBorderDisabled` |
| Metin | `CommonControls.ComboBoxTextDisabled` |
| Ayırıcı | `CommonControls.ComboBoxSeparatorDisabled` |
| Karakter | `CommonControls.ComboBoxGlyphDisabled` |
| Karakter arka plan | `CommonControls.ComboBoxGlyphBackgroundDisabled` |

**Aşağı açılan listeler ve birleşik giriş kutuları: vurgulu durumu**  

![Vurgulu aşağı/birleşik açılır kutusunda](../../extensibility/ux-guidelines/media/0303-170_dropdowncomboboxhover.png "0303 170_DropDownComboBoxHover")<br />Aşağı/birleşik açılır kutusunda vurgulu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `CommonControls.ComboBoxBackgroundHover` |
| Kenarlık | `CommonControls.ComboBoxBorderHover` |
| Metin | `CommonControls.ComboBoxTextHover` |
| Ayırıcı | `CommonControls.ComboBoxSeparatorHover` |
| Karakter | `CommonControls.ComboBoxGlyphHover` |
| Karakter arka plan | `CommonControls.ComboBoxGlyphBackgroundHover` |

**Aşağı açılan listeler ve birleşik giriş kutuları: durumu basılı**  

![Aşağı/birleşik açılır kutusunu basılı](../../extensibility/ux-guidelines/media/0303-171_dropdowncomboboxpressed.png "0303 171_DropDownComboBoxPressed")<br />Aşağı/birleşik açılır kutusunu basılı  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `CommonControls.ComboBoxBackgroundPressed` |
| Kenarlık | `CommonControls.ComboBoxBorderPressed` |
| Metin | `CommonControls.ComboBoxTextPressed` |
| Ayırıcı | `CommonControls.ComboBoxSeparatorPressed` |
| Karakter | `CommonControls.ComboBoxGlyphPressed` |
| Karakter arka plan | `CommonControls.ComboBoxGlyphBackgroundPressed` |

**Aşağı açılan listeler ve birleşik giriş kutuları liste öğesi görünümü: durumu basılı**  

 ![Liste öğesi görünümü basılı aşağı/birleşik açılır kutusunu](../../extensibility/ux-guidelines/media/0303-174_dropdowncomboboxlistview.png "0303 174_DropDownComboBoxListView")<br />Liste öğesi görünümü basılı aşağı/birleşik açılır kutusunu  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan |  `CommonControls.ComboBoxListBackground`<br />`CommonControls.ComboBoxListBackgroundHover`<br />`CommonControls.ComboBoxListItemBackgroundPressed`<br />`CommonControls.ComboBoxListItemBackgroundFocused` |
| Kenarlık | `CommonControls.ComboBoxListBorder`<br />`CommonControls.ComboBoxListBorderHover`<br />`CommonControls.ComboBoxListBorderPressed`<br />`CommonControls.ComboBoxListBorderFocused` |
| Öğesi metni | `CommonControls.ComboBoxListItemText`<br /> `CommonControls.ComboBoxListItemTextHover`<br />`CommonControls.ComboBoxListItemTextPressed`<br />`CommonControls.ComboBoxListItemTextFocused` |
| Arka plan gölgesi | `CommonControls.ComboBoxListBackgroundShadow` |

**Aşağı açılan listeler ve birleşik giriş kutuları: durumu odaklanmış**  

![Aşağı/birleşik açılır kutusunu Odaklanılan](../../extensibility/ux-guidelines/media/0303-172_dropdowncomboboxfocused.png "0303 172_DropDownComboBoxFocused")<br />Aşağı/birleşik açılır kutusunu odaklanılan

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `CommonControls.ComboBoxBackgroundFocused` |
| Kenarlık | `CommonControls.ComboBoxBorderFocused` |
| Metin | `CommonControls.ComboBoxTextFocused` |
| Ayırıcı | `CommonControls.ComboBoxSeparatorFocused` |
| Karakter | `CommonControls.ComboBoxGlyphFocused` |
| Karakter arka plan | `CommonControls.ComboBoxGlyphBackgroundFocused` |

**Aşağı açılan listeler ve birleşik giriş kutuları: metin girişi seçimi**  

![Aşağı/birleşik açılır kutusunda metin girişi seçimi](../../extensibility/ux-guidelines/media/0303-173_dropdowncomboboxtextinput.png "0303 173_DropDownComboBoxTextInput")<br />Seçimi aşağı/birleşik açılır kutusunda metin girişi  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Vurgula | `CommonControls.ComboBoxTextInputSelection` |

### <a name="tabular-data-grid-controls"></a>Tablo verisi (Izgara) denetimleri  
Tablo verisi denetimler, kılavuz denetimleri olarak da bilinen, büyük miktarlarda verinin birden çok sütun sunmak için kullanılan Visual Studio için ortak denetimleridir. Standart tablo veri denetimleri, Visual Studio içinde birden çok yerde bulunabilir: hata listesi araç penceresi, IntelliTrace raporları ve diğerlerinin yanı sıra bellek yığın görünümü. Her zaman sağlanan standart tablo veri denetimleri kullanın. Bazı nadir durumlarda, standart tablo verileri denetimlere erişim sahip olmayabilir. Bu durumlarda, kullanıcı Arabirimi diğer tablo veri denetimleri Visual Studio ile tutarlı olduğundan emin olmak için aşağıdaki belirteci adları kullanın.  

![Tablo veri kılavuzu denetim (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-197_tabulardatagridcontrolredline.png "0303 197_TabularDataGridControlRedline")<br />Tablo veri kılavuzu denetim (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... için tablo veya kılavuz denetimleri. | bir tablo veya kılavuz denetim olmayan... hiç kullanıcı Arabirimi için. |

#### <a name="column-headers"></a>Sütun üstbilgileri  
Sütun üstbilgileri arka plan, kenarlık, başlık metnini ve kılavuz sütuna göre sıralandığında genellikle kullanılan isteğe bağlı bir karakter oluşur.  

**Sütun başlığını: varsayılan durumu**

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Header.Default` |
| Ön plan (metin) | `Environment.CommandBarTextActive` |
| Ön plan (karakter) | `Header.Glyph` |
| Kenarlık | `Header.SeparatorLine` |

**Sütun başlığını: vurgulu durumu**

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Header.MouseOver` |
| Ön plan (metin) | `Environment.CommandBarTextHover` |
| Ön plan (karakter) | `Header.MouseOverGlyph` |
| Kenarlık | `Header.SeparatorLine` |

**Sütun başlığını: durumu basılı**

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `CommonControls.CheckBoxBackgroundPressed` |
| Ön plan (metin) | `CommonControls.CheckBoxBorderPressed` |
| Ön plan (karakter) | `CommonControls.CheckBoxTextPressed` |
| Kenarlık | `CommonControls.CheckBoxGlyphPressed` |

#### <a name="list-view-items"></a>Liste görünümü öğesi  
 Liste görünümü öğesi arka plan ve içeriği oluşur. İçerik, metin, simge veya her ikisi de olabilir.  

**Liste Görünümü öğelerini: varsayılan durumu**

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Geçirgen |
| Ön plan (metin) | `Environment.CommandBarTextActive` |
| Kenarlık | Yok. |

**Liste Görünümü öğelerini: Etkin durumu**

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `TreeView.SelectedItemActive` |
| Ön plan (metin) | `TreeView.SelectedItemActiveText` |
| Kenarlık | Yok. |

**Liste Görünümü öğelerini: devre dışı durum**

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `TreeView.SelectedItemInactive` |
| Ön plan (metin) | `TreeView.SelectedItemInactiveText` |
| Kenarlık | Yok. |  

### <a name="ui-text"></a>UI metin

#### <a name="instructional-text"></a>Açıklayıcı metin
Açıklayıcı metin ne de bir iletişim kutusu veya belge sayfası yapmak belirgin ana bir açıklama sağlar.

![Varsayılan yol gösterici metni](../../extensibility/ux-guidelines/media/0303_InstructionalText.png "0303_InstructionalText.png")<br />Varsayılan yol gösterici metni

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Ön plan (metin) | `Environment.ControlText` |

#### <a name="secondary-instructional-text"></a>İkincil açıklayıcı metin
Belge sayfalarını metin ve denetimler çok sayıda'de, bazı açıklayıcı metni farklı bir renk değeri kullanır. Hangi bilgilerin en önemli iletmek ve kullanıcı Arabirimi öğeleri genel yoğunluğunu azaltmak için yardımcı olur. (Ayrıca bkz. ipucu metnini bölümünde aşağıda.)

![İkincil açıklayıcı metin](../../extensibility/ux-guidelines/media/0303_SecondaryInstructionalText.png "0303_SecondaryInstructionalText.png")<br />İkincil açıklayıcı metin

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Ön plan (metin) | `Environment.ControlEditHintText` |

#### <a name="hint-text"></a>İpucu metni
İpucu metnini boş bir denetimi, denetim altına ya da kullanıcı bundan sonra yapmanız gerekenler göstermek için bir boş belge yüzeyinde görünür. İpucu metnini penceresi veya denetim arka plan ile kullanabilirsiniz.

**Varsayılan İpucu metni**

![Varsayılan ipucu metnini](../../extensibility/ux-guidelines/media/0303_HintText.png "0303_HintText.png")<br />Varsayılan İpucu metni

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Ön plan (metin) | `Environment.ControlEditHintText` |

**Gerekli ipucu metnini**

![Gerekli ipucu metnini](../../extensibility/ux-guidelines/media/0303_RequiredHintText.png "0303_RequiredHintText.png")<br />Gerekli ipucu metnini

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Ön plan (metin) | `Environment.ControlRequiredHintText` |
| Arka Plan | `Environment.ControlRequiredBackground` |

**Arama kutusu denetim metni**

> Bkz: [arama kutuları](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_SearchBoxes) arama denetimi ile ilgili diğer renk belirteçleri.

![Arama kutusu denetim metni](../../extensibility/ux-guidelines/media/0303_SearchBoxControl.png "0303_SearchBoxControl.png")<br />Arama kutusu denetim metni

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Ön plan (metin) | `SearchControl.UnfocusedWatermarkText` |

### <a name="hyperlink"></a>Köprü  
Köprü bir ön plan/arka plan çifti sahip olmayan bir denetimdir. Her durumda, doğru koyu, gri ve beyaz arka planlar görünür ön plan köprü rengi kullanın. Köprü denetim için renk belirteci kullanmıyorsanız, kırmızı yanar "basılı" için varsayılan sistem rengi görürsünüz. Denetim doğru ortamı renk belirteci kullanmıyor sinyal olmasıdır.  

![Köprü (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-133_hyperlinkredline.png "0303 133_HyperlinkRedline")<br />Köprü (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... ne zaman özel köprü oluşturmanız gerekir. | ... her şey için bir köprü değil. |

**Köprü: varsayılan durumu**  

![Varsayılan köprü](../../extensibility/ux-guidelines/media/0303-134_hyperlink.png "0303 134_Hyperlink")<br />Varsayılan köprü

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Ön plan (metin) | `Environment.PanelHyperlink` |

**Köprü: vurgulu durumu**

![Köprü vurgulu üzerinde](../../extensibility/ux-guidelines/media/0303-135_hyperlinkhover.png "0303 135_HyperlinkHover")<br />Köprü vurgulu üzerinde  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Ön plan (metin) | `Environment.PanelHyperlinkHover` |

**Köprü: basılı durumu**

![Basılı köprü](../../extensibility/ux-guidelines/media/0303-136_hyperlinkpressed.png "0303 136_HyperlinkPressed")<br />Basılı köprü  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Ön plan (metin) | `Environment.PanelHyperlinkPressed` |

**Köprü: devre dışı durum**

![Devre dışı köprü](../../extensibility/ux-guidelines/media/0303-137_hyperlinkdisabled.png "0303 137_HyperlinkDisabled")<br />Devre dışı köprü  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Ön plan (metin) | `Environment.PanelHyperlinkDisabled` |

### <a name="infobars"></a>Infobars  
Infobars her zaman bir belge penceresine veya araç penceresi üstünde görünür ve belirli bir bağlam hakkında daha fazla bilgi sağlamak için kullanılır.  

![Bilgi Çubuğu (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-138_infobarredline.png "0303 138_InfobarRedline")<br />Bilgi Çubuğu (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... özel infobars oluştururken. | bir bilgi çubuğu benzer olmayan... için kullanıcı Arabirimi öğeleri. |

**Bilgi Çubuğu: varsayılan durumu**

![Varsayılan bilgi çubuğu](../../extensibility/ux-guidelines/media/0303-139_infobar.png "0303 139_Infobar")<br />Varsayılan bilgi çubuğu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `InfoBar.InfoBarBackground` |
| Ön plan (metin) | `InfoBar.InfoBar` |
| Kenarlık | `InfoBar.InfoBarBorder` |

**Bilgi çubuğu Kapat (&times;) düğmesini: varsayılan durumu**

![Varsayılan bilgi çubuğu Kapat (&times;) düğmesini](../../extensibility/ux-guidelines/media/0303_InfobarCloseDefault.png "0303_InfobarCloseDefault.png")<br />Varsayılan bilgi çubuğu Kapat (&times;) düğmesine

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `InfoBar.CloseButton` |
| Kenarlık | `InfoBar.CloseButtonBorder` |
| Karakter | `InfoBar.CloseButtonGlyph` |

**Bilgi çubuğu Kapat (&times;) düğmesini: vurgulu durumu**

![Bilgi çubuğu Kapat (&times;) vurgulu düğmesinde](../../extensibility/ux-guidelines/media/0303_InfobarCloseHover.png "0303_InfobarCloseHover.png")<br />Bilgi çubuğu Kapat (&times;) vurgulu düğmesine

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `InfoBar.CloseButtonHover` |
| Kenarlık | `InfoBar.CloseButtonHoverBorder` |
| Karakter | `InfoBar.CloseButtonHoverGlyph` |

**Bilgi çubuğu Kapat (&times;) düğmesini: durumu basılı**

![Bilgi çubuğu Kapat basılı (&times;) düğmesini](../../extensibility/ux-guidelines/media/0303_InfobarClosePressed.png "0303_InfobarClosePressed.png")<br />Bilgi çubuğu Kapat basılı (&times;) düğmesine

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `InfoBar.CloseButtonDown` |
| Kenarlık | `InfoBar.CloseButtonDownBorder` |
| Karakter | `InfoBar.CloseButtonDownGlyph` |

**Bilgi çubuğu köprü düğmesi: varsayılan durumu**

![Varsayılan bilgi çubuğu köprü düğme](../../extensibility/ux-guidelines/media/0303_InfobarHyperlinkButtonDefault.png "0303_InfobarHyperlinkButtonDefault.png")<br />Varsayılan bilgi çubuğu köprü düğmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Ön plan (metin) | `InfoBar.Hyperlink` |

**Bilgi çubuğu köprü düğmesi: vurgulu durumu**

![Bilgi çubuğu köprü vurgulu düğmesinde](../../extensibility/ux-guidelines/media/0303_InfobarHyperlinkButtonHover.png "0303_InfobarHyperlinkButtonHover.png")<br />Bilgi çubuğu köprü düğmesine vurgulu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Ön plan (metin) | `Infobar.HyperlinkMouseOver`<br />(Alt çizgi ile) |

**Bilgi çubuğu köprü düğmesi: durumu basılı**

![Basılı bilgi çubuğu köprü düğmesi](../../extensibility/ux-guidelines/media/0303_InfobarHyperlinkButtonPressed.png "0303_InfobarHyperlinkButtonPressed.png")<br />Basılı bilgi çubuğu köprü düğmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Ön plan (metin) | `Infobar.HyperlinkMouseDown`<br />(Alt çizgi ile) |

**Bilgi çubuğu satır içi köprü (içinde bir cümle): varsayılan durumu**

![Varsayılan satır içi bilgi çubuğu köprü düğme](../../extensibility/ux-guidelines/media/0303_InfobarHyperlinkButtonDefault.png "0303_InfobarHyperlinkButtonDefault.png")<br />Varsayılan satır içi bilgi çubuğu köprü düğmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Ön plan (metin) | `InfoBar.Hyperlink` |

**Bilgi çubuğu satır içi köprü (içinde bir cümle): vurgulu durumu**

![Bilgi çubuğu satır içi köprü vurgulu düğmesinde](../../extensibility/ux-guidelines/media/0303_InfobarHyperlinkInlineHover.png "0303_InfobarHyperlinkInlineHover.png")<br />Bilgi çubuğu satır içi köprü vurgulu düğmesinde

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Ön plan (metin) | `Infobar.HyperlinkMouseOver`<br />(Alt çizgi ile) |

**Bilgi çubuğu satır içi köprü (içinde bir cümle): durumu basılı**

![Satır içi köprü düğmesini basılı bilgi çubuğu](../../extensibility/ux-guidelines/media/0303_InfobarHyperlinkInlinePressed.png "0303_InfobarHyperlinkInlinePressed.png")<br />Bilgi çubuğu satır içi köprü düğmesine basıldığında

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Ön plan (metin) | `Infobar.HyperlinkMouseDown`<br />(Alt çizgi ile) |

**Bilgi çubuğu düğmesini: varsayılan durumu**

![Varsayılan bilgi çubuğu düğme](../../extensibility/ux-guidelines/media/0303_InfobarButtonDefault.png "0303_InfobarButtonDefault.png")<br />Varsayılan bilgi çubuğu düğmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `InfoBar.Button` |
| Ön plan (metin) | `InfoBar.Button` |
| Kenarlık | `InfoBar.ButtonBorder` |

**Bilgi çubuğu düğmesini: vurgulu durumu**

![Bilgi çubuğu düğmesini vurgulu](../../extensibility/ux-guidelines/media/0303_InfobarButtonHover.png "0303_InfobarButtonHover.png")<br />Bilgi çubuğu düğmesini vurgulu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `InfoBar.ButtonMouseOver` |
| Ön plan (metin) | `InfoBar.ButtonMouseOver` |
| Kenarlık | `InfoBar.ButtonMouseOverBorder` |

**Bilgi çubuğu düğmesini: durumu basılı**

![Basılı bilgi çubuğu düğmesini](../../extensibility/ux-guidelines/media/0303_InfobarButtonPressed.png "0303_InfobarButtonPressed.png")<br />Basılı bilgi çubuğu düğmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `InfoBar.ButtonMouseDown` |
| Ön plan (metin) | `InfoBar.ButtonMouseDown` |
| Kenarlık | `InfoBar.ButtonMouseDownBorder` |

**Bilgi çubuğu düğmesini: devre dışı durum**

![Devre dışı bilgi çubuğu düğmesini](../../extensibility/ux-guidelines/media/0303_InfobarButtonDisabled.png "0303_InfobarButtonDisabled.png")<br />Devre dışı bilgi çubuğu düğmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `InfoBar.ButtonDisabled` |
| Ön plan (metin) | `InfoBar.ButtonDisabled` |
| Kenarlık | `InfoBar.ButtonDisabledBorder` |

**Bilgi çubuğu düğmesini: durumu odaklanmış**

![Odaklanmış bilgi çubuğu düğmesini](../../extensibility/ux-guidelines/media/0303_InfobarButtonFocus.png "0303_InfobarButtonFocus.png")<br />Odaklanmış bilgi çubuğu düğmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `InfoBar.ButtonFocus` |
| Ön plan (metin) | `InfoBar.ButtonFocus` |
| Kenarlık | `InfoBar.ButtonFocusBorder` |

### <a name="scroll-bars"></a>Kaydırma çubukları  
Kaydırma çubukları, Visual Studio ortamı tarafından stilde ve tema uygulanabilir olması gerekmez. Ancak, böylece UI her zaman Visual Studio ortamında bu kısmı tutarlı görünür kaydırma çubukları kullanılan renkleri yararlanmak istediğiniz karar verebilirsiniz.  

![Kaydırma çubuğu (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-140_scrollbarredline.png "0303 140_ScrollbarRedline")<br />Kaydırma çubuğu (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... Visual Studio kaydırma çubukları eşleştirmek istediğiniz kullanıcı Arabirimi, oluştururken. | her zaman eşleşecek şekilde istemediğiniz her şey için... kaydırma kullanıcı Arabirimi. |

**Kaydırma çubuğu: varsayılan durumu**  

![Varsayılan kaydırma çubuğu](../../extensibility/ux-guidelines/media/0303-141_scrollbar.png "0303 141_Scrollbar")<br />Varsayılan kaydırma çubuğu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Kaydırma çubuğu | `Environment.ScrollBarBackground` |
| Ön plan (Flash) | `Environment.ScrollBarThumbBackground` |

**Kaydırma çubuğu: vurgulu durumu**

![Kaydırma çubuğu vurgulu](../../extensibility/ux-guidelines/media/0303-143_scrollbarhover.png "0303 143_ScrollbarHover")<br />Vurgulu kaydırma çubuğu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Kaydırma çubuğu | `Environment.ScrollBarBackground` |
| Ön plan (Flash) | `Environment.ScrollBarThumbMouseOverBackground` |

*Kaydırma çubuğu: durumu basılı**

![Basılı kaydırma çubuğu](../../extensibility/ux-guidelines/media/0303-145_scrollbarpressed.png "0303 145_ScrollbarPressed")<br />Kaydırma çubuğu basılı  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Kaydırma çubuğu | `Environment.ScrollBarBackground` |
| Ön plan (Flash) | `Environment.ScrollBarThumbPressedBackground` |

**Kaydırma ok: varsayılan durumu**  

![Varsayılan kaydırma çubuğu okunu](../../extensibility/ux-guidelines/media/0303-142_scrollbararrow.png "0303 142_ScrollbarArrow")<br />Varsayılan kaydırma çubuğu oku

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ScrollBarArrowBackground`<br />(Aynı renk kaydırma çubuğu olarak ayarlayın.) |
| Ön plan (karakter) | `Environment.ScrollBarArrowGlyph` |

**Kaydırma ok: vurgulu durumu**

![Kaydırma çubuğu vurgulu okuna](../../extensibility/ux-guidelines/media/0303-144_scrollbararrowhover.png "0303 144_ScrollbarArrowHover")<br />Kaydırma çubuğu okuna vurgulu  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ScrollBarArrowMouseOverBackground`<br />(Aynı renk kaydırma çubuğu olarak ayarlayın.) |
| Ön plan (karakter) | `Environment.ScrollBarArrowGlyphMouseOver` |

**Kaydırma ok: durumu basılı**  

![Basılı kaydırma çubuğu okunu](../../extensibility/ux-guidelines/media/0303-146_scrollbararrowpressed.png "0303 146_ScrollbarArrowPressed")<br />Kaydırma çubuğu okunu basılı

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ScrollBarArrowPressedBackground`<br />(Aynı renk kaydırma çubuğu olarak ayarlayın.) |
| Ön plan (karakter) | `Environment.ScrollBarArrowGlyphPressed` |

### <a name="BKMK_SearchBoxes"></a>Arama kutuları  
Mümkün olduğunda, Visual Studio ortamı tarafından sağlanan ortak arama denetimini kullanın. Arama kutusu renkleri "SearchControl" kategorisinde bulunan **ShellColors.pkgdef** giriş alanı, eylem düğmesi, açılan düğmesine ve açılır menü için belirteç adlarını içeren dosya.  

Bir arama kutusu birkaç durumları bazıları karşılıklı olarak birbirini dışlar, biri olabilir:  

-   "Odaklanmış" veya "Odaksız" imleci olsun veya olmasın metin kutusuna etmektir başvuruyor.  

-   "Active" veya "etkin olmayan" olup kullanıcı metin kutusuna bir arama sorgusu girişi için ifade eder.  

-   "Vurgulu" kullanıcı arama kutusu içinde (Bu durum, diğer tüm durumları geçersiz kılar) fareyle moused anlamına gelir.  

-   "Devre dışı" arama işlevi için geçerli bağlam kapalı anlamına gelir.  

![Arama kutusuna (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-110_searchboxredline.png "0303 110_SearchBoxRedline")<br />Arama kutusuna (kırmızı çizgi)  

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... ne zaman, tasarlama özel arama kutusu. | ... her şey için bir arama kutusu değil. |
| | ... arama her zaman aynı istemediğiniz hiçbir şey için kullanıcı Arabirimi kutusu. |

**Arama giriş alanını odaklanmış**

![Odaklanmış bir arama giriş alanını](../../extensibility/ux-guidelines/media/0303-111_searchinputfieldfocused.png "0303 111_SearchInputFieldFocused")<br />Arama giriş alanını odaklanmış  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `SearchControl.FocusedBackground` |
| Ön plan (metin) | `SearchControl.FocusedBackground` |
| Kenarlık | `SearchControl.FocusedBorder` |
| Ayırıcı | `SearchControl.FocusedDropDownSeparator` |

**Odaksız, etkin arama giriş alanı**

![Arama giriş alanını Odaksız](../../extensibility/ux-guidelines/media/0303-114_searchinputfieldunfocused.png "0303 114_SearchInputFieldUnfocused")<br />Odaksız, etkin arama giriş alanı

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `SearchControl.SearchActiveBackground` |
| Ön plan (metin) | `SearchControl.SearchActiveBackground` |
| Kenarlık | `SearchControl.UnfocusedBorder` |
| Ayırıcı | `SearchControl.DropDownSeparator` |

**Odaksız, etkin olmayan arama giriş alanı**

![Odaksız, etkin olmayan arama giriş alanını](../../extensibility/ux-guidelines/media/0303-114-1_searchinputfieldunfocusedinactive.png "0303 114 1_SearchInputFieldUnfocusedInactive")<br />Odaksız, etkin olmayan arama giriş alanı  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `SearchControl.Unfocused` |
| Ön plan (metin) | `SearchControl.Unfocused` |
| Kenarlık | `SearchControl.UnfocusedBorder` |
| Ayırıcı | `SearchControl.DropDownSeparator` |

**Vurgulanan arama giriş alanı (yalnızca metin)**

![Vurgulanan arama giriş alanını](../../extensibility/ux-guidelines/media/0303-120_searchinputfieldhighlight.png "0303 120_SearchInputFieldHighlight")<br />Vurgulanan arama giriş alanı

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `SearchControl.Selection` |
| Ön plan (metin) | `SearchControl.FocusedBackground` |
| Kenarlık | Yok. |
| Ayırıcı | `SearchControl.FocusedDropDownSeparator` |

**Devre dışı giriş alanını arama**

![Devre dışı arama giriş alanını](../../extensibility/ux-guidelines/media/0303-121_searchinputfielddisabled.png "0303 121_SearchInputFieldDisabled")<br />Devre dışı giriş alanını arama

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `SearchControl.Disabled` |
| Ön plan (metin) | `SearchControl.Disabled` |
| Kenarlık | `SearchControl.DisabledBorder` |
| Ayırıcı | `SearchControl.DropDownSeparator` |

**Odaklanmış bir arama eylem düğmesi**

![Arama eylem düğmesi odaklanmış](../../extensibility/ux-guidelines/media/0303-112_searchactionbuttonfocused.png "0303 112_SearchActionButtonFocused")<br />Odaklanmış bir arama eylem düğmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Yok. |
| Ön plan (arama karakter) | `SearchControl.SearchGlyph` |
| Ön plan (Dur karakter) | `SearchControl.StopGlyph` |
| Ön plan (Temizle karakter) | `SearchControl.ClearGlyph` |
| Kenarlık | Yok |

**Odaksız arama eylem düğmesi**  

![Odaksız arama eylem düğmesi](../../extensibility/ux-guidelines/media/0303-115_searchactionbuttonunfocused.png "0303 115_SearchActionButtonUnfocused")<br />Odaksız arama eylem düğmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Yok |
| Ön plan (arama karakter) | `SearchControl.SearchGlyph` |
| Ön plan (Dur karakter) | `SearchControl.StopGlyph` |
| Ön plan (Temizle karakter) | `SearchControl.ClearGlyph` |
| Kenarlık | Yok |

**Arama eylem düğmesine basıldığında**

![Basılı arama eylem düğmesi](../../extensibility/ux-guidelines/media/0303-116-1_searchactionbuttonpressed.png "0303 116 1_SearchActionButtonPressed")<br />Arama eylem düğmesine basıldığında

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `SearchControl.ActionButtonMouseDown` |
| Ön plan (karakter) | `SearchControl.ActionButtonMouseDownGlyph` |
| Kenarlık | `SearchControl.ActionButtonMouseDownBorder` |

**Devre dışı arama eylem düğmesi**

![Arama eylem düğmesi devre dışı](../../extensibility/ux-guidelines/media/0303-122_searchactionbuttondisabled.png "0303 122_SearchActionButtonDisabled")<br />Devre dışı arama eylem düğmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Yok. |
| Ön plan (karakter) | `SearchControl.ActionButtonDisabledGlyph` |
| Kenarlık | Yok. |

**Odaklanmış bir arama açılan düğmesine**

![Odaklanmış bir arama açılan düğmesine](../../extensibility/ux-guidelines/media/0303-113_searchdropdownbuttonfocused.png "0303 113_SearchDropdownButtonFocused")<br />Odaklanmış bir arama açılan düğmesine

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `SearchControl.FocusedDropDownButton` |
| Ön plan (karakter) | `SearchControl.FocusedDropDownButtonGlyph` |
| Kenarlık | `SearchControl.FocusedDropDownButtonBorder` |

**Odaksız arama açılan düğmesine**

![Odaksız arama açılan düğmesine](../../extensibility/ux-guidelines/media/0303-116_searchdropdownbuttonunfocused.png "0303 116_SearchDropdownButtonUnfocused")<br />Odaksız arama açılan düğmesine

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `SearchControl.UnfocusedDropDownButton` |
| Ön plan (karakter) | `SearchControl.UnfocusedDropDownButtonGlyph` |
| Kenarlık | `SearchControl.UnfocusedDropDownButtonBorder` |

**Arama açılan düğmesine basıldığında**

![Basılı arama açılan düğmesine](../../extensibility/ux-guidelines/media/0303-116-2_searchdropdownbuttonpressed.png "0303 116 2_SearchDropdownButtonPressed")<br />Arama açılan düğmesine basıldığında

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `SearchControl.MouseDownDropDownButton` |
| Ön plan (karakter) | `SearchControl.MouseDownDropDownButtonGlyph` |
| Kenarlık | `SearchControl.MouseDownDropDownButtonBorder` |

**Devre dışı arama açılan düğmesine**

![Devre dışı arama açılan düğmesine](../../extensibility/ux-guidelines/media/0303-123_searchdropdownbuttondisabled.png "0303 123_SearchDropdownButtonDisabled")<br />Devre dışı arama açılan düğmesine

| Öğe | Belirteç adını: Category.color |
| --- | --- |  
| Arka Plan | Yok. |
| Ön plan (karakter) | `SearchControl.DisabledDownButtonGlyph` |
| Kenarlık | Yok. |

#### <a name="search-drop-down-lists"></a>Arama aşağı açılır listeler  
Arama kutusunda aşağı açılan menüden diğer aşağı açılır menüler Visual Studio'da biraz daha karmaşık olma olasılığına sahiptir. "Önerilen aramalar" ve "Seçenekler Ara" bölümleri tek başına veya birlikte menüde yer alabilir ve her biri ayrı olarak renkli. Bir satır da birlikte görünürler ve tüm açılır menüsünde kenarlık çevreleyen bu iki bölüme ayırır.  

![Arama açılan listesi (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-124_searchdropdownredline.png "0303 124_SearchDropdownRedline")<br />Arama açılan listesi (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... özel arama açılan listesini oluştururken. | diğer bağlamlarda görünen... aşağı açılır listeler için. |
| ... doğru listesi bileşenleri için doğru belirteci adları. | Belirtilen dışındaki... tüm arka plan/ön plan birlikte. |

**Arama açılan liste öğeleri**

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Kenarlık | `SearchControl.PopupBorder` |
| Ayırıcı | `SearchControl.PopupSectionHeaderSeparator` |
| Gölge | `Environment.DropShadowBackground` |

**Aramaları önerilen: varsayılan durumu**

![Önerilen aramaları varsayılan](../../extensibility/ux-guidelines/media/0303-125_searchsuggested.png "0303 125_SearchSuggested")<br />Önerilen aramaları varsayılan  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `SearchControl.PopupItemsListBackgroundGradientBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `SearchControl.PopupItemText` |

**Aramaları önerilen: vurgulu durumu**

![Vurgulu aramaları önerilen](../../extensibility/ux-guidelines/media/0303-128_searchsuggestedhover.png "0303 128_SearchSuggestedHover")<br />Vurgulu önerilen arama

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `SearchControl.PopupControlMouseOverBackgroundGradientBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `SearchControl.PopupMouseOverItemText` |
| Kenarlık | `SearchControl.PopupControlMouseOverBorder` |

**Arama Seçenekleri: varsayılan durumu**

![Arama onay kutusunu](../../extensibility/ux-guidelines/media/0303-126_searchcheckbox.png "0303 126_SearchCheckbox")<br />Varsayılan arama seçenekleri (onay kutusu)  

![Arama Seçenekleri](../../extensibility/ux-guidelines/media/0303-127_searchoptions.png "0303 127_SearchOptions")<br />Varsayılan arama seçenekleri (bağlantı)  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `SearchControl.PopupSectionBackgroundGradientBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (onay kutusu metni) | `SearchControl.PopupCheckboxText` |
| Ön plan (bağlantı metni) | `SearchControl.PopupButtonText` |
| Üstbilgi arka planı | `SearchControl.PopupSectionHeaderGradientBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (başlık metni) | `SearchControl.PopupSectionHeaderText` |

**Arama Seçenekleri: vurgulu durumu**

![Arama Seçenekleri (onay kutusu) gidildiğinde](../../extensibility/ux-guidelines/media/0303-129_searchcheckboxhover.png "0303 129_SearchCheckboxHover")<br />Arama Seçenekleri (onay kutusu) vurgulu  

![Arama Seçenekleri (bağlantı) gidildiğinde](../../extensibility/ux-guidelines/media/0303-130_searchoptionshover.png "0303 130_SearchOptionsHover")<br />Vurgulu arama seçenekleri (bağlantı)  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `SearchControl.PopupControlMouseOverBackgroundGradientBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (onay kutusu metni) | `SearchControl.PopupCheckboxMouseDownText` |
| Ön plan (bağlantı metni) | `SearchControl.PopupButtonMouseDownText` |
| Kenarlık | `SearchControl.PopupControlMouseOverBorder` |

**Arama Seçenekleri: durumu basılı**  

![Arama Seçenekleri (onay kutusu) basılı](../../extensibility/ux-guidelines/media/0303-131_searchsuggestedpressed.png "0303 131_SearchSuggestedPressed")<br />Arama Seçenekleri (onay kutusu) basılı   

![Arama Seçenekleri (bağlantı) basılı](../../extensibility/ux-guidelines/media/0303-132_searchoptionspressed.png "0303 132_SearchOptionsPressed")<br />Arama Seçenekleri (bağlantı) basılı  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Onay kutusu arka plan | `SearchControl.PopupControlMouseDownBackgroundGradientBegin`<br />`SearchControl.PopupControlMouseDownBackgroundGradientEnd`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (onay kutusu metni) | `SearchControl.PopupCheckboxMouseDownText` |
| Bağlantı arka plan | `SearchControl.PopupButtonMouseDownBackgroundGradientBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (bağlantı metni) | `SearchControl.PopupButtonMouseDownText` |

###  <a name="BKMK_TreeView"></a> Ağaç görünümleri  
Çözüm Gezgini, Sunucu Gezgini ve sınıf görünümü de dahil olmak üzere birkaç aracı windows renklerini renk adlarında tarafından denetlenen hiyerarşik bir kuruluş şeması uygulayan `TreeView` kategorisi. Ağaç görünümünde tüm öğeleri arka plan ve metin renkleri vardır. Alt öğeler yuvalanmış öğeleri öğesi genişletilmiş mi, yoksa daraltılmış mı olduğunu belirtmek karakterlerin de vardır.  

![Ağaç görünümü (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-147_treeviewredline.png "0303 147_TreeViewRedline")<br />Ağaç görünümü (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... herhangi bir yere hiyerarşik bir kuruluş görünümü uygulamanız gerekir. | ... her şey için bir ağaç görünümüne benzer değil. |
| | Belirtilen dışındaki... tüm arka plan/ön plan birlikte. |

**Ağaç görünümü öğesi: varsayılan durumu**

![Varsayılan ağaç görünümü öğesi](../../extensibility/ux-guidelines/media/0303-148_treeview.png "0303 148_TreeView")<br />Varsayılan ağaç görünümü öğesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `TreeView.Background` |
| Ön plan (metin) | `TreeView.Background` |
| Ön plan (karakter) | `TreeView.Glyph` |
| Kenarlık | Yok. |

**Ağaç görünümü öğesi: vurgulu durumu**

![Ağaç görünümü vurgulu maddesinde](../../extensibility/ux-guidelines/media/0303-149_treeviewhover.png "0303 149_TreeViewHover")<br />Ağaç görünümü vurgulu maddesinde

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `TreeView.Background` |  
| Ön plan (metin) | `TreeView.Background` |
| Ön plan (karakter) | `TreeView.GlyphMouseOver` |
| Kenarlık | Yok. |

**Ağaç görünümü öğesi: durumu sürükleyin**

![Ağaç görünümü öğesi Sürükle üzerinde üzerinden](../../extensibility/ux-guidelines/media/0303-150_treeviewdragover.png "0303 150_TreeViewDragOver")<br />Ağaç görünümü öğede sürükleyin üzerinden  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `TreeView.DragOverItem` |
| Ön plan (metin) | `TreeView.DragOverItem` |
| Ön plan (karakter) | `TreeView.DragOverItemGlyph` |
| Kenarlık | Yok. |

**Ağaç görünümü öğesi: Seçili, durumu odaklanmış**

![Seçili ve ağaç görünümü öğesi odaklanmış](../../extensibility/ux-guidelines/media/0303-151_treeviewfocused.png "0303 151_TreeViewFocused")<br />Seçilen ve odaklanmış ağaç görünümü öğesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `TreeView.SelectedItemActive` |
| Ön plan (metin) | `TreeView.SelectedItemActive` |
| Ön plan (karakter) | `TreeView.SelectedItemActiveGlyph` |
| Kenarlık | `TreeView.FocusVisualBorder` |

**Ağaç görünümü öğesi: Seçili, Odaksız durumu**  

![Seçilen ve Odaksız ağaç görünümü öğesi](../../extensibility/ux-guidelines/media/0303-152_treeviewunfocused.png "0303 152_TreeViewUnfocused")<br />Seçilen ve Odaksız ağaç görünümü öğesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `TreeView.SelectedItemInactive` |
| Ön plan (metin) | `TreeView.SelectedItemInactive` |
| Ön plan (karakter) | `TreeView.SelectedItemInactiveGlyph` |
| Kenarlık | Yok. |

**Ağaç görünümü öğesi: üzerine getirildiği, seçili ve durumu odaklanmış**

![Seçili ve ağaç görünümü öğesi gidildiğinde odaklanmış](../../extensibility/ux-guidelines/media/0303-153_treeviewfocusedhover.png "0303 153_TreeViewFocusedHover")<br />Seçilen ve odaklanmış ağaç görünümü vurgulu öğede  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `TreeView.SelectedItemActive` |
| Ön plan (metin) | `TreeView.SelectedItemActive` |
| Ön plan (karakter) | `TreeView.SelectedItemActiveGlyphMouseOver` |
| Kenarlık | `TreeView.FocusVisualBorder` |

**Ağaç görünümü öğesi: vurgulanan, seçili ve Odaksız durumu**

![Seçilen ve Odaksız ağaç görünümü vurgulu maddesinde](../../extensibility/ux-guidelines/media/0303-154_treeviewunfocusedhover.png "0303 154_TreeViewUnfocusedHover")<br />Seçilen ve Odaksız ağaç görünümü vurgulu maddesinde  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `TreeView.SelectedItemInactive` |
| Ön plan (metin) | `TreeView.SelectedItemInactive` |
| Ön plan (karakter) | `TreeView.SelectedItemActiveGlyphMouseOver` |
| Kenarlık | Yok. |

## <a name="shell-appearance"></a>Kabuk görünümü

### <a name="background"></a>Arka Plan  
Ortam arka plan iki katmandan oluşur. Tüm IDE kapsayan bir düz renk alt katmanıdır. Üst Katman komutu raf altında arasında aracı penceresi otomatik olarak gizle kanalları IDE sol ve sağ kenarlarının sığar. Üst ve alt arka plan katmanlarının açık ve koyu Temalar aynı renkte ayarlanır.  

![Visual Studio Kabuğu arka plan (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-187_shellbackgroundredline.png "0303 187_ShellBackgroundRedline")<br />Visual Studio Kabuğu arka plan (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| Visual Studio ortamı arka planını eşleştirmek istediğiniz... yerlerde. | ... bir dolgu olarak arka plan yüzeyleri olmayan yerleri. |
| | ön plan öğeleri yerleştirmek için... arka plan olarak. |

**Alt Katman Kabuk görünümü**

| Öğe | Belirteç adını: Category.color |
| --- | --- |  
| Arka Plan | `Environment.EnvironmentBackground` |

**Üst katman Kabuk görünümü**

> Gradyan Visual Studio 2013'ün açık ve koyu Tema rengi değer aynı kümesine durdurur.

| Öğe | Belirteç adını: Category.color |
| --- | --- |  
| Arka Plan | `Environment.EnvironmentBackgroundGradientBegin`<br />`Environment.EnvironmentBackgroundGradientEnd`<br />`Environment.EnvironmentBackgroundGradientMiddle1`<br />`Environment.EnvironmentBackgroundGradientMiddle2` |  

### <a name="command-shelf"></a>Komut raf  
İki belirteci adlarının komutu raf arka planlar için kullanılır: Burada menü çubuğunda bulunur ve için burada komut çubukları sit ayarlayın. Bir tek tek komut çubuğu grubu "Komut çubuğunda" bölümünde daha ayrıntılı olarak ele alınmıştır kendi arka plan rengi değeri içeriyor. Menü çubuğu ve komut çubuğundan metin sırasıyla menü ve komut çubuğu bölümlerde ele alınmıştır.  

![Visual Studio komut raf (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-188_commandshelfredline.png "0303 188_CommandShelfRedline")<br />Visual Studio komut raf (kırmızı çizgi)  

| Kullanım... | Kullanmayan... |
| --- | --- |
| menüleri ve araç çubuklarını nereye... için alanlar. | bir komut raf benzer olmayan... için alanlar. |
|... doğru arka plan/ön plan belirteç adı ile birlikte. | |

**Komut raf menü çubuğu**

> Gradyan Visual Studio 2013'ün açık ve koyu Tema rengi değer aynı kümesine durdurur.

| Öğe | Belirteç adını: Category.color |
| --- | --- |  
| Arka Plan | `Environment.CommandShelfHighlightGradientBegin`<br /><br />`Environment.CommandShelfHighlightGradientMiddle`<br />`Environment.CommandShelfHighlightGradientEnd` |

** Komutu raf komut çubuğu **

> Gradyan Visual Studio 2013'ün açık ve koyu Tema rengi değer aynı kümesine durdurur.

| Öğe | Belirteç adını: Category.color |
| --- | --- |  
| Arka Plan | `Environment.CommandShelfBackgroundGradientBegin`<br />`Environment.CommandShelfBackgroundGradientMiddle`<br />`Environment.CommandShelfBackgroundGradientEnd` |

## <a name="manifest-designer"></a>Bildirim Tasarımcısı  
Bildirim Tasarımcısı Windows 8 ve Windows Phone 8 projeleri bildirim dosyasında düzenlemek daha kolay bir yolu olarak tasarlanmıştır. Tüketimi için kullanılabilir paylaşılan çerçeve iken tasarım düzenini ve genel yapısı ve yönlendirme/gezinme sekmeleri renklerini eşleştirmek için uygun olabilir. Düzen ayrıntıları hakkında daha fazla bilgi için bkz: [Visual Studio için Düzen](../../extensibility/ux-guidelines/layout-for-visual-studio.md).  

![Bildirim Tasarımcısı (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-175_manifestdesignerredline.png "0303 175_ManifestDesignerRedline")<br />Bildirim Tasarımcısı (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| Bildirim Tasarımcısı benzer... tasarımcıları için. | ... altıdan fazla sekme varsa. |
| ... Genel sekmesini kullanarak yerine bir düzenleyici belge içinde üstündeki iyi denetler. | ... hiç kullanıcı Arabirimi için bildirim Tasarımcısı gibi yapılandırılmaz. |

**Bildirim Tasarımcısı seçili sekmesi: varsayılan durumu**

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `ManifestDesigner.TabActive` |
| Kenarlık | Yok. |

**Bildirim Tasarımcısı seçili açıklama bölmesinde: varsayılan durumu**

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `ManifestDesigner.DescriptionPane` |

**Bildirim Tasarımcısı seçili içerik sayfası: varsayılan durumu**

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `ManifestDesigner.Background` |
| İletişim yardımcı metin | `ManifestDesigner.WatermarkText`<br />(Bu belirteç adını kendi işlevini eşleşmiyor.) |

**Bildirim Tasarımcısı sekmesi: Seçili durumu**

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `ManifestDesigner.Tab.Inactive` |

**Bildirim Tasarımcısı sekmesi: vurgulu durumu**

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `ManifestDesigner.Tab.Mouseover` |

## <a name="command-structures"></a>Komut yapıları  

###  <a name="BKMK_CommandMenus"></a> Menüleri  
Menüleri, Visual Studio içinde çeşitli yerlerde oluşabilir: belge veya aracı Windows'da ya da sağ IDE boyunca çeşitli konumlarda katıştırılmış ana menü çubuğu. Diğer kullanıcı Arabirimi öğeleri ile ilişkili menüleri uygulamaları ilgili öğesi için bölümünde ele alınmıştır. Visual Studio ortamı tarafından sağlanan standart menü uygulama her zaman kullanmalısınız. Ancak, bazı ender durumlarda, standart Visual Studio menüler erişimi olmayabilir. Bu durumlarda, kullanıcı Arabirimi diğer menüleri Visual Studio ile tutarlı olduğundan emin olmak için aşağıdaki belirteci adları kullanın.  

![Visual Studio menü (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-000_menuredline.png "0303 000_MenuRedline")<br />Visual Studio menü (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... ne zaman özel bir menüyü oluşturmanız gerekir.| ... tek başına arka plan rengi. Her zaman arka plan/ön plan bileşimi belirtildiği şekilde kullanın. |
| ... Visual Studio menüleri eşleştirmek istediğiniz yeni bir kullanıcı Arabirimi bileşeni olduğunda.| |

#### <a name="menu-titles"></a>Menü başlığı  
Genellikle menü komut çubuğunda bulunduğunda arka plan, kenarlık ve başlık metni, hem de isteğe bağlı bir karakter menü başlıkları oluşur.  

![Menü başlığı (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-001_menutitleredline.png "0303 001_MenuTitleRedline")<br />Menü başlığı (kırmızı çizgi)  

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... her oluşturduğunuz özel menü başlığı. | ... herhangi bir şey için her zaman menü başlığı eşleşecek şekilde istemediğiniz. |
| | Belirtilen dışındaki... tüm arka plan/ön plan birlikte. |

**Menü başlığı: varsayılan durumu**

![Varsayılan menü başlığı](../../extensibility/ux-guidelines/media/0303-002_menutitledefault.png "0303 002_MenuTitleDefault")<br />Varsayılan menü başlığı

![Varsayılan karakter menü başlık](../../extensibility/ux-guidelines/media/0303-003_menutitlewithglyphdefault.png "0303 003_MenuTitleWithGlyphDefault")<br />Varsayılan menü başlığı karakterleriyle

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Yok. |
| Ön plan (metin) | `Environment.CommandBarTextActive` |
| Ön plan (karakter) | `Environment.CommandBarMenuGlyph` |
| Kenarlık | Yok. |

**Menü başlığı: vurgulu durumu**  

![Menü başlığı vurgulu üzerinde](../../extensibility/ux-guidelines/media/0303-004_menutitlehover.png "0303 004_MenuTitleHover")<br />Menü başlığı vurgulu üzerinde  

![Menü başlığı vurgulu üzerinde karakterleriyle](../../extensibility/ux-guidelines/media/0303-005_menutitlewithglyphhover.png "0303 005_MenuTitleWithGlyphHover")<br />Menü başlığı vurgulu üzerinde karakterleriyle

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.CommandBarMouseOverBackgroundBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.CommandBarTextHover` |
| Ön plan (karakter) | `Environment.CommandBarMenuMouseOverGlyph` |  
| Kenarlık | `Environment.CommandBarBorder` |

**Menü başlığı: durumu basılı**  

![Menü başlığı basılı](../../extensibility/ux-guidelines/media/0303-006_menutitlepressed.png "0303 006_MenuTitlePressed")<br />Basılı menü başlığı

![Menü başlığı karakterleriyle basılı](../../extensibility/ux-guidelines/media/0303-007_menutitlewithglyphpressed.png "0303 007_MenuTitleWithGlyphPressed")<br />Menü başlığı karakterleriyle basılı

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.CommandBarMenuBackgroundGradientBegin`<br/>(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.CommandBarTextActive` |
| Ön plan (karakter) | `Environment.CommandBarMenuMouseDownGlyph` |
| Kenarlık | `Environment.CommandBarMenuBorder`<br />(Yalnızca sol üst ve sağ tarafa.) |  

**Menü başlığı: devre dışı durum**  

![Menü başlığı karakterleriyle devre dışı](../../extensibility/ux-guidelines/media/0303-008_menutitlewithglyphdisabled.png "0303 008_MenuTitleWithGlyphDisabled")<br />Karakterleriyle devre dışı bırakılmış menü başlığı

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Yok. |
| Ön plan (metin) | `Environment.CommandBarTextInactive` |
| Ön plan (karakter) | `Environment.CommandBarTextInactive` |
| Kenarlık | Yok. |

#### <a name="menu-items"></a>Menü öğeleri
Tek tek menü öğesini menü metni ve bir isteğe bağlı simge, onay kutusunu veya alt simge oluşur. Arka plan ve metin rengi değişiklik vurgulu üzerinde. Bu renk belirteci bir arka plan/ön plan çiftidir.  

![Menü öğeleri kırmızı çizgi](../../extensibility/ux-guidelines/media/0303-009_menuitemredline.png "0303 009_MenuItemRedline")  

| Kullanım... | Kullanmayan...  |
|---|---|
| ... menü çubuğunu ya da komut çubuğunda'da, bir için herhangi bir aşağı açılan listeyi başlatılır. | ... herhangi aşağı açılan listesinde için başka bir bağlam. |
| | Belirtilen dışındaki... tüm arka plan/ön plan birlikte. |

**Menü öğeleri: varsayılan durumu**

![Menü öğeleri varsayılan](../../extensibility/ux-guidelines/media/0303-010_menudefault.png "0303 010_MenuDefault")<br />Varsayılan menü öğeleri  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.CommandBarMenuBackgroundGradientBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.CommandBarTextActive` |
| Ön plan (alt karakter) | `Environment.CommandBarMenuSubmenuGlyph` |
| Kenarlık | `Environment.CommandBarMenuBorder` |
| Simge kanal arka plan | `Environment.CommandBarMenuIconBackground` |
| Ayırıcı | `Environment.CommandBarMenuSeparator` |
| Gölge | `Environment.DropShadowBackground` |

**Menü öğeleri: denetlenir ve seçili durumları**  

![İşaretli menü](../../extensibility/ux-guidelines/media/0303-011_menuchecked.png "0303 011_MenuChecked")<br />Checked menü öğesi

![Seçili menü](../../extensibility/ux-guidelines/media/0303-012_menuselected.png "0303 012_MenuSelected")<br />Seçili menü öğesi    

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Onay işareti | `Environment.CommandBarCheckBox` |  
| Onay işareti arka plan | `Environment.CommandBarSelectedIcon` |  
| Simge arka plan | `Environment.CommandBarSelected` |
| Simge kenarlığı | `Environment.CommandBarSelectedBorder` |

**Menü öğeleri: vurgulu durumu**  

![Menü vurgulu](../../extensibility/ux-guidelines/media/0303-013_menuhover.png "0303 013_MenuHover")<br />Menü öğesini vurgulu

![İşaretli menü vurgulu](../../extensibility/ux-guidelines/media/0303-014_menuhoverchecked.png "0303 014_MenuHoverChecked")<br />Menü öğesinin üzerine gelindiğinde işaretli

![Seçili menü vurgulu](../../extensibility/ux-guidelines/media/0303-015_menuhoverselected.png "0303 015_MenuHoverSelected")<br />Seçili menü öğesini vurgulu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.CommandBarMenuItemMouseOver` |
| Ön plan (metin) | `Environment.CommandBarMenuItemMouseOver` |
| Ön plan (alt karakter) | `Environment.CommandBarMenuMouseOverSubmenuGlyph` |
| Onay işareti | `Environment.CommandBarCheckBoxMouseOver` |
| Onay işareti arka plan | `Environment.CommandBarHoverOverSelectedIcon` |
| Simge arka plan | `Environment.CommandBarHoverOverSelected` |
| Simge kenarlığı | `Environment.CommandBarHoverOverSelectedIconBorder` |

**Menü öğeleri: devre dışı durum**  

![Devre dışı menü](../../extensibility/ux-guidelines/media/0303-016_menudisabled.png "0303 016_MenuDisabled")<br />Devre dışı menü öğesi

![Menü devre dışı işaretli](../../extensibility/ux-guidelines/media/0303-017_menudisabledchecked.png "0303 017_MenuDisabledChecked")<br />Onay işareti ile devre dışı menü öğesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Ön plan (metin) | `Environment.CommandBarTextInactive` |
| Ön plan (alt karakter) | `Environment.CommandBarMenuSubmenuGlyph` |
| Onay işareti | `Environment.CommandBarCheckBoxDisabled` |
| Onay işareti arka plan | `Environment.CommandBarSelectedIconDisabled` |

### <a name="command-bars"></a>Komut çubukları  
Komut çubuğunda, birden fazla yerde Visual Studio IDE içinde özellikle komutu raf ve katıştırılmış aracı veya belge pencereleri yer alabilir.  

Genel olarak, Visual Studio ortamı tarafından sağlanan standart komut çubuğu uygulaması her zaman kullanın. Standart mekanizmasını kullanarak tüm visual ayrıntıları doğru görünür ve etkileşimli öğeler davrandığını tutarlı bir şekilde diğer Visual Studio komut çubuğu denetimleri ile sağlar. Ancak, kendi komut çubuğu oluşturmak için gerekli değilse, doğru aşağıdaki simge adları kullanarak stil emin olun.  

![Komut çubuğunda kırmızı çizgi](../../extensibility/ux-guidelines/media/0303-018_commandbarredline.png "0303 018_CommandBarRedline")<br />Komut çubuğunda (kırmızı çizgi)  

![Taşma düğmesini kırmızı çizgi](../../extensibility/ux-guidelines/media/0303-019_overflowbuttonredline.png "0303 019_OverflowButtonRedline")<br />Taşma düğmesi (kırmızı çizgi)  

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... katıştırılmış komut çubuğunda ihtiyacınız olduğu yerlerde, ancak standart Visual Studio komut çubuğu uygulaması kullanma sorunu yaşıyor. | Komut çubuğuna benzer olmayan... için kullanıcı Arabirimi öğeleri. |
| | belirteç adları olan dışındaki belirtilen... komut çubuğu bileşenleri için. |

#### <a name="command-bar-groups"></a>Komut çubuğu grupları  
Komut çubuğu grubu ilgili komut çubuğu denetimleri kümesini oluşur ve herhangi bir sayıda düğmeleri, düğmeler, aşağı açılan menüler, birleşik giriş kutuları veya menüleri bölme içerebilir. Bu denetimleri için renk ayrı belirteci adlarına göre düzenlenir ve tek tek başka bir yerde bu kılavuzda ele alınmıştır. Bir ayırıcı satır, bir komut çubuğu grubu ilgili alt gruplar bölmek için kullanılır.  

![Komut çubuğu grubu kırmızı çizgi](../../extensibility/ux-guidelines/media/0303-020_commandbargroupredline.png "0303 020_CommandBarGroupRedline")<br />Komut çubuğu grubu (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |  
| ... katıştırılmış komut çubuğunda ihtiyacınız olduğu yerlerde, ancak standart Visual Studio komut çubuğu uygulaması kullanma sorunu yaşıyor. | Komut çubuğuna benzer olmayan... için kullanıcı Arabirimi öğeleri. |
| | belirteç adları olan dışındaki belirtilen... komut çubuğu bileşenleri için. |

**Komut çubuğu Grup: varsayılan durumu**  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.CommandBarGradientBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Kenarlık | `Environment.CommandBarToolBarBorder` |
| tutamacını sürükleyin | `Environment.CommandBarDragHandle` |
| Ayırıcı | `Environment.CommandBarToolBarSeparator`<br />`Environment.CommandBarToolBarSeparatorHighlight` |

#### <a name="command-icons"></a>Komut simgeleri  
![Komut simgesinin kırmızı çizgi](../../extensibility/ux-guidelines/media/0303-021_commandiconredline1.png "0303 021_CommandIconRedline1")<br />Komut simgesinin (kırmızı çizgi)  

![Komut simgesinin metinle kırmızı çizgi](../../extensibility/ux-guidelines/media/0303-022_commandiconredline2.png "0303 022_CommandIconRedline2")<br />Komut simgesinin metinle (kırmızı çizgi)  

| Kullanım... | Kullanmayan... |
| --- | --- |
| bir komut çubuğunda yerleştirilecek... düğmeleri için. | ... denetimleri için belirteç adlarını sahip. |
| | Belirtilen dışındaki... tüm arka plan/ön plan birlikte. |

**Komut simgesinin: varsayılan durumu**  

![Komut simgesi varsayılan](../../extensibility/ux-guidelines/media/0303-023_commandicondefault.png "0303 023_CommandIconDefault")<br />Varsayılan komut simgesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Yok (komut çubuğu arka planından devralır) |
| Ön plan (metin) | `Environment.CommandBarTextActive` |
| Kenarlık | Yok |

**Komut simgesinin: varsayılan seçili duruma**

![Varsayılan, seçilen komut simgesinin](../../extensibility/ux-guidelines/media/0303-024_commandicondefaultselected.png "0303 024_CommandIconDefaultSelected")<br />Varsayılan, seçili komutu simgesi  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.CommandBarSelected` |
| Ön plan (metin) | `Environment.CommandBarTextSelected` |
| Kenarlık | `Environment.CommandBarSelectedBorder` |

**Komut simgesinin: hover veya odağı durumları**  

![Komut simgesinin vurgulu veya odak](../../extensibility/ux-guidelines/media/0303-025_commandiconhover.png "0303 025_CommandIconHover")<br />Vurgulu veya odağı komut simgesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.CommandBarMouseOverBackgroundBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.CommandBarTextHover` |
| Kenarlık | `Environment.CommandBarBorder` |

**Komut simgesinin: Seçili vurgulu veya odağı durumları**

![Komut simgesinin vurgulu veya odak seçili](../../extensibility/ux-guidelines/media/0303-026_commandiconhoverselected.png "0303 026_CommandIconHoverSelected")<br />Seçili komut simgesinin vurgulu veya odak

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.CommandBarHoverOverSelected` |
| Ön plan (metin) | `Environment.CommandBarTextHoverOverSelected` |
| Kenarlık | `Environment.CommandBarHoverOverSelectedIconBorder` |

 **Komut simgesinin: durumu basılı**  

![Komut simgesinin basılı](../../extensibility/ux-guidelines/media/0303-027_commandiconpressed.png "0303 027_CommandIconPressed")<br />Basılı komutu simgesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.CommandBarMouseDownBackgroundBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.CommandBarTextMouseDown` |
| Kenarlık | `Environment.CommandBarBorder` |

**Komut simgesinin: devre dışı durum**  

![Devre dışı bırakılmış komut simgesinin](../../extensibility/ux-guidelines/media/0303-028_commandicondisabled.png "0303 028_CommandIconDisabled")<br />Devre dışı komutu simgesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Yok (komut çubuğu arka planından devralır) |
| Ön plan (metin) | `Environment.CommandBarTextInactive` |
| Kenarlık | Yok |

####  <a name="BKMK_CommandComboBox"></a> Komut çubuğu birleşik giriş kutuları

> [!IMPORTANT]
> Birleşik giriş kutuları açılır listeleri benzerdir, ancak bir düzenlenebilir metin bölge içerir. Açılan bir düzenlenebilir metin bölge içermiyorsa için renk belirteçlerini kullanmak [aşağı açılan listeler çubuğu komutu](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_CommandDropDown).  

![Birleşik giriş kutusu çubuğu komutu kırmızı çizgi](../../extensibility/ux-guidelines/media/0303-029_comboboxredline.png "0303 029_ComboBoxRedline")<br />Komut çubuğu birleşik giriş kutusu (kırmızı çizgi)  

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... özel birleşik giriş kutuları oluştururken. | ... için herhangi bir şey her zaman komutu eşleşecek şekilde istemediğiniz çubuğu kullanıcı Arabirimi. |
| ... bir birleşik giriş kutusu benzer bir komut çubuğu denetiminin oluştururken. | ... stilde açılan kutuya erişimi olduğunda. |

**Komut çubuğu birleşik giriş kutusu giriş alanı: varsayılan durumu**

![Komut çubuğu birleşik giriş kutusu giriş alanı](../../extensibility/ux-guidelines/media/0303-030_comboboxinputfield.png "0303 030_ComboBoxInputField")<br />Komut çubuğu birleşik giriş kutusu giriş alanı  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ComboBoxBackground` |
| Ön plan (metin) | `Environment.ComboBoxText` |
| Kenarlık | `Environment.ComboBoxBorder` |
| Ayırıcı | Ayırıcı |

**Komut çubuğu açılır düğmesi: varsayılan durumu**  

![Birleşik giriş kutusu açılan&#45;düğmesini basılı](../../extensibility/ux-guidelines/media/0303-031_comboboxdropdownbutton.png "0303 031_ComboBoxDropdownButton")<br />Komut çubuğu açılır düğmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Yok (komut çubuğu arka planından devralır) |
| Ön plan (karakter) | `Environment.ComboBoxGlyph` |

**Komut çubuğu açılır listesi: varsayılan durumu**

![Komut çubuğu açılır listesi](../../extensibility/ux-guidelines/media/0303-032_comboboxdropdownlist.png "0303 032_ComboBoxDropdownList")<br />Komut çubuğu açılır listesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ComboBoxPopupBackgroundBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.ComboBoxItemText` |
| Kenarlık | `Environment.ComboBoxPopupBorder` |

**Komut çubuğu birleşik giriş kutusu giriş alanı: vurgulu durumu**  

![Komut çubuğu birleşik giriş kutusu giriş alanı vurgulu üzerinde](../../extensibility/ux-guidelines/media/0303-033_comboboxinputfieldhover.png "0303 033_ComboBoxInputFieldHover")<br />Komut çubuğu birleşik giriş kutusu giriş alanı vurgulu üzerinde  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ComboBoxMouseOverBackgroundBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.ComboBoxMouseOverText` |
| Kenarlık | `Environment.ComboBoxMouseOverBorder` |
| Ayırıcı | `Environment.ComboBoxMouseOverSeparator` |

 **Komut çubuğu açılır düğmesi: vurgulu durumu**  

![Komut çubuğu açılan düğmesine vurgulu](../../extensibility/ux-guidelines/media/0303-034_comboboxdropdownbuttonhover.png "0303 034_ComboBoxDropdownButtonHover")<br />Komut çubuğu açılan düğmesine vurgulu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ComboBoxButtonMouseOverBackground` |
| Ön plan (karakter) | `Environment.ComboBoxMouseOverGlyph` |

**Komut çubuğu açılır listesi: vurgulu durumu**

 ![Komut çubuğu aşağı açılan listede vurgulu](../../extensibility/ux-guidelines/media/0303-035_comboboxdropdownlisthover.png "0303 035_ComboBoxDropdownListHover")<br />Komut çubuğu aşağı açılan listede vurgulu  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka plan (menü öğesi) | `Environment.ComboBoxItemMouseOverBackground` |
| Ön plan (metin) | `Environment.ComboBoxItemMouseOverText` |
| Kenarlık (menü öğesi) | `Environment.ComboBoxItemMouseOverBorder` |

 **Komut çubuğu birleşik giriş kutusu giriş alanı: durumu odaklanmış**  

![Birleşik giriş kutusu giriş alanı çubuğu komutu odaklanmış](../../extensibility/ux-guidelines/media/0303-036_comboboxinputfieldfocused.png "0303 036_ComboBoxInputFieldFocused")<br />Komut çubuğu birleşik giriş kutusu giriş alanı odaklanmış

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ComboBoxFocusedBackground` |
| Ön plan (metin) | `Environment.ComboBoxFocusedText` |
| Kenarlık | `Environment.ComboBoxFocusedBorder` |
| Ayırıcı | `Environment.ComboBoxFocusedButtonSeparator` |

**Komut çubuğu açılır düğmesi: durumu odaklanmış**  

![Komut çubuğu açılan düğmesine odaklanmış](../../extensibility/ux-guidelines/media/0303-037_comboboxdropdownbuttonfocused.png "0303 037_ComboBoxDropdownButtonFocused")<br />Aşağı açılan düğme çubuğu odaklanmış komutu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ComboBoxFocusedButtonBackground` |
| Ön plan (karakter) | `Environment.ComboBoxFocusedGlyph` |

 **Komut çubuğu birleşik giriş kutusu giriş alanı: durumu basılı**  

![Komut birleşik giriş kutusu giriş alanı basılı](../../extensibility/ux-guidelines/media/0303-038_comboboxinputfieldpressed.png "0303 038_ComboBoxInputFieldPressed")<br />Komut çubuğu birleşik giriş kutusu giriş alanı basılı

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ComboBoxMouseDownBackground` |
| Ön plan (metin) | `Environment.ComboBoxMouseDownText` |
| Kenarlık | `Environment.ComboBoxMouseDownBorder` |
| Ayırıcı | `Environment.ComboBoxMouseDownSeparator` |

**Komut çubuğu açılır düğmesi: durumu basılı**

![Komut çubuğu açılan düğmesine basıldığında](../../extensibility/ux-guidelines/media/0303-039_comboboxdropdownbuttonpressed.png "0303 039_ComboBoxDropdownButtonPressed")<br />Komut çubuğu açılan düğmesine basıldığında  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ComboBoxButtonMouseDownBackground` |
| Ön plan (karakter) | `Environment.ComboBoxMouseDownGlyph` |

**Komut çubuğu birleşik giriş kutusu giriş alanı: devre dışı durum**  

![Birleşik giriş kutusu giriş alanı çubuğu komutu devre dışı](../../extensibility/ux-guidelines/media/0303-041_comboboxinputfielddisabled.png "0303 041_ComboBoxInputFieldDisabled")<br />Birleşik giriş kutusu giriş alanı çubuğu devre dışı komutu  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ComboBoxDisabledBackground` |
| Ön plan (metin) | `Environment.ComboBoxDisabledText` |
| Kenarlık | `Environment.ComboBoxDisabledBorder` |
| Ayırıcı | Ayırıcı |

**Komut çubuğu açılır düğmesi: devre dışı durum**  

![Komut çubuğu açılır düğmesi devre dışı](../../extensibility/ux-guidelines/media/0303-040_comboboxdropdownbuttondisabled.png "0303 040_ComboBoxDropdownButtonDisabled")<br />Aşağı açılan düğme çubuğu devre dışı komutu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Yok. |
| Ön plan (karakter) | `Environment.ComboBoxDisabledGlyph` |

####  <a name="BKMK_CommandDropDown"></a> Komut çubuğu aşağı açılan listeler

> [!IMPORTANT]
>  Aşağı açılan listeler birleşik giriş kutuları benzerdir, ancak düzenlenebilir metin bölgeler eksik. Düzenlenebilir metin bölge, açılan içeriyorsa, renk belirteçleri kullanmanız [birleşik giriş kutuları çubuğu komutu](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_CommandComboBox).  

![Komut açılır (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-042_dropdownredline.png "0303 042_DropdownRedline")<br />Komut açılır (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... özel açılan liste denetimleri oluştururken. | ... her şey için aşağı açılan listesine benzer değil. |
| | ... birleşik giriş kutuları veya Bölünmüş düğme için. |   

**Komut çubuğu aşağı açılan seçimi alanını: varsayılan durumu**  

![Varsayılan komut çubuğu aşağı açılan seçimi alanını](../../extensibility/ux-guidelines/media/0303-043_dropdownselectionfield.png "0303 043_DropdownSelectionField")<br />Varsayılan komut çubuğu aşağı açılan seçimi alan  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.DropDownBackground` |
| Ön plan (metin) | `DropDownText` |
| Kenarlık | `DropDownBorder` |
| Ayırıcı | Ayırıcı |

**Komut çubuğu açılır düğmesi: varsayılan durumu**

![Varsayılan komut çubuğu açılan düğmesine](../../extensibility/ux-guidelines/media/0303-044_dropdownbutton.png "0303 044_DropdownButton")<br />Varsayılan komut çubuğu açılır düğmesi  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Yok. |
| Ön plan (karakter) | `Environment.DropDownGlyph` |

**Komut çubuğu açılır listesi: varsayılan durumu**

![Varsayılan komut çubuğu açılır liste](../../extensibility/ux-guidelines/media/0303-045_dropdownlist.png "0303 045_DropdownList")<br />Varsayılan komut çubuğu açılır listesi  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.DropDownPopupBackgroundBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.ComboBoxItemText` |
| Kenarlık | `Environment.DropDownPopupBorder` |
| Gölge | `Environment.DropShadowBackground` |

**Komut çubuğu aşağı açılan seçimi alanını: vurgulu durumu**  

![Komut çubuğu açılır seçim alanında vurgulu](../../extensibility/ux-guidelines/media/0303-046_dropdownselectionfieldhover.png "0303 046_DropdownSelectionFieldHover")<br />Komut çubuğu açılır seçim alanında vurgulu  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.DropDownMouseOverBackgroundBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.DropDownMouseOverText` |
| Kenarlık | `Environment.DropDownMouseOverBorder` |
| Ayırıcı | `Environment.DropDownButtonMouseOverSeparator` |

**Komut çubuğu açılır düğmesi: vurgulu durumu**  

![Komut çubuğu açılan düğmesine vurgulu](../../extensibility/ux-guidelines/media/0303-047_dropdownbuttonhover.png "0303 047_DropdownButtonHover")<br />Komut çubuğu açılan düğmesine vurgulu  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.DropDownButtonMouseOverBackground` |
| Ön plan (karakter) | `Environment.DropDownMouseOverGlyph` |

**Komut çubuğu açılır listesi: vurgulu durumu**  

![Komut çubuğu aşağı açılan listede vurgulu](../../extensibility/ux-guidelines/media/0303-048_dropdownlisthover.png "0303 048_DropdownListHover")<br />Komut çubuğu aşağı açılan listede vurgulu  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka plan (menü öğesi) | `Environment.ComboBoxItemMouseOverBackground` |
| Ön plan (metin) | `Environment.ComboBoxItemMouseOverText` |
| Kenarlık (menü öğesi) | `Environment.ComboBoxItemMouseOverBorder` |

 **Komut çubuğu aşağı açılan seçimi alanını: durumu basılı**  

![Bırakma&#45;tuşunu basılı seçimi alanını](../../extensibility/ux-guidelines/media/0303-049_dropdownselectionfieldpressed.png "0303 049_DropdownSelectionFieldPressed")<br />Komut aşağı açılan seçimi alanını basılı

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.DropDownMouseDownBackground` |
| Ön plan (metin) | `Environment.DropDownMouseDownText` |
| Kenarlık | `Environment.DropDownMouseDownBorder` |
| Ayırıcı | `Environment.DropDownButtonMouseDownSeparator` |

**Komut çubuğu açılır düğmesi: durumu basılı**

![Komut çubuğu açılan düğmesine basıldığında](../../extensibility/ux-guidelines/media/0303-050_dropdownbuttonpressed.png "0303 050_DropdownButtonPressed")<br />Komut çubuğu açılan düğmesine basıldığında  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.DropDownButtonMouseDownBackground` |
| Ön plan (karakter) | `Environment.DropDownMouseDownGlyph` |

**Komut çubuğu aşağı açılan seçimi alanını: devre dışı durum**  

![Komut çubuğu aşağı açılan seçimi alanını devre dışı](../../extensibility/ux-guidelines/media/0303-051_dropdownselectionfielddisabled.png "0303 051_DropdownSelectionFieldDisabled")<br />Aşağı açılan seçimi alanını çubuğu devre dışı komutu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.DropDownDisabledBackground` |
| Ön plan (metin) | `Environment.DropDownDisabledText` |
| Kenarlık | `Environment.DropDownDisabledBorder` |
| Ayırıcı | Ayırıcı |

**Komut çubuğu açılır düğmesi: devre dışı durum**

![Komut çubuğu açılır düğmesi devre dışı](../../extensibility/ux-guidelines/media/0303-052_dropdownbuttondisabled.png "0303 052_DropdownButtonDisabled")<br />Aşağı açılan düğme çubuğu devre dışı komutu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Yok |
| Ön plan (karakter) | `Environment.DropDownDisabledGlyph` |

#### <a name="command-bar-split-buttons"></a>Komut çubuğu düğmelerini bölme
Bölünmüş düğme birçok belirteci adları düğmeler, menüler ve komut çubuğu metni gibi diğer komut çubuğu denetimleri ile paylaşır. Burada tüm gerekli eylem ve açılan düğmesine belirteci adları kolaylık sağlamak için yinelenir. Bölünmüş düğme açılan listeleri olan uygulamaları [menü çubuğu komutunu](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_CommandMenus).  

![Bölünmüş düğme kırmızı çizgi](../../extensibility/ux-guidelines/media/0303-053_splitbuttonredline.png "0303 053_SplitButtonRedline")<br />Komut çubuğu düğmesi bölme (kırmızı çizgi)  

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... özel Bölünmüş düğme oluştururken. | ... diğer tür düğmeleri için. |
| | Belirtilen dışındaki... tüm arka plan/ön plan birlikte. |

**Komut çubuğunda Bölünmüş düğme: varsayılan durumu**  

![Varsayılan komut çubuğu Bölünmüş düğme](../../extensibility/ux-guidelines/media/0303-054_splitbutton.png "0303 054_SplitButton")<br />Bölünmüş düğme çubuğu varsayılan komutu  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Yok. |
| Ön plan (metin) | `Environment.CommandBarTextActive` |
| Ön plan (karakter) | `Environment.CommandBarSplitButtonGlyph` |
| Kenarlık | Yok |
| Ayırıcı | Yok |

**Komut çubuğunda Bölünmüş düğme: vurgulu durumu**  

![Komut çubuğunda bölme vurgulu düğmesinde](../../extensibility/ux-guidelines/media/0303-055_splitbuttonhover.png "0303 055_SplitButtonHover")<br />Komut çubuğu vurgulu düğmesinde bölme

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.CommandBarMouseOverBackgroundBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.CommandBarTextHover` |
| Ön plan (karakter) | `Environment.CommandBarSplitButtonMouseOverGlyph` |
| Kenarlık | `Environment.CommandBarBorder` |
| Ayırıcı | `Environment.CommandBarSplitButtonSeparator` |

**Komut çubuğunda Bölünmüş düğme: durumu basılı**  

![Komut çubuğu bölme düğmesine basıldığında](../../extensibility/ux-guidelines/media/0303-056_splitbuttonpressed.png "0303 056_SplitButtonPressed")<br />Bölünmüş düğme çubuğu basılı komutu  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.CommandBarMouseDownBackgroundBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.CommandBarTextMouseDown` |
| Ön plan (karakter) | `Environment.CommandBarSplitButtonMouseDownGlyph` |
| Kenarlık | `Environment.CommandBarBorder` |
| Ayırıcı | Yok |

**Komut çubuğunda Bölünmüş düğme: devre dışı durum**

![Komut çubuğu bölme düğmesi devre dışı](../../extensibility/ux-guidelines/media/0303-057_splitbuttondisabled.png "0303 057_SplitButtonDisabled")<br />Bölünmüş düğme devre dışı bırakılmış bir komut çubuğu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Yok |
| Ön plan (metin) | `Environment.ComboBoxItemTextInactive` |
| Ön plan (karakter) | `Environment.CommandBarTextInactive` |
| Kenarlık | Yok |
| Ayırıcı | Yok |

#### <a name="command-bar-more-options-and-overflow-buttons"></a>'Daha Seçenekleri' ve 'Overflow' düğmelerini komutu  
"Daha fazla seçenek" düğmesine bir komut çubuğu Grup özelleştirilebilir ekleyerek veya ilişkili komut çubuğu düğmelerini kaldırarak olduğunda kullanılır. Bir komut çubuğu yatay boşluk eksikliği nedeniyle kesildi ve görüntülenemiyor komut çubuğu düğmelerini içeren bir menü çubuğunda gösterir "Taşma" düğmesi görünür. Bu iki düğmeleri için renk belirteci adlarının aynı kümesi tarafından denetlenir.  

![Komut çubuğu 'Daha fazla seçenek' düğmesini (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-058_moreoptionsredline.png "0303 058_MoreOptionsRedline")<br />Komut çubuğu 'Daha fazla seçenek' düğmesini (kırmızı çizgi)  

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... Özel 'daha Seçenekleri' veya 'Overflow' düğmeleri için. | 'Daha Seçenekleri' veya 'Overflow' düğmesini benzer işlevlere sahip olmayan... düğmeleri için. |

**Komut çubuğu 'Daha Seçenekleri' ve 'Dışında'Overflow ' düğmeleri: varsayılan durumu**  

![Varsayılan komut çubuğu 'Daha fazla seçenek' düğmesini](../../extensibility/ux-guidelines/media/0303-059_moreoptions.png "0303 059_MoreOptions")<br />Komut çubuğunda 'Daha fazla seçenek' düğmesini varsayılan

![Varsayılan komut çubuğu 'Dışında'Overflow ' düğmesini](../../extensibility/ux-guidelines/media/0303-060_overflow.png "0303 060_Overflow")<br />Varsayılan komut çubuğu 'Dışında'Overflow ' düğmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.CommandBarOptionsBackground` |
| Ön plan (karakter) | `Environment.CommandBarOptionsGlyph` |

**Komut çubuğu 'Daha Seçenekleri' ve 'Dışında'Overflow ' düğmeleri: vurgulu durumu**

![Komut çubuğu vurgulu 'Daha fazla seçenek' düğmesini](../../extensibility/ux-guidelines/media/0303-061_moreoptionshover.png "0303 061_MoreOptionsHover")<br />Vurgulu 'Daha fazla seçenek' düğmesini çubuğu komutu  

![Komut çubuğu 'Dışında'Overflow ' düğmesine vurgulu](../../extensibility/ux-guidelines/media/0303-062_overflowoptions.png "0303 062_OverflowOptions")<br />Komut çubuğu 'Dışında'Overflow ' düğmesine vurgulu   

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.CommandBarOptionsMouseOverBackgroundBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (karakter) | `Environment.CommandBarOptionsMouseDownGlyph` |

**Komut çubuğu 'Daha Seçenekleri' ve 'Dışında'Overflow ' düğmeleri: durumu basılı**  

![Komut çubuğu 'Daha fazla seçenek' düğmesini basılı](../../extensibility/ux-guidelines/media/0303-063_moreoptionspressed.png "0303 063_MoreOptionsPressed")<br />Komut çubuğu 'Daha fazla seçenek' düğmesini basılı  

![Taşma basılı](../../extensibility/ux-guidelines/media/0303-064_overflowpressed.png "0303 064_OverflowPressed")<br />Komut çubuğu 'Dışında'Overflow ' düğmesine basıldığında  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.CommandBarOptionsMouseDownBackgroundBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (karakter) | `Environment.CommandBarOptionsMouseDownGlyph` |

## <a name="document-windows"></a>Belge pencereleri  
Visual Studio ortamı tarafından sağlanan çünkü belge pencereleri çoğaltmak için gerek yoktur. Ancak, böylece UI her zaman Visual Studio ortamında bu kısmı tutarlı görünür belge Windows'ta kullanılan renkleri kullanmasına istediğiniz karar verebilirsiniz.  

Belge penceresi renk belirteçleri kullanırken, benzer öğeleri için yalnızca ve her zaman çiftler halinde kullanma konusunda dikkatli olun. Yapmazsanız, kullanıcı Arabiriminde beklenmeyen sonuçlar alabilirsiniz.  

### <a name="document-window-frames"></a>Belge pencere çerçeveleri  
Belge pencereleri IDE içinde yerleşik ya da ayrı bir pencere olarak kayan olabilir. Bir belge penceresi dışında IDE kayan, hala bir belge iyi bulunur ve arka plan, kenarlık, metin ve IDE parçası olduğunda, aynı sekmesi renkleri vardır. Ancak, belgeyi kendi arka plan, kenarlık ve metin renkleri sahip bir çerçeve içinde bulunur. Araç pencereleri belge iyi yerleştirildiğinde, bunların davranışı ve sekmeleri rengini belge penceresi belirteci adlarından devralır.  

![Yerleşik belge penceresine (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-065_dockeddocumentwindowredline.png "0303 065_DockedDocumentWindowRedline")<br />Yerleşik belge penceresine (kırmızı çizgi)  

![Kayan belge penceresine (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-066_floatingdocumentwindowredline.png "0303 066_FloatingDocumentWindowRedline")<br />Kayan belge penceresine (kırmızı çizgi)  

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... herhangi bir yere belge penceresine eşleştirmek istediğiniz UI oluşturmakta olduğunuz. | ... otomatik olarak değiştirmek için istemediğiniz hiç kullanıcı Arabirimi için bir tema güncelleştirmesi Kabuk bulunuyor. |

**Yerleşik veya kayan belge penceresine: varsayılan durumu**  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Belge türüne bağlıdır |
| Ön plan (metin) | Belge türüne bağlıdır |
| Kenarlık | `Environment.ToolWindowBorder` |

**Odaklanmış, belge pencere çerçevesi kayan: varsayılan durumu**

![Odaklanmış, varsayılan belge pencere çerçevesi kayan](../../extensibility/ux-guidelines/media/0303-067_framefocused.png "0303 067_FrameFocused")<br />Odaklanmış, varsayılan belge pencere çerçevesi kayan

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ToolWindowFloatingFrame` |
| Ön plan (metin) | `Environment.ToolWindowFloatingFrame` |
| Ön plan (karakter) | `Environment.RaftedWindowButtonActiveGlyph` |
| Kenarlık | `Environment.MainWindowActiveDefaultBorder` |
| Kenarlık (karakter) | `Environment.RaftedWindowButtonActiveBorder`<br />(Saydam ayarlamak) |

**Belge Odaksız, kayan pencere çerçevesi: varsayılan durumu**  

![Varsayılan Belge Odaksız, kayan pencere çerçevesi](../../extensibility/ux-guidelines/media/0303-068_frameunfocused.png "0303 068_FrameUnfocused")<br />Varsayılan Belge Odaksız, kayan pencere çerçevesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ToolWindowFloatingFrameInactive` |
| Ön plan (metin) | `Environment.ToolWindowFloatingFrameInactive` |
| Ön plan (karakter) | `Environment.RaftedWindowButtonInactiveGlyph` |
| Kenarlık | `Environment.MainWindowInactiveBorder` |
| Kenarlık (karakter) | `Environment.RaftedWindowButtonInactiveBorder`<br />(Saydam ayarlamak) |

**Odaklanmış, belge pencere çerçevesi kayan: vurgulu durumu**

![Odaklanmış, belge pencere çerçevesi gidildiğinde kayan](../../extensibility/ux-guidelines/media/0303-069_framefocusedhover.png "0303 069_FrameFocusedHover")<br />Odaklanmış, belge pencere çerçevesi gidildiğinde kayan  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka plan (karakter) | `Environment.RaftedWindowButtonHoverActive` |
| Ön plan (karakter) | `Environment.RaftedWindowButtonHoverActiveGlyph` |
| Kenarlık (karakter) | `Environment.RaftedWindowButtonHoverActiveBorder` |

**Belge Odaksız, kayan pencere çerçevesi: vurgulu durumu**  

![Vurgulu Odaksız, kayan bir belge pencere çerçevesi](../../extensibility/ux-guidelines/media/0303-070_frameunfocusedhover.png "0303 070_FrameUnfocusedHover")<br />Odaksız, belge pencere çerçevesi gidildiğinde kayan

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka plan (karakter) | `EnvironmentRaftedWindowButtonHoverInactive` |
| Ön plan (karakter) | `Environment.RaftedWindowButtonHoverInactiveGlyph` |
| Kenarlık (karakter) | `Environment.RaftedWindowButtonHoverInactiveBorder` |

**Odaklanmış, belge pencere çerçevesi kayan: durumu basılı**  

![Odaklanmış, belge pencere çerçevesi makinesinde kayan](../../extensibility/ux-guidelines/media/0303-071_framefocusedpressed.png "0303 071_FrameFocusedPressed")<br />Odaklanmış, belge pencere çerçevesi makinesinde kayan

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka plan (karakter) | `Environment.RaftedWindowButtonDown` |
| Ön plan (karakter) | `Environment.RaftedWindowButtonDownGlyph` |
| Kenarlık (karakter) | `Environment.RaftedWindowButtonDownBorder` |

### <a name="document-tabs"></a>Belge sekmeleri  
Belge sekmeleri kalmaya devam hangi belgeleri hangisinin seçili geçerli değil veya etkin belgeyi birlikte şu anda açık olduğunu belirtmek için sekme kanal. Aracı windows, ayrıca kullanıcı var. bunları yerleştirir, belge sekmesini kanalda yerleştirilmiş. Bu durumda, belge pencereleri aynı sekmesi renkleri kullanırlar. Kullanıcı Arabirimi, oluşturuyorsanız, her zaman (Tema güncelleştirmeleri veya yeni temalar yüklediyseniz dahil) belge penceresi renkleri eşleşen, ardından bu renk belirteçleri başvuru istiyor.  

![Belge sekmeleri (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-072_documenttabredline.png "0303 072_DocumentTabRedline")<br />Belge sekmeleri (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... herhangi bir yere belge sekmeleri eşleşen ve tema güncelleştirmeleri veya yeni Tema renkleri otomatik olarak seçmek istediğiniz UI oluşturmakta olduğunuz. | Kabuk güncelleştirme tema içinde olduğunda otomatik olarak değiştirmek için istemediğiniz... hiç kullanıcı Arabirimi için. |

#### <a name="open-document-tabs"></a>Açık belge sekmeleri  
Her açık belge adını görüntüler belge sekmesini kanalda bir sekme sahiptir. Belge ya da seçilebilir veya arka planda açın ve bu durumlar sekmeleri yansıtır:  

-   Seçili sekme belgede iyi görüntülenmekte belgeyi temsil eder. Seçili sekme belgenin üst kenarı arasında iyi genişleten bir belge kenarlığa sahip.  

-   Arka plan sekmeleri şu anda seçili sekme olmayan herhangi bir belge sekme kümesidir. Tıklattıktan sonra seçili sekme olur ve tüm arka plan, kenarlık ve metin renklerini Bu belirteci adlarından alma.  

![Açık belge sekmesini (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-073_opendocumenttabredline.png "0303 073_OpenDocumentTabRedline")<br />Açık belge sekmesini (kırmızı çizgi)

| Kullanım...  | Kullanmayan... |
| --- | --- |
| ... özel belge sekmeleri oluştururken. | ... (Önizleme) geçici sekmeler için. |
| | ... varsa otomatik olarak değiştirmek istemiyorsanız hiç kullanıcı Arabirimi için bir tema güncelleştirmesi Kabuk bulunuyor. |

**Seçili, odaklanmış bir belge sekmesi**  

![Seçili, belge sekmesini odaklanmış](../../extensibility/ux-guidelines/media/0303-074_selectedtabfocused.png "0303 074_SelectedTabFocused")<br />Seçili, odaklanmış bir belge sekmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.FileTabSelectedGradientTop`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.FileTabSelectedText` |
| Kenarlık | `Environment.FileTabSelectedBorder`<br />(Aynı renk arka plan olarak ayarlayın.) |
| Belge kenarlığı | `Environment.FileTabDocumentBorderBackground` |

**Seçili, Odaksız belge sekmesi**

![Seçili, Odaksız belge sekmesini](../../extensibility/ux-guidelines/media/0303-075_selectedtabunfocused.png "0303 075_SelectedTabUnfocused")<br />Seçili, Odaksız belge sekmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.FileTabInactiveGradientTop`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.FileTabInactiveText` |
| Kenarlık | `Environment.FileTabInactiveBorder`<br />(Aynı renk arka plan olarak ayarlayın.) |
| Belge kenarlığı | `Environment.FileTabInactiveDocumentBorderBackground` |

**Arka plan belge sekmesi: varsayılan durumu**  

![Varsayılan arka plan belge sekmesi](../../extensibility/ux-guidelines/media/0303-076_backgroundtab.png "0303 076_BackgroundTab")<br />Varsayılan arka plan belge sekmesi  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.FileTabBackground` |
| Ön plan (metin) | `Environment.FileTabText` |
| Kenarlık | `Environment.FileTabBorder`<br />(Aynı renk arka plan olarak ayarlayın.) |

**Arka plan belge sekmesi: vurgulu durumu**  

![Arka plan belge vurgulu sekmesinde](../../extensibility/ux-guidelines/media/0303-077_backgroundtabhover.png "0303 077_BackgroundTabHover")<br />Arka plan belge vurgulu sekmesinde  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.FileTabHotGradientTop`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.FileTabHotText` |
| Kenarlık | `Environment.FileTabHotBorder`<br />(Aynı renk arka plan olarak ayarlayın.) |

#### <a name="preview-tab"></a>Önizleme sekmesi  
"Geçici" sekmesini olarak da bilinir. Kullanıcı Solution Explorer araç penceresi bir öğeyi tıklattığında Önizleme sekmesi belge sekmesini kanal sağ tarafında görünür. Bir belgeyi önizleme davranır ve kullanıcı belgenin belge sekmesini kanal sol tarafındaki açık tutmak için seçeneği de sunar. Aynı anda yalnızca bir önizleme sekmesi açık açık olabilir. Önizleme sekmeleri sahip hem de arka plan ve seçili durumları açık sekmelerinizden ister ve bunların etkin durumda odaklanmış veya Odaksız olabilir.  

![Önizleme sekmesi (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-078_previewtabredline.png "0303 078_PreviewTabRedline")<br />Önizleme sekmesi (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... her yerden oluşturduğunuz geçici Önizleme ve geçerli Önizleme sekme rengi eşleştirmek için bazı öğe istiyorsanız. | Belge veya geçici olmayan sekme herhangi bir tür için... (Önizleme). |
| | ... varsa otomatik olarak değiştirmek istemiyorsanız hiç kullanıcı Arabirimi için bir tema güncelleştirmesi Kabuk bulunuyor. |

**Odaklanmış, seçilen Önizleme sekmesi**  

![Odaklanmış, seçilen Önizleme sekmesi](../../extensibility/ux-guidelines/media/0303-079_previewtabfocused.png "0303 079_PreviewTabFocused")<br />Odaklanmış, seçilen Önizleme sekmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.FileTabProvisionalSelectedActive` |
| Ön plan (metin) | `Environment.FileTabProvisionalSelectedActiveForeground` |
| Kenarlık | `Environment.FileTabProvisionalSelectedActiveBorder`<br />(Aynı renk arka plan olarak ayarlayın.) |
| Belge kenarlığı | `Environment.FileTabProvisionalSelectedActiveBorder` |

**Odaksız, seçilen Önizleme sekmesi**  

![Odaksız, seçilen Önizleme sekmesi](../../extensibility/ux-guidelines/media/0303-080_previewtabunfocused.png "0303 080_PreviewTabUnfocused")<br />Odaksız, seçilen Önizleme sekmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.FileTabProvisionalSelectedInactive` |
| Ön plan (metin) | `Environment.FileTabProvisionalSelectedInactiveForeground` |
| Kenarlık | `Environment.FileTabProvisionalSelectedInactiveBorder` |
| Belge kenarlığı | `Environment.FileTabProvisionalSelectedInactiveBorder` |

**Arka plan Önizleme sekmesi: varsayılan durumu**  

![Varsayılan arka plan Önizleme sekmesi](../../extensibility/ux-guidelines/media/0303-081_previewbackgroundtab.png "0303 081_PreviewBackgroundTab")<br />Varsayılan arka plan Önizleme sekmesi  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.FileTabProvisionalInactive` |
| Ön plan (metin) | `Environment.FileTabProvisionalInactiveForeground` |
| Kenarlık | `Environment.FileTabProvisionalInactiveBorder`<br />(Aynı renk arka plan olarak ayarlayın.) |

**Arka plan Önizleme sekmesi: vurgulu durumu**  

![Arka plan Önizleme vurgulu sekmesinde](../../extensibility/ux-guidelines/media/0303-082_previewbackgroundtabhover.png "0303 082_PreviewBackgroundTabHover")<br />Arka plan Önizleme vurgulu sekmesinde  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.FileTabProvisionalHover` |
| Ön plan (metin) | `Environment.FileTabProvisionalHoverForeground` |
| Kenarlık | `Environment.FileTabProvisionalHoverBorder`<br />(Aynı renk arka plan olarak ayarlayın.) |

#### <a name="document-overflow-button"></a>Belge Taşma düğmesi  
Belge Taşma düğmesine bir veya daha fazla belge olup olmamasına bakılmaksızın açık, mevcut ise tüm belge sekmeleri uyacak şekilde geçerli yapılandırmada dikey alanı yok. Tarafından denetlenen belge taşma açılır menü [menü çubuğu komutunu](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_CommandMenus) renkler, görünür ve gizli, açık olan tüm belgeler ve tüm açık belgeleri olmanıza bağlı olarak taşma karakter değişiklikleri listesini görüntüler Sekme kanalda görüntülenir.  

![Belge taşma düğmesini (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-083_overflowredline.png "0303 083_OverflowRedline")<br />Belge taşma düğmesini (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... özel belge taşma düğmesini oluştururken. | taşma düğmesini için benzer olmayan... için kullanıcı Arabirimi. |
| | ... komut çubuğu taşma düğmeleri için. |

**Belge Taşma Düğmesi: varsayılan durumu**  

![Varsayılan Belge Taşma düğmesi](../../extensibility/ux-guidelines/media/0303-084_overflow.png "0303 084_Overflow")<br />Varsayılan Belge Taşma düğmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.DocWellOverflowButtonBackground` |
| Ön plan (karakter) | `Environment.DocWellOverflowButtonGlyph` |
| Kenarlık | Yok |

**Belge Taşma Düğmesi: vurgulu durumu**

![Belge Taşma vurgulu düğmesinde](../../extensibility/ux-guidelines/media/0303-085_overflowhover.png "0303 085_OverflowHover")<br />Belge taşma düğmesini vurgulu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.DocWellOverflowButtonMouseOverBackground` |
| Ön plan (karakter) | `Environment.DocWellOverflowButtonMouseOverGlyph` |
| Kenarlık | `Environment.DocWellOverflowButtonMouseOverBorder` |

**Belge Taşma Düğmesi: durumu basılı**  

![Belge Taşma düğmesine basın](../../extensibility/ux-guidelines/media/0303-086_overflowpressed.png "0303 086_OverflowPressed")<br />Belge Taşma düğmesine basın

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.DocWellOverflowButtonMouseDownBackground` |
| Ön plan (karakter) | `Environment.DocWellOverflowButtonMouseDownGlyph` |
| Kenarlık | `Environment.DocWellOverflowButtonMouseDownBorder` |

### <a name="tagging"></a>Etiketleme  
Visual Studio etiketleme, izleme amacıyla aranabilir anahtar sözcükleri bildirmek bir kullanıcı sağlayan destekler. Örneğin, proje yöneticileri ve geliştiriciler Team Foundation Server (TFS) iş öğelerini etiketlemek için kullanabilirsiniz. Aşağıdaki tablolarda etiketi ve vurgulu ve seçili durumları görünür "simgesini Kapat" karakteri için renk adlar verin.  

![Visual Studio'da etiketleme (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-176_taggingredline.png "0303 176_TaggingRedline")<br />Visual Studio'da etiketleme (kırmızı çizgi)  

| Kullanım... | Kullanmayan... |
| --- | --- |
| etiketleme destekleyen... için kullanıcı Arabirimi. | ... herhangi bir türü kullanıcı Arabirimi için. |

#### <a name="tags"></a>Etiketler  

**Etiket: varsayılan durumu**

![Varsayılan etiket](../../extensibility/ux-guidelines/media/0303-177_tag.png "0303 177_Tag")<br />Varsayılan etiketi

| Öğe | Belirteç adını: Category.color |
| --- | --- |  
| Arka Plan | `Tag.Background` |
| Ön plan (metin) | `Tag.Background` |

**Etiket: vurgulu durumu**  

![Gidildiğinde etiketi](../../extensibility/ux-guidelines/media/0303-178_taghover.png "0303 178_TagHover")<br />Gidildiğinde etiketi  

| Öğe | Belirteç adını: Category.color |
| --- | --- |  
| Arka Plan | `Tag.HoverBackground` |
| Ön plan (metin) | `Tag.HoverBackgroundText` |

**Etiketi: durum basılı**

![Etiket basılı](../../extensibility/ux-guidelines/media/0303-179_tagpressed.png "0303 179_TagPressed")<br />Basılı etiketi  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Tag.PressedBackground` |
| Ön plan (metin) | `Tag.PressedBackgroundText` |

**Etiket: seçilen durumu**

![Etiket seçili](../../extensibility/ux-guidelines/media/0303-180_tagselected.png "0303 180_TagSelected")<br />Seçili etiketi  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Tag.SelectedBackground` |
| Ön plan (metin) | `Tag.SelectedBackgroundText` |

#### <a name="close-times-tag-glyph"></a>Kapat (&times;) simge etiketi

**Kapat (&times;) karakter etiketi: varsayılan durumu**

![Varsayılan Kapat (&times;) karakter etiketi](../../extensibility/ux-guidelines/media/0303-181_tagglyph.png "0303 181_TagGlyph")<br />Varsayılan Kapat (&times;) simge etiketi

| Öğe | Belirteç adını: Category.color |
| --- | --- |  
| Arka Plan | Yok |
| Ön plan (karakter) | `Tag.TagHoverGlyph` |

**Kapat (&times;) karakter etiketi: vurgulu durumu**

![Kapat (&times;) karakter gidildiğinde etiketi](../../extensibility/ux-guidelines/media/0303-182_tagglyphhover.png "0303 182_TagGlyphHover")<br />Kapat (&times;) gidildiğinde simge etiketi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Tag.TagHoverGlyphHoverBackground` |
| Ön plan (karakter) | `Tag.TagHoverGlyphHover` |
| Kenarlık | `Tag.TagHoverGlyphHoverBorder` |

**Kapat (&times;) karakter etiketi: durumu basılı**

![Kapat basılı (&times;) karakter etiketi](../../extensibility/ux-guidelines/media/0303-183_tagglyphpressed.png "0303 183_TagGlyphPressed")<br />Kapat basılı (&times;) simge etiketi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Tag.TagHoverGlyphPressedBackground` |
| Ön plan (karakter) | `Tag.TagHoverGlyphPressed` |
| Kenarlık | `Tag.TagHoverGlyphPressedBorder` |

**Seçili kapatma etiketi (&times;) karakteri: varsayılan durumu**

![Seçili etiketi Kapat ile varsayılan (&times;) karakter](../../extensibility/ux-guidelines/media/0303-184_tagselected.png "0303 184_TagSelected")<br />Seçili etiketi Kapat ile varsayılan (&times;) karakteri

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Yok |
| Ön plan (karakter) | `Tag.TagSelectedGlyph` |

**Seçili kapatma etiketi (&times;) karakter: vurgulu durumu**  

![Seçili kapatma etiketi (&times;) karakter vurgulu üzerinde](../../extensibility/ux-guidelines/media/0303-185_tagselectedhover.png "0303 185_TagSelectedHover")<br />Seçili kapatma etiketi (&times;) üzerine gelindiğinde karakter  


| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Tag.TagSelectedGlyphHoverBackground` |
| Ön plan (karakter) | `Tag.TagSelectedGlyphHover` |
| Kenarlık | `Tag.TagSelectedGlyphHoverBorder` |

**Seçili kapatma etiketi (&times;) karakteri: durumu basılı**  

![Seçili, basılı kapatma etiketi (&times;) karakter](../../extensibility/ux-guidelines/media/0303-186_tagselectedpressed.png "0303 186_TagSelectedPressed")<br />Seçili, basılı kapatma etiketi (&times;) karakteri

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Tag.TagSelectedGlyphPressedBackground` |
| Foreground(glyph) | `Tag.TagSelectedGlyphPressed` |
| Kenarlık | `Tag.TagSelectedGlyphPressedBorder` |

## <a name="tool-windows"></a>Araç pencereleri  
Visual Studio ortamı tarafından sağlanan olduğundan aracı windows çoğaltmak için gerek yoktur. Ancak, böylece UI her zaman Visual Studio ortamında bu kısmı tutarlı görünür aracı Windows'ta kullanılan renkleri kullanmasına istediğiniz karar verebilirsiniz.  

![Araç penceresi (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-087_toolwindowredline.png "0303 087_ToolWindowRedline")<br />Araç penceresi (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... herhangi bir yere, aracı windows eşleştirmek istediğiniz UI oluşturmakta olduğunuz. | ... varsa otomatik olarak değiştirmek istemiyorsanız hiç kullanıcı Arabirimi için bir tema güncelleştirmesi Kabuk bulunuyor. |

### <a name="tool-window-frame"></a>Aracı pencere çerçevesi  
Visual Studio'da aracı windows birçok farklı görevler için kullanılır ve birçok farklı durumlardan birinde bulunabilir. Araç penceresi açık ise, tüm belge alanı dört tarafına atanabilir. Araç pencereleri kullanıcının ekran içinde herhangi bir yere konumlandırılmasına veren IDE dışında da kaydırın. Kayan windows her zaman en üstünde IDE sit. Son olarak, aracı windows belge pencereleri yerleşik ve belgenin iyi bir sekmede olarak görünür. Belge pencereleri yerleşik aracı windows kısmen belge pencere belirteci adları kullanarak renkte görünür.  

![Aracı pencere çerçevesi (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-088_toolwindowframeredline.png "0303 088_ToolWindowFrameRedline")<br />Aracı pencere çerçevesi (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... herhangi bir yere, aracı windows eşleştirmek istediğiniz UI oluşturmakta olduğunuz. | ... varsa otomatik olarak değiştirmek istemiyorsanız hiç kullanıcı Arabirimi için bir tema güncelleştirmesi Kabuk bulunuyor. |

**Yerleşik araç penceresi**  

![Yerleşik araç penceresi](../../extensibility/ux-guidelines/media/0303-089_toolwindowdocked.png "0303 089_ToolWindowDocked")<br />Yerleşik araç penceresi  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ToolWindowBackground` |
| Kenarlık | `Environment.ToolWindowBorder` |

**Kayan, odaklanmış araç penceresi**

![Kayan, araç penceresi odaklanmış](../../extensibility/ux-guidelines/media/0303-090_toolwindowfocused.png "0303 090_ToolWindowFocused")<br />Kayan, odaklanmış araç penceresi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ToolWindowBackground` |
| Kenarlık | `Environment.MainWindowActiveDefaultBorder` |

**Kayan, Odaksız araç penceresi**  

![Kayan, Odaksız araç penceresi](../../extensibility/ux-guidelines/media/0303-091_toolwindowunfocused.png "0303 091_ToolWindowUnfocused")<br />Kayan, Odaksız araç penceresi  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ToolWindowBackground` |
| Kenarlık | `Environment.MainWindowInactiveBorder` |

### <a name="toolbox-like-windows"></a>Araç kutusu benzeri windows
Araç kutusu Visual Studio'da en sık kullanılan ortak aracı windows biridir. Temelde ağaç denetimi ile özel teması ve stil uygulanmış olduğunu.  

![Araç kutusu benzeri penceresi (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-189_toolboxredline.png "0303 189_ToolboxRedline")<br />Araç kutusu benzeri penceresi (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... ne zaman, tasarlama her zaman Kabuk araç kutusu ile tutarlı olmasını istediğiniz bir araç penceresi. | Araç kutusu kullanıcı Arabirimi, benzer olmayan herhangi bir şey için... veya kabuk araç kutusunu değiştirme renkleri seçerseniz, kullanıcı Arabirimi sorunları olup olmadığını gerekir emin değilseniz. |

**Araç kutusu düğümleri: varsayılan durumu**

![Varsayılan araç kutusunu üst düğümü](../../extensibility/ux-guidelines/media/0303-190_toolboxparentnode.png "0303 190_ToolboxParentNode")<br />Varsayılan araç kutusunu üst düğümü

![Varsayılan araç kutusunu alt düğüm](../../extensibility/ux-guidelines/media/0303-191_toolboxchildnode.png "0303 191_ToolboxChildNode")<br />Varsayılan araç kutusunu alt düğümü

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ToolboxContent`<br />(Başlıkları) |
| Arka Plan | `Environment.ToolWindowBackground`<br />(Tek tek öğeler veya tüm pencereyi kullanılabilir denetim varsa) |
| Kenarlık | Yok. |
| Ön plan (karakter) | `Environment.ToolboxContent` |
| Ön plan (metin) | `Environment.ToolboxContent` |

**Araç kutusu alt düğümleri: vurgulu durumu**

![Araç kutusu alt vurgulu düğümde](../../extensibility/ux-guidelines/media/0303-192_toolboxchildnodehover.png "0303 192_ToolboxChildNodeHover")<br />Araç kutusu alt düğümünde vurgulu  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ToolboxContentMouseOver`<br />(Yalnızca tek tek öğe) |
| Kenarlık | Yok. |
| Ön plan (metin) | `Environment.ToolboxContentMouseOver`<br />(Yalnızca tek tek öğe) |

**Araç kutusu düğümleri seçilen: durumu odaklanmış**

![Odaklanmış, seçilen araç üst düğümü](../../extensibility/ux-guidelines/media/0303-193_toolboxparentnodefocused.png "0303 193_ToolboxParentNodeFocused")<br />Odaklanmış, seçilen araç üst düğümü  

![Araç kutusu odaklanmış, seçili alt düğüm](../../extensibility/ux-guidelines/media/0303-194_toolboxchildnodefocused.png "0303 194_ToolboxChildNodeFocused")<br />Araç kutusu odaklanmış, seçili alt düğüm

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `TreeView.SelectedItemActive`<br />Gelen [ağaç görünümü](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_TreeView) kategorisi |
| Kenarlık | `TreeView.FocusVisualBorder`<br />Gelen [ağaç görünümü](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_TreeView) kategorisi |
| Ön plan (karakter) | `TreeView.SelectedItemActive`<br />Gelen [ağaç görünümü](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_TreeView) kategorisi |
| Ön plan (metin) | `TreeView.SelectedItemActive`<br />Gelen [ağaç görünümü](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_TreeView) kategorisi |

**Araç kutusu düğümleri seçilen: Odaksız durumu**

![Seçili, Odaksız araç üst düğümü](../../extensibility/ux-guidelines/media/0303-195_toolboxparentnodeunfocused.png "0303 195_ToolboxParentNodeUnfocused")<br />Üst düğümü seçildiğinde, Odaksız araç kutusu  

![Seçili, Odaksız araç alt düğüm](../../extensibility/ux-guidelines/media/0303-196_toolboxchildnodeunfocused.png "0303 196_ToolboxChildNodeUnfocused")<br />Seçili, Odaksız araç alt düğümü  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `TreeView.SelectedItemInactive`<br />Gelen [ağaç görünümü](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_TreeView) kategorisi |
| Kenarlık | Yok. |
| Ön plan (karakter) | `TreeView.SelectedItemInactive`<br />Gelen [ağaç görünümü](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_TreeView) kategorisi |
| Ön plan (metin) | `TreeView.SelectedItemInactive`<br />Gelen [ağaç görünümü](../../extensibility/ux-guidelines/shared-colors-for-visual-studio.md#BKMK_TreeView) kategorisi |

### <a name="tool-window-title-bar"></a>Araç penceresi başlık çubuğu  
Başlık çubuğu kenarlık true kenarlık değilse, başlık çubuğu üst arasında kalın bir çizgi bulunur. Bir belirteç adı Odaksız durumuna sahip değil.  

![Araç penceresi başlık çubuğunda (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-092_toolwindowtitlebarredline.png "0303 092_ToolWindowTitleBarRedline")<br />Araç penceresi başlık çubuğunda (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... herhangi bir yere, aracı windows eşleştirmek istediğiniz UI oluşturmakta olduğunuz. | ... varsa otomatik olarak değiştirmek istemiyorsanız hiç kullanıcı Arabirimi için bir tema güncelleştirmesi Kabuk bulunuyor. |

**Odaklanmış başlık çubuğu**

![Odaklanmış başlık çubuğu](../../extensibility/ux-guidelines/media/0303-093_titlebarfocused.png "0303 093_TitleBarFocused")<br />Odaklanmış başlık çubuğu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.TitleBarActiveGradientBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.TitleBarActiveText` |
| Kenarlık | `Environment.TitleBarActiveBorder`<br />(Aynı renk arka plan olarak ayarlayın.) |
| tutamacını sürükleyin | `Environment.TitleBarDragHandleActive` |

**Odaksız başlık çubuğu**  

![Başlık çubuğu Odaksız](../../extensibility/ux-guidelines/media/0303-094_titlebarunfocused.png "0303 094_TitleBarUnfocused")<br />Odaksız başlık çubuğu

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.TitleBarInactiveGradientBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.TitleBarInactiveText` |
| Kenarlık | Yok |
| tutamacını sürükleyin | `Environment.TitleBarDragHandle` |

#### <a name="tool-window-title-bar-buttons"></a>Araç penceresi başlık çubuğu düğmeleri  
![Başlık düğme (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-095_titlebarbuttonredline.png "0303 095_TitleBarButtonRedline")<br />Başlık düğme (kırmızı çizgi)  

| Kullanım... | Kullanmayan... |
| --- | --- |
| araç penceresi başlık çubukları renk belirteçlerinden kullanan kullanıcı arabiriminde görünen... düğmeleri için. | başka bir konumda görünen... düğmeleri için. |
| | Belirtilen dışındaki... tüm arka plan/ön plan birlikte. |

**Başlık çubuğu düğmelerini odaklanmış: varsayılan durumu**

![Varsayılan, başlık çubuğu düğmelerini odaklanmış](../../extensibility/ux-guidelines/media/0303-096_titlebarbuttonfocused.png "0303 096_TitleBarButtonFocused")<br />Varsayılan, odaklanmış başlık çubuğu düğmeleri  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Yok |
| Ön plan (karakter) | `Environment.ToolWindowButtonActiveGlyph` |
| Kenarlık | Yok |

**Odaksız başlık çubuğu düğmelerini: varsayılan durumu**

![Varsayılan, Odaksız başlık çubuğu düğmelerinin](../../extensibility/ux-guidelines/media/0303-097_titlebarbuttonunfocused.png "0303 097_TitleBarButtonUnfocused")<br />Varsayılan, Odaksız başlık çubuğu düğmeleri    

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | Yok |
| Ön plan (karakter) | `Environment.ToolWindowButtonInactiveGlyph` |
| Kenarlık | Yok |

**Başlık çubuğu düğmelerini odaklanmış: vurgulu durumu**  

![Başlık çubuğu düğmelerini gidildiğinde odaklanmış](../../extensibility/ux-guidelines/media/0303-098_titlebarbuttonfocusedhover.png "0303 098_TitleBarButtonFocusedHover")<br />Vurgulu odaklanmış başlık çubuğu düğmeleri

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ToolWindowButtonHoverActive` |
| Ön plan (karakter) | `Environment.ToolWindowButtonHoverActiveGlyph` |
| Kenarlık | `Environment.ToolWindowButtonHoverActiveBorder` |

**Odaksız başlık çubuğu düğmelerini: vurgulu durumu**  

![Vurgulu Odaksız başlık çubuğu düğmelerini](../../extensibility/ux-guidelines/media/0303-099_titlebarbuttonunfocusedhover.png "0303 099_TitleBarButtonUnfocusedHover")<br />Vurgulu Odaksız başlık çubuğu düğmeleri

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ToolWindowButtonHoverInactive` |
| Ön plan (karakter) | `Environment.ToolWindowButtonHoverInactiveGlyph` |
| Kenarlık | `Environment.ToolWindowButtonHoverInactiveBorder` |

**Başlık çubuğu düğmelerini odaklanmış: durumu basılı**

![Başlık çubuğu düğmelerini makinesinde odaklanmış](../../extensibility/ux-guidelines/media/0303-100_titlebarbuttonfocusedpressed.png "0303 100_TitleBarButtonFocusedPressed")<br />Makinesinde odaklanmış başlık çubuğu düğmeleri

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ToolWindowButtonDown` |
| Ön plan (karakter) | `Environment.ToolWindowButtonDownActiveGlyph` |
| Kenarlık | `Environment.ToolWindowButtonDownBorder` |

**Odaksız başlık çubuğu düğmelerini: durumu basılı**

![Odaksız başlık çubuğu düğmelerini makinesinde](../../extensibility/ux-guidelines/media/0303-101_titlebarbuttonunfocusedpressed.png "0303 101_TitleBarButtonUnfocusedPressed")<br />Makinesinde Odaksız başlık çubuğu düğmeleri  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ToolWindowButtonDown` |
| Ön plan (karakter) | `Environment.ToolWindowButtonDownInactiveGlyph` |
| Kenarlık | `Environment.ToolWindowButtonDownBorder` |

### <a name="tool-window-tabs"></a>Araç penceresi sekmeleri  
![Araç penceresi sekmesine (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-102_toolwindowtabredline.png "0303 102_ToolWindowTabRedline")<br />Araç penceresi sekmesine (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... herhangi bir yere, aracı windows eşleştirmek istediğiniz UI oluşturmakta olduğunuz. | ... varsa otomatik olarak değiştirmek istemiyorsanız hiç kullanıcı Arabirimi için bir tema güncelleştirmesi Kabuk bulunuyor. |

**Seçili, odaklanmış aracı penceresi sekmesi**

![Seçili, araç penceresi sekmesine odaklanmış](../../extensibility/ux-guidelines/media/0303-103_toolwindowtabfocused.png "0303 103_ToolWindowTabFocused")<br />Seçili, odaklanmış aracı penceresi sekmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ToolWindowTabSelectedTab` |
| Ön plan (metin) | `Environment.ToolWindowTabSelectedActiveText` |
| Kenarlık | `Environment.ToolWindowTabSelectedBorder`<br />(Aynı renk arka plan olarak ayarlayın.) |

**Seçili, Odaksız aracı penceresi sekmesi**  

![Seçili, Odaksız araç penceresi sekmesine](../../extensibility/ux-guidelines/media/0303-104_toolwindowtabunfocused.png "0303 104_ToolWindowTabUnfocused")<br />Seçili, Odaksız aracı penceresi sekmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ToolWindowTabSelectedTab` |
| Ön plan (metin) | `Environment.ToolWindowTabSelectedText` |
| Kenarlık | `Environment.ToolWindowTabSelectedBorder`<br />(Aynı renk arka plan olarak ayarlayın.) |

**Arka plan araç penceresi sekmesine: varsayılan durumu**

![Varsayılan arka plan araç penceresi sekmesine](../../extensibility/ux-guidelines/media/0303-105_toolwindowbackgroundtab.png "0303 105_ToolWindowBackgroundTab")<br />Varsayılan arka plan aracı penceresi sekmesi  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ToolWindowTabGradientBegin`<br />`Environment.ToolWindowTabGradientEnd`<br />(Visual Studio 2013'te aynı renk değere ayarlanırsa gradyan durdurur.) |
| Ön plan (metin) | `Environment.ToolWindowTabText` |
| Kenarlık | `Environment.ToolWindowTabBorder` |

**Arka plan araç penceresi sekmesine: vurgulu durumu**

![Arka plan araç penceresi vurgulu sekmesinde](../../extensibility/ux-guidelines/media/0303-106_toolwindowbackgroundtabhover.png "0303 106_ToolWindowBackgroundTabHover")<br />Arka plan araç penceresi vurgulu sekmesinde

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.ToolWindowTabMouseOverBackgroundBegin`<br />`Environment.ToolWindowTabMouseOverBackgroundEnd`<br />(Visual Studio 2013'te aynı renk değere ayarlanırsa gradyan durdurur.) |
| Ön plan (metin) | `Environment.ToolWindowTabMouseOverText` |
| Kenarlık | `Environment.ToolWindowTabMouseOverBorder`<br />(Aynı renk arka plan olarak ayarlayın.) |  

### <a name="auto-hide-tabs"></a>Sekmeleri otomatik olarak gizle  

![Otomatik olarak gizle sekmeler (kırmızı çizgi)](../../extensibility/ux-guidelines/media/0303-107_autohideredline.png "0303 107_AutoHideRedline")otomatik olarak gizle sekmeler (kırmızı çizgi)

| Kullanım... | Kullanmayan... |
| --- | --- |
| ... herhangi bir yerde otomatik gizli araç penceresi sekmeleri eşleştirmek istediğiniz UI oluşturmakta olduğunuz. | ... varsa otomatik olarak değiştirmek istemiyorsanız hiç kullanıcı Arabirimi için bir tema güncelleştirmesi Kabuk bulunuyor. |

**Sekmeleri otomatik olarak gizle: varsayılan durumu**  

![Varsayılan otomatik olarak gizle sekmesi](../../extensibility/ux-guidelines/media/0303-108_autohidetab.png "0303 108_AutoHideTab")<br />Varsayılan otomatik olarak gizle sekmesi

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.AutoHideTabBackgroundBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.AutoHideTabText` |
| Kenarlık | `Environment.AutoHideTabBorder` |

**Sekmeleri otomatik olarak gizle: vurgulu durumu**

![Hover gizle otomatik sekmesinde](../../extensibility/ux-guidelines/media/0303-109_autohidetabhover.png "0303 109_AutoHideTabHover")<br />Vurgulu sekmesinde otomatik olarak gizle  

| Öğe | Belirteç adını: Category.color |
| --- | --- |
| Arka Plan | `Environment.AutoHideTabMouseOverBackgroundBegin`<br />(Bu belirtece konulu kullanıcı Arabiriminde kullanılmayan gradyan durur.) |
| Ön plan (metin) | `Environment.AutoHideTabMouseOverText` |
| Kenarlık | `Environment.AutoHideTabMouseOverBorder` |
