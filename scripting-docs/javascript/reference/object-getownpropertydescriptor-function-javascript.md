---
title: "Object.getOwnPropertyDescriptor işlevi (JavaScript) | Microsoft Docs"
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
helpviewer_keywords:
- getOwnPropertyDescriptor method [JavaScript]
ms.assetid: 8f0e1c90-c4f9-44c4-bf76-726bacecbc14
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd147d567fc4d8a39d7a251d55772c40518e7a26
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="objectgetownpropertydescriptor-function-javascript"></a>Object.getOwnPropertyDescriptor İşlevi (JavaScript)
Belirtilen nesnenin kendi özellik tanımlayıcı alır. Kendi özellik tanımlayıcısı, doğrudan nesnede tanımlanır ve nesnenin prototip alınmadı biridir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Object.getOwnPropertyDescriptor(object, propertyname)  
```  
  
## <a name="parameters"></a>Parametreler  
 `object`  
 Gerekli. Özellik içeren nesne.  
  
 `propertyname`  
 Gerekli. Özelliğin adı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Özellik tanımlayıcısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `Object.getOwnPropertyDescriptor` işlevi özelliği özniteliklerini açıklayan bir tanımlayıcı nesnesini alın.  
  
 [Object.defineProperty işlevi](../../javascript/reference/object-defineproperty-function-javascript.md) eklemek veya özellikleri değiştirmek için kullanılır.  
  
## <a name="data-property-example"></a>Veri Özelliği Örneği  
 Aşağıdaki örnek veri özellik tanımlayıcısını alır ve özelliği salt okunur duruma getirmek için kullanır.  
  
```JavaScript  
// Create a user-defined object.  
var obj = {};  
  
// Add a data property.  
obj.newDataProperty = "abc";  
  
// Get the property descriptor.  
var descriptor = Object.getOwnPropertyDescriptor(obj, "newDataProperty");  
  
// Change a property attribute.  
descriptor.writable = false;  
Object.defineProperty(obj, "newDataProperty", descriptor);  
  
```  
  
 Özellik öznitelikleri listelemek için bu örnek için aşağıdaki kodu ekleyebilirsiniz.  
  
```JavaScript  
// Get the descriptor from the object.  
var desc2 = Object.getOwnPropertyDescriptor(obj, "newDataProperty");  
  
// List the descriptor attributes.  
for (var prop in desc2) {  
    document.write(prop + ': ' + desc2[prop]);  
    document.write("<br />");  
}  
  
// Output:  
// value: abc  
// writable: false  
// enumerable: true  
// configurable: true  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Tüm özellikleri desteklenen [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)].  
  
 [!INCLUDE[jsv58textspecific](../../javascript/reference/includes/jsv58textspecific-md.md)]DOM nesneler, ancak kullanıcı tanımlı nesneler destekler. `enumerable` Ve `configurable` öznitelikleri belirtilebilir, ancak bunlar kullanılmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge nesne modeli prototipleri, bölüm 2: Erişimci (alıcı/ayarlayıcı) desteği](http://msdn.microsoft.com/library/dd229916\(v=VS.85\).aspx)   
 [Object.defineProperty işlevi](../../javascript/reference/object-defineproperty-function-javascript.md)