---
title: "Özel karakterler (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- line terminator character
- white space character
- Unicode character
- escape sequence
- backslash (\)
ms.assetid: 3b38b1bd-1f0f-4748-b13e-55cab36fd126
caps.latest.revision: "31"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0eaae8dfc84d9a3be6db54c50558d4cf675a53a8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="special-characters-javascript"></a>Özel Karakterler (JavaScript)
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]doğrudan yazamazsınız karakterler oluşturma dizelerde içerebilir kaçış sıraları sağlar.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir dize değeri, sıfır veya daha fazla Unicode karakterler (harfler, rakamlar ve diğer karakterler) dizisidir. Dize değişmez değerleri tek veya çift tırnak işaretleri çiftlerini eşleştirmelerinde iliştirilir. Çift tırnak işaretleri içindeki tek tırnak işaretleri içine bir dize. Tek tırnak işaretleri içindeki çift tırnak işaretleri içine bir dize.  
  
 Bir değişmez dize değeri her karakteri kaçış dizisi tarafından temsil edilebilir. Bir kaçış sırası ters eğik çizgi ile başlayan (\\), sizi bilgilendirir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] sonraki karakteri bir özel karakter olduğunu yorumlayıcı.  
  
 \U kullanarak bir Unicode karakter belirtebilirsiniz*ssss* kaçış sırası, burada *ssss* dört basamaklı onaltılık bir sayıdır. Unicode kaçış sırası herhangi bir 16 bit karakteri temsil edebilir. Ek bilgi için bkz: [Unicode kod noktası kaçış sıraları](#CodePoint).  
  
 Bir tek karakteri kaçış sırası için bazı karakter kullanabilirsiniz. Örneğin, bir sekme karakteri \t belirtir.  
  
## <a name="escape-sequences"></a>Çıkış Sıraları  
 Aşağıdaki tabloda kaçış sıraları ortak karakterler için birkaç örnekleri listeler.  
  
|Unicode karakter değeri|Kaçış sırası|Açıklama|Kategori|  
|-----------------------------|---------------------|-------------|--------------|  
|\u0008|\b|Geri Al tuşu||  
|\u0009|\t|Tab|Beyaz alan|  
|\u000A|\n|(Yeni satır) satır besleme|Satır Sonlandırıcı|  
|\u000B|\v<br /><br /> (Not sonra bu tabloya bakın.)|Dikey sekme|Beyaz alan|  
|\u000C|\f|sonraki sayfaya geçme|Beyaz alan|  
|\u000D|\r|satır başı|Satır Sonlandırıcı|  
|\u0020||Alan|Beyaz alan|  
|\u0022|\\"|Çift tırnak işareti (")||  
|\u0027|\\'|Tek tırnak işareti (')||  
|\u005C|\\\|Ters eğik çizgi (\\)||  
|\u00A0||Bölünemez boşluk|Beyaz alan|  
|\u2028||Satır ayırıcı|Satır Sonlandırıcı|  
|\u2029||Paragraf ayırıcı|Satır Sonlandırıcı|  
|\uFEFF||Unicode bayt sırası işareti|Beyaz alan|  
  
 Kategori sütunu karakteri boşluk veya satır Sonlandırıcı karakteri olup olmadığını belirtir. [Trim yöntemi (dize)](../../javascript/reference/trim-method-string-javascript.md) baştaki ve sondaki boşluk ve satır Sonlandırıcı karakterleri bir dizeden kaldırır.  
  
 Ters eğik çizgi kendisini kaçış karakteri olarak kullanılır. Bu nedenle, bir komut doğrudan yazamazsınız. Ters eğik çizgi yazmak istiyorsanız, ikisi birlikte yazmalısınız (\\\\).  
  
> [!NOTE]
>  İtibariyle [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)], dikey sekme (\v) ve "v" eşdeğer için test ederek tarayıcı Internet Explorer tanımlanamıyor. Önceki sürümlerde, ifade `"\v" === "v"` döndürür `true`. İçinde [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)], ifade döndürür `false`.  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnekte gösterilmiştir \\\ ve \\' kaçış sıraları.  
  
### <a name="code"></a>Kod  
  
```JavaScript  
document.write('The image path is C:\\webstuff\\mypage\\gifs\\garden.gif.');  
document.write ("<br />");  
document.write('The caption reads, "After the snow of \'97. Grandma\'s house is covered."');  
```  
  
<a name="CodePoint"></a>   
## <a name="unicode-code-point-escape-sequences"></a>Unicode kod noktası kaçış dizileri  
 İçinde [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)], Unicode tam olarak desteklenmektedir. En yaygın Unicode kod noktası /u0009 bir sekme karakteri gibi dört onaltılık basamak gösterilir. Dörtten fazla onaltılık basamak gerektiren tüm sembolleri içeren astral kod noktaları, Basitleştirilmiş bir biçimde artık desteklenmektedir. Biçimi kullanarak "\u {*codepoint*}", tam Unicode karakter kümesinde bir değişmez değer biçiminde temsil edilebilir. Örneğin, "𠮷" simgesi temsil etmek için aşağıdaki biçimde kullanabilirsiniz: "\u{20BB7}".  
  
 Aşağıdaki kod örneğinde dizeleri tüm eşdeğerdir. (\uD842\uDFB7 önceki sürümlerinde bu simgeyi belirtmek için geçici çözüm yöntemidir.)  
  
```JavaScript  
"\u{20BB7}"=="𠮷"=="\uD842\uDFB7"  
```  
  
 RegExp şimdi astral kod noktaları için tam destek sağlamak için bir /u bayrak ekler. Örneğin, aşağıdaki kod örneğinde astral eşleşen normal ifade etkinleştirir /u bayrağı (dönem sağlanan dizedeki herhangi bir karakterle eşleşir) noktaları kodu.  
  
```JavaScript  
"𠮷".match(/./u)[0].length == 2  
```  
  
 /U bayrağı sağlayan yeni biçimi, ayrıştırma \u{codepoint}), bir Unicode olarak kaçış dizisi. Bu gereklidir çünkü \u{xxxxx} /u bayrağı farklı bir anlam normal bir ifade içeriyor.  
  
> [!NOTE]
>  Astral kod noktaları için her zaman 2 uzunluğudur. Bu davranış önceki sürümlerinde eşleşir.  
  
 Kod noktaları String.codePointAt ve String.fromCodePoint, astral desteklemek için dize nesnesi şimdi iki yeni yöntemler içerir. Örneğin, kod noktası "𠮷" simgesinin eşdeğer döndürülecek codePointAt kullanabilirsiniz.  
  
```JavaScript  
"𠮷".codePointAt(0) == 0x20BB7  
  
```  
  
 Kod noktaları kullanarak yineleyebilirsiniz `for...of` deyimi.  
  
```JavaScript  
for(var c of "𠮷") {  
    console.log(c);  
}  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [String.fromCharCode işlevi](../../javascript/reference/string-fromcharcode-function-javascript.md)