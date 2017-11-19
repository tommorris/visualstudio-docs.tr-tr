---
title: "JsDoubleToNumber işlevi | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsDoubleToNumber
helpviewer_keywords: JsDoubleToNumber function
ms.assetid: 43eb2ee1-2789-4302-954e-c4087e1ee786
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 65c385e8d54d45200f6e3b5d7b38ffa8e188c8e6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jsdoubletonumber-function"></a>JsDoubleToNumber İşlevi
Sayı bir değerden oluşturur bir `double` değeri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsDoubleToNumber(  
   _In_ double doubleValue,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `doubleValue`  
 `double` Bir sayı değerine dönüştürülemiyor.  
  
 `value`  
 Yeni sayı değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)