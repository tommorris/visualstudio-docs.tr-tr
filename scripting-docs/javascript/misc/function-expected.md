---
title: "İşlev bekleniyor | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5002
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f62ade94-9f6f-4832-9b9b-49a06a385bbe
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aa2db3e95d4baece288c9f984a7a9cf7a82c9d1d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="function-expected"></a>İşlev bekleniyor
Aşağıdakilerden birini çağırma denedi ya da **işlev prototipi** yöntemleri değil bir nesne üzerinde bir `Function` nesnesi veya bir işlev çağrısı bağlamında bir nesne kullanılan. Örneğin, aşağıdaki kodu çünkü bu hatayı üreten **örnek** bir işlev değil.  
  
```JavaScript  
var example = new Object();  // Create a new object called "example".  
var x = example();           // Try and call example as if it were a function.  
```  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Yalnızca çağrısı **işlev prototipi** yöntemlere `Function` nesneleri.  
  
-   İşlev çağırma işleci kullandığından emin olun `()` yalnızca işlevleri çağırmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlev nesnesi](../../javascript/reference/function-object-javascript.md)   
 [prototype özelliği (nesne)](../../javascript/reference/prototype-property-object-javascript.md)