---
title: Koleksiyonlar (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 23c26185-6a7b-4b69-9d22-63e1841b4905
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aa14730fffbf7c2747f15243590be89dc01a7ceb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="collections-javascript"></a>Koleksiyonlar (JavaScript)
Toplama nesneleri kullanabilirsiniz [harita](../../javascript/reference/map-object-javascript.md), [ayarlamak](../../javascript/reference/set-object-javascript.md), ve [WeakMap](../../javascript/reference/weakmap-object-javascript.md) değerleri ve nesneleri depolamak için. Bu nesneler, bir indis yerine bir anahtar ya da değer kullanarak üye eklemek veya almak için kolay yöntemler sağlar. Bir dizini kullanarak bir koleksiyon erişim üyelerine kullanmak bir `Array` nesnesi. Daha fazla bilgi için bkz: [kullanarak dizileri](../../javascript/advanced/using-arrays-javascript.md).  
  
> [!CAUTION]
>  `Map`, `Set`, ve `WeakMap` Internet Explorer 11 önce tarayıcı sürümlerinde desteklenmez. Sürüm desteği hakkında daha fazla bilgi için bkz: [sürüm bilgilerini](../../javascript/reference/javascript-version-information.md).  
  
## <a name="using-collections"></a>Koleksiyonları kullanma  
 `Map` Ve `WeakMap` nesneleri anahtar/değer çiftlerini depolamak ve ekleme, almak ve anahtarı kullanarak üyeleri kaldırma imkan tanır. Anahtar ve değer herhangi bir türde olabilir. `Set` Nesnesi herhangi bir tür değerleri depolar.  
  
 `Map` Ve `Set` nesneleri kullanarak koleksiyon üyeleri listeleme olanak tanır `forEach` yöntemi ve koleksiyon boyutunu kullanarak denetlemek için `size` yöntemi. `WeakMap` Nesnesi, buna karşılık, değil numaralandırılabilir. Bu koleksiyon için ana başvurular iyi korunmuyor. Kullanım `WeakMap` uygulama bellek koleksiyonda her üye korumak olup olmadığını belirlemek için atık toplayıcı istiyorsanız. Örneğin bu, önbelleğe alınan nesnelerin çok büyük olduğu ve gereksiz nesneleri bellekte tutmak istemediğiniz senaryoları önbelleğe alırken yararlı olabilir. Bazı senaryolarda bu nesneyi bellek sızıntılarını önlemek için kullanabilirsiniz.  
  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `Map` nesnesi. Bu örnekte, Üyeler her ikisini de kullanarak erişim `get` ve `forEach`. Geri çağırma işlevi `forEach` sağlamak geçerli koleksiyon öğesinin değeri, geçerli öğe ve koleksiyon nesnesi anahtarı en fazla üç parametre alabilir.  
  
```JavaScript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
m.set({x:1}, 3);  
  
document.write(m.get(2));  
document.write("<br />");  
  
m.forEach(function (value, key, mapObj) {  
    document.write(item.toString() + "<br />");  
});  
  
// Output:  
// red  
  
// black  
// red  
// 2  
// 3  
  
```  
  
 Kullanımını `WeakMap` benzer `Map`, yalnızca kullanarak üyeleri alabilir ancak bu `get`. Bir örnek için bkz: [WeakMap](../../javascript/reference/weakmap-object-javascript.md) nesnesi.  
  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `Set` nesnesi. Bu örnekte geri çağırma işlevi bir parametreyi alır, bu parametre geçerli koleksiyon öğesinin değeridir.  
  
```JavaScript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
s.add("founding father");  
  
s.forEach(function (value) {  
    document.write(item.toString() + ", ");  
});  
  
// Output:  
// Thomas Jefferson, 1776, founding father,  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş JavaScript](../../javascript/advanced/advanced-javascript.md)