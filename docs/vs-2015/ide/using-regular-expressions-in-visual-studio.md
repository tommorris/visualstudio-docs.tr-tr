---
title: Visual Studio'da normal ifadeler kullanarak | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
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
caps.latest.revision: 56
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c74ed503b13e9f5efab3e6bf0df2fab75d34e7cb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630568"
---
# <a name="use-regular-expressions-in-visual-studio"></a>Visual Studio'da normal ifadeler kullanma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Visual Studio'da normal ifadeler kullanarak](https://docs.microsoft.com/visualstudio/ide/using-regular-expressions-in-visual-studio).

Visual Studio metin bulma ve değiştirme için .NET Framework normal ifadelerini kullanır. .NET normal ifadeler hakkında daha fazla bilgi için bkz. [.NET Framework normal ifadelerinde](http://msdn.microsoft.com/library/521b3f6d-f869-42e1-93e5-158c54a6895d).

Önce Visual Studio 2012, Visual Studio Bul ve Değiştir pencerelerinde özel normal ifade sözdizimi kullanılır. Bkz: [Visual Studio normal ifade dönüştürmeler](https://msdn.microsoft.com/library/2k3te2cs\(v=vs.110\).aspx) bazı sık kullanılan özel normal ifade simgelerinin .NET sürümlerine nasıl dönüştürmek bir açıklama için.

> [!TIP]
> Windows işletim sistemlerinde satırların çoğu "\r\n" (bir yeni satırın izlediği bir satır başı) bitmelidir. Bu karakterler görünür değildir ancak düzenleyicide bulunur ve .NET normal ifade hizmetine iletilir.

> [!TIP]
> Değiştirme desenlerinde kullanılan düzenli ifadeler hakkında daha fazla bilgi için bkz: [değişimler](http://msdn.microsoft.com/library/d1f52431-1c7d-4dc6-8792-6b988256892e). Numaralandırılmış yakalama grubu kullanmak için sözdizimi aşağıdaki gibidir `$1` numaralı grubu belirtmek için ve `(x)` söz konusu grubu belirtmek için. Örneğin, gruplanan normal ifadeyle `(\d)([a-z])` aşağıdaki dizede dört eşleşme bulur: **1a 2b 3c 4d**. Değiştirme dizesi `z$1` Bu dizeye dönüştürür **z1 z2 z3 z4**.

## <a name="regular-expression-examples"></a>Normal ifade örnekleri

Bazı örnekler şunlardır:

|Amaç|İfade|Örnek|
|-------------|----------------|-------------|
|(Satır sonu hariç) tek bir karakterle eşleştir|biçimindeki telefon numarasıdır.|`a.o` "Around" öğesinde "ARO" ve "about" öğesinde "abo" ancak değil "eri" "arasında" ile eşleşir.|
|Önünde gelen ifadenin sıfır veya daha çok tekrarı ile eşleştir (mümkün olduğu kadar çok karakterle Eşleştir)|*|`a*r` "rack" daki "r", "ark" içinde "ar" ve "aardvark", "aar" ile eşleşir.|
|Sıfır veya daha fazla kez herhangi bir karakterle eşleştir (joker karakter *)|.*|c.*e "comme" "racket", "comment" "comme" ve "Code" ve "code" ile eşleşir|
|Önünde gelen ifadenin bir veya daha çok tekrarı ile eşleştir (mümkün olduğu kadar çok karakterle Eşleştir)|+|`e.+e` "eede" ile eşleşir ancak değil "ee" içindeki "eede" ile eşleşir.|
|Bir veya daha fazla (joker?) herhangi bir karakterle eşleştir|.+|e. + e, "Besleyici" içindeki "eede" ile eşleşir ancak değil "ee".|
|Önünde gelen ifadenin sıfır veya daha çok tekrarı ile eşleştir (mümkün olduğu kadar az karakterle Eşleştir)|*?|`e.*?e` "eede" ile eşleşir ancak "eede" içinde "ee" ile eşleşir.|
|Önünde gelen ifadenin bir veya daha çok tekrarı ile eşleştir (mümkün olduğu kadar az karakterle Eşleştir)|+?|`e.+?e` "Telefo" ve "erprise" ile "Kurumsal" ancak değil tüm "enterprise" kelimesinin eşleşir.|
|Eşleşme dizesini bir satırın veya dizenin başına bağlantı|^|`^car` yalnızca satırın başında göründüğünde "car" sözcüğü eşleştirir.|
|Eşleşme dizesini bir satırın sonuna Bağla|\r?$|`End\r?$` "yalnızca, bir satırın sonunda göründüğünde end" ile eşleşir.|
|Bir kümedeki tek bir karakterle eşleştir|[abc]|`b[abc]` "ba", "bb" ve "bc" ile eşleşir.|
|Karakter aralığındaki herhangi bir karakterle eşleştir|[a-f]|`be[n-t]` "içinde"between","beneath"içinde" ben"ve"bes""beside", ancak"below"bet" eşleşir.|
|Yakalama ve parantez içinde yer alan ifadesi örtük olarak numaralandır|()|`([a-z])X\1` "aXa" ve "bXb" ancak değil "aXb" ile eşleşir. ". "\1", ilk ifade grubu "[a-z]" anlamına gelir.|
|Eşlemeyi geçersiz kıl|(?!abc)|`real (?!ity)` "gerçek" bir "realty" ve "really" eşleşir ancak değil içinde "gerçeklik." Ayrıca ikinci "real" (ancak değil ilk "real") "realityreal" içinde bulur.|
|Belirli bir karakter kümesinde olmayan herhangi bir karakterle eşleştir|[^ abc]|`be[^n-t]` "önce", "behind", "beh" içinde "bef" ile eşleşir ve "BEh" "below", ancak "beneath".|
|Önce ifadesi veya bir sonraki eşleştirin.|&#124;|`(sponge&#124;mud) bath` "sponge bath" ve "mud bath" ile eşleşir|
|Eğik çizgiyi takip eden karakterden çıkış yapın|\|`\^` bir karakterle eşleşir ^.|
|Önceki karakterin veya grubun oluşum sayısını belirtin|{x}, burada x oluşum sayısıdır|`x(ab){2}x` "xababx" ile eşleşir ve `x(ab){2,3}x` "xababx" ve "xabababx ile eşleşir" ancak değil "xababababx" ile eşleşir.|
|Metni "X" değerinin Unicode numarası olduğu bir Unicode karakter sınıfı eşleştirin. Unicode karakter sınıfları hakkında daha fazla bilgi için bkz.<br /><br /> [Unicode standart 5.2 karakter özellikleri](http://www.unicode.org/versions/Unicode5.2.0/ch04.pdf).|\p{X}|`\p{Lu}` "T" ve "Thomas Doe" içinde "D" ile eşleşir.|
|Bir sözcük sınırını eşleştir|`\b` (Bir karakter sınıfı dışında sözcük sınırını \b belirler ve içinde bir karakter sınıfı bir geri belirtir).|`\bin` "içinde" inside "içinde" değil "pinto" eşleşir.|
|Satır sonu (yeni bir satır tarafından izlenen IE bir satır başı) eşleştirin.|\r?\n|`End\r?\nBegin` "Son" ve "olduğunda yalnızca"End"bir satırdaki son dizeyse ve"Begin"sonraki satırdaki ilk dizedir Begin" ile eşleşir.|
|Herhangi bir alfasayısal karakteri eşleştir|\w|`a\wd` eşleşme "Ekle" ve "a1d ile eşleşir" ancak "a d".|
|Bir boşluk karakteriyle Eşleştir.|(? ([^ \r\n])\s)|`Public\sInterface` ' % s'ifadesinin "Ortak arabirim" ile eşleşir.|
|Bir sayısal karakterle eşleştir|\d|`\d` eşleşiyor ve "3", "3456" 23" içinde" 2"ve"1"içinde"1".|
|Unicode karakterini eşleştir|\uXXXX nerede XXXX Unicode karakter değerini belirtir.|`\u0065` "e" karakteriyle eşleşir.|
|Tanımlayıcı eşleştir|\b(_\w+&#124;[\w-[0-9\_]]\w*)\b|Eşleşme "type1" ama & type1 "veya" #define ".|
|Tırnak işaretleri içindeki bir dizeyle eşleştir|((\\".+?\\")&#124;('.+?'))|Tek veya çift tırnak içindeki herhangi bir dizeyle eşleşir.|
|Onaltılık bir sayıyla eşleştir|\b0[xx]([0-9a-FA-F]\)\b|"0xc67f ile eşleşir" ancak "0xc67fc67f" ile eşleşir.|
|Eşleşme tamsayıları ve ondalık sayıları|\b[0-9]*\\.\*[0-9]+\b|"1.333" eşleşir.|