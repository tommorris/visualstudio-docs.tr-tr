---
title: "Debug.msTraceAsyncCallbackStarting işlevi | Microsoft Docs"
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
ms.assetid: 0e2ca7c4-103c-44f2-b76c-102fb1e42543
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 49203cdf16e7cbd74493c882d9cf17b7629da79a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="debugmstraceasynccallbackstarting-function"></a>Debug.msTraceAsyncCallbackStarting İşlevi
Geri Çağırma yığını, daha önce belirtilen bir zaman uyumsuz işlem ile ilişkilendirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.msTraceAsyncCallbackStarting(asyncOperationId)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `asyncOperationId`  
 Gerekli. Zaman uyumsuz işlemle ilişkili kimliği.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev çağrısından sonra zaman uyumsuz işlemi için geri çağırma işlevi çağrısı `Debug.msTraceAsyncOperationCompleted`.  
  
> [!NOTE]
>  Bazı hata ayıklama araçları için hata ayıklayıcı gönderilen bilgiler görüntülenmez.  
  
 `asyncOperationId`daha önce döndürülen işlem adı eşleşmelidir `Debug.msTraceAsyncOperationStarting`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod zaman uyumsuz bir çağrı izleme örneğidir bir [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulama.  
  
```JavaScript  
function asyncWrapperFunction() {  
    var opID = Debug.msTraceAsyncOperationStarting('async trace');  
    doSomethingAsync().then(function (result) {  
        Debug.msTraceAsyncOperationCompleted(opID, Debug.MS_ASYNC_OP_STATUS_SUCCESS);  
        Debug.msTraceAsyncCallbackStarting(opID);  
        // Process result of async operation.  
    }, function (error) {  
        Debug.msTraceAsyncOperationCompleted(opID, Debug.MS_ASYNC_OP_STATUS_ERROR);  
        Debug.msTraceAsyncCallbackStarting(opID);  
    });  
  
    Debug.msTraceAsyncCallbackCompleted();  
}  
  
function doSomethingAsync() {  
    return WinJS.Promise.as(true);  
}  
  
asyncWrapperFunction();  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]