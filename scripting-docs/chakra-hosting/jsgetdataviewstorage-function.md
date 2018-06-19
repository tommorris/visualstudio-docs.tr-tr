---
title: JsGetDataViewStorage işlevi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 7c2180e0-51d5-4cc8-ad21-8bf29ff7c583
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b405fc22e411c343dcd5214495deb0275f5db52
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788336"
---
# <a name="jsgetdataviewstorage-function"></a>JsGetDataViewStorage İşlevi
Tarafından kullanılan temel alınan bellek depolama alacağı bir `DataView`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
STDAPI_(JsErrorCode) JsGetDataViewStorage(  
   _In_ JsValueRef dataView,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dataView`  
 DataView örneği.  
  
 `buffer`  
 DataView arabelleği. Döndürülen arabellek ömrü ömrü aynıdır `DataView`. Arabellek işaretçi bir başvuru olarak sayılmaz `DataView` çöp toplama amacıyla.  
  
 `bufferLength`  
 Arabellekteki bayt sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
 Bu API yalnızca kenar modunda desteklenir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)