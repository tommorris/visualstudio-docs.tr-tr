---
title: "lastMatch özelliği ($&amp;) (RegExp) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: $&
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- lastMatch property ($%)
- lastMatch property ($&)
ms.assetid: d223836d-5235-48a5-a926-d20764ad3f14
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 25991bf5b577d785fc4f7d8c6b2af14b93486000
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="lastmatch-property-amp-regexp-javascript"></a>lastMatch özelliği ($&amp;) (RegExp) (JavaScript)
Son eşleşen karakterler herhangi normal ifade araması döndürür. Salt okunur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
RegExp.lastMatch  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu özellik ile ilişkilendirilmiş nesne her zaman geneldir `RegExp` nesnesi.  
  
 Başlangıç değeri `lastMatch` boş bir dize bir özelliktir. Değeri `lastMatch` başarılı bir eşleşme yapıldığında özelliğini değiştirir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `lastMatch` özelliği:  
  
```JavaScript  
// Create the regular expression pattern.  
var re = new RegExp("d(b+)(d)","ig");  
var str = "cdbBdbsbdbdz";  
  
// Perform the search.  
var arr = re.exec(str);  
  
// Print the output.  
var s = ""   
s += "$1: " + RegExp.$1 + "<br />";  
s += "$2: " + RegExp.$2 + "<br />";  
s += "$3: " + RegExp.$3 + "<br />";  
s += "input: " + RegExp.input + "<br />";  
s += "lastMatch: " + RegExp.lastMatch + "<br />";  
s += "leftContext: " + RegExp.leftContext + "<br />";  
s += "rightContext: " + RegExp.rightContext + "<br />";   
s += "lastParen: " + RegExp.lastParen + "<br />";  
  
document.write(s);  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Uygulandığı öğe**: [RegExp nesnesi](../../javascript/reference/regexp-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [$1... $9 özellikleri (RegExp)](../../javascript/reference/dollar-1-dot-dot-dot-dollar-9-properties-regexp-javascript.md)   
 [index özelliği (RegExp)](../../javascript/reference/index-property-regexp-javascript.md)   
 [input özelliği ($_) (RegExp)](../../javascript/reference/input-property-dollar-regexp-javascript.md)   
 [lastIndex özelliği (RegExp)](../../javascript/reference/lastindex-property-regexp-javascript.md)   
 [lastParen özelliği ($ +) (RegExp)](../../javascript/reference/lastparen-property-dollar-regexp-javascript.md)   
 [leftContext özelliği ($') (RegExp)](../../javascript/reference/leftcontext-property-dollar-grave-regexp-javascript.md)   
 [rightContext özelliği ($') (RegExp)](../../javascript/reference/rightcontext-property-dollar-regexp-javascript.md)