---
title: "İş Akışı Tasarımcısı ile uygulamaları geliştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "17"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: cbb7b09e5c36980ceeedd99f69241996bd25bfa3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="developing-applications-with-the-workflow-designer"></a>İş Akışı Tasarımcısı ile uygulamaları geliştirme
[!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] Bir görsel tasarımcı ve grafik oluşturma ve, hata ayıklama için hata ayıklayıcı [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] uygulamalarında [!INCLUDE[netfx40_long](../workflow-designer/includes/netfx40_long_md.md)] içinde barındırılan [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] geliştirme ortamı. Bileşik iş akışı uygulama, etkinlik kitaplığı oluşturmanıza olanak tanır veya [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] hizmet şablonları ve etkinlik tasarımcıları yalıtılacaktır. [!INCLUDE[crabout](../test/includes/crabout_md.md)]İş akışları, bkz: [Windows Workflow Foundation &#91;. .NET Framework 4 &#93; ](http://msdn.microsoft.com/Library/9a23ea6b-d600-483e-89cd-8889cfec5f66).  
  
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
  
## <a name="in-this-section"></a>Bu Bölümde  
 [İş Akışı Tasarımcısı'nı kullanarak](../workflow-designer/using-the-workflow-designer.md)  
 Yeni etkinlikler ve yerleşik Designer kullanarak iş akışı projeleri oluşturma ve tasarımcı tarafından sağlanan diğer araçlar bağımsız değişkenleri, değişkenleri, ifadeler, içeri aktarmalar ve içerik haritası Gezinti işlemek için nasıl kullanılacağını gösterir.  
  
 [Etkinlik tasarımcıları kullanma](../workflow-designer/using-the-activity-designers.md)  
 Etkinlikler, şablonları ve sistem tarafından sağlanan kendi tasarımcıları kategorileri açıklanmaktadır.  
  
 [İş Akışı Tasarımcısı ile hata ayıklama](../workflow-designer/debugging-workflows-with-the-workflow-designer.md)  
 Geleneksel yordamları hata ayıklama yanı sıra XAML ve ifadeler hata ayıklama gerçekleştirmeyi açıklar.  
  
 [İş Akışı Tasarımcısı kullanıcı Arabirimi Yardım](../workflow-designer/workflow-designer-ui-help.md)  
 Tarafından sağlanan iletişim kutuları için bağlama duyarlı Yardım konularını içerir [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)], Tasarımcı Kabuk özellikleri hakkında daha fazla yönergeler yanı sıra, klavye kısayolları ve hata iletileri.  
  
 [.NET 3.0 ya da .NET 3.5 hedefleyen iş akışı uygulamaları geliştirme Framework](../workflow-designer/developing-workflow-applications-targeting-the-dotnet-3-0-or-dotnet-3-5-framework.md)  
 Hedefleyen eski Tasarımcısı'nı kullanarak konusunda yönergeler içeren [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] veya [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 [Yeniden barındırma designer &#91; WF örnekleri &#93;](http://msdn.microsoft.com/Library/b676ad31-5f64-4d84-9a36-b4d7113a2f4d)  
 Bu örnek Tasarımcı içerecek şekilde WPF düzeni oluşturulacağını gösterir.  
  
 [Özel Etkinlik tasarımcıları](/dotnet/framework/windows-workflow-foundation/samples/custom-activity-designers)  
 Bu bölümde iş akışı Tasarımcısı'nda görünen özel tasarımcıları kullanılmaya etkinlik örnekleri içerir.