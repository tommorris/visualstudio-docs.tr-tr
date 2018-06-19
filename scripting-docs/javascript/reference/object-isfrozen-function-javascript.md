---
title: Object.isFrozen işlevi (JavaScript) | Microsoft Docs
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
- isFrozen function [JavaScript]
- Object.isFrozen function [JavaScript]
ms.assetid: 6cf1bbc6-56e8-429b-8e2c-0024fa614acc
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3e1ccd11d5b4ef3b5f24dbfc8e815f0e3e156347
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792041"
---
# <a name="objectisfrozen-function-javascript"></a>Object.isFrozen İşlevi (JavaScript)
Döndürür `true` var olan özellik öznitelikleri ve değerleri, bir nesne değiştirilemez ve yeni özellikleri nesneye eklenemez.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
Object.isFrozen(object)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `object`  
 Gerekli. Sınanacak nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`Aşağıdakilerin tümü doğruysa:  
  
-   Yeni özellikler nesneye eklenemez belirten olmayan-genişletilebilir, nesnesidir.  
  
-   `configurable` Özniteliği `false` tüm var olan özellikler için.  
  
-   `writable` Özniteliği `false` tüm mevcut verileri özelliklerinin.  
  
 Nesne var olan özellik varsa, işlevi döndürür `true` nesne Genişletilebilir olmayan ise.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `object` bağımsız değişkeni bir nesne değil bir `TypeError` özel durumu oluşur.  
  
## <a name="remarks"></a>Açıklamalar  
 Zaman `configurable` özniteliği bir özellik olan `false`, özellik öznitelikleri değiştirilemez ve özellik silinemez. Zaman `writable` olan `false`, veri özellik değeri değiştirilemez. Zaman `configurable` olan `false` ve `writable` olan `true`, `value` ve `writable` öznitelikleri değiştirilebilir.  
  
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
|[Object.isSealed](../../javascript/reference/object-issealed-function-javascript.md)|Hayır|Evet|Hayır|  
|`Object.isFrozen`|Hayır|Evet|Evet|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `Object.isFrozen` işlevi.  
  
```JavaScript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
  
// Freeze the object, and verify that it is frozen.  
Object.freeze(obj);  
document.write(obj.isFrozen());  
  
// Try to add a new property, and then verify that it is not added.   
obj.newProp = 50;  
document.write (obj.newProp);  
document.write ("<br/>");  
  
// Try to delete a property, and then verify that it is still present.  
delete obj.length;  
document.write (obj.length);  
document.write ("<br/> ");  
  
// Try to change a property value, and then verify that it is not changed.  
obj.pasta = "linguini";  
document.write (obj.pasta);  
  
// Output:  
// true  
// undefined  
// 10  
// spaghetti  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Object.preventExtensions işlevi](../../javascript/reference/object-preventextensions-function-javascript.md)   
 [Object.seal işlevi](../../javascript/reference/object-seal-function-javascript.md)   
 [Object.Freeze işlevi](../../javascript/reference/object-freeze-function-javascript.md)   
 [Object.isExtensible işlevi](../../javascript/reference/object-isextensible-function-javascript.md)   
 [Object.isSealed işlevi](../../javascript/reference/object-issealed-function-javascript.md)   
 [Object.defineProperty işlevi](../../javascript/reference/object-defineproperty-function-javascript.md)   
 [Object.getOwnPropertyDescriptor işlevi](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)   
 [Object.getOwnPropertyNames işlevi](../../javascript/reference/object-getownpropertynames-function-javascript.md)