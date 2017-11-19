---
title: "Sayı Sabitleri (JavaScript) | Microsoft Docs"
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
helpviewer_keywords:
- POSITIVE_INFINITY constant [JavaScript]
- MAX_VALUE constant [JavaScript]
- MIN_VALUE constant [JavaScript]
- number constants [JavaScript]
- Number.NEGATIVE_INFINITY constant [JavaScript]
- Number.POSITIVE_INFINITY constant [JavaScript]
- NEGATIVE_INFINITY constant [JavaScript]
- NaN constant [JavaScript]
- Number.MIN_VALUE constant [JavaScript]
- constants [JavaScript], number
- Number.NaN constant [JavaScript]
- Number.MAX_VALUE constant [JavaScript]
ms.assetid: e0701b41-99ae-4916-9ec0-f79bb15386fb
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f846ef7cbd9609f7913d6305e48cb4942476ca21
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="number-constants-javascript"></a>Sayı Sabitleri (JavaScript)
Aşağıdaki sayı sabitleri özellikleridir `Number` nesnesi.  
  
## <a name="number-object-constants"></a>Sayı nesnesi sabitleri  
 Oluşturmak zorunda değil `Number` bu sabitleri erişmek için nesne.  
  
|Sabit|Döndürülen değer|  
|--------------|--------------------|  
|`Number.EPSILON`|' De temsil edilebilir en küçük sayı [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]. Yaklaşık 2.2204460492503130808472633361816E eşit-16.|  
|`Number.MAX_SAFE_INTEGER`|JavaScript'te güvenle temsil edilebilir en büyük sayı. 9007199254740991 için eşit.|  
|`Number.MAX_VALUE`|' De temsil en büyük sayı [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]. Yaklaşık 1, 79E + 308 için eşit.|  
|`Number.MIN_SAFE_INTEGER`|JavaScript'te güvenle temsil edilebilir en küçük sayı. -9007199254740991 için eşit.|  
|`Number.MIN_VALUE`|İçinde sıfıra yakın numarasını temsil [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]. Yaklaşık 5.00E eşit-324.|  
|`Number.NaN`|Bir sayı değil bir değer.<br /><br /> Eşitlik karşılaştırmaları içinde `NaN` kendisi de dahil olmak üzere herhangi bir değer eşit değil. Bir değerin eşit olup olmadığını test etmek için `NaN`, kullanın [isNaN işlevi](../../javascript/reference/isnan-function-javascript.md).|  
|`Number.NEGATIVE_INFINITY`|' De temsil negatif bir sayı'dan küçük bir değer [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)].<br /><br /> [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]görüntüler `NEGATIVE_INFINITY` olarak değerleri `-infinity`.|  
|`Number.POSITIVE_INFINITY`|' De temsil en büyük sayıdan büyük bir değer [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)].<br /><br /> [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]görüntüler `POSITIVE_INFINITY` olarak değerleri `infinity`.|  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
 İçin `Number.EPSILON`, `Number.MAX_SAFE_INTEGER`, ve `Number.MIN_SAFE_INTEGER`:  
  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **Uygulandığı öğe**: [sayı nesnesi](../../javascript/reference/number-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Matematik sabitleri](../../javascript/reference/math-constants-javascript.md)   
 [JavaScript sabitleri](../../javascript/reference/javascript-constants.md)   
 [Sonsuzluk sabiti](../../javascript/reference/infinity-constant-javascript.md)   
 [NaN sabiti](../../javascript/reference/nan-constant-javascript.md)   
 [isNaN işlevi](../../javascript/reference/isnan-function-javascript.md)