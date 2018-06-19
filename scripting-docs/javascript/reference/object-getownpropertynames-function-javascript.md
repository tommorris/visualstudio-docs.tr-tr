---
title: Object.getOwnPropertyNames işlevi (JavaScript) | Microsoft Docs
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
- getOwnPropertyNames method [JavaScript]
- Object.getOwnPropertyNames method [JavaScript]
ms.assetid: 59f4b6b1-02be-44b3-a06c-a5ca8f70c3d8
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 76ca0036b9dedf7b4cee7b543469939e35dfe8d1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791489"
---
# <a name="objectgetownpropertynames-function-javascript"></a>Object.getOwnPropertyNames İşlevi (JavaScript)
Bir nesnenin kendi özellik adlarını döndürür. Bir nesnenin kendi özelliklerini doğrudan nesnede tanımlanır ve nesnenin prototip devralınmaz izinlerdir. Bir nesnenin özelliklerini alanları (nesneler) ve işlevler içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
Object.getOwnPropertyNames(object)  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Tanım|  
|---------------|----------------|  
|`object`|Gerekli. Kendi özellikleri içeren nesne.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 Nesnenin kendi özellik adlarını içeren bir dizi.  
  
## <a name="exceptions"></a>Özel Durumlar  
 İçin değer belirttiğinizde `object` bağımsız değişkeni bir nesne adı değil bir `TypeError` özel durumu oluşur.  
  
## <a name="remarks"></a>Açıklamalar  
 `getOwnPropertyNames` Yöntemi numaralandırılabilir ve numaralandırılabilir olmayan özellikleri ve yöntemleri adlarını döndürür. Yalnızca numaralandırılabilir özellikleri ve yöntemleri adlarını döndürmek için kullanabileceğiniz [Object.keys işlevi](../../javascript/reference/object-keys-function-javascript.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, üç özellik ve yöntemi sahip bir nesne oluşturur. Daha sonra kullanır `getOwnPropertyNames` (yöntemi dahil) kendi nesnenin özelliklerini elde etmek için yöntemi.  
  
```JavaScript  
function Pasta(grain, width, shape) {  
    // Define properties.  
    this.grain = grain;  
    this.width = width;  
    this.shape = shape;  
    this.toString = function () {  
        return (this.grain + ", " + this.width + ", " + this.shape);  
    }  
}  
  
// Create an object.  
var spaghetti = new Pasta("wheat", 0.2, "circle");  
  
// Get the own property names.  
var arr = Object.getOwnPropertyNames(spaghetti);  
document.write (arr);  
  
// Output:  
//   grain,width,shape,toString  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek harfle 's başlangıç özellik adlarını görüntüler ' ın bir **spaghetti** nesne oluşturulan ile **bellek** Oluşturucusu.  
  
```JavaScript  
function Pasta(grain, size, shape) {  
    this.grain = grain;   
    this.size = size;   
    this.shape = shape;   
}  
  
var spaghetti = new Pasta("wheat", 2, "circle");  
  
var names = Object.getOwnPropertyNames(spaghetti).filter(CheckKey);  
document.write(names);   
  
// Check whether the first character of a string is 's'.   
function CheckKey(value) {  
    var firstChar = value.substr(0, 1);   
    if (firstChar.toLowerCase() == 's')  
        return true;   
    else  
         return false;   
}  
// Output:  
// size,shape  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Object.Keys işlevi](../../javascript/reference/object-keys-function-javascript.md)