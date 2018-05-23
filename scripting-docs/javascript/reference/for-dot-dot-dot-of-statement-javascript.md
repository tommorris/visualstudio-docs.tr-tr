---
title: for... of deyimi (JavaScript) | Microsoft Docs
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
ms.assetid: 7872b0b2-5701-4d72-9b52-ed13991542cc
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2373d319347f927304c32cb47856405a1d69a6b2
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
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
 Gerekli. İterable nesne gibi bir `Array`, `Map`, `Set`, veya uygulayan bir nesne [yineleyici arabirimleri](../../javascript/advanced/iterators-and-generators-javascript.md).  
  
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
 [while Deyimi](../../javascript/reference/while-statement-javascript.md)