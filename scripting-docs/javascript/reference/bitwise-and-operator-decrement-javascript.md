---
title: Bit düzeyinde AND işleci (&amp;) (JavaScript) | Microsoft Docs
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
- '&'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- assignment operators, bitwise [JavaScript]
- '& operator, about & operator'
- AND operator
- '& operator'
- bitwise operators, AND operator
- '& operator, bitwise operators'
ms.assetid: a8c17a55-2599-4518-98d7-671699f4d5f3
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fa8b3eec0cbd7c172d08b16120fb54f3be3c6a48
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789179"
---
# <a name="bitwise-and-operator-amp-javascript"></a>Bit düzeyinde AND işleci (&amp;) (JavaScript)
İki 32-bit ifadeye bit tabanlı AND işlemi gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result = expression1 & expression2  
```  
  
## <a name="parameters"></a>Parametreler  
 `result`  
 İşlem sonucu.  
  
 `expression1`  
 Herhangi bir ifade.  
  
 `expression2`  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 `&` Her iki 32-bit ifadeye bit bit tabanlı AND işlemi yapar. BITS her ikisi de 1 olduğunda sonuç 1'dir. Aksi takdirde, sonuç 0'dır.  
  
|Bit1|Bit2|AND işleciyle değeri|  
|----------|----------|-----------------|  
|0|0|0|  
|1.|1.|1.|  
|1.|0|0|  
|0|1.|0|  
  
 Aşağıdaki örnekler nasıl kullanılacağını `&` işleci.  
  
```JavaScript  
// 9 is 00000000000000000000000000001001  
var expr1 = 9;  
  
// 5 is 00000000000000000000000000000101  
var expr2 = 5;  
  
// 1 is 00000000000000000000000000000001  
var result = expr1 & expr2;  
  
document.write(result);  
// Output: 1  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bit düzeyinde AND atama işleci (& =)](../../javascript/reference/bitwise-and-assignment-operator-decrement-equal-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)