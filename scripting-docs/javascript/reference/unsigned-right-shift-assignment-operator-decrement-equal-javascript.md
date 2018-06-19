---
title: İşaretsiz sağ kaydırma atama işleci (&gt;&gt;&gt;=) (JavaScript) | Microsoft Docs
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
- '>>>='
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '>>>= operator'
- unsigned right shift assignment operator (>>>=)
- assignment operators, JavaScript
ms.assetid: f67c3737-7d39-41ae-9c11-8b16d38f6179
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1272cbb58645df605743c6790642cd0e295442aa
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791939"
---
# <a name="unsigned-right-shift-assignment-operator-gtgtgt-javascript"></a>İşaretsiz sağ kaydırma atama işleci (&gt;&gt;&gt;=) (JavaScript)
Sağa bit sayısı kadar oturum, korumadan bir ifade değerinde belirtilen bir değişkenin değeri olarak geçer ve sonucu değişkenine atar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result >>>= expression  
```  
  
## <a name="parameters"></a>Parametreler  
 *Sonuç*  
 Herhangi bir değişken.  
  
 *ifade*  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanarak >>> = işleci tam olarak aynı olup aşağıdakileri yapabilirsiniz:  
  
```JavaScript  
result = result >>> expression  
```  
  
 **>>>=**  İşleci kaydırır bitleri *sonuç* sağ tarafından belirtilen bit sayısı *ifade*. Sıfır soldan doldurulur. Sağ gölgeye basamak atılır. Örneğin:  
  
```JavaScript  
var temp  
temp = -14  
temp >>>= 2  
```  
  
 Değişkeni *temp* -14 (11111111 11111111 11110010 iki kişinin tamamlama ikili dosyada 11111111) başlangıç değeri vardır. Doğru iki bit gölgeye zaman 1073741820 (11111111 11111111 11111100 ikili dosyada 00111111) değerine eşit.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşaretsiz sağ kaydırma işleci (>>>)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [Bit düzeyinde sola kaydırma işleci (<\<)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [Bitwise sağ kaydırma işleci (>>)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)