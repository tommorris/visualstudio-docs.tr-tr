---
title: "Then yöntemi (Promise) | Microsoft Docs"
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
ms.assetid: c7f3259d-78f7-4ca7-8bdf-99fbd3f41e8d
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eeb97fae19ca9923280b5099e3e4d8c839fa2815
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="then-method-promise"></a>then Yöntemi (Promise)
Bir promise yerine getirme üzerinde yapılacak işleri belirtmenize olanak tanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
promise.then(onCompleted, onRejected);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `promise`  
 Gerekli. Promise nesnesi.  
  
 `onCompleted`  
 Gerekli. Promise başarıyla tamamlandığında çalıştırmak yerine getirme işleyici işlev.  
  
 `onRejected`  
 İsteğe bağlı. Promise reddedildiğinde çalıştırmak için hata işleyici işlevi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir Promise ya da bir değerle doldurulmalıdır veya bir sebeple reddedilmesi gerekir. `then` Promise nesnesinin yöntemi promise tamamlandı ya da reddedilen hangisi önce gerçekleşirse olmadığında çalıştırılabilir. Promise başarıyla tamamlanırsa yerine getirme işleyici işlevinin `then` yöntemi çalışır. Promise reddedilirse, hata işleyici işlevinin `then` yöntemi (veya `catch` yöntemi) çalıştırır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bir işlevi çağırmak nasıl gösterir (`timeout`) bir promise döndürür. Karşılama işleyicisini `then` yöntemi çalıştıktan sonra 5000ms zaman aşımı süresi sona erene.  
  
```JavaScript  
function timeout(duration) {  
    return new Promise(function(resolve, reject) {  
        setTimeout(resolve, duration);  
    });  
}  
  
// Note: This code uses arrow function syntax  
var m = timeout(5000).then(() => {  
    console.log("done!");  
})  
  
// Output (after 5 seconds):  
// done!  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Promise nesnesi](../../javascript/reference/promise-object-javascript.md)