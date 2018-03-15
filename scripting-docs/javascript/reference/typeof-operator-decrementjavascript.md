---
title: "typeof işleci (JavaScript) | Microsoft Docs"
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
- typeof_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- typeof operator
ms.assetid: ee8a1036-119f-486f-b034-b07bdba87f0c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a9ff8c7942c773d138dd599956c41d1e583e6288
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="typeof-operator-javascript"></a>typeof İşleci (JavaScript)
Bir ifade veri türünü tanımlayan bir dize döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
typeof[(]expression[)] ;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 *İfade* için hangi tür bilgileri Aranan herhangi bir ifade bağımsız değişkeni aşağıdaki gibidir.  
  
 `typeof` İşleç türü bilgilerini dize olarak döndürür. Vardır yedi olası değerler `typeof` döndürür: "number," "dize," "boolean," "nesnesi," "işlev," "tanımsız" ve "Bilinmeyen".  
  
 Parantez isteğe bağlı olarak `typeof` sözdizimi.  

 Bir nesne bir XMLHTTPRequest içinde bilinmeyen bir tür olarak döndürebilir. Bir COM nesnesi hiçbir analog JavaScript'te ile de bilinmeyen bir tür olarak döndürebilir.
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, değişken veri türü sınar.  
  
```JavaScript  
var index = 5;  
var result = (typeof index === 'number');  
// Output: true  
  
var description = "abc";  
var result = (typeof description === 'string');  
// Output: true  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir veri türü için testleri `undefined` bildirilen ve bildirilmemiş değişkenler için.  
  
```JavaScript  
var declared;  
var result = (declared === undefined);  
// Output: true  
  
var result = (typeof declared === 'undefined');  
// Output: true  
  
var result = (typeof notDeclared === 'undefined')  
// Output: true  
  
var obj = {};  
var result = (typeof obj.propNotDeclared === 'undefined');  
// Output: true  
  
// An undeclared variable cannot be used in a comparison without  
// the typeof operator, so the next line generates an error.  
//  var result = (notDeclared === undefined);  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Array.isArray işlevi](../../javascript/reference/array-isarray-function-javascript.md)   
 [Object.getPrototypeOf Function](../../javascript/reference/object-getprototypeof-function-javascript.md)   
 [undefined sabiti](../../javascript/reference/undefined-constant-javascript.md)   
 [Karşılaştırma işleçleri](../../javascript/reference/comparison-operators-javascript.md)   
 [Veri türleri](../../javascript/data-types-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç Özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)