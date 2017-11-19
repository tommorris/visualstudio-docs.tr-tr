---
title: "Koşullu derleme kapalı | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.Help.SCRIPT1030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 59a030b0-a6c6-47f2-b90e-c0ed204d5116
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8f2eabb900e24072c8f390061b5d6081de9bc889
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="conditional-compilation-is-turned-off"></a>Koşullu derleme kapalı
Koşullu derleme değişkeni ilk dönüş koşullu derleme olmadan üzerinde kullanma girişimi. Koşullu derleme üzerinde bildirir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] @ koşullu derleme değişkenleri olarak itibaren tanımlayıcıları yorumlamaya derleyici. Bu koşullu kodunuzu ifadesiyle başlayan tarafından yapın:  
  
```  
/*@cc_on @*/  
```  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Aşağıdaki deyim koşullu kodunuzu başlangıcına ekleyin:  
  
    ```JavaScript  
    /*@cc_on @*/  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koşullu derleme](../../javascript/advanced/conditional-compilation-javascript.md)   
 [Koşullu derleme değişkenleri](../../javascript/advanced/conditional-compilation-variables-javascript.md)   
 [@cc_onDeyimi](../../javascript/reference/at-cc-on-statement-javascript.md)   
 [@ifDeyimi](../../javascript/reference/at-if-statement-javascript.md)   
 [@setDeyimi](../../javascript/reference/at-set-statement-javascript.md)