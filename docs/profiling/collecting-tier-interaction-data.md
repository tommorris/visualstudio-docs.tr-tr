---
title: Katman etkileşim verileri toplama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.tierinteraction
helpviewer_keywords:
- Profiling Tools,ADO.NET profiling
- tier interaction profiling method
- Profiling Tools,tier-interaction method
- ADO.NET performance profiling
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 79bcd9093202d4685078694f3f51cccc08f0be33
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="collecting-tier-interaction-data"></a>Katman etkileşim verileri toplama

Katman etkileşim profil veritabanları ADO.NET Hizmetleri aracılığıyla iletişim çok katmanlı uygulamaların işlevlerini yürütme sürelerinin hakkında ek bilgi sağlar. Verileri yalnızca zaman uyumlu işlev çağrıları için toplanır.

**Visual Studio sürümleri**

Katman etkileşimli profil oluşturma verilerini herhangi bir sürümünü Visual Studio kullanarak toplanabilir. Ancak, katman etkileşimli profil oluşturma verilerini, yalnızca Visual Studio kuruluş içinde görüntülenebilir.

**Windows 8 ve Windows Server 2012**

Masaüstü uygulamaları Windows 8 ve Windows Server 2012 uygulamalar katman etkileşim verileri toplamak için izleme metodunu kullanmanız gerekir. UWP uygulamalar için katman etkileşim verileri toplayamazsınız. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md). Desteklenen diğer Windows sürümünde tüm profil oluşturma yöntemlerini katman etkileşim verileri içerebilir.

**Performans Sihirbazı**

Performans Sihirbazı bir hata nedeniyle, katman etkileşim verileri toplama seçeneğini profil çalışmaya performans Gezgini'nden eklemeniz gerekir. Proje, yürütülebilir dosya veya Web sitesi performans Gezgini hedef düğüme eklemelisiniz.

## <a name="to-add-tier-interaction-data-to-a-profiling-run-by-using-the-performance-session-property-pages"></a>Bir performans oturumu özellik sayfalarını kullanarak çalıştırmak profil için katman etkileşim verileri eklemek için

1. Performans Gezgini seçin **özellikleri** ve bağlam menüsünden.

2. Seçin **katman etkileşimleri** sayfasında ve ardından denetleyin **katman etkileşim profil etkinleştirmek** onay kutusu.

3. Performans Gezgini içinde seçin **hedefleri** düğümü, proje, yürütülebilir dosya veya profil oluşturmayı istediğiniz web sitesi belirtin.

## <a name="see-also"></a>Ayrıca bkz.

[Katman Etkileşimleri Görünümü](../profiling/tier-interactions-view.md)