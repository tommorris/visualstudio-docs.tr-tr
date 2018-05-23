---
title: Office uygulaması ve proje türüne göre kullanılabilir özellikler
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application-level add-ins [Office development in Visual Studio]
- Office development in Visual Studio, features
- Ribbon [Office development in Visual Studio]
- Office applications [Office development in Visual Studio], features available
- document-level customizations [Office development in Visual Studio]
- Office projects [Office development in Visual Studio], features available
- add-ins [Office development in Visual Studio]
- form regions [Office development in Visual Studio], features available
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d4b0c4ea5ec07fec187c5fa377239cdec2ccceb5
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="features-available-by-office-application-and-project-type"></a>Office uygulaması ve proje türüne göre kullanılabilir özellikler
  Visual Studio aşağıdaki türleri dahil olmak üzere Microsoft Office uygulamaları, farklı iş senaryolarını desteklemek proje şablonları çeşitli türleri vardır:  
  
-   Belge düzeyi özelleştirmeleri.  
  
-   VSTO eklentileri.  
  
 Tüm uygulamalar her proje türü kullanabilirsiniz. Örneğin, yalnızca Microsoft Office Word ve Microsoft Office Excel için belge düzeyi projelerine kullanılabilir. Benzer şekilde, bazı özellikler yalnızca belirli türdeki projeleri veya uygulamalar için kullanılabilir. Örneğin, Eylemler bölmesinde yalnızca belge düzeyi projelerine kullanılabilir ve Şerit uzantıları sadece bazı uygulamalar için kullanılabilir. Farklı proje türleri hakkında daha fazla bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
> [!NOTE]  
>  Office proje şablonları yalnızca bazı sürümlerinde kullanılabilir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Daha fazla bilgi için bkz: [Office çözümleri geliştirmek için bilgisayarı yapılandırma](../vsto/configuring-a-computer-to-develop-office-solutions.md).  
  
## <a name="project-types-available-for-different-microsoft-office-applications"></a>Proje türleri farklı Microsoft Office uygulamaları için kullanılabilir  
 Aşağıdaki tabloda her proje türü ile kullanabileceğiniz uygulamalar gösterilmektedir.  
  
|Proje türleri|Microsoft Office uygulama|  
|-------------------|----------------------------------|  
|Belge düzeyinde özelleştirmeler|Excel<br /><br /> Word|  
|VSTO eklentileri|Excel<br /><br /> InfoPath (InfoPath 2013 ve InfoPath 2010 yalnızca)<br /><br /> Outlook<br /><br /> PowerPoint<br /><br /> Proje<br /><br /> Visio<br /><br /> Word<br /><br /> Excel|  
  
## <a name="features-available-in-different-project-types"></a>Farklı proje türlerinde kullanılabilir özellikler  
 Hangi proje türlerinin aşağıdaki tabloda gösterildiği her bir özellik sağlar.  
  
|Özellik|Özelliği sağlayan proje türleri|Daha fazla bilgi|  
|-------------|--------------------------------------------|---------------------|  
|Eylemler bölmesi.|Belge düzeyi projelerine.|[Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md)|  
|ClickOnce dağıtımı.|VS ve belge düzeyi projelerine.|[Office çözümünü dağıtma](../vsto/deploying-an-office-solution.md)|  
|Özel görev bölmeleri.|VSTO eklentisi projelerine şu uygulamalar için:<br /><br /> -Excel<br />-InfoPath (InfoPath 2013 ve InfoPath 2010 yalnızca)<br />-Outlook<br />-PowerPoint<br />-Word|[Özel görev bölmeleri](../vsto/custom-task-panes.md)|  
|Özel XML bölümleri.|Belge düzeyi projelerine.<br /><br /> Aşağıdaki uygulamalar için uygulama düzeyi projeleri:<br /><br /> -Excel<br />-PowerPoint<br />-Word|[Özel XML bölümlerine genel bakış](../vsto/custom-xml-parts-overview.md)|  
|Veri önbelleği.|Belge düzeyi projelerine.|[Belge düzeyi özelleştirmelerinde önbelleğe alınan veriler](../vsto/cached-data-in-document-level-customizations.md)|  
|VSTO eklenti diğer Microsoft Office çözümleri için bir nesnesinde kullanıma sunar.|VSTO eklentisi projelerine.|[VSTO eklentileri diğer Office Çözümlerinden kodu çağırma](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md)|  
|Aşağıdaki ana bilgisayar denetimleri:<br /><br /> -Grafik<br />-ListObject<br />-NamedRange<br />-İçerik denetimleri<br />-Yer işareti|Belge düzeyi projelerine.<br /><br /> VSTO eklentisi projelerine Word ve Excel için.|[Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)|  
|Aşağıdaki ana bilgisayar denetimleri:<br /><br /> -XMLMappedRange<br />-XMLNode<br />-XMLNodes|Belge düzeyi projelerine.|[Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)|  
|Birden çok proje dağıtımı.|Belge düzeyi projelerine.<br /><br /> VSTO eklentisi projelerine.|[İzlenecek yol: tek ClickOnce Yükleyicisinde birden çok Office çözümlerini dağıtma](http://msdn.microsoft.com/en-us/051223c0-4082-4799-b78b-a4763a9def55)|  
|Outlook form bölgeleri.|VSTO eklentisi projelerine Outlook.|[Outlook form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)|  
|Dağıtım sonrası eylemleri.|Belge düzeyi projelerine.<br /><br /> VSTO eklentisi projelerine.|[İzlenecek yol: belge son kullanıcının bilgisayarına bir ClickOnce yüklemesinden sonra kopyalama](http://msdn.microsoft.com/en-us/100090f7-bc63-4152-b3e1-19b48bc27466)|  
|Şerit Özelleştirmelerini.|Belge düzeyi projelerine.<br /><br /> VSTO eklentisi projelerine şu uygulamalar için:<br /><br /> -Excel<br />-InfoPath (InfoPath 2013 ve InfoPath 2010 yalnızca)<br />-Outlook<br />-PowerPoint<br />-Proje<br />-Visio<br />-Word|[Şerite Genel Bakış](../vsto/ribbon-overview.md)|  
|Görsel belge Tasarımcısı.|Belge düzeyi projelerine.|[Visual Studio ortamında Office projeleri](../vsto/office-projects-in-the-visual-studio-environment.md)|  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Başlama &#40;Visual Studio'da Office geliştirme&#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Office çözümleri geliştirmesine genel bakış &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md)   
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Outlook form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Belge düzeyi özelleştirmelerinde önbelleğe alınan veriler](../vsto/cached-data-in-document-level-customizations.md)   
 [Office çözümünü dağıtma](../vsto/deploying-an-office-solution.md)  
  
  