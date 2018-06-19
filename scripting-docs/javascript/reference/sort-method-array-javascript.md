---
title: sort yöntemi (dizi) (JavaScript) | Microsoft Docs
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
- sort
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Sort method
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0462e60e623b99af458beb61eb7ef4215fe8ef41
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/05/2018
ms.locfileid: "28987821"
---
# <a name="sort-method-array-javascript"></a>sort Yöntemi (Dizi) (JavaScript)
Sıralar bir `Array`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
arrayobj.sort(sortFunction)   
```  
  
## <a name="parameters"></a>Parametreler  
 `arrayObj`  
 Gerekli. Tüm `Array` nesnesi.  
  
 `sortFunction`  
 İsteğe bağlı. Öğelerin sırasını belirlemek için kullanılan işlevin adı. Atlanırsa, öğeleri artan sırada, ASCII karakter sırasını sıralanır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sıralanmış dizi.  
  
## <a name="remarks"></a>Açıklamalar  
 `sort` Yöntemi sıralar `Array` nesneyi yerinde; Hayır yeni `Array` nesnesi, yürütme sırasında oluşturulur.  
  
 `sortFunction`iki bağımsız değişkeni alır ve aşağıdaki değerlerden birini döndürmesi gerekir:  
  
-   İlk bağımsız değişken aktarılırsa küçük negatif bir değer (0'dan az) ikinci bağımsız değişkenden.  İlk bağımsız değişken için bir alt dizin sıralanır.
  
-   Sıfır (0) if iki bağımsız değişken eşdeğerdir.  İki bağımsız değişken dizisindeki diğer öğeleri göre sıralanır ancak birbirine göre sıralanmış değil.
  
-   Pozitif bir değer (ilk bağımsız değişken ikinci bağımsız değişkeni'den büyükse, 0'dan büyük).  İkinci bağımsız değişkeni için bir alt dizin sıralanır.
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `sort` yöntemi.  
  
```JavaScript  
var a = new Array(4, 11, 2, 10, 3, 1);  
  
var b = a.sort();  
document.write(b);  
document.write("<br/>");  
  
// This is ASCII character order.  
// Output: 1,10,11,2,3,4)  
  
// Sort the array elements with a function that compares array elements.  
b = a.sort(CompareForSort);  
document.write(b);  
document.write("<br/>");  
// Output: 1,2,3,4,10,11.  
  
// Sorts array elements in ascending order numerically.  
function CompareForSort(first, second)  
{  
    if (first == second)  
        return 0;  
    if (first < second)  
        return -1;  
    else  
        return 1;   
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]