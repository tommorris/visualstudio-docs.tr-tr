---
title: Biçimlendirme, XML, metin düzenleyici, Seçenekler iletişim kutusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: bb539b3a-027c-4b2f-906e-403e0e22ba8d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 95fdc563b288c965dbbff7a6201e9b1ef8ec4ae9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="formatting-xml-text-editor-options-dialog-box"></a>Biçimlendirme, XML, metin düzenleyici, Seçenekler iletişim kutusu
Bu iletişim kutusu için XML Düzenleyicisi biçimlendirme ayarları belirtmenize olanak sağlar. Erişebileceğiniz **seçenekleri** iletişim kutusundan **Araçları** menüsü.  
  
> [!NOTE]
>  Öğesini seçtiğinizde bu ayarlar kullanılabilir **metin düzenleyici** klasörü, **XML** klasörünü ve ardından **biçimlendirme** gelen seçeneği **seçenekleri** iletişim kutusu.  
  
## <a name="attributes"></a>Öznitelikler  
 **El ile öznitelik biçimlendirmeyi koru**  
 Öznitelikleri yeniden biçimlendirilen değil. Bu varsayılandır.  
  
> [!NOTE]
>  Öznitelikleri birden çok satırda varsa, her satırın üst öğenin girinti eşleştirilecek özniteliklerin Düzenleyicisi girintileri.  
  
 **Öznitelikleri her kendi satırında hizalayın**  
 Dikey olarak ilk öznitelik girinti eşleştirmek için ikinci ve sonraki öznitelikleri hizalar. Aşağıdaki XML metni nasıl öznitelikleri hizalı bir örnektir.  
  
```xml
<item id = "123-A"  
      name = "hammer"  
      price = "9.95">  
</item>  
```
  
## <a name="auto-reformat"></a>Otomatik yeniden biçimlendirme  
 **Pano'dan üzerinde Yapıştır**  
 Panodan yapıştırılan XML metni yeniden biçimlendirir.  
  
 **Bitiş etiketi tamamlama hakkında**  
 Bitiş etiketi tamamlandığında, öğeyi yeniden biçimlendirir.  
  
## <a name="mixed-content"></a>Karışık içerik  
 **Varsayılan olarak karışık içerik koruma**  
 Düzenleyici karışık içerik yeniden biçimlendirir olup olmadığını belirler. Varsayılan olarak, içeriği ne zaman bulunur dışında karışık içerik yeniden biçimlendirmek Düzenleyicisi çalışır bir `xml:space="preserve"` kapsam.  
  
 Bir öğenin metin ve biçimlendirme bir karışımını içeriyorsa, içeriği içerik karışık kabul edilir. Bir öğenin karışık içerikli bir örnek verilmiştir.  
  
```xml
<dir>c:\data\AlphaProject\  
  <file readOnly="false">test1.txt</file>  
  <file readOnly="false">test2.txt</file>  
</dir>  
```
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML belge özellikleri, özellik penceresi](../xml-tools/xml-document-properties-properties-window.md)   
 [XML Düzenleyicisi Bileşenleri](../xml-tools/xml-editor-components.md)