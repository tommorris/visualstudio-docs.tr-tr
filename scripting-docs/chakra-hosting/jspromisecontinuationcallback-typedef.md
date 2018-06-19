---
title: Jspromisecontinuationcallback tür | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 51a3fd02-9668-4cf7-bb0b-e1fd03b2528f
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 762391cb66e5298bd70beb3238720d3717554ae0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788480"
---
# <a name="jspromisecontinuationcallback-typedef"></a>JsPromiseContinuationCallback Tür Tanımı
Promise devamlılık geri çağırma.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef void (CALLBACK *JsPromiseContinuationCallback)(  
  _In_ JsValueRef task,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `task`  
  `callbackState`  
  
## <a name="remarks"></a>Açıklamalar  
 Konak bir promise devamlılık geri belirtebilirsiniz `JsSetPromiseContinuationCallback`. Daha sonra çalıştırılacak bir görev bir betiği oluşturur sonra promise devamlılık geri çağırma olan görev çağrılacağı ve görev geçerli komut dosyasını tamamladığınızda çalıştırılacak bir FIFO sırada sokulmalıdır yürütülüyor.  
  
 Bu API yalnızca kenar modunda desteklenir.  
  
## <a name="requirements"></a>Gereksinimler  
 jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)