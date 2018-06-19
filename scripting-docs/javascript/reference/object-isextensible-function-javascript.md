---
title: Object.isExtensible işlevi (JavaScript) | Microsoft Docs
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
- Object.isExtensible function [JavaScript]
- isExtensible function [JavaScript]
ms.assetid: a7d10beb-0d01-4e2d-8263-59ff07ac4352
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f88a61917811a5c6b5583e6c30539efc682296df
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791843"
---
# <a name="objectisextensible-function-javascript"></a>Object.isExtensible İşlevi (JavaScript)
Bir nesne için yeni özellikler eklenebilir olup olmadığını belirten bir değer döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
Object.isExtensible(object)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `object`  
 Gerekli. Sınanacak nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`Nesne genişletilebilir, nesneye yeni özellikler eklenebilir gösterir; Aksi takdirde `false`.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `object` bağımsız değişkeni bir nesne değil bir `TypeError` özel durumu oluşur.  
  
## <a name="remarks"></a>Açıklamalar  
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
|`Object.isExtensible`|Evet|Hayır|Hayır|  
|[Object.isSealed](../../javascript/reference/object-issealed-function-javascript.md)|Hayır|Evet|Hayır|  
|[Object.isFrozen](../../javascript/reference/object-isfrozen-function-javascript.md)|Hayır|Evet|Evet|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `Object.isExtensible` işlevi.  
  
```JavaScript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
  
// Make the object non-extensible.  
Object.preventExtensions(obj);  
  
// Try to add a new property, and then verify that it is not added.  
obj.newProp = 50;  
document.write(obj.newProp);  
  
// Output:  
undefined  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Object.preventExtensions işlevi](../../javascript/reference/object-preventextensions-function-javascript.md)   
 [Object.seal işlevi](../../javascript/reference/object-seal-function-javascript.md)   
 [Object.Freeze işlevi](../../javascript/reference/object-freeze-function-javascript.md)   
 [Object.isSealed işlevi](../../javascript/reference/object-issealed-function-javascript.md)   
 [Object.isFrozen işlevi](../../javascript/reference/object-isfrozen-function-javascript.md)