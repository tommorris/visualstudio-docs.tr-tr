---
title: "Math.max işlevi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: max
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: max method
ms.assetid: f3ea1b8a-5fd0-482a-971b-b7f8e2b9b7eb
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: adf66164346f3802d92f8e0de82356df49bad5fa
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="mathmax-function-javascript"></a>Math.max İşlevi (JavaScript)
Büyük sağlanan sayısal ifadeler bir dizi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Math.max([number1[, number2[... [, numberN]]]])   
```  
  
## <a name="remarks"></a>Açıklamalar  
 İsteğe bağlı `number1, number2, ..., numberN` bağımsız değişkenler olarak değerlendirilecek sayısal ifadeler.  
  
 Bağımsız değişkenler verdiyse, dönüş değeri eşittir [Number.negatıve_ınfınıty](../../javascript/reference/number-constants-javascript.md). Herhangi bir bağımsız değişken ise `NaN`, dönüş değeri de mi `NaN`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod iki ifadeye daha büyük alma gösterir.  
  
```JavaScript  
var x = Math.max(107 - 3,  48 * 90);  
document.write(x);  
  
// Output:  
// 4320  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Math.min işlevi](../../javascript/reference/math-min-function-javascript.md)