---
title: "Object.isSealed işlevi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- properties [JavaScript], locking attributes
- isSealed function [JavaScript]
- Object.isSealed [JavaScript]
ms.assetid: af4f192e-cebe-44b9-8eef-90c096f5ae8f
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d3b9cb603a456382e3b23e6f7d0037063027b98
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="objectissealed-function-javascript"></a>Object.isSealed İşlevi (JavaScript)
Döndürür `true` var olan özellik öznitelikleri bir nesne değiştirilemez ve yeni özellikleri nesneye eklenemez.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
Object.isSealed(object)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `object`  
 Gerekli. Sınanacak nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`Aşağıdaki her ikisi de doğruysa:  
  
-   Yeni özellikler nesneye eklenemez belirten olmayan-genişletilebilir, nesnesidir.  
  
-   `configurable` Özniteliği `false` tüm var olan özellikler için.  
  
 Nesne herhangi bir özelliği yoksa, işlevi döndürür `true` nesne Genişletilebilir olmayan ise.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `object` bağımsız değişkeni bir nesne değil bir `TypeError` özel durumu oluşur.  
  
## <a name="remarks"></a>Açıklamalar  
 Zaman `configurable` özniteliği bir özellik olan `false`, özellik öznitelikleri değiştirilemez ve özellik silinemez. Zaman `writable` olan `false`, veri özellik değeri değiştirilemez. Zaman `configurable` olan `false` ve `writable` olan `true`, `value` ve `writable` öznitelikleri değiştirilebilir.  
  
 `Object.isSealed` İşlevi kullanmaz `writable` dönüş değeri belirlemek için özellikler özniteliği.  
  
 Özellik öznitelikleri ayarlama hakkında daha fazla bilgi için bkz: [Object.defineProperty işlevi](../../javascript/reference/object-defineproperty-function-javascript.md). Bir özellik özniteliklerini elde etmek için kullanabileceğiniz [Object.getOwnPropertyDescriptor işlevi](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md).  
  
## <a name="related-functions"></a>İlgili işlevleri  
 Aşağıdaki ilgili işlevleri nesne öznitelikleri değiştirilmesini engellemek.  
  
|İşlev|Nesne Genişletilebilir olmayan yapılır|`configurable`ayarlanmış `false` her bir özellik için|`writable`ayarlanmış `false` her bir özellik için|  
|--------------|------------------------------------|--------------------------------------------------------|----------------------------------------------------|  
|[Object.preventExtensions](../../javascript/reference/object-preventextensions-function-javascript.md)|Evet|Hayır|Hayır|  
|[Object.seal](../../javascript/reference/object-seal-function-javascript.md)|Evet|Evet|Hayır|  
|[Object.Freeze](../../javascript/reference/object-freeze-function-javascript.md)|Evet|Evet|Evet|  
  
 Aşağıdaki işlevleri return `true` aşağıdaki tabloda işaretlenmiş koşulların tümü doğruysa.  
  
|İşlev|Nesne Genişletilebilir mi?|`configurable`olan `false` tüm özelliklerinin?|`writable`olan `false` tüm veri özelliklerinin?|  
|--------------|---------------------------|---------------------------------------------------|----------------------------------------------------|  
|[Object.isExtensible](../../javascript/reference/object-isextensible-function-javascript.md)|Evet|Hayır|Hayır|  
|`Object.isSealed`|Hayır|Evet|Hayır|  
|[Object.isFrozen](../../javascript/reference/object-isfrozen-function-javascript.md)|Hayır|Evet|Evet|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `Object.isSealed` işlevi.  
  
```JavaScript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
  
// Seal the object, and verify that it is sealed.  
Object.seal(obj);  
document.write(Object.isSealed(obj));  
document.write("<br/>");  
  
// Try to add a new property, and then verify that it is not added.   
obj.newProp = 50;  
document.write(obj.newProp);  
document.write("<br/>");  
  
// Try to delete a property, and then verify that it is still present.   
delete obj.length;  
document.write(obj.length);  
  
// Output:  
// true  
// undefined  
// 10  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Object.preventExtensions işlevi](../../javascript/reference/object-preventextensions-function-javascript.md)   
 [Object.seal işlevi](../../javascript/reference/object-seal-function-javascript.md)   
 [Object.Freeze işlevi](../../javascript/reference/object-freeze-function-javascript.md)   
 [Object.isExtensible işlevi](../../javascript/reference/object-isextensible-function-javascript.md)   
 [Object.isFrozen işlevi](../../javascript/reference/object-isfrozen-function-javascript.md)   
 [Object.defineProperty işlevi](../../javascript/reference/object-defineproperty-function-javascript.md)   
 [Object.getOwnPropertyDescriptor işlevi](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)