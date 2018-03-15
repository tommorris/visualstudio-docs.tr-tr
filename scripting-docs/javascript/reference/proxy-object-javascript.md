---
title: Proxy nesnesi (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 2b89abee-04fa-47e6-9676-980016cff5f8
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4ee75310f1d976e0a0896b1be34a80c594cdd054
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="proxy-object-javascript"></a>Proxy Nesnesi (JavaScript)
Bir nesne için özel davranışını etkinleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
proxyObj = new Proxy(target, handler)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `target`  
 Gerekli. Nesne veya proxy sunucu tarafından sanallaştırılacak işlev.  
  
 `handler`  
 Gerekli. Özel davranışı uygulamak yöntemleri (tuzakları) sahip bir nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 A `Proxy` nesnesi başka bir nesne üzerinde iç düşük düzey işlemler müdahale için kullanılır. Proxy nesneleri kişiler tarafından ele, nesne sanallaştırma, günlüğe kaydetme ve profil ve diğer amaçlar için kullanılabilir.  
  
 Belirli bir işlemi Tuzağını işleyicisinde proxy için tanımlı değil, işlem hedefe iletilir.  
  
 İşleyici nesnesi özel davranışı uygulamak için aşağıdaki yöntemleri (tuzakları) tanımlar. Örnekler burada eksiksiz değildir. Koşullu varsayılan davranışı işleyicisi yönteminde desteklemek için yöntemlerini kullanın [yansıtmak nesne](../../javascript/reference/reflect-object-javascript.md).  
  
|İşleyici yöntemi (tuzak) sözdizimi|Kullanım örnekleri|  
|------------------------------------|-----------------------|  
|`apply: function(target, thisArg, args)`|Bir işlev çağrısı Tuzağını.|  
|`construct: function(target, args)`|Bir oluşturucu Tuzağını.|  
|`defineProperty: function(target, propertyName, descriptor)`|Yakalama için [Object.defineProperty işlevi](../../javascript/reference/object-defineproperty-function-javascript.md).|  
|`deleteProperty: function(target, propertyName)`|Yakalama için `delete` deyimi.|  
|`enumerate: function(target)`|Yakalama için [for... içinde](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md) deyimi, [Object.getOwnPropertySymbols](../../javascript/reference/object-getownpropertysymbols-function-javascript.md), [Object.keys](../../javascript/reference/object-keys-function-javascript.md) işlevini ve [JSON.stringify](../../javascript/reference/json-stringify-function-javascript.md).|  
|`get: function(target, propertyName, receiver)`|Herhangi bir yakalama [alıcı](../../javascript/creating-objects-javascript.md) özellikleri.|  
|`getOwnPropertyDescriptor: function(target, propertyName)`|Yakalama için [Object.getOwnPropertyDescriptor işlevi](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md).|  
|`getPrototypeOf: function(target)`|Yakalama için [Object.getPrototypeOf işlevi](../../javascript/reference/object-getprototypeof-function-javascript.md).|  
|`has: function(target, propertyName)`|Yakalama için `in` işleci, [hasOwnProperty yöntemi (nesne)](../../javascript/reference/hasownproperty-method-object-javascript.md)ve diğer yöntemleri.|  
|`isExtensible: function(target)`|Yakalama için [Object.isExtensible işlevi](../../javascript/reference/object-isextensible-function-javascript.md).|  
|`ownKeys: function(target)`|Yakalama için [Object.getOwnPropertyNames işlevi](../../javascript/reference/object-getownpropertynames-function-javascript.md).|  
|`preventExtensions: function(target)`|Yakalama için [Object.preventExtensions işlevi](../../javascript/reference/object-preventextensions-function-javascript.md).|  
|`set: function(target, propertyName, value, receiver)`|Herhangi bir yakalama [ayarlayıcı](../../javascript/creating-objects-javascript.md) özellikleri.|  
|`setPrototypeOf: function(target, prototype)`|Yakalama için [Object.setPrototypeOf](../../javascript/reference/object-setprototypeof-function-javascript.md).|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği kullanarak bir nesnenin değişmez değer için bir proxy oluşturulacağını gösterir `get` yakalama.  
  
```JavaScript  
var target = {};  
var handler = {  
  get: function (target, property, receiver) {  
    // This example includes a template string.  
    return `Hello, ${property}!`;  
  }  
};  
  
var p = new Proxy(target, handler);  
console.log(p.world);  
  
// Output:  
// Hello, world!  
  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde işlevi kullanmak için bir proxy oluşturulacağını gösterir `apply` yakalama.  
  
```JavaScript  
var target = function () { return 'I am the target'; };  
var handler = {  
  // This example includes a rest parameter.  
  apply: function (receiver, ...args) {  
    return 'I am the proxy';  
  }  
};  
  
var p = new Proxy(target, handler);  
console.log(target()):  
console.log(p()):  
  
// Output:  
// I am the target  
// I am the proxy  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]
