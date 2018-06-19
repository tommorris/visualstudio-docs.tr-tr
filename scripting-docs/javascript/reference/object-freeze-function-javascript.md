---
title: Object.Freeze işlevi (JavaScript) | Microsoft Docs
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
- Object.freeze function
- freeze function
ms.assetid: 83ffe193-0a37-4e0c-9b66-44c422765fb3
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ec08b34c3c8b32245928e6e75f5df1fbdfe2d4a6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792074"
---
# <a name="objectfreeze-function-javascript"></a>Object.freeze İşlevi (JavaScript)
Var olan özellik öznitelikleri ve değerleri değiştirilmesini ve yeni özellikleri eklenmesini engeller.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
Object.freeze(object)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `object`  
 Gerekli. Nesne öznitelikleri kilitlenemiyor.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlevine geçirilen nesne.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `object` bağımsız değişkeni bir nesne değil bir `TypeError` özel durumu oluşur.  
  
## <a name="remarks"></a>Açıklamalar  
 `Object.freeze` İşlevi aşağıdakileri yapar:  
  
-   Nesne olmayan-genişletilebilir, yapar ve böylece yeni özellikler eklenemez.  
  
-   Ayarlar `configurable` özniteliğini `false` nesnenin tüm özelliklerinin. Zaman `configurable` olan `false`, özellik öznitelikleri değiştirilemez ve özellik silinemez.  
  
-   Ayarlar `writable` özniteliğini `false` nesnesinin tüm veri özellikleri için. Zaman `writable` yanlış veri özellik değeri değiştirilemez.  
  
 Özellik öznitelikleri ayarlama hakkında daha fazla bilgi için bkz: [Object.defineProperty işlevi](../../javascript/reference/object-defineproperty-function-javascript.md). Bir özellik özniteliklerini elde etmek için kullanabileceğiniz [Object.getOwnPropertyDescriptor işlevi](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md).  
  
## <a name="related-functions"></a>İlgili işlevleri  
 Aşağıdaki ilgili işlevleri nesne öznitelikleri değiştirilmesini engellemek.  
  
|İşlev|Nesne Genişletilebilir olmayan yapılır|`configurable`ayarlanmış `false` her bir özellik için|`writable`ayarlanmış `false` her bir özellik için|  
|--------------|------------------------------------|--------------------------------------------------------|----------------------------------------------------|  
|[Object.preventExtensions](../../javascript/reference/object-preventextensions-function-javascript.md)|Evet|Hayır|Hayır|  
|[Object.seal](../../javascript/reference/object-seal-function-javascript.md)|Evet|Evet|Hayır|  
|`Object.freeze`|Evet|Evet|Evet|  
  
 Aşağıdaki işlevleri return `true` aşağıdaki tabloda işaretlenmiş koşulların tümü doğruysa.  
  
|İşlev|Nesne Genişletilebilir mi?|`configurable`olan `false` tüm özelliklerinin?|`writable`olan `false` tüm veri özelliklerinin?|  
|--------------|---------------------------|---------------------------------------------------|----------------------------------------------------|  
|[Object.isExtensible](../../javascript/reference/object-isextensible-function-javascript.md)|Evet|Hayır|Hayır|  
|[Object.isSealed](../../javascript/reference/object-issealed-function-javascript.md)|Hayır|Evet|Evet|  
|[Object.isFrozen](../../javascript/reference/object-isfrozen-function-javascript.md)|Hayır|Evet|Evet|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `Object.freeze` işlevi.  
  
```JavaScript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
  
// Freeze the object.  
Object.freeze(obj);  
  
// Try to add a new property, and then verify that it is not added.   
    obj.newProp = 50;  
    document.write(obj.newProp);  
    document.write("<br/>");  
  
// Try to delete a property, and then verify that it is still present.   
delete obj.length;  
document.write(obj.length);  
document.write("<br/>");  
  
// Try to change a property value, and then verify that it is not changed.   
obj.pasta = "linguini";  
document.write(obj.pasta);  
  
// Output:  
// undefined  
// 10  
// spaghetti  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Object.preventExtensions işlevi](../../javascript/reference/object-preventextensions-function-javascript.md)   
 [Object.seal işlevi](../../javascript/reference/object-seal-function-javascript.md)   
 [Object.isExtensible işlevi](../../javascript/reference/object-isextensible-function-javascript.md)   
 [Object.isSealed işlevi](../../javascript/reference/object-issealed-function-javascript.md)   
 [Object.isFrozen işlevi](../../javascript/reference/object-isfrozen-function-javascript.md)