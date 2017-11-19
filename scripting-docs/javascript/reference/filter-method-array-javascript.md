---
title: "filter yöntemi (dizi) (JavaScript) | Microsoft Docs"
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
- arrays [JavaScript], filter method
- filter method [JavaScript]
ms.assetid: 1d260370-9e6e-43fc-870f-2d35850db7ee
caps.latest.revision: "32"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 33a08fdba38de558dabc749a634fb9b69c52c98a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="filter-method-array-javascript"></a>filter Yöntemi (Dizi) (JavaScript)
Bir geri çağırma fonksiyonu içinde belirtilen koşulu karşılayan bir dizi öğelerini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
array1.filter(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Tanım|  
|---------------|----------------|  
|`array1`|Gerekli. Bir dizi nesnesi.|  
|`callbackfn`|Gerekli. En fazla üç bağımsız değişkeni kabul eden bir işlev. `filter` Yöntem çağrılarını `callbackfn` işlev dizideki her öğe için bir kez.|  
|`thisArg`|İsteğe bağlı. Bir nesneye `this` anahtar sözcüğü başvurabilir `callbackfn` işlevi. Varsa `thisArg` atlanırsa, `undefined` olarak kullanılan `this` değeri.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geri çağırma işlevi döndüğü tüm değerleri içeren yeni bir dizi `true`. Geri çağırma işlevi döndürürse `false` tüm öğeler için `array1`, yeni bir dizi uzunluğu 0'dır.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `callbackfn` bağımsız değişkeni bir işlev nesnesi değil bir `TypeError` özel durumu oluşur.  
  
## <a name="remarks"></a>Açıklamalar  
 `filter` Yöntem çağrılarını `callbackfn` işlev dizin artan dizideki her öğe için bir kez. Geri çağırma işlevi, dizinin eksik öğeleri için çağrılmaz.  
  
 Array nesneleri yanı sıra `filter` yöntemi olan herhangi bir nesne tarafından kullanılabilecek bir `length` özelliği ve, sayısal olarak dizin oluşturulmuş özellik adları.  
  
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
 `filter` Yöntemi doğrudan değişiklik orijinal array, ancak geri çağırma işlevini değiştirmek. Sonra dizi nesnesi değiştirme işleminin sonuçları aşağıdaki tabloda açıklanmıştır `filter` yöntemi başlatır.  
  
|Sonra koşul `filter` yöntemi başlatır|Geri çağırma işlevine öğe aktarıldı mı?|  
|------------------------------------------------|------------------------------------------|  
|Öğe, dizinin özgün uzunluğunun ardından eklenir.|Hayır.|  
|Öğe, dizinin eksik bir öğesini tamamlamak için eklenir.|Evet, o dizin henüz geri çağırma işlevine aktarılmadıysa.|  
|Öğe değiştirildi.|Evet, o öğe henüz geri çağırma işlevine aktarılmadıysa.|  
|Öğe diziden silindi.|Hayır, o öğe henüz geri çağırma işlevine aktarılmadıysa.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `filter` yöntemi.  
  
```JavaScript  
// Define a callback function.  
function CheckIfPrime(value, index, ar) {  
    high = Math.floor(Math.sqrt(value)) + 1;  
  
    for (var div = 2; div <= high; div++) {  
        if (value % div == 0) {  
            return false;  
        }  
    }   
    return true;  
}  
  
// Create the original array.  
var numbers = [31, 33, 35, 37, 39, 41, 43, 45, 47, 49, 51, 53];  
  
// Get the prime numbers that are in the original array.   
var primes = numbers.filter(CheckIfPrime);  
  
document.write(primes);  
// Output: 31,37,41,43,47,53  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, `callbackfn` bağımsız değişkeni geri çağırma işlevi kodunu içerir.  
  
```JavaScript  
// Create the original array.  
var arr = [5, "element", 10, "the", true];  
  
// Create an array that contains the string  
// values that are in the original array.  
var result = arr.filter(  
    function (value) {  
        return (typeof value === 'string');  
    }  
);  
  
document.write(result);  
// Output: element, the  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek "css" harfiyle başlayan özellik adlarını görüntüler `window` DOM nesnesi.  
  
```JavaScript  
var filteredNames = Object.getOwnPropertyNames(window).filter(IsC);  
  
    for (i in filteredNames)  
        document.write(filteredNames[i] + "<br/>");  
  
// Check whether the string starts with "css".  
function IsC(value) {  
    var firstChar = value.substr(0, 3);  
    if (firstChar.toLowerCase() == "css")  
        return true;  
    else  
        return false;  
    }  
  
// Output:  
// CSSRule  
// CSSFontFaceRule  
// CSSImportRule  
// CSSMediaRule  
// CSSNamespaceRule  
// CSSPageRule  
// CSSRuleList  
// CSSStyleDeclaration  
// CSSStyleRule  
// CSSStyleSheet  
  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `thisArg` bir nesneye belirtir bağımsız değişkeni `this` anahtar sözcüğü başvurabilir.  
  
```JavaScript  
var checkNumericRange = function(value) {  
    if (typeof value !== 'number')  
        return false;  
    else   
        return value >= this.minimum && value <= this.maximum;  
}  
  
var numbers = [6, 12, "15", 16, "the", -12];  
  
// The obj argument enables use of the this value  
// within the callback function.  
var obj = { minimum: 10, maximum: 20 }  
  
var result = numbers.filter(checkNumericRange, obj);  
  
document.write(result);  
// Output: 12,16  
  
```  
  
## <a name="example"></a>Örnek  
 `filter` Yöntemi, bir dizi yerine bir dizeye uygulanabilir. Aşağıdaki örnek bunun nasıl yapılacağı gösterilmektedir.  
  
```JavaScript  
// Define a callback function that returns true  
// if the current array element follows a space  
// or is the first character.  
function CheckValue(value, index, ar) {  
    if (index == 0)  
        return true;  
    else  
        return ar[index - 1] === " ";  
}  
  
// Create a string.  
var sentence = "The quick brown fox jumps over the lazy dog.";   
  
// Create an array that contains all characters that follow a space.  
var subset = [].filter.call(sentence, CheckValue);   
  
// You can use this alternative syntax.  
//var subset = Array.prototype.filter.call(sentence, CheckValue);  
  
document.write(subset);  
// Output: T,q,b,f,j,o,t,l,d  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizi nesnesi](../../javascript/reference/array-object-javascript.md)   
 [Dizileri kullanma](../../javascript/advanced/using-arrays-javascript.md)   
 [map yöntemi (dizi)](../../javascript/reference/map-method-array-javascript.md)   
 [forEach yöntemi (dizi)](../../javascript/reference/foreach-method-array-javascript.md)