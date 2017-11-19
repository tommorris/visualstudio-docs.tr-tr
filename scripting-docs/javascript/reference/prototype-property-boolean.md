---
title: "prototype özelliği (Boolean) | Microsoft Docs"
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
ms.assetid: e4f07cb5-3462-488c-a418-76064ab10eae
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 52d2d241c4d550fe4491ea827fab9d586281242d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-boolean"></a>prototype Özelliği (Boolean)
Prototip başvuru için bir Boole değeri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
boolean.prototype  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `boolean` Bağımsız değişkeni bir nesne adıdır.  
  
 `prototype` Özelliği, temel bir işlev nesneleri bir sınıfa kümesi sağlar. Bir nesnenin "Bu nesneye atanmış prototip davranışını devral" yeni örnekleri. Özellikleri ve yöntemleri için prototip eklenebilir, ancak yerleşik nesneler farklı prototip atanmamış olabilir.  
  
 Örneğin, bir yöntem eklemek için `Boolean` dizisinin en büyük öğenin değerini döndürür nesne, işlev bildirme, ekleyin `Boolean.prototype`ve ardından onu kullanabilirsiniz.  
  
```JavaScript  
function isFalse( ){  
    if (this.toString() == "false")  
         return true;  
    else  
        return false;  
}  
Boolean.prototype.isFalse = isFalse;  
var bool = new Boolean(1);  
document.write(bool.isFalse());  
  
// Output:  
// false  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]