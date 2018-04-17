---
title: Biçimlendirme seçenekler, metin düzenleyici, XAML | Microsoft Docs
ms.custom: ''
ms.date: 01/17/2017
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XAML.Formatting.General
- VS.ToolsOptionsPages.Text_Editor.XAML.Miscellaneous
- VS.ToolsOptionsPages.Text_Editor.XAML.Formatting.Spacing
helpviewer_keywords:
- element spacing, XAML view settings
- attribute spacing, XAML view settings
- XAML view settings, auto-formatting events
- auto-formatting events, XAML view settings
- XAML view settings, tag wrapping
- XAML view settings, auto insert
- quotation mark style, XAML view settings
- XAML formatting, WPF Designer
- XAML view settings, Toolbox
- XAML view settings, element spacing
- default view, XAML view settings
- auto insert, XAML view settings
- XAML view settings, default view
- XAML view settings, quotation mark style
- tag wrapping, XAML view settings
- WPF Designer, XAML formatting
- XAML view settings, attribute spacing
ms.assetid: ad3820b1-0d94-4807-a74c-c3467ed973a2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 401e0f6c5da01413042eb30f336a7e2081e84ba1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="options-text-editor-xaml-formatting"></a>Seçenekler, Metin Düzenleyici, XAML, Biçimlendirme
Kullanım **biçimlendirme** özellik sayfası öğeleri ve özniteliklerinin XAML belgelerinizi nasıl biçimlendirileceğini belirtin. Açmak için **seçenekleri** iletişim kutusu, tıklatın **Araçları** menüsünü seçin ve ardından **seçenekleri**. Erişim için **biçimlendirme** özellik sayfasında **metin düzenleyici**, **XAML**, **biçimlendirme** düğümü.  

> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).  

## <a name="auto-formatting-events"></a>Otomatik biçimlendirme olayları  
 Otomatik biçimlendirme oluşabilir zaman aşağıdaki olaylardan herhangi biri algılandı.  

-   Tamamlama bir bitiş etiketi veya basit etiketi.  

-   Bir başlangıç etiketi tamamlanmasından.  

-   Panodan yapıştırarak.  

-   Biçimlendirme klavye komutları.  

Otomatik biçimlendirme olayları neden belirtebilirsiniz.  

|||  
|-|-|  
|**Bitiş etiketi veya basit etiketinin tamamlanma**|Bitiş etiketi veya basit bir etiketin yazmayı bitirdikten otomatik biçimlendirme oluşur. Basit bir etiket öznitelikleri, örneğin yok `<Button />`.|  
|**Başlangıç etiketi tamamlama hakkında**|Bir başlangıç etiketi yazmayı bitirdikten otomatik biçimlendirme oluşur.|  
|**Pano'dan üzerinde Yapıştır**|XAML panodan XAML görünümü içine yapıştırdığınız otomatik biçimlendirme oluşur.|  

## <a name="quotation-mark-style"></a>Tırnak işareti stili  
 Bu ayar, öznitelik değerleri tek veya çift tırnak işaretleri içine olup olmadığını gösterir. Otomatik biçimlendirici ve IntelliSense otomatik tamamlama bu ayarı kullanın.  

 Bu seçenek ayarladıktan sonra yalnızca öznitelikler sonradan Tasarımcısı'nı kullanarak eklenemez veya el ile XAML görünümünde etkilenir.  

|||  
|-|-|  
|**Çift tırnak (")**|Öznitelik değerleri çift tırnak işareti içine alınır.<br /><br /> `<Button Name="button1">Hello</Button>`|  
|**Tek tırnak işareti (')**|Öznitelik değerlerini tek tırnak işareti içine alınır.<br /><br /> `<Button Name='button1'>Hello</Button>`|  

## <a name="tag-wrapping"></a>Etiket kaydırma  
 Etiket kaydırma için bir satır uzunluğu belirtebilirsiniz. Etiket kaydırma etkinleştirildiğinde, tasarımcıyı kullanarak sonradan eklenen XAML uygun şekilde sarılır.  

|||  
|-|-|  
|**Belirtilen uzunluğu aşan kaydırma etiketleri**|Satıra tarafından belirtilen satır uzunluğu en gibi olup olmadığını belirtir **uzunluğu**.|  
|**uzunluğu**|Bir satır içerebilir karakter sayısı. Gerekirse, bazı XAML satırları belirtilen satır uzunluğu aşabilir.|  

## <a name="attribute-spacing"></a>Öznitelik aralığı  
 Öznitelikleri XAML belgenizi nasıl düzenlenir denetlemek için bu ayarı kullanın  

|||  
|-|-|  
|**Satır başı ve öznitelikleri arasında boşluk koru**|Yeni satırlar ve öznitelikleri arasında boşluk tarafından otomatik olarak biçimlendirme etkilenmez.<br /><br /> `<Button Height="23"   Name="button1"`<br /><br /> `Width="75">Hello</Button>`|  
|**Öznitelikler arasındaki tek bir boşluk Ekle**|Öznitelikleri bitişik öznitelikleri ayıran bir boşluk ile tek bir çizgi kaplar. Etiket kaydırma ayarları uygulanır.<br /><br /> `<Button Height="23" Name="button1" Width="75">Hello</Button>`|  
|**Her öznitelik ayrı bir satıra getirin**|Her öznitelik kendi satırında kaplar. Bu, çok sayıda özniteliği mevcut olduğunda yararlıdır.<br /><br /> `<Button`<br /><br /> `Height="23"`<br /><br /> `Name="button1"`<br /><br /> `Width="75">Hello</Button>`|  
|**Başlangıç etiketi olarak aynı satırındaki ilk öznitelik konumu**|İşaretlendiğinde, öğenin başlangıç etiketinde aynı satırındaki ilk öznitelik görüntülenir.<br /><br /> `<Button Height="23"`<br /><br /> `Name="button1"`<br /><br /> `Width="75">Hello</Button>`|  

## <a name="element-spacing"></a>Öğe aralığı  
 Öğeleri XAML belgenizi nasıl düzenlenir denetlemek için bu ayarı kullanın  

|||  
|-|-|  
|**Yeni satırlar içerik koruma**|Öğe içeriğinde boş satırları kaldırılmaz.<br /><br /> `<Grid>`<br /><br /> ``<br /><br /> ``<br /><br /> `<Button Name="button1">Hello</Button>`<br /><br /> ``<br /><br /> `</Grid>`|  
|**İçerikte birden çok boş satırlar için tek bir satır Daralt**|Öğe içeriğinde boş satırlar için tek bir satır daraltılır.<br /><br /> `<Grid>`<br /><br /> ``<br /><br /> `<Button Name="button1">Hello</Button>`<br /><br /> ``<br /><br /> `</Grid>`|  
|**İçeriği boş satırları kaldırın**|Öğe içeriğinde tüm boş satırları kaldırılır.<br /><br /> `<Grid>`<br /><br /> `<Button Name="button1">Hello</Button>`<br /><br /> `</Grid>`|  

## <a name="miscellaneous-section-auto-insert"></a>Çeşitli bölümünde, otomatik ekleme  
 Etiketleri ve tırnak işaretleri ne zaman otomatik olarak oluşturulan denetlemek için bu ayarı kullanın.  

|||  
|-|-|  
|**Kapatma etiketleri**|Büyüktür (>) karakteri ile açılış etiketi kapattığınızda, bir öğenin kapatma etiketi otomatik olarak oluşturulup oluşturulmayacağını belirtir.|  
|**Öznitelik tırnak işaretleri**|Deyim tamamlama aşağı açılan listeden bir öznitelik değeri seçildiğinde kapsayan teklifleri oluşturulan olup olmadığını belirtir.|  
|**MarkupExtensions için Küme ayraçları kapatma**|Açılış yazdığınızda, bir işaretleme uzantının kapanış ayracı (}) otomatik olarak oluşturulup oluşturulmayacağını belirtir ayracı karakter ({}).|  
|**MarkupExtension parametreleri ayırmak için virgül**|Birden fazla parametre biçimlendirme uzantısı'nda yazdığınız zaman virgül oluşturulan olup olmadığını belirtir.|  

## <a name="see-also"></a>Ayrıca bkz.

[WPF'de XAML](/dotnet/framework/wpf/advanced/xaml-in-wpf)
