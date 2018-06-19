---
title: Jsobjectbeforecollectcallback tür | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: f21a064a-579f-44cb-9d21-76b62e8c18f5
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7d11de01c44792d3e41cc2721a404f2ed906f02e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788432"
---
# <a name="jsobjectbeforecollectcallback-typedef"></a>JsObjectBeforeCollectCallback Tür Tanımı
Bir geri çağırma nesneyi toplama önce çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef void (CALLBACK *JsObjectBeforeCollectCallback)(  
  _In_ JsRef ref,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ref`  
 Toplanacak nesnesi.  
  
 `callbackState`  
 Durum geçirilen `JsSetObjectBeforeCollectCallback`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu API yalnızca kenar modunda desteklenir.  
  
## <a name="requirements"></a>Gereksinimler  
 jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)