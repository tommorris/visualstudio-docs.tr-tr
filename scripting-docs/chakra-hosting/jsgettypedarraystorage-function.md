---
title: JsGetTypedArrayStorage işlevi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 52e4ac5f-cc71-456d-95de-a48f7327503d
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5b6f4dc99c219c2ebba631c42493bc194148b497
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788510"
---
# <a name="jsgettypedarraystorage-function"></a>JsGetTypedArrayStorage İşlevi
Yazılı dizisi tarafından kullanılan temel alınan bellek depolama alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsGetTypedArrayStorage(  
   _In_ JsValueRef typedArray,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength,  
   _Out_opt_ JsTypedArrayType *arrayType,  
   _Out_opt_ int *elementSize  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `typedArray`  
 Yazılı dizi örneği.  
  
 `buffer`  
 Dizinin arabelleği. Döndürülen arabellek ömrü dizi ömrü ile aynıdır. Arabellek işaretçi dizi çöp toplama amacıyla bir başvuru olarak sayılmaz.  
  
 `bufferLength`  
 Arabellekteki bayt sayısı.  
  
 `arrayType`  
 Dizi türü.  
  
 `elementSize`  
 Dizi öğesi boyutu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
 Bu API yalnızca kenar modunda desteklenir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)