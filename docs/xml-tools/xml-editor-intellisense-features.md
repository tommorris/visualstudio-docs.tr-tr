---
title: XML Düzenleyicisi IntelliSense özellikleri
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 2b26f214-cc3a-46bf-b260-14eb8e599182
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 82d05e481d313a7ba9010fe253756d3f21c345e2
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/24/2018
ms.locfileid: "34476852"
---
# <a name="xml-editor-intellisense-features"></a>XML Düzenleyicisi IntelliSense özellikleri

XML Düzenleyicisi'ni Visual Studio'da sağlanan diğer dil düzenleyicileri karşılaştırılabilir tam IntelliSense özellikleri sağlar. Bu bölümde, XML Şeması Tanım Dili (XSD) ve XSLT belgelerle IntelliSense nasıl kullanabileceğinizi açıklar.

## <a name="intellisense-in-an-xsd-document"></a>XSD belgesindeki IntelliSense
 Bir şema, belge ile ilişkilendirilen sonra yazdığınız dilediğiniz zaman beklenen öğelerin açılan listesini almak `"<"` veya **bir nesne üye listesini görüntüleme** XML Düzenleyicisi araç çubuğunda. Şemalar, XML belgelerle ilişkilendirme hakkında daha fazla bilgi için bkz: [XML belge doğrulama](../xml-tools/xml-document-validation.md).

 Bir başlangıç etiketi içinde ALANINDAN yazdığınızda, ayrıca geçerli öğeye eklenen tüm öznitelikleri gösteren açılan listesini alın.

 Yazdığınızda `"="` bir öznitelik değeri veya tırnak değeri için Ayrıca bu öznitelik için olası değerler listesini alın. Değerleri yalnızca şema aracılığıyla numaralandırılmış değerler sağlıyorsa sağlanan `xsd:enumeration` modellerini veya öznitelik ise bir `Boolean` türü. Bilinen dil kodlarının IntelliSense listesi de için sağlanan `xml:lang` veya tüm `simpleType` , türetilen `xsd:language`. Bilinen IntelliSense listesi `targetNamespace` değerleri, ad alanı bildirimleri için sağlanır.

 Olası değerler IntelliSense listesi yazarken de sağlanır `">"` öğe ise bir başlangıç etiketi kapatmak için bir `simpleType`. Önceki paragrafta açıklanan öznitelikler için davranışına benzer biçimde öğelerin davranıştır.

 Araç ipuçları da görünür göre bu IntelliSense listelerde `xsd:annotation` ve `xsd:documentation` ilişkili şemasında bilgi bulunamadı.

## <a name="intellisense-in-an-xslt-document"></a>XSLT belgesindeki IntelliSense
 XSLT belgenize adlandırılmış bir şablonu veya öznitelik ekledikten sonra aşağıdaki eklemek için IntelliSense kullanabilirsiniz:

-   Öznitelik adları ayarlayın.

-   Şablon modları.

-   Şablon adları.

-   Belirli bir mod için parametre adları.

-   Verilen bir adlandırılmış şablon parametresi adları.

Daha fazla bilgi için bkz: [izlenecek yol: kullanarak XSLT IntelliSense](../xml-tools/walkthrough-using-xslt-intellisense.md) konu.

## <a name="auto-completion"></a>Otomatik Tamamlama
 XML Düzenleyicisi'ni de gerekli XML sözdiziminde doldurarak XML daha kolay düzenlemeyi sağlar. Örneğin aşağıdaki başlangıç etiketi yazın:

 `<book>`

 XML Düzenleyicisi'ni bitiş etiketinde doldurur ve sonra başlangıç etiketi imleci yerleştirir. Bunun bir örneği aşağıda verilmiştir ("&#124;" imleç konumu Notlar):

 `<book>`&#124;`</book>`

 Öznitelik değerlerine tırnak her zaman olması gerektiğinden, XML Düzenleyicisi'ni tırnak içine doldurur. Örneğin aşağıdaki komutu yazın:

 `<book title=`

 XML Düzenleyicisi'ni tırnak işaretleri ekler ve tırnak işaretleri arasında imleci geçir konumlandırır:

 `<book title="`&#124;`"`

 Benzer şekilde, XML Düzenleyicisi'ni de aşağıdaki XML sözdizimi otomatik olarak ekler:

-   Bir işleme yönergesi Bitir:  `?>`

-   CDATA bloğu Bitir: `]]>`

-   Açıklama bitiş: `-->`

-   DTD bildirimi Bitir: `>`

XML Düzenleyicisi'ni bir ad alanı ekleme olanağı da sahip bir ad alanı tam öğesi seçin veya bir IntelliSense listesi ve bu öğe veya öznitelik için ad alanı özniteliğinden henüz kapsamında değilse bildirimi.

Örneğin, `e:Book` burada önek bağlı IntelliSense listesi öğesinden `http://books` XML Düzenleyicisi ekler, gerekli ad alanı bildirimi belgede bildirilmedi ad alanı. Sonuçta elde edilen XML metni verilmiştir:

`<e:Book xmlns:e="http://books"`

## <a name="brace-matching"></a>Ayraç eşleştirme
 XML Düzenleyicisi'ni küme parantezi vurgulama kapalı öğelerde hemen görüş sağlar. Klavye kısayolu da kullanabilirsiniz (**Ctrl**+**]**) için eşleşen küme parantezi bir ayraç atlamak için.

 XML Düzenleyicisi'ni bu aşağıdaki öğeler için yapar:

-   Başlangıç ve bitiş etiketleri eşleşen.

-   Tüm çifti "\<" veya ">" açılı ayraçları.

-   Başlangıç ve bitiş açıklama.

-   Başlangıç ve bitiş yönergeleri işleme.

-   Başlangıç ve bitiş CDATA bloğu.

-   Başlangıç ve bitiş DTD bildirimlerinin.

-   Dosyaları açma ve kapama öznitelikleri tekliflerinde.

## <a name="modify-the-intellisense-options"></a>IntelliSense seçeneklerini değiştirin
 IntelliSense ve otomatik tamamlama özellikler varsayılan olarak etkindir. Ancak, bu değiştirerek değiştirebilirsiniz, **Araçları** > **seçenekleri** ayarlar.

 **Otomatik ekleme** bölümünü **çeşitli** sayfa aşağıdaki davranışı denetler:

|Ad|Açıklama|
|----------|-----------------|
|Kapatma etiketleri|Ekler için yeni öğe etiketleri kapatın.|
|Öznitelik tırnak işaretleri|Yeni bir öznitelik adını girin, öznitelik değer tırnakları ekler.|
|Diğer biçimlendirme|Açıklamalar, CDATA, DOCTYPE, işleme yönergeleri ve diğer biçimlendirme bildirimleri tamamlar.|

### <a name="to-change-the-auto-completion-behavior"></a>Otomatik Tamamlama davranışını değiştirmek için

1.  Seçin **seçenekleri** gelen **Araçları** menüsü.

2.  Genişletme **metin düzenleyici**, genişletin **XML**seçip **çeşitli**.

3.  Hiçbir değişiklik **otomatik ekleme** 'ye tıklayın **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

- [XML Düzenleyicisi](../xml-tools/xml-editor.md)
- [IntelliSense Kullanma](../ide/using-intellisense.md)
- [İzlenecek Yol: XSLT IntelliSense Kullanma](../xml-tools/walkthrough-using-xslt-intellisense.md)