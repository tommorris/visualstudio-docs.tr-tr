---
title: "JsBoolToBoolean işlevi | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsBoolToBoolean
helpviewer_keywords: JsBoolToBoolean function
ms.assetid: 24322ea3-0638-40a3-9b4c-fc912ebed3ff
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b94f6f48cdb91edc967ad3e9f710462355fcd505
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jsbooltoboolean-function"></a>JsBoolToBoolean İşlevi
Bir Boole değeri oluşturur bir `bool` değeri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode JsBoolToBoolean(  
   _In_ bool value,  
   _Out_ JsValueRef *booleanValue  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `value`  
 Dönüştürülecek değer.  
  
 `booleanValue`  
 Dönüştürülen değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)