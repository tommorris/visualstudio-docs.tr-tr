---
title: apply yöntemi (işlev) (JavaScript) | Microsoft Docs
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
- apply
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Apply method
ms.assetid: b36df78e-b14b-46ca-b5cb-de752d80f40a
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5a06a37006937b07214bf5a314d5151c3b658acf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788855"
---
# <a name="apply-method-function-javascript"></a>apply Yöntemi (İşlev) (JavaScript)
Belirtilen nesne için değiştirerek işlevi çağırdığı `this` işlevi ve belirtilen dizi işlevinin bağımsız değişkenleri için değeri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
apply([thisObj[,argArray]])  
```  
  
## <a name="parameters"></a>Parametreler  
 `thisObj`  
 İsteğe bağlı. Nesne olarak kullanılacak `this` nesnesi.  
  
 `argArray`  
 İsteğe bağlı. İşlev için geçirilecek bağımsız değişkenler kümesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `argArray` "Nesne bekleniyor" hata oluşursa, geçerli bir nesne değil.  
  
 Ne `argArray` ya da `thisObj` sağlanır, özgün `this` nesne olarak kullanılıyor `thisObj` ve hiç bağımsız değişken geçirildi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod Uygula yönteminin nasıl kullanılacağını gösterir.  
  
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
  
document.write("Function called with apply: <br/>");  
document.write(callMe.apply(3, [ 4, 5 ]));  
  
// Output:   
// Original function:   
// this value: [object Window]  
// arguments: 1  
// arguments: 2  
  
// Function called with apply:   
// this value: 3  
// arguments: 4  
// arguments: 5  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlev nesnesi](../../javascript/reference/function-object-javascript.md)