---
title: constructor özelliği (dizi) | Microsoft Docs
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
ms.assetid: b78d517b-cb56-4866-b30f-ef8121a27843
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ca779a2fa2356c1f3e1ca816f16531c0930459a4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789047"
---
# <a name="constructor-property-array"></a>constructor Özelliği (Dizi)
Bir diziyi oluşturan işlevi belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
array.constructor  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `array` bir dizi adıdır.  
  
 `constructor` Özelliği bir prototip olan her nesneyi prototip bir üyesidir. Bu tüm iç içerir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] dışında nesneleri `Global` ve `Math` nesneleri. `constructor` Özelliği, belirli nesne örneklerini oluşturur işlevi için bir başvuru içeriyor.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek constructor özelliği kullanımını göstermektedir.  
  
```JavaScript  
var x = new Array();  
  
if (x.constructor == Array)  
    document.write("Object is an Array.");  
else  
    document.write("Object is not an Array.");  
  
// Output:  
// Object is an Array.  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]