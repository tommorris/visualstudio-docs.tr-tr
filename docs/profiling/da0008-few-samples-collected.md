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
ms.openlocfilehash: fb8471728adda5bb141422833c96e0278fed8e5f
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
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
  
## <a name="rule-description"></a>Kural Tanımı  
 Örnekleme yöntemi kullanıldığında, veri gerçek program davranışını temsil emin olmak için örnekleri istatistiksel olarak önemli sayıda toplamanız gerekir. Örnekleme hatalar en aza indirmek için en az 1000 program yönerge yürütme davranışını örnekleri toplama denemelisiniz. Yeterli örnekleri toplamaz, profil oluşturma verilerini analiz ederken, misled.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bir uygulama bir artık çalışma profil veya istatistiksel olarak önemli sonuçları elde etmek için daha hızlı örnekleme hızını kullanmayı düşünün. Visual Studio IDE örnekleme hızını değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: örnekleme olayları seçin](../profiling/how-to-choose-sampling-events.md). Profil oluşturma araçları komut satırı kullandığınızda örnekleme hızını değiştirme hakkında daha fazla bilgi için bkz: [Zamanlayıcı](../profiling/timer.md) içinde [VSPerfCmd](../profiling/vsperfcmd.md) başvuru.