---
title: "Bit düzeyinde XOR işleci (^) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: ^
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- bitwise operators, XOR operator
- XOR operator
ms.assetid: 44ef0d18-abb5-4d83-9e77-6394635b3f48
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2ebe8ff9805793bf306688622b0b29007b1562e2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-xor-operator--javascript"></a>Bit Düzeyinde XOR İşleci (^) (JavaScript)
Bit düzeyinde XOR iki ifadeleri gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result = expression1 ^ expression2  
```  
  
## <a name="parameters"></a>Parametreler  
 *Sonuç*  
 Herhangi bir değişken.  
  
 *İfade1*  
 Herhangi bir ifade.  
  
 *İfade2*  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 **^**  İşleci iki ifadelerin değerlerini ikili gösterimidir arar ve onlar üzerinde bit tabanlı Dışlayıcı veya işlemi yapar. Bu işlem sonucu şu şekilde davranır:  
  
```JavaScript  
0101   (expression1)  
1100   (expression2)  
----  
1001   (result)  
```  
  
 Bir ve yalnızca bir tane ifadelerinin varsa 1 bir rakam, sonuç 1 Bu basamakta sahiptir. Aksi takdirde, sonuç bu basamakta 0 sahiptir.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bit düzeyinde XOR atama işleci (^ =)](../../javascript/reference/bitwise-xor-assignment-operator-decrement-hat-equal-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)