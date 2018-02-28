---
title: "Bit düzeyinde OR işleci (|) (JavaScript) | Microsoft Docs"
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
- '|'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- bitwise operators, OR operator
- OR operator
- '| operator'
ms.assetid: ffc8f758-3151-478e-bafb-fc78f1c469a0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a91c616c84b9d38154bf936f61fb856a4ebad0f7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-or-operator--javascript"></a>Bit Düzeyinde OR İşleci (|) (JavaScript)
Bit düzeyinde OR iki ifadeleri gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result = expression1 | expression2  
```  
  
## <a name="parameters"></a>Parametreler  
 *Sonuç*  
 Herhangi bir değişken.  
  
 *İfade1*  
 Herhangi bir ifade.  
  
 *İfade2*  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 **&#124;** işleci iki ifadelerin değerlerini ikili gösterimidir arar ve bunları üzerinde bit düzeyinde OR işlemi yapar. Bu işlem sonucu şu şekilde davranır:  
  
```JavaScript  
0101   (expression1)  
1100   (expression2)  
----  
1101   (result)  
```  
  
 Herhangi bir saat ya da ifadelerin 1 bir basamak sahip, sonuç bu sayı 1 gerekir. Aksi takdirde, sonuç bu basamakta 0 olacaktır.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bit düzeyinde OR atama işleci (&#124; =)](../../javascript/reference/bitwise-or-assignment-operator-decrement-equal-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)