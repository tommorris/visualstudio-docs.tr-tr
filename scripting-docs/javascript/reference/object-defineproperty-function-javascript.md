---
title: "Object.defineProperty işlevi (JavaScript) | Microsoft Docs"
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
- defineProperty function [JavaScript]
- Object.defineProperty function [JavaScript]
ms.assetid: c5d05346-940a-40c2-b12a-e8b25abc8d46
caps.latest.revision: "74"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 89291f5c836f74a5dd71099328ce389a12f6fd24
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="objectdefineproperty-function-javascript"></a>Object.defineProperty İşlevi (JavaScript)
Bir özellik için bir nesne ekler veya varolan bir özellik özniteliklerini değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Object.defineProperty(object, propertyname, descriptor)  
```  
  
## <a name="parameters"></a>Parametreler  
 `object`  
 Gerekli. Nesne eklemek veya özelliği değiştirmek. Bu bir yerel olabilir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesnesi (diğer bir deyişle, kullanıcı tanımlı bir nesne veya yerleşik bir nesne) veya DOM nesnesi.  
  
 `propertyname`  
 Gerekli. Özellik adını içeren dize.  
  
 `descriptor`  
 Gerekli. Özelliği için bir tanımlayıcı. Veri özelliği veya bir erişimci özelliği için olabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Değiştirilmiş nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `Object.defineProperty` işlevi aşağıdakileri yapın:  
  
-   Yeni bir özellik için bir nesne ekleyin. Bu durum, nesne belirtilen özellik adı yok oluşur.  
  
-   Mevcut bir özellik özniteliklerini değiştirin. Bu durum, nesne belirtilen özellik adı zaten oluşur.  
  
 Özellik tanımı bir veri özellik ya da bir erişimci özelliği özniteliklerini açıklayan bir tanımlayıcı nesnesi içinde sağlanır. Tanımlayıcı nesnesi, bir parametredir `Object.defineProperty` işlevi.  
  
 Bir nesne için birden çok özellik eklemek veya birden çok mevcut özelliklerini değiştirmek için kullanabileceğiniz [Object.defineProperties işlevi](../../javascript/reference/object-defineproperties-function-javascript.md).  
  
## <a name="exceptions"></a>Özel Durumlar  
 A `TypeError` aşağıdaki koşullardan herhangi biri doğruysa, özel durum:  
  
-   `object` Bağımsız değişkeni bir nesne değil.  
  
-   Nesne değil [Genişletilebilir](../../javascript/reference/object-isextensible-function-javascript.md) ve belirtilen özellik adı yok...  
  
-   `descriptor` Sahip bir `value` veya `writable` özniteliği ve sahip bir `get` veya `set` özniteliği.  
  
-   `descriptor` Sahip bir `get` veya `set` özniteliği bir işlev değil veya tanımlanmamış.  
  
-   Belirtilen özellik adı zaten var, varolan özelliğine sahip bir `configurable` özniteliği `false`ve `descriptor` mevcut özellik kullanılanlardan farklı bir veya daha fazla öznitelikleri içerir. Ancak, mevcut özellik olduğunda bir `configurable` özniteliği `false` ve `writable` özniteliği `true`, için izin `value` veya `writable` için öznitelik farklı olmalıdır.  
  
## <a name="adding-a-data-property"></a>Veri Özelliği Ekleme  
 Aşağıdaki örnekte, `Object.defineProperty` işlevi, kullanıcı tanımlı bir nesneye bir veri özelliği ekler. Bunun yerine var olan bir DOM nesnesi özelliği eklemek için açıklamadan çıkarın `var = window.document` satır.  
  
```JavaScript  
var newLine = "<br />";  
  
// Create a user-defined object.  
var obj = {};  
  
// Add a data property to the object.  
Object.defineProperty(obj, "newDataProperty", {  
    value: 101,  
    writable: true,  
    enumerable: true,  
    configurable: true  
});  
  
// Set the property value.  
obj.newDataProperty = 102;  
document.write("Property value: " + obj.newDataProperty + newLine);  
  
// Output:  
// Property value: 102  
```  
  
 Nesne özellikleri listelemek için bu örnek için aşağıdaki kodu ekleyin.  
  
```JavaScript  
var names = Object.getOwnPropertyNames(obj);  
for (var i = 0; i < names.length; i++) {  
    var prop = names[i];  
  
    document.write(prop + ': ' + obj[prop]);  
    document.write(newLine);  
}  
  
// Output:  
//  newDataProperty: 102  
```  
  
## <a name="modifying-a-data-property"></a>Veri Özelliğini Değiştirme  
 Nesne için özellik özniteliği değiştirmek için aşağıdaki kodu ekleyin `addDataProperty` daha önce gösterilen işlevi. `descriptor` Parametre içeren yalnızca bir `writable` özniteliği. Bir veri özellik öznitelikleri aynı kalır.  
  
```JavaScript  
// Modify the writable attribute of the property.  
Object.defineProperty(obj, "newDataProperty", { writable: false });  
  
// List the property attributes by using a descriptor.  
// Get the descriptor with Object.getOwnPropertyDescriptor.  
var descriptor = Object.getOwnPropertyDescriptor(obj, "newDataProperty");  
for (var prop in descriptor) {  
    document.write(prop + ': ' + descriptor[prop]);  
    document.write(newLine);  
}  
  
// Output  
// writable: false  
// value: 102  
// configurable: true  
// enumerable: true  
```  
  
## <a name="adding-an-accessor-property"></a>Erişimci Özelliği Ekleme  
 Aşağıdaki örnekte, `Object.defineProperty` işlevi, kullanıcı tanımlı bir nesneye bir erişimci özelliği ekler.  
  
```JavaScript  
var newLine = "<br />";  
  
// Create a user-defined object.  
var obj = {};  
  
// Add an accessor property to the object.  
Object.defineProperty(obj, "newAccessorProperty", {  
    set: function (x) {  
        document.write("in property set accessor" + newLine);  
        this.newaccpropvalue = x;  
    },  
    get: function () {  
        document.write("in property get accessor" + newLine);  
        return this.newaccpropvalue;  
    },  
    enumerable: true,  
    configurable: true  
});  
  
// Set the property value.  
obj.newAccessorProperty = 30;  
document.write("Property value: " + obj.newAccessorProperty + newLine);  
  
// Output:  
// in property set accessor  
// in property get accessor  
// Property value: 30  
  
```  
  
 Nesne özellikleri listelemek için bu örnek için aşağıdaki kodu ekleyin.  
  
```JavaScript  
var names = Object.getOwnPropertyNames(obj);  
for (var i = 0; i < names.length; i++) {  
    var prop = names[i];  
  
    document.write(prop + ': ' + obj[prop]);  
    document.write(newLine);  
}  
// Output:  
// in property get accessor  
// newAccessorProperty: 30  
  
```  
  
## <a name="modifying-an-accessor-property"></a>Erişimci Özelliğini Değiştirme  
 Nesne için özellik özniteliği değiştirmek için daha önce gösterilen kodu aşağıdaki kodu ekleyin. `descriptor` Parametre içeren yalnızca bir `get` erişimci tanımı. Bir özellik öznitelikleri aynı kalır.  
  
```JavaScript  
// Modify the get accessor.  
Object.defineProperty(obj, "newAccessorProperty", {  
    get: function () { return this.newaccpropvalue; }  
});  
  
// List the property attributes by using a descriptor.  
// Get the descriptor with Object.getOwnPropertyDescriptor.  
var descriptor = Object.getOwnPropertyDescriptor(obj, "newAccessorProperty");  
for (var prop in descriptor) {  
    document.write(prop + ': ' + descriptor[prop]);  
    document.write(newLine);  
}  
  
// Output:  
// get: function () { return this.newaccpropvalue; }  
// set: function (x) { document.write("in property set accessor" + newLine); this.newaccpropvalue = x; }  
// configurable: true  
// enumerable: true  
```  
  
## <a name="modifying-a-property-on-a-dom-element"></a>Bir DOM Öğesindeki Özelliği Değiştirme  
 Aşağıdaki örnek, kullanarak yerleşik DOM özellikleri özelleştirmek gösterilmiştir `Object.getOwnPropertyDescriptor` almak ve özelliğin özellik tanımlayıcısı değiştirmek için işlevi. Bu örnekte, "div" Kimliğine sahip DIV öğesinin tarafından var. gerekir.  
  
```JavaScript  
// Get the querySelector property descriptor.  
var descriptor = Object.getOwnPropertyDescriptor(Element.prototype, "querySelector");  
  
// Make the property read-only.  
descriptor.value = "query";  
descriptor.writable = false;  
// Apply the changes to the Element prototype.  
Object.defineProperty(Element.prototype, "querySelector", descriptor);  
  
// Get a DOM element from the HTML body.  
var elem = document.getElementById("div");  
  
// Attempt to change the value. This causes the revised value attribute to be called.  
elem.querySelector = "anotherQuery";  
document.write(elem.querySelector);  
  
// Output:  
// query  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Internet Explorer 9 standartları modu ve Internet Explorer 10 standartları modu, yanı [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamaları, tüm özelliklerini destekler.  
  
 [!INCLUDE[jsv58textspecific](../../javascript/reference/includes/jsv58textspecific-md.md)]DOM nesneler, ancak kullanıcı tanımlı nesneler destekler. `enumerable` Ve `configurable` öznitelikleri belirtilebilir, ancak bunlar kullanılmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge nesne modeli prototipleri, bölüm 2: Erişimci (alıcı/ayarlayıcı) desteği](http://msdn.microsoft.com/library/dd229916\(v=VS.85\).aspx)   
 [Object.defineProperties işlevi](../../javascript/reference/object-defineproperties-function-javascript.md)   
 [Object.Create işlevi](../../javascript/reference/object-create-function-javascript.md)   
 [Object.getOwnPropertyDescriptor işlevi](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)   
 [Object.getOwnPropertyNames işlevi](../../javascript/reference/object-getownpropertynames-function-javascript.md)