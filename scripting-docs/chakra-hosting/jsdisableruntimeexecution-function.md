---
title: JsDisableRuntimeExecution işlevi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsDisableRuntimeExecution
helpviewer_keywords:
- JsDisableRuntimeExecution function
ms.assetid: 4bd4670a-a9da-4f8c-b3fd-1fd366d915c3
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f44545f7c81344a2d22f0083087f77ac8074278c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788381"
---
# <a name="jsdisableruntimeexecution-function"></a>JsDisableRuntimeExecution İşlevi
Betik yürütme askıya alır ve bir çalışma zamanı çalışan tüm betiklerde sona erer.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsDisableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `runtime`  
 Askıya alınmasına çalışma zamanı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Askıya alınmış bir çalışma zamanı çağrıları kadar başarısız olur `JsEnableRuntimeExecution` olarak adlandırılır.  
  
 Bu API çalışma zamanı etkin iş parçacığı üzerinde çağrılması gerekmez. Çalışma zamanı askıya alınmış durumuna ayarlanacak rağmen yürütülen betik hemen askıya alınabilir değil; çalışan bir komut dosyası mümkün olan en kısa sürede yakalanamayan bir özel durumla sona erdirilecek.  
  
 Zaten askıya alınmış bir çalışma zamanı yürütme askıya Hayır op olur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)