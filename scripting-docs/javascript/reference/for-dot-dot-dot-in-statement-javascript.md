---
title: for... in deyimi (JavaScript) | Microsoft Docs
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
- iteration statements, for...in statement
- loop structures, for...in statements
ms.assetid: 1b51a0ce-89f7-4a69-88ed-017b47dc398f
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a9c3ce78def6ab91256ff724a4acc87b7cf19ba2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="forin-statement-javascript"></a>for...in Deyimi (JavaScript)
Bir nesnenin her bir özellik ya da bir dizinin her öğe için bir veya daha fazla deyimleri yürütür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
for (variable in [object | array]) {  
    statements   
}  
```  
  
## <a name="parameters"></a>Parametreler  
 `variable`  
 Gerekli. Tüm özellik adı olabilir bir değişken `object` veya hiçbir öğe dizini bir `array`.  
  
 `object`, `array`  
 İsteğe bağlı. Bir nesne veya dizi üzerinden yineleme.  
  
 `statements`  
 İsteğe bağlı. Her özelliği için çalıştırılacak bir veya daha fazla deyimleri `object` ya da her öğeye `array`. Bileşik deyim olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 Her bir yineleme döngüsü, değerini başındaki `variable` sonraki özellik adı `object` veya sonraki öğe dizini `array`. Daha sonra `variable` herhangi bir özelliği başvurmak için döngü içindeki ifadeler `object` veya öğenin `array`.  
  
 Bir nesnenin özelliklerini belirli bir biçimde atanmaz. Yalnızca özellik adında kendi dizini tarafından belirli bir özellik belirtemezsiniz.  
  
 Bir dizi yineleme öğesi sırada başka bir deyişle, 0, 1, 2 gerçekleştirilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `for...in` deyimi ilişkilendirilebilir bir dizi kullanılan bir nesne.  
  
```JavaScript  
// Initialize object.  
a = {"a" : "Athens" , "b" : "Belgrade", "c" : "Cairo"}  
  
// Iterate over the properties.  
var s = ""  
for (var key in a) {  
    s += key + ": " + a[key];  
    s += "<br />";  
    }  
document.write (s);  
  
// Output:  
// a: Athens  
// b: Belgrade  
// c: Cairo  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek kullanımını göstermektedir `for ... in` ancak yinelemek için deyimi bir `Array` expando özelliklere sahip bir nesne.  
  
```JavaScript  
// Initialize the array.  
var arr = new Array("zero","one","two");  
  
// Add a few expando properties to the array.  
arr["orange"] = "fruit";  
arr["carrot"] = "vegetable";  
  
// Iterate over the properties and elements.  
var s = "";  
for (var key in arr) {  
    s += key + ": " + arr[key];  
    s += "<br />";  
}  
  
document.write (s);  
  
// Output:  
//   0: zero  
//   1: one  
//   2: two  
//   orange: fruit  
//   carrot: vegetable  
```  
  
> [!NOTE]
>  Kullanım `Enumerator` bir koleksiyonun üyelerini yinelemek için nesne.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [for deyimi](../../javascript/reference/for-statement-javascript.md)   
 [while deyimi](../../javascript/reference/while-statement-javascript.md)