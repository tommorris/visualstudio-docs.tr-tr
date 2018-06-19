---
title: Jsprojectioncallbackcontext tür | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 50c705c5-664f-4a1a-92f6-4882fc718ab1
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7548dc14ab4b3dddc1633a1ba948aba564d8438a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788426"
---
# <a name="jsprojectioncallbackcontext-typedef"></a>JsProjectionCallbackContext Tür Tanımı
Bağlam JsRT JsProjectionEnqueueCallback, uygulama geri geçirilen ve sağlanan geri çağırma JsRT dön geçirilen `JsProjectionCallback`, doğru iş parçacığı üzerinde uygulama tarafından.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef void *JsProjectionCallbackContext;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Arama gerektirir `JsSetProjectionEnqueueCallback` geri aramalar almak için.  
  
 Bu API yalnızca kenar modunda desteklenir.  
  
## <a name="requirements"></a>Gereksinimler  
 jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)