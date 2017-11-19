---
title: "every yöntemi (dizi) (JavaScript) | Microsoft Docs"
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
- every method
- arrays [JavaScript], every method
ms.assetid: dc4ee2f8-fb9e-4c9f-af5a-fe836e40ddd1
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4a05263ae45df61c47a3580d474863c8d4ff3dd1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="every-method-array-javascript"></a>every Yöntemi (Dizi) (JavaScript)
Belirtilen testi karşılayan bir dizinin tüm üyeler olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
array1.every(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Tanım|  
|---------------|----------------|  
|`array1`|Gerekli. Bir dizi nesnesi.|  
|`callbackfn`|Gerekli. En fazla üç bağımsız değişkeni kabul eden bir işlev. `every` Yöntem çağrılarını `callbackfn` işlevi her öğe için `array1` kadar `callbackfn` döndürür `false`, veya dizinin sonuna kadar.|  
|`thisArg`|İsteğe bağlı. Bir nesneye `this` anahtar sözcüğü başvurabilir `callbackfn` işlevi. Varsa `thisArg` atlanırsa, `undefined` olarak kullanılan `this` değeri.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`varsa `callbackfn` işlev döndürür `true` tüm öğeleri; dizisi için Aksi halde, `false`. Dizi sahip hiçbir öğe ise `every` yöntemi döndürür `true`.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `callbackfn` bağımsız değişkeni bir işlev nesnesi değil bir `TypeError` özel durumu oluşur.  
  
## <a name="remarks"></a>Açıklamalar  
 `every` Yöntem çağrılarını `callbackfn` işlev dizin, kadar artan her dizi öğesi için bir kez `callbackfn` işlev döndürür `false`. Neden olan bir öğe `callbackfn` döndürülecek `false` bulunan `every` yöntemi hemen döndürür `false`. Aksi takdirde, `every` yöntemi döndürür `true`.  
  
 Geri çağırma işlevi, dizinin eksik öğeleri için çağrılmaz.  
  
 Array nesneleri yanı sıra `every` yöntemi olan herhangi bir nesne tarafından kullanılabilecek bir `length` özelliği ve, sayısal olarak dizin oluşturulmuş özellik adları.  
  
> [!NOTE]
>  Kullanabileceğiniz [bazı yöntemi (dizi)](../../javascript/reference/some-method-array-javascript.md) geri çağırma işlevi döndürür olup olmadığını denetlemek için `true` dizi herhangi bir öğe için.  
  
## <a name="callback-function-syntax"></a>Geri Çağırma İşlevi Sözdizimi  
 Geri çağırma işlevinin sözdizimi aşağıdaki gibidir:  
  
 `function callbackfn(value, index, array1)`  
  
 En fazla üç parametre ile geri çağırma işlevi bildirebilirsiniz.  
  
 Geri çağırma işlevi parametreleri aşağıdaki tabloda listelenmektedir.  
  
|Geri çağırma parametresi|Tanım|  
|------------------------|----------------|  
|`value`|Dizi öğesinin değeri.|  
|`index`|Dizi öğesinin sayısal dizini.|  
|`array1`|Öğeyi içeren dizi nesnesi.|  
  
## <a name="modifying-the-array-object"></a>Dizi Nesnesini Değiştirme  
 Dizi nesnesi, geri çağırma işlevi tarafından değiştirilebilir.  
  
 Sonra dizi nesnesi değiştirme işleminin sonuçları aşağıdaki tabloda açıklanmıştır `every` yöntemi başlatır.  
  
|Sonra koşul `every` yöntemi başlatır|Geri çağırma işlevine öğe aktarıldı mı?|  
|-----------------------------------------------|------------------------------------------|  
|Öğe, dizinin özgün uzunluğunun ardından eklenir.|Hayır.|  
|Öğe, dizinin eksik bir öğesini tamamlamak için eklenir.|Evet, o dizin henüz geri çağırma işlevine aktarılmadıysa.|  
|Öğe değiştirildi.|Evet, o öğe henüz geri çağırma işlevine aktarılmadıysa.|  
|Öğe diziden silindi.|Hayır, o öğe henüz geri çağırma işlevine aktarılmadıysa.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `every` yöntemi.  
  
```JavaScript  
// Define the callback function.  
function CheckIfEven(value, index, ar) {  
    document.write(value + " ");  
  
    if (value % 2 == 0)  
        return true;  
    else  
        return false;  
}  
  
// Create an array.  
var numbers = [2, 4, 5, 6, 8];  
  
// Check whether the callback function returns true for all of the  
// array values.  
if (numbers.every(CheckIfEven))  
    document.write("All are even.");  
else  
    document.write("Some are not even.");  
  
// Output:  
// 2 4 5 Some are not even.  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `thisArg` bir nesneye belirtir bağımsız değişkeni `this` anahtar sözcüğü başvurabilir.  
  
```JavaScript  
// Create a function that returns true if the value is  
// numeric and within range.  
var checkNumericRange = function(value) {  
    if (typeof value !== 'number')  
        return false;  
    else   
        return value >= this.minimum && value <= this.maximum;  
}  
  
// Create an array of numbers.  
var numbers = [10, 15, 19];  
  
// Check whether the callback function returns true for  
// all of the array values.  
// The obj argument enables use of the this value  
// within the callback function.  
  
var obj = { minimum: 10, maximum: 20 }  
  
if (numbers.every(checkNumericRange, obj))  
    document.write ("All are within range.");  
else  
    document.write ("Some are not within range.");  
  
// Output:  
//   All are within range.  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Some yöntemi (dizi)](../../javascript/reference/some-method-array-javascript.md)   
 [filter yöntemi (dizi)](../../javascript/reference/filter-method-array-javascript.md)   
 [Dizi nesnesi](../../javascript/reference/array-object-javascript.md)   
 [Dizileri kullanma](../../javascript/advanced/using-arrays-javascript.md)