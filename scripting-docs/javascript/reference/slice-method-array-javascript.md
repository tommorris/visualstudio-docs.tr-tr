---
title: "slice yöntemi (dizi) (JavaScript) | Microsoft Docs"
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
- slice
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- zero-based index
- Array object
- slice method
ms.assetid: 3c122219-14de-4126-b091-809659c026d6
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a61cd331abef9d1a0d979f547f6d6f12222c1eee
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="slice-method-array-javascript"></a>slice Yöntemi (Dizi) (JavaScript)
Dizinin bir bölümünü döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
arrayObj.slice(start, [end])   
```  
  
## <a name="parameters"></a>Parametreler  
 `arrayObj`  
 Gerekli. Bir `Array` nesnesi.  
  
 `start`  
 Gerekli. Belirtilen kısmını başlangıcını `arrayObj`.  
  
 `end`  
 İsteğe bağlı. Belirtilen kısmını sonuna `arrayObj`.  
  
## <a name="remarks"></a>Açıklamalar  
 `slice` Yöntemi döndürür bir `Array` belirtilen bölümünü içeren bir nesne `arrayObj`.  
  
 `slice` Yöntemi kopyalar kadar ancak dahil olmak üzere, belirtilen öğe `end`. Varsa `start` olan negatif, onu olarak işlem görür `length`  +  `start`, burada `length` dizi uzunluğu. Varsa `end` olan negatif, onu olarak işlem görür `length`  +  `end` burada `length` dizi uzunluğu. Varsa `end` girilmezse, ayıklama sonuna kadar devam `arrayObj`. Varsa `end` önce oluşur `start`, hiçbir öğe için yeni bir dizi kopyalanır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler nasıl kullanılacağını `slice` yöntemi. İlk örnekteki son öğesinden dışındaki tüm `myArray` kopyalanır `newArray`. İkinci örnekte, yalnızca son iki öğelerini `myArray` içine kopyalanır `newArray`.  
  
```JavaScript  
var origArray = [3, 5, 7, 9];  
var newArray = origArray. slice(0, -1);  
document.write(origArray);  
document.write("<br/>");  
newArray = origArray. slice(-2);  
document.write(newArray);  
  
// Output:  
// 3,5,7,9  
// 7,9  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [slice yöntemi (dize)](../../javascript/reference/slice-method-string-javascript.md)   
 [Dize nesnesi](../../javascript/reference/string-object-javascript.md)