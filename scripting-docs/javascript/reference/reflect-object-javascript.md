---
title: Yansıtma nesnesi (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1df74f34-2eb4-42f1-a930-b943c86daa0e
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3574c54ee7ff69f56951cd7f4c9a93cac5275fc1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791789"
---
# <a name="reflect-object-javascript"></a>Yansıtma Nesnesi (JavaScript)
Durdurulan işlem kullanmak için yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Reflect.[method]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `method`  
 Gerekli. Yöntemlerinden birini adını `Reflect` nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Yansıtma nesnesi ile başlatılamaz `new` işleci.  
  
 Yöntemleri ile kullanılan genellikle yansıtacak [proxy'leri](../../javascript/reference/proxy-object-javascript.md) kodunuzda varsayılan davranışı uygulamadan varsayılan davranışa temsilciye izin verdiğinden.  
  
 Yansıtacak şekilde her proxy tuzak aynı ada sahip bir statik yöntem sağlar. Tablo açıklamalarında eksiksiz değildir.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|`Reflect.apply(target, thisArg, args)`|Benzer şekilde [uygulamak](../../javascript/reference/apply-method-function-javascript.md) işlevi nesnesinin yöntemi.|  
|`Reflect.construct(target, args)`|Bir işlev için eşdeğer `new` işleci.|  
|`Reflect.defineProperty(target, propertyName, descriptor)`|Benzer şekilde [Object.defineProperty](../../javascript/reference/object-defineproperty-function-javascript.md). Çağrı başarılı olup olmadığını gösteren bir Boole değeri döndürür.|  
|`Reflect.deleteProperty(target, propertyName)`|Benzer şekilde `delete` deyimi. Çağrı başarılı olup olmadığını gösteren bir Boole değeri döndürür.|  
|`Reflect.enumerate(target)`|Benzer şekilde [for... içinde](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md) deyimi, [Object.getOwnPropertySymbols](../../javascript/reference/object-getownpropertysymbols-function-javascript.md), [Object.keys](../../javascript/reference/object-keys-function-javascript.md) işlevini ve [JSON.stringify](../../javascript/reference/json-stringify-function-javascript.md).|  
|`Reflect.get(target, propertyName, receiver)`|Bir işlev için eşdeğer [alıcı](../../javascript/creating-objects-javascript.md) özellikleri.|  
|`Reflect.getOwnPropertyDescriptor(target, propertyName)`|Benzer şekilde [Object.getOwnPropertyDescriptor](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md). Çağrı başarılı olup olmadığını gösteren bir Boole değeri döndürür.|  
|`Reflect.getPrototypeOf(target)`|Benzer şekilde [Object.getPrototypeOf](../../javascript/reference/object-getprototypeof-function-javascript.md).|  
|`Reflect.has(target, propertyName)`|Benzer şekilde `in` işleci, [hasOwnProperty yöntemi (nesne)](../../javascript/reference/hasownproperty-method-object-javascript.md)ve diğer yöntemleri. Çağrı başarılı olup olmadığını gösteren bir Boole değeri döndürür.|  
|`Reflect.isExtensible(target)`|Benzer şekilde [Object.isExtensible](../../javascript/reference/object-isextensible-function-javascript.md).|  
|`Reflect.ownKeys(target)`|Benzer şekilde [Object.getOwnPropertyNames](../../javascript/reference/object-getownpropertynames-function-javascript.md).|  
|`Reflect.preventExtensions(target)`|Benzer şekilde [Object.preventExtensions](../../javascript/reference/object-preventextensions-function-javascript.md). Çağrı başarılı olup olmadığını gösteren bir Boole değeri döndürür.|  
|`Reflect.set(target, propertyName, value, receiver)`|Kullanarak benzer [ayarlayıcı](../../javascript/creating-objects-javascript.md) özelliği. Çağrı başarılı olup olmadığını gösteren bir Boole değeri döndürür.|  
|`Reflect.setPrototypeOf(target, prototype)`|Benzer şekilde [Object.setPrototypeOf](../../javascript/reference/object-setprototypeof-function-javascript.md). Çağrı başarılı olup olmadığını gösteren bir Boole değeri döndürür.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde nasıl kullanıldığını gösterir `Reflect.get` blokları işlemleri için bir alt çizgi ile başlayan özellikler alma proxy yazılacak.  
  
```JavaScript  
var p = new Proxy({}, {  
    get(k, t, r) {  
        // return undefined if key begins with underscore  
        if(k[0] === '_') return undefined;  
  
       // otherwise do default behavior  
       return Reflect.get(k, t, r);  
    }  
});  
  
p._foo = 1;  
console.log(p._foo);  
  
p.foo = 1;  
console.log(p.foo);  
  
// Output:  
// undefined  
// 1  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]