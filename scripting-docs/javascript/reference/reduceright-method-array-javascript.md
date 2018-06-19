---
title: reduceRight yöntemi (dizi) (JavaScript) | Microsoft Docs
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
- arrays [JavaScript], reduceRight method
- reduceRight method [JavaScript]
ms.assetid: 85963761-da11-407c-8bce-278c930e61bd
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0d7fd2794157eadacefa7404f9333c51aed9425c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792104"
---
# <a name="reduceright-method-array-javascript"></a>reduceRight Yöntemi (Dizi) (JavaScript)
Azalan bir dizideki tüm öğeler için belirtilen geri çağırma işlevini çağırır. Geri çağrı işlevinin dönüş değeri biriken sonuçtur ve geri çağrı işlevine yapılan sonraki çağrıda bir bağımsız değişken olarak sağlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
array1.reduceRight(callbackfn[, initialValue])  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Tanım|  
|---------------|----------------|  
|`array1`|Gerekli. Bir dizi nesnesi.|  
|`callbackfn`|Gerekli. En fazla dört bağımsız değişkenleri kabul eden bir işlev. `reduceRight` Yöntem çağrılarını `callbackfn` işlev dizideki her öğe için bir kez.|  
|`initialValue`|İsteğe bağlı. Varsa `initialValue` belirtilirse, Birikme başlatmak için ilk değeri olarak kullanılır. İlk çağrıda `callbackfn` işlevi bir dizi değeri yerine bağımsız değişken olarak bu değer sağlar.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geri çağırma işlevi son çağrısı birikmiş sonuç içeren bir nesne.  
  
## <a name="exceptions"></a>Özel Durumlar  
 A `TypeError` özel durum olduğunda aşağıdaki koşullardan herhangi biri doğruysa:  
  
-   `callbackfn` Bağımsız değişkeni bir işlev nesnesi değil.  
  
-   Dizi öğe içeriyor ve `initialValue` sağlanmaz.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa bir `initialValue` sağlanan `reduceRight` yöntem çağrılarını `callbackfn` işlev dizin azalan dizideki her öğe için bir kez. Yoksa `initialValue` sağlanan `reduceRight` yöntem çağrılarını `callbackfn` dizin azalan ikinci son öğesi ile başlayan her öğe üzerinde işlevi.  
  
 Geri çağırma işlevinin dönüş değeri olarak sağlanan `previousValue` sonraki çağrı geri çağırma işlevi bağımsız değişken. Son çağrı geri çağırma işlevi için dönüş değerini dönüş değeri `reduceRight` yöntemi.  
  
 Geri çağırma işlevi, dizinin eksik öğeleri için çağrılmaz.  
  
 Dizin artan bir sonuç birikmesini için kullanmak [reduce yöntemi (dizi)](../../javascript/reference/reduce-method-array-javascript.md).  
  
## <a name="callback-function-syntax"></a>Geri Çağırma İşlevi Sözdizimi  
 Geri çağırma işlevinin sözdizimi aşağıdaki gibidir:  
  
 `function callbackfn(previousValue, currentValue, currentIndex, array1)`  
  
 En fazla dört parametre kullanarak geri çağırma işlevi bildirebilirsiniz.  
  
 Geri çağırma işlevi parametreleri aşağıdaki tabloda listelenmektedir.  
  
|Geri çağırma bağımsız değişkeni|Tanım|  
|-----------------------|----------------|  
|`previousValue`|Geri çağırma işlevi önceki çağrısı değeri. Varsa bir `initialValue` için sağlanan `reduceRight` yöntemi, `previousValue` olan `initialValue` işlevi çağrıldığında ilk kez.|  
|`currentValue`|Geçerli dizi öğesinin değeri.|  
|`currentIndex`|Geçerli dizi öğesi sayısal dizini.|  
|`array1`|Öğeyi içeren dizi nesnesi.|  
  
## <a name="first-call-to-the-callback-function"></a>İlk çağrıda geri çağırma işlevi  
 Geri çağırma işlevi çağrıldığında, ilk bağımsız değişken olarak sağlanan değerler olup olmadığına göre bağımlı `reduceRight` yöntemi sahip bir `initialValue` bağımsız değişkeni.  
  
 Varsa bir `initialValue` için sağlanan `reduceRight` yöntemi:  
  
-   `previousValue` Bağımsız değişkeni `initialValue`.  
  
-   `currentValue` Bağımsız değişken, son öğe dizisinde değerdir.  
  
 Varsa bir `initialValue` sağlanmaz:  
  
-   `previousValue` Bağımsız değişken, son öğe dizisinde değerdir.  
  
-   `currentValue` Değişkendir dizisinde ikinci son öğenin değeri.  
  
## <a name="modifying-the-array-object"></a>Dizi Nesnesini Değiştirme  
 Dizi nesnesi, geri çağırma işlevi tarafından değiştirilebilir.  
  
 Sonra dizi nesnesi değiştirme işleminin sonuçları aşağıdaki tabloda açıklanmıştır `reduceRight` yöntemi başlatır.  
  
|Sonra koşul `reduceRight` yöntemi başlatır|Geri çağırma işlevine öğe aktarıldı mı?|  
|-----------------------------------------------------|------------------------------------------|  
|Öğe, dizinin özgün uzunluğunun ardından eklenir.|Hayır.|  
|Öğe, dizinin eksik bir öğesini tamamlamak için eklenir.|Evet, o dizin henüz geri çağırma işlevine aktarılmadıysa.|  
|Öğe değiştirildi.|Evet, o öğe henüz geri çağırma işlevine aktarılmadıysa.|  
|Öğe diziden silindi.|Hayır, o öğe henüz geri çağırma işlevine aktarılmadıysa.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek değerlerle ayıran bir dizeye dizi değerlerini sıralar "::". İlk değer sağlandığından `reduceRight` yöntemi, geri çağırma işlevi ilk çağrıda sahip olarak 456 `previousValue` bağımsız değişkeni ve 123 olarak `currentValue` bağımsız değişkeni.  
  
```JavaScript  
// Define the callback function.  
function appendCurrent (previousValue, currentValue) {  
    return previousValue + "::" + currentValue;  
    }  
  
// Create an array.  
var elements = ["abc", "def", 123, 456];  
  
// Call the reduceRight method, which calls the callback function  
// for each array element, in descending index order.  
var result = elements.reduceRight(appendCurrent);  
  
document.write(result);  
  
// Output:  
//  456::123::def::abc  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek dizi öğelerinin kareler toplamı bulur. `reduceRight` Yöntemi ile başlangıç değeri 0 olarak çağrılır.  
  
```JavaScript  
// Define the callback function.  
function Process(previousValue, currentValue, index, array) {  
    // Add the previous value to the current value squared.  
    var nextValue = previousValue + (currentValue * currentValue);  
  
    // If this is not the last call by the reduceRight method,  
    // the return value is previousValue on the next call.  
    // If this is the last call by the reduceRight method, the  
    // return value is the return value of the reduceRight method.  
    return nextValue;  
}  
  
// Create an array.  
var numbers = [3, 4, 5];  
  
// Call the reduceRight method with an initial value of 0.  
var sumOfSquares = numbers.reduceRight(Process, 0);  
  
document.write("sum of squares=" + sumOfSquares);  
  
// Output:  
//  sum of squares=50  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu değerleri 1 ile 10 arasında olan bir dizi öğelerini alır. Sağlanan ilk değer `reduceRight` boş bir dizi bir yöntemdir.  
  
```JavaScript  
function Process2(previousArray, currentValue) {  
    // If currentValue is between 1 and 10,   
    // append currentValue to the array.  
    var nextArray;  
    if (currentValue >= 1 && currentValue <= 10)  
        nextArray = previousArray.concat(currentValue);  
    else  
        nextArray = previousArray;  
  
    // If this is not the last call by the reduceRight method,  
    // the returned array is previousArray on the next call.  
    // If this is the last call by the reduceRight method, the  
    // returned array is the return value of the reduceRight method.  
    return nextArray;  
}  
  
// Create an array.  
var numbers = [20, 1, -5, 6, 50, 3];  
  
// Call the reduceRight method, starting with an empty array.  
var emptyArray = new Array();  
var resultArray = numbers.reduceRight(Process2, emptyArray);  
  
document.write("result array=" + resultArray);  
  
// Output:  
//  result array=3,6,1  
```  
  
## <a name="example"></a>Örnek  
 `reduceRight` Yöntemi bir dizeye uygulanabilir. Aşağıdaki örnek, bir dizedeki karakter tersine çevirmek için bu yöntemi kullanmak gösterilmiştir.  
  
```JavaScript  
// Define the callback function.  
function AppendToArray(previousValue, currentValue) {  
    return previousValue + currentValue;  
}  
  
var word = "retupmoc";  
  
// Create a string that reverses the characters of another string.  
// The commented-out statement shows an alternative syntax.  
var result = [].reduceRight.call(word, AppendToArray, "the ");  
// var result = Array.prototype.reduceRight.call(word, AppendToArray, "the ");  
  
document.write(result);  
  
// Output:  
// the computer  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [reduce yöntemi (dizi)](../../javascript/reference/reduce-method-array-javascript.md)