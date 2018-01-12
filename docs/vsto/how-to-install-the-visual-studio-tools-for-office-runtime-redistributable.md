---
title: "Nasıl yapılır: Office çalışma zamanı için yeniden dağıtılabilir Visual Studio Araçları'nı yükleme | Microsoft Docs"
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
- Office runtime [Office development in Visual Studio]
- installing Office development tools in Visual Studio
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 5f76191ca8b41f252e5009c0d3e7e09415f6f081
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-install-the-visual-studio-tools-for-office-runtime-redistributable"></a>Nasıl Yapılır: Office Çalışma Zamanı Yeniden Dağıtılabilir için Visual Studio Araçları Yükleme
  Office çalışma zamanı için Visual Studio 2010 Araçları, Microsoft Office geliştirici araçları kullanılarak oluşturulan çözümleri çalıştıran her bilgisayara yüklenmelidir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Çalışma zamanı yüklediğinizde otomatik olarak yüklenir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]ve Microsoft Office. Daha fazla bilgi için bkz: [Office çalışma zamanı yükleme senaryoları için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md).  
  
 Aşağıdaki durumlarda aşağıdaki el ile yükleme yönergeleri izleyerek gerekebilir:  
  
-   Yüklemenize gerek [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] bir sunucuda. Örneğin, kullanmak istediğiniz <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> bir sunucuda belge düzeyi çözümleri yönetmek için sınıf.  
  
-   Çalışma zamanı zaten yüklenmiş Office çözümleri için diğer tüm önkoşullara sahip bir bilgisayara yüklemeniz gerekir.  
  
    > [!NOTE]  
    >  .NET Framework'ü yüklemek için yönetici geliştirme bilgisayarındaki olmalıdır ve [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
### <a name="to-install-the-visual-studio-tools-for-office-runtime"></a>Office çalışma zamanı için Visual Studio Araçları'nı yüklemek için  
  
1.  Yükleme [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü.  
  
    -   Karşıdan yüklemek için [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], bkz: [Microsoft .NET Framework 4 (Web Yükleyicisi)](http://go.microsoft.com/fwlink/?LinkId=178957).  
  
    -   Karşıdan yüklemek için [!INCLUDE[net_client_v40_long](../vsto/includes/net-client-v40-long-md.md)], bkz: [Microsoft .NET Framework 4 istemci profili (Web Yükleyicisi)](http://go.microsoft.com/fwlink/?LinkId=178958).  
  
    -   Karşıdan yüklemek için [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], bkz: [Microsoft .NET Framework 4.5](http://www.microsoft.com/download/details.aspx?id=30653).  
  
2.  Yüklemek için vstor_redist.exe çalıştırmak [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
     Bu kurulum dosyalarından indirebilirsiniz [Office çalışma zamanı için Visual Studio 2010 Araçları](http://go.microsoft.com/fwlink/?LinkId=140384). Önkoşulları [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] .NET Framework önkoşulları eşleşmesi.  
  
     [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]Dil paketlerini içerir. İngilizce dışında bir dil için Windows yüklemesini ayarlarsanız, Windows için kullandığınız aynı dilde çalışma zamanı iletilerini görüntüleyebilirsiniz. Benzer şekilde, son kullanıcıların yüklerseniz [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] ve çalışma zamanı iletilerini Windows aynı dilde görünür ayarlanan İngilizce dışında bir dil için Windows yüklemeleri üzerinde çözümlerinizi çalıştırın. Bazı durumlarda, ek dil paketlerini gerekebilir. Örneğin, birden fazla dil ayarı Windows kopyanızı kullanıyorsa veya zaten yükledikten sonra başka bir dil için geçiş ek dil paketlerini gerekebilir [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Dil paketleri bulabilirsiniz [Microsoft Visual Studio 2010 Araçları Microsoft Office sistemi (sürüm 4.0 çalışma zamanı) Dil Paketi için](http://go.microsoft.com/fwlink/?LinkId=140386).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlarken &#40; Office geliştirme Visual Studio &#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Office çözümleri geliştirmek için bilgisayarı yapılandırma](../vsto/configuring-a-computer-to-develop-office-solutions.md)   
 [Nasıl yapılır: Office çözümleri geliştirmek için bilgisayarı yapılandırma](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)   
 [Nasıl yapılır: Office birincil birlikte çalışma derlemelerini yükleme](../vsto/how-to-install-office-primary-interop-assemblies.md)   
 [ServerDocument sınıfını kullanarak bir sunucu üzerinde belgeleri yönetme](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)   
 [Office Çözümünü Dağıtma](../vsto/deploying-an-office-solution.md)  
  
  