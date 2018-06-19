---
title: Array.From işlevi (dizi) (JavaScript) | Microsoft Docs
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
ms.assetid: 1bf59a99-f860-4c4d-b4c6-d5f1f946a490
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a240cb439942bfeb6b4c9a1febb4d24cef1c5c18
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789044"
---
# <a name="arrayfrom-function-array-javascript"></a>Array.from İşlevi (Dizi) (JavaScript)
Bir dizi bir dizi benzeri veya iterable nesnesinden döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Array.from (arrayLike [ , mapfn [ , thisArg ] ] );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `arrayLike`  
 Gerekli. Bir dizi benzeri veya iterable nesne.  
  
 `mapfn`  
 İsteğe bağlı. Her bir öğe çağırmak için bir eşleme işlev `arrayLike`.  
  
 `thisArg`  
 İsteğe bağlı. Belirtir `this` eşleme işlevde nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 `arrayLike` Parametresi dizinli öğeleri olan bir ya da bir nesne olmalıdır ve bir `length` özelliği veya iterable bir nesne gibi bir `Set` nesnesi.  
  
 İsteğe bağlı eşleme işlevi dizideki her öğe adı verilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek DOM öğe düğümlerinin koleksiyondan bir dizi döndürür.  
  
```JavaScript  
var elemArr = Array.from(document.querySelectorAll('*'));  
var elem = elemArr[0]; // elem contains a reference to the first DOM element  
  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir karakter dizisi döndürür.  
  
```JavaScript  
var charArr = Array.from("abc");  
// charArr[0] == "a";  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, koleksiyonda yer alan nesneleri dizisini döndürür.  
  
```JavaScript  
var setObj = new Set("a", "b", "c");  
var objArr = Array.from(setObj);  
// objArr[1] == "b";   
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, ok sözdizimi kullanımı ve öğeleri değerini değiştirmek için bir eşleme işlev gösterir.  
  
```JavaScript  
var arr = Array.from([1, 2, 3], x => x * 10);  
// arr[0] == 10;  
// arr[1] == 20;  
// arr[2] == 30;  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]