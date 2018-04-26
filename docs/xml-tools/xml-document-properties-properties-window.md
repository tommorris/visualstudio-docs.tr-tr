---
title: XML belge özellikleri, özellik penceresi
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: reference
ms.assetid: 9dbb34d9-02ea-4201-b445-c98a0eb0d6db
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f4610a2574fbd822e4468436655668cff3892270
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="xml-document-properties-properties-window"></a>XML belge özellikleri, özellik penceresi

**Özellikleri** penceresi XML Düzenleyicisi'nde etkin belgeyi hakkında temel bilgiler sağlar. Kullanılabilir özellikler şu anda etkin olan XML belgesi türüne bağlı olarak farklılık gösterir.

> [!NOTE]
> Tüm XML belge özellikleri çözümde kaydedilir. Sonuç olarak, çözümü bir sonraki açışınızda bu değerleri yeniden girin gerekmez.

 **Kodlama**

 İçin dosya kodlamasını karakter. Bu özellik ayrıca kodlama özniteliği XML bildirimi ve tersi değişiklikleri değiştirme. Yeni kodlama dosyayı kaydettiğinizde dosya kodlamak için kullanılır.

 **Giriş**

 XSLT stil sayfası ile ilişkili giriş belgesi. Tarafından kullanılan **ShowXSLT çıkış** komutu. Gözat'ı kullanarak bir belge seçilebilir (**...** ) düğmesi.

 Bu özellik, yalnızca bir XSLT dosyası Düzenleyicisi penceresinde şu anda etkin olduğunda görülebilir.

 **Output**

 Bir XML belgesi dönüşüm sırasında oluşturulan dosya.

 Bir dosya belirtilmezse, varsayılan dosya adı temel alınarak oluşturulur `method` özniteliği `xsl:output` öğesinin dosya uzantısı belirler. Varsayılan dosya geçerli kullanıcının geçici dizinde bulunur.

 **Şemaları**

 Doğrulama için kullanılacak şemalar. Düğme açar **XSD şemaları** kullanılacak şemaları seçmek için kullanılan iletişim kutusu.

 Yol için şemaların da girebilirsiniz. Birden çok şema belirtilirse, her şema çift tırnak içine alınmalıdır.

 **Stil sayfası**

 Belge dönüştürmek için kullanılan XSLT dosyası olduğunda **Göster XSLT çıktı** komutu kullanılır. Bu alan boşsa, **Göster XSLT çıktı** komutu kullanıldığında, sağlanan değer Düzenleyici kullanır `xml-stylesheet` işleme yönergesi bir belgenin ya da sizden için dosya adı.

 Farklı stil sayfası olması gerektiğini belirtmek için bir XSLT dosyası düzenlerken, bu özellik kullanılabilir olduğunda kullanılabilir **XSLT çıkış Göster** veya **hata ayıklama XSLT** komutu seçilidir. Örneğin, bir üst stil sayfasında bulunan bir stil sayfası düzenlerken bunu yapmak isteyebilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

- [XML Düzenleyicisi](../xml-tools/xml-editor.md)
- [XML Düzenleyicisi Bileşenleri](../xml-tools/xml-editor-components.md)