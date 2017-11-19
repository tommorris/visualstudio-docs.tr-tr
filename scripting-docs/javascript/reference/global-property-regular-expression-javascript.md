---
title: "Global özelliği (normal ifade) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Global
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: global property
ms.assetid: 76a0f115-0d89-4aca-86d5-932895c6d649
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7e2b0256fea60b7ab998c504e79565fc7028cd98
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="global-property-regular-expression-javascript"></a>global Özelliği (Normal İfade) (JavaScript)
Genel bayrağının durumunu gösteren bir Boole değeri döndürür (**g**) normal bir ifade ile kullanılır. Varsayılan değer **false**. Salt okunur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
rgExp.global  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `rgExp` başvurudur örneği bir **normal ifade** nesnesi.  
  
 `global` Özelliği döndürür **true** genel bayrağı için normal bir ifade ayarlanır ve döndürür, **false** değilse.  
  
 Genel Bayrak kullanıldığında, bir arama değil yalnızca ilk dizine Aranan dizesindeki tüm deseninin bulmalıdır gösterir. Bu da genel eşleşen denir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `global` özelliği. Geçirirseniz **g** , aşağıda gösterilen işlevi sözcüğün tüm örneklerini "" olan sözcüğüyle yerine "a". "" Başında dizesinin çünkü değiştirilmez olduğunu unutmayın **ı** (servis talebi yoksay) bayrağı işlevine geçirilen değil.  
  
 Bu işlev olan izin verilen normal ifade bayraklarıyla ilişkili özellikleri durumunu görüntüler **g**, **ı**, ve **m**. İşlev dize yapılan tüm değişiklikleri ile de görüntüler.  
  
```JavaScript  
function RegExpPropDemo(flag){  
   // The flag parameter is a string that contains  
   // g, i, or m.  The flags can be combined.  
  
   // Check flags for validity.  
   if (flag.match(/[^gim]/))  
      {  
      return ("Flag specified is not valid");  
      }  
  
   // Create the string on which to perform the replacement.  
   var ss = "The batter hit the ball with the bat ";  
   ss += "and the fielder caught the ball with the glove.";  
  
   //Replace "the" with "a".  
   var re = new RegExp("the", flag);  
   var r = ss.replace(re, "a");          
  
   // Output the resulting string and the flags.  
   var s = "";  
   s += "global: " + re.global.toString();  
   s += "<br />";  
   s += "ignoreCase: " + re.ignoreCase.toString();  
   s += "<br />";  
   s += "multiline: " + re.multiline.toString();  
   s += "<br />";  
   s += "Resulting String: " + r;  
  
   return (s);  
}  
  
document.write(RegExpPropDemo("g"));  
```  
  
## <a name="example"></a>Örnek  
 Sonuçta çıktı verilmiştir.  
  
```JavaScript  
global: true  
ignoreCase: false  
multiline: false  
Resulting String: The batter hit a ball with a bat and a fielder caught a ball with a glove.  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Uygulandığı öğe**: [normal ifade nesnesi](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ignoreCase özelliği (normal ifade)](../../javascript/reference/ignorecase-property-regular-expression-javascript.md)   
 [multiline özelliği (normal ifade)](../../javascript/reference/multiline-property-regular-expression-javascript.md)   
 [Normal ifade sözdizimini (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)