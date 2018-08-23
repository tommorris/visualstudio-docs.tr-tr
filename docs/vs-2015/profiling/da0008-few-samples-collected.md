---
title: 'DA0008: Toplanan örnek az | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.rules.DATooFewSamples
- vs.performance.8
- vs.performance.DA0008
- vs.performance.rules.DA0008
ms.assetid: 8a5b78aa-7b3d-476c-a47d-abfaff3fae7c
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 205bedf2baa7c9fa1e1c5f40ccbaa4041427074b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691316"
---
# <a name="da0008-few-samples-collected"></a>DA0008: Toplanan örnek az
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [DA0008: toplanan örnek az](https://docs.microsoft.com/visualstudio/profiling/da0008-few-samples-collected).  
  
Kural Kimliği | DA0008 |  
| Kategori | Profil oluşturma araçları kullanım |  
| Profil oluşturma yöntemi | Örnekleme |  
| İleti | Yalnızca birkaç örnek toplanmadı. Uzun bir veya daha hızlı çalışmasını örnekleme hızını daha geçerli sonuçlar için göz önünde bulundurun. |  
| Kural türü | Bilgi |  
  
## <a name="cause"></a>Sebep  
 Yalnızca birkaç örnek profil oluşturma çalışmasında toplanmadı.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Örnekleme yöntemi kullanıldığında, bir istatistiksel veriler gerçek program davranışını temsil emin olmak için örnek sayısı toplamanız gerekir. Örnekleme hataları en aza indirmek için en az 1000 program yönerge yürütme davranışını örnekleri toplamak çalışmanız gerekir. Yeterli örnekleri tahsil etmeme, profil oluşturma verilerinin analiz ederken, misled.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bir uygulama bir artık çalıştırma profili oluşturma veya istatistiksel sonuçları elde etmek için daha hızlı bir örnekleme hızı kullanmayı düşünün. Visual Studio IDE'de örnekleme oranını değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: örnekleme olayları seçin](../profiling/how-to-choose-sampling-events.md). Profil Araçları komut satırı özelliğini kullandığınızda, örnekleme hızını değiştirme hakkında daha fazla bilgi için bkz. [Zamanlayıcı](../profiling/timer.md) içinde [VSPerfCmd](../profiling/vsperfcmd.md) başvuru.



