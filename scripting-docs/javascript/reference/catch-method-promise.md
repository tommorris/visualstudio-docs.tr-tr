---
title: "catch yöntemi (Promise) | Microsoft Docs"
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
ms.assetid: 55266f6a-db4d-4de8-857a-8bc7d35ed4b8
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 307e5b2a501b038542a602df4538523a3fc6eccd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="catch-method-promise"></a>catch Yöntemi [Promise]
Bir promise reddetme üzerinde yapılacak işleri belirtmenize olanak tanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
promise.catch(onRejected)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `promise`  
 Gerekli. Promise nesnesi.  
  
 `onRejected`  
 Gerekli. Bir promise reddedildiğinde çalıştırmak için hata işleyici işlevi.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde ilk çağrıda zaman aşımı sonra 5000ms döndürür. Bu kod promise reddedilir ve hata işleyicisi işlevi çalıştırır.  
  
```JavaScript  
function timeout(duration) {  
    return new Promise(function(resolve, reject) {  
        setTimeout(reject, duration);  
    });  
}  
  
var p = timeout(5000).then(() => {  
    console.log("done!");  
}).catch(err => {  
    console.log("error!");  
})  
  
// Output (after five seconds):  
// error!  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]