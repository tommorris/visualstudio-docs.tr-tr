---
title: "DA0003: Pek çok çekirdek örneği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DA0003
- vs.performance.DA0003
- vs.performance.3
- vs.performance.rules.DAManyKernelSamples
ms.assetid: c1f46f77-eb95-42e5-b340-d86bc9de41b4
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e7451a5b18b0879a64d92525d5b72a6f4c1ec8cf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="da0003-many-kernel-samples"></a>DA0003: Pek çok çekirdek örneği
|||  
|-|-|  
|Kural Kimliği|DA0003|  
|Kategori|Profil oluşturma araçları kullanım|  
|Profil oluşturma yöntemleri|Örnekleme|  
|İleti|Yüksek oranda örnekleri çekirdek modunda sahip. Bu, g/ç etkinliğini hacmi yüksek veya yüksek oranda bir içerik geçişi gösterebilir. Profil oluşturma araçları modunu kullanarak yeniden uygulamanız göz önünde bulundurun.|  
|Kural türü|Bilgiler|  
  
## <a name="cause"></a>Sebep  
 Uygulama için toplanan çağrı yığını örnekleri önemli bir kısmının çekirdek modunda yürütülüyor. Farklı bir profil oluşturma yöntemi kullanarak uygulamanızı profil göz önünde bulundurun.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Windows, çekirdek modu veya kullanıcı modunda kod çalıştırılabilir. (Çekirdek modu da ayrıcalıklı modu olarak adlandırılır.) Bir aygıt sürücüleri gibi alt düzey sistem kodu yalnızca çekirdek modunda çalışır. Bir kullanıcı modu uygulaması için iş parçacığı veya işlem eşitleme temelleri bekleyin ya da sistem çağrıları yapmak için g/ç işlemleri gerçekleştirmek için çekirdek moduna geçiş yapabilir.  
  
 Profil oluşturma çoğu kullanıcı modunda çalışarak zamanlarının harcamanız uygulamaları örnekleme en etkilidir. Uygulama çekirdek modunda yürütülürken toplanan örnek sayısını sık g/ç işlemleri belirtebilir veya anahtarları oluşan bu bağlamı gösterebilir. Bu işlemlerin hiçbiri örnekleme yöntemini kullanarak araştırılması. Çok fazla sayıda çekirdek modu örneği alınır, örnekleme verileri istatistiksel olarak önemli olacak yeterli kullanıcı modu örnek içerebilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Aşağıdaki seçeneklerden birini kullanarak yeniden uygulamanız profil göz önünde bulundurun:  
  
-   İzleme metodunu kullanarak profil.  
  
-   Daha fazla örnekleri kullanıcı modunda toplanacak denemek için örnekleme hızını artırır.