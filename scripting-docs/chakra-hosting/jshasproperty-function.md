---
title: JsHasProperty işlevi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsHasProperty
helpviewer_keywords:
- JsHasProperty function
ms.assetid: 26c94c3d-aae6-4257-8644-df63c7e714fb
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b8edbd1069936152b5edddc0561f45af2ba4ce36
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788564"
---
# <a name="jshasproperty-function"></a>JsHasProperty İşlevi
Bir nesnenin bir özelliğini olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsHasProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ bool *hasProperty  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `object`  
 Özellik içerebilir nesne.  
  
 `propertyId`  
 Özellik kimliği.  
  
 `hasProperty`  
 Nesne (veya bir prototip) özelliği olup olmadığı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Etkin komut dosyası bağlamı gerektiriyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)