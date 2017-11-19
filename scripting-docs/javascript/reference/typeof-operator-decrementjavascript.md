---
title: "typeof işleci (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: typeof_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: typeof operator
ms.assetid: ee8a1036-119f-486f-b034-b07bdba87f0c
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c79c69e6c447b14e61fa67ccb8600d5d83bebd2b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="typeof-operator-javascript"></a>typeof İşleci (JavaScript)
Bir ifade veri türünü tanımlayan bir dize döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
typeof[(]expression[)] ;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 *İfade* için hangi tür bilgileri Aranan herhangi bir ifade bağımsız değişkeni aşağıdaki gibidir.  
  
 `typeof` İşleç türü bilgilerini dize olarak döndürür. Vardır altı olası değerler `typeof` döndürür: "number," "dize," "boolean," "nesnesi," "işlev" ve "tanımsız."  
  
 Parantez isteğe bağlı olarak `typeof` sözdizimi.  
  
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
 [Object.getPrototypeOf işlevi](../../javascript/reference/object-getprototypeof-function-javascript.md)   
 [undefined sabiti](../../javascript/reference/undefined-constant-javascript.md)   
 [Karşılaştırma işleçleri](../../javascript/reference/comparison-operators-javascript.md)   
 [Veri türleri](../../javascript/data-types-javascript.md)   
 [İşleç önceliği](../../javascript/operator-subtractprecedence-javascript.md)   
 [İşleç özeti (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)