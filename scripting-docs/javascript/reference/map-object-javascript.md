---
title: Harita nesnesi (JavaScript) | Microsoft Docs
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
- Map
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: a91dbcbe-f58d-41a0-be15-8c9d30020327
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d89890f9fecaf61e47e136734ed7fefb7b73cabd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="map-object-javascript"></a>Eşleme Nesnesi (JavaScript)
Anahtar/değer çiftlerinin koleksiyonu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
mapObj = new Map()  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Anahtarlar ve değerler koleksiyonu içinde herhangi bir türde olabilir. Mevcut bir anahtarı kullanarak koleksiyona bir değer eklerseniz, yeni değer eski değerin yerini alır.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda özelliklerini `Map` nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[Oluşturucusu](../../javascript/reference/constructor-property-map.md)|Bir harita oluşturur işlevi belirtir.|  
|[prototip](../../javascript/reference/prototype-property-map.md)|Bir harita prototipi bir başvuru döndürür.|  
|[boyutu](../../javascript/reference/size-property-map-javascript.md)|Bir harita öğe sayısını döndürür.|  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `Map` nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Temizle](../../javascript/reference/clear-method-map-javascript.md)|Tüm öğeleri bir eşlemesinden kaldırır.|  
|[Sil](../../javascript/reference/delete-method-map-javascript.md)|Belirtilen öğe bir eşlemesinden kaldırır.|  
|[forEach](../../javascript/reference/foreach-method-map-javascript.md)|Bir harita her öğe için belirtilen eylemi gerçekleştirir.|  
|[Al](../../javascript/reference/get-method-map-javascript.md)|Belirtilen öğe bir eşlemesinden döndürür.|  
|[sahip](../../javascript/reference/has-method-map-javascript.md)|Döndürür `true` harita belirtilen öğeyi içeriyorsa.|  
|[ayarlama](../../javascript/reference/set-method-map-javascript.md)|Yeni bir öğe için bir harita ekler.|  
|[toString](../../javascript/reference/tostring-method-map-javascript.md)|Bir harita dize gösterimini döndürür.|  
|[valueOf](../../javascript/reference/valueof-method-map-javascript.md)|Belirtilen nesne ilkel değerini döndürür.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, üye eklemek gösterilmiştir bir `Map` ve sonra bunları alır.  
  
```JavaScript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
m.set({x:1}, 3);  
  
m.forEach(function (item, key, mapObj) {  
    document.write(item.toString() + "<br />");  
});  
  
document.write("<br />");  
document.write(m.get(2));  
  
// Output:  
// black  
// red  
// 2  
// 3  
//  
// red  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]