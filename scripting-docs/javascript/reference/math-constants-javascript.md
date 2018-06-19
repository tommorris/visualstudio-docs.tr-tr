---
title: Matematik Sabitleri (JavaScript) | Microsoft Docs
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
helpviewer_keywords:
- LN2 constant [JavaScript]
- E constant [JavaScript]
- LOG10E constant [JavaScript]
- SQRT1_2 constant [JavaScript]
- LOG2E constant [JavaScript]
- Math.SQRT2 constant [JavaScript]
- PI constant [JavaScript]
- Math.LOG2E constant [JavaScript]
- constants [JavaScript], math
- Math.E constant [JavaScript]
- logarithm consants [JavaScript]
- Math.LOG10E constant [JavaScript]
- Math.SQRT1_2 constant [JavaScript]
- SQRT2 constant [JavaScript]
- square root constants [JavaScript]
- Math.PI constant [JavaScript]
- math constants [JavaScript]
- LN10 constant [JavaScript]
- Math.LN2 constant [JavaScript]
- Math.LN10 constant [JavaScript]
ms.assetid: 8a674046-cb99-4103-92be-83697fba6344
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9942abb69af416cd4cd7f092dc9f1478e0bc3a69
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791195"
---
# <a name="math-constants-javascript"></a>Matematik Sabitleri (JavaScript)
Matematik sabitleri dönüş özellikleridir sabit değerleri `Math` nesnesi.  
  
## <a name="math-object-constants"></a>Matematik Nesnesi Sabitleri  
 Özellikleridir sabit değerleri aşağıdaki tabloda listelenmektedir [matematik nesnesi](../../javascript/reference/math-object-javascript.md).  
  
|Sabit|Açıklama|Yaklaşık değeri|  
|--------------|-----------------|-----------------------|  
|`Math.E`|E matematiksel sabiti. Bu Euler'ın Doğal logaritmanın tabanı numarasıdır.|2.718|  
|`Math.LN2`|Doğal logaritmasını 2.|0.693|  
|`Math.LN10`|10 doğal logaritmasını.|2.302|  
|`Math.LOG2E`|2 tabanındaki logaritmasını e.|1.443|  
|`Math.LOG10E`|10 tabanında logaritmasını e.|0.434|  
|`Math.PI`|Pi. Bu kendi çapının için dairenin çevresi orandır.|3.14159|  
|`Math.SQRT1_2`|Kare kökünü 0,5 veya, eşdeğer, bir 2 karekökünü tarafından ayrılmış.|0.707|  
|`Math.SQRT2`|2'in kare kökü.|1.414|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını anlatan `Math.PI` sabit.  
  
```JavaScript  
var radius = 3;  
var area = Math.PI * radius * radius;  
document.write(area);  
  
// Output: 28.274333882308138  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [matematik nesnesi](../../javascript/reference/math-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayı sabitleri](../../javascript/reference/number-constants-javascript.md)   
 [JavaScript sabitleri](../../javascript/reference/javascript-constants.md)