---
title: Çözümleri Microsoft Office'in farklı sürümlerinde çalıştırma
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], multiple Office versions
- Office applications [Office development in Visual Studio], multiple Office versions
- Office development in Visual Studio, multiple Office versions
- Office solutions [Office development in Visual Studio]
- multiple Office versions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 153b8faa356ceed9eecc5c616c2330f980728e49
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693974"
---
# <a name="run-solutions-in-different-versions-of-microsoft-office"></a>Çözümleri Microsoft Office'in farklı sürümlerinde çalıştırma
    
## <a name="run-office-solutions-created-by-using-visual-studio-2010-and-above"></a>Office çözümlerini Visual Studio 2010 kullanarak ve yukarıda oluşturulan çalıştırın  
  
|Proje şablonu tarafından hedeflenen Office sürümü|Hedef .NET Framework projenin<sup>1</sup>|Çözümü çalıştırmadan Office sürümleri|Son kullanıcı bilgisayarda gerekli çalışma zamanı|  
|--------------------------------------------------------|------------------------------------------------------|--------------------------------------------------|-------------------------------------------|  
|Office 2016 ve [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]|[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya üzeri|Office 2016<br /><br /> [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]<br /><br /> [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]<br /><br /> 2007 Microsoft Office sistemi<sup>2</sup>|Office çalışma zamanı için Visual Studio 2010 Araçları|  
|[!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]|[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya üzeri|Office 2016<br /><br /> [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]<br /><br /> [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]<br /><br /> 2007 Microsoft Office sistemi<sup>2</sup>|Office çalışma zamanı için Visual Studio 2010 Araçları|  
|[!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]|.NET Framework 3.5|Office 2016<br /><br /> [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]<br /><br /> [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]|Office çalışma zamanı için Visual Studio 2010 Araçları|  
|2007 Microsoft Office sistemi|[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki sürümlerde,<br /><br /> veya<br /><br /> .NET Framework 3.5|Office 2016<br /><br /> [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]<br /><br /> [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]<br /><br /> 2007 Microsoft Office sistemi|Office çalışma zamanı için Visual Studio 2010 Araçları|  
  
 1. .NET Framework sürümünü, projenizin hedeflediği çalıştırmak, çözümünüz için son kullanıcı bilgisayarlarında gereklidir. Örneğin, .NET Framework 3.5 projeniz .NET Framework 3.5 hedefliyorsa, son kullanıcı bilgisayarlarında gereklidir. Bu örnekte, çözümünüzü yalnızca çalışmaz [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] son kullanıcı bilgisayarlara yüklenir.  
  
 2. Yalnızca yeni özellikler kullanmıyorsa, bu senaryoda çözümü hatasız 2007 Microsoft Office sistemi çalıştıracak [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)].  
  
## <a name="run-office-solutions-created-by-using-versions-of-visual-studio-prior-to-visual-studio-2010"></a>Office çözümlerini Visual Studio 2010 önce Visual Studio sürümleri kullanılarak oluşturulan çalıştırın  
 Microsoft Office uygulamaları, Visual Studio 2010 önce Visual Studio sürümleri kullanılarak oluşturduğu çözümleri çalıştırabilirsiniz. Bazı durumlarda, bu çözümlerin farklı sürümlerini gerektirir [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Farklı sürümlerini [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yüklü yan yana aynı bilgisayarda olabilir.  
  
 Aşağıdaki tabloda hangi sürümlerinin Microsoft Office çözümlerini Visual Studio'nun önceki sürümleri kullanılarak oluşturulan çalıştırabilir ve hangi sürümlerinin gösterilmektedir [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] ve her çözüm için .NET Framework gereklidir.  
  
|Visual Studio çözümü oluşturmak için kullanılan sürümü|Proje şablonu tarafından hedeflenen Office sürümü|Çözümü çalıştırmadan Office sürümleri|Son kullanıcı bilgisayarda gerekli çalışma zamanı|Son kullanıcı bilgisayarda gerekli .NET Framework sürümü|  
|----------------------------------------------------------|--------------------------------------------------------|--------------------------------------------------|-------------------------------------------|----------------------------------------------------------|  
|Visual Studio 2008 Professional<br /><br /> veya<br /><br /> Visual Studio Team System 2008|2007 Microsoft Office sistemi|[!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] ve [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] <sup>1</sup><br /><br /> 2007 Microsoft Office sistemi|Office çalışma zamanı için Visual Studio 2010 Araçları<sup>1</sup><br /><br /> veya<br /><br /> Microsoft Office sistemi için Visual Studio Araçları (sürüm 3.0 çalışma zamanı)|.NET Framework 3.5|  
|Visual Studio 2005 VSTO 2005 SE ile aşağıdaki sürümlerinden birini<sup>2</sup> yüklü:<br /><br /> -Office için visual Studio 2005 Araçları<br />-Visual Studio Team System 2005<br />-Visual Studio 2005 Professional|2007 Microsoft Office sistemi|[!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] ve [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] (yalnızca 32-bit<sup>3</sup>)<br /><br /> 2007 Microsoft Office sistemi|Office için Visual Studio 2005 Araçları Edition çalışma zamanı saniye|.NET framework 2.0, .NET Framework 3.0 veya .NET Framework 3.5|  
|Visual Studio aşağıdaki sürümlerinden birini:<br /><br /> -Visual Studio 2008 Professional<br />-Visual Studio Team System 2008<br />-Office için visual Studio 2005 Araçları (ile veya olmadan VSTO 2005 SE<sup>2</sup> yüklü)<br />-Visual Studio Team System 2005 (ile veya olmadan VSTO 2005 SE<sup>2</sup> yüklü)<br />-VSTO 2005 SE visual Studio 2005 Professional<sup>2</sup> yüklü|Microsoft Office 2003|[!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] ve [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] (yalnızca 32-bit<sup>3</sup>)<br /><br /> 2007 Microsoft Office sistemi<br /><br /> Microsoft Office 2003|Office için Visual Studio 2005 Araçları Edition çalışma zamanı saniye|.NET framework 2.0, .NET Framework 3.0 veya .NET Framework 3.5|  
  
 1. [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] ve [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] uygulamalar Office çalışma zamanı için Visual Studio 2010 araçları içerir. Bu nedenle, bu uygulamalar her zaman Office çalışma zamanı için Visual Studio 2010 Araçları yerine Visual Studio Araçları Microsoft Office sistemi için kullanın (sürüm 3.0 çalışma zamanı) Bu senaryoda. Office çalışma zamanı veya Microsoft Office sistemi için Visual Studio Araçları, Visual Studio 2010 Araçları 2007 Microsoft Office sistemi uygulamalarında kullanabilirsiniz (sürüm 3.0 çalışma zamanı).  
  
 2. VSTO 2005 SE Microsoft Office 2003 ve 2007 Microsoft Office sistemi için VSTO eklentisi proje şablonları sağlayan ücretsiz bir Visual Studio eklentisidir. Visual Studio 2005 Professional, Office için Visual Studio 2005 Araçları veya Visual Studio Team System 2005'teki bir sürüm ile yüklenebilir. Daha fazla bilgi için bkz: [Office ikinci sürümü için Visual Studio 2005 Araçları](http://go.microsoft.com/fwlink/?LinkId=148446).  
  
 3. Office ikinci Edition çalışma zamanı için Visual Studio 2005 Araçları gerektiren office çözümleri 64 bit sürümleri ile uyumlu olmadığında [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] ve [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]. Bu çözümlerin 64 bit sürümünde çalıştırmak için [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] veya [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)], projeye yükseltmelisiniz [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)] veya 2007 Microsoft Office sistemi hedefleyen Visual Studio 2008 projesine.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Office çalışma zamanı yükleme senaryoları için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)   
 [Office çözümleri geliştirmek için bilgisayarı yapılandırma](../vsto/running-solutions-in-different-versions-of-microsoft-office.md)  
  
  