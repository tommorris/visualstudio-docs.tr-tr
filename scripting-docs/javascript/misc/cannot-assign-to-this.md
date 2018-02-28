---
title: Olamaz atanacak &#39; &#39; | Microsoft Docs
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
- VS.WebClient.Help.SCRIPT5000
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ba2b0a2b-f0f8-4698-b335-a4ab6c166671
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c164b9b7d2989076a9dc0ef0bafba6159bc08885
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="cannot-assign-to-39this39"></a>Olamaz atanacak &#39; &#39;
Bir değer atadığınız çalışıldı **bu**. **Bu** olan bir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] ya da başvuruyor anahtar sözcüğü:  
  
-   şu anda yürütülmekte olan bir yöntem nesnesi  
  
-   Genel nesne geçerli bir yöntem yoktur (veya yöntemi başka bir nesneye ait değil varsa).  
  
 Bir yöntem bir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesne üzerinden çağrılan işlev. Bir yöntemin içinde **bu** sözcüktür yöntemi üzerinden çağrıldığı nesneye bir başvurusu (sınıf oluşturucu çağırarak oluşturulan nesne olmasını olur **yeni** işleci).  
  
 Bir yöntem içinde kullandığınız **bu** geçerli nesne, ancak için başvurmak için yeni bir değer atayamazsınız **bu**.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Atamak çalışmayın **bu**. Bir özellik veya yöntem başlatılan bir nesnenin erişmek için nokta işleci kullanın (örneğin, yuvarlak**.** RADIUS).  
  
    > [!NOTE]
    >  Bir kullanıcı tarafından oluşturulan değişken adlandıramazsınız **bu**; bu bir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] ayrılmış sözcük.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bu bildirimi](../../javascript/reference/this-statement-javascript.md)   
 [Betiklerinizin sorunlarını giderme](../../javascript/advanced/troubleshooting-your-scripts-javascript.md)