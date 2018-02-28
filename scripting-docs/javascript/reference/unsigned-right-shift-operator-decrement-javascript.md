---
title: "İşaretsiz sağ kaydırma işleci (&gt;&gt;&gt;) (JavaScript) | Microsoft Docs"
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
- '>>>'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- unsigned right shift operator (>>>)
- '>>> operator'
ms.assetid: df48bdfc-8741-46ab-b681-449da57ac95c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: efb873bedc0a64089c7ec892d6378b4869c0ca21
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="unsigned-right-shift-operator-gtgtgt-javascript"></a>İşaretsiz sağ kaydırma işleci (&gt;&gt;&gt;) (JavaScript)
Sağ ifade, BITS oturum korumadan kaydırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result = expression1 >>> expression2  
```  
  
## <a name="parameters"></a>Parametreler  
 *Sonuç*  
 Herhangi bir değişken.  
  
 *İfade1*  
 Herhangi bir ifade.  
  
 *İfade2*  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 **>>>**  İşleci kaydırır bitleri *İfade1* sağ tarafından belirtilen bit sayısı *İfade2*. Sıfır soldan doldurulur. Sağ gölgeye basamak atılır. Örneğin:  
  
```JavaScript  
var temp  
temp = -14 >>> 2  
```  
  
 Değişkeni *temp* başlangıç değeri-14 (11111111 11111111 11111111 11110010 iki kişinin tamamlama ikili olarak) sahiptir. Ötelenen doğru iki bit olduğunda 1073741820 (11111111 11111111 11111100 ikili dosyada 00111111) değerine eşit.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşaretsiz sağ kaydırma atama işleci (>>> =)](../../javascript/reference/unsigned-right-shift-assignment-operator-decrement-equal-javascript.md)   
 [Bit düzeyinde sola kaydırma işleci (<\<)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [Bitwise sağ kaydırma işleci (>>)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)