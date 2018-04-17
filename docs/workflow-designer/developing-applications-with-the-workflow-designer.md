---
title: İş Akışı Tasarımcısı ile uygulamaları geliştirme | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
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
ms.openlocfilehash: 9c48e7b43b23e7bfe8887f437cc17e6db077c0e4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="developing-applications-with-the-workflow-designer"></a>İş Akışı Tasarımcısı ile uygulamaları geliştirme

Windows iş akışı Tasarımcısı bir görsel tasarımcı ve grafik oluşturma ve, hata ayıklama için hata ayıklayıcı, [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] uygulamalarında [!INCLUDE[netfx40_long](../workflow-designer/includes/netfx40_long_md.md)] içinde barındırılan [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] geliştirme ortamı. Bileşik iş akışı uygulama, etkinlik kitaplığı oluşturmanıza olanak tanır veya [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] hizmet şablonları ve etkinlik tasarımcıları yalıtılacaktır. İş akışları hakkında daha fazla bilgi için bkz: [Windows Workflow Foundation &#91;.NET Framework 4&#93;](http://msdn.microsoft.com/Library/9a23ea6b-d600-483e-89cd-8889cfec5f66).

 Bu yeni sürümü ayarlar birkaç yeni tasarım özellikleri aşağıda verilmiştir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] eski sürümleri dışında [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]:

-   [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Kullanılarak oluşturulan [!INCLUDE[avalon1](../workflow-designer/includes/avalon1_md.md)]. Bu etkinlik Tasarımcısı deneyimini geliştirir ve büyük ve karmaşık iş akışları için performansı geliştirir.

-   Özel etkinlikler ile tasarlanan şimdi [!INCLUDE[avalon2](../workflow-designer/includes/avalon2_md.md)], etkinlik tasarımcıları oluşturma Basitleştirilmiş için XAML ve programlama modeli kullanarak.

-   Program akışı stili modelleme tanıdık akış kullanarak görselleştirmek için bir akış etkinliği uygulanmıştır.

-   [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Etkinlikler için bağlama bildirme ve, iş akışlarınızı değişkenler kapsam olanak tanıyan bir yeni değişken designer sahiptir.

-   İçinde [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] içinde Visual Basic deyimleri yazarken tam IntelliSense yetenekleri sağlar, [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] iş akışları.

-   Hata ayıklama deneyimini XAML XAML iş akışı tanımınızı ve XAML kodunuzu yönetilen kodda benzer bir deneyim sağlar çalışma zamanında adımla kesme noktaları ayarlamanıza olanak veren olarak genişletir.

-   Yeniden barındırma [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] dışında [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] artık yalnızca birkaç satır kod gerektiren önceki sürümlerine kıyasla önemli ölçüde basitleştirilmiştir.

-   Yeni <xref:System.Activities.Statements.Flowchart> etkinliği ve kendi [akış çizelgesi](../workflow-designer/flowchart-activity-designer.md) stili modelleme tanıdık akış kullanarak, program akışı görselleştirmek olanak sağlar.

-   Mesajlaşma etkinlikleri, yazmak tam bildirim temelli sağlayarak geliştirilmiştir (kod) [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] Hizmetleri.

-   **Hizmet Başvurusu Ekle...**  işlevsellik otomatik olarak Web hizmetlerine erişmek etkinlikler oluşturmanıza olanak sağlar.