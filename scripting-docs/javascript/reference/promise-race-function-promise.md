---
title: "Promise.race işlevi (Promise) | Microsoft Docs"
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
ms.assetid: 9236eced-d313-4d03-8c3e-d89d762b3084
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fedd512f4565009c8429b43b0d9d93de943d13fb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="promiserace-function-promise"></a>Promise.race İşlevi (Promise)
Gidermek veya reddetme yeni bir promise gidermek veya geçirilen bağımsız değişkenleri arasında reddetmek için ilk promise aynı sonucu değeri oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Promise.race(iterable)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `iterable`  
 Gerekli. Bir veya daha fazla öneriler.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa söz birini `iterable` çözülmüş veya reddedilen bir durumda zaten `Promise.race` çözümlenmiş ya da bu promise çözmek (veya reddetmek için) kullanılan değerine eşit sonuç değeri ile aynı şekilde reddedilen bir promise döndürür. İçinde birden çok taahhüt eder, `iterable` zaten çözümlenmiş veya reddedilen `Promise.race` yinelendiğinde ilk promise aynı şekilde çözülmüş promise döndürür. Promise hiçbir taahhüdü durumunda iterable çözümler veya reddeder, döndürülen `Promise.race` de çözmek Reddet veya değil.  
  
## <a name="example"></a>Örnek  
  
```JavaScript  
var p1 = new Promise(function(resolve, reject) {  
    setTimeout(resolve, 0, 'success');  
});  
var p2 = new Promise(function(resolve, reject) { });  
var p2 = new Promise(function(resolve, reject) { });  
  
var race = Promise.race( [p1, p2, p3] );  
race.then(function(result) {  
    console.log(result);  
});  
  
// Output:  
// success  
  
var race = Promise.race( [Promise.reject('failure'),  
    Promise.resolve('success')] );  
race.catch(function(result) {  
    console.log(result);  
});  
  
// Output:  
// failure  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Promise nesnesi](../../javascript/reference/promise-object-javascript.md)