---
title: Boolean bekleniyor | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.Help.SCRIPT5010
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 35d71b7f-53fd-44c4-a7c7-b1550c65cfd4
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 600ab26f60c2196ebc682adcffcd6b24c23cd358
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="boolean-expected"></a>Boolean bekleniyor
Çağrılacak çalıştı **Boolean.prototype.toString** veya **Boolean.prototype.valueOf** dışında bir türde bir nesne üzerinde yöntemi `Boolean`. Bu tür çağırma nesne türünde olmalıdır `Boolean`. Örneğin:  
  
```JavaScript  
var o = new Object;  
o.f = Boolean.prototype.toString;  
o.f();  
```  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Yalnızca Boole çağırma**. prototype.toString** veya **Boolean.prototype.valueOf** türündeki nesneleri yöntemlere **Boolean.**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Boole nesnesi](../../javascript/reference/boolean-object-javascript.md)   
 [Veri türleri](../../javascript/data-types-javascript.md)   
 [Program akışı denetimi](../../javascript/controlling-program-flow-javascript.md)   
 [Veri kopyalama, geçirme ve karşılaştırma](../../javascript/advanced/copying-passing-and-comparing-data-javascript.md)