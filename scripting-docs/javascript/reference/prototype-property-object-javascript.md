---
title: "prototype özelliği (nesne) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Prototype
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- inheritance, objects
- Prototype property
ms.assetid: 9fc434a1-5995-4fcb-a4e8-00e7f615aaa2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a73d213b6b17f5046eb1f4c498aeb223f942f2d8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-object-javascript"></a>prototype Özelliği (Nesne) (JavaScript)
Bir nesne sınıfı için prototipe bir başvuru döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
objectName.prototype  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `objectName` Bağımsız değişkeni bir nesne adıdır.  
  
 Kullanım `prototype` temel nesne sınıfı için işlevselliği sağlamak için özellik. Bir nesnenin "Bu nesneye atanmış prototip davranışını devral" yeni örnekleri.  
  
 Örneğin, bir yöntem eklemek için `Array` dizisinin en büyük öğenin değerini döndürür nesne, işlev bildirme, ekleyin `Array.prototype`ve ardından onu kullanabilirsiniz.  
  
```JavaScript  
function array_max( ){  
    var i, max = this[0];  
    for (i = 1; i < this.length; i++)  
    {  
    if (max < this[i])  
    max = this[i];  
    }  
    return max;  
}  
Array.prototype.max = array_max;  
var myArray = new Array(7, 1, 3, 11, 25, 9  
);  
document.write(myArray.max());  
  
// Output:  
// 25  
  
```  
  
 Tüm iç [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesneler sahip bir `prototype` salt okunur özellik. Özellikleri ve yöntemleri için prototip eklenebilir, ancak nesne farklı bir prototip atanmamış olabilir. Ancak, kullanıcı tanımlı nesneler, yeni bir prototip atanabilir.  
  
 Bu dil başvurusu iç her nesne için yöntem ve özellik listeleri hangilerinin nesnenin prototip parçası olan ve olmayan gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [constructor özelliği (nesne)](../../javascript/reference/constructor-property-object-javascript.md)