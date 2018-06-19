---
title: prototype özelliği (dizi) | Microsoft Docs
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
ms.assetid: 5fedf632-8316-4e5d-ab20-10e41aa4d9f8
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4fd5102fe2f49218de76c498a11256a6ef24ff0f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791213"
---
# <a name="prototype-property-array"></a>prototype Özelliği (Dizi)
Prototip dizinin bir sınıf için bir başvuru döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
array.prototype  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `array` Bağımsız değişkeni bir dizi adıdır.  
  
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
  
// Output: 25  
```  
  
 Tüm iç [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesneler sahip bir `prototype` salt okunur özellik. Özellikleri ve yöntemleri için prototip eklenebilir, ancak nesne farklı bir prototip atanmamış olabilir. Ancak, kullanıcı tanımlı nesneler, yeni bir prototip atanabilir.  
  
 Bu dil başvurusu iç her nesne için yöntem ve özellik listeleri hangilerinin nesnenin prototip parçası olan ve olmayan gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]