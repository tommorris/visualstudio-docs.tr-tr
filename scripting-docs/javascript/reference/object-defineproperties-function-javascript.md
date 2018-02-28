---
title: "Object.defineProperties işlevi (JavaScript) | Microsoft Docs"
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
- Object.defineProperties function [JavaScript]
ms.assetid: 2dae6658-a1c9-495f-bf06-bb3e964e6762
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 65f4f5817a105283a26c971bd98869d000ca0bc2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="objectdefineproperties-function-javascript"></a>Object.defineProperties İşlevi (JavaScript)
Bir veya daha fazla özellikleri bir nesne ekler ve/veya var olan özellikleri özniteliklerini değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
object.defineProperties(object, descriptors)  
```  
  
## <a name="parameters"></a>Parametreler  
 `object`  
 Gerekli. Nesne eklemek veya özellikleri değiştirmek. Bu bir yerel olabilir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesnesi veya DOM nesnesi.  
  
 `descriptors`  
 Gerekli. A [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] bir veya daha fazla tanımlayıcı nesnesini içeren nesne. Her tanımlayıcı nesnesi bir veri özellik ya da bir erişimci özelliği açıklar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlevine geçirilen nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 `descriptors` Bağımsız değişkeni olan bir veya daha fazla tanımlayıcı nesneleri içeren bir nesne.  
  
 A *veri özelliği* depolamak ve bir değer almak bir özelliktir. Veri özellik tanımlayıcısını içeren bir `value` öznitelik, bir `writable` özniteliği ya da her ikisini de. Daha fazla bilgi için bkz: [veri özellikleri ve erişimci özellikleri](../../javascript/advanced/data-properties-and-accessor-properties.md).  
  
 Bir *erişimci özelliği* özellik değerini ayarlayın ya da alınan her zaman bir kullanıcı tarafından sağlanan işlevi çağırır. Erişimci özellik tanımlayıcısını içeren bir `set` öznitelik, bir `get` özniteliği ya da her ikisini de.  
  
 Nesne zaten belirtilen ada sahip bir özellik varsa, özellik öznitelikleri değiştirilmiştir. Daha fazla bilgi için bkz: [Object.defineProperty işlevi](../../javascript/reference/object-defineproperty-function-javascript.md).  
  
 Bir nesne oluşturmak ve yeni nesne için özellikler eklemek için kullanabileceğiniz [Object.create işlevi](../../javascript/reference/object-create-function-javascript.md).  
  
## <a name="adding-properties"></a>Özellikler Ekleme  
 Aşağıdaki örnekte, `Object.defineProperties` işlevi, kullanıcı tanımlı bir nesneye bir veri özelliği ile bir erişimci özelliği ekler.  
  
 Örnek değişmez değer bir nesne oluşturmak için kullanır. `descriptors` nesnesi ile `newDataProperty` ve `newAccessorProperty` tanımlayıcısı nesneleri.  
  
```JavaScript  
var newLine = "<br />";  
  
var obj = {};  
Object.defineProperties(obj, {  
    newDataProperty: {  
        value: 101,  
        writable: true,  
        enumerable: true,  
        configurable: true  
    },  
    newAccessorProperty: {  
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
    }});  
  
// Set the accessor property value.  
obj.newAccessorProperty = 10;  
document.write ("newAccessorProperty value: " + obj.newAccessorProperty + newLine);  
  
// Output:  
// in property set accessor  
// in property get accessor  
// newAccessorProperty value: 10  
  
```  
  
 Daha önceki örnekteki gibi aşağıdaki örnekte özelliklerini dinamik olarak yerine değişmez değer bir nesne ekler.  
  
```JavaScript  
  
var newLine = "<br />";  
  
// Create the descriptors object.  
var descriptors = new Object();  
  
// Add a data property descriptor to the descriptors object.  
descriptors.newDataProperty = new Object();  
descriptors.newDataProperty.value = 101;  
descriptors.newDataProperty.writable = true;  
descriptors.newDataProperty.enumerable = true;  
descriptors.newDataProperty.configurable = true;  
  
// Add an accessor property descriptor to the descriptors object.  
descriptors.newAccessorProperty = new Object();  
descriptors.newAccessorProperty.set = function (x) {  
    document.write("in property set accessor" + newLine);  
    this.newaccpropvalue = x;  
};  
descriptors.newAccessorProperty.get = function () {  
    document.write("in property get accessor" + newLine);  
    return this.newaccpropvalue;  
};  
descriptors.newAccessorProperty.enumerable = true;  
descriptors.newAccessorProperty.configurable = true;  
  
// Call the Object.defineProperties function.  
var obj = new Object();  
Object.defineProperties(obj, descriptors);  
  
// Set the accessor property value.  
obj.newAccessorProperty = 10;  
document.write ("newAccessorProperty value: " + obj.newAccessorProperty + newLine);  
  
// Output:  
// in property set accessor  
// in property get accessor  
// newAccessorProperty value: 10  
  
```  
  
## <a name="modifying-properties"></a>Özellikleri Değiştirme  
 Nesne için özellik öznitelikleri değiştirmek için aşağıdaki kodu ekleyin. `Object.defineProperties` İşlevi değiştirir `writable` özniteliği `newDataProperty`ve değiştirir `enumerable` özniteliği `newAccessorProperty`. Ekler `anotherDataProperty` nesnesine bu özellik adı zaten var olmadığından.  
  
```  
Object.defineProperties(obj, {  
    newDataProperty: { writable: false },  
    newAccessorProperty: { enumerable: false },  
    anotherDataProperty: { value: "abc" }  
});  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Internet Explorer 9 standartları, Internet Explorer 10 standartları desteklenen ve [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar. Internet Explorer aksi desteklenmiyor 8'de yalnızca DOM nesneleri için desteklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Object.getOwnPropertyDescriptor işlevi](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)   
 [Object.getOwnPropertyNames işlevi](../../javascript/reference/object-getownpropertynames-function-javascript.md)   
 [Object.defineProperty işlevi](../../javascript/reference/object-defineproperty-function-javascript.md)   
 [Object.Create işlevi](../../javascript/reference/object-create-function-javascript.md)   
 [Nesne nesnesi](../../javascript/reference/object-object-javascript.md)