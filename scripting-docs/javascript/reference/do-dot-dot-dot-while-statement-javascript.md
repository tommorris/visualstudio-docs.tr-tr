---
title: do... while deyimi (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: do_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- do...while statement
- terminating loops
- loop structures, do and do-while
ms.assetid: 8b7782ba-fbad-48cd-9639-193566da6ae5
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 895d98a3de3a6691ce60bf0456bb838403619f88
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="dowhile-statement-javascript"></a>do...while Deyimi (JavaScript)
Bir ifade bloğu bir kez çalıştırır ve değerlendiren bir koşul ifadesi kadar döngü yürütülmesi tekrarlar `false`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
do {  
    statement  
}  
while (expression) ;   
```  
  
## <a name="parameters"></a>Parametreler  
 `statement`  
 Gerekli. Deyim, yürütülecek `expression` olan `true`. Bileşik deyim olabilir.  
  
 `expression`  
 Gerekli. Boole yüklenen bir ifade `true` veya `false`. Varsa `expression` olan `true`, döngü yeniden yürütülür. Varsa `expression` olan `false`, döngü sonlandırılır.  
  
## <a name="remarks"></a>Açıklamalar  
 Farklı `while` deyimi, bir `do...while` döngü koşullu ifade değerlendirilir önce bir kez gerçekleştirilir.  
  
 Her satırda bir `do...while` bloğu kullanabilirsiniz `break` ifadesini döngü veya çıkmak program akışı neden için kullanabileceğiniz `continue` doğrudan gitmek için deyimi `while` ifade.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, ifadeler `do...while` döngünün devam değişkeni sürece yürütmek `i` değerinden 10'dur.  
  
```JavaScript  
var i = 0;  
do {  
    document.write(i + " ");  
    i++;  
} while (i < 10);  
  
// Output: 0 1 2 3 4 5 6 7 8 9   
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, koşulu karşılanmadı olsa bile ifadeleri döngü içinde bir kez çalıştırılır.  
  
```JavaScript  
var i = 10;  
do {  
    document.write(i + " ");  
    i++;  
} while (i < 10);  
  
// Output: 10  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [break deyimi](../../javascript/reference/break-statement-javascript.md)   
 [continue deyimi](../../javascript/reference/continue-statement-javascript.md)   
 [for deyimi](../../javascript/reference/for-statement-javascript.md)   
 [for... deyimi içinde](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [while deyimi](../../javascript/reference/while-statement-javascript.md)   
 [Etiketli deyim](../../javascript/reference/labeled-statement-javascript.md)