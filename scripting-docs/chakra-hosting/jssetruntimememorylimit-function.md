---
title: JsSetRuntimeMemoryLimit işlevi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryLimit
helpviewer_keywords:
- JsSetRuntimeMemoryLimit function
ms.assetid: 74feb31f-19f6-43e3-b117-0694c59ac593
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 587eb369e6971c7527177624ccf5baf839246cf9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788594"
---
# <a name="jssetruntimememorylimit-function"></a>JsSetRuntimeMemoryLimit İşlevi
Bir çalışma zamanı için geçerli bellek sınırını ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _In_ size_t memoryLimit  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `runtime`  
 Ayarlanacak bellek sınırı olan çalışma zamanı.  
  
 `memoryLimit`  
 Yeni çalışma zamanı bellek sınırı bayt veya bellek sınırsız için -1.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bellek sınırı "yetersiz bellek" hatasıyla başarısız sınırını aşıyor herhangi bir işlem neden olur. Bir çalışma zamanı bellek sınırı çalışma zamanı bellek sınırı yoktur-1 olarak ayarlandığında. Hiçbir bellek sınırına sahip olmak için yeni çalışma zamanları varsayılan. Geçerli kullanım yeni bellek sınırını aşarsa, çağrı başarılı olur ve çalışma zamanı'nın bellek kullanımı sınırın altına düşene kadar bu çalışma zamanında gelecekteki tüm ayırmaları başarısız olur.  
  
 Bir çalışma zamanı bellek sınırı olması her zaman olabilir ayarlanmışsa, çalışma zamanı başka bir iş parçacığı üzerinde etkin olup olmadığına bakılmaksızın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)