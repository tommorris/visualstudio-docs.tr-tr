---
title: "Bit düzeyinde XOR atama işleci (^ =) (JavaScript) | Microsoft Docs"
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
- ^=
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- ^= operator, about ^= operator
- assignment operators, bitwise [JavaScript]
- bitwise operators, XOR operator
- XOR operator
- ^= operator
ms.assetid: a6ded216-27b6-4fc4-a51b-7d10cc6f820c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 511ff5b3346bb2b04bf4c24cb3e0b715b2ccf4c5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-xor-assignment-operator--javascript"></a>Bit Düzeyinde XOR Atama İşleci (^=) (JavaScript)
Bit düzeyinde XOR bir değişken ve bir ifade gerçekleştirir ve sonucu değişkenine atar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result ^= expression  
```  
  
## <a name="parameters"></a>Parametreler  
 *Sonuç*  
 Herhangi bir değişken.  
  
 *ifade*  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanarak  **^=**  işleci tam olarak aynı olup belirtme:  
  
```JavaScript  
result = result ^ expression  
```  
  
 **^=**  İşleci iki ifadelerin değerlerini ikili gösterimidir arar ve onlar üzerinde bit tabanlı Dışlayıcı veya işlemi yapar. Bu işlem sonucu şu şekilde davranır:  
  
```JavaScript  
0101    (result)  
1100    (expression)  
----  
1001    (result)  
```  
  
 Bir ve yalnızca bir tane ifadelerinin varsa 1 bir rakam, sonuç 1 Bu basamakta sahiptir. Aksi takdirde, sonuç bu basamakta 0 sahiptir.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bit düzeyinde XOR işleci (^)](../../javascript/reference/bitwise-xor-operator-decrement-hat-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)