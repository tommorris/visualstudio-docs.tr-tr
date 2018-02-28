---
title: WeakMap nesnesi (JavaScript) | Microsoft Docs
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
- WeakMap
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 4682d2dc-caf9-4fa8-8313-a0a0b804fd1d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8de97f8acb94921090696e9019a1df5d945db7c6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="weakmap-object-javascript"></a>WeakMap Nesnesi (JavaScript)
Her anahtar nesne başvurusu olduğu anahtar/değer çiftlerinin koleksiyonu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
weakmapObj = new WeakMap()  
```  
  
## <a name="remarks"></a>Açıklamalar  
 A `WeakMap` nesne NUMARALANDIRILAMAZ.  
  
 Mevcut bir anahtarı kullanarak koleksiyona bir değer eklerseniz, yeni değer eski değerin yerini alır.  
  
 İçinde bir `WeakMap` nesnesi, anahtar nesnelere başvurular 'zayıf' tutulur. Bunun anlamı `WeakMap` oluşmasını anahtar nesnelerde çöp koleksiyonundan önlemez. Başvuru olduğunda (dışında `WeakMap`) anahtar nesnelere atık toplayıcı anahtar nesneler toplayabilir.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda özelliklerini `WeakMap` nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[Oluşturucusu](../../javascript/reference/constructor-property-weakmap.md)|Oluşturur işlevini belirten bir `WeakMap`.|  
|[prototip](../../javascript/reference/prototype-property-weakmap.md)|İçin prototip bir başvuru döndürür bir `WeakMap`.|  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `WeakMap` nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Temizle](../../javascript/reference/clear-method-weakmap-javascript.md)|Tüm öğeleri kaldırır bir `WeakMap`.|  
|[Sil](../../javascript/reference/delete-method-weakmap-javascript.md)|Belirtilen bir öğesinden kaldırır bir `WeakMap`.|  
|[Al](../../javascript/reference/get-method-weakmap-javascript.md)|Belirtilen bir öğeden döndürür bir `WeakMap`.|  
|[sahip](../../javascript/reference/has-method-weakmap-javascript.md)|Döndürür `true` varsa `WeakMap` belirtilen bir öğe içeriyor.|  
|[ayarlama](../../javascript/reference/set-method-weakmap-javascript.md)|Yeni bir öğe ekler bir `WeakMap`.|  
|[toString](../../javascript/reference/tostring-method-weakmap-javascript.md)|Bir dize gösterimini döndürür bir `WeakMap`.|  
|[valueOf](../../javascript/reference/valueof-method-weakmap-javascript.md)|Belirtilen nesne ilkel değerini döndürür.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, üye eklemek gösterilmiştir bir `WeakMap` nesne ve sonra bunları alır.  
  
```JavaScript  
var dog = {  
    breed: "yorkie"  
}  
  
var cat = {  
    breed: "burmese"  
}  
  
var wm = new WeakMap();  
wm.set(dog, "fido");  
wm.set(cat, "pepper");  
  
document.write(wm.get(dog) + ": ");  
document.write(dog.breed);  
document.write("<br />");  
document.write(wm.get(cat) + ": ");  
document.write(cat.breed);  
  
// Output:  
// fido: yorkie  
// pepper: burmese  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]