---
title: Kaynak izleme performans kuralları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f0f77faf-0a05-4718-a2c5-47934be40868
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b2bd11b8b18e5dd4e3f6625b1b269d104a6fd5a5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684609"
---
# <a name="resource-monitoring-performance-rules"></a>Kaynak İzleme Performans Kuralları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [kaynak izleme performans kuralları](https://docs.microsoft.com/visualstudio/profiling/resource-monitoring-performance-rules).  
  
Kaynak İzleme kategorisi içindeki performans iletileri, uygulamanızın performansı ile ilgili ek bilgiler sağlayın. Performans sorunlarını analiz etmek için bu verileri kullanabilirsiniz. Bu, bilgilendirme ve her profil oluşturma için bildirilen kurallardır.  
  
|||  
|-|-|  
|[DA0501: İşlemin ortalama CPU kullanımının profili oluşturuluyor.](../profiling/da0501-average-cpu-consumption-by-the-process-being-profiled.md)|Bu ileti bir işlemci yönergeleri uygulamadan çalıştırmakla meşgul olduğu sürenin yüzdesini bildirir. Bildirilen değer profil oluşturulan işlem etkin olduğu tüm ölçüm aralıklarında bir ortalamadır.|  
|[DA0502: İşlemin maksimum CPU kullanımının profili oluşturuluyor](../profiling/da0502-maximum-cpu-consumption-by-the-process-being-profiled.md)|Bu ileti, en yüksek işlemci yönergeleri uygulamadan çalıştırmakla meşgul olduğu süre yüzdesi bildirir. Profil oluşturulan işlem etkin olduğu tüm ölçüm aralıklarında arasında bildirilen en yüksek değeri bildirilen değerdir.|  
|[DA0503: İşlem için Bayt Cinsinden Ortalama Çalışma Kümesinin profili oluşturuluyor](../profiling/da0503-average-working-set-in-bytes-for-the-process-being-profiled.md)|Bu ileti, profil oluşturma etkinken kullanmadan işlemi bayt cinsinden fiziksel bellek miktarını ortalama bildirir. Bu ölçüm, fiziksel bellek çalışma kümesi bilinir.|  
|[DA0504: İşlem için izin verilen Bayt Cinsinden En Büyük Çalışma Kümesinin profili oluşturuluyor](../profiling/da0504-maximum-working-set-in-bytes-for-the-process-being-profiled.md)|Bu ileti, en fazla profil oluşturma etkinken kullanmadan işlemi bayt cinsinden fiziksel bellek miktarını bildirir.|  
|[DA0505: İşlem için izin verilen Ortalama Özel Bayt Sayısının profili oluşturuluyor](../profiling/da0505-average-private-bytes-allocated-for-the-process-being-profiled.md)|Bu ileti, ortalama profil oluşturma sırasında bayt cinsinden ayrılan işlem etkin sanal bellek miktarını bildirir. Bu ölçü sanal bellek olarak da bilinen *özel baytlar*. Özel baytlar yalnızca işlem içinde çalışan iş parçacığı tarafından erişilebilir bir işlem tarafından ayrılan sanal bellek konumları temsil eder.|  
|[DA0506: İşlem için izin verilen Maksimum Özel Bayt Sayısının profili oluşturuluyor](../profiling/da0506-maximum-private-bytes-allocated-for-the-process-being-profiled.md)|Bu ileti, profil oluşturma sırasında özel bayt cinsinden ayrılan işlem etkin sanal bellek miktarını bildirir.|



