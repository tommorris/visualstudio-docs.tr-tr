---
title: return deyimi (JavaScript) | Microsoft Docs
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
- return_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- terminating execution
- return statement
- function statement
- return statement, syntax
- return statement, exiting functions in script
ms.assetid: a9130d90-11fb-43f5-a819-7e5435f74c05
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c28f17bed2dfff021ea1aea268bb7a2eb3f3e58
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791309"
---
# <a name="return-statement-javascript"></a>return Deyimi (JavaScript)
Geçerli işlevinden çıkar ve bu işlevi bir değer döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
return[(][expression][)];   
```  
  
## <a name="remarks"></a>Açıklamalar  
 İsteğe bağlı *ifade* değişkendir işlevinden döndürülecek değer. Atlanırsa, işlevi bir değer döndürmüyor.  
  
 Kullandığınız `return` işlevinin yürütme durdurup değerini döndürmek için deyimi *ifade*. Varsa *ifade* atlanırsa, ya da hiç `return` deyimi işlev içinde yürütülürse, geçerli işlevini çağırdı ifadesi tanımlanmamış değeri atanır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `return` deyimi.  
  
```JavaScript  
function myfunction(arg1, arg2){  
   var r;  
   r = arg1 * arg2;  
   return(r);  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `return` deyimi bir işlev döndürür.  
  
```JavaScript  
function doWork() {  
    return function calculate(y) { return y + 1; };  
}  
  
var func = doWork();  
var x = func(5);  
document.write(x);  
  
// Output: 6  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Function deyimi](../../javascript/reference/function-statement-javascript.md)