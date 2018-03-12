---
title: "Desteklenmeyen senaryolar iş akışı Tasarımcısı'nda hata ayıklama | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 6adbe379-41d0-4681-9cd0-b91f187c3c2c
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 958937e8d846c07cafc8293b4592ad6c67479849
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="unsupported-debugging-scenarios-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda hata ayıklama desteklenmeyen senaryolar
İş Akışı Tasarımcısı'nda [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] birçok yeni özellik eklendi ancak hala desteği olmayan hata ayıklama bazı senaryolar vardır. Bu belge desteklenmeyen İş Akışı Tasarımcısı'nı senaryoları hata ayıklama ayrıntılarını verir.  
  
-   Kodu düzenlenmiş sonra yürütme devam edemiyor.  
  
-   Yürütme (sonraki ayarlayın) iş akışı içindeki rastgele bir noktadan devam edemiyor.  
  
-   İmleç (imleç çalışmaya) ulaşılana kadar yürütme devam edemiyor.  
  
-   İş Akışı Tasarımcısı'nı, iş akışı Tasarımcısı'nın kullanmadan kodda oluşturulan hata ayıklamak için kullanılamaz.  
  
-   ' In önceki sürümlerinde oluşturulan iş akışı [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] içinde hata ayıklaması yapılabilir olamaz [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] Tasarımcısı.  
  
-   Kesme noktaları, etkinlikler arasındaki bağlantılarında tanımlanamıyor veya <xref:System.Activities.Statements.Flowchart> düğümleri.  
  
-   Pano hata ayıklama sırasında kullanılamaz.  
  
-   Etkinlikler kopyalandığında veya yapıştırılan kesme noktaları korunmaz.  
  
-   İş akışı kesme noktaları, çağrı yığını penceresinde olacak şekilde ayarlanamaz.  
  
-   Kesme noktaları Tasarımcısı'nda oluştururken **satır** ve **karakter** ayarlarında **yeni kesme noktası** iletişim kullanılmaz.  
  
-   Kesme noktası penceresi veya kısayol menüsünden aşağıdaki sütunları veya seçenekleri iş akışı hata ayıklama için desteklemez:  
  
    -   Koşul  
  
    -   İsabet sayısı  
  
    -   Ne zaman ulaştı.  
  
    -   İşlev  
  
    -   Veri  
  
    -   İşlem  
  
    -   Çözüme Git