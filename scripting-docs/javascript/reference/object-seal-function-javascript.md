---
title: "Object.seal işlevi (JavaScript) | Microsoft Docs"
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
- Object.seal function
- seal function
ms.assetid: e72c804a-4dab-4ec9-b9df-9c9c908aa12d
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2dca9066be9a557b97a52ae749cecfb218504509
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="objectseal-function-javascript"></a>Object.seal İşlevi (JavaScript)
Var olan özellikleri özniteliklerini değiştirme ve yeni özellikleri eklenmesini engeller.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
Object.seal(object)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `object`  
 Gerekli. Nesne öznitelikleri kilitlenemiyor.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlevine geçirilen nesne.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `object` bağımsız değişkeni bir nesne değil bir `TypeError` özel durumu oluşur.  
  
## <a name="remarks"></a>Açıklamalar  
 `Object.seal` İşlevi şunların ikisini de yapar:  
  
-   Nesne olmayan-genişletilebilir, yapar ve böylece yeni özellikler eklenemez.  
  
-   Ayarlar `configurable` özniteliğini `false` nesnenin tüm özelliklerinin.  
  
 Zaman `configurable` özniteliği `false`, özellik öznitelikleri değiştirilemez ve özellik silinemez. Zaman `configurable` olan `false` ve `writable` olan `true`, `value` ve `writable` öznitelikleri değiştirilebilir.  
  
 `Object.seal` İşlevi değiştirmez `writable` özniteliği.  
  
 Özellik öznitelikleri ayarlama hakkında daha fazla bilgi için bkz: [Object.defineProperty işlevi](../../javascript/reference/object-defineproperty-function-javascript.md). Bir özellik özniteliklerini almak için kullanabileceğiniz [Object.getOwnPropertyDescriptor işlevi](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md).  
  
## <a name="related-functions"></a>İlgili işlevleri  
 Aşağıdaki ilgili işlevleri nesne öznitelikleri değiştirilmesini engellemek.  
  
|İşlev|Nesne Genişletilebilir olmayan yapılır|`configurable`ayarlanmış `false` her bir özellik için|`writable`ayarlanmış `false` her bir özellik için|  
|--------------|------------------------------------|--------------------------------------------------------|----------------------------------------------------|  
|[Object.preventExtensions](../../javascript/reference/object-preventextensions-function-javascript.md)|Evet|Hayır|Hayır|  
|`Object.seal`|Evet|Evet|Hayır|  
|[Object.Freeze](../../javascript/reference/object-freeze-function-javascript.md)|Evet|Evet|Evet|  
  
 Aşağıdaki işlevleri return `true` aşağıdaki tabloda işaretlenmiş koşulların tümü doğruysa.  
  
|İşlev|Nesne Genişletilebilir mi?|`configurable`olan `false` tüm özelliklerinin?|`writable`olan `false` tüm veri özelliklerinin?|  
|--------------|---------------------------|---------------------------------------------------|----------------------------------------------------|  
|[Object.isExtensible](../../javascript/reference/object-isextensible-function-javascript.md)|Evet|Hayır|Hayır|  
|[Object.isSealed](../../javascript/reference/object-issealed-function-javascript.md)|Hayır|Evet|Hayır|  
|[Object.isFrozen](../../javascript/reference/object-isfrozen-function-javascript.md)|Hayır|Evet|Evet|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `Object.seal` işlevi.  
  
```JavaScript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
// Seal the object.  
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
 [Object.Freeze işlevi](../../javascript/reference/object-freeze-function-javascript.md)   
 [Object.isExtensible işlevi](../../javascript/reference/object-isextensible-function-javascript.md)   
 [Object.isSealed işlevi](../../javascript/reference/object-issealed-function-javascript.md)   
 [Object.isFrozen işlevi](../../javascript/reference/object-isfrozen-function-javascript.md)