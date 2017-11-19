---
title: "Kaynak izleme performans kuralları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0f77faf-0a05-4718-a2c5-47934be40868
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aed7363a51b08359fc5023cbbd9b7df1b7b7f8cd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="resource-monitoring-performance-rules"></a>Kaynak İzleme Performans Kuralları
Kaynak İzleme kategorideki performans iletileri, uygulamanızın performansı ile ilgili ek bilgiler sağlar. Bu veriler, performans sorunlarını analiz etmek için kullanabilirsiniz. Bu, bilgi ve her çalıştırma profili oluşturma için bildirilen kurallardır.  
  
|||  
|-|-|  
|[DA0501: Ortalama CPU kullanımının profili oluşturuluyor işlem.](../profiling/da0501-average-cpu-consumption-by-the-process-being-profiled.md)|Bu ileti bir işlemci yönergeleri uygulamadan çalıştırmakla meşgul zamanın yüzde olarak bildirir. Bildirilen ortalama profili oluşturuluyor işlem etkin olan tüm ölçüm aralıklarında değerdir.|  
|[DA0502: Maksimum CPU kullanımının profili oluşturuluyor işlemi](../profiling/da0502-maximum-cpu-consumption-by-the-process-being-profiled.md)|Bu ileti, en yüksek işlemci yönergeleri uygulamadan çalıştırmakla meşgul zamanı yüzdesi bildirir. Profili oluşturuluyor işlem etkin olan tüm ölçüm aralıkları arasında bildirilen en büyük değeri bildirilen değerdir.|  
|[DA0503: Ortalama çalışma kümesinin profili oluşturuluyor işlem için bayt cinsinden](../profiling/da0503-average-working-set-in-bytes-for-the-process-being-profiled.md)|Bu ileti ortalama profil oluşturma etkinken, işlemin kullandığı bayt cinsinden fiziksel bellek miktarını raporlar. Bu ölçü fiziksel bellek çalışma kümesi bilinir.|  
|[DA0504: En büyük çalışma kümesinin profili oluşturuluyor işlem için bayt cinsinden](../profiling/da0504-maximum-working-set-in-bytes-for-the-process-being-profiled.md)|Bu ileti en fazla profil oluşturma etkinken, işlemin kullandığı bayt cinsinden fiziksel bellek miktarını raporlar.|  
|[DA0505: Ortalama özel bayt sayısının profili oluşturuluyor işlemi için ayrılmış](../profiling/da0505-average-private-bytes-allocated-for-the-process-being-profiled.md)|Bu ileti ortalama belleğin sanal profil oluşturma sırasında bayt cinsinden ayrılmış işleminin etkin olduğunu bildirir. Bu ölçü sanal bellek olarak bilinen *özel bayt*. Özel bayt yalnızca işlem içinde çalışan iş parçacıkları tarafından erişilebilecek bir işlem tarafından ayrılan sanal bellek konumlarını temsil eder.|  
|[DA0506: Maksimum özel bayt sayısının profili oluşturuluyor işlemi için ayrılmış](../profiling/da0506-maximum-private-bytes-allocated-for-the-process-being-profiled.md)|Bu ileti maksimum sanal bellek profili oluşturma sırasında özel bayt cinsinden ayrılmış işleminin etkin olduğunu bildirir.|