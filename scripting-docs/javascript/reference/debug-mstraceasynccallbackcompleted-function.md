---
title: Debug.msTraceAsyncCallbackCompleted işlevi | Microsoft Docs
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
ms.assetid: 6f9bf139-a6f0-4d91-b7bf-bcc0515de686
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 952aa3cd1b5c1c223a438c825ac1d97466db86ff
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790334"
---
# <a name="debugmstraceasynccallbackcompleted-function"></a>Debug.msTraceAsyncCallbackCompleted İşlevi
Daha önce belirtilen bir zaman uyumsuz işlemle ilişkili geri çağırma yığını tamamladığını gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.msTraceAsyncCallbackCompleted()  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrısından sonra bu işlevi çağırmak `Debug.msTraceAsyncCallbackStarting`.  
  
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