---
title: işlev deyimi (JavaScript) | Microsoft Docs
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
- function_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- new operator
- declaring functions, syntax
- function statement
- declaring functions
ms.assetid: cc9cfd43-1305-41c8-ad67-545d20f4fafe
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e5fac3647e9374a9c909a420b73b86354cac69b6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790571"
---
# <a name="function-statement-javascript"></a>function Deyimi (JavaScript)
Yeni bir işlev bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
function functionname ([arg1 [, arg2 [,...[, argN]]]]) {  
    statements  
}   
```  
  
## <a name="parameters"></a>Parametreler  
 `functionname`  
 Gerekli. İşlevin adı.  
  
 `arg1...argN`  
 İsteğe bağlı. Bağımsız değişkenler isteğe bağlı, virgülle ayrılmış bir listesini işlevi bilir.  
  
 `statements`  
 İsteğe bağlı. Bir veya daha fazla[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] deyimleri.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanmak `function` daha sonra kullanmak için bir işlev bildirmek için deyimi. Bulunan kod `statements` işlevi başka bir yerde komut dosyasındaki çağrılır kadar yürütülmedi.  
  
 [Dönmek](../../javascript/reference/return-statement-javascript.md) deyimi işlevinden bir değer döndürmek için kullanılır. Kullanmak zorunda değil bir `return` deyimi; işlevi sonuna ulaştığında dönüş program olacaktır. Öyle değilse `return` deyimi işlevinde yürütülen veya `return` deyimi sahip herhangi bir ifade, işlevi değerini döndürür `undefined`.  
  
> [!NOTE]
>  Bir işlev çağırdığınızda, parantezleri ve gerekli tüm bağımsız değişkenleri eklediğinizden emin olun. Parantez olmadan bir işlevi çağırmak değil işlevinin sonuçlarını işlevi için bir başvuru döndürür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `function` deyimi.  
  
```JavaScript  
function myfunction (arg1, arg2) {  
    var r = arg1 * arg2;  
    return(r);  
}  
```  
  
## <a name="example"></a>Örnek  
 Bir işlev bir değişkene atanabilir. Bu, aşağıdaki örnekte gösterilmiştir.  
  
```JavaScript  
function AddFive(x) {  
    return x + 5;  
}  
  
function AddTen(x) {  
    return x + 10;  
}  
  
var condition = false;  
  
var MyFunc;  
if (condition) {  
    MyFunc = AddFive;  
}  
else {  
    MyFunc = AddTen;  
}  
  
var result = MyFunc(123);  
// Output: 133  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [New işleci](../../javascript/reference/new-operator-decrementjavascript.md)