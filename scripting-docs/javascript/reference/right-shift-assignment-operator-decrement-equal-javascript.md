---
title: "Sağa kaydırma atama işleci (&gt;&gt;=) (JavaScript) | Microsoft Docs"
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
- '>>='
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '>>= operator [JavaScript]'
- right shift operators [JavaScript]
- assignment operators, JavaScript
ms.assetid: 8c1f7f90-e3ac-42ee-94f2-5ccc47d7aef6
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cb93d146ad00bd19c09fb4cfca3af776a11f245d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="right-shift-assignment-operator-gtgt-javascript"></a>Sağa kaydırma atama işleci (&gt;&gt;=) (JavaScript)
Sağ oturum Bakımı bir değişkenin değerini bir deyim değerinde belirtilen bit sayısı tarafından kaydırır ve sonucu değişkenine atar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
result >>= expression  
```  
  
## <a name="parameters"></a>Parametreler  
 *Sonuç*  
 Herhangi bir değişken.  
  
 *ifade*  
 Herhangi bir ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanarak  **>>=**  işleci tam olarak aynı olup belirtme:  
  
```JavaScript  
result = result >> expression  
```  
  
 **>>=**  İşleci kaydırır bitleri *sonuç* sağ tarafından belirtilen bit sayısı *ifade*. Oturum açma bit *sonuç* sol rakamları doldurmak için kullanılır. Sağ gölgeye basamak atılır. Örneğin, aşağıdaki kodu değerlendirildikten sonra *temp* -4 değerine sahip: 14 (11110010 ikili dosyada) gölgeye doğru iki bit eşittir -4 (11111100 ikili olarak).  
  
```JavaScript  
var temp  
temp = -14  
temp >>= 2  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bit düzeyinde sola kaydırma işleci (<\<)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [Bitwise sağ kaydırma işleci (>>)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [İşaretsiz sağ kaydırma işleci (>>>)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)