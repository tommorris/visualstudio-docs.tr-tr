---
title: "Nasıl yapılır: CPU sayaç verileri toplama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.property.cpucounters
helpviewer_keywords:
- profiling tools, using portable CPU counters
- performance tools, portable CPU counters
ms.assetid: 102fb6ca-5fbf-4b05-925f-56912ce3f44b
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 13bba809b77286cd4a6eea4efa41b69c317d23d7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-collect-cpu-counter-data"></a>Nasıl yapılır: CPU Sayaç Verileri Toplama
Bir CPU olay sayacı, donanıma özgü performans verilerini toplamak için kullanılır. Bu konuda izleme profili oluşturma yöntemi kullandığınızda, olay sayaç verileri toplamak nasıl gösterilmektedir.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 İki tür CPU sayaç olay oluşur:  
  
-   Taşınabilir olayları - bakılmaksızın belirli CPU toplanabilir CPU olayları.  
  
-   Platform olayları - belirli bir CPU eşleşmiş CPU olayları.  
  
 Taşınabilir olayları yönergeleri kullanımdan ve durdurulamaz harici döngüleri gibi genel olayları, CPU arabellek olayları, dallanma olayları ve L2 önbellek olayları içerir. Kullanılabilir platformu olay sayaç işlemci üreticisi tarafından belirlenir.  
  
 Olayların kategorilerini taşınabilir ve platform sayaçları arasında paylaşılabilir. Örneğin, aşağıdaki veri her iki tür sık sık karşılaşılan şunlardır:  
  
-   Bellek olaylar.  
  
-   Ön uç olaylar.  
  
-   Dal olaylar.  
  
 Profil Oluşturucu iki yolla performans sayacı verilerini toplayabilir:  
  
-   Araçları tarafından profil olduğunda veri bir veya daha fazla sayaçlarını toplar.  
  
-   Örnekleme tarafından profil zaman sayacı olay örnekleme aralığı belirtin. Daha fazla bilgi için bkz: [nasıl yapılır: örnekleme olayları seçin](../profiling/how-to-choose-sampling-events.md).  
  
### <a name="to-collect-cpu-performance-counter-data-when-you-profile-by-instrumentation"></a>Araçları tarafından profil, CPU performans sayacı verilerini toplamak için  
  
1.  Performans oturum **özellik sayfaları**, tıklatın **CPU sayaçları.**  
  
2.  Seçin **toplamak CPU sayaçları** onay kutusu.  
  
3.  Genişletme **kullanılabilir performans sayaçları** toplamak istediğiniz örnek olaylar bulana kadar ağacı.  
  
4.  Toplamak istediğiniz her olay için olay seçin ve ardından olaya eklemek için sağ oka tıklayın **seçili sayaçları** listesi.  
  
    > [!NOTE]
    >  **Kullanılabilir performans sayaçları** yalnızca seçerseniz etkin **toplamak CPU sayaçları** onay kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)   
 [Performans oturum özellikleri](../profiling/performance-session-properties.md)   
 [CPU ve Windows sayaçları](../profiling/cpu-and-windows-counters.md)   
 [Nasıl yapılır: örnekleme olayları seçme](../profiling/how-to-choose-sampling-events.md)