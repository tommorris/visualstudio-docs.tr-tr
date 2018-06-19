---
title: Debug.msTraceAsyncOperationStarting işlevi | Microsoft Docs
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
ms.assetid: c8458264-07e0-4cd6-8528-ff7cf009cf9e
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a50c58e352d40a06192664cdf7424348be02d466
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790391"
---
# <a name="debugmstraceasyncoperationstarting-function"></a>Debug.msTraceAsyncOperationStarting İşlevi
Zaman uyumsuz bir işlem için bir izleme başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.msTraceAsyncOperationStarting(operationName)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `operationName`  
 Gerekli. Zaman uyumsuz işlemi tanımlayan bir dize. Varsa `operationName` null veya tanımsız, boş bir dize için işlem adı kullanılır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem kimliğini temsil eden bir tamsayı  
  
## <a name="remarks"></a>Açıklamalar  
 Zaman uyumsuz işlemi başlamadan önce bu yöntemi çağırın.  
  
> [!NOTE]
>  Bazı hata ayıklama araçları için hata ayıklayıcı gönderilen bilgiler görüntülenmez.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod zaman uyumsuz bir çağrı düzenleme örneğidir bir [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulama.  
  
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