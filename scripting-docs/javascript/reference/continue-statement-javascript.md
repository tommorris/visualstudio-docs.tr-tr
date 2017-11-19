---
title: continue deyimi (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: continue_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- do...while statement
- continue statement
- loop structures, continue statement
ms.assetid: f8a30d9f-e2de-4e1f-8668-4e4cf95f7df9
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 391f919c4d06a6c529bfee34e21ca7238b3c63b7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="continue-statement-javascript"></a>continue Deyimi (JavaScript)
Geçerli yineleme döngüsü durdurur ve yeni bir yineleme başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
continue [label];  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İsteğe bağlı `label` bağımsız değişkeni belirtir ifadesine `continue` uygular.  
  
 Kullanabileceğiniz `continue` deyimi içinde yalnızca bir `while`, `do...while`, **için**, veya `for...in` döngü. Yürütme `continue` deyimi geçerli döngü durdurur ve program akışı döngünün başlangıcı ile devam eder. Bu, döngüler farklı türleri hakkında aşağıdaki etkileri gösterir:  
  
-   `while`ve `do...while` döngüleri kendi koşulu test ve true ise, döngü yeniden yürütün.  
  
-   `for`Döngüler kendi artışı ifade yürütün ve test ifade doğruysa, döngü yeniden yürütün.  
  
-   `for...in`Döngüler belirtilen değişkeni sonraki alana devam ve döngü yeniden çalıştırın.  
  
## <a name="examples"></a>Örnekler  
 Bu örnekte, bir döngü 1 ile 9 arasında yineler. Arasında deyimleri `continue` ve sonuna `for` gövde kullanımı nedeniyle atlanır `continue` ifade birlikte deyimi `(i < 5)`.  
  
```JavaScript  
for (var i = 1; i < 10; i++) {  
    if (i < 5) {  
        continue;  
    }  
    document.write (i);  
    document.write (" ");  
}  
  
// Output: 5 6 7 8 9  
```  
  
 Aşağıdaki kodda, `continue` deyimi başvurduğu `for` öncesinde döngü `Inner:` etiketi. Zaman `j` 24'ün, `continue` deyimi neden `for` döngü sonraki yinelemeye gidin. 23 ve 25 ile 30 arasında 21 sayıları, her satırda yazdırın.  
  
```JavaScript  
Outer:  
for (var i = 1; i <= 10; i++) {  
    document.write ("<br />");  
    document.write ("i: " + i);  
    document.write (" j: ");  
  
Inner:  
    for (var j = 21; j <= 30; j++) {  
        if (j == 24) {  
             continue Inner;  
        }  
        document.write (j + " ");  
    }  
}  
  
//Output:  
//i: 1 j: 21 22 23 25 26 27 28 29 30   
//i: 2 j: 21 22 23 25 26 27 28 29 30   
//i: 3 j: 21 22 23 25 26 27 28 29 30   
//i: 4 j: 21 22 23 25 26 27 28 29 30   
//i: 5 j: 21 22 23 25 26 27 28 29 30   
//i: 6 j: 21 22 23 25 26 27 28 29 30   
//i: 7 j: 21 22 23 25 26 27 28 29 30   
//i: 8 j: 21 22 23 25 26 27 28 29 30   
//i: 9 j: 21 22 23 25 26 27 28 29 30   
//i: 10 j: 21 22 23 25 26 27 28 29 30  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [break deyimi](../../javascript/reference/break-statement-javascript.md)   
 [do... while deyimi](../../javascript/reference/do-dot-dot-dot-while-statement-javascript.md)   
 [for deyimi](../../javascript/reference/for-statement-javascript.md)   
 [for... deyimi içinde](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [Etiketli deyim](../../javascript/reference/labeled-statement-javascript.md)   
 [while deyimi](../../javascript/reference/while-statement-javascript.md)