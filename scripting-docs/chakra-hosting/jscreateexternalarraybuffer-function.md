---
title: JsCreateExternalArrayBuffer işlevi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a02aaec-0f67-4bf9-b37c-71cdb1410ca4
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 95459f9a9ff676f47d56ed584ad44a30f24fd4cb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788309"
---
# <a name="jscreateexternalarraybuffer-function"></a>JsCreateExternalArrayBuffer işlevi
Bir Javascript oluşturur `ArrayBuffer` dış belleğe erişmeye nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsCreateExternalArrayBuffer(  
  _Pre_maybenull_ _Pre_writable_byte_size_(byteLength) void *data,  
  _In_ unsigned int byteLength,  
  _In_opt_ JsFinalizeCallback finalizeCallback,  
  _In_opt_ void *callbackState,  
  _Out_ JsValueRef *result  
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `data`  
 Dış bellek için bir işaretçi.  
  
 `byteLength`  
 Dış bellekteki bayt sayısı.  
  
 `finalizeCallback`  
 Nesnenin ne zaman sonlandırılır için bir geri çağırma. Null olabilir.  
  
 `callbackState`  
 Kullanıcı tarafından sağlanan geri finalizeCallback geçirilen durumu.  
  
 `result`  
 Yeni `ArrayBuffer` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)