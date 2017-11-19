---
title: "JsCreateContext işlevi | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsCreateContext
helpviewer_keywords: JsCreateContext function
ms.assetid: aceca043-2c73-4029-a06c-8ad6695109cf
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ee756158401468ee00007a764e18a0846f35a3dc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jscreatecontext-function"></a>JsCreateContext İşlevi
Komut dosyaları çalıştırmak için bir komut dosyası içeriği oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
// Edge mode signature  
STDAPI_(JsErrorCode) JsCreateContext(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ JsContextRef *newContext);  
  
// Legacy mode signature  
STDAPI_(JsErrorCode) JsCreateContext(  
   _In_ JsRuntimeHandle runtime,  
   _In_ IDebugApplication *debugApplication,  
   _Out_ JsContextRef *newContext  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `runtime`  
 Çalışma zamanı betik bağlam içinde oluşturuldu.  
  
 `debugApplication`  
 Hata ayıklama için kullanılacak hata ayıklama uygulama. Bu durumda hata ayıklama bağlam için etkin değil Bu parametre null olabilir.  
  
 `newContext`  
 Oluşturulan komut dosyası bağlamı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Her komut dosyası bağlamının diğer tüm betik bağlamları yalıtılır kendi genel nesne vardır.  
  
 `debugApplication` Parametresi kenar modunda desteklenmiyor. Bu API kenar modda kullanma hakkında daha fazla bilgi için bkz: [hedefleme kenar vs. Eski altyapıların](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)