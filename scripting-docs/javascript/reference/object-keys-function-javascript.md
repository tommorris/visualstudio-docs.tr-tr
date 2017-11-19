---
title: "Object.Keys işlevi (JavaScript) | Microsoft Docs"
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
- Object.keys method [JavaScript]
- keys method [JavaScript]
ms.assetid: cf4a7daf-cf28-4467-bc6b-f7f106ec3876
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0e725c3ab7206b04d9a900cb614b57c37dfc4351
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="objectkeys-function-javascript"></a>Object.keys İşlevi (JavaScript)
Numaralandırılabilir özellik adlarını ve bir yöntemlerinden birini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
Object.keys(object)  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Tanım|  
|---------------|----------------|  
|`object`|Gerekli. Özellikleri ve yöntemleri içeren nesne. Bu, oluşturduğunuz bir nesne veya varolan bir belge nesne modeli (DOM) nesne olabilir.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 Numaralandırılabilir özellik adlarını ve yöntemlerinden birini içeren bir dizi.  
  
## <a name="exceptions"></a>Özel Durumlar  
 İçin değer belirttiğinizde `object` bağımsız değişkeni bir nesne adı değil bir `TypeError` özel durumu oluşur.  
  
## <a name="remarks"></a>Açıklamalar  
 `keys` Yöntemi yalnızca numaralandırılabilir özellikleri ve yöntemleri adlarını döndürür. Numaralandırılabilir ve numaralandırılabilir olmayan özellikleri ve yöntemleri adlarını döndürmek için kullanabileceğiniz [Object.getOwnPropertyNames işlevi](../../javascript/reference/object-getownpropertynames-function-javascript.md).  
  
 Hakkında bilgi için `enumerable` özniteliği bir özelliği, bkz: [Object.defineProperty işlevi](../../javascript/reference/object-defineproperty-function-javascript.md) ve [Object.getOwnPropertyDescriptor işlevi](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, üç özellik ve yöntemi sahip bir nesne oluşturur. Daha sonra kullanır `keys` özellikleri ve yöntemleri nesnenin almak için yöntemi.  
  
```JavaScript  
// Create a constructor function.  
function Pasta(grain, width, shape) {  
    this.grain = grain;  
    this.width = width;  
    this.shape = shape;  
  
    // Define a method.  
    this.toString = function () {  
        return (this.grain + ", " + this.width + ", " + this.shape);  
    }  
}  
  
// Create an object.  
var spaghetti = new Pasta("wheat", 0.2, "circle");  
  
// Put the enumerable properties and methods of the object in an array.  
var arr = Object.keys(spaghetti);  
document.write (arr);  
  
// Output:  
// grain,width,shape,toString  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bellek nesnedeki "g" harfiyle başlayan tüm numaralandırılabilir özellik adlarını görüntüler.  
  
```JavaScript  
// Create a constructor function.  
function Pasta(grain, width, shape) {  
    this.grain = grain;  
    this.width = width;  
    this.shape = shape;  
}  
  
var polenta = new Pasta("corn", 1, "mush");  
  
var keys = Object.keys(polenta).filter(CheckKey);  
document.write(keys);  
  
// Check whether the first character of a string is "g".  
function CheckKey(value) {  
    var firstChar = value.substr(0, 1);  
    if (firstChar.toLowerCase() == "g")  
        return true;  
    else  
        return false;  
}  
  
// Output:  
// grain  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Object.getOwnPropertyNames işlevi](../../javascript/reference/object-getownpropertynames-function-javascript.md)