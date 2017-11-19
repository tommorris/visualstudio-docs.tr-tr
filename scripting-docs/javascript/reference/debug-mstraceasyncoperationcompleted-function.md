---
title: "Debug.msTraceAsyncOperationCompleted işlevi | Microsoft Docs"
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
ms.assetid: 9b628b71-61f1-478a-857f-5e1f607db56c
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 41370257042a2de50d21eba51c299198a6bfb72a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="debugmstraceasyncoperationcompleted-function"></a>Debug.msTraceAsyncOperationCompleted İşlevi
Zaman uyumsuz bir işlemin tamamlandığını gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.msTraceAsyncOperationCompleted(asyncOperationId, status)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `asyncOperationId`  
 Gerekli. Zaman uyumsuz bir işlem ile ilişkili kimliği.  
  
 `status`  
 İsteğe bağlı. Zaman uyumsuz işlem durumu. Belirtilmezse, `Debug.MS_ASYNC_OP_STATUS_SUCCESS` kullanılır.  
  
## <a name="remarks"></a>Açıklamalar  
 Zaman uyumsuz işlemi tamamlandığında bu işlevini çağırın.  
  
 `asyncOperationId`Kimliği daha önce döndürülen işlem karşılık gelmelidir `Debug.msTraceAsyncOperationStarting`.  
  
 Olası değerler için `status` içerir:  
  
-   `Debug.MS_ASYNC_OP_STATUS_SUCCESS`  
  
-   `Debug.MS_ASYNC_OP_STATUS_CANCELED`  
  
-   `Debug.MS_ASYNC_OP_STATUS_ERROR`  
  
> [!NOTE]
>  Bazı hata ayıklama araçları için hata ayıklayıcı gönderilen bilgiler görüntülenmez.  
  
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