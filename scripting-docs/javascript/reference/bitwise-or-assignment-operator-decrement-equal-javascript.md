---
title: "Bit düzeyinde OR atama işleci (| =) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '|='
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- assignment operators, bitwise [JavaScript]
- '|= operator'
- bitwise operators, OR operator
- OR operator
ms.assetid: 9b424ff6-4442-4621-b3b6-83e7fd1e5cd5
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8ce9cadcf07906c9eba6749706620ae6293c2682
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-or-assignment-operator--javascript"></a>Bitwise VEYA Atama İşleci (|=) (JavaScript)
Bir değişkenin değerini ve bir ifadenin değerini bit düzeyinde OR gerçekleştirir ve sonucu değişkenine atar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result |= expression  
```  
  
## <a name="parameters"></a>Parametreler  
 *Sonuç*  
 Herhangi bir değişken.  
  
 *ifade*  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlecini kullanarak tam olarak belirterek aynıdır:  
  
```JavaScript  
result = result | expression  
```  
  
 **&#124; =** işleci arar değerlerini ikili gösterimidir *sonuç* ve *ifade* ve bunları üzerinde bit düzeyinde OR işlemi yapar. Bu işlem sonucu şu şekilde davranır:  
  
```JavaScript  
0101    (result)  
1100    (expression)  
----  
1101    (output)  
```  
  
 Herhangi bir saat ya da ifadelerin 1 bir basamak vardır, bu sayı 1 sonucu sahip. Aksi takdirde, sonuç bu basamakta 0 sahiptir.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bit düzeyinde OR işleci (&#124;)](../../javascript/reference/bitwise-or-operator-decrement-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)