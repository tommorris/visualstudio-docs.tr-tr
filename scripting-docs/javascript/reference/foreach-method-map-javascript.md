---
title: forEach yöntemi (eşleme) (JavaScript) | Microsoft Docs
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
ms.assetid: 9cdf0adc-77c7-4407-8ba7-ada0fb09e507
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 549d7d625fb4dfe88b2db69e6aa0ff66c7e90f66
ms.sourcegitcommit: 37144589d9f850ff81ec7bfb884429989925a43d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/19/2018
ms.locfileid: "34335807"
---
# <a name="foreach-method-map-javascript"></a>forEach Yöntemi (Eşleme) (JavaScript)
Bir harita her öğe için belirtilen eylemi gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```JavaScript  
mapObj.forEach(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>Parametreler  
 `mapObj`  
 Gerekli. A `Map` nesnesi.  
  
 `callbackfn`  
 Gerekli. İşlev, `forEach` eşlemesindeki her öğe için bir kez çağırır. `callbackfn` en fazla üç bağımsız değişken kabul eder. `forEach` çağrıları `callbackfn` işlev eşleme her öğe için bir kez.  
  
 `thisArg`  
 İsteğe bağlı. Bir nesne, `this` anahtar sözcüğü için söz başvurabilir `callbackfn` işlevi. Varsa `thisArg` atlanırsa, `undefined` olarak kullanılan `this` değeri.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Varsa `callbackfn` bağımsız değişkeni bir işlev nesnesi değil bir `TypeError` özel durumu oluşur.  
  
## <a name="remarks"></a>Açıklamalar  
 Geri çağırma işlevinin sözdizimi aşağıdaki gibidir:  
  
 `function callbackfn(value, key, mapObj)`  
  
 Aşağıdaki tabloda gösterildiği gibi en fazla üç parametre kullanarak geri çağırma işlevi bildirebilirsiniz.  
  
|Geri çağırma bağımsız değişkeni|Tanım|  
|-----------------------|----------------|  
|`value`|Eşleme içinde yer alan bir değer.|  
|`key`|Eşleme içinde bulunan anahtar.|  
|`mapObj`|`Map` Gezinmesine nesnesi.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek üyeleri almak nasıl gösterir bir `Map` kullanarak `forEach`.  
  
```JavaScript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
m.set({x:1}, 3);  
  
m.forEach(function (value, key, mapObj) {  
    document.write(value.toString() + "<br />");  
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
