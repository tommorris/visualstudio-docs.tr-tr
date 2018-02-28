---
title: "Remainder işleci (JavaScript) | Microsoft Docs"
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
- '%'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- remainder operator, JavaScript
- '% operator [JavaScript]'
- Remainder function [JavaScript]
ms.assetid: 087d654f-623b-498d-95ff-596d26bf674d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ce74b8512b25cfe215d294873102b274623b42a2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="remainder-operator-javascript"></a>Kalan işleci (JavaScript)
Bir ifadenin değerini başka bir değerle böler ve kalanı döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result = number1 % number2  
```  
  
## <a name="arguments"></a>Arguments  
 `result`  
 Herhangi bir değişken.  
  
 `number1`  
 Herhangi bir sayısal ifade.  
  
 `number2`  
 Herhangi bir sayısal ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Kalan işleci böler `number1` tarafından `number2`ve yalnızca kalanı olarak döndürür `result`. İşaretini `result` işaretini aynı `number1`. Değeri `result` 0 ile mutlak değerini arasında `number2`.  
  
 Aşağıdaki kod kalan işleci kullanmayı gösterir.  
  
```  
var modResult = 19 % 6.7;  
document.write(modResult);  
  
// Output: 5.6  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)
