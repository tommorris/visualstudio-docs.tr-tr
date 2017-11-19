---
title: "Promise.Reject işlevi (Promise) | Microsoft Docs"
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
ms.assetid: 9746e15b-9717-4e36-bf6b-910dcc6cd667
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0711bdd8a478d4ea07ee40ea6822af3c8c4ac610
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="promisereject-function-promise"></a>Promise.reject İşlevi (Promise)
Yeni bir reddedilen promise geçirilen bağımsız değişken sonuç eşit oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Promise.reject(r);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `r`  
 Gerekli. Promise neden reddedilme nedeni.  
  
## <a name="remarks"></a>Açıklamalar  
 Hata işleme işlevinin `then` veya `catch` yöntemi, reddedilen promise döndürüldüğünde çalıştırır.  
  
## <a name="example"></a>Örnek  
  
```JavaScript  
var p = Promise.reject('failure');  
p.catch(function(result) {  
    console.log(result);  
});  
  
// Output:  
// failure  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Promise nesnesi](../../javascript/reference/promise-object-javascript.md)