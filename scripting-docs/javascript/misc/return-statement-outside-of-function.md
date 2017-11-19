---
title: "&#39; return &#39; deyimi işlev dışı | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.Help.SCRIPT1018
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 03568f9f-5f4f-4a10-a738-9a73f3832b9e
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 07b633c87dc11b291a5a5783f8121b2a368996d6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="39return39-statement-outside-of-function"></a>&#39; return &#39; deyimi işlev dışı
Kullanılan bir `return` genel kapsamlı bir deyiminde kodunuzun. `return` Deyimi yalnızca bir işlev gövdesi içinde görünmelidir.  
  
 Bir işlev çağırma `()` işleci bir ifadedir. Tüm ifadeler değerlere sahip; `return` deyimi, bir işlev tarafından döndürülen değerin belirtmek için kullanılır. Genel biçimi şöyledir:  
  
```  
  
return [ expression ];  
```  
  
 Zaman `return` deyimi yürütüldüğünde, *ifade* değerlendirilir ve işlev değeri olarak döndürdü. Herhangi bir ifade ise **tanımsız** döndürülür.  
  
 İşlev yürütülmesini durdurur `return` deyimi yürütüldüğünde, yine işlev gövdesi kalan diğer deyimler olsa bile. Bu kural için özel durum, **dönmek** deyimi oluşur içinde bir **deneyin** bloğu ve karşılık gelen **son** engelleyin, kod  **Son olarak** blok işlevi döndürmeden önce yürütülecek.  
  
 Bir işlev çalıştırmadan işlev gövdesi sonuna ulaştığında çünkü döndürürse, bir `return` açıklamadır, döndürülen değer **tanımsız** değeri (yani işlev sonucunu daha büyük bir ifadenin bir parçası olarak kullanılamaz ).  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Kaldırma `return` kodunuzu (genel kapsam) ana gövdesini from deyimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [return deyimi](../../javascript/reference/return-statement-javascript.md)   
 [İşlev nesnesi](../../javascript/reference/function-object-javascript.md)   
 [caller özelliği (işlev)](../../javascript/reference/caller-property-function-javascript.md)