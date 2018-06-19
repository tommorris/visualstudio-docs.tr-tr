---
title: Veri türleri (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Boolean data type, supported data types
ms.assetid: c7a6bd3a-4b1c-4dbe-8505-106dbf483b41
caps.latest.revision: 35
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aa3a0e4cdbb25019758f89958afdf06c11f01a34
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789323"
---
# <a name="data-types-javascript"></a>Veri Türleri (JavaScript)
İçinde [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], üç birincil veri türleri, iki bileşik veri türleri ve iki özel veri türü vardır.  
  
## <a name="primary-data-types"></a>Birincil Veri Türleri  
 Birincil (Temel) veri türleri şunlardır:  
  
-   Dize  
  
-   Sayı  
  
-   Boole değeri  
  
## <a name="composite-data-types"></a>Bileşik Veri Türleri  
 Bileşik (başvuru) veri türleri şunlardır:  
  
-   Nesne  
  
-   Dizi  
  
## <a name="special-data-types"></a>Özel Veri Türleri  
 Özel veri türleri şunlardır:  
  
-   Null  
  
-   Tanımlanmamış  
  
## <a name="string-data-type"></a>Dize Veri Türü  
 Sıfır veya daha fazla Unicode karakterler (harfler, sayılar ve noktalama işaretlerini) zinciri bir dize değeridir. Dize veri türü metin göstermek için kullandığınız [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]. Tek veya çift tırnak işaretleri içine kapsayan tarafından komut dosyalarınızı dize değişmez değerleri içerir. Tek tırnak işaretleri dizelerde çift tırnak işaretleri bulunabilir ve tek tırnak işaretleri çift tırnak işaretleri dizelerde bulunabilir. Dizeleri örnekleri verilmiştir:  
  
```JavaScript  
"Happy am I; from care I'm free!"  
'"Avast, ye lubbers!" roared the technician.'   
"45"  
'c'  
```  
  
 Dikkat [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] bir tek karakteri temsil etmesi için bir türü yok. Bir tek karakteri temsil etmek için [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], yalnızca bir karakter içeren bir dize oluşturun. Sıfır karakter içeren bir dize ("") boş bir (sıfır uzunluklu) dize.  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]doğrudan yazamazsınız karakterler oluşturma dizelerde içerebilir kaçış sıraları sağlar. Örneğin, `\t` sekme karakteri belirtir. Daha fazla bilgi için bkz: [özel karakterleri](../javascript/advanced/special-characters-javascript.md).  
  
## <a name="number-data-type"></a>Sayı Veri Türü  
 İçinde [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], tamsayı ve kayan nokta değerlerini; arasında fark yoktur bir [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] numarası ya da olabilir (dahili olarak, [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] kayan nokta değerleri olarak tüm sayıları temsil eder).  
  
### <a name="integer-values"></a>Tamsayı Değerler  
 Tamsayı değerleri pozitif tamsayılar, negatif tam sayılar ve 0 olabilir. Bunlar temel 10 (ondalık) temsil edilebilir, 16 (onaltılık) temel ve 8 (sekizlik) temel. Çoğu numaraları [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] ondalık yazılır.  
  
 Başında "0 x ile" ekleyerek onaltılık ("onaltılık") tamsayılar belirtmek (sıfır ve x &#124; X). Sayı 0 ile 9 ve harfler F (büyük veya küçük harf) aracılığıyla içerebilirler yalnızca. Harfler ile F tek sayı, 10-15 temel 10 olarak temsil etmek için kullanılır. Diğer bir deyişle, 0xF 15'e eşdeğerdir ve 0x10 16 eşdeğerdir.  
  
 Sekizlik tamsayılar bir başında "0" (sıfır) ekleyerek gösterir. Sayı 0 ile 7 yalnızca içerebilirler. Önde gelen "0" ve "8" ve/veya "9" basamak içeren bir sayı ondalık bir sayı olarak yorumlanır.  
  
 Onaltılık ve sekizli sayı negatif olabilir ancak bir ondalık bölümü olamaz ve (üstel) bilimsel gösterimde yazılamaz.  
  
> [!NOTE]
>  İtibariyle [!INCLUDE[jsv9text](../javascript/includes/jsv9text-md.md)], [parseInt işlevi](../javascript/reference/parseint-function-javascript.md) sekizli olarak "0" ön ekine sahip bir dize kabul etmiyor. Değil kullanırken `parseInt` işlev, ancak "0" öneki dizelerle hala olarak sekizli yorumlanabilir.  
  
### <a name="floating-point-values"></a>Kayan Nokta Değerleri  
 Kayan nokta değerlerine tam sayılar ondalık bir bölümü olabilir. Ayrıca, bilimsel gösterimde belirtilebilir. Diğer bir deyişle, bir büyük veya küçük harf "e", "on gücünü olarak" temsil etmek için kullanılır. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]sekiz bayt IEEE 754 kayan nokta standart sayısal gösterimi kullanarak sayıyı temsil eder. Bu sayı 1.79769x10 büyük yazma anlamına gelir<sup>308</sup>ve 5 x 10 olabildiğince küçük<sup>-324</sup>. Ondalık içeren ve ondalık ayırıcıdan önce tek "0" olan bir sayı ondalık bir kayan noktalı sayı olarak yorumlanır.  
  
 "0 x" veya "00" ile başlayan ve ondalık içeren bir sayı bir hata oluşturur dikkat edin. Bazı örnekler şunlardır [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] sayı.  
  
|Sayı|Açıklama|Ondalık eşdeğeri|  
|------------|-----------------|------------------------|  
|.0001, 0.0001, 1e-4, 1.0E-4|Dört eşdeğer kayan nokta sayıları.|0.0001|  
|3.45e2|Bir kayan noktalı sayı.|345|  
|45|Bir tam sayı.|45|  
|0378|Bir tam sayı. (Sıfır ile başlayan) sekizlik bir sayı gibi bu görünüyor ancak sayı ondalık olarak kabul edilir şekilde 8 geçerli bir sekizli basamak değil.|378|  
|0377|Sekizlik tamsayı. Bu yalnızca bir'den küçük Yukarıdaki sayı, gerçek değerini görünmesine karşın oldukça farklı olduğuna dikkat edin.|255|  
|0.0001|Kayan nokta sayısı. Bu bir Sıfırla başlayan olsa bile, ondalık içerdiğinden bu sekizlik bir sayı değil.|0.0001|  
|00.0001|Bu bir hatadır. İki başında sıfır sayıyı bir sekizli olarak işaretlemek, ancak bir ondalık bileşeni octals izin verilmiyor.|Yok (Derleyici Hatası)|  
|0Xff|Onaltılık bir tamsayı.|255|  
|0x37CF|Onaltılık bir tamsayı.|14287|  
|0x3e7|Onaltılık bir tamsayı. 'E' üs işlenmez dikkat edin.|999|  
|0x3.45e2|Bu bir hatadır. Onaltılık sayı ondalık bölümleri sahip olamaz.|Yok (Derleyici Hatası)|  
  
 Ayrıca, [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] özel değerlerle numaralarını içerir. Bunlar:  
  
-   NaN (sayı değil). Dizeleri veya Tanımsız değer gibi uygun olmayan veriler üzerinde bir matematik işlemi gerçekleştirildiğinde kullanılır  
  
-   Pozitif sonsuzluk. Pozitif bir sayı olarak temsil etmek için çok büyük olduğunda kullanılır[!INCLUDE[javascript](../javascript/includes/javascript-md.md)]  
  
-   Negatif sonsuzluk. Negatif bir sayı olarak temsil etmek için çok büyük olduğunda kullanılır[!INCLUDE[javascript](../javascript/includes/javascript-md.md)]  
  
-   Pozitif ve negatif 0. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]pozitif ve negatif sıfır arasında ayırır.  
  
## <a name="boolean-data-type"></a>Boole Veri Türü  
 Dize ve sayı veri türleri farklı değerler neredeyse sınırsız sayıda içerebilir oysa Boole veri türü yalnızca iki olabilir. Değişmez değerler oldukları `true` ve `false`. Bir Boole değeri olan bir truth-value: koşul true olup olmadığını belirtir.  
  
 Komut dosyalarınızı her zaman yaptığınız karşılaştırmaları bir Boolean sonucu vardır. Aşağıdaki satırı göz önünde bulundurun [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] kodu.  
  
```JavaScript  
y = (x == 2000);  
```  
  
 Burada, değişkenin değerini `x` numarası 2000 karşılaştırılır. Bu karşılaştırma sonucu Boolean değeri ise, **true**, değişkenine atanan `y`. Varsa `x` Boolean değer karşılaştırma sonucu ise 2000'e eşit değil `false`.  
  
 Boole değerleri denetim yapıları özellikle yararlı olur. Aşağıdaki kod bir Boole değeri doğrudan kullandığı bir deyimiyle oluşturan bir karşılaştırma birleştirir. Aşağıdakileri göz önünde bulundurun [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] kod örneği.  
  
```JavaScript  
if (x == 2000) {  
    z = z + 1;  
}  
else {  
    x = x + 1;  
}  
```  
  
 `if/else` Deyiminde [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] bir Boole değeri ise, bir eylem gerçekleştirir `true` (`z = z + 1`) ve Boole değeri ise alternatif bir eylem `false` (`x = x + 1`).  
  
 Herhangi bir ifade karşılaştırmalı bir ifade olarak kullanabilirsiniz. 0, null, tanımlanmamış veya boş veren herhangi bir ifade dize olarak yorumlanır `false`. Başka bir değer veren bir ifade olarak yorumlanır `true`. Örneğin, bir ifade gibi kullanabilirsiniz:  
  
```JavaScript  
// This may not do what you expect. See below!  
if (x = y + z)   
```  
  
 Yukarıdaki satırında denetlemez Not olup olmadığını `x` eşittir `y + z`, yalnızca bir tek eşittir işaretinden (atama işleci) kullanıldığından. Bunun yerine, yukarıdaki kod değeri atar `y + z` değişkenine `x`ve ardından denetler olup olmadığını tüm ifadenin sonucu (değerini `x`) sıfırdır. Denetlenecek olup olmadığını `x` eşittir `y + z`, aşağıdaki kodu kullanmanız gerekir.  
  
```JavaScript  
// This is different from the code above!  
if (x == y + z)   
```  
  
 Karşılaştırmaları hakkında daha fazla bilgi için bkz: [denetleme Program akış](../javascript/controlling-program-flow-javascript.md).  
  
## <a name="the-null-data-type"></a>Null Veri Türü  
 `null` Veri türü yalnızca bir değere sahip [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]: null. `null` Anahtar sözcüğü bir işlevi veya değişken adı olarak kullanılamaz.  
  
 İçeren bir değişkeni `null` hiçbir geçerli sayısı, dize, Boolean, dizi veya nesne içerir. Bir değişken içeriğini (değişkeni silmeden) atama tarafından silebilirsiniz `null` değeri.  
  
 Uygulamasında fark [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], `null` 0 ile aynı değildir (C ve C++ olduğu gibi). Ayrıca `typeof` işlecinde [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] raporları `null` türü olarak değerleri `Object`, türünde değil `null`. Bu büyük olasılıkla kafa karıştırıcı davranış geriye dönük uyumluluk içindir.  
  
## <a name="the-undefined-data-type"></a>Tanımlanmamış Veri Türü  
 `undefined` Bildirildi, ancak hiçbir zaman sahip bir değişken kendisine atanmış bir değere sahip veya var olmayan bir nesnenin özelliğini kullandığınızda değeri döndürülür.  
  
 bir değişken için karşılaştırarak olup olmadığını kontrol edebilirsiniz `undefined`, türü olup olmadığını kontrol edebilirsiniz ancak `undefined` "tanımsız dizeye değişkeninin türü karşılaştırarak". Aşağıdaki örnek değişkenini bulmayı gösteren `x` bildirilmiş:  
  
```JavaScript  
  
var x;  
  
// This method works.  
if (x == undefined) {  
    document.write("comparing x to undefined <br/>");  
}  
.  
// This method doesn't work - you must check for the string "undefined".  
if (typeof(x) == undefined) {  
    document.write("comparing the type of x to undefined <br/>");  
}  
// This method does work.   
if (typeof(x) == "undefined") {  
    document.write("comparing the type of x to the string 'undefined'");  
}  
  
// Output:   
// comparing x to undefined   
// comparing the type of x to the string 'undefined'  
  
```  
  
 Tanımsız değer de karşılaştırabilirsiniz `null`. Bu karşılaştırma `true` varsa özelliği `someObject.prop` olan `null` veya özelliği `someObject.prop` yok.  
  
```JavaScript  
someObject.prop == null;  
```  
  
 Bir nesnenin özelliğini varolup çıkışı bulmak için kullanabileceğiniz **içinde** işleci:  
  
```JavaScript  
if ("prop" in someObject)  
    // someObject has the property 'prop'  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nesneler ve diziler](../javascript/objects-and-arrays-javascript.md)   
 [typeof işleci](../javascript/reference/typeof-operator-decrementjavascript.md)