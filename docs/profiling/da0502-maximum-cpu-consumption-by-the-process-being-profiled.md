---
title: 'DA0502: Maksimum CPU kullanımının profili oluşturuluyor işlem | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DA0502
- vs.performance.DA0502
- vs.performance.502
ms.assetid: 1ee53df5-b0dc-4265-9d4f-527830d08725
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f8803a1a0daa0efb9ead00e1e5169057fd88d218
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="da0502-maximum-cpu-consumption-by-the-process-being-profiled"></a>DA0502: İşlemin maksimum CPU kullanımının profili oluşturuluyor
|||  
|-|-|  
|Kural Kimliği|DA0502|  
|Kategori|Kaynak İzleme|  
|Profil oluşturma yöntemi|Tümü|  
|İleti|Bu kural, yalnızca bilgi içindir. Process()\\% İşlemci Zamanı sayacını ölçer, profil oluşturma işleminin CPU tüketimi. Değer, en fazla tüm ölçüm aralıklarında gözlenir bildirdi.|  
|Kural türü|Bilgi|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 10 örnekleri toplamanız gerekir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu ileti, en yüksek işlemci yönergeleri uygulamadan çalıştırmakla meşgul zamanı yüzdesi bildirir. Profili oluşturuluyor işlem etkin olan tüm ölçüm aralıkları arasında bildirilen en büyük değeri bildirilen değerdir. Yüzde birden çok işlemciye sahip bir makinede % 100'den büyük olabilir.  
  
## <a name="how-to-use-the-rule-data"></a>Kural verileri kullanma  
 Farklı sürümlerini performansını veya programın derlemeleri karşılaştırmak ya da farklı profil oluşturma senaryoları altında uygulamanın performansını anlamak için kuralı değeri kullanın.