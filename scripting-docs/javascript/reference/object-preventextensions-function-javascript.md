---
title: Object.preventExtensions işlevi (JavaScript) | Microsoft Docs
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
- properties [JavaScript], preventing new
- preventing new properties [JavaScript]
- preventExtensions function [JavaScript]
- Object.preventExtensions function [JavaScript]
ms.assetid: e6b48197-2374-4437-a9fe-519dd45a2077
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 868f917cc2249a1634194e4b2dd097e0dcbd4c08
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791846"
---
# <a name="objectpreventextensions-function-javascript"></a>Object.preventExtensions İşlevi (JavaScript)
Yeni özelliklerin eklenmesi nesneye engeller.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
Object.preventExtensions(object)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `object`  
 Gerekli. Genişletilebilir olmayan yapmak için nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlevine geçirilen nesne.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `object` bağımsız değişkeni bir nesne değil bir `TypeError` özel durumu oluşur.  
  
## <a name="remarks"></a>Açıklamalar  
 `Object.preventExtensions` İşlevi kılan bir nesne olmayan-genişletilebilir, böylece yeni adlandırılmış özellikler eklenemez. Bir nesne Genişletilebilir olmayan yapıldıktan sonra Genişletilebilir yapılamaz.  
  
 Özellik öznitelikleri ayarlama hakkında daha fazla bilgi için bkz: [Object.defineProperty işlevi](../../javascript/reference/object-defineproperty-function-javascript.md).  
  
## <a name="related-functions"></a>İlgili işlevleri  
 Aşağıdaki ilgili işlevleri nesne öznitelikleri değiştirilmesini engellemek.  
  
|İşlev|Nesne Genişletilebilir olmayan yapılır|`configurable`ayarlanmış `false` her bir özellik için|`writable`ayarlanmış `false` her bir özellik için|  
|--------------|------------------------------------|--------------------------------------------------------|----------------------------------------------------|  
|`Object.preventExtensions`|Evet|Hayır|Hayır|  
|[Object.seal](../../javascript/reference/object-seal-function-javascript.md)|Evet|Evet|Hayır|  
|[Object.Freeze](../../javascript/reference/object-freeze-function-javascript.md)|Evet|Evet|Evet|  
  
 Aşağıdaki işlevleri return `true` aşağıdaki tabloda işaretlenmiş koşulların tümü doğruysa.  
  
|İşlev|Nesne Genişletilebilir mi?|`configurable`olan `false` tüm özelliklerinin?|`writable`olan `false` tüm veri özelliklerinin?|  
|--------------|---------------------------|---------------------------------------------------|----------------------------------------------------|  
|[Object.isExtensible](../../javascript/reference/object-isextensible-function-javascript.md)|Evet|Hayır|Hayır|  
|[Object.isSealed](../../javascript/reference/object-issealed-function-javascript.md)|Hayır|Evet|Hayır|  
|[Object.isFrozen](../../javascript/reference/object-isfrozen-function-javascript.md)|Hayır|Evet|Evet|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `Object.preventExtensions` işlevi.  
  
```JavaScript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
  
// Make the object non-extensible.  
Object.preventExtensions(obj);  
document.write(Object.isExtensible(obj));  
document.write("<br/>");  
  
// Try to add a new property, and then verify that it is not added.  
obj.newProp = 50;  
document.write(obj.newProp);  
  
// Output:  
// false  
// undefined  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Object.seal işlevi](../../javascript/reference/object-seal-function-javascript.md)   
 [Object.Freeze işlevi](../../javascript/reference/object-freeze-function-javascript.md)   
 [Object.isExtensible işlevi](../../javascript/reference/object-isextensible-function-javascript.md)   
 [Object.isSealed işlevi](../../javascript/reference/object-issealed-function-javascript.md)   
 [Object.isFrozen işlevi](../../javascript/reference/object-isfrozen-function-javascript.md)