---
title: 'DA0003: Pek çok çekirdek örneği | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: 30743df0fc8b27e9b5c4df1a35a7bb12ef395a3c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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