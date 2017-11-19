---
title: "Koşullu (üçlü) işleç (?:) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '?:'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- conditional operators
- conditional (Ternary) operator
- ternary
ms.assetid: 7399ac32-9324-4a9a-ae76-be9c0f9df81c
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1dc34b5c633cfc02219cb01061e1aaa017e0f7f2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="conditional-ternary-operator--javascript"></a>Koşullu (Üçlü) İşleci (?:) (JavaScript)
Bir koşula bağlı olarak iki ifadeden birini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
test ? expression1 : expression2  
```  
  
## <a name="parameters"></a>Parametreler  
 `test`  
 Herhangi bir Boolean ifadesi.  
  
 `expression1`  
 Bir ifade döndürülen if `test` olan `true`. Bir virgül ifadesi olabilir.  
  
 `expression2`  
 Bir ifade döndürülen if `test` olan `false`. Birden fazla ifade bir virgül ifadesiyle bağlantılı olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 `?:` İşleci için bir kısayol olarak kullanılabilir bir `if...else` deyimi. Genellikle daha büyük bir ifadenin bir parçası olarak kullanılır burada bir `if...else` deyimi garip olacaktır. Örneğin:  
  
```JavaScript  
var now = new Date();  
var greeting = "Good" + ((now.getHours() > 17) ? " evening." : " day.");  
```  
  
 Örnek, "İyi akşamlar." içeren bir dize oluşturur. 6 pm sonra ise. Eşdeğer kod kullanarak bir `if...else` deyimi uygulamamız görünecektir gibi:  
  
```JavaScript  
var now = new Date();  
var greeting = "Good";  
if (now.getHours() > 17)  
   greeting += " evening.";  
else  
   greeting += " day.";  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [if... else deyimi](../../javascript/reference/if-dot-dot-dot-else-statement-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)   
 [Kod delisi olun yapılandırma pencere öğesi örnek uygulaması](http://code.msdn.microsoft.com/Script-Junkie-Configuration-543ece24)