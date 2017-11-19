---
title: "Office çözümleri geliştirmek için bilgisayarı yapılandırma | Microsoft Docs"
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
helpviewer_keywords: Office development in Visual Studio, installing tools
ms.assetid: 0b481186-fd31-43bf-aa4a-591f94309555
caps.latest.revision: "97"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2d3e0b354375d6116a1bcc0cc2b0d69ecc2f16b5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="configuring-a-computer-to-develop-office-solutions"></a>Office Çözümleri Geliştirmek İçin Bilgisayarı Yapılandırma
  VSTO eklentileri ve Microsoft Office için özelleştirmeler oluşturmak için Visual Studio, .NET Framework ve Microsoft Office desteklenen bir sürümünü yükleyin.  
  
|Yazılım|Desteklenen sürümleri|  
|--------------|------------------------|  
|Visual Studio|-   [!INCLUDE[vsPro](../sharepoint/includes/vspro-md.md)]<br />-   [!INCLUDE[vsPreShort](../vsto/includes/vspreshort-md.md)]<br />-   [!INCLUDE[vsUltShort](../vsto/includes/vsultshort-md.md)]**Önemli:** Kurulum sırasında Microsoft Office geliştirici araçları onay kutusunu seçmeniz gerekir.|  
|.NET Framework|-.NET Framework 4 veya üstü.|  
|Microsoft Office|<ul><li>Tüm Office Professional Plus Office 365 için de dahil olmak üzere Office suite sürümü.</li><li>Uygulamalardan herhangi biri aşağıdaki tek başına:<br /><br /> <ul><li>Excel</li><li>InfoPath (Office 2013 ve yalnızca Office 2010)</li><li>Outlook</li><li>PowerPoint</li><li>Project</li><li>Visio</li><li>Word</li></ul></li></ul><br /> Visual Basic for Applications (VBA) Office bir parçası olarak yüklenmelidir. **Önemli:** Office 2010 uygulamaları Tıklat Çalıştır sürümleri desteklenmez.|  
  
 Ayrıntılı yükleme adımları için bkz: [nasıl yapılır: Office çözümleri geliştirmek için bilgisayarı yapılandırma](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md).  
  
## <a name="if-project-templates-dont-appear-or-they-dont-work-in-visual-studio"></a>Proje şablonları görünmüyor veya Visual Studio'da çalışmıyor  
 Visual Studio, .NET Framework ve Microsoft Office desteklenen bir sürümünü yükleyin, ancak Office proje şablonları ya da görünmez Visual Studio'da **yeni proje** iletişim kutusu veya bir kullanmaya çalıştığınızda bir hata alıyorsunuz aşağıdakileri denetleyin:  
  
-   Microsoft Office geliştirici araçları, bilgisayarınızda yüklü olduğundan emin olun.  
  
     Office geliştirici araçları, Visual Studio'nun isteğe bağlı bir bileşen olan, ancak bunlar genellikle otomatik olarak Visual Studio ile birlikte yüklenir. Yüklenecek özellikleri belirterek Visual Studio yüklemesini özelleştirirseniz, seçtiğinizden emin olun **Microsoft Office geliştirici araçları** araçlarını yüklemek için Kurulum sırasında.  
  
     Bu araçlar yüklü olduğundan emin olmak için Visual Studio Kurulum programını başlatın ve seçin **Değiştir** düğmesi. Seçin **Microsoft Office geliştirici araçları** onay kutusunu işaretleyin ve ardından **güncelleştirme** düğmesi.  
  
-   Tıklat Çalıştır tarafından dağıtılan Office sürümü çalıştırdığınız değil emin olun. Bkz: [nasıl yapılır: Outlook bir bilgisayardaki bir Tıklat Çalıştır uygulaması olup olmadığını doğrulayın](http://msdn.microsoft.com/library/office/ff864733(v=office.14).aspx).  
  
-   Microsoft Office yalnızca bir sürümü çalıştırdığınızdan emin olun.  
  
 Sorun yaşamaya devam ederseniz, bkz: [Office çözümlerindeki hatalar için ek destek](../vsto/additional-support-for-errors-in-office-solutions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlarken &#40; Office geliştirme Visual Studio &#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Nasıl yapılır: Office çözümleri geliştirmek için bilgisayarı yapılandırma](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)   
 [Nasıl yapılır: Office çalışma zamanı için yeniden dağıtılabilir Visual Studio Araçları'nı yükleme](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)   
 [Nasıl yapılır: Office birincil birlikte çalışma derlemelerini yükleme](../vsto/how-to-install-office-primary-interop-assemblies.md)   
 [Office uygulaması ve proje türüne göre kullanılabilir özellikler](../vsto/features-available-by-office-application-and-project-type.md)  
  
  