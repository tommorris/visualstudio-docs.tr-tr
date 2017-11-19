---
title: for... of deyimi (JavaScript) | Microsoft Docs
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
ms.assetid: 7872b0b2-5701-4d72-9b52-ed13991542cc
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 47154261fd4817ba95b8884bd6482a87e044a5a4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="forof-statement-javascript"></a>for...of Deyimi (JavaScript)
Her bir değer için bir veya daha fazla bilgilerinin iterable nesneden elde yineleyici yürütür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
for (variable of object) {  
    statements   
}  
```  
  
## <a name="parameters"></a>Parametreler  
 `variable`  
 Gerekli. Tüm özellik değeri olabilecek bir değişken `object`.  
  
 `object`  
 Gerekli. İterable nesne gibi bir `Array`, `Map`, `Set`, veya uygulayan bir nesne [yineleyici arabirimleri](http://msdn.microsoft.com/en-us/3692355a-a703-4d43-8fb5-c03b4b7e8db1).  
  
 `statements`  
 İsteğe bağlı. Her değer için çalıştırılacak bir veya daha fazla deyimleri bir `object`. Bileşik deyim olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 Her bir yineleme döngüsü, değerini başındaki `variable` sonraki özellik değeri `object`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `for...of` deyimi bir dizi.  
  
```JavaScript  
let arr = [ "fred", "tom", "bob" ];  
  
for (let i of arr) {  
    console.log(i);  
}  
  
// Output:  
// fred  
// tom  
// bob  
  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `for...of` on deyimi bir `Map` nesnesi.  
  
```JavaScript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
  
for (var n of m) {  
  console.log(n);  
}  
  
// Output:  
// 1,black  
// 2,red  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [for... deyimi içinde](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [for deyimi](../../javascript/reference/for-statement-javascript.md)   
 [while deyimi](../../javascript/reference/while-statement-javascript.md)