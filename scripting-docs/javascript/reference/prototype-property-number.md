---
title: prototype özelliği (sayı) | Microsoft Docs
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
ms.assetid: d5fb87af-fc3a-4469-8dde-d31daf654f94
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2dba8b8886b4fdbc48a662796863b1dfca019aec
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791279"
---
# <a name="prototype-property-number"></a>prototype Özelliği (Sayı)
Prototip sayının bir sınıf için bir başvuru döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
number.prototype  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `number` Bağımsız değişkeni bir sayı adıdır.  
  
 Kullanım `prototype` temel nesne sınıfı için işlevselliği sağlamak için özellik. Bir nesnenin "Bu nesneye atanmış prototip davranışını devral" yeni örnekleri.  
  
 Örneğin, bir yöntem eklemek için `Number` sayısı (tamsayı), rakamları döndürür nesne, işlev bildirme, ekleyin `Number.prototype`ve ardından onu kullanabilirsiniz.  
  
```JavaScript  
function number_digits() {  
    var digits = 0;  
    var num = this;  
    while (num) >= 1) {  
        digits++;  
        num /= 10;  
    }  
    return digits;  
}  
  
Number.prototype.digits = number_digits;  
var myNumber = new Number(3456.789);  
document.write(myNumber.digits());  
// Output:  
// 4  
```  
  
 Tüm iç [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesneler sahip bir `prototype` salt okunur özellik. Özellikleri ve yöntemleri için prototip eklenebilir, ancak nesne farklı bir prototip atanmamış olabilir. Ancak, kullanıcı tanımlı nesneler, yeni bir prototip atanabilir.  
  
 Bu dil başvurusu iç her nesne için yöntem ve özellik listeleri hangilerinin nesnenin prototip parçası olan ve olmayan gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]