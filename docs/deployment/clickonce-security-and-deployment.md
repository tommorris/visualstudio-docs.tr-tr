---
title: ClickOnce güvenliği ve dağıtımı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows applications, ClickOnce deployment
- deploying applications [ClickOnce]
- ClickOnce deployment
- publishing, ClickOnce
ms.assetid: abab6d34-c3c2-45c1-a8b6-43c7d3131e7a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4ec2e74623c39640517ae73786d7865143bf1505
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31562838"
---
# <a name="clickonce-security-and-deployment"></a>ClickOnce Güvenliği ve Dağıtımı
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] yüklü ve minimum kullanıcı etkileşimi ile çalıştırın kendi kendini güncelleştirme ve Windows tabanlı uygulamalar oluşturmanıza olanak tanıyan bir dağıtım teknolojisidir. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Yayımlama ve projelerinizi Visual Basic ve Visual C# ile geliştirdiyseniz ClickOnce teknolojisiyle dağıtılan uygulamaları güncelleştirmek için tam destek sağlar. Visual C++ uygulamalarını dağıtma hakkında daha fazla bilgi için bkz: [Visual C++ uygulamaları için ClickOnce dağıtımı](/cpp/ide/clickonce-deployment-for-visual-cpp-applications).  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Dağıtım üç önemli sorunları dağıtımda üstesinden gelen:  
  
-   **Uygulamaları güncelleştirmede karşılaşılan zorluklar.** Microsoft Windows Installer dağıtımı ile bir uygulama güncelleştirildiğinde, kullanıcı bir msp dosyası bir güncelleştirmeyi yüklemek ve yüklü ürün uygulayabilirsiniz; ile [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtımı, güncelleştirmeleri otomatik olarak sağlayabilirsiniz. Yalnızca değiştirilen uygulama bölümlerinin indirilir ve ardından tam, güncelleştirilmiş uygulama yan yana bir klasörden yeniden yüklenir.  
  
-   **Kullanıcının bilgisayarına etkisi.** Windows Installer dağıtımı ile uygulamalar genellikle sürüm çakışmaları olasılığıyla paylaşılan bileşenler kullanır; ile [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım, her uygulamanın kendi içinde yer alan ve diğer uygulamalarla müdahale edemez.  
  
-   **Güvenlik izinleri.** Windows Installer dağıtımı, yönetim izinleri gerektirir ve yalnızca sınırlı kullanıcı yüklemesine izin verir; [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtımı yönetici olmayan kullanıcılara yükleme olanağı sağlar ve yalnızca uygulama için gerekli kod erişimi güvenliği izinleri verir.  
  
 Geçmişte, bu sorunları bazen ödün Yükleme kolaylığı için zengin bir kullanıcı arabirimi, Windows tabanlı uygulamalar yerine Web uygulamaları oluşturmaya karar geliştiricilerin neden oldu. Kullanılarak dağıtılan uygulamaları kullanarak [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], her iki teknolojinin en iyi olabilir.  
  
## <a name="what-is-a-clickonce-application"></a>ClickOnce uygulaması nedir?  
 A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamasıdır Windows Presentation Foundation (.xbap), Windows Forms (.exe), konsol uygulaması (.exe) veya Office çözümü (.dll) kullanılarak yayımlanan [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] teknolojisi. Yayımlayabilirsiniz bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] üç farklı yolla uygulama: bir Web sayfası, bir ağ dosya paylaşımı veya bir CD-ROM gibi medya. A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bir son kullanıcının bilgisayarda yüklü ve hatta bilgisayarı çevrimdışı olduğunda veya kalıcı olarak herhangi bir şey son kullanıcının bilgisayarda yüklemeden yalnızca çevrimiçi modda çalıştırılabilir yerel olarak çalıştırın. Daha fazla bilgi için bkz: [ClickOnce dağıtım stratejisini seçme](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamaları kendi kendini güncelleştirme; Bunlar için kullanılabilir hale gelir ve güncelleştirilmiş dosyaları otomatik olarak değiştirme gibi daha yeni sürümleri kontrol edebilirsiniz. Geliştirici, güncelleştirme davranışını belirtebilirsiniz; bir ağ yöneticisi de denetleyebilirsiniz güncelleştirme stratejileri, örneğin, güncelleştirme zorunlu olarak işaretleme. Güncelleştirmeleri de yeniden önceki bir sürüme son kullanıcı tarafından veya bir yönetici tarafından alınabilir. Daha fazla bilgi için bkz: [ClickOnce güncelleştirme stratejisini seçme](../deployment/choosing-a-clickonce-update-strategy.md).  
  
 Çünkü [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamalar, yüklenmesini veya çalıştırılmasını yalıtılmış bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama varolan uygulamaları kesemez. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamaları kendi içinde bulunan; Her [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulaması için yüklenebilir ve bir güvenli kullanıcı, uygulama başına önbellek çalıştırılabilir. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamaları Internet veya Intranet güvenlik bölgeleri'nde çalıştırın. Gerekirse, uygulama yükseltilmiş güvenlik izinlerini isteyebilir. Daha fazla bilgi için bkz: [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md).  
  
## <a name="how-clickonce-security-works"></a>ClickOnce güvenliği nasıl çalışır  
 Çekirdek [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] güvenlik sertifikaları, kod erişim güvenliği ilkeleri ve ClickOnce güven istemi dayanır.  
  
### <a name="certificates"></a>Sertifikalar  
 Authenticode sertifikaları uygulamanın yayımcı özgünlüğünü doğrulamak için kullanılır. ClickOnce, uygulama dağıtımı için Authenticode kullanarak zararlı bir programın kurulu olan güvenilir bir kaynaktan geliyor yasal bir program olarak kendisi tanıtmasını önlemeye yardımcı olur. İsteğe bağlı olarak, sertifikalar, uygulamayı imzalamak için de kullanılabilir ve dağıtım bildirimlerini dosyaları ile oynanmadığını olduğunu kanıtlamak için. Daha fazla bilgi için bkz: [ClickOnce ve Authenticode](../deployment/clickonce-and-authenticode.md). Sertifikalar, güvenilen yayımcılar listesini sağlamak için istemci bilgisayarları yapılandırmak üzere de kullanılabilir. Uygulamanın güvenilir bir yayımcıdan geliyorsa, kullanıcı etkileşimi olmadan yüklenebilir. Daha fazla bilgi için bkz: [güvenilir uygulama dağıtımına genel bakış](../deployment/trusted-application-deployment-overview.md).  
  
### <a name="code-access-security"></a>Kod Erişimi Güvenliği  
 Kod erişimi güvenliği, kod korumalı kaynaklara sahip olan erişimini sınırlamanıza yardımcı olur. Çoğu durumda izinleri sınırlamak için Internet veya yerel Intranet bölgesinin seçebilirsiniz. Kullanım **güvenlik** sayfasındaki **ProjectDesigner** uygulama için uygun bölgeyi istemek için. Ayrıca uygulamalar için son kullanıcı deneyimi benzetmek için kısıtlı izinle ayıklayabilirsiniz. Daha fazla bilgi için bkz: [ClickOnce uygulamaları için kod erişimi güvenliği](../deployment/code-access-security-for-clickonce-applications.md).  
  
### <a name="clickonce-trust-prompt"></a>ClickOnce güven istemi  
 Uygulama bölgenin izin verdiğinden daha fazla izin isterse, son kullanıcı bir güven kararı istenecek. Son kullanıcı, Windows Forms uygulamaları, Windows Presentation Foundation uygulamaları, konsol uygulamaları, XAML tarayıcısı uygulamaları ve Office çözümleri gibi ClickOnce uygulamalarını çalıştırmak için güvenilir olup olmadığına karar verebilir. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce güven istemi davranışını yapılandırma](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md).  
  
## <a name="how-clickonce-deployment-works"></a>ClickOnce dağıtımı nasıl çalışır  
 Çekirdek [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım mimarisi iki XML bildirim dosyası üzerinde temel: bir uygulama bildirimi ve bir dağıtım bildirimi. Dosyaları ClickOnce uygulamalarını gelen yüklendiği, nasıl güncelleştirilir ve ne zaman güncelleştirileceğini tanımlamak için kullanılır.  
  
### <a name="publishing-clickonce-applications"></a>ClickOnce Uygulamalarını Yayımlama  
 Uygulama bildirimi uygulamanın kendisinden açıklar. Bu, derlemeleri, bağımlılıklar ve uygulama, gerekli izinler ve burada güncelleştirme bulunmayacaktır konumu oluşturan dosyaları içerir. Visual Studio veya bildirim oluşturma ve düzenleme aracı (Mage.exe) Yayımlama Sihirbazı kullanarak uygulama bildirimi uygulama geliştiricisi yazarlarına [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Daha fazla bilgi için bkz: [nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
 Dağıtım bildirimi uygulamanın nasıl dağıtılacağını açıklar. Bu, uygulama bildirimi konumu ve istemcilerin çalıştıracağı uygulamanın sürümünü içerir.  
  
### <a name="deploying-clickonce-applications"></a>ClickOnce uygulamaları dağıtma  
 Oluşturulduktan sonra dağıtım bildirimi dağıtım konumuna kopyalanır. Bu, bir Web sunucusu, ağ dosya paylaşımı veya CD gibi medya olabilir. Ayrıca uygulama bildirimi ve tüm uygulama dosyalarını dağıtım bildiriminde belirtilen bir dağıtım konuma kopyalanır. Bu dağıtım konumu ile aynı olabilir veya farklı bir konum olabilir. Kullanırken **Yayımlama Sihirbazı** Visual Studio'da kopyalama işlemleri otomatik olarak gerçekleştirilir.  
  
### <a name="installing-clickonce-applications"></a>ClickOnce uygulamalarını yükleme  
 Dağıtım konumuna dağıtıldıktan sonra son kullanıcıların indirin ve bir klasörde veya bir Web sayfasında dağıtım bildirim dosyasını temsil eden simgeyi tıklayarak uygulamayı yükleyin. Çoğu durumda, son kullanıcı yüklemeyi, hangi yükleme işlemi devam eder ve ek müdahalesi olmadan uygulamanın başlatılmasından sonra onaylamak için kullanıcı soran bir basit iletişim kutusu sunulur. Burada uygulama yükseltilmiş izinler veya uygulama tarafından güvenilen bir sertifika imzalanmamış olması durumunda gerektiriyor durumlarda, iletişim kutusu, ayrıca kullanıcıya yüklemenin devam edebilmesi için izni ister. ClickOnce yükler kullanıcı başına olmakla birlikte, yönetici ayrıcalıkları gerektiren önkoşullar varsa izin yükseltme gerekli olabilir. Yükseltilmiş izinler hakkında daha fazla bilgi için bkz: [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md).  
  
 ClickOnce uygulamaları güvenilir bir sertifika ile imzalanmış sessiz yükleyebilmek sertifikaları makine ya da kuruluş düzeyinde güvenilir olabilir. Güvenilir sertifikalar hakkında daha fazla bilgi için bkz: [güvenilir uygulama dağıtımına genel bakış](../deployment/trusted-application-deployment-overview.md).  
  
 Uygulama kullanıcının eklenebilir **Başlat** menü ve **Program Ekle veya Kaldır** grubu **Denetim Masası**. Diğer dağıtım teknolojileri farklı olarak, hiçbir şey eklenen **Program Files** klasör veya kayıt defteri ve yönetici hakları yok yükleme için gerekli  
  
> [!NOTE]
>  Uygulamanın eklenmesini önlemek mümkündür **Başlat** menü ve **Program Ekle veya Kaldır** grup, etkin bir Web uygulaması gibi davranır kolaylaştırarak. Daha fazla bilgi için bkz: [ClickOnce dağıtım stratejisini seçme](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
### <a name="updating-clickonce-applications"></a>ClickOnce uygulamaları güncelleştirme  
 Uygulama geliştiricilerinin uygulamanın güncelleştirilmiş bir sürümü oluşturduğunuzda, bunlar yeni bir uygulama bildirimi oluşturmak ve dosyaları bir dağıtım konumuna kopyalamak — genellikle eşdüzey klasörüne özgün uygulama dağıtım klasörü. Yönetici dağıtım bildirimini uygulamanın yeni sürümü konumunu gösterecek şekilde güncelleştirir.  
  
> [!NOTE]
>  **Yayımlama Sihirbazı** Visual Studio'da bu adımları gerçekleştirmek için kullanılabilir.  
  
 Dağıtım konumu yanı sıra dağıtım bildirimi burada uygulama için güncelleştirilmiş sürümleri denetler bir güncelleştirme konumu (bir Web sayfası veya ağ dosya paylaşımı) de içerir. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] **Yayımlama** özellikleri, zaman ve ne sıklıkta uygulama güncelleştirmeleri denetlemesi gerektiğini belirlemek için kullanılır. Güncelleştirme davranışı dağıtım bildiriminde belirtilebilir ya da kullanıcı seçenekleri yoluyla uygulamanın kullanıcı arabiriminde olarak sunulabilir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] API'leri. Ayrıca, **Yayımla** özellikleri işe zorunlu güncelleştirmeleri yapmak veya önceki bir sürüme geri almak için. Daha fazla bilgi için bkz: [ClickOnce güncelleştirme stratejisini seçme](../deployment/choosing-a-clickonce-update-strategy.md).  
  
### <a name="third-party-installers"></a>Üçüncü taraf yükleyicileri  
 Uygulamanızı birlikte üçüncü taraf bileşenleri yüklemek için ClickOnce Yükleyicinizle özelleştirebilirsiniz. Yeniden dağıtılabilir paketi (.exe veya .msi dosyası) sahip ve bir dilden bağımsız ürün bildirimi ve dile özgü paket bildirimi paketiyle açıklanmaktadır. Daha fazla bilgi için bkz: [önyükleyici paketleri oluşturma](../deployment/creating-bootstrapper-packages.md).  
  
## <a name="clickonce-tools"></a>ClickOnce Araçları  
 Aşağıdaki tabloda, oluşturmak, düzenlemek, oturum ve uygulama ve dağıtım bildirimlerini yeniden imzalamak için kullanabileceğiniz araçlar gösterir.  
  
|Aracı|Açıklama|  
|----------|-----------------|  
|[Güvenlik Sayfası, Proje Tasarımcısı](../ide/reference/security-page-project-designer.md)|Uygulama ve dağıtım bildirimlerini açar.|  
|[Yayın Sayfası, Proje Tasarımcısı](../ide/reference/publish-page-project-designer.md)|Oluşturur ve Visual Basic ve Visual C# uygulamaları için uygulama ve dağıtım bildirimlerini düzenler.|  
|[Mage.exe (Bildirim Oluşturma ve Düzenleme Aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)|Visual Basic, Visual C# ve Visual C++ uygulamaları için uygulama ve dağıtım bildirimlerini oluşturur.<br /><br /> İmzalar ve uygulama ve dağıtım bildirimlerini yeniden imzalar.<br /><br /> Toplu iş komut dosyaları ve komut isteminden çalıştırabilirsiniz.|  
|[MageUI.exe (Bildirim Oluşturma ve Düzenleme Aracı, Grafik İstemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)|Oluşturur ve uygulama ve dağıtım bildirimlerini düzenler.<br /><br /> İmzalar ve uygulama ve dağıtım bildirimlerini yeniden imzalar.|  
|[GenerateApplicationManifest Görevi](../msbuild/generateapplicationmanifest-task.md)|Uygulama bildirimi oluşturur.<br /><br /> MSBuild çalıştırabilirsiniz. Daha fazla bilgi için bkz: [MSBuild başvurusu](../msbuild/msbuild-reference.md).|  
|[GenerateDeploymentManifest Görevi](../msbuild/generatedeploymentmanifest-task.md)|Dağıtım bildirimi oluşturur.<br /><br /> MSBuild çalıştırabilirsiniz. Daha fazla bilgi için bkz: [MSBuild başvurusu](../msbuild/msbuild-reference.md).|  
|[SignFile Görevi](../msbuild/signfile-task.md)|Uygulama ve dağıtım bildirimlerini açar.<br /><br /> MSBuild çalıştırabilirsiniz. Daha fazla bilgi için bkz: [MSBuild başvurusu](../msbuild/msbuild-reference.md).|  
|<xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities>|Uygulama ve dağıtım bildirimlerini oluşturmak için kendi uygulamanızı geliştirin.|  
  
 Aşağıdaki tabloda bu tarayıcılarda ClickOnce uygulamalarını desteklemek için gerekli .NET Framework sürümünü gösterir.  
  
|Tarayıcı|.NET Framework sürümü|  
|-------------|----------------------------|  
|Internet Explorer|2.0, 3.0, 3.5, 3.5 SP1, 4|  
|Firefox|2.0 SP1, 3.5 SP1 4|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Vista'da ClickOnce dağıtımı](../deployment/clickonce-deployment-on-windows-vista.md)   
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [ClickOnce ile COM bileşenleri dağıtma](../deployment/deploying-com-components-with-clickonce.md)   
 [Komut satırından ClickOnce uygulamalarını yapılandırma](../deployment/building-clickonce-applications-from-the-command-line.md)   
 [System.Deployment.Application Kullanan ClickOnce Uygulamalarında Hata Ayıklama](../deployment/debugging-clickonce-applications-that-use-system-deployment-application.md)