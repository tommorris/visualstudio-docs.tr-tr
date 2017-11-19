---
title: "isNaN işlevi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: isNaN
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: isNaN method
ms.assetid: 5af4eb29-72f6-484f-93bd-04ae1261f849
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7b7e6d3687e795ea5d5e38308a8af0d73ba7f5ff
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="isnan-function-javascript"></a>isNaN İşlevi (JavaScript)
Bir değer ayrılan değeri olup olmadığını belirten bir Boole değeri döndürür `NaN` (sayı değil).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
isNaN(numValue)   
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`değer dönüştürülüp varsa `Number` türü `NaN`, aksi takdirde `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `numValue` karşı test edilecek değer `NaN`.  
  
 Dönüş değerleri test etmek için bu yöntemi kullanın `parseInt` ve `parseFloat` yöntemleri.  
  
 Alternatif olarak, içeren bir değişkeni `NaN` veya başka bir değer kendisi için karşılaştırılması gereken. Eşit olmayan karşılaştırır, olmasına `NaN`. Bunun nedeni, `NaN` kendisine eşit değil tek değerdir.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [genel nesne](../../javascript/reference/global-object-javascript.md)  
  
## <a name="example"></a>Örnek  
  
```JavaScript  
// Returns false.  
isNaN(100);  
  
// Returns false.  
isNaN("100");  
  
// Returns true.  
isNaN("ABC");  
  
// Returns true.  
isNaN("10C");  
  
// Returns true.  
isNaN("abc123");  
  
// Returns true.  
isNaN(Math.sqrt(-1));           
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [isFinite işlevi](../../javascript/reference/isfinite-function-javascript.md)   
 [NaN sabiti](../../javascript/reference/nan-constant-javascript.md)   
 [parseFloat işlevi](../../javascript/reference/parsefloat-function-javascript.md)   
 [parseInt işlevi](../../javascript/reference/parseint-function-javascript.md)