---
title: "Desteklenmeyen senaryolar iş akışı Tasarımcısı'nda hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 6adbe379-41d0-4681-9cd0-b91f187c3c2c
caps.latest.revision: "4"
ms.author: sdanie
manager: erikre
ms.openlocfilehash: e442c47611edbc207b3a9ba7c8f10363cd020d10
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
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