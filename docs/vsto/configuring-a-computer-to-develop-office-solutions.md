---
title: Office çözümleri geliştirmek için bilgisayarı yapılandırma | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, installing tools
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 59c00639ce839962c06cacf3c036a5cd8f74b508
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="configuring-a-computer-to-develop-office-solutions"></a>Office Çözümleri Geliştirmek İçin Bilgisayarı Yapılandırma

VSTO eklentileri ve Microsoft Office için özelleştirmeler oluşturmak için Visual Studio, .NET Framework ve Microsoft Office desteklenen bir sürümünü yükleyin.

|Yazılım|Desteklenen sürümleri|
|--------------|------------------------|
|Visual Studio 2017| Sahip herhangi bir sürüm **Office/SharePoint geliştirme** iş yükü.|
|.NET Framework|-.NET Framework 4 veya üstü.|
|Microsoft Office|<ul><li>Tüm Office Professional Plus Office 365 için de dahil olmak üzere Office suite sürümü.</li><li>Uygulamalardan herhangi biri aşağıdaki tek başına:<br /><br /> <ul><li>Excel</li><li>InfoPath (Office 2013 ve yalnızca Office 2010)</li><li>Outlook</li><li>PowerPoint</li><li>Proje</li><li>Visio</li><li>Word</li></ul></li></ul><br /> Visual Basic for Applications (VBA) Office bir parçası olarak yüklenmelidir. **Önemli:** Office 2010 uygulamaları Tıklat Çalıştır sürümleri desteklenmez.|

Ayrıntılı yükleme adımları için bkz: [nasıl yapılır: Office çözümleri geliştirmek için bilgisayarı yapılandırma](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md).

## <a name="if-project-templates-dont-appear-or-they-dont-work-in-visual-studio"></a>Proje şablonları görünmüyor veya Visual Studio'da çalışmıyor

Visual Studio, .NET Framework ve Microsoft Office desteklenen bir sürümünü yükleyin, ancak Office proje şablonları ya da görünmez Visual Studio'da **yeni proje** iletişim kutusu veya bir kullanmaya çalıştığınızda bir hata alıyorsunuz aşağıdakileri denetleyin:

- Microsoft Office geliştirici araçları, bilgisayarınızda yüklü olduğundan emin olun.

     Office geliştirici araçları, Visual Studio'nun isteğe bağlı bir bileşen olan, ancak bunlar genellikle otomatik olarak Visual Studio ile birlikte yüklenir. Yüklenecek özellikleri belirterek Visual Studio yüklemesini özelleştirirseniz, seçtiğinizden emin olun **Microsoft Office geliştirici araçları** araçlarını yüklemek için Kurulum sırasında.

     Bu araçlar yüklü olduğundan emin olmak için Visual Studio Kurulum programını başlatın ve seçin **Değiştir** düğmesi. Seçin **Microsoft Office geliştirici araçları** onay kutusunu işaretleyin ve ardından **güncelleştirme** düğmesi.

- Tıklat Çalıştır tarafından dağıtılan Office sürümü çalıştırdığınız değil, emin olun. Bkz: [nasıl yapılır: Outlook bir bilgisayardaki bir Tıklat Çalıştır uygulaması olup olmadığını doğrulayın](http://msdn.microsoft.com/library/office/ff864733(v=office.14).aspx).

- Microsoft Office yalnızca bir sürümü çalıştırdığınızdan emin olun.

Sorun yaşamaya devam ederseniz, bkz: [Office çözümlerindeki hatalar için ek destek](../vsto/additional-support-for-errors-in-office-solutions.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Başlarken &#40;Visual Studio'da Office geliştirme&#41;](../vsto/getting-started-office-development-in-visual-studio.md)  
[Nasıl Yapılır: Office Çözümleri Geliştirmek İçin Bilgisayarı Yapılandırma](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)  
[Nasıl Yapılır: Office Çalışma Zamanı Yeniden Dağıtılabilir için Visual Studio Araçları Yükleme](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)  
[Nasıl Yapılır: Office Birincil Birlikte Çalışma Derlemelerini Yükleme](../vsto/how-to-install-office-primary-interop-assemblies.md)  
[Office Uygulaması ve Proje Türüne Göre Kullanılabilir Özellikler](../vsto/features-available-by-office-application-and-project-type.md)
