---
title: 'DA0004: Yüksek işlemci kullanımına | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DAHighProcessorUsage
- vs.performance.rules.DA0004
- vs.performance.DA0004
- vs.performance.4
ms.assetid: 2c4fb569-929e-4f1d-8c50-b590ee371351
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d5800acfded9d500c68a0e071ffa6501d6b3c77e
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749616"
---
# <a name="da0004-high-processor-usage"></a>DA0004: Yüksek işlemci kullanımı
|||  
|-|-|  
|Kural Kimliği|DA0004|  
|Kategori|Profil oluşturma araçları kullanım|  
|Profil oluşturma yöntemleri|İzleme<br /><br /> Örnekleme|  
|İleti|İşlemci kullanımı tutarlı bir şekilde %75 olur. CPU bağımlı uygulamalar için örnekleme modu kullanmayı düşünün.|  
|Kural türü|Bilgiler|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="cause"></a>Sebep  
 İşlemci (CPU) kullanımı izleme metodunu kullanarak toplanan verileri profil yüksek. Örnekleme profili oluşturma yöntemi bir CPU profil bağlı uygulama zaman kullanmayı düşünün.  
  
## <a name="rule-description"></a>Kural açıklaması  
 Bu profil çalışması sırasında sürekli olarak işlemci (veya işlemciler) meşguldü. CPU kullanımının yüksek CPU bağımlı uygulama belirtebilirsiniz. İzleme eklenmiş profilleri CPU kullanım senaryoları araştırmak amacıyla en etkili şekilde değildir. Profil oluşturma yönergeleri işlemci yürütme kendi süresi çoğunu harcamanız uygulamaları örnekleme daha etkilidir.  
  
## <a name="how-to-fix-violations"></a>İhlallerini düzeltmek nasıl  
 Yeniden örnekleme yöntemini işlevi zamanlamaları gerektiren veya işlemci performansı sorunlarını anlama giriş/çıkış daha ilgilendiğiniz sürece yerine izleme yöntemini kullanarak uygulamanızı profil göz önünde bulundurun.