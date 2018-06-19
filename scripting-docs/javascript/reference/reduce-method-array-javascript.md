---
title: reduce yöntemi (dizi) (JavaScript) | Microsoft Docs
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
- callback function, reduce method [JavaScript]
- arrays [JavaScript], reduce method
- reduce method [JavaScript]
ms.assetid: 48d069e0-e083-494f-86d5-d459d2377dc5
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d99f92d90885f26b19392b476ee64ae17bd40aed
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34264782"
---
# <a name="reduce-method-array-javascript"></a>reduce Yöntemi (Dizi) (JavaScript)
Bir dizinin tüm öğeleri için belirtilen geri çağırma işlevini çağırır. Geri çağrı işlevinin dönüş değeri biriken sonuçtur ve geri çağrı işlevine yapılan sonraki çağrıda bir bağımsız değişken olarak sağlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
array1.reduce(callbackfn[, initialValue])  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Tanım|  
|---------------|----------------|  
|`array1`|Gerekli. Bir dizi nesnesi.|  
|`callbackfn`|Gerekli. En fazla dört bağımsız değişkenleri kabul eden bir işlev. `reduce` Yöntem çağrılarını `callbackfn` işlev dizideki her öğe için bir kez.|  
|`initialValue`|İsteğe bağlı. Varsa `initialValue` belirtilirse, Birikme başlatmak için ilk değeri olarak kullanılır. İlk çağrıda `callbackfn` işlevi bir dizi değeri yerine bağımsız değişken olarak bu değer sağlar.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geri çağırma işlevi için son çağrısından birikmiş sonucu.  
  
## <a name="exceptions"></a>Özel Durumlar  
 A `TypeError` özel durum olduğunda aşağıdaki koşullardan herhangi biri doğruysa:  
  
-   `callbackfn` Bağımsız değişkeni bir işlev nesnesi değil.  
  
-   Dizi öğe içeriyor ve `initialValue` sağlanmaz.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa bir `initialValue` sağlanan `reduce` yöntem çağrılarını `callbackfn` işlev mevcut dizin artan dizideki her öğe için bir kez. Varsa bir `initialValue` sağlanmadı, `reduce` yöntem çağrılarını `callbackfn` ikinci öğesi ile başlayan her öğenin işlevi.  
  
 Geri çağırma işlevinin dönüş değeri olarak sağlanan `accumulator` sonraki çağrı geri çağırma işlevi bağımsız değişken. Son çağrı geri çağırma işlevi için dönüş değerini dönüş değeri `reduce` yöntemi.  
  
 Geri çağırma işlevi, dizinin eksik öğeleri için çağrılmaz.  
  
> [!NOTE]
>  [ReduceRight yöntemi (dizi)](../../javascript/reference/reduceright-method-array-javascript.md) dizin azalan öğeleri işler.  
  
## <a name="callback-function-syntax"></a>Geri Çağırma İşlevi Sözdizimi  
 Geri çağırma işlevinin sözdizimi aşağıdaki gibidir:  
  
 `function callbackfn(accumulator, currentValue, currentIndex, array1)`  
  
 En fazla dört parametre kullanarak geri çağırma işlevi bildirebilirsiniz.  
  
 Geri çağırma işlevi parametreleri aşağıdaki tabloda listelenmektedir.  
  
|Geri çağırma bağımsız değişkeni|Tanım|  
|-----------------------|----------------|  
|`accumulator`|Geri çağırma işlevi önceki çağrısı değeri. Varsa bir `initialValue` için sağlanan `reduce` yöntemi, `accumulator` olan `initialValue` işlevi çağrıldığında ilk kez.|  
|`currentValue`|Geçerli dizi öğesinin değeri.|  
|`currentIndex`|Geçerli dizi öğesi sayısal dizini.|  
|`array1`|Öğeyi içeren dizi nesnesi.|  
  
## <a name="first-call-to-the-callback-function"></a>İlk çağrıda geri çağırma işlevi  
 Geri çağırma işlevi çağrıldığında, ilk bağımsız değişken olarak sağlanan değerler olup olmadığına göre bağımlı `reduce` yöntemi sahip bir `initialValue` bağımsız değişkeni.  
  
 Varsa bir `initialValue` azaltın yöntemi sağlanır:  
  
-   `accumulator` Bağımsız değişkeni `initialValue`.  
  
-   `currentValue` Bağımsız değişkeni, ilk öğe dizisinde değerdir.  
  
 Varsa bir `initialValue` sağlanmaz:  
  
-   `accumulator` Bağımsız değişkeni, ilk öğe dizisinde değerdir.  
  
-   `currentValue` Bağımsız değişkeni, ikinci öğesi dizisinde değerdir.  
  
## <a name="modifying-the-array-object"></a>Dizi Nesnesini Değiştirme  
 Dizi nesnesi, geri çağırma işlevi tarafından değiştirilebilir.  
  
 Sonra dizi nesnesi değiştirme işleminin sonuçları aşağıdaki tabloda açıklanmıştır `reduce` yöntemi başlatır.  
  
|Sonra koşul `reduce` yöntemi başlatır|Geri çağırma işlevine öğe aktarıldı mı?|  
|------------------------------------------------|------------------------------------------|  
|Öğe, dizinin özgün uzunluğunun ardından eklenir.|Hayır.|  
|Öğe, dizinin eksik bir öğesini tamamlamak için eklenir.|Evet, o dizin henüz geri çağırma işlevine aktarılmadıysa.|  
|Öğe değiştirildi.|Evet, o öğe henüz geri çağırma işlevine aktarılmadıysa.|  
|Öğe diziden silindi.|Hayır, o öğe henüz geri çağırma işlevine aktarılmadıysa.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek değerlerle ayıran bir dizeye dizi değerlerini sıralar "::". İlk değer sağlandığından `reduce` yöntemi, geri çağırma işlevi ilk çağrıda sahip "abc" olarak `accumulator` bağımsız değişkeni ve "def" olarak `currentValue` bağımsız değişkeni.  
  
```JavaScript  
// Define the callback function.  
function appendCurrent (accumulator, currentValue) {  
    return accumulator + "::" + currentValue;  
    }  
  
// Create an array.  
var elements = ["abc", "def", 123, 456];  
  
// Call the reduce method, which calls the callback function  
// for each array element.  
var result = elements.reduce(appendCurrent);  
  
document.write(result);  
  
// Output:  
//  abc::def::123::456  
  
```  
  
## <a name="example"></a>Örnek  
 Yuvarlanmış sonra aşağıdaki örnekte bir dizi değerlerini ekler. `reduce` Yöntemi ile başlangıç değeri 0 olarak çağrılır.  
  
```JavaScript  
// Define the callback function.  
function addRounded (accumulator, currentValue) {  
    return accumulator + Math.round(currentValue);  
    }  
  
// Create an array.  
var numbers = [10.9, 15.4, 0.5];  
  
// Call the reduce method, starting with an initial value of 0.  
var result = numbers.reduce(addRounded, 0);  
  
document.write (result);  
// Output: 27  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir dizi değerler ekler. `currentIndex` Ve `array1` parametreleri, geri çağırma işlevi kullanılır.  
  
```JavaScript  
function addDigitValue(accumulator, currentDigit, currentIndex, array) {  
    var exponent = (array.length - 1) - currentIndex;  
    var digitValue = currentDigit * Math.pow(10, exponent);  
    return accumulator + digitValue;  
    }  
  
var digits = [4, 1, 2, 5];  
  
// Determine an integer that is computed from values in the array.  
var result = digits.reduce(addDigitValue, 0);  
  
document.write (result);  
// Output: 4125  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, 1 ile 10 başka bir dizide arasında olan değerleri içeren bir dizi alır. Sağlanan ilk değer `reduce` boş bir dizi bir yöntemdir.  
  
```JavaScript  
function Process(accumulatedArray, currentValue) {  
    // If currentValue is between 1 and 10,   
    // append currentValue to the array.  
    var nextArray;  
    if (currentValue >= 1 && currentValue <= 10)  
        nextArray = accumulatedArray.concat(currentValue);  
    else  
        nextArray = accumulatedArray;  
  
    // If this is not the last call by the reduce method,  
    // the returned array is accumulatedArray on the next call.  
    // If this is the last call by the reduce method, the  
    // returned array is the return value of the reduce method.  
    return nextArray;  
}  
  
// Create an array.  
var numbers = [20, 1, -5, 6, 50, 3];  
  
// Call the reduce method, starting with an initial empty array.  
var emptyArray = new Array();  
var resultArray = numbers.reduce(Process, emptyArray);  
  
document.write("result array=" + resultArray);  
  
// Output:  
// result array=1,6,3  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [reduceRight Metodu (Dizi)](../../javascript/reference/reduceright-method-array-javascript.md)
