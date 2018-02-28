---
title: "Bitwise sağ kaydırma işleci (&gt;&gt;) (JavaScript) | Microsoft Docs"
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
- '>>'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '>> operator'
- '>> operator, about >> operator'
- '>> operator, bitsets'
- bitwise operators, right shift operator
ms.assetid: 89dc57e0-0b0d-49a4-a8ed-56d8bb20f3e3
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 70db0c176b475886a26cfe4c06f7f2f0c9d4fc2a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-right-shift-operator-gtgt-javascript"></a>Bitwise sağ kaydırma işleci (&gt;&gt;) (JavaScript)
Sağ ifade, BITS oturum koruma kaydırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result = expression1 >> expression2  
```  
  
## <a name="parameters"></a>Parametreler  
 *Sonuç*  
 Herhangi bir değişken.  
  
 *İfade1*  
 Herhangi bir ifade.  
  
 *İfade2*  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 >> İşleci kaydırır bitleri *İfade1* sağ tarafından belirtilen bit sayısı *İfade2*. Oturum açma bit *İfade1* sol rakamları doldurmak için kullanılır. Sağ gölgeye basamak atılır. Örneğin, aşağıdaki kodu değerlendirildikten sonra *temp* -4 değerine sahip:-14 (11110010 içinde ikiye tamamlama ikili) gölgeye doğru iki bit eşittir -4 (11111100 içinde ikiye tamamlama ikili).  
  
```JavaScript  
var temp  
temp = -14 >> 2  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bit düzeyinde sola kaydırma işleci (<\<)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [Sağa kaydırma atama işleci (>> =)](../../javascript/reference/right-shift-assignment-operator-decrement-equal-javascript.md)   
 [İşaretsiz sağ kaydırma işleci (>>>)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)