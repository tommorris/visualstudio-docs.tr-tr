---
title: JsRuntimeAttributes numaralandırması | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsRuntimeAttributes
helpviewer_keywords:
- JsRuntimeAttributes enumeration
ms.assetid: f76d82e9-a695-4d6a-96c1-b3a4d27fed68
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3a7917ad5468b8d2924526f953ae444c5d8381eb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788630"
---
# <a name="jsruntimeattributes-enumeration"></a>JsRuntimeAttributes Numaralandırması
Bir çalışma zamanının öznitelikleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
enum JsRuntimeAttributes;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`JsRuntimeAttributeAllowScriptInterrupt`|Çalışma zamanı güvenilir kod kesintini desteklemelidir. Bu, az miktarda bir çalışma zamanı performansı karşılığında betik kesintisi için çalışma zamanının denetleneceği yerlerin sayısını artırır.|  
|`JsRuntimeAttributeDisableBackgroundWork`|Çalışma zamanı arka plan iş parçacıklarında herhangi bir iş yapmaz (atık toplama gibi).|  
|`JsRuntimeAttributeDisableEval`|`eval` veya `function` yapıcı kullanılması bir özel durum oluşturur.|  
|`JsRuntimeAttributeDisableNativeCodeGeneration`|Çalışma zamanı yerel kod oluşturmaz.|  
|`JsRuntimeAttributeEnableExperimentalFeatures`|Çalışma zamanı, tüm Deneysel özellikleri etkinleştirir.|  
|`JsRuntimeAttributeEnableIdleProcessing`|Ana bilgisayar `JsIdle`'i çağırır, bu nedenle boşta işlemi etkinleştirin. Aksi takdirde çalışma zamanı, belleği biraz daha agresif bir biçimde yönetir.|  
|`JsRuntimeAttributeDispatchSetExceptionsToDebugger`|Çağırma `JsSetException` gönderme hata ayıklayıcı bir özel durum nedeniyle bölüneceği iletmenize özel durumu (varsa) komut dosyası hata ayıklayıcısı kazandırır.|  
|`JsRuntimeAttributeNone`|Özel öznitelik yok.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)