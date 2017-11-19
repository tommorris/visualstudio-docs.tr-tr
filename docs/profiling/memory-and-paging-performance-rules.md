---
title: "Bellek ve disk belleği performans kuralları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f37972b2-efe4-4a1c-a5d1-a246ccd76817
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 15b9963d10a2a51d34ef3a426ac7a2aba17c2430
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="memory-and-paging-performance-rules"></a>Bellek ve Disk Belleği Performans Kuralları
Performans kuralları bellek ve disk belleği kategori uygulama performansı ve yanıt hızını etkileyebilir profil çalıştırmada sayfalama etkinliğini tanımlar.  
  
|||  
|-|-|  
|[DA0014: aşırı yüksek hızda diske etkin bellek Sayfalaması](../profiling/da0014-extremely-high-rates-of-paging-active-memory-to-disk.md)|Çalıştırma profili oluşturma boyunca son derece yüksek oranda bir disk gelen ve giden etkin bellek Sayfalaması oluştu. Bu düzey genellikle etkisi uygulama performansı ve yanıt hızını oranlarda disk belleği. Bellek ayırma algoritmaları düzeltilmesi tarafından azaltmayı deneyin. Uygulamanızın bellek gereksinimleri göz önünde bulundurun gerekebilir. Daha fazla belleğe sahip bir bilgisayarda yeniden profil çalıştırmayı deneyin. Disk belleği etkinlik miktarı kuralının D0017 üst eşiğini aştığında, bu kural ateşlenir.|  
|[DA0017: diske etkin bellek Sayfalaması yüksek hızda](../profiling/da0017-high-rates-of-paging-active-memory-to-disk.md)|Göreceli olarak yüksek oranda bir disk gelen ve giden etkin bellek Sayfalaması çalıştırmak profil boyunca oluştu. Bu düzey genellikle etkisi uygulama performansı ve yanıt hızını oranlarda disk belleği. Bellek ayırma algoritmaları düzeltilmesi tarafından azaltmayı deneyin. Uygulamanızın bellek gereksinimleri göz önünde bulundurun gerekebilir. Daha fazla belleğe sahip bir bilgisayarda yeniden profil çalıştırmayı deneyin.|