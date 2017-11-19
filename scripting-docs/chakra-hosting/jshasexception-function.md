---
title: "JsHasException işlevi | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsHasException
helpviewer_keywords: JsHasException function
ms.assetid: ac7da3ce-c746-4154-bbb8-bcb0859a8d5b
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 32334f4b8787bebaffb9553fcdd40f85334462cb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jshasexception-function"></a>JsHasException İşlevi
Çalışma zamanı geçerli bağlamın bir özel durum durumda olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsHasException(  
   _Out_ bool *hasException  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `hasException`  
 Çalışma zamanı geçerli bağlamın özel durum durumunda olup olmadığı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir çağrı yazarsa (bir komut dosyası çalıştırma veya bir şey nedeniyle sonucunda ya da bir dönüştürme hatası gibi) bir özel durum çalışma zamanı sonuçlarında, bir "özel durum durumuna." çalışma zamanı yerleştirilir Çalışma zamanı (dışında özel API) tarafından oluşturulan her bağlam tüm çağrılar başarısız `JsErrorInExceptionState` özel temizlenene kadar.  
  
 Geri arama motoruna döndürdüğünde geçerli bağlamın çalışma zamanı özel durum durumdaysa, altyapısı özel durumu yeniden oluşturulması.  
  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)