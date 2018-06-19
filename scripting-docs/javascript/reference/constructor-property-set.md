---
title: constructor özelliği (küme) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f350b7eb-8994-40bf-9011-f8b20fcef34f
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ea9af6d60c2ae8bc8a383c4cebbf0955e183895e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790373"
---
# <a name="constructor-property-set"></a>constructor Özelliği (Küme)
Bir küme oluşturur işlevi belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
set.constructor  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `set` kümesinin adı.  
  
 `constructor` Özelliği bir prototip olan her nesneyi prototip bir üyesidir. Bu dışındaki tüm iç JavaScript nesneleri içerir `Global` ve `Math` nesneleri. `constructor` Özelliği, belirli nesne örneklerini oluşturur işlevi için bir başvuru içeriyor.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]