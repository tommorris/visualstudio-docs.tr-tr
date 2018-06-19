---
title: isPrototypeOf yöntemi (nesne) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- isPrototypeOf
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- isPrototypeOf method
ms.assetid: 9c821319-c208-480f-915e-565ef6e017b6
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 47ce97faecfade089bbf0b7a725a02ee73b54718
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790724"
---
# <a name="isprototypeof-method-object-javascript"></a>isPrototypeOf Yöntemi (Nesne) (JavaScript)
Bir nesnenin, başka bir nesnenin prototip zincirinde bulunup bulunmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
prototype.isPrototypeOf(object)  
```  
  
## <a name="parameters"></a>Parametreler  
 `prototype`  
 Gerekli. Bir nesne prototipi.  
  
 `object`  
 Gerekli. Prototip zinciri denetlenecek olan başka bir nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 `isPrototypeOf` Yöntemi döndürür `true` varsa `object` sahip `prototype` kendi prototip zincirindeki. Prototip zinciri, işlevselliği aynı nesne türü örnekleri arasında paylaşmak için kullanılır. `isPrototypeOf` Yöntemi döndürür `false` zaman `object` bir nesne değil veya ne zaman `prototype` prototip zincirindeki görünmez `object`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanımını göstermektedir `isPrototypeOf` yöntemi.  
  
```JavaScript  
function Rectangle() {  
}  
  
var rec = new Rectangle();  
  
document.write(Rectangle.prototype.isPrototypeOf(rec));  
  
// Output: true  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [prototype özelliği (nesne)](../../javascript/reference/prototype-property-object-javascript.md)