---
title: "Jsınspectabletoobject işlevi | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: dd0ad567-2ba8-4a63-bee4-2c6ff5ce9fa9
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc2c1cb12bf4b89d15e20a06c5366ac5fbc07faf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jsinspectabletoobject-function"></a>JsInspectableToObject İşlevi
Geçirilen, projeksiyon bir JavaScript değer oluşturur, `IInspectable` işaretçi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsInspectableToObject(  
        _In_ IInspectable  *inspectable,  
        _Out_ JsValueRef *value  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `inspectable`  
 A `IInspectable` öngörülen için.  
  
 `value`  
 JavaScript değeri başka bir deyişle, bir yansıtma `IInspectable`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Öngörülen Değer WinRT nesne çağırmak için komut dosyası tarafından kullanılabilir. Konaklar, kuralları iş parçacığı oluşturma COM zorlama için sorumludur.  
  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
 Bu API yalnızca kenar modunda desteklenir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)