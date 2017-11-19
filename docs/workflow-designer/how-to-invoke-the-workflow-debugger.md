---
title: "Nasıl yapılır: iş akışı hata ayıklayıcı çağırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 34c592af-f4f6-4d02-99f6-63a94698e48b
caps.latest.revision: "9"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8d7fbdb1851669d704cb8a44f8144291c04ae0ce
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-invoke-the-workflow-debugger"></a>Nasıl yapılır: iş akışı hata ayıklayıcı çağırma
Genellikle, diğer Visual Studio programlama dilinde yazılmış programları yalnızca hata ayıklama gibi iş akışları hata ayıklama. İş akışı hata ayıklayıcı aşağıdaki yollarla başlatabilirsiniz:  
  
-   Seçin **ekleme işlemi için** üzerinde **hata ayıklama** menüsü, iş akışı örneği için çalışan ana bilgisayar işlemi seçin. Bu yordam bir ana bilgisayar işlemi yönetilen kod ekleme aynıdır.  
  
-   Tuşuna **F5** iş akışı örneği çalıştırma başlatın ya da bir kesme noktası isabet sonra çalışmaya devam eder.  
  
-   Uzaktan hata ayıklama kullanın. Uzaktan hata ayıklama kullanma hakkında daha fazla bilgi için bkz: [nasıl yapılır: uzaktan hata ayıklama etkinleştirme](http://go.microsoft.com/fwlink/?LinkId=196257).  
  
    > [!NOTE]
    >  İş akışı uygulaması x86 hedefliyorsa mimarisi ve uzaktan hata ayıklama sürece çalışmaz sonra bir 64 bit işletim sistemi çalıştıran bir makinede barındırıldığı [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] uzak makineye veya hedef için iş akışı uygulaması değiştirilirse yüklü **Tüm CPU**.  
  
### <a name="stepping-through-code"></a>Kod atlama  
  
-   **Adım içinde**: kullanarak etkinliğini içine adım **F11**. Hata ayıklayıcı adımları tanımlanan işleyicisine. Hiçbir işleyici tanımlanmışsa, etkinlik adım veya diğer etkinlikler içeren bileşik etkinliklerle ilk yürütülen etkinliğe adım.  
  
-   **Adım çıkışı:** kullanarak etkinliğini dışında adım **Shift F11**. Bir etkinlik dışına Adımlama geçerli etkinliği ve tüm eşdüzey tamamlanıncaya kadar etkinlikleri çalıştırır. Hata ayıklayıcı sonra geçerli etkinliğin üst öğede keser. Kod işleyicisinden atlama, hata ayıklayıcı işleyici ilişkilendirildiği faaliyete keser.  
  
-   **Step Over**: kullanarak etkinliğini üzerinden adım **F10**. Bileşik etkinlik Adımlama, hata ayıklayıcı bileşik etkinlik ilk yürütülebilir alt keser. Bir olmayan-bileşik gibi adımlarken bir <xref:System.Activities.Statements.Assign> etkinlik, hata ayıklayıcı sonraki faaliyete etkinliği ve ilişkili işleyicileri ve sonları yürütür. Ardından, yürütülen etkinliği son alt bileşik etkinlikte etkinlikse, yürütme sonrasında hata ayıklayıcı üst faaliyete keser.  
  
### <a name="debugging-with-f5"></a>F5 ile hata ayıklama  
  
-   Bir iş akışı konsol uygulama projesi oluşturuluyorsa tuşuna basmanız yeterlidir **F5** uygulama ve iş akışı hata ayıklamayı başlatmak için. Bir etkinlik kitaplığı, kendi oluşturuyorsanız, yürütülebilir konak uygulamanın başlangıç projesi olarak olması gerekir. Başlangıç projesi ayarlama **Çözüm Gezgini**, ana proje adına sağ tıklayın ve seçin **başlangıç projesi olarak ayarla**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: iş akışlarında kesme noktalarını ayarlama](../workflow-designer/how-to-set-breakpoints-in-workflows.md)   
 [İş Akışı Tasarımcısı ile hata ayıklama](../workflow-designer/debugging-workflows-with-the-workflow-designer.md)