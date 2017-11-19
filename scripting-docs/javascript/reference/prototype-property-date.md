---
title: "prototype özelliği (tarih) | Microsoft Docs"
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
ms.assetid: 44f9c637-7da7-4833-906d-358506f32ced
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8c0b337964d2a2fe17a4e9a7906d81069470e61b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="prototype-property-date"></a>prototype Özelliği (Tarih)
Prototip başvuru için bir tarihi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
date.prototype  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `date` Bağımsız değişkeni bir nesne adıdır.  
  
 Kullanım `prototype` özelliği bir tarih olarak işlevselliği temel kümesi sağlar. Bir nesnenin "Bu nesneye atanmış prototip davranışını devral" yeni örnekleri.  
  
 Örneğin, bir yöntem eklemek için `Date` dizisinin en büyük öğenin değerini döndürür nesne, işlev bildirme, ekleyin `Date.prototype`ve ardından onu kullanabilirsiniz.  
  
```JavaScript  
function max( ){  
    var max = new Date();  
    max.setFullYear(2200, 01, 01);  
    return max;  
}  
Date.prototype.maxDate = max;  
var myDate = new Date();  
  
if (myDate < myDate.maxDate())  
    document.write("today isn't the max");  
else if (myDate == myDate.maxDate())  
    document.write("today is the max");   
  
// Output:  
// today isn't the max  
  
```  
  
 Tüm iç [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesneler sahip bir `prototype` salt okunur özellik. Özellikleri ve yöntemleri için prototip eklenebilir, ancak nesne farklı bir prototip atanmamış olabilir. Ancak, kullanıcı tanımlı nesneler, yeni bir prototip atanabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]