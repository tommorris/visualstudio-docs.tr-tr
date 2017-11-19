---
title: Visual Studio'da normal ifadeler kullanarak | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vsregularexpressionhelp
- vs.regularexpressionhelp
- vs.wildcardsbuilder
- vs.netregularexpressionhelp
- vs.wildcards
helpviewer_keywords:
- regular expressions [Visual Studio]
- regular expressions
- Visual Studio, regular expressions
ms.assetid: 718a617d-0e05-47e1-a218-9746971527f4
caps.latest.revision: "53"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c01023649879c34838cbca3172aec6b5a053f4bd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="using-regular-expressions-in-visual-studio"></a>Visual Studio'da Normal İfadeler Kullanma
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]metin bulma ve değiştirme için .NET Framework normal ifadeleri kullanır. .NET normal ifadeler hakkında daha fazla bilgi için bkz: [.NET Framework normal ifadeleri](/dotnet/standard/base-types/regular-expressions).  
  
 Visual Studio 2012 önce Visual Studio bulma ve değiştirme pencerelerinde bir özel normal ifade sözdizimi kullanılır. Bkz: [Visual Studio normal ifade dönüşümleri](https://msdn.microsoft.com/en-us/library/2k3te2cs\(v=vs.110\).aspx) daha yaygın olarak kullanılan bir özel normal ifade simgeler bazıları .NET sürümlerini dönüştürme açıklaması için.  
  
> [!TIP]
>  Windows işletim sistemlerinde, çoğu satırları "\r\n" (ve ardından yeni bir satır başı) içinde sona. Bu karakterler görünmüyorsa, ancak Düzenleyicisi'nde mevcut olan ve .NET normal ifadesi hizmete geçirilir.  
  
> [!TIP]
>  Değiştirme desenleri kullanılan normal ifadeler hakkında daha fazla bilgi için bkz: [değişimler](/dotnet/standard/base-types/substitutions-in-regular-expressions). Numaralı yakalama grubu kullanmak için söz dizimi `$1` numaralı grubu belirtmek için ve `(x)` söz konusu grup belirtmek için. Örneğin, gruplandırılmış normal ifade `(\d)([a-z])` aşağıdaki dizede dört eşleştiğini bulur: **1a 2b 3c 4d**. Değiştirme dizesini `z$1` Bu dizeye dönüştürür **z1 z2 z3 z4**.  
  
## <a name="regular-expressions-in-visual-studio"></a>Visual Studio'da normal ifadeler  
 İşte bazı örnekler  
  
|Amaç|İfade|Örnek|  
|-------------|----------------|-------------|  
|Herhangi bir tek karakteri (dışında bir satır sonu) eşleşmesi|biçimindeki telefon numarasıdır.|`a.o`"geçici" içindeki "aro" ve "hakkında" içindeki "abo" ancak değil "eri" "arasında" ile eşleşir.|  
|Önündeki ifadeyi sıfır veya daha çok tekrarı eşleşen (mümkün olduğunca sayıda karakteri eşleştirmek)|*|`a*r`"dolapta" "r", "ark" "ar" ve "aardvark" "aar" ile eşleşir|  
|Sıfır veya daha fazla kez herhangi bir karakteri eşleştirmek (joker karakter *)|.*|c.*e eşleşen "yasadışı etkinlik" "cke", "comment" "comme" ve "Code" "code"|  
|Önündeki ifadeyi bir veya daha fazla oluşumları eşleşen (mümkün olduğunca sayıda karakteri eşleştirmek)|+|`e.+e`"Besleyici" ancak değil "ee" "eede" ile eşleşir.|  
|Bir veya daha fazla (joker?) herhangi bir karakter eşleşmesi|.+|e. + e "Besleyici" ancak değil "ee" "eede" ile eşleşir.|  
|Önündeki ifadeyi sıfır veya daha çok tekrarı eşleşen (mümkün olduğu kadar az karakterle eşleşen)|*?|`e.*?e`"Besleyici" ancak değil "eede" "ee" ile eşleşir.|  
|Önündeki ifadeyi bir veya daha fazla oluşumları eşleşen (mümkün olduğu kadar az karakterle eşleşen)|+?|`e.+?e`"Telefo" ve "Kurumsal" ancak değil tam sözcükleri "Kuruluş" "erprise" ile eşleşir.|  
|Bir satır veya dize başlangıcını eşleşme dizeye sabitleme|^|`^car`yalnızca bir satır başında görüntülendiğinde "araba" word eşleşir.|  
|Satırın sonuna eşleşme dizeye sabitleme|\r?$|`End\r?$`"yalnızca ne zaman bir satırın sonunda görüntülenir son" ile eşleşir.|  
|Kümedeki herhangi bir tek karakterle eşleşen|[abc]|`b[abc]`"ba", "bb" ve "bc" ile eşleşir.|  
|Karakter aralığı içinde herhangi bir karakter eşleşmesi|[a-f]|`be[n-t]`"içindeki"arasında","altında"içindeki" ben"ve"bes"içindeki"yanındaki"ancak değil"altında"sonuç" eşleşir.|  
|Yakalama ve örtük olarak parantez içinde yer alan ifade sayı|()|`([a-z])X\1`"aXa" ve "bXb" ancak değil "aXb" ile eşleşir. ". İlk ifade grubu "[a-z]" "\1" başvuruyor.|  
|Bir eşleşme geçersiz kıl|(?! ABC)|`real (?!ity)`eşleşme "gerçek" "Gayrimenkul" ve "gerçekten" ancak değil söz "gerçekte." Bu ayrıca ikinci "gerçek" (ancak değil ilk "gerçek") "realityreal içinde" bulur.|  
|Belirli bir karakter kümesi değil herhangi bir karakter eşleşmesi|[^ abc]|`be[^n-t]`"bef" ile eşleşen "önce", "arka plan", "beh" ve "bel" içindeki "altında" ancak değil "altında".|  
|Eşleşen ifadesinden önce veya simgesinden sonra bir.|&#124;|`(sponge&#124;mud) bath`eşleşme "Sünger banyo" ve "mud banyo."|  
|Kaçış aşağıdaki ters eğik çizgi karakteri|\|`\^`karakterle eşleşir ^.|  
|Önceki karakter veya grubun yinelenme sayısını belirtin|{x}, x yineleme sayısı,|`x(ab){2}x`"xababx" ile eşleşen ve `x(ab){2,3}x` "xababx" ve "xabababx" ancak değil "xababababx" ile eşleşir.|  
|Burada "X" Unicode numarasıdır bir Unicode karakter sınıfında metinle eşleşen. Unicode karakter sınıfları hakkında daha fazla bilgi için bkz:<br /><br /> [Unicode standart 5.2 karakter özelliklerini](http://www.unicode.org/versions/Unicode5.2.0/ch04.pdf).|\p{X}|`\p{Lu}`"T" ve "Thomas Doe"nun "D" ile eşleşir.|  
|Word sınır eşleşmesi|`\b`(Karakter sınıf dışında \b bir word sınırı ve karakter içinde sınıfı bir geri belirtir).|`\bin`"içinde" değil "pinto ancak" "İç içinde" eşleşir.|  
|Satır sonu (yeni bir satırla tarafından izlenen IE bir satır başı) eşleşmesi.|\r?\n|`End\r?\nBegin`"Bitiş" ve "yalnızca bir satır son dizede"Bitiş"olduğunda ve"Başlangıç"sonraki satıra ilk dizesinde başlayın" ile eşleşir.|  
|Alfasayısal bir karakterle eşleşmesi|\w|`a\wd`eşleşme "Ekle" ve "a1d" ancak değil "d".|  
|Herhangi bir boşluk karakteri eşleştirmek.|(? ([^ \r\n])\s)|`Public\sInterface`"Ortak arabirimi" tümceciği eşleşir.|  
|Sayısal bir karakterle eşleşmesi|\d|`\d`eşleşme ve "3.", "3456", "2" içindeki 23" ve"1.","1".|  
|Unicode karakter eşleşmesi|\uXXXX burada XXXX Unicode karakter değerini belirtir.|`\u0065`"e" karakteri ile eşleşir.|  
|Tanımlayıcı eşleşmesi|\b (_\w + &#124; [ \w-[0-9\_]] \w*)\b|Eşleşme "type1" ama & type1 "veya" #define ".|  
|Tırnak işaretleri içine bir dizeyle eşleştir|((\\".+?\\")&#124;('.+?'))|Tek veya çift tırnak içine herhangi bir dizeyle eşleşir.|  
|Bir onaltılık sayı eşleşmesi|\b0[xx]([0-9a-FA-F]\)\b|"0xc67f" ancak değil "0xc67fc67f" ile eşleşmez.|  
|Eşleşme tamsayılar ve ondalık basamaklar|\b[0-9]*\\.\* [0-9] + \b0|"1,333" eşleşir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Metin bulma ve değiştirme](../ide/finding-and-replacing-text.md)