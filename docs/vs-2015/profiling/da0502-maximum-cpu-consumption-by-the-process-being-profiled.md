---
title: 'DA0502: Maksimum CPU kullanımının profili oluşturuluyor işlem tarafından | Microsoft Docs'
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
- vs.performance.rules.DA0502
- vs.performance.DA0502
- vs.performance.502
ms.assetid: 1ee53df5-b0dc-4265-9d4f-527830d08725
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: be9b9ff318ade6546369e20d5508b2ad79dc0bb9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630120"
---
# <a name="da0502-maximum-cpu-consumption-by-the-process-being-profiled"></a>DA0502: İşlemin maksimum CPU kullanımının profili oluşturuluyor
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [DA0502: profili oluşturulan işlemin maksimum CPU kullanımının](https://docs.microsoft.com/visualstudio/profiling/da0502-maximum-cpu-consumption-by-the-process-being-profiled).  
  
Kural Kimliği | DA0502 |  
| Kategori | Kaynak İzleme |  
| Profil oluşturma yöntemi | Tüm |  
| İleti | Bu kural yalnızca bilgi içindir. İşlem()\\% İşlemci Zamanı sayacı, profil oluşturma işleminin CPU kullanımını ölçer. Bildirilen değer olan en yüksek tüm ölçüm aralıklarında gözlemlenen. |  
| Kural türü | Bilgilendirme |  
  
 Örnekleme, .NET bellek ve kaynak çekişmesi yöntemleri kullanılarak profili, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu ileti, en yüksek işlemci yönergeleri uygulamadan çalıştırmakla meşgul olduğu süre yüzdesi bildirir. Profil oluşturulan işlem etkin olduğu tüm ölçüm aralıklarında arasında bildirilen en yüksek değeri bildirilen değerdir. Yüzde, birden çok işlemcili bir makinede % 100'den daha büyük olabilir.  
  
## <a name="how-to-use-the-rule-data"></a>Kural verileri kullanma  
 Kural değeri, farklı sürümlerin performans veya programın yapıları karşılaştırmak veya farklı bir profil oluşturma senaryoları altında uygulama performansını anlamanın kullanın.



