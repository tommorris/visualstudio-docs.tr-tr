---
title: "JsParseSerializedScript işlevi | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsParseSerializedScript
helpviewer_keywords: JsParseSerializedScript function
ms.assetid: 40d0c7c4-fd5b-46ed-9e65-38c2db2fc859
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7eb18c8537d7bdfe69969293b66a5909ba7c3fa1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jsparseserializedscript-function"></a>JsParseSerializedScript İşlevi
Seri hale getirilmiş bir komut dosyası ayrıştırır ve komut dosyasını temsil eden bir işlev döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsParseSerializedScript(  
   _In_z_ const wchar_t *script,  
   _In_ BYTE *buffer,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `script`  
 Ayrıştırılacak komut dosyası.  
  
 `buffer`  
 Serileştirilmiş komut dosyası.  
  
 `sourceContext`  
 Debuggable betik bağlamları tarafından kullanılan betik tanımlayan bir tanımlama bilgisi.  
  
 `sourceUrl`  
 Komut dosyası konumu geldiği.  
  
 `result`  
 Betik kodu temsil eden bir işlev.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
 Komut dosyalarını yürütmek için kullanılabilir olduğu sürece, kodunuzu bu için Canlı gerekir böylece arabellek komut dosyası altyapısı tarafından bellekte kalıcı yapılmaz.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)