---
title: Object.Create işlevi (JavaScript) | Microsoft Docs
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
helpviewer_keywords:
- create function [JavaScript]
- Object.create function [JavaScript]
ms.assetid: 0ad31f36-a9ee-444e-b0fe-c87843d03196
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f359908c5c836743e22390580f542df27d7b98e7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791654"
---
# <a name="objectcreate-function-javascript"></a>Object.create İşlevi (JavaScript)
Belirtilen prototipi sahip ve isteğe bağlı olarak belirtilen özellikleri içeren bir nesne oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Object.create(prototype, descriptors)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `prototype`  
 Gerekli. Prototip olarak kullanılacak nesnedir. Olabilir `null`.  
  
 `descriptors`  
 İsteğe bağlı. A [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] bir veya daha fazla özellik tanımları içeren nesne.  
  
 A *veri özelliği* almak ve bir değer ayarlamak bir özelliktir. Bir veri özellik tanımlayıcısını içeren bir `value` özniteliği, artı `writable`, `enumerable`, ve `configurable` öznitelikleri. Son üç özniteliği belirtilmezse, bunlar varsayılan `false`. Bir *erişimci özelliği* değeri alınan ya da her zaman bir kullanıcı tarafından sağlanan işlevi çağırır. Erişimci özellik tanımlayıcısını içeren bir `set` öznitelik, bir `get` özniteliği ya da her ikisini de. Daha fazla bilgi için bkz: [Object.defineProperty işlevi](../../javascript/reference/object-defineproperty-function-javascript.md).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Belirtilen iç prototip sahip ve belirtilen özellikleri, varsa içeren yeni bir nesne.  
  
## <a name="exceptions"></a>Özel Durumlar  
 A `TypeError` aşağıdaki koşullardan herhangi biri doğru olduğunda özel durum:  
  
-   `prototype` Bağımsız değişkeni bir nesne değil ve değil `null`.  
  
-   Bir tanımlayıcı `descriptors` bağımsız bir `value` veya `writable` özniteliği ve sahip bir `get` veya `set` özniteliği.  
  
-   Bir tanımlayıcı `descriptors` bağımsız bir `get` veya `set` bir işlev değil özniteliği.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanarak bu işlevi kullanabilirsiniz bir `null``prototype` prototip zinciri durdurmak için parametre. Oluşturulan nesne hiçbir prototip sahip olur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, kullanarak bir nesne oluşturur bir `null` prototip ve iki numaralandırılabilir özellikler ekler.  
  
```JavaScript  
var newObj = Object.create(null, {  
            size: {  
                value: "large",  
                enumerable: true  
            },  
            shape: {  
                value: "round",  
                enumerable: true  
            }  
        });  
  
document.write(newObj.size + "<br/>");  
document.write(newObj.shape + "<br/>");  
document.write(Object.getPrototypeOf(newObj));  
  
// Output:  
// large  
// round  
// null  
  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, aynı iç prototip nesne olarak sahip bir nesne oluşturur. Değişmez değer bir nesne kullanılarak oluşturulan bir nesne olarak aynı prototip olduğunu görebilirsiniz. [Object.getPrototypeOf](../../javascript/reference/object-getprototypeof-function-javascript.md) işlevi özgün nesne örneğini alır. Nesnenin özellik tanımlayıcısı almak için kullanabileceğiniz [Object.getOwnPropertyDescriptor işlevi](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md).  
  
```JavaScript  
var firstLine = { x: undefined, y: undefined };  
  
var secondLine = Object.create(Object.prototype, {  
        x: {  
                value: undefined,   
                writable: true,   
                configurable: true,   
                enumerable: true  
            },  
            y: {  
                value: undefined,   
                writable: true,   
                configurable: true,   
                enumerable: true  
            }  
});  
  
document.write("first line prototype = " + Object.getPrototypeOf(firstLine));  
document.write("<br/>");  
document.write("second line prototype = " + Object.getPrototypeOf(secondLine));  
  
// Output:  
// first line prototype = [object Object]  
// second line prototype = [object Object]  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, Şekil nesnesi olarak aynı iç prototip sahip bir nesne oluşturur.  
  
```JavaScript  
  
// Create the shape object.  
var Shape = { twoDimensional: true, color: undefined, hasLineSegments: undefined };  
  
var Square = Object.create(Object.getPrototypeOf(Shape));  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Object.getPrototypeOf işlevi](../../javascript/reference/object-getprototypeof-function-javascript.md)   
 [isPrototypeOf yöntemi (nesne)](../../javascript/reference/isprototypeof-method-object-javascript.md)   
 [Nesne oluşturma](../../javascript/creating-objects-javascript.md)