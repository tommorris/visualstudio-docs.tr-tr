---
title: Throw ardından aynı kaynak satırdaki bir ifade tarafından gerekir | Microsoft Docs
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
- VS.WebClient.Help.SCRIPT1035
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b03b7747-01a1-40c6-af80-a1dd70bc5781
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7179a22d2713c9ddc894618bd6921f3f873f2ad8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788771"
---
# <a name="throw-must-be-followed-by-an-expression-on-the-same-source-line"></a>Throw ardından aynı kaynak satırdaki bir ifade gelmelidir
Kullanılan `throw` anahtar sözcüğü, ancak bir ifade ile aynı kaynak satırdaki izleyerek değil. A `throw` deyimi iki bölümden oluşur: `throw` anahtar sözcüğünü oluşturulmasına ifadeyle,. Örneğin:  
  
```JavaScript  
if (denominator == 0) {  
 throw new DivideByZeroException();  
}  
```  
  
 Bu iki bileşenin bölünemez.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Olduğundan emin olun `throw` anahtar sözcüğü ve oluşturulmasına ifadesi aynı çizgi üzerinde görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata nesnesi](../../javascript/reference/error-object-javascript.md)   
 [throw deyimi](../../javascript/reference/throw-statement-javascript.md)   
 [try... catch... finally deyimi](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)