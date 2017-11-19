---
title: "DA0004: Yüksek işlemci kullanımına | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DAHighProcessorUsage
- vs.performance.rules.DA0004
- vs.performance.DA0004
- vs.performance.4
ms.assetid: 2c4fb569-929e-4f1d-8c50-b590ee371351
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5eeb6d43ff388050ad9c1fa8140f2e6bdfb352ac
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 İşlemci (CPU) kullanımı izleme metodunu kullanarak toplanan verileri profil önemli ölçüde yüksek. Örnekleme profili oluşturma yöntemi bir CPU profil bağlı uygulama zaman kullanmayı düşünün.  
  
## <a name="rule-description"></a>Kural Tanımı  
 İşlemci (veya işlemciler) Bu profil çalışması sırasında sürekli olarak çok meşgul. CPU kullanımının yüksek CPU bağımlı uygulama belirtebilirsiniz. İzleme eklenmiş profilleri genellikle CPU kullanım senaryoları araştırmak amacıyla en etkili şekilde değildir. Profil oluşturma yönergeleri işlemci yürütme kendi süresi çoğunu harcamanız uygulamaları örnekleme genellikle daha etkilidir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Yeniden örnekleme yöntemini işlevi zamanlamaları gerektiren veya işlemci performansı sorunlarını anlama giriş/çıkış daha ilgilendiğiniz sürece yerine izleme yöntemini kullanarak uygulamanızı profil göz önünde bulundurun.