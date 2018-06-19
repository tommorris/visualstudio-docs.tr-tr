---
title: multiline özelliği (normal ifade) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- multiline
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- multiline property
ms.assetid: ca7b276a-1fe2-4189-ac27-f089ab3e9974
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 289cb8d8e103d8c4ac1b1ef06714105d21cba743
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791405"
---
# <a name="multiline-property-regular-expression-javascript"></a>multiline Özelliği (Normal İfade) (JavaScript)
Çok satırlı bayrağının durumunu gösteren bir Boole değeri döndürür (**m**) normal bir ifade ile kullanılır. Varsayılan değer **false**. Salt okunur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
rgExp.multiline  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `rgExp` bağımsız değişkeni bir örneğidir `RegExp` nesnesi  
  
 **Çok satırlı** özelliği döndürür **true** multiline bayrağı için normal bir ifade ayarlanır ve döndürür, **false** değilse. **Çok satırlı** özelliği **true** normal ifade nesnesi ile oluşturulmuşsa, **m** bayrağı.  
  
 Varsa **çok satırlı** olan **yanlış**, "^" konumunu başında bir dize ve "$" eşleşen bir dize sonu konumunda eşleşir. Varsa **çok satırlı** olan **doğru**, "^" "\n" veya "\r" ve "$" Aşağıdaki konumun bir dize sonu konumunda eşleştiğinden ve "\n önceki konumu bir dize de başında konumunu eşleşen "veya"\r".  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek davranışını gösterilmektedir **çok satırlı** özelliği. "M", aşağıda gösterilen işlevi geçirirseniz, word "sırasında" sözcüğüyle değiştirilir "ve". Çok satırlı bayrağıyla ayarlandığından budur ve yeni satır karakteri sonra satırın başındaki "sırasında" word oluşur. Çok satırlı bayrağı çok satırlı dizeleri gerçekleştirilecek arama sağlar.  
  
```JavaScript  
function RegExpMultilineDemo(flag){  
   // The flag parameter is a string that contains  
   // g, i, or m.  The flags can be combined.  
  
   // Check flags for validity.  
   if (flag.match(/[^gim]/))  
      {  
      return ("Flag specified is not valid");  
      }  
  
   // Create the string on which to perform the replacement.  
   var ss = "The man hit the ball with the bat ";  
   ss += "\nwhile the fielder caught the ball with the glove.";  
  
   // Replace "while" with "and".  
   var re = new RegExp("^while", flag);  
   var r = ss.replace(re, "and");          
  
   // Output the multiline flag and the resulting string.  
   var s = "";  
   s += "Result for multiline = " + re.multiline.toString();  
   s += ": " + r;  
  
   return(s);  
  
}  
  
sa = RegExpMultilineDemo("m");  
sb = RegExpMultilineDemo("");  
document.write (sa + "<br />" + sb);  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Uygulandığı öğe**: [normal ifade nesnesi](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Global özelliği (normal ifade)](../../javascript/reference/global-property-regular-expression-javascript.md)   
 [ignoreCase özelliği (normal ifade)](../../javascript/reference/ignorecase-property-regular-expression-javascript.md)   
 [Normal ifade sözdizimini (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)