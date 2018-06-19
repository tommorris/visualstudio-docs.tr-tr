---
title: Some yöntemi (dizi) (JavaScript) | Microsoft Docs
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
- arrays [JavaScript], some method
- some method [JavaScript]
ms.assetid: 7b6822f9-c406-4f4e-bfec-a93459745992
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ba3f855c61daac511bcf7aca6b47f643dda93313
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792056"
---
# <a name="some-method-array-javascript"></a>some Yöntemi (Dizi) (JavaScript)
Belirtilen geri çağırma işlevi döndürüp döndürmediğini belirler `true` dizi herhangi bir öğe için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
array1.some(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Tanım|  
|---------------|----------------|  
|`array1`|Gerekli. Bir dizi nesnesi.|  
|`callbackfn`|Gerekli. En fazla üç bağımsız değişkeni kabul eden bir işlev. `some` Yöntem çağrılarını `callbackfn` işlevi her öğe için `array1` kadar `callbackfn` döndürür `true`, veya dizinin sonuna kadar.|  
|`thisArg`|İsteğe bağlı. Bir nesneye `this` anahtar sözcüğü başvurabilir `callbackfn` işlevi. Varsa `thisArg` atlanırsa, `undefined` olarak kullanılan `this` değeri.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`varsa `callbackfn` işlev döndürür `true` için herhangi bir dizi öğesi; Aksi halde, `false`.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `callbackfn` bağımsız değişkeni bir işlev nesnesi değil bir `TypeError` özel durumu oluşur.  
  
## <a name="remarks"></a>Açıklamalar  
 `some` Yöntem çağrılarını `callbackfn` dizini, kadar artan her dizi öğesi üzerinde işlevi `callbackfn` işlev döndürür `true`. Neden olan bir öğe `callbackfn` döndürülecek `true` bulunan `some` yöntemi hemen döndürür `true`. Geri çağırma oluşmazsa `true` herhangi bir öğe üzerinde `some` yöntemi döndürür `false`.  
  
 Geri çağırma işlevi, dizinin eksik öğeleri için çağrılmaz.  
  
 Array nesneleri yanı sıra `some` yöntemi olan herhangi bir nesne tarafından kullanılabilecek bir `length` özelliği ve, sayısal olarak dizin oluşturulmuş özellik adları.  
  
> [!NOTE]
>  Kullanabileceğiniz [every yöntemi (dizi)](../../javascript/reference/every-method-array-javascript.md) geri çağırma işlevi döndürür olup olmadığını denetlemek için `true` bir dizinin tüm öğeleri için.  
  
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
  
 Sonra dizi nesnesi değiştirme işleminin sonuçları aşağıdaki tabloda açıklanmıştır `some` yöntemi başlatır.  
  
|Sonra koşul `some` yöntemi başlatır|Geri çağırma işlevine öğe aktarıldı mı?|  
|----------------------------------------------|------------------------------------------|  
|Öğe, dizinin özgün uzunluğunun ardından eklenir.|Hayır.|  
|Öğe, dizinin eksik bir öğesini tamamlamak için eklenir.|Evet, o dizin henüz geri çağırma işlevine aktarılmadıysa.|  
|Öğe değiştirildi.|Evet, o öğe henüz geri çağırma işlevine aktarılmadıysa.|  
|Öğe diziden silindi.|Hayır, o öğe henüz geri çağırma işlevine aktarılmadıysa.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `some` herhangi bir öğenin bir dizide olmadığını öğrenmek için yöntemdir bile.  
  
```JavaScript  
// The callback function.  
function CheckIfEven(value, index, ar) {  
    if (value % 2 == 0)  
        return true;  
}  
  
var numbers = [1, 15, 4, 10, 11, 22];  
  
var evens = numbers.some(CheckIfEven);  
document.write(evens);  
  
// Output:  
// true  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `thisArg` bir nesneye belirten parametresi `this` anahtar sözcüğü başvurabilir. Herhangi bir dizi sayılar geçirilen nesne tarafından sağlanan izin verilen aralığın dışında olup olmadığını denetler  
  
```JavaScript  
// Create a function that returns true if the value is   
// outside the range.  
var isOutsideRange = function (value) {  
    return value < this.minimum || value > this.maximum;  
}  
  
// Create an array of numbers.  
var numbers = [6, 12, 16, 22, -12];  
  
// The range object is to be the 'this' object.  
var range = { minimum: 10, maximum: 20 };  
  
document.write(numbers.some(isOutsideRange, range));  
  
// Output: true  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [every yöntemi (dizi)](../../javascript/reference/every-method-array-javascript.md)   
 [filter yöntemi (dizi)](../../javascript/reference/filter-method-array-javascript.md)   
 [map yöntemi (dizi)](../../javascript/reference/map-method-array-javascript.md)