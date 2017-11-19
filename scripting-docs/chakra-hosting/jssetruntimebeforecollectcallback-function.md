---
title: "JsSetRuntimeBeforeCollectCallback işlevi | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsSetRuntimeBeforeCollectCallback
helpviewer_keywords: JsSetRuntimeBeforeCollectCallback function
ms.assetid: 7b2fb911-6007-4ed9-a307-66cefe590ea4
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 469b33a324f67d17bd6f5156da7cce169b98c663
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jssetruntimebeforecollectcallback-function"></a>JsSetRuntimeBeforeCollectCallback İşlevi
Çöp toplama önce çalışma zamanı tarafından çağrılan bir geri çağırma işlevini ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsSetRuntimeBeforeCollectCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsBeforeCollectCallback beforeCollectCallback  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `runtime`  
 Ayırma geri çağırma kaydetmek üzere çalışma zamanı.  
  
 `callbackState`  
 Kullanıcı tarafından sağlanan geri geri çağırma geçirilen durumu.  
  
 `beforeCollectCallback`  
 Ayarlanan geri çağırma işlevi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Geçerli çalışma zamanı yürütme iş parçacığı üzerinde geri arama çağrılır, yürütme geri çağırma işlemi tamamlanana kadar bu nedenle engellenir.  
  
 Geri arama, atık toplama için hazırlamak için ana bilgisayarı tarafından kullanılabilir. Örneğin, gereksiz başvuruları Chakra nesneler üzerinde bırakarak.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)