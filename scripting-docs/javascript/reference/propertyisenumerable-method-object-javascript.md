---
title: "Propertyısenumerable yöntemi (nesne) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: propertyIsEnumerable
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: propertyIsEnumerable property
ms.assetid: d90c7c2e-ea23-4710-a957-9aefbbd1f68b
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5664732db6a311586f11eb13eee4407fdf81410f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="propertyisenumerable-method-object-javascript"></a>propertyIsEnumerable Yöntemi (Nesne) (JavaScript)
Belirtilen özellik numaralandırılabilir olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
object. propertyIsEnumerable(proName)  
```  
  
## <a name="parameters"></a>Parametreler  
 `object`  
 Gerekli. Bir nesne örneği.  
  
 `proName`  
 Gerekli. Dize değeri, bir özellik adı.  
  
## <a name="remarks"></a>Açıklamalar  
 `propertyIsEnumerable` Yöntemi döndürür `true` varsa `proName` bulunmaktadır `object` ve kullanarak numaralandırılmış bir `For` döngü. `propertyIsEnumerable` Yöntemi döndürür `false` varsa `object` Belirtilen adda bir özellik içermiyor veya belirtilen özellik numaralandırılabilir değilse. Genellikle, önceden tanımlanmış özellikler numaralandırılabilir değildir, ancak kullanıcı tarafından tanımlanan her zaman numaralandırılabilir özelliklerdir.  
  
 `propertyIsEnumerable` Yöntemi prototip zincirindeki nesneleri dikkate almaz.  
  
## <a name="example"></a>Örnek  
  
```JavaScript  
var a = new Array("apple", "banana", "cactus");  
document.write(a.propertyIsEnumerable(1));  
  
// Output: true  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [prototype özelliği (nesne)](../../javascript/reference/prototype-property-object-javascript.md)