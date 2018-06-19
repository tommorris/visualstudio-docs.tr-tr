---
title: JsSetPromiseContinuationCallback işlevi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 6ef0faf4-1500-4bd9-aeca-c208492af8ea
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c20b5c81bd34a44158a975f0c1aed88614e01022
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788495"
---
# <a name="jssetpromisecontinuationcallback-function"></a>JsSetPromiseContinuationCallback İşlevi
Bir görevi gelecekteki yürütülmek üzere sıraya gerektiğinde bağlam tarafından çağrılan bir promise devamlılık geri çağırma işlevini ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsSetPromiseContinuationCallback(  
   _In_ JsPromiseContinuationCallback promiseContinuationCallback,  
   _In_opt_ void *callbackState  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `promiseContinuationCallback`  
 Ayarlanan geri çağırma işlevi.  
  
 `callbackState`  
 Kullanıcı tarafından sağlanan geri geri çağırma geçirilen durumu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
 Bu API yalnızca kenar modunda desteklenir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)