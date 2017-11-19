---
title: "concat yöntemi (dizi) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: concat
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- concat method (array)
- Concat method
ms.assetid: bc2b4a6a-209e-4d59-8c24-59db01d53b1e
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 19f3a216a36f9ad8c422036476e46b89b6ee488c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="concat-method-array-javascript"></a>concat Yöntemi (Dizi) (JavaScript)
İki veya daha fazla diziler birleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
array1.concat([item1[, item2[, . . . [, itemN]]]])   
```  
  
## <a name="parameters"></a>Parametreler  
 `array1`  
 Gerekli. `Array` Nesnesi diğer diziler birleştirilmiş.  
  
 `item1,. . ., itemN`  
 İsteğe bağlı. Sonuna eklenecek ek öğelerini `array1`.  
  
## <a name="remarks"></a>Açıklamalar  
 `concat` Yöntemi döndürür bir `Array` birleşimini içeren bir nesne `array1` ve diğer sağlanan öğeleri.  
  
 Eklenecek öğeleri (*Item1 itemN*) diziye listedeki ilk öğe başlayarak sırayla eklenir. Öğelerden birini bir dizi ise içeriğinin sonuna eklenen `array1`. Öğe bir dizi dışında her şey ise, tek bir dizi öğesi olarak dizinin sonuna eklenir.  
  
 Kaynak diziler öğelerden ortaya çıkan diziye gibi kopyalanır:  
  
-   Yeni bir dizi birleştirilmiş dizi herhangi bir nesne kopyaladıysanız, nesne başvurusu de aynı nesneye işaret edecek şekilde devam eder. Yeni bir dizi veya özgün dizinin bir değişiklik, diğer bir değişiklik neden olur.  
  
-   Bir sayı veya dize değeri için yeni bir dizi eklediyseniz, yalnızca değer kopyalanır. Bir dizi değeri, değerin diğer etkilemez.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `concat` sahip bir dizi kullanıldığında yöntemi:  
  
```JavaScript  
var a, b, c, d;  
a = new Array(1,2,3);  
b = "dog";  
c = new Array(42, "cat");  
d = a.concat(b, c);  
document.write(d);  
  
//Output:   
1, 2, 3, "dog", 42, "cat"  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [concat yöntemi (dize)](../../javascript/reference/concat-method-string-javascript.md)   
 [join yöntemi (dizi)](../../javascript/reference/join-method-array-javascript.md)