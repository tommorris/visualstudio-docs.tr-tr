---
title: Jsprojectionenqueuecallback tür | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 19c1cefb-a7be-4196-b780-9fe6adf35ba5
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bda4a3a80edac38ab2c3885c2256cdf9d03eb8c1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788393"
---
# <a name="jsprojectionenqueuecallback-typedef"></a>JsProjectionEnqueueCallback Tür Tanımı
Orijinal adından farklı bir iş parçacığı üzerinde bir yansıtma API'si tamamlandığında JsRT tarafından çağrılan uygulama geri çağırma.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef void (CALLBACK *JsProjectionEnqueueCallback)(  
  _In_ JsProjectionCallback jsCallback,  
  _In_ JsProjectionCallbackContext jsContext,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `jsCallback`  
 Özgün iş parçacığında çağrılan geri çağırma.  
  
 `jsContext`  
 Uygulama bağlamı.  
  
 `callbackState`  
 İçine geçirilmelidir JsRT bağlamı `jsCallback`.  
  
## <a name="remarks"></a>Açıklamalar  
 Geri aramalar almaya JsSetProjectionEnqueueCallback çağrılması gerekir.  
  
 Bu API yalnızca kenar modunda desteklenir.  
  
## <a name="requirements"></a>Gereksinimler  
 jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)