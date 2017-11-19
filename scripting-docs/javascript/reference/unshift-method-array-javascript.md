---
title: "unshift yöntemi (dizi) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: unshift
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: unshift method
ms.assetid: 8c6a39ed-bab3-4ca4-9350-571a9427ec94
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c3f0d210514d04afa5cf467819a5e843925e1a68
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="unshift-method-array-javascript"></a>unshift Yöntemi (Dizi) (JavaScript)
Bir dizinin başlangıcına yeni öğeler ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
arrayObj.unshift([item1[, item2 [, . . . [, itemN]]]])  
```  
  
## <a name="parameters"></a>Parametreler  
 `arrayObj`  
 Gerekli. Bir `Array` nesnesi.  
  
 `item1, item2,. . ., itemN`  
 İsteğe bağlı. Başlangıcında eklemek için öğeleri `Array`.  
  
## <a name="remarks"></a>Açıklamalar  
 `unshift` Yöntemi bağımsız değişken listesinde göründükleri sırada göründükleri şekilde bu öğelerini bir diziye başlangıç ekler.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `unshift` yöntemi.  
  
```JavaScript  
var ar = new Array();  
ar.unshift(10, 11);  
ar.unshift(12, 13, 14);  
document.write(ar.toString());  
  
// Output: 12,13,14,10,11  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [shift yöntemi (dizi)](../../javascript/reference/shift-method-array-javascript.md)