---
title: "Exec yöntemi (normal ifade) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- exec
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- matching strings
- Exec method
ms.assetid: 83092452-60cc-4218-b4ae-af9e3cb96c34
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 426cc1a8162b03090289cf737a03d64a75df77e9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="exec-method-regular-expression-javascript"></a>exec Yöntemi (Normal İfade) (JavaScript)
Bir arama normal ifade deseni kullanarak bir dize yürütür ve arama sonuçlarını içeren bir dizi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
rgExp.exec(str)   
```  
  
## <a name="parameters"></a>Parametreler  
 `rgExp`  
 Gerekli. Örneği bir **normal ifade** normal ifade deseni ve geçerli bayrakları içeren nesne.  
  
 `str`  
 Gerekli. `String` Nesne veya arama yapmak, değişmez dize değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `exec` yöntemi, bir eşleşme bulamazsa, döndürür `null`. Bir eşleşme bulursa `exec` bir dizi ve genel özelliklerini döndürür `RegExp` nesne eşleşme sonuçlarını yansıtacak şekilde güncelleştirilir. Dizinin sıfır öğesi içeren öğeleri 1 - sırasında tüm eşleşme  *n*  içinde eşleşme oluşmuş submatches içerir. Bu davranış için davranışını aynıdır `match` genel bayrağı olmadan yöntemi (**g**) ayarlayın.  
  
 Normal bir ifade için genel bayrağı ayarlarsanız `exec` değeri tarafından belirtilen konumda başlayan dize arar `lastIndex`. Genel bayrağı ayarlanmamışsa `exec` değerini yoksayar `lastIndex` ve aramaları dizesinin başından.  
  
 Tarafından döndürülen dizi `exec` yöntemi sahip üç özellik **giriş**, **dizin** ve **lastIndex.** **Giriş** özelliği, tüm Aranan dizesi içerir. **Dizin** özelliği, tam Aranan dizesi içinde eşleşen alt dizenin konumunu içerir. `lastIndex` Özellik eşleşme son harfinden konumunu içerir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `exec` yöntemi:  
  
```JavaScript  
function RegExpTest()  
{  
   var ver = Number(ScriptEngineMajorVersion() + "." + ScriptEngineMinorVersion())  
   if (ver < 5.5)  
   {  
      document.write("You need a newer version of JavaScript for this to work");  
      return;  
   }  
  
   var src = "The quick brown fox jumps over the lazy dog.";  
  
   // Create regular expression pattern with a global flag.  
   var re = /\w+/g;  
  
   // Get the next word, starting at the position of lastindex.  
   var arr;  
   while ((arr = re.exec(src)) != null)  
      {  
      // New line:  
      document.write ("<br />");    
      document.write (arr.index + "-" + arr.lastIndex + " ");  
      document.write (arr[0]);  
      }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [normal ifade nesnesi](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [match yöntemi (dize)](../../javascript/reference/match-method-string-javascript.md)   
 [RegExp nesnesi](../../javascript/reference/regexp-object-javascript.md)   
 [Normal ifade sözdizimini (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [search yöntemi (dize)](../../javascript/reference/search-method-string-javascript.md)   
 [test yöntemi (normal ifade)](../../javascript/reference/test-method-regular-expression-javascript.md)   
 [Normal ifade programlama (JavaScript)](http://msdn.microsoft.com/en-us/3b62e27c-4f07-4726-a95b-6e841807bfaf)