---
title: "Jsref tür | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 6aafc39f-6b9c-457f-8bf0-48831bffe9b8
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d9d4c478a45f53e83dfa59fdde21cfa4c988c92e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="jsref-typedef"></a>JsRef Tür Tanımı
Chakra atık toplayıcısı tarafından sahip olunan bir nesne başvurusu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef void *JsRef;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Chakra çalışma zamanı, yerel değişkenler veya parametrelerde (yani yığın üzerinde) saklandıkları sürece JsRef başvurularını otomatik olarak izler. Nesnenin yaşam süresini yönetmek için JsRef'in yığından başka bir yerde depolanması, JsAddRef ve JsRelease'in çağırılmasını gerektirir, aksi halde atık toplayıcısı nesne hala kullanımdayken nesneyi boşaltabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** jsrt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)