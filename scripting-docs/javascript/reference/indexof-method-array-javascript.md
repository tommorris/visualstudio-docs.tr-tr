---
title: indexOf yöntemi (dizi) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- arrays [JavaScript], indexOf method
- indexOf method [JavaScript]
ms.assetid: 5bee31ae-aaf1-4466-8cfd-ed287e3cdf17
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 63685219faf42991da6b798493c58b356ab97279
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790754"
---
# <a name="indexof-method-array-javascript"></a>indexOf Yöntemi (Dizi) (JavaScript)
Bir dizi içinde bir değerin ilk geçtiği dizini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
array1.indexOf(searchElement[, fromIndex])  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Tanım|  
|---------------|----------------|  
|`array1`|Gerekli. Bir dizi nesnesi.|  
|`searchElement`|Gerekli. Bulunacak değer `array1`.|  
|`fromIndex`|İsteğe bağlı. Aramanın başlatılacağı dizi dizini. Varsa `fromIndex` olan atlanırsa, 0 dizininde arama başlatır.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 İlk örneğini dizinini `searchElement` dizi ya da-1 IF `searchElement` bulunamadı.  
  
## <a name="remarks"></a>Açıklamalar  
 `indexOf` Yöntemi için belirtilen değer bir dizi arar. Belirtilen değer bulunamazsa, yöntem ilk a geçişi veya -1 dizinini döndürür.  
  
 Arama dizini artan düzende oluşur.  
  
 Dizi öğeleri karşılaştırılır `searchElement` katı eşitlik, benzer değeriyle `===` işleci. Daha fazla bilgi için bkz: [Karşılaştırma işleçleri](../../javascript/reference/comparison-operators-javascript.md).  
  
 İsteğe bağlı `fromIndex` bağımsız değişkeni aramanın başlatılacağı dizi dizini belirtir. Varsa `fromIndex` değerinden büyük veya eşit dizi uzunluğu, -1 döndürülür. Varsa `fromIndex` olan artı dizi uzunluğu negatif, aramayı başlatır `fromIndex`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler kullanımını göstermek `indexOf` yöntemi.  
  
```JavaScript  
// Create an array. (The elements start at index 0.)  
var ar = ["ab", "cd", "ef", "ab", "cd"];  
  
// Determine the first location of "cd".  
document.write(ar.indexOf("cd") + "<br/>");  
  
// Output: 1  
  
// Find "cd" starting at index 2.  
document.write(ar.indexOf("cd", 2) + "<br/>");  
  
// Output: 4  
  
// Find "gh" (which is not found).  
document.write (ar.indexOf("gh")+ "<br/>");  
  
// Output: -1  
  
// Find "ab" with a fromIndex argument of -2.  
// The search starts at index 3, which is the array length plus -2.  
document.write (ar.indexOf("ab", -2) + "<br/>");  
// Output: 3  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript yöntemleri](../../javascript/reference/javascript-methods.md)   
 [Dizi nesnesi](../../javascript/reference/array-object-javascript.md)   
 [Dizileri kullanma](../../javascript/advanced/using-arrays-javascript.md)