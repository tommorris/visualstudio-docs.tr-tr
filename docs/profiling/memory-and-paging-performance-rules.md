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
ms.workload: multiple
ms.openlocfilehash: c6466db86c8c27f660fd5a5755f30372efdc7f6c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="memory-and-paging-performance-rules"></a>Bellek ve Disk Belleği Performans Kuralları
Performans kuralları bellek ve disk belleği kategori uygulama performansı ve yanıt hızını etkileyebilir profil çalıştırmada sayfalama etkinliğini tanımlar.  
  
|||  
|-|-|  
|[DA0014: Aşırı yüksek oranda diske etkin bellek sayfalaması gerçekleşiyor.](../profiling/da0014-extremely-high-rates-of-paging-active-memory-to-disk.md)|Çalıştırma profili oluşturma boyunca son derece yüksek oranda bir disk gelen ve giden etkin bellek Sayfalaması oluştu. Bu düzey genellikle etkisi uygulama performansı ve yanıt hızını oranlarda disk belleği. Bellek ayırma algoritmaları düzeltilmesi tarafından azaltmayı deneyin. Uygulamanızın bellek gereksinimleri göz önünde bulundurun gerekebilir. Daha fazla belleğe sahip bir bilgisayarda yeniden profil çalıştırmayı deneyin. Disk belleği etkinlik miktarı kuralının D0017 üst eşiğini aştığında, bu kural ateşlenir.|  
|[DA0017: Yüksek oranda diske etkin bellek sayfalaması gerçekleşiyor.](../profiling/da0017-high-rates-of-paging-active-memory-to-disk.md)|Göreceli olarak yüksek oranda bir disk gelen ve giden etkin bellek Sayfalaması çalıştırmak profil boyunca oluştu. Bu düzey genellikle etkisi uygulama performansı ve yanıt hızını oranlarda disk belleği. Bellek ayırma algoritmaları düzeltilmesi tarafından azaltmayı deneyin. Uygulamanızın bellek gereksinimleri göz önünde bulundurun gerekebilir. Daha fazla belleğe sahip bir bilgisayarda yeniden profil çalıştırmayı deneyin.|