---
title: "JsSetRuntimeMemoryAllocationCallback işlevi | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryAllocationCallback
helpviewer_keywords:
- JsSetRuntimeMemoryAllocationCallback function
ms.assetid: 6aa7d58d-6456-4df1-815f-1ba36fb4ae14
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 755ab36c8edb8c0350eb2b245e060344c8825dee
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jssetruntimememoryallocationcallback-function"></a>JsSetRuntimeMemoryAllocationCallback İşlevi
Belirtilen çalışma zamanı için bir bellek ayırma geri çağırma ayarlar  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryAllocationCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryAllocationCallback allocationCallback  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `runtime`  
 Ayırma geri çağırma kaydetmek üzere çalışma zamanı.  
  
 `callbackState`  
 Kullanıcı tarafından sağlanan geri geri çağırma geçirilen durumu.  
  
 `allocationCallback`  
 Bellek ayırma olaylar için çağrılacak bellek ayırma geri çağırma.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bellek ayırma geri çağırma kaydetme çalışma zamanı bellekten alması veya bellek, işletim sistemi sürümleri her ana bilgisayara geri aramayı neden olur. Geri arama yordamı, bir bellek bloğu çalışma zamanı bellek yöneticisi ayırır önce çağrılır. Geri çağırma false değeri döndürülürse ayırma reddedilir. Çalışma zamanı bellek yöneticisi, ayrıca bir bellek bloğu boşaltma sonra yanı sıra ayırma hatadan sonra geri arama yordamı çağırır.  
  
 Geçerli çalışma zamanı yürütme iş parçacığı üzerinde geri arama çağrılır, yürütme geri çağırma işlemi tamamlanana kadar bu nedenle engellenir.  
  
 Geri dönüş değerini depolanmaz; Önceden Reddedilen ayırmaları daha sonra yeniden yeni bellek ayırma için geri çağırma çalışma zamanı önlemez.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)