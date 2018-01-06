---
title: VSTO eklentileri mimarisi | Microsoft Docs
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
- VSTOLoader.dll
- architecture [Office development in Visual Studio], application-level add-ins
- vstoee.dll
- application-level add-ins [Office development in Visual Studio], architecture
- add-ins [Office development in Visual Studio], architecture
ms.assetid: 978f102f-15c6-44e4-84e8-80b161408324
caps.latest.revision: "70"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: a4dbe8611da0814bfaa148b2d9c4caf7f7858d9d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="architecture-of-vsto-add-ins"></a>VSTO Eklentileri Mimarisi
  Visual Studio'da Office geliştirici araçları kullanılarak oluşturulan VSTO eklentileri kararlılık ve güvenlik sağlayan mimari özelliklere sahiptir ve bunları Microsoft Office ile yakından çalışmaya etkinleştirin. Bu konuda aşağıdaki VSTO eklentileri yönleri açıklanmaktadır:  
  
-   [VSTO eklentileri anlama](#UnderstandingAddIns)  
  
-   [VSTO eklentilerini bileşenleri](#AddinComponents)  
  
-   [Microsoft Office uygulamalarıyla VSTO eklentileri nasıl çalışır](#HowAddinsWork)  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
 VSTO eklentileri oluşturma hakkında daha fazla genel bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md) ve [Başlarken VSTO eklentilerini programlamaya](../vsto/getting-started-programming-vsto-add-ins.md).  
  
##  <a name="UnderstandingAddIns"></a>VSTO eklentileri anlama  
 Bir VSTO eklenti oluşturmak için Visual Studio'da Office geliştirici araçları kullandığınızda, Microsoft Office uygulama tarafından yüklenen bir yönetilen kod derlemesi oluşturun. Derleme yüklendikten sonra VSTO eklenti uygulama (örneğin, bir kullanıcı bir menü öğesini tıkladığında) uygulamasında oluşturulan olaylara yanıt verebilir. VSTO eklenti ayrıca nesne modelini çağırıp uygulamayı genişletebilir çağırabilir ve sınıflarda birini kullanabilirsiniz [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)].  
  
 Derleme uygulamanın COM bileşenlerini birincil birlikte çalışma derlemesi uygulamanın üzerinden iletişim kurar. Daha fazla bilgi için bkz: [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md) ve [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
 Her VSTO eklenti farklı uygulama etki alanında birden çok VSTO eklentileri için bir uygulama yüklü değilse yüklenir. Başka bir deyişle, bir VSTO hatalı davranan eklenti diğer VSTO başarısız olmasına eklentileri sebep olamaz. Ayrıca uygulama kapatıldığında tüm VSTO eklenti derlemelerinin bellekten olduğundan emin olmak için yardımcı olur. Uygulama etki alanları hakkında daha fazla bilgi için bkz: [uygulama etki alanları](/dotnet/framework/app-domains/application-domains).  
  
> [!NOTE]  
>  VSTO Visual Studio'da Office geliştirici araçları kullanarak oluşturduğunuz eklentileri, yalnızca bir son kullanıcı tarafından Microsoft Office uygulama ana bilgisayar başlatıldığında kullanılmak üzere tasarlanmıştır. Uygulamayı programlı olarak (örneğin, Otomasyon kullanarak) başlatılırsa, VSTO eklenti beklendiği gibi çalışmayabilir.  
  
##  <a name="AddinComponents"></a>VSTO eklentilerini bileşenleri  
 VSTO eklenti derlemesi ana bileşen olsa da, Microsoft Office uygulamaları nasıl bulmak ve VSTO eklentileri yük önemli bir rol oynar diğer birçok bileşen vardır.  
  
### <a name="registry-entries"></a>Kayıt defteri girdileri  
 Microsoft Office uygulamaları VSTO eklentileri için kayıt defteri girdileri kümesi bakarak bulur. VSTO eklentileri tarafından kullanılan kayıt defteri girdilerinin tam bir listesi için bkz: [VSTO eklentileri için kayıt defteri girişleri](../vsto/registry-entries-for-vsto-add-ins.md).  
  
 Çözümünüzü yapılandırdığınızda, Visual Studio hata ayıklama ve VSTO eklentinizi çalıştırın, tüm gerekli kayıt defteri girdilerini geliştirme bilgisayarınızda oluşturur. Daha fazla bilgi için bkz: [Office çözümleri oluşturma](../vsto/building-office-solutions.md).  
  
 Çözümünüzü dağıtmak için ClickOnce kullanırsanız yayımlama işlemi tarafından otomatik olarak oluşturulan Kurulum programı son kullanıcı bilgisayarda kayıt defteri anahtarlarını oluşturur. Daha fazla bilgi için bkz: [tarafından ClickOnce kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
### <a name="deployment-manifest-and-application-manifest"></a>Dağıtım bildirimi ve uygulama bildirimi  
 VSTO eklentileri belirlemek ve VSTO eklenti derlemesi en güncel sürümünü yüklemek için dağıtım bildirimleri ve uygulama bildirimlerini kullanın. Dağıtım noktaları geçerli uygulama bildirimine bildirimi. Uygulama bildirimini VSTO eklenti derlemeye işaret ve derlemede yürütmek için giriş noktası sınıfını belirler. Daha fazla bilgi için bkz: [uygulama ve dağıtım bildirimlerini Office çözümlerinde](../vsto/application-and-deployment-manifests-in-office-solutions.md).  
  
### <a name="visual-studio-tools-for-office-runtime"></a>Office çalışma zamanı için Visual Studio Araçları  
 VSTO Visual Studio'da Office geliştirici araçları kullanılarak oluşturulan eklentileri çalıştırmak için son kullanıcı bilgisayarlarında yüklü olmalıdır [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yüklü. Çalışma zamanı yönetilmeyen bileşenleri ve Yönetilen derlemeler kümesini içerir. Yönetilmeyen bileşenleri VSTO eklenti derlemesi yüklenemiyor. Yönetilen derlemeler VSTO eklenti kodunuzun konak uygulamasını otomatikleştirmek ve genişletmek için kullandığı nesne modeli sağlar.  
  
 Daha fazla bilgi için bkz: [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
##  <a name="HowAddinsWork"></a>Microsoft Office uygulamalarıyla VSTO eklentileri nasıl çalışır  
 Bir kullanıcı bir Microsoft Office uygulamasını başlattığında uygulama bulmak ve VSTO eklenti derlemesi en güncel sürümünü yüklemek için dağıtım bildirimi ve uygulama bildirimini kullanır. Aşağıdaki çizim bu VSTO eklentileri temel mimarisini göstermektedir.  
  
 ![2007 office eklenti mimarisi](../vsto/media/office07addin.png "2007 Office eklenti mimarisi")  
  
> [!NOTE]  
>  Office çözümlerinde hedef [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], konak uygulama tarafından nesne modeline çağrı PIA içine doğrudan çağırmak yerine çözüm derlemesindeki katıştırılmış PIA tür bilgisini kullanarak çözümler. Daha fazla bilgi için bkz: [tasarlama ve oluşturma Office çözümleri](../vsto/designing-and-creating-office-solutions.md).  
  
### <a name="loading-process"></a>Yükleme işlemi  
 Bir kullanıcı bir uygulama başlattığında aşağıdaki adımlardan oluşur:  
  
1.  Uygulama, Visual Studio'da Office geliştirici araçları kullanılarak oluşturulan VSTO Add-ins tanımlamak girişleri için kayıt defterini denetler.  
  
2.  Uygulama bu kayıt defteri girdileri bulursa, uygulama VSTOLoader.dll yükleyen VSTOEE.DLL'i yükler. Yönetilmeyen bunlar Office çalışma zamanı için Visual Studio 2010 Araçları yükleyicisi bileşenleri DLL'leri. Daha fazla bilgi için bkz: [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
3.  VSTOLoader.dll yükleyen [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)] ve yönetilen kısmına başlar [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
4.  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Bildirim güncelleştirmeleri denetler ve en son uygulama ve dağıtım bildirimlerini indirir.  
  
5.  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Bir dizi güvenlik denetimi gerçekleştirir. Daha fazla bilgi için bkz: [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md).  
  
6.  VSTO eklenti çalıştırmak için güvenilir olması durumunda [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] derleme güncelleştirmeleri denetlemek için dağıtım bildirimi ve uygulama bildirimini kullanır. Derleme yeni bir sürümü kullanılabilir durumda, çalışma zamanı derlemesi için yeni sürümü indirir [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] önbellek istemci bilgisayardaki. Daha fazla bilgi için bkz: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
7.  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] VSTO eklenti derlemesi yüklemek yeni bir uygulama etki alanı oluşturur.  
  
8.  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] VSTO eklenti derlemesi uygulama etki alanına yükler.  
  
9. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Çağrıları <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> VSTO siz kıldıysanız eklentinizi, yöntemi.  
  
     İsteğe bağlı olarak, bir nesneyi VSTO eklentinizi diğer Microsoft Office çözümleri için kullanıma sunmak için bu yöntemin üzerine yazabilir. Daha fazla bilgi için bkz: [VSTO eklentileri diğer Office Çözümlerinden gelen çağırma kodda](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md).  
  
10. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Çağrıları <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> VSTO siz kıldıysanız eklentinizi, yöntemi.  
  
     İsteğe bağlı olarak bir Genişletilebilirlik arabirimini uygulayan bir nesneyi döndürerek Microsoft Office özelliğini genişletmek için bu yöntemin üzerine yazabilir. Daha fazla bilgi için bkz: [özelleştirme kullanıcı Arabirimi özellikleri tarafından kullanarak genişletilebilirlik arabirimleri](../vsto/customizing-ui-features-by-using-extensibility-interfaces.md).  
  
    > [!NOTE]  
    >  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Ayrı çağrılar için yapar <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> konak uygulama tarafından desteklenen her genişletilebilirlik arayüzü yöntemi. İlk çağrı rağmen <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> yöntemi genellikle olur çağırmadan önce `ThisAddIn_Startup` yöntemi, VSTO eklentinizi hale ne zaman dair varsayımlar <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> yöntemi çağrılır veya kaç kez çağrılır.  
  
11. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Çağrıları `ThisAddIn_Startup` VSTO eklentinizi yöntemi. Bu yöntem varsayılan olay işleyicisidir için <xref:Microsoft.Office.Tools.AddInBase.Startup> olay. Daha fazla bilgi için bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da Office çözümleri mimarisi](../vsto/architecture-of-office-solutions-in-visual-studio.md)   
 [Belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md)   
 [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Office çözümleri geliştirme](../vsto/developing-office-solutions.md)   
 [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md)   
 [Office Çözümünü Dağıtma](../vsto/deploying-an-office-solution.md)  
  
  