---
title: "Array.of işlevi (dizi) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 2884dda3-65d1-4990-9afe-87865c2d4f7f
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 042315bbc3b956e92fff866f7d403b6f87726a74
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="arrayof-function-array-javascript"></a>Array.of İşlevi (Dizi) (JavaScript)
Geçirilen bağımsız değişkenlerden bir dizi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Array.of(element0[, element1][, ...][,elementN]);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `element0,...,elementN`  
 İsteğe bağlı. Diziye yerleştirilecek öğeler. N + 1 öğeleri ve n + 1 uzunluğu ile bir dizi oluşturur.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevi çağırmak için benzer `new Array(args)`, ancak `Array.of` bir bağımsız değişken olarak geçirildiğinde özel davranış içermez.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir dizi geçirilen sayı oluşturur.  
  
```JavaScript  
var arr = Array.of(1, 2, 3);  
// arr[0] == 1   
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, kullanma arasındaki fark gösterir `Array.of` ve `new Array`.  
  
```JavaScript  
var arr1 = Array.of(3);  
// arr1[0] == 3  
  
// With new Array, a single argument specifies  
// the length of the new array.  
var arr2 = new Array(3);  
// arr2[0] is undefined  
// arr2.length == 3  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]