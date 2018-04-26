---
title: İş Akışı Tasarımcısı - Visual Studio hata ayıklayıcısı Windows Workflow Foundation (eski) için çağırma
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- stepping
- Step Over command
- stepping, commands
- debugging, using workflow debugger
- workflows, debugger
- workflow debugger, starting
- Step In command
- debugger, workflow
- Step Out command
- debugging workflows, starting the debugger
ms.assetid: d6f58e35-5cce-4ff2-9afc-b2d9d0f819cf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a326f8b6dc482c2adfc2caba797c38094a99f8c5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy"></a>Visual Studio hata ayıklayıcısı Windows Workflow Foundation (eski) için çağırma

Bu konuda açıklanmaktadır nasıl eski Windows iş akışı Tasarımcısı'nda Windows Workflow Foundation (WF) uygulamalarında hata ayıklamak için Visual Studio hata ayıklayıcısı kullanın. .NET Framework sürüm 3.5 veya WinFX hedeflemek gerektiğinde eski iş akışı Tasarımcısı kullanın.

Genellikle, diğer Visual Studio programlama dilinde yazılmış programları yalnızca hata ayıklama gibi eski iş akışları hata ayıklama. Visual Studio hata ayıklayıcısı için Windows Workflow Foundation aşağıdaki yollarla başlatabilirsiniz:

-   Seçin **ekleme işlemi için** üzerinde **hata ayıklama** menüsünde kullanılabilir işlemleri çalışan bir iş akışı örneği seçin.

-   Tuşuna **F5** iş akışı örneği çalıştırma başlatın ya da bir kesme noktası isabet sonra çalışmaya devam eder.

## <a name="stepping-through-code"></a>Kod atlama

Hata ayıklayıcı Adımlama, en sık karşılaşılan hata ayıklama yordamlardan birini, kodu bir satır aynı anda yürütülmekte olduğu destekler. Kod atlama için üç komutlar şunlardır:

-   **Adım içinde**: kullanarak etkinliğini içine adım **F11**. Hata ayıklayıcı adımları tanımlanan işleyicisine. Hiçbir işleyici tanımlanmışsa, etkinlik adım veya diğer etkinlikler içeren bileşik etkinliklerle ilk yürütülen etkinliğe adım. Tasarımcısı'ndan kod işleyicileri Adımlama aşağıdaki etkinlikler için desteklenmiyor: **IfElseActivity**, **WhileActivity**, **ConditionedActivityGroup**, veya **ReplicatorActivity**. Bu etkinlikler ile ilişkili işleyicileri hata ayıklamak için kod açık kesme noktaları konulmalıdır.

-   **Step Out**: kullanarak etkinliğini dışında adım **Shift F11**. Bir etkinlik dışına Adımlama geçerli etkinliği ve tüm eşdüzey tamamlanıncaya kadar etkinlikleri çalıştırır. Hata ayıklayıcı sonra geçerli etkinliğin üst öğede keser. Kod işleyicisinden atlama, hata ayıklayıcı işleyici ilişkilendirildiği faaliyete keser.

-   **Step Over**: kullanarak etkinliğini üzerinden adım **F10**. Bileşik etkinlik atlama olduğunda. hata ayıklayıcı bileşik etkinlik ilk yürütülebilir alt keser. Bir olmayan-bileşik gibi adımlarken bir **CodeActivity** etkinlik, hata ayıklayıcı sonraki faaliyete etkinliği ve ilişkili işleyicileri ve sonları yürütür. Yürütülen etkinliği son alt bileşik etkinlikte etkinlikse, yürütme sonrasında hata ayıklayıcı üst faaliyete keser.

## <a name="attaching-to-a-process"></a>Bir işlemine iliştirme
 Bir işlemin ekleyerek bir iş akışı hata ayıklamak için kullanılabilir işleminden seçin **kullanılabilir işlemler** liste kutusunda **ekleme işlemi için** iletişim kutusu. Varsa **otomatik: iş akışı kodu** görüntülenmez **ekleme** metin kutusuna ve ardından **seçin**. İçinde **kod türünü seç** iletişim kutusu, tıklatın **bu kodu türleri hata ayıklama** seçip **iş akışı**. Ardından **Tamam** tıklatıp **Attach**.

## <a name="debugging-with-f5"></a>F5 ile hata ayıklama
 Bir iş akışı etkinlik kütüphanesini kullanırken bir iş akışı ana bilgisayar uygulaması ve iş akışı DLL farklı Visual Studio projelerinde, örneğin, bulunuyorsa iş akışı DLL projesi iş akışı hata ayıklamak için Visual Studio çözüm başlangıç projesi olarak ayarlamanız gerekir kullanarak **F5**. İş akışı DLL projenin konak uygulamaya yolu ayarlamalısınız **başlangıç dış program** özelliği.

 Çözüm Gezgini'nde başlangıç projesi ayarlamak için proje adına sağ tıklayın ve seçin **başlangıç projesi olarak ayarla**. Ana yolu ayarlamak için **başlangıç dış program** özelliği, iş akışı projenin çift **özellikleri** düğümünü Çözüm Gezgini ve seçin **hata ayıklama** sekmesini tıklatın. Altında **eylemi Başlat**seçin **başlangıç dış program** ve istediğiniz hata ayıklamak için iş akışı barındırma .exe dosyasının yolunu girin.

 Ana bilgisayar uygulaması başlangıç projesi olarak ayarlanırsa, yalnızca Visual Studio hata ayıklayıcısı hata ayıklama için çağrılır; Visual Studio hata ayıklayıcısı için Windows Workflow Foundation çağrılır. Visual Studio hata ayıklayıcısı kullanılırsa, yalnızca C# veya Visual Basic kodu kesme noktası isabet; İş Akışı Tasarımcısı'nda ayarlanmış kesme noktası isabet değil. Örneğin, üzerinde ayarlanmış bir kesme noktası bir <xref:System.Workflow.Activities.ParallelActivity> etkinlik Tasarımcısı'nda Visual Studio hata ayıklayıcısı için Windows Workflow Foundation kullandıysanız, ancak Visual Studio hata ayıklayıcısı değil kullandığınızda ulaştı.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl Yapılır: İş Akışlarında Kesme Noktası Ayarlama (Eski)](../workflow-designer/how-to-set-breakpoints-in-workflows-legacy.md)
- [Eski İş Akışlarında Hata Ayıklama](../workflow-designer/debugging-legacy-workflows.md)