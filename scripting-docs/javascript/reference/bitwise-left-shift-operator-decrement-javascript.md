---
title: "Bit düzeyinde sola kaydırma işleci (&lt;&lt;) (JavaScript) | Microsoft Docs"
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
- <<
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- << operator
- left shift operators
- << operator, about << operator
- bitwise operators, Left Shift operator
ms.assetid: 18148596-7b86-4add-aeef-106991c69435
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9d63fc50659695f518e581edbed67c009b36577f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-left-shift-operator-ltlt-javascript"></a>Bit düzeyinde sola kaydırma işleci (&lt;&lt;) (JavaScript)
Sol ifade bit kaydırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result = expression1 << expression2  
```  
  
## <a name="parameters"></a>Parametreler  
 *Sonuç*  
 Herhangi bir değişken.  
  
 *İfade1*  
 Herhangi bir ifade.  
  
 *İfade2*  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 **<<**  İşleci kaydırır bitleri *İfade1* belirtilen bit sayısı tarafından sol *İfade2*. Örneğin:  
  
```JavaScript  
var temp  
temp = 14 << 2  
```  
  
 Değişkeni *temp* 14 (00001110 ikili dosyada) sol iki BITS eşittir 56 (00111000 ikili dosyada) gölgeye çünkü 56 değerine sahip.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sola kaydırma atama işleci (<\<=)](../../javascript/reference/left-shift-assignment-operator-decrement-equal-javascript.md)   
 [Bitwise sağ kaydırma işleci (>>)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [İşaretsiz sağ kaydırma işleci (>>>)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)