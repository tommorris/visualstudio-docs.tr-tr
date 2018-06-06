---
title: 'Nasıl yapılır: CPU sayaç verileri toplama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.cpucounters
helpviewer_keywords:
- profiling tools, using portable CPU counters
- performance tools, portable CPU counters
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ee77d340eec13c42588511575c6047b5c8f28d16
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765105"
---
# <a name="how-to-collect-cpu-counter-data"></a>Nasıl yapılır: CPU sayaç verileri toplama

Bir CPU olay sayacı, donanıma özgü performans verilerini toplamak için kullanılır. Bu makalede izleme profili oluşturma yöntemi kullandığınızda, olay sayaç verileri toplamak nasıl gösterir.

İki tür CPU sayaç olay oluşur:

- Taşınabilir olayları - bakılmaksızın belirli CPU toplanabilir CPU olayları.

- Platform olayları - belirli bir CPU eşleşmiş CPU olayları.

 Taşınabilir olayları yönergeleri kullanımdan ve durdurulamaz harici döngüleri gibi genel olayları, CPU arabellek olayları, dallanma olayları ve L2 önbellek olayları içerir. Kullanılabilir platformu olay sayaç işlemci üreticisi tarafından belirlenir.

 Olayların kategorilerini taşınabilir ve platform sayaçları arasında paylaşılabilir. Örneğin, aşağıdaki veri her iki tür sık sık karşılaşılan şunlardır:

- Bellek olaylar.

- Ön uç olaylar.

- Dal olaylar.

 Profil Oluşturucu iki yolla performans sayacı verilerini toplayabilir:

- Araçları tarafından profil olduğunda veri bir veya daha fazla sayaçlarını toplar.

- Örnekleme tarafından profil zaman sayacı olay örnekleme aralığı belirtin. Daha fazla bilgi için bkz: [nasıl yapılır: örnekleme olayları seçme](../profiling/how-to-choose-sampling-events.md).

## <a name="to-collect-cpu-performance-counter-data-when-you-profile-by-instrumentation"></a>Araçları tarafından profil, CPU performans sayacı verilerini toplamak için

1. Performans oturum **özellik sayfaları**, tıklatın **CPU sayaçları.**

2. Seçin **toplamak CPU sayaçları** onay kutusu.

3. Genişletme **kullanılabilir performans sayaçları** toplamak istediğiniz örnek olaylar bulana kadar ağacı.

4. Toplamak istediğiniz her olay için olay seçin ve ardından olaya eklemek için sağ oka tıklayın **seçili sayaçları** listesi.

    > [!NOTE]
    > **Kullanılabilir performans sayaçları** yalnızca seçerseniz etkin **toplamak CPU sayaçları** onay kutusu.

## <a name="see-also"></a>Ayrıca bkz.

[Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)  
[Performans oturumu özellikleri](../profiling/performance-session-properties.md)  
[CPU ve Windows sayaçları](../profiling/cpu-and-windows-counters.md)  
[Nasıl yapılır: Örnekleme olayları seçme](../profiling/how-to-choose-sampling-events.md)