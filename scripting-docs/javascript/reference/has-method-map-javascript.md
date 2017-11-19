---
title: "has yöntemi (eşleme) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 876df854-2941-4db2-92c6-1b497840b169
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 48228b495c845bef91caa0b85e67980100a6f790
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="has-method-map-javascript"></a>has Yöntemi (Eşleme) (JavaScript)
Döndürür `true` harita belirtilen öğeyi içeriyorsa.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
mapObj.has(key)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `mapObj`  
 Gerekli. A `Map` nesnesi.  
  
 `key`  
 Gerekli. Test edilecek öğe anahtarı.  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 `true`Harita belirtilen öğeyi içeriyorsa.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir üye eklemek gösterilmiştir bir `Map` ve harita içerip içermediğini denetleyin.  
  
```JavaScript  
var m = new Map();  
m.set(2, "red");  
  
document.write(m.has(2));  
  
// Output:  
// true  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]