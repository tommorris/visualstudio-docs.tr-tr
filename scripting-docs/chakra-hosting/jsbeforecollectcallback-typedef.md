---
title: Jsbeforecollectcallback tür | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 58bece47-4e6d-49e7-a93d-b6a8f9928b41
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 50e2b79ceb2809aee0348bae594e8494596b6089
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788165"
---
# <a name="jsbeforecollectcallback-typedef"></a>JsBeforeCollectCallback Tür Tanımı
Bir geri çağırma koleksiyonu önce çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef void (CALLBACK *JsBeforeCollectCallback)(  
_In_opt_ void *callbackState  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 callbackState  
 Durumu için JsSetBeforeCollectCallback geçirildi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu geri çağırma kaydetmek için JsSetBeforeCollectCallback kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)