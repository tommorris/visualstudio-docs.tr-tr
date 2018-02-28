---
title: "Can &#39; sahip t &#39; sonu &#39; döngü dışında | Microsoft Docs"
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
- VS.WebClient.Help.SCRIPT1019
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 11d02172-2a78-4705-a730-d21111db5f42
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bb23f1bc3de087515cad9ba4910cf2ebaf640353
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="can39t-have-39break39-outside-of-loop"></a>Can &#39; sahip t &#39; sonu &#39; döngü dışında
Kullanmaya çalıştığınız **sonu** anahtar sözcüğü bir döngü dışında. **Sonu** bir döngü sonlandırmak için kullanılan anahtar sözcüğü veya `switch` deyimi. Döngü gövdesine gömülü gerekir veya `switch` deyimi. Ancak, bir **etiket** break anahtar sözcüğü izleyebilirsiniz.  
  
```  
break labelname;  
```  
  
 Etiketli biçiminde yeterlidir **sonu** kullanırken anahtar sözcüğü, döngüler iç içe geçmiş veya `switch` deyimleri ve en içteki değil bir döngü dışında bölün gerekiyorsa.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Emin olun **sonu** anahtar sözcüğü bir kapsayan döngü veya anahtar deyimi içinde görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [break deyimi](../../javascript/reference/break-statement-javascript.md)   
 [Program akışı denetimi](../../javascript/controlling-program-flow-javascript.md)   
 [Betiklerinizin sorunlarını giderme](../../javascript/advanced/troubleshooting-your-scripts-javascript.md)