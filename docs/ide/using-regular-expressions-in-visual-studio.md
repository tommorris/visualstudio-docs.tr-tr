---
title: Visual Studio'da Normal İfadeler Kullanma
ms.date: 03/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vsregularexpressionhelp
- vs.regularexpressionhelp
- vs.wildcardsbuilder
- vs.netregularexpressionhelp
- vs.wildcards
helpviewer_keywords:
- regular expressions [Visual Studio]
- regular expressions
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1dae1c3d62fce5ba8b3991e41bade1d612b74647
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="using-regular-expressions-in-visual-studio"></a>Visual Studio'da normal ifadeler kullanma

Visual Studio kullanan [.NET Framework normal ifadeleri](/dotnet/standard/base-types/regular-expressions) metin bulma ve değiştirme için.

## <a name="replacement-patterns"></a>Değiştirme desenleri

Numaralı yakalama grubu kullanmak için normal ifade deseni parantezlerde grubuyla koyun. Kullanım `$number`, burada `number` belirli, numaralandırılmış bir grubu değiştirme desende belirtmek için 1'den başlayarak bir tamsayıdır. Örneğin, gruplandırılmış normal ifade `(\d)([a-z])` iki grupları tanımlar: tek bir ondalık basamak içeren ilk grubu ve ikinci grup arasında tek bir karakter içeriyor **bir** ve **z**. İfade dört eşleşmeleri aşağıdaki dizeyi bulur: **1a 2b 3c 4d**. Değiştirme dizesini `z$1` yalnızca ilk grubu başvuruyor ve dizeye dönüştürür **z1 z2 z3 z4**.

Değiştirme desenleri kullanılan normal ifadeler hakkında daha fazla bilgi için bkz: [(.NET Kılavuzu) normal ifadelerdeki değişimler](/dotnet/standard/base-types/substitutions-in-regular-expressions).

## <a name="regular-expression-examples"></a>Normal ifade örnekleri

Bazı örnekler şunlardır:

|Amaç|İfade|Örnek|
|-------------|----------------|-------------|
|Herhangi bir tek karakteri (dışında bir satır sonu) eşleşmesi|biçimindeki telefon numarasıdır.|`a.o` "geçici" içindeki "aro" ve "hakkında" içindeki "abo" ancak değil "eri" "arasında" ile eşleşir.|
|Önündeki ifadeyi sıfır veya daha çok tekrarı eşleşen (mümkün olduğunca sayıda karakteri eşleştirmek)|*|`a*r` "dolapta" "r", "ark" "ar" ve "aardvark" "aar" ile eşleşir|
|Sıfır veya daha fazla kez herhangi bir karakteri eşleştirmek (joker karakter *)|.*|c.*e eşleşen "yasadışı etkinlik" "cke", "comment" "comme" ve "Code" "code"|
|Önündeki ifadeyi bir veya daha fazla oluşumları eşleşen (mümkün olduğunca sayıda karakteri eşleştirmek)|+|`e.+e` "Besleyici" ancak değil "ee" "eede" ile eşleşir.|
|Bir veya daha fazla (joker?) herhangi bir karakter eşleşmesi|.+|e. + e "Besleyici" ancak değil "ee" "eede" ile eşleşir.|
|Önündeki ifadeyi sıfır veya daha çok tekrarı eşleşen (mümkün olduğu kadar az karakterle eşleşen)|*?|`e.*?e` "Besleyici" ancak değil "eede" "ee" ile eşleşir.|
|Önündeki ifadeyi bir veya daha fazla oluşumları eşleşen (mümkün olduğu kadar az karakterle eşleşen)|+?|`e.+?e` "Telefo" ve "Kurumsal" ancak değil tam sözcükleri "Kuruluş" "erprise" ile eşleşir.|
|Bir satır veya dize başlangıcını eşleşme dizeye sabitleme|^|`^car` yalnızca bir satır başında görüntülendiğinde "araba" word eşleşir.|
|Satırın sonuna eşleşme dizeye sabitleme|\r?$|`End\r?$` "yalnızca ne zaman bir satırın sonunda görüntülenir son" ile eşleşir.|
|Kümedeki herhangi bir tek karakterle eşleşen|[abc]|`b[abc]` "ba", "bb" ve "bc" ile eşleşir.|
|Karakter aralığı içinde herhangi bir karakter eşleşmesi|[a-f]|`be[n-t]` "içindeki"arasında","altında"içindeki" ben"ve"bes"içindeki"yanındaki"ancak değil"altında"sonuç" eşleşir.|
|Yakalama ve örtük olarak parantez içinde yer alan ifade sayı|()|`([a-z])X\1` "aXa" ve "bXb" ancak değil "aXb" ile eşleşir. İlk ifade grubu "[a-z]" "\1" başvuruyor.|
|Bir eşleşme geçersiz kıl|(?!abc)|`real (?!ity)` eşleşme "gerçek" "Gayrimenkul" ve "gerçekten" ancak değil söz "gerçekte." Bu ayrıca ikinci "gerçek" (ancak değil ilk "gerçek") "realityreal içinde" bulur.|
|Belirli bir karakter kümesi değil herhangi bir karakter eşleşmesi|[^ abc]|`be[^n-t]` "bef" ile eşleşen "önce", "arka plan", "beh" ve "bel" içindeki "altında" ancak değil "altında".|
|Eşleşen ifadesinden önce veya simgesinden sonra bir.|&#124;|`(sponge&#124;mud) bath` eşleşme "Sünger banyo" ve "mud banyo."|
|Kaçış aşağıdaki ters eğik çizgi karakteri| \\ |`\^` karakterle eşleşir ^.|
|Önceki karakter veya grubun yinelenme sayısını belirtin|{x}, x yineleme sayısı,|`x(ab){2}x` "xababx" ile eşleşen ve `x(ab){2,3}x` "xababx" ve "xabababx" ancak değil "xababababx" ile eşleşir.|
|Burada "X" Unicode numarasıdır bir Unicode karakter sınıfında metinle eşleşen. Unicode karakter sınıfları hakkında daha fazla bilgi için bkz:<br /><br /> [Unicode standart 5.2 karakter özelliklerini](http://www.unicode.org/versions/Unicode5.2.0/ch04.pdf).|\p{X}|`\p{Lu}` "T" ve "Thomas Doe"nun "D" ile eşleşir.|
|Word sınır eşleşmesi|`\b` (Karakter sınıf dışında \b bir word sınırı ve karakter içinde sınıfı bir geri belirtir).|`\bin` "içinde" değil "pinto ancak" "İç içinde" eşleşir.|
|Satır sonu (yeni bir satır ve ardından başka bir deyişle, bir satır başı) eşleşmesi.|\r?\n|`End\r?\nBegin` "Bitiş" ve "yalnızca bir satır son dizede"Bitiş"olduğunda ve"Başlangıç"sonraki satıra ilk dizesinde başlayın" ile eşleşir.|
|Alfasayısal bir karakterle eşleşmesi|\w|`a\wd` eşleşme "Ekle" ve "a1d" ancak değil "d".|
|Herhangi bir boşluk karakteri eşleştirmek.|(? ([^ \r\n])\s)|`Public\sInterface` "Ortak arabirimi" tümceciği eşleşir.|
|Sayısal bir karakterle eşleşmesi|\d|`\d` eşleşme ve "3.", "3456", "2" içindeki 23" ve"1.","1".|
|Unicode karakter eşleşmesi|\uXXXX burada XXXX Unicode karakter değerini belirtir.|`\u0065` "e" karakteri ile eşleşir.|
|Tanımlayıcı eşleşmesi|\b(_\w+&#124;[\w-[0-9\_]]\w*)\b|Eşleşme "type1" ama & type1 "veya" #define ".|
|Tırnak işaretleri içine bir dizeyle eşleştir|((\\".+?\\")&#124;('.+?'))|Tek veya çift tırnak içine herhangi bir dizeyle eşleşir.|
|Bir onaltılık sayı eşleşmesi|\b0[xx]([0-9a-FA-F]\)\b|"0xc67f" ancak değil "0xc67fc67f" ile eşleşmez.|
|Eşleşme tamsayılar ve ondalık basamaklar|\b[0-9]*\\.\*[0-9]+\b|"1,333" eşleşir.|

> [!TIP]
> Windows işletim sistemlerinde, çoğu satırları "\r\n" (ve ardından yeni bir satır başı) içinde sona. Bu karakterler görünmez, ancak Düzenleyicisi'nde mevcut olan ve .NET normal ifade hizmetine geçirilir.

## <a name="see-also"></a>Ayrıca bkz.

- [Metin Bulma ve Değiştirme](../ide/finding-and-replacing-text.md)