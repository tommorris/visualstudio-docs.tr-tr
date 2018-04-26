---
title: İş Akışı Tasarımcısı ile uygulamaları geliştirme
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- DefaultWorkflowDesigner
- DefaultWorkflowDesigner.UI
helpviewer_keywords:
- Visual Studio 2010 Workflow Designer [WFD], overview
- Workflow Designer [WFD]
- Visual Studio 2010 Workflow Designer [WFD]
- Workflow Designer [WFD], overview
ms.assetid: 4cd062b1-b496-4668-bbc1-ee85545e066d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ecc9e42146bfa7de259551ff1c90d27201db5725
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="developing-applications-with-the-workflow-designer"></a>İş Akışı Tasarımcısı ile uygulamaları geliştirme

Windows iş akışı Tasarımcısı bir görsel tasarımcı ve grafik oluşturma ve Visual Studio 2010 geliştirme ortamı'nda barındırılan .NET Framework 4'te Windows Workflow Foundation (WF) uygulamalarının hata ayıklama için hata ayıklayıcı ' dir. Bileşik iş akışı uygulaması, etkinlik kitaplığı veya şablonları ve etkinlik tasarımcıları kullanarak Windows Communication Foundation (WCF) hizmet oluşturma sağlar. İş akışları hakkında daha fazla bilgi için bkz: [Windows Workflow Foundation &#91;.NET Framework 4&#93;](http://msdn.microsoft.com/Library/9a23ea6b-d600-483e-89cd-8889cfec5f66).

 İş Akışı Tasarımcısı'nın eski sürümleri dışında iş akışı Tasarımcısı'nın bu yeni sürüm kümesi birkaç yeni tasarım özellikleri şunlardır:

-   İş Akışı Tasarımcısı Windows Presentation Foundation (WPF) kullanılarak oluşturulur. Bu etkinlik Tasarımcısı deneyimini geliştirir ve büyük ve karmaşık iş akışları için performansı geliştirir.

-   Özel etkinlikler ile tasarlanan şimdi [!INCLUDE[avalon2](../workflow-designer/includes/avalon2_md.md)], etkinlik tasarımcıları oluşturma Basitleştirilmiş için XAML ve programlama modeli kullanarak.

-   Program akışı stili modelleme tanıdık akış kullanarak görselleştirmek için bir akış etkinliği uygulanmıştır.

-   İş Akışı Tasarımcısı etkinlikler için bağlama bildirme ve, iş akışlarınızı değişkenler kapsam olanak tanıyan bir yeni değişken designer sahiptir.

-   Visual Studio 2010'da, iş akışı Tasarımcısı, .NET Framework 4 iş akışlarınızı içinde Visual Basic deyimleri yazarken tam IntelliSense yetenekleri sağlar.

-   Hata ayıklama deneyimini XAML XAML iş akışı tanımınızı ve XAML kodunuzu yönetilen kodda benzer bir deneyim sağlar çalışma zamanında adımla kesme noktaları ayarlamanıza olanak veren olarak genişletir.

-   Visual Studio dışında iş akışı Tasarımcısı yeniden barındırılmasını artık yalnızca birkaç satır kod gerektiren önceki sürümlerine kıyasla önemli ölçüde basitleştirilmiştir.

-   Yeni <xref:System.Activities.Statements.Flowchart> etkinliği ve kendi [akış çizelgesi](../workflow-designer/flowchart-activity-designer.md) stili modelleme tanıdık akış kullanarak, program akışı görselleştirmek olanak sağlar.

-   Mesajlaşma etkinlikleri, yazmak tam bildirim temelli sağlayarak geliştirilmiştir (kod) Windows Communication Foundation (WCF) hizmetlerini.

-   **Hizmet Başvurusu Ekle...**  işlevsellik otomatik olarak Web hizmetlerine erişmek etkinlikler oluşturmanıza olanak sağlar.