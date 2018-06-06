---
title: 'DA0008: Toplanan örnek az | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DATooFewSamples
- vs.performance.8
- vs.performance.DA0008
- vs.performance.rules.DA0008
ms.assetid: 8a5b78aa-7b3d-476c-a47d-abfaff3fae7c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 13065ac4b55b8ae84d299aa15eeb184e7d864d2e
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749820"
---
# <a name="da0008-few-samples-collected"></a>DA0008: Toplanan örnek az
|||  
|-|-|  
|Kural Kimliği|DA0008|  
|Kategori|Profil oluşturma araçları kullanım|  
|Profil oluşturma yöntemi|Örnekleme|  
|İleti|Yalnızca birkaç örnek toplanan. Daha önemli sonuçlar için uzun bir veya daha hızlı çalışmasını örnekleme hızını göz önünde bulundurun.|  
|Kural türü|Bilgiler|  
  
## <a name="cause"></a>Sebep  
 Yalnızca birkaç örnekleri çalıştırmak profil toplanan.  
  
## <a name="rule-description"></a>Kural açıklaması  
 Örnekleme yöntemi kullanıldığında, veri gerçek program davranışını temsil emin olmak için örnekleri istatistiksel olarak önemli sayıda toplamanız gerekir. Örnekleme hatalar en aza indirmek için en az 1000 program yönerge yürütme davranışını örnekleri toplama denemelisiniz. Yeterli örnekleri toplamaz, profil oluşturma verilerini analiz ederken, misled.  
  
## <a name="how-to-fix-violations"></a>İhlallerini düzeltmek nasıl  
 Bir uygulama bir artık çalışma profil veya istatistiksel olarak önemli sonuçları elde etmek için daha hızlı örnekleme hızını kullanmayı düşünün. Visual Studio IDE örnekleme hızını değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: örnekleme olayları seçme](../profiling/how-to-choose-sampling-events.md). Profil oluşturma araçları komut satırı kullandığınızda örnekleme hızını değiştirme hakkında daha fazla bilgi için bkz: [Zamanlayıcı](../profiling/timer.md) içinde [VSPerfCmd](../profiling/vsperfcmd.md) başvuru.