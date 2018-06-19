---
title: İşleçler (JavaScript) | Microsoft Docs
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
- JavaScript, operators
ms.assetid: b8602b69-aba9-46e8-86e1-cb533ad41410
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a3068a609da2468c59066ccd38f6de87cef1ed17
ms.sourcegitcommit: 873c0e1a31def013bcca1b0caa0eb0249de89bec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
ms.locfileid: "29753277"
---
# <a name="operators-javascript"></a>İşleçler (JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] eksiksiz bir aritmetik, mantıksal, bit düzeyinde işleçler, atama yanı sıra, bazı çeşitli işleçler sahiptir. Açıklamalar ve örnekler için belirli işleçlerini konulara bakın.  
  
## <a name="computational-operators"></a>Hesaplama İşleçleri  
  
|Açıklama|Simgesi|  
|-----------------|------------|  
|[Tekli değilleme](../javascript/reference/subtraction-operator-decrement-javascript.md)|-|  
|[Artırma](../javascript/reference/increment-and-decrement-operators-javascript.md)|++|  
|[Azaltma](../javascript/reference/increment-and-decrement-operators-javascript.md)|--|  
|[Çarpma](../javascript/reference/multiplication-operator-decrement-javascript.md)|*|  
|[bölme](../javascript/reference/division-operator-decrement-javascript.md)|/|  
|[Kalan aritmetik](../javascript/reference/modulus-operator-decrementjavascript.md)|%|  
|[Toplama](../javascript/reference/addition-operator-decrement-javascript.md)|+|  
|[Çıkarma](../javascript/reference/subtraction-operator-decrement-javascript.md)|-|  
  
## <a name="logical-operators"></a>Mantıksal İşleçler  
  
|Açıklama|Simgesi|  
|-----------------|------------|  
|[Mantıksal değil](../javascript/reference/logical-not-operator-decrement-exclpt-javascript.md)|!|  
|[Küçüktür](../javascript/reference/comparison-operators-javascript.md)|\<|  
|[Büyüktür](../javascript/reference/comparison-operators-javascript.md)|>|  
|[Küçük veya eşit](../javascript/reference/comparison-operators-javascript.md)|\<=|  
|[Büyüktür veya eşittir](../javascript/reference/comparison-operators-javascript.md)|>=|  
|[Eşitlik](../javascript/reference/comparison-operators-javascript.md)|==|  
|[Eşitsizlik](../javascript/reference/comparison-operators-javascript.md)|!=|  
|[Mantıksal AND](../javascript/reference/logical-and-operator-decrement-javascript.md)|&&|  
|[Mantıksal OR](../javascript/reference/logical-or-operator-decrement-javascript.md)|&#124;&#124;|  
|[Koşullu (üçlü)](../javascript/reference/conditional-ternary-operator-decrement-javascript.md)|?:|  
|[Virgül](../javascript/reference/comma-operator-decrement-javascript.md)|,|  
|[Katı eşitlik](../javascript/reference/comparison-operators-javascript.md)|===|  
|[Katı eşitsizlik](../javascript/reference/comparison-operators-javascript.md)|!==|  
  
## <a name="bitwise-operators"></a>Bitwise İşleçleri  
  
|Açıklama|Simgesi|  
|-----------------|------------|  
|[Bit düzeyinde değil](../javascript/reference/bitwise-not-operator-decrement-tilde-javascript.md)|~|  
|[Bitsel sola kaydırma](../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)|<\<|  
|[Bitwise sağ kaydırma](../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)|>>|  
|[İmzasız sağa kaydırma](../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)|>>>|  
|[Bit düzeyinde AND](../javascript/reference/bitwise-and-operator-decrement-javascript.md)|&|  
|[Bit düzeyinde XOR](../javascript/reference/bitwise-xor-operator-decrement-hat-javascript.md)|^|  
|[Bit düzeyinde OR](../javascript/reference/bitwise-or-operator-decrement-javascript.md)|&#124;|  
  
## <a name="assignment-operators"></a>Atama İşleçleri  
  
|Açıklama|Simgesi|  
|-----------------|------------|  
|[Atama](../javascript/reference/assignment-operator-decrement-equal-javascript.md)|=|  
|[Bileşik atama](../javascript/reference/compound-assignment-operators-javascript.md)|*OP*= (+= gibi ve & =)|  
  
## <a name="miscellaneous-operators"></a>Çeşitli İşleçler  
  
|Açıklama|Simgesi|  
|-----------------|------------|  
|[delete](../javascript/reference/delete-operator-decrementjavascript.md)|Sil|  
|[typeof](../javascript/reference/typeof-operator-decrementjavascript.md)|typeof|  
|[void](../javascript/reference/void-operator-decrementjavascript.md)|void|  
|[instanceof](../javascript/reference/instanceof-operator-decrementjavascript.md)|instanceof|  
|[new](../javascript/reference/new-operator-decrementjavascript.md)|new|  
|[in](../javascript/reference/in-operator-decrementjavascript.md)|içinde|  
  
## <a name="equality-and-strict-equality"></a>Eşitlik ve Katı Eşitlik  
 Fark arasında (eşitlik) == ve === (katı eşitlik) olan eşitlik için denetlemeden önce farklı türlerde değerler eşitlik işleci coerce emin. Örneğin, 1 numaralı "1" dize karşılaştırma doğru olarak karşılaştırır. Katı eşitlik işleci diğer yandan, farklı değerlere coerce değil ve bu nedenle "1" dizesini 1 sayısına eşit olarak karşılaştırır değil.  
  
 İlkel dizeler, sayılar ve Boole değerlerini değeriyle karşılaştırılır. Bunlar aynı değeri varsa, bunlar eşit. Nesneler (de dahil olmak üzere `Array`, `Function`, `String`, **numarası**, `Boolean`, **hata**, `Date` ve `RegExp` nesneler) başvuru ile karşılaştırın. Bu tür iki değişken aynı değere sahip olsa bile, yalnızca tam olarak aynı nesneye başvurursanız bunlar eşit.  
  
 Örneğin:  
  
```JavaScript  
// Two strings with the same value.  
var string1 = "Hello";  
var string2 = "Hello";  
  
// Two String objects with the same value.  
var StringObject1 = new String(string1);  
var StringObject2 = new String(string2);  
  
if (string1 == string2)  
    document.write("string1 is equal to string2 <br/>");  
  
if (StringObject1 != StringObject2)  
    document.write("StringObject1 is not equal to StringObject2 <br/>");  
  
// To compare the values of String objects, use the toString() or valueOf() methods.  
if (StringObject1.valueOf() == StringObject2.valueOf())  
    document.write("The value of StringObject1 is equal to the value of StringObject2");  
  
//Output:  
// string1 is equal to string2   
// StringObject1 is not equal to StringObject2   
// The value of StringObject1 is equal to the value of StringObject2  
  
```