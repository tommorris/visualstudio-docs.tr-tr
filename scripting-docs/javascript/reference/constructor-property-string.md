---
title: constructor özelliği (dize) | Microsoft Docs
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
ms.assetid: ef0e9c82-4651-4404-87b1-d00cad38c6f9
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7f1942073a9950a77c7e0cae759a9653318d8a18
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790328"
---
# <a name="constructor-property-string"></a>constructor Özelliği (Dize)
Bir dize oluşturur işlevi belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
string.constructor  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli `string` bir dize adı.  
  
 `constructor` Özelliği bir prototip olan her nesneyi prototip bir üyesidir. Bu tüm iç içerir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] dışında nesneleri `Global` ve `Math` nesneleri. `constructor` Özelliği, belirli nesne örneklerini oluşturur işlevi için bir başvuru içeriyor.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek constructor özelliği kullanımını göstermektedir.  
  
```JavaScript  
var x = new String();  
  
if (x.constructor == String)  
    document.write("Object is a String.");  
else  
    document.write("Object is not a String.");  
  
// Output:  
// Object is a String.  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]