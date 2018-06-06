---
title: 'DA0003: Pek çok çekirdek örneği | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DA0003
- vs.performance.DA0003
- vs.performance.3
- vs.performance.rules.DAManyKernelSamples
ms.assetid: c1f46f77-eb95-42e5-b340-d86bc9de41b4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 97e2e745b59a22110f6392e2cd6fec1aea0a667a
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750239"
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
  
## <a name="rule-description"></a>Kural açıklaması  
 Windows, çekirdek modu veya kullanıcı modunda kod çalıştırılabilir. (Çekirdek modu da ayrıcalıklı modu olarak adlandırılır.) Bir aygıt sürücüsü gibi alt düzey sistem kodu yalnızca çekirdek modunda çalışır. Bir kullanıcı modu uygulaması için iş parçacığı veya işlem eşitleme temelleri bekleyin ya da sistem çağrıları yapmak için g/ç işlemleri gerçekleştirmek için çekirdek moduna geçiş yapabilir.  
  
 Profil oluşturma çoğu kullanıcı modunda çalışarak zamanlarının harcamanız uygulamaları örnekleme en etkilidir. Uygulama çekirdek modunda yürütülürken toplanan örnek sayısını sık g/ç işlemleri belirtebilir veya anahtarları oluşan bu bağlamı gösterebilir. Bu işlemlerin hiçbiri örnekleme yöntemini kullanarak araştırılması. Çok fazla sayıda çekirdek modu örneği alınır, örnekleme verileri istatistiksel olarak önemli olacak yeterli kullanıcı modu örnek içerebilir.  
  
## <a name="how-to-fix-violations"></a>İhlallerini düzeltmek nasıl  
 Aşağıdaki seçeneklerden birini kullanarak yeniden uygulamanız profil göz önünde bulundurun:  
  
-   İzleme metodunu kullanarak profil.  
  
-   Daha fazla örnekleri kullanıcı modunda toplanacak denemek için örnekleme hızını artırır.