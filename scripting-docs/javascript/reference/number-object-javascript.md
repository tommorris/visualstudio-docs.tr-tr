---
title: "Sayı nesnesi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Number_JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: Number object
ms.assetid: 76e87c37-cf6c-46cc-bafa-04be1fe3d78d
caps.latest.revision: "23"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7cbe58fdc9673a8fffe35b8b15d7edbf86ffa655
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="number-object-javascript"></a>Sayı Nesnesi (JavaScript)
Herhangi bir türde bir sayıyı temsil eden nesne. Tüm JavaScript 64-bit kayan nokta sayıları numaralarıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
numObj = new Number(value)  
```  
  
## <a name="parameters"></a>Parametreler  
 `numObj`  
 Gerekli. Değişken adına `Number` nesne atanır.  
  
 `value`  
 Gerekli. Sayısal değer.  
  
## <a name="remarks"></a>Açıklamalar  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]oluşturur `Number` nesneler bir değişken için bir sayı değeri, örneğin ayarlandığında `var num = 255.336;`. Nadiren oluşturmak gerekli olan `Number` açıkça nesneleri.  
  
 `Number` Nesne varsa kendi özellikleri ve yöntemleri, ayrıca özellikleri ve yöntemleri devralınan `Object`. Sayı dönüştürülür belirli koşullar altında dizeleri halinde, bir sayı eklendiğinde veya bir dizeyle de olarak göre birleştirilmiş örnek anlamına gelir için `toString` yöntemi. Daha fazla bilgi için bkz: [Toplama işleci (+)](../../javascript/reference/addition-operator-decrement-javascript.md).  
  
 JavaScript birkaç sayı sabitleri vardır. Tam bir listesi için bkz: [sayı sabitleri](../../javascript/reference/number-constants-javascript.md).  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda özelliklerini `Number` nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[constructor özelliği](../../javascript/reference/constructor-property-object-javascript.md)|Bir nesneyi oluşturan işlevi belirtir.|  
|[prototype özelliği](../../javascript/reference/prototype-property-object-javascript.md)|Bir nesne sınıfı için prototipe bir başvuru döndürür.|  
  
## <a name="functions"></a>İşlevler  
 Aşağıdaki tabloda işlevlerini listeler `Number` nesnesi.  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|[Number.isFinite işlevi](../../javascript/reference/number-isfinite-function-number-javascript.md)|Bir değer sınırlı olup olmadığını belirten bir Boole değeri döndürür.|  
|[Number.isınteger işlevi](../../javascript/reference/number-isinteger-function-number-javascript.md)|Bir değer bir tamsayı olup olmadığını belirten bir Boole değeri döndürür.|  
|[Number.isNaN işlevi](../../javascript/reference/number-isnan-function-number-javascript.md)|Bir değer ayrılan değeri olup olmadığını belirten bir Boole değeri döndürür `NaN` (sayı değil).|  
|[Number.issafeınteger](../../javascript/reference/number-issafeinteger-number-javascript.md)|Bir değer güvenle JavaScript'te temsil edilebilir olup olmadığını gösteren bir Boole değeri döndürür.|  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `Number` nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[hasOwnProperty yöntemi](../../javascript/reference/hasownproperty-method-object-javascript.md)|Bir nesnenin belirtilen adda bir özelliği olup olmadığını belirten bir Boolean değer döndürür.|  
|[isPrototypeOf yöntemi](../../javascript/reference/isprototypeof-method-object-javascript.md)|Bir nesne başka bir nesnenin prototip hiyerarşisinde var olup olmadığını belirten bir Boole değeri döndürür.|  
|[Propertyısenumerable yöntemi](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|Belirtilen bir özelliğin bir nesnenin parçası olup olmadığını ve numaralandırılabilir olup olmadığını belirten bir Boolean değer döndürür.|  
|[toExponential yöntemi](../../javascript/reference/toexponential-method-number-javascript.md)|Üstel gösterimde temsil edilen bir sayı içeren bir dize döndürür.|  
|[toFixed yöntemi](../../javascript/reference/tofixed-method-number-javascript.md)|Sabit noktalı gösterim sayıyı temsil eden bir dize döndürür.|  
|[toLocaleString yöntemi](../../javascript/reference/tolocalestring-number.md)|Geçerli bölgesel ayarına göre bir dizeye dönüştürülen bir nesne döndürür.|  
|[toPrecision yöntemi](../../javascript/reference/toprecision-method-number-javascript.md)|Üstel ya da sabit noktalı gösterimde temsil ve belirtilen sayıda basamağa sahip bir sayı içeren bir dize döndürür.|  
|[toString yöntemi](../../javascript/reference/tostring-method-object-javascript.md)|Bir nesnenin dize gösterimini döndürür.|  
|[valueOf yöntemi](../../javascript/reference/valueof-method-object-javascript.md)|Belirtilen nesne ilkel değerini döndürür.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript nesneleri](../../javascript/reference/javascript-objects.md)   
 [Matematik nesnesi](../../javascript/reference/math-object-javascript.md)   
 [New işleci](../../javascript/reference/new-operator-decrementjavascript.md)