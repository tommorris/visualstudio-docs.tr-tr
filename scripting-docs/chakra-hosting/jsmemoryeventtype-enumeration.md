---
title: JsMemoryEventType numaralandırması | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsMemoryEventType
helpviewer_keywords:
- JsMemoryEventType enumeration
ms.assetid: b4b176b6-b536-472e-8999-95b681a1df55
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ef39008ba84337cebdc9613db17cc9fbdfc8aa79
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788456"
---
# <a name="jsmemoryeventtype-enumeration"></a>JsMemoryEventType Numaralandırması
Ayırma geri çağırma olay türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
enum JsMemoryEventType;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`JsMemoryAllocate`|Bellek ayırma için bir istek gösterir.|  
|`JsMemoryFailure`|Başarısız bir ayırma olayını gösterir.|  
|`JsMemoryFree`|Bir bellek boşaltma olayını gösterir.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)