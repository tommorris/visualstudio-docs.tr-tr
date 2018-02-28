---
title: "Math.log işlevi (JavaScript) | Microsoft Docs"
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
- log
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- log method
- Math object
ms.assetid: 5d617fb5-4b27-404e-842f-eea5549a7c1a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 62bfb6bf9bb95b541a51224af4484ded22ccb4e8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="mathlog-function-javascript"></a>Math.log İşlevi (JavaScript)
Doğal logaritmasını döndürür (temel `e`) bir sayı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Math.log(number)   
```  
  
#### <a name="parameters"></a>Parametreler  
 sayı  
 Bir sayı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Varsa `number` pozitif, bu işlev, sayının doğal logaritmasını döndürür. Varsa `number` bu işlevi döndürür, negatifse `NaN`. Varsa `number` bu işlevi döndürür 0 ' dır `-Infinity`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod bu işlevinin nasıl kullanılacağını gösterir.  
  
```JavaScript  
var numArr = [ 45.3, 69.0, 557.04, 0.222 ];  
  
for (i in numArr) {  
    document.write(Math.log(numArr[i]));  
    document.write("<br/>");  
}  
  
// Output:   
// 3.8133070324889884  
// 4.23410650459726  
// 6.322637050634291  
// -1.5050778971098575  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [matematik nesnesi](../../javascript/reference/math-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Math.Sqrt işlevi](../../javascript/reference/math-sqrt-function-javascript.md)