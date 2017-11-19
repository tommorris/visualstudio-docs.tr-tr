---
title: "Deyimi (JavaScript) için | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: for_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: loop structures, for statements
ms.assetid: bae0ec40-152e-43f3-969b-3696489ec5c4
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7142dbb8c00a351918d0821c3ca7dba3d7b2acb6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="for-statement-javascript"></a>for Deyimi (JavaScript)
Belirtilen bir koşul true olduğu sürece deyimleri için bloğunu yürütür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
for ([initialization]; [test]; [increment])  
   statement   
```  
  
## <a name="parameters"></a>Parametreler  
 `initialization`  
 İsteğe bağlı. Bir ifade. Döngü yürütülmeden önce bu deyim yalnızca bir kez çalıştırılır.  
  
 `test`  
 İsteğe bağlı. Boole ifadesi. Varsa `test` olan `true`, `statement` yürütülür. Varsa `test` varsa `false`, döngü sonlandırılır.  
  
 `increment`  
 İsteğe bağlı. Bir ifade. Döngünün her geçiş işleminin sonunda artışı ifade yürütülür.  
  
 `statement`  
 İsteğe bağlı. Varsa yürütülmesi için bir veya daha fazla deyimleri `test` olan **doğru**. Bileşik deyim olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 Genellikle kullandığınız bir `for` döngü döngü olarak yürütülen bilinen kaç kez olduğunda. A `for` döngü, sıralı işlem gerçekleştirme ve diziler yineleme için yararlıdır.  
  
 Koşullu ifade test döngü çalışmaya başlamadan önce bu nedenle oluşur bir `for` sıfır veya daha fazla kez deyimini yürütür.  
  
 Her satırda bir `for` döngü deyimi blok kullanabilir `break` ifadesini döngü veya çıkmak için kullanabileceğiniz `continue` Denetim Döngü sonraki yinelemeye aktarma deyimi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, `for` deyimini yürütür kapalı deyimleri gibi:  
  
-   İlk olarak, ilk değer değişkenin `i` değerlendirilir.  
  
-   Ardından, değeri olan en kısa sürece `i` 9, küçük veya ona eşit `document.write` deyimleri çalıştırılır ve `i` değerlendirilir.  
  
-   Zaman `i` 9 ' büyük koşul false olur ve denetim döngü dışında aktarılır.  
  
```JavaScript  
// i is set to 0 at the start and is incremented by 1 at the  
// end of each iteration.  
// The loop terminates when i is not less than or equal to  
// 9 before a loop iteration.  
for (var i = 0; i <= 9; i++) {  
   document.write (i);  
   document.write (" ");  
}  
  
// Output: 0 1 2 3 4 5 6 7 8 9  
```  
  
## <a name="example"></a>Örnek  
 Tüm ifadelerin `for` deyimi isteğe bağlıdır. Aşağıdaki örnekte, `for` deyimleri sonsuz bir döngüde oluşturmak ve bir `break` deyimi döngü çıkmak için kullanılır.  
  
```JavaScript  
var j = 0;  
for (;;) {  
    if (j >= 5) {  
        break;  
    }  
    j++;  
    document.write (j + " ");  
}  
  
// Output: 1 2 3 4 5  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [for... deyimi içinde](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [while deyimi](../../javascript/reference/while-statement-javascript.md)