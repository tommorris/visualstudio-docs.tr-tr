---
title: "Jsısruntimeexecutiondisabled işlevi | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsIsRuntimeExecutionDisabled
helpviewer_keywords: JsIsRuntimeExecutionDisabled function
ms.assetid: 77490280-fb84-4614-a1f0-6ac31e3bd607
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f4827205a33d337445faf9b0e9812133f0de3e97
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jsisruntimeexecutiondisabled-function"></a>JsIsRuntimeExecutionDisabled İşlevi
Çalışma zamanında betik yürütmesinin devre dışı olup olmadığını gösteren bir değeri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```vb  
STDAPI_(JsErrorCode) JsIsRuntimeExecutionDisabled(    _In_ JsRuntimeHandle runtime,    _Out_ bool *isDisabled);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `runtime`  
 Yürütmenin devre dışı olup olmadığını denetlemek için çalışma zamanı belirtir.  
  
 `isDisabled`  
 Yürütme devre dışıysa `true`, aksi halde `false` .  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı olursa `JsNoError`, aksi halde bir hata kodu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)