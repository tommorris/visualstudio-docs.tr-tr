---
title: "Bit düzeyinde AND atama işleci (&amp;=) (JavaScript) | Microsoft Docs"
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
- '&='
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '&= operator'
- assignment operators, bitwise [JavaScript]
- AND operator
- bitwise operators, AND operator
ms.assetid: e7e2eabb-4fc1-4fdc-9dd8-1e6d715371fa
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dfd2a77e66296cafc6c8403570f0536e1333e081
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-and-assignment-operator-amp-javascript"></a>Bit düzeyinde AND atama işleci (&amp;=) (JavaScript)
Bir değişkenin değerini üzerinde bit tabanlı ve işleminin sonucu ve bir ifadenin değerini ayarlar. Değişkeni ve ifade 32 bit tamsayı olarak kabul edilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result &= expression  
```  
  
## <a name="parameters"></a>Parametreler  
 `result`  
 Herhangi bir değişken.  
  
 `expression`  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlecini kullanarak belirtme aynıdır:  
  
```JavaScript  
result = result & expression  
```  
  
 [Bit düzeyinde ve işleci (&)](../../javascript/reference/bitwise-and-operator-decrement-javascript.md) değerlerini ikili gösterimidir arar `result` ve `expression` ve onlar üzerinde bit tabanlı AND işlemi yapar. Bu işlemin çıktısı şu şekilde davranır:  
  
```JavaScript  
// 9 is 00000000000000000000000000001001  
var expr1 = 9;  
  
// 5 is 00000000000000000000000000000101  
var expr2 = 5;  
  
// 1 is 00000000000000000000000000000001  
expr1 &= expr2;  
  
document.write(expr1);  
```  
  
 İfadeler her ikisinin bir rakam, 1 olduğunda her zaman sonucu bu sayı 1 sahip. Aksi takdirde, sonuç bu basamakta 0 sahiptir.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bit düzeyinde AND işleci (&)](../../javascript/reference/bitwise-and-operator-decrement-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)