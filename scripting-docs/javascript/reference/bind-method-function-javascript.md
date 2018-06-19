---
title: bind yöntemi (işlev) (JavaScript) | Microsoft Docs
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
- parameters [JavaScript], bind method
- arguments [JavaScript], bind method
- bind method [JavaScript]
- this keyword [JavaScript], bind method
ms.assetid: 28946f47-b758-48cf-b508-610a0f2f6e19
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd7fc752df9bd41f8625ac2cb484486dfd19558d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789236"
---
# <a name="bind-method-function-javascript"></a>bind Yöntemi (İşlev) (JavaScript)
Belirli bir işlev için, orijinal işlevle aynı gövdeye sahip bağlı işlev oluşturur. İlişkili işlevinde `this` nesne geçirilen nesneye çözümler. Bağlı işlev belirtilen başlangıç parametrelerine sahiptir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
function.bind(thisArg[,arg1[,arg2[,argN]]])  
```  
  
#### <a name="parameters"></a>Parametreler  
 `function`  
 Gerekli. Bir işlev nesnesi.  
  
 `thisArg`  
 Gerekli. Bir nesneye `this` anahtar sözcüğü yeni işlev içinde başvurabilir.  
  
 `arg1`[,`arg2`[,`argN`]]]  
 İsteğe bağlı. Yeni işleve gönderilecek bağımsız değişkenlerin bir listesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aynı yeni bir işlev `function` işlevi dışında `thisArg` nesne ve ilk bağımsız değişken.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa belirtilen `function` bir işlev değil bir `TypeError` özel durumu oluşur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösterir `bind` yöntemi.  
  
```JavaScript  
// Define the original function.  
var checkNumericRange = function (value) {  
    if (typeof value !== 'number')  
        return false;  
    else  
        return value >= this.minimum && value <= this.maximum;  
}  
  
// The range object will become the this value in the callback function.  
var range = { minimum: 10, maximum: 20 };  
  
// Bind the checkNumericRange function.  
var boundCheckNumericRange = checkNumericRange.bind(range);  
  
// Use the new function to check whether 12 is in the numeric range.  
var result = boundCheckNumericRange (12);  
document.write(result);  
  
// Output: true  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, `thisArg` nesne özgün yöntemi içeren nesneyi farklıdır.  
  
```JavaScript  
// Create an object that contains the original function.  
var originalObject = {  
    minimum: 50,  
    maximum: 100,  
    checkNumericRange: function (value) {  
        if (typeof value !== 'number')  
            return false;  
        else  
            return value >= this.minimum && value <= this.maximum;  
    }  
}  
  
// Check whether 10 is in the numeric range.  
var result = originalObject.checkNumericRange(10);  
document.write(result + " ");  
// Output: false  
  
// The range object supplies the range for the bound function.  
var range = { minimum: 10, maximum: 20 };  
  
// Create a new version of the checkNumericRange function that uses range.  
var boundObjectWithRange = originalObject.checkNumericRange.bind(range);  
  
// Check whether 10 is in the numeric range.  
var result = boundObjectWithRange(10);  
document.write(result);  
// Output: true  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösterir `arg1[,arg2[,argN]]]` bağımsız değişkenler. Belirtilen parametreleri bağlı işlev kullanır `bind` birinci ve ikinci parametre olarak yöntemi. Bağımlı işlev çağrıldığında belirtilen tüm parametreler üçüncü, dördüncü (ve sonraki) parametreler olarak kullanılır.  
  
```JavaScript  
// Define the original function with four parameters.  
var displayArgs = function (val1, val2, val3, val4) {  
    document.write(val1 + " " + val2 + " " + val3 + " " + val4);  
}  
  
var emptyObject = {};  
  
// Create a new function that uses the 12 and "a" parameters  
// as the first and second parameters.  
var displayArgs2 = displayArgs.bind(emptyObject, 12, "a");  
  
// Call the new function. The "b" and "c" parameters are used  
// as the third and fourth parameters.  
displayArgs2("b", "c");  
// Output: 12 a b c   
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlev nesnesi](../../javascript/reference/function-object-javascript.md)   
 [filter yöntemi (dizi)](../../javascript/reference/filter-method-array-javascript.md)   
 [Bağlama yöntemini kullanma](../../javascript/advanced/using-the-bind-method-javascript.md)   
 [Hilo JavaScript örnek uygulama (Windows mağazası)](http://hilojs.codeplex.com/SourceControl/latest)