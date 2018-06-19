---
title: Debug.msUpdateAsyncCallbackRelation işlevi | Microsoft Docs
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
ms.assetid: ee6a1efc-375c-4ce8-a4e8-8896ee29f849
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c47ed7f6313646dddf86dd766d7f1027b2d38ad
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790376"
---
# <a name="debugmsupdateasynccallbackrelation-function"></a>Debug.msUpdateAsyncCallbackRelation İşlevi
Zaman uyumlu iş öğesi ve ilişkili zaman uyumsuz işlemi arasındaki ilişki durumunu güncelleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.msUpdateAsyncCallbackRelation(relatedAsyncOperationId, relationType)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `relatedAsyncOperationId`  
 Gerekli. Zaman uyumsuz işlemle ilişkili kimliği.  
  
 `relationType`  
 İsteğe bağlı. İlişki durumuna belirten değer.  
  
## <a name="remarks"></a>Açıklamalar  
 Zaman uyumlu iş öğesi genellikle zaman uyumsuz işlemi için geri çağırma işlevidir. Bu işlev, zaman uyumsuz bir işlem, bir birleştirme işlemi kullanıldığında veya diğer senaryolarda iptal edildiğinde çağrılabilir.  
  
 Olası değerler için `relationType` içerir:  
  
-   `Debug.MS_ASYNC_CALLBACK_STATUS_ASSIGN_DELEGATE`  
  
-   `Debug.MS_ASYNC_CALLBACK_STATUS_JOIN`  
  
-   `Debug.MS_ASYNC_CALLBACK_STATUS_CHOOSEANY`  
  
-   `Debug.MS_ASYNC_CALLBACK_STATUS_CANCEL`  
  
-   `Debug.MS_ASYNC_CALLBACK_STATUS_ERROR`  
  
 Daha fazla bilgi için bkz: [Debug sabitleri](../../javascript/reference/debug-constants.md).  
  
> [!NOTE]
>  Bazı hata ayıklama araçları için hata ayıklayıcı bu işlev tarafından gönderilen bilgiler görüntülenmez.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]