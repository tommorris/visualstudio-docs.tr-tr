---
title: break deyimi (JavaScript) | Microsoft Docs
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
- break_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- do...while statement
- break statement
ms.assetid: 5be0f2a8-5fe7-4a6c-89af-ca20a925ce87
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5f085a4e51309bf9a060e9ffa352c6ae85924237
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789143"
---
# <a name="break-statement-javascript"></a>break Deyimi (JavaScript)
Geçerli döngü ya da Eğer birlikte sonlandırır bir `label`, ilişkili deyim sonlandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
break [label];  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İsteğe bağlı `label` bağımsız değişkeni, kesilmesini deyimi etiketini belirtir.  
  
 Tipik olarak kullandığınız `break` deyiminde `switch` deyimleri ve `while`, `for`, `for...in`, veya `do...while` döngüler. En sık kullandığınız `label` değişkeninde `switch` deyimleri, ancak kullanılabilir herhangi bir deyimle, basit bileşik ister.  
  
 Yürütme `break` deyimi geçerli döngü ya da deyimi çıkar ve komut dosyası yürütme hemen deyimi ile başlar.  
  
## <a name="examples"></a>Örnekler  
 Bu örnekte, sayaç 1 ile 99 saymak üzere ayarlanmış; Ancak, `break` açıklamayı sonlandıran döngü sonra 14 sayar.  
  
```JavaScript  
for (var i = 1; i < 100; i++) {  
    if (i == 15) {  
        break;  
    }  
    document.write (i);  
    document.write (" ");  
}  
  
// Output: 1234567891011121314  
```  
  
 Aşağıdaki kodda, `break` deyimi başvurduğu `for` öncesinde döngü `Inner:` deyimi. Zaman `j` 24'e eşittir `break` deyimi Bu döngü çıkmak program akışı neden olur. 23 aracılığıyla 21 sayıları, her satırda yazdırın.  
  
```JavaScript  
Outer:  
for (var i = 1; i <= 10; i++) {  
    document.write ("<br />");  
    document.write ("i: " + i);  
    document.write (" j: ");  
Inner:  
    for (var j = 21; j <= 30; j++) {  
        if (j == 24) {  
            break Inner;  
        }  
        document.write (j + " ");  
    }  
}  
  
// Output:   
// i: 1 j: 21 22 23   
// i: 2 j: 21 22 23   
// i: 3 j: 21 22 23   
// i: 4 j: 21 22 23   
// i: 5 j: 21 22 23   
// i: 6 j: 21 22 23   
// i: 7 j: 21 22 23   
// i: 8 j: 21 22 23   
// i: 9 j: 21 22 23   
// i: 10 j: 21 22 23  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [continue deyimi](../../javascript/reference/continue-statement-javascript.md)   
 [do... while deyimi](../../javascript/reference/do-dot-dot-dot-while-statement-javascript.md)   
 [for deyimi](../../javascript/reference/for-statement-javascript.md)   
 [for... deyimi içinde](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [Etiketli deyim](../../javascript/reference/labeled-statement-javascript.md)   
 [while deyimi](../../javascript/reference/while-statement-javascript.md)