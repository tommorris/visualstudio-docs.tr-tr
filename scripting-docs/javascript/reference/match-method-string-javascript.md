---
title: match yöntemi (dize) (JavaScript) | Microsoft Docs
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
- match
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Match method
ms.assetid: eda9ad27-4f9b-4cb1-8345-a0ae85979ca0
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 46727942d73779351f1c0cceaf2eb90a691a8ebe
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791321"
---
# <a name="match-method-string-javascript"></a>match Yöntemi (Dize) (JavaScript)
Bir dize normal bir ifade ile eşleşen ve arama sonuçlarını içeren bir dizi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
stringObj.match(rgExp)   
```  
  
## <a name="parameters"></a>Parametreler  
 `stringObj`  
 Gerekli. `String` Nesne veya arama yapmak, değişmez dize değeri.  
  
 `rgExp`  
 Gerekli. Normal ifade deseni ve geçerli bayrakları içeren bir normal ifade nesnesi. Bu aynı zamanda bir değişken adı veya normal ifade deseni ve bayrakları içeren değişmez dize değeri olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `match` yöntemi, bir eşleşme bulamazsa, döndürür `null`. Bir eşleşme bulursa `match` bir dizi ve genel özelliklerini döndürür `RegExp` nesne eşleşme sonuçlarını yansıtacak şekilde güncelleştirilir.  
  
 Varsa genel bayrağını (`g`) ayarlı değil, dizinin sıfır içeren aracılığıyla öğelerin 1 sırasında tüm eşleşme öğesi  *n*  herhangi submatches içerir. Bu davranış davranışını aynıdır [exec yöntemi (normal ifade)](../../javascript/reference/exec-method-regular-expression-javascript.md) zaman genel bayrağı ayarlı değil. Genel bayrağı ayarlanmışsa, aracılığıyla öğelerin 0  *n*  oluştu tüm eşleşmeleri içerir.  
  
 Genel Bayrak ayarlanmazsa, tarafından döndürülen dizi `match` yöntemi sahip iki özellik `input` ve `index`. `input` Özelliği, tüm Aranan dizesi içerir. `index` Özelliği, tam Aranan dizesi içinde eşleşen alt dizenin konumunu içerir.  
  
 Varsa bayrağı `i` , arama büyük küçük harfe duyarlı değildir ayarlanmadı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `match` yöntemi.  
  
```JavaScript  
var src = "azcafAJAC";  
  
var re = /[a-c]/;  
  
var result = src.match(re);  
  
// The entire match is in array element 0.  
document.write(result[0] + "<br/>");  
  
// Now try the same match with the global flag.  
var reg = /[a-c]/g;  
result = src.match(reg);  
  
// The matches are in elements 0 through n.  
for (var index = 0; index < result.length; index++)  
{  
    document.write ("submatch " + index + ": " +  result[index]);  
    document.write("<br />");  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Uygulandığı öğe**: [dize nesnesi](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Exec yöntemi (normal ifade)](../../javascript/reference/exec-method-regular-expression-javascript.md)   
 [RegExp nesnesi](../../javascript/reference/regexp-object-javascript.md)   
 [Normal ifade nesnesi](../../javascript/reference/regular-expression-object-javascript.md)   
 [replace yöntemi (dize)](../../javascript/reference/replace-method-string-javascript.md)   
 [search yöntemi (dize)](../../javascript/reference/search-method-string-javascript.md)   
 [test yöntemi (normal ifade)](../../javascript/reference/test-method-regular-expression-javascript.md)   
 [Normal ifade programlama (JavaScript)](http://msdn.microsoft.com/en-us/3b62e27c-4f07-4726-a95b-6e841807bfaf)   
 [Değişim ve alt ifadelerin (JavaScript)](http://msdn.microsoft.com/en-us/c59dd3e8-7fee-493e-9123-065af1e651ae)   
 [Yeniden başvurular (JavaScript)](http://msdn.microsoft.com/en-us/5d8dbd5a-cd03-4548-850b-9d7bad2c839a)