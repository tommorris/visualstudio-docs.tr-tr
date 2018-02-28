---
title: Beklenmeyen niceleyici (JavaScript) | Microsoft Docs
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
- VS.WebClient.Help.SCRIPT5018
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ba6d34f9-2d6f-486c-a929-6cd9818be322
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb6d6d3129057c399dd7369c6f69eb7396f07ab4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="unexpected-quantifier-javascript"></a>Beklenmeyen niceleyici (JavaScript)
Normal ifade arama deseni oluştururken, bir geçersiz yineleme faktörüyle bir desen öğesi oluşturdunuz. Örneğin, düzeni  
  
```  
/^+/  
```  
  
 geçersiz olduğundan öğesi ^ (giriş başlangıcı) bir yineleme faktörü sahip olamaz. Aşağıdaki tabloda, yineleme Etkenler olamaz öğeleri listeler.  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|^|Giriş başlangıcı|  
|$|Giriş sonu|  
|\b|Word sınır|  
|\B|Olmayan word sınır|  
|*|Sıfır veya daha fazla tekrarları|  
|+|Bir veya daha fazla tekrarları|  
|?|Sıfır veya bir tekrarları|  
|{n}|n tekrarları|  
|{n}|n veya daha fazla tekrarları|  
|{n, m}|M tekrarları, kapsayıcı için n|  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Yalnızca geçerli yineleme Etkenler arama deseni öğesi içeren emin olun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Normal ifade nesnesi](../../javascript/reference/regular-expression-object-javascript.md)   
 [Normal ifade sözdizimini (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)