---
title: "JsSetProjectionEnqueueCallback işlevi | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c751ccef-20d2-4d41-9568-1c54adf47cdf
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8abdc575c5066ade4a700a0c88e09e3476a65366
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jssetprojectionenqueuecallback-function"></a>JsSetProjectionEnqueueCallback İşlevi
Projeksiyon tamamlama arayanlar gerekli iş parçacığı için geri çağırma için kullanılacak geri çağırma ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsSetProjectionEnqueueCallback(  
   _In_ JsProjectionEnqueueCallback projectionEnqueueCallback,  
   _In_opt_ void *projectionEnqueueContext);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `projectionEnqueueContext`  
 Projeksiyon tamamlama herhangi bir arka plan iş parçacığında oluştuğunda çağrılan geri çağırma.  
  
 `callbackState`  
 Sağlanan uygulama bağlamı `projectionEnqueueContext`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
 Çağrı farklı bir COM Grup ya da farklı bir iş parçacığı aynı MTA, gelen.  
  
 Bu API yalnızca kenar modunda desteklenir.  
  
> [!CAUTION]
>  PInvoke bu API için şu anda desteklenmiyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)