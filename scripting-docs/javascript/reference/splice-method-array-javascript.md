---
title: splice yöntemi (dizi) (JavaScript) | Microsoft Docs
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
- splice
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- splice method
ms.assetid: 85fdfb13-e3d9-4c89-b524-3ccee7001c93
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0d56a22244f76f5ce7221c276629907811733d51
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791378"
---
# <a name="splice-method-array-javascript"></a>splice Yöntemi (Dizi) (JavaScript)
Bir diziden öğeleri kaldırır, ve gerekirse, yerlerine yeni öğeler ekleyerek silinen öğeleri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
arrayObj.splice(start, deleteCount, [item1[, item2[, . . . [,itemN]]]])  
```  
  
## <a name="parameters"></a>Parametreler  
 `arrayObj`  
 Gerekli. Bir `Array` nesnesi.  
  
 `start`  
 Gerekli. Öğeleri kaldırma başlayacağı dizisindeki sıfır tabanlı konumu.  
  
 `deleteCount`  
 Gerekli. Kaldırılacak öğe sayısı.  
  
 `item1, item2,. . ., itemN`  
 İsteğe bağlı. Silinen öğeleri yerine dizi eklemek için öğeleri.  
  
## <a name="remarks"></a>Açıklamalar  
 `splice` Yöntemi değiştirir `arrayObj` konumundan belirtilen sayıda öğeyi kaldırarak `start` ve yeni öğeler ekleniyor. Silinen öğeleri yeni bir döndürülen `Array` nesnesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösterir `splice` yöntemi.  
  
```JavaScript  
var arr = new Array("4", "11", "2", "10", "3", "1");  
arr.splice(2, 2, "21", "31");  
document.write(arr);  
  
// Output: 4,11,21,31,3,1  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [slice yöntemi (dizi)](../../javascript/reference/slice-method-array-javascript.md)