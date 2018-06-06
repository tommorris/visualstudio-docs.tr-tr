---
title: Office çalışma zamanı yükleme senaryoları için Visual Studio Araçları
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Studio Tools for Office runtime, installation scenarios
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2af3f4834fecfe4fcfba30f736892057893ed143
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767731"
---
# <a name="visual-studio-tools-for-office-runtime-installation-scenarios"></a>Office çalışma zamanı yükleme senaryoları için Visual Studio Araçları
  Office çalışma zamanı için Visual Studio 2010 Araçları üç şekilde yükleyebilirsiniz:  
  
-   Visual Studio yüklediğinizde.  
  
-   Microsoft Office yüklediğinizde.  
  
-   Office çalışma zamanı yeniden dağıtılabilir için Visual Studio 2010 araçları yüklediğinizde.  
  
 Yüklenen çalışma zamanı bileşenleri bilgisayar ve yükleme senaryosu yapılandırmasına göre değişir.  
  
## <a name="runtime-components-that-are-installed-in-each-installation-scenario"></a>Her yükleme senaryosunda yüklü çalışma zamanı bileşenleri  
 Office çalışma zamanı için Visual Studio 2010 Araçları üç bileşeni vardır: Office çözüm yükleyicisi, .NET Framework 3.5 için Office uzantıları ve Office uzantıları [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü. Çalışma zamanı yükleme Office çözüm yükleyicisi her zaman yüklenir. .NET Framework için Office uzantıları yüklemesi bilgisayar ve yükleme senaryosu yapılandırmasına bağlıdır. Çalışma zamanı ilk yüklendiğinde Office uzantılardan birine yüklenemezse, belirli gereksinimleri karşılandığında çalışma zamanı otomatik olarak eksik Office uzantıları daha sonra yükler. Bu özellik çalışma zamanının adlı *isteğe bağlı yükleme*.  
  
 Aşağıdaki tabloda, hangi çalışma zamanı bileşenlerini her çalışma zamanı yükleme senaryosunda varsayılan olarak yüklenen gösterir. Her senaryo hakkında daha fazla bilgi daha sonra görünür.  
  
|Çalışma zamanı yükleme senaryoları|Office çözüm yükleyicisi|.NET Framework 3.5 için Office uzantıları|Office uzantıları [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]|Office uzantıları [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]|  
|-----------------------------------|----------------------------|--------------------------------------------------|---------------------------------------------------------------------------------------|---------------------------------------------------------------------------|  
|İle [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] ve sonraki sürümler|Evet|Evet, .NET Framework 3.5 yüklü ise.|Evet|Evet|  
|İle [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]|Evet|Evet, .NET Framework 3.5 yüklü ise.|Hayır|Hayır|  
|Office 2010 Service Pack 1 (SP1) veya daha yenisi|Evet|Evet, .NET Framework 3.5 yüklü ise.|Evet, varsa [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] zaten yüklü.|Hayır|  
|Çalışma zamanı yeniden dağıtılabilir|Evet|Evet, .NET Framework 3.5 yüklüyse|Evet, varsa [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] zaten yüklü.|Evet, varsa [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] zaten yüklü.|  
  
### <a name="install-the-runtime-with-visual-studio-or-the-microsoft-office-developer-tools-for-visual-studio"></a>Visual Studio için Visual Studio veya Microsoft Office geliştirici araçları ile çalışma zamanı yükleme  
 Visual Studio'da Office uzantıları için Office geliştirici araçları yüklediğinizde [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] ve [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] geliştirme bilgisayarınızda her zaman yüklenir. Yalnızca .NET Framework 3.5 geliştirme bilgisayarınızda zaten varsa .NET Framework 3.5 için Office uzantıları yüklenir. Yükledikten sonra .NET Framework 3.5 yüklerseniz [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)], .NET Framework 3.5, .NET Framework 3.5, bir Office proje oluşturma, ilk kez hedefler için çalışma zamanı Office uzantıları otomatik olarak yükler.  
  
> [!WARNING]  
>  Kullanarak .NET Framework 3.5 hedefleyen bir Office proje oluşturulamıyor [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] veya sonraki bir sürümü.  
  
 Office Geliştirici Araçları'nı yükleme hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office çözümleri geliştirmek için bilgisayarı yapılandırma](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md).  
  
### <a name="install-the-runtime-with-office"></a>Office çalışma zamanı yükleme  
 Office yüklediğinizde, bilgisayarda .NET Framework 3.5 zaten varsa, .NET Framework 3.5 için Office uzantıları yüklenir. .NET Framework 3.5 Office sonra yüklerseniz, çalışma zamanı Office uzantıları bir Office uygulamasında .NET Framework 3.5 hedefleyen bir çözüm yüklemeye .NET Framework 3.5 ilk kez otomatik olarak yükler.  
  
 Office uzantıları [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya Office ile daha sonra yüklenmemiş olsa bile [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra Office yüklediğinizde zaten.  
  
 Office uzantıları [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] Office ile birlikte yüklenir. Son kullanıcılar için Office uzantıları elde edebilirsiniz [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] bir Windows güncelleştirmesi yükleyerek.  
  
 Kullanıcılarınızın uygulamanızın kullanmak için gerekli genişletmeleri olmasını sağlamak için çözümünüz için bir önkoşul olarak yeniden dağıtılabilir Office çalışma zamanı için Visual Studio 2010 Araçları en son sürümünü içerir. Önkoşullar hakkında daha fazla bilgi için bkz: [dağıtım için Office çözümü önkoşulları](http://msdn.microsoft.com/en-us/9f672809-43a3-40a1-9057-397ce3b5126e).  
  
### <a name="install-the-runtime-by-using-the-runtime-redistributable"></a>Çalışma zamanı yeniden dağıtılabilir kullanarak çalışma zamanı yükleme  
 Office çalışma zamanı yeniden dağıtılabilir için Visual Studio 2010 Araçları el ile çalıştırarak veya Office çözümünü dağıtırken yeniden dağıtılabilir önkoşul olarak dahil olmak üzere çalışma zamanı yükleyebilirsiniz.  
  
 Office çalışma zamanı yeniden dağıtılabilir, .NET Framework 3.5 için Office uzantıları ve Office uzantıları için Visual Studio 2010 araçları kullanarak çalışma zamanı yüklediğinizde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya üstü değilse yüklü .NET karşılık gelen sürümleri Framework zaten bilgisayarda mevcut. Çalışma zamanı yüklü olduğunda bilgisayarda .NET Framework'ün bu sürümlerinden birini eksikse, eksik .NET Framework sürümü için Office uzantıları o anda yüklü değil. .NET Framework daha sonra eksik sürümünü yüklerseniz, çalışma zamanı karşılık gelen Office uzantıları sonraki kez (çalışma zamanı dağıtılan bir çözüm yüklenmişse, uzantıları gerektiren bir çözüm yüklendiğinde otomatik olarak yükler. ClickOnce kullanarak) veya (çalışma zamanı Windows Installer kullanılarak dağıtılan çözümü olan yüklenmişse) yüklenemedi.  
  
 ClickOnce çözüm önkoşulları hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office çözümlerini çalıştırmak için son kullanıcı bilgisayarlarında Önkoşulları Yükleme](http://msdn.microsoft.com/en-us/74dd2c52-838f-4abf-b2b4-4d7b0c2a0a98). Çalışma zamanı yeniden dağıtılabilir paketi el ile yükleme hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office çalışma zamanı yeniden dağıtılabilir için Visual Studio araçlarını yükleme](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Office çalışma zamanı için Visual Studio araçlarındaki derlemeler](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md)  
  
  