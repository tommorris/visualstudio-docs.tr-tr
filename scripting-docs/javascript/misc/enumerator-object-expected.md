---
title: Numaralandırıcı nesne bekleniyor | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5015
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: dc6e32c1-a6e6-4e12-ac99-e3f65f91c8d7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 485e6e387f07fd3a54727f5f8e08c0a00743c6d9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788672"
---
# <a name="enumerator-object-expected"></a>Numaralandırıcı nesne bekleniyor
Çağrılacak çalıştı **Enumerator.prototype.atEnd, Enumerator.prototype.item, Enumerator.prototype.moveFirst,** veya **Enumerator.prototype.moveNext** başka bir türde bir nesne üzerinde yöntemi daha `Enumerator`. Bu tür çağırma nesne türünde olmalıdır `Enumerator`. Bu kural sonları kod örneğini şöyledir:  
  
```JavaScript  
var o = new Object;  
o.f = Enumerator.prototype.atEnd;  
o.f();  
```  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Yalnızca çağırma **Enumerator.prototype.atEnd**, **Enumerator.prototype.item**, **Enumerator.prototype.moveFirst**, veya  **Enumerator.prototype.moveNext** türündeki nesneleri yöntemlere `Enumerator`. Nesnenizin olmadığını öğrenmek için olan bir `Enumerator` nesne, kullanın:  
  
    ```  
    if(x instanceof Enumerator)  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırıcı nesnesi](../../javascript/reference/enumerator-object-javascript.md)