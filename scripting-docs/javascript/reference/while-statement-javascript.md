---
title: while deyimi (JavaScript) | Microsoft Docs
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
- while_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- loop structures, while statements
- while statement
ms.assetid: d63777cf-0e1a-4555-8d3a-334381001f48
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: de64bf9181a0fc86a528fa7af21216b99530f217
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="while-statement-javascript"></a>while Deyimi (JavaScript)
Belirtilen bir koşul olana kadar bir deyim veya dizi deyimi yürütür `false`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
while (expression) {  
    statements  
}   
```  
  
## <a name="parameters"></a>Parametreler  
 `expression`  
 Gerekli. Her döngü tekrarında önce denetlenir Boole ifadesi. Varsa `expression` olan `true`, döngü yürütülür. Varsa `expression` olan `false`, döngü sonlandırılır.  
  
 `statements`  
 İsteğe bağlı. Varsa yürütülmesi için bir veya daha fazla deyimleri `expression` olan `true`.  
  
## <a name="remarks"></a>Açıklamalar  
 `while` Deyimi denetimleri `expression` bir döngü ilk yürütülmeden önce. Varsa `expression` olan `false` şu anda döngü hiçbir zaman yürütülür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `while` deyimi.  
  
```JavaScript  
var i = 0;  
var j = 10;  
while (i < 100) {  
    if (i == j)  
        break;  
    i++;  
}  
document.write(i);  
  
// Output: 10  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [break deyimi](../../javascript/reference/break-statement-javascript.md)   
 [continue deyimi](../../javascript/reference/continue-statement-javascript.md)   
 [do... while deyimi](../../javascript/reference/do-dot-dot-dot-while-statement-javascript.md)   
 [for deyimi](../../javascript/reference/for-statement-javascript.md)   
 [for... deyimi içinde](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)