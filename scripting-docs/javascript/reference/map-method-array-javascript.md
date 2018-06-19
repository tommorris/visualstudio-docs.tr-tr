---
title: map yöntemi (dizi) (JavaScript) | Microsoft Docs
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
- map method [JavaScript]
- arrays [JavaScript], map method
ms.assetid: 500dc4f8-d73d-4a28-a5b8-c9bd5674ea36
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 609d9c88000a7a30fe8edc03b52df032f7d19ba9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791765"
---
# <a name="map-method-array-javascript"></a>map Yöntemi (Dizi) (JavaScript)
Bir dizideki her öğe için tanımlı geri çağırma işlevini çağırır ve sonuçları içeren bir dize döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
array1.map(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Tanım|  
|---------------|----------------|  
|`array1`|Gerekli. Bir dizi nesnesi.|  
|`callbackfn`|Gerekli. En fazla üç bağımsız değişkeni kabul eden bir işlev. `map` Yöntem çağrılarını `callbackfn` işlev dizideki her öğe için bir kez.|  
|`thisArg`|İsteğe bağlı. Bir nesneye `this` anahtar sözcüğü başvurabilir `callbackfn` işlevi. Varsa `thisArg` atlanırsa, `undefined` olarak kullanılan `this` değeri.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 Her öğenin, ilişkili özgün dizi öğesi için geri çağırma işlevi dönüş değeri olduğu yeni bir dizi.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `callbackfn` bağımsız değişkeni bir işlev nesnesi değil bir `TypeError` özel durumu oluşur.  
  
## <a name="remarks"></a>Açıklamalar  
 `map` Yöntem çağrılarını `callbackfn` işlev dizin artan dizideki her öğe için bir kez. Geri çağırma işlevi, dizinin eksik öğeleri için çağrılmaz.  
  
 Array nesneleri yanı sıra `map` yöntemi olan herhangi bir nesne tarafından kullanılabilecek bir `length` özelliği ve, sayısal olarak dizin oluşturulmuş özellik adları.  
  
## <a name="callback-function-syntax"></a>Geri Çağırma İşlevi Sözdizimi  
 Geri çağırma işlevinin sözdizimi aşağıdaki gibidir:  
  
 `function callbackfn(value, index, array1)`  
  
 En çok üç parametre kullanarak geri çağırma işlevini bildirebilirsiniz.  
  
 Geri çağırma işlevi parametreleri aşağıdaki tabloda listelenmektedir.  
  
|Geri çağırma bağımsız değişkeni|Tanım|  
|-----------------------|----------------|  
|`value`|Dizi öğesinin değeri.|  
|`index`|Dizi öğesinin sayısal dizini.|  
|`array1`|Öğeyi içeren dizi nesnesi.|  
  
## <a name="modifying-the-array-object"></a>Dizi Nesnesini Değiştirme  
 Dizi nesnesi, geri çağırma işlevi tarafından değiştirilebilir.  
  
 Sonra dizi nesnesi değiştirme işleminin sonuçları aşağıdaki tabloda açıklanmıştır `map` yöntemi başlatır.  
  
|Sonra koşul `map` yöntemi başlatır|Geri çağırma işlevine öğe aktarıldı mı?|  
|---------------------------------------------|------------------------------------------|  
|Öğe, dizinin özgün uzunluğunun ardından eklenir.|Hayır.|  
|Öğe, dizinin eksik bir öğesini tamamlamak için eklenir.|Evet, o dizin henüz geri çağırma işlevine aktarılmadıysa.|  
|Öğe değiştirildi.|Evet, o öğe henüz geri çağırma işlevine aktarılmadıysa.|  
|Öğe diziden silindi.|Hayır, o öğe henüz geri çağırma işlevine aktarılmadıysa.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `map` yöntemi.  
  
```JavaScript  
// Define the callback function.  
function AreaOfCircle(radius) {  
    var area = Math.PI * (radius * radius);  
    return area.toFixed(0);  
}  
  
// Create an array.  
var radii = [10, 20, 30];  
  
// Get the areas from the radii.  
var areas = radii.map(AreaOfCircle);  
  
document.write(areas);  
  
// Output:  
// 314,1257,2827  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `thisArg` bir nesneye belirtir bağımsız değişkeni `this` anahtar sözcüğü başvurabilir.  
  
```JavaScript  
// Define an object that contains a divisor property and  
// a remainder function.  
var obj = {  
    divisor: 10,  
    remainder: function (value) {  
        return value % this.divisor;  
    }  
}  
  
// Create an array.  
var numbers = [6, 12, 25, 30];  
  
// Get the remainders.  
// The obj argument specifies the this value in the callback function.  
var result = numbers.map(obj.remainder, obj);  
document.write(result);  
  
// Output:  
// 6,2,5,0  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, bir yerleşik[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] yöntemi geri çağırma işlevi kullanılır.  
  
```JavaScript  
// Apply Math.sqrt(value) to each element in an array.  
var numbers = [9, 16];  
var result = numbers.map(Math.sqrt);  
  
document.write(result);  
// Output: 3,4  
```  
  
## <a name="example"></a>Örnek  
 `map` Yöntemi bir dizeye uygulanabilir. Aşağıdaki örnek bunu göstermektedir.  
  
```JavaScript  
// Define the callback function.  
function threeChars(value, index, str) {  
    // Create a string that contains the previous, current,  
    // and next character.  
    return str.substring(index - 1, index + 2);  
}  
  
// Create a string.  
var word = "Thursday";  
  
// Apply the map method to the string.  
// Each array element in the result contains a string that  
// has the previous, current, and next character.  
// The commented out statement shows an alternative syntax.  
var result = [].map.call(word, threeChars);  
// var result = Array.prototype.map.call(word, threeChars);  
  
document.write(result);  
  
// Output:  
// Th,Thu,hur,urs,rsd,sda,day,ay  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript yöntemleri](../../javascript/reference/javascript-methods.md)   
 [Dizi nesnesi](../../javascript/reference/array-object-javascript.md)   
 [Dizileri kullanma](../../javascript/advanced/using-arrays-javascript.md)   
 [filter yöntemi (dizi)](../../javascript/reference/filter-method-array-javascript.md)   
 [forEach yöntemi (dizi)](../../javascript/reference/foreach-method-array-javascript.md)   
 [Hilo JavaScript örnek uygulama (Windows mağazası)](http://hilojs.codeplex.com/SourceControl/latest)