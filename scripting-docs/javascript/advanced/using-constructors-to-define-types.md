---
title: Türler tanımlamak için oluşturucular kullanma | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- creating objects, constructor functions
- constructor functions
- functions, constructor functions
- objects, creating [JavaScript]
- constructors, creating
ms.assetid: e869702e-4caf-4513-8dd5-fe690535f8aa
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0bff42606fda27e00a537cc227a0b636e016f7c6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788822"
---
# <a name="using-constructors-to-define-types"></a>Türler Tanımlamak için Oluşturucular Kullanma
Bir oluşturucu belirli bir tür oluşturan bir işlevdir [nesne](../../javascript/objects-and-arrays-javascript.md). Bir oluşturucu çağırma **yeni** anahtar sözcüğü. Yerleşik JavaScript nesnelerine ve özel nesnelere sahip oluşturucu örneklerinden bazıları verilmiştir.  
  
## <a name="constructor-examples"></a>Oluşturucu Örnekleri  
  
```JavaScript  
// Creates a generic object.  
var myObject = new Object();  
// Creates a Date object.  
var myBirthday = new Date(1961, 5, 10);  
// Creates a user defined object.  
var myCar = new Car();  
```  
  
 Oluşturucu işlevi içeren **bu** yeni oluşturulan boş bir nesneye bir başvurusu olan anahtar sözcük. Özellikler oluşturup bunlara başlangıç değerleri vererek yeni nesneler başlatır. Oluşturucu, oluşturduğu nesneye referans döndürür.  
  
## <a name="writing-constructors"></a>Oluşturucuları Yazma  
 Nesneleri kullanarak oluşturabileceğiniz **yeni** birlikte işleci oluşturucu işlevleri gibi önceden tanımlanmış **NESNEOLUŞTUR()**, **Date()**, ve **Function()** . Ayrıca bir özellik ve yöntem kümesi tanımlayan özel oluşturucu işlevleri oluşturabilirsiniz. Bir özel oluşturucu örneği aşağıda verilmiştir.  
  
```JavaScript  
function Circle (xPoint, yPoint, radius) {  
    this.x = xPoint;  // The x component of the center of the circle.  
    this.y = yPoint;  // The y component of the center of the circle.  
    this.r = radius;  // The radius of the circle.  
}  
```  
  
 Circle kurucusunu çağırdığınızda, dairenin merkez noktası ve RADIUS için değerleri girersiniz. Üç özellik içeren bir Daire nesnesi elde edersiniz. Bir Daire nesnesini nasıl oluşturacağınız aşağıda verilmiştir.  
  
```JavaScript  
var aCircle = new Circle(5, 11, 99);  
```  
  
 Özel Oluşturucu ile oluşturulmuş tüm nesnelerin türüdür `object`. JavaScript'te yalnızca altı tür vardır: `object`, `function`, `string`, `number`, `boolean`, ve `undefined`. Daha fazla bilgi için bkz: [typeof işleci](../../javascript/reference/typeof-operator-decrementjavascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlama yöntemini kullanma](../../javascript/advanced/using-the-bind-method-javascript.md)