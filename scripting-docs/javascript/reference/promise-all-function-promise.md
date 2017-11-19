---
title: "Promise.all işlevi (Promise) | Microsoft Docs"
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
ms.assetid: 02a7b90c-96f6-4484-9466-d261efa1b494
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 997a419a990b407ae018f7da39fd75673ea28b6d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="promiseall-function-promise"></a>Promise.all İşlevi (Promise)
İki veya daha fazla öneriler birleştirir ve yalnızca belirtilen tüm öneriler tamamladıktan veya reddedilen döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Promise.all(func1, func2 [,funcN])  
```  
  
#### <a name="parameters"></a>Parametreler  
 `func1`  
 Gerekli. Bir promise döndüren bir işlev.  
  
 `func2`  
 Gerekli. Bir promise döndüren bir işlev.  
  
 `funcN`  
 İsteğe bağlı. Bir promise döndüren bir veya daha fazla işlevler.  
  
## <a name="remarks"></a>Açıklamalar  
 Döndürülen sonuç tamamlanmış öneriler tarafından döndürülen değerlerin bir dizidir. Birleştirilmiş öneriler birini reddedilirse, `Promise.all` hemen reddedilen promise için (diğer tüm döndürür değerleri atılır) sebeple döndürür.  
  
## <a name="example"></a>Örnek  
 Bu kod, zaman aşımı ilk çağrıda sonra 5000ms döndürür. Tamamlama işleyicisi çağrılarını `Promise.all`, zaman aşımı hem çağrıları yalnızca tamamlandı veya reddedilen döndürür.  
  
```JavaScript  
function timeout(duration) {  
    return new Promise(function(resolve, reject) {  
        setTimeout(resolve, duration);  
    });  
}  
  
var p = timeout(5000).then(() => {  
    return Promise.all([timeout(100), timeout(200)]);  
})  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Promise nesnesi](../../javascript/reference/promise-object-javascript.md)