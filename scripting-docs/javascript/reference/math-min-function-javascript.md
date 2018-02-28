---
title: "Math.min işlevi (JavaScript) | Microsoft Docs"
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
- min
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- min method
ms.assetid: a1d7dd85-27ef-45cd-aa2a-f8e80f0b2898
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bb496cff65db11cf6c99d6a6e687f39e20ea857c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="mathmin-function-javascript"></a>Math.min İşlevi (JavaScript)
Sayısal ifadeler kümesi daha küçük veya döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Math.min([number1[, number2[... [,numberN]]]])  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İsteğe bağlı `number1, number2, ..., numberN` bağımsız değişkenler olarak değerlendirilecek sayısal ifadeler.  
  
 Bağımsız değişkenler verdiyse, dönüş değeri eşittir [Number.posıtıve_ınfınıty](../../javascript/reference/number-constants-javascript.md). Herhangi bir bağımsız değişken ise `NaN`, dönüş değeri de mi `NaN`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod iki ifadeye daha küçük alma gösterir.  
  
```JavaScript  
var x = Math.min(107 - 3, 48 * 90);  
document.write(x);  
  
// Output:  
// 104  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Math.max işlevi](../../javascript/reference/math-max-function-javascript.md)