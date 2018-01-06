---
title: "Office uygulaması ve proje türüne göre kullanılabilen özellikler | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
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
ms.assetid: 3e9aa4d3-affb-4f76-bc67-49fe5f26a6a1
caps.latest.revision: "53"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6a0f2e0b87e791618477ff6e11c9e180793d5495
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="features-available-by-office-application-and-project-type"></a>Office Uygulaması ve Proje Türüne Göre Kullanılabilir Özellikler
  Visual Studio aşağıdaki türleri dahil olmak üzere Microsoft Office uygulamaları, farklı iş senaryolarını desteklemek proje şablonları çeşitli türleri vardır:  
  
-   Belge düzeyi özelleştirmeleri.  
  
-   VSTO eklentileri.  
  
 Tüm uygulamalar her proje türü kullanabilirsiniz. Örneğin, yalnızca Microsoft Office Word ve Microsoft Office Excel için belge düzeyi projelerine kullanılabilir. Benzer şekilde, bazı özellikler yalnızca belirli türdeki projeleri veya uygulamalar için kullanılabilir. Örneğin, Eylemler bölmesinde yalnızca belge düzeyi projelerine kullanılabilir ve Şerit uzantıları sadece bazı uygulamalar için kullanılabilir. Farklı proje türleri hakkında daha fazla bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
> [!NOTE]  
>  Office proje şablonları yalnızca bazı sürümlerinde kullanılabilir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Daha fazla bilgi edinmek için bkz. [Bir Bilgisayarı Office Çözümleri Geliştirmek Üzere Yapılandırma](../vsto/configuring-a-computer-to-develop-office-solutions.md).  
  
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
|Eylemler bölmesi.|Belge düzeyi projelerine.|[Eylemler Bölmesine Genel Bakış](../vsto/actions-pane-overview.md)|  
|ClickOnce dağıtımı.|VS ve belge düzeyi projelerine.|[Office Çözümünü Dağıtma](../vsto/deploying-an-office-solution.md)|  
|Özel görev bölmeleri.|VSTO eklentisi projelerine şu uygulamalar için:<br /><br /> -Excel<br />-InfoPath (InfoPath 2013 ve InfoPath 2010 yalnızca)<br />-Outlook<br />-PowerPoint<br />-Word|[Özel Görev Bölmeleri](../vsto/custom-task-panes.md)|  
|Özel XML bölümleri.|Belge düzeyi projelerine.<br /><br /> Aşağıdaki uygulamalar için uygulama düzeyi projeleri:<br /><br /> -Excel<br />-PowerPoint<br />-Word|[Özel XML Bölümlerine Genel Bakış](../vsto/custom-xml-parts-overview.md)|  
|Veri önbelleği.|Belge düzeyi projelerine.|[Belge Düzeyi Özelleştirmelerdeki Önbelleğe Alınmış Veriler](../vsto/cached-data-in-document-level-customizations.md)|  
|VSTO eklenti diğer Microsoft Office çözümleri için bir nesnesinde kullanıma sunar.|VSTO eklentisi projelerine.|[VSTO Eklentilerinde Diğer Office Çözümlerinden Kod Çağırma](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md)|  
|Aşağıdaki ana bilgisayar denetimleri:<br /><br /> -Grafik<br />-ListObject<br />-NamedRange<br />-İçerik denetimleri<br />-Yer işareti|Belge düzeyi projelerine.<br /><br /> VSTO eklentisi projelerine Word ve Excel için.|[Konak Öğelerine ve Denetimlerine Genel Bakış](../vsto/host-items-and-host-controls-overview.md)|  
|Aşağıdaki ana bilgisayar denetimleri:<br /><br /> -XMLMappedRange<br />-XMLNode<br />-XMLNodes|Belge düzeyi projelerine.|[Konak Öğelerine ve Denetimlerine Genel Bakış](../vsto/host-items-and-host-controls-overview.md)|  
|Birden çok proje dağıtımı.|Belge düzeyi projelerine.<br /><br /> VSTO eklentisi projelerine.|[İzlenecek yol: Bir tek ClickOnce Yükleyicisinde birden çok Office çözümü dağıtma](http://msdn.microsoft.com/en-us/051223c0-4082-4799-b78b-a4763a9def55)|  
|Outlook form bölgeleri.|VSTO eklentisi projelerine Outlook.|[Outlook Form Bölgeleri Oluşturma](../vsto/creating-outlook-form-regions.md)|  
|Dağıtım sonrası eylemleri.|Belge düzeyi projelerine.<br /><br /> VSTO eklentisi projelerine.|[İzlenecek yol: bir belgeyi son kullanıcının bilgisayarına bir ClickOnce yüklemesinden sonra kopyalama](http://msdn.microsoft.com/en-us/100090f7-bc63-4152-b3e1-19b48bc27466)|  
|Şerit Özelleştirmelerini.|Belge düzeyi projelerine.<br /><br /> VSTO eklentisi projelerine şu uygulamalar için:<br /><br /> -Excel<br />-InfoPath (InfoPath 2013 ve InfoPath 2010 yalnızca)<br />-Outlook<br />-PowerPoint<br />-Proje<br />-Visio<br />-Word|[Şeride Genel Bakış](../vsto/ribbon-overview.md)|  
|Görsel belge Tasarımcısı.|Belge düzeyi projelerine.|[Visual Studio Ortamında Office Projeleri](../vsto/office-projects-in-the-visual-studio-environment.md)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlarken &#40; Office geliştirme Visual Studio &#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md)   
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Belge düzeyi özelleştirmelerinde önbelleğe alınan veriler](../vsto/cached-data-in-document-level-customizations.md)   
 [Office Çözümünü Dağıtma](../vsto/deploying-an-office-solution.md)  
  
  