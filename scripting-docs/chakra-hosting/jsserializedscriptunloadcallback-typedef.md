---
title: JsSerializedScriptUnloadCallback typedef | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d18c392-cca0-411e-9f2b-0d788b16161a
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6f485d31367f189231d354c653c8e58cc8656eb9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788471"
---
# <a name="jsserializedscriptunloadcallback-typedef"></a>JsSerializedScriptUnloadCallback typedef
Betik yürütme ilgili tüm kaynaklarla bittiğinde çalışma zamanı tarafından çağrılır.     Arayan kaynak yüklerse, bayt kodu ve bağlam şu anda boş.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
 typedef void (CALLBACK * JsSerializedScriptUnloadCallback)(  
  _In_ JsSourceContext sourceContext  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `sourceContext`  
 Bağlam geçirilen `JsParseSerializedScriptWithCallback` veya `JsRunSerializedScriptWithCallback`.  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!WARNING]
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)