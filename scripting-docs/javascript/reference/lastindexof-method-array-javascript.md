---
title: lastIndexOf yöntemi (dizi) (JavaScript) | Microsoft Docs
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
- arrays [JavaScript], lastIndexOf method
- lastIndexOf method [JavaScript]
ms.assetid: 04f5145d-007e-498f-b06f-11ab384c2968
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 12d2a0fca7a7cd82543a83ea19aca49d3cbb93b6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790928"
---
# <a name="lastindexof-method-array-javascript"></a>lastIndexOf Yöntemi (Dizi) (JavaScript)
Bir dizi içinde bir belirtilen değerin son geçtiği dizini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
array1.lastIndexOf(searchElement[, fromIndex])  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Tanım|  
|---------------|----------------|  
|`array1`|Gerekli. Aranacak dizi nesnesi.|  
|`searchElement`|Gerekli. Bulunacak değer `array1`.|  
|`fromIndex`|İsteğe bağlı. Aramanın başlatılacağı dizi dizini. Varsa `fromIndex` olan atlandığında dizideki son dizininde arama başlatır.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 Son dizinini `searchElement` dizi ya da-1 IF `searchElement` bulunamadı.  
  
## <a name="remarks"></a>Açıklamalar  
 `lastIndexOf` Yöntemi için belirtilen değer bir dizi arar. Belirtilen değer bulunamazsa, yöntem ilk a geçişi veya -1 dizinini döndürür.  
  
 Arama dizini azalan sırada oluşur (son ilk üye). Artan düzende aramak için kullanın [indexOf yöntemi (dizi)](../../javascript/reference/indexof-method-array-javascript.md).  
  
 Dizi öğeleri karşılaştırılır `searchElement` katı eşitlik, tarafından yapılan karşılaştırma benzer değeriyle `===` işleci. Daha fazla bilgi için bkz: [Karşılaştırma işleçleri](../../javascript/reference/comparison-operators-javascript.md).  
  
 İsteğe bağlı `fromIndex` bağımsız değişkeni aramanın başlatılacağı dizi dizini belirtir. Varsa `fromIndex` değerinden daha büyük ya da dizi uzunluğuna eşit, tüm dizi aranır. Varsa `fromIndex` olan artı dizi uzunluğu negatif, aramayı başlatır `fromIndex`. Hesaplanan dizin 0'dan az ise, -1 döndürülür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler kullanımını göstermek `lastIndexOf` yöntemi.  
  
```JavaScript  
// Create an array.  
var ar = ["ab", "cd", "ef", "ab", "cd"];  
  
// Determine the first location, in descending order, of "cd".  
document.write(ar.lastIndexOf("cd") + "<br/>");  
  
// Output: 4  
  
// Find "cd" in descending order, starting at index 2.  
document.write(ar.lastIndexOf("cd", 2) + "<br/>");  
  
// Output: 1  
  
// Search for "gh" (which is not found).  
document.write(ar.lastIndexOf("gh")+ "<br/>");  
  
// Output: -1  
  
// Find "ab" with a fromIndex argument of -3.  
// The search in descending order starts at index 3,  
// which is the array length minus 2.  
document.write(ar.lastIndexOf("ab", -3) + "<br/>");  
// Output: 0  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [indexOf yöntemi (dizi)](../../javascript/reference/indexof-method-array-javascript.md)   
 [Dizi nesnesi](../../javascript/reference/array-object-javascript.md)   
 [Dizileri kullanma](../../javascript/advanced/using-arrays-javascript.md)