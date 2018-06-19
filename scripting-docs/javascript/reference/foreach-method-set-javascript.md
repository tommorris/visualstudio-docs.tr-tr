---
title: forEach yöntemi (küme) (JavaScript) | Microsoft Docs
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
ms.assetid: 813bff6e-6098-4260-ab6e-b0d2da6be94d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b89c56b54fd74c25c43a84f2f0fd68922aa9f637
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790538"
---
# <a name="foreach-method-set-javascript"></a>forEach Yöntemi (Küme) (JavaScript)
Kümedeki her öğe için belirtilen eylemi gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
setObj.forEach(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>Parametreler  
 `setObj`  
 Gerekli. A `Set` nesnesi.  
  
 `callbackfn`  
 Gerekli. `callbackfn`en fazla üç bağımsız değişken kabul eder. İşlev, `forEach` kümesindeki her bir öğe için bir kez çağırır.  
  
 `thisArg`  
 İsteğe bağlı. Bir nesne, `this` anahtar sözcüğü için söz başvurabilir `callbackfn` işlevi. Varsa `thisArg` atlanırsa, `undefined` olarak kullanılan `this` değeri.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `callbackfn` bağımsız değişkeni bir işlev nesnesi değil bir `TypeError` özel durumu oluşur.  
  
## <a name="remarks"></a>Açıklamalar  
 Geri çağırma işlevinin sözdizimi aşağıdaki gibidir:  
  
 `function callbackfn(value, key, setObj)`  
  
 Aşağıdaki tabloda gösterildiği gibi en fazla üç parametre kullanarak geri çağırma işlevi bildirebilirsiniz.  
  
|Geri çağırma bağımsız değişkeni|Tanım|  
|-----------------------|----------------|  
|`value`|Kümesinde yer alan bir değer.|  
|`key`|Kümesinde yer alan bir değer. Bu değer ile aynı olacak şekilde bir anahtarı yok ayarlanmış `value`.|  
|`setObj`|`Set` Gezinmesine nesnesi.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `forEach`. `callbackfn` Bağımsız değişkeni geri çağırma işlevi kodunu içerir.  
  
```JavaScript  
var s = new Set();  
  
s.add("scale");  
s.add(10);  
s.add("5");  
  
s.forEach(function(item, sameItem, s) {  
    document.write("Size of the set object is: " + s.size + "<br />");  
    document.write("Deleting item: " + item + "<br />");  
    s.delete(sameItem);  
});  
  
// Output:  
// Size of the set object is: 3  
// Deleting item: scale  
// Size of the set object is: 2  
// Deleting item: 10  
// Size of the set object is: 1  
// Deleting item: 5  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, ayrıca üyeleri kümesinden geri çağırma işlevi yalnızca tek bir parametre geçirerek alabilirsiniz olduğunu gösterir.  
  
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