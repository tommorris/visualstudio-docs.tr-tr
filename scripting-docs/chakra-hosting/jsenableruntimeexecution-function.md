---
title: JsEnableRuntimeExecution işlevi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsEnableRuntimeExecution
helpviewer_keywords:
- JsEnableRuntimeExecution function
ms.assetid: daa2036b-aef6-497d-a8ce-5a006b6ed13f
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ad54fb76aec1bf6c1a7f53aa64192807cf0361c2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788264"
---
# <a name="jsenableruntimeexecution-function"></a>JsEnableRuntimeExecution İşlevi
Bir çalışma zamanı komut dosyası yürütme sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDAPI_(JsErrorCode) JsEnableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `runtime`  
 Etkinleştirilecek çalışma zamanı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı ise `JsNoError` kodu, değilse hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 Etkin komut dosyası yürütme zaten bir çalışma zamanı komut dosyası yürütme Hayır op sağlamaktır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)