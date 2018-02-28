---
title: "JsSetException işlevi | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsSetException
helpviewer_keywords:
- JsSetException function
ms.assetid: c528793a-2e1b-4ee1-bd2e-e63fd547dc40
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5d8fce71f14dedea02e1809fb72281f575f60604
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jssetexception-function"></a>JsSetException İşlevi
Geçerli bağlamın çalışma zamanını özel bir duruma ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsSetException(  
   _In_ JsValueRef exception  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `exception`  
 Geçerli bağlamın çalışma zamanı için ayarlanacak olan JavaScript özel durumu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `JsNoError`Altyapı bir özel durum durumuna bir hata kodu aksi ayarlanmışsa.  
  
## <a name="remarks"></a>Açıklamalar  
 Geçerli içeriğinin çalışma zamanı zaten özel durumdaysa, bu API `JsErrorInExceptionState`'i döndürür.  
  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)