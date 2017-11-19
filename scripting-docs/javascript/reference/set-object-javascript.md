---
title: "Kümesi nesnesi (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Set
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 4a4dd749-2a76-44fb-9cb0-a3ef317f75fb
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5134ec09c9a8642499212af9dd5fd44de0068adc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="set-object-javascript"></a>Küme Nesnesi (JavaScript)
Herhangi bir türde olabilir benzersiz değerler koleksiyonu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
setObj = new Set()     
```  
  
## <a name="remarks"></a>Açıklamalar  
 Benzersiz olmayan bir değer eklemeyi deneyin bir `Set`, yeni değer koleksiyona eklenemiyor.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda özelliklerini `Set` nesnesi.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[Oluşturucusu](../../javascript/reference/constructor-property-set.md)|Bir küme oluşturur işlevi belirtir.|  
|[prototip](../../javascript/reference/prototype-property-set.md)|Prototip kümesine ilişkin bir başvuru döndürür.|  
|[boyutu](../../javascript/reference/size-property-set-javascript.md)|Bir kümedeki öğe sayısını döndürür.|  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `Set` nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[ekleme](../../javascript/reference/add-method-set-javascript.md)|Bir öğenin bir kümesine ekler.|  
|[Temizle](../../javascript/reference/clear-method-set-javascript.md)|Tüm öğeleri bir kümeden kaldırır.|  
|[Sil](../../javascript/reference/delete-method-set-javascript.md)|Belirtilen öğe bir kümeden kaldırır.|  
|[forEach](../../javascript/reference/foreach-method-set-javascript.md)|Kümedeki her öğe için belirtilen eylemi gerçekleştirir.|  
|[sahip](../../javascript/reference/has-method-set-javascript.md)|Döndürür `true` kümesi belirtilen öğeyi içeriyorsa.|  
|[toString](../../javascript/reference/tostring-method-set-javascript.md)|Bir dize gösterimini döndürür.|  
|[valueOf](../../javascript/reference/valueof-method-set-javascript.md)|Belirtilen nesne ilkel değerini döndürür.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir grup için üye ekleyin ve bunları almak gösterilmiştir.  
  
```JavaScript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
s.add("founding father");  
  
s.forEach(function (item) {  
    document.write(item.toString() + ", ");  
});  
  
// Output:  
// Thomas Jefferson, 1776, founding father,  
  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]