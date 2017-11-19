---
title: "JsRunSerializedScript işlevi | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsRunSerializedScript
helpviewer_keywords: JsRunSerializedScript function
ms.assetid: 3fd3f6f1-eb3e-4751-92a5-c93b1035f3b2
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b770edbcaa4e7dc36f295407627c10a8b574b88b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jsrunserializedscript-function"></a>JsRunSerializedScript İşlevi
Seri hale getirilmiş bir komut dosyasını çalıştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsRunSerializedScript(  
   _In_z_ const wchar_t *script,  
   _In_ BYTE *buffer,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `script`  
 Serileştirilmiş betik kaynak kodu.  
  
 `buffer`  
 Serileştirilmiş komut dosyası.  
  
 `sourceContext`  
 Debuggable betik bağlamları tarafından kullanılan betik tanımlayan bir tanımlama bilgisi.  
  
 `sourceUrl`  
 Komut dosyası konumu geldiği.  
  
 `result`  
 Varsa betik çalıştıran sonucu. Bu parametre null olabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
 Komut dosyalarını yürütmek için kullanılabilir olduğu sürece, kodunuzu bu için Canlı gerekir böylece arabellek komut dosyası altyapısı tarafından bellekte kalıcı yapılmaz.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)