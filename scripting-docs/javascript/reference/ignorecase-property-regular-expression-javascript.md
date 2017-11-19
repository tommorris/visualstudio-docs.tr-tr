---
title: "ignoreCase özelliği (normal ifade) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: ignoreCase
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: IgnoreCase property
ms.assetid: 816f0df5-5a82-44a5-a4ab-dbc91fa76e61
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ae9fee8e6303fb944f59c11c173f9e8b7f7cc75a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="ignorecase-property-regular-expression-javascript"></a>ignoreCase Özelliği (Normal İfade) (JavaScript)
İgnoreCase bayrağının durumunu gösteren bir Boole değeri döndürür (**ı**) normal bir ifade ile kullanılır. Varsayılan değer **false**. Salt okunur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
rgExp.ignoreCase  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `rgExp` başvurudur örneği `RegExp` nesnesi.  
  
 **İgnoreCase** özelliği döndürür **true** ignoreCase bayrağı için normal bir ifade ayarlanır ve döndürür, **false** değilse.  
  
 Kullanıldığında, ignoreCase bayrağı, bir arama büyük küçük harfe duyarlılığın Aranan dizesindeki desen eşleştirme yapılırken yok saymanız gerekir olduğunu gösterir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir **ignoreCase** özelliği. "GI" içinde aşağıda gösterilen işlevi geçirirseniz, word'ün tüm örneklerini "" olan word ile değiştirildi. ilk dahil "a", "". İgnoreCase bayrağı ayarlandığında, tüm büyük küçük harfe duyarlılığın arama yoksayar olmasıdır. Bu nedenle "T" eşleştirme amacıyla "t" ile aynı olur.  
  
 Bu işlev olan izin verilen normal ifade bayrakları durumunu belirten Boole değerleri döndüren **g**, **ı**, ve **m**. İşlevi, tüm değişiklik yapıldı ile de dize döndürür.  
  
```JavaScript  
function RegExpPropDemo(flag){  
    // The flag parameter is a string that contains  
    // g, i, or m. The flags can be combined.  
  
    // Check flags for validity.  
    if (flag.match(/[^gim]/))  
        {  
        return ("Flag specified is not valid");  
        }  
  
    // Create the string on which to perform the replacement.  
    var orig = "The batter hit the ball with the bat ";  
    orig += "and the fielder caught the ball with the glove.";  
  
    // Replace "the" with "a".  
    var re = new RegExp("the", flag);  
    var r = orig.replace(re, "a");          
  
    // Output the resulting string and the values of the flags.  
    var s = "";  
    s += "global: " + re.global.toString();  
    s += "<br />";  
    s += "ignoreCase: " + re.ignoreCase.toString();  
    s += "<br />";  
    s += "multiline: " + re.multiline.toString();  
    s += "<br />";  
    s += "Resulting String: " + r;  
    s += "<br />";  
    s += "<br />";  
    return (s);  
}  
  
document.write(RegExpPropDemo("gi"));  
document.write(RegExpPropDemo("g"));  
```  
  
## <a name="example"></a>Örnek  
 Sonuçta çıktı verilmiştir.  
  
```JavaScript  
global: true  
ignoreCase: true  
multiline: false  
Resulting String: a batter hit a ball with a bat and a fielder caught a ball with a glove.  
  
global: true  
ignoreCase: false  
multiline: false  
Resulting String: The batter hit a ball with a bat and a fielder caught a ball with a glove.  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Uygulandığı öğe**: [normal ifade nesnesi](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Global özelliği (normal ifade)](../../javascript/reference/global-property-regular-expression-javascript.md)   
 [multiline özelliği (normal ifade)](../../javascript/reference/multiline-property-regular-expression-javascript.md)   
 [Normal ifade sözdizimini (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)