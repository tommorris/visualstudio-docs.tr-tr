---
title: JsGetAndClearException işlevi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetAndClearException
helpviewer_keywords:
- JsGetAndClearException function
ms.assetid: 6aec8a88-41ee-47f6-b5f4-32f3cae6bb7b
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3e7e4f89bac59aa776762586ab20fa831b5c24bf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788333"
---
# <a name="jsgetandclearexception-function"></a>JsGetAndClearException İşlevi
Çalışma zamanı özel durum durumda olacak şekilde geçerli bağlamın neden oldu ve bu çalışma zamanı için özel durum durumunu sıfırlar özel durumu döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsGetAndClearException(  
   _Out_ JsValueRef *exception  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `exception`  
 Özel durum çalışma zamanı geçerli bağlamın.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı geçerli bağlamın bir özel durum durumda değilse, bu API döndürülecek `JsErrorInvalidArgument`. Çalışma zamanı devre dışıysa, bu komut dosyası sonlandırıldı, ancak özel durum silmek olmadığı belirten bir özel durum döndürür (çalışma zamanı kullanarak yeniden etkinse, özel durum silinecek `JsEnableRuntimeExecution`).  
  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)