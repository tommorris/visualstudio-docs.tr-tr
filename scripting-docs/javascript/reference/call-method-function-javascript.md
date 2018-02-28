---
title: "call yöntemi (işlev) (JavaScript) | Microsoft Docs"
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
- call
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- call method
ms.assetid: fa356dec-48e6-4f75-8bf3-c1814a76818f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2ef871f85459ad875a747ae79c7c054b30a82e55
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="call-method-function-javascript"></a>call Yöntemi (İşlev) (JavaScript)
Geçerli nesne için başka bir nesnenin değiştirerek bir nesnenin bir yöntemi çağırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
call([thisObj[, arg1[, arg2[,  [, argN]]]]])  
```  
  
## <a name="parameters"></a>Parametreler  
 `thisObj`  
 İsteğe bağlı. Geçerli nesne olarak kullanılacak nesne.  
  
 `arg1, arg2, , argN`  
 İsteğe bağlı. Yönteme iletilecek bağımsız değişkenler listesi.  
  
## <a name="remarks"></a>Açıklamalar  
 `call` Yöntemi başka bir nesne adına bir yöntemi çağırmak için kullanılır. Değiştirmenize izin verir `this` nesnesi tarafından belirtilen yeni nesneye özgün bağlamından işlevinin `thisObj`.  
  
 Varsa `thisObj` sağlanmaz, `global` nesne olarak kullanılıyor `thisObj`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösterir `call` yöntemi.  
  
```JavaScript  
function callMe(arg1, arg2){  
    var s = "";  
  
    s += "this value: " + this;  
    s += "<br />";  
    for (i in callMe.arguments) {  
        s += "arguments: " + callMe.arguments[i];  
        s += "<br />";  
    }  
    return s;  
}  
  
document.write("Original function: <br/>");  
document.write(callMe(1, 2));  
document.write("<br/>");  
  
document.write("Function called with call: <br/>");  
document.write(callMe.call(3, 4, 5));  
  
// Output:   
// Original function:   
// this value: [object Window]  
// arguments: 1  
// arguments: 2  
  
// Function called with call:   
// this value: 3  
// arguments: 4  
// arguments: 5  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlev nesnesi](../../javascript/reference/function-object-javascript.md)   
 [apply yöntemi (işlev)](../../javascript/reference/apply-method-function-javascript.md)