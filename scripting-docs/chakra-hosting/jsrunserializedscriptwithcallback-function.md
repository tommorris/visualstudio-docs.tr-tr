---
title: "JsRunSerializedScriptWithCallback işlevi | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0608d778-f65b-4dc5-a745-364aac57ef59
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ce51c9473100e71831dd53cc6572d9740790ffa0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jsrunserializedscriptwithcallback-function"></a>JsRunSerializedScriptWithCallback işlevi
Seri hale getirilmiş bir komut dosyasını çalıştırır.     IF/olduğunda gerekli yalnızca betik kaynağı geç yükleme olanağı sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsRunSerializedScriptWithCallback(  
  _In_ JsSerializedScriptLoadSourceCallback scriptLoadCallback,  
  _In_ JsSerializedScriptUnloadCallback scriptUnloadCallback,  
  _In_ BYTE *buffer,  
  _In_ JsSourceContext sourceContext,  
  _In_z_ const wchar_t *sourceUrl,  
  _Out_opt_ JsValueRef *result  
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `scriptLoadCallback`  
 Kaynak Kodu komut dosyasının yüklenmesi gerekiyor geri çağırma çağrılır.  
  
 `scriptUnloadCallback`  
 Kaynak kodu ve seri hale getirilmiş komut dosyası artık gerekli geri çağırma çağrılır.  
  
 `buffer`  
 Serileştirilmiş komut dosyası.  
  
 `sourceContext`  
 Debuggable betik bağlamları tarafından kullanılan betik tanımlayan bir tanımlama bilgisi.     Bu bağlamda scriptLoadCallback ve scriptUnloadCallback olarak geçirildi.  
  
 `sourceUrl`  
 Komut dosyası konumu geldiği.  
  
 `result`  
 Varsa betik çalıştıran sonucu. Bu parametre null olabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu API henüz mağazası uygulamaları için kullanılabilir değil.  
  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
 Çöp toplama arabelleğinden oluşturulan tüm işlevler tüm örneklerini olana kadar çalışma zamanı arabelleğe tutar.  Ardından sürüm güvenlidir çağıran bildirmek için scriptUnloadCallback çağırır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)