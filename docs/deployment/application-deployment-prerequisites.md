---
title: Uygulama dağıtımının önkoşulları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, platform detection
- ClickOnce deployment, prerequisites
- ClickOnce deployment, dependencies
- prerequisites, ClickOnce
- dependencies, ClickOnce
ms.assetid: fc6e047e-ad94-44e8-8ff5-b6d1f4ca7735
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 5fdeb1d5e543216e0cbb9cab72ecd98001caff3c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="application-deployment-prerequisites"></a>Uygulama Dağıtımının Önkoşulları
Uygulamanızı yüklemek ve başarılı bir şekilde çalıştırılması sağlamak için önce uygulamanızın bağımlı olduğu tüm bileşenleri, hedef bilgisayarda zaten yüklü emin olmalısınız. Örneğin, çoğu uygulamayı kullanılarak oluşturulan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] üzerinde bir bağımlılığa sahip [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]; uygulama yüklenmeden önce ortak dil çalışma zamanı doğru sürümü hedef bilgisayarda mevcut olması gerekir.  
  
 Bu Önkoşullar seçebilirsiniz **Önkoşullar iletişim kutusu** ve .NET Framework ve diğer yeniden dağıtılabilir paketlerini, yüklemenin bir parçası olarak yükleyin. Bu yöntem olarak bilinen *önyükleme*. Ardından, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] olarak da bilinen Setup.exe adlı bir Windows yürütülebilir programı oluşturur bir *önyükleyici*. Önyükleyici, uygulamanız çalışmadan önce bu önkoşulları yüklemek için sorumludur. Bu önkoşulları seçme hakkında daha fazla bilgi için bkz: [Önkoşullar iletişim kutusu](../ide/reference/prerequisites-dialog-box.md).  
  
 Her bir önyükleyici paketi önkoşuldur. Önyükleyici paketi, dizinler ve önkoşul nasıl yükleneceğini açıklayan bildirim dosyaları içeren dosyaları grubudur. Uygulama önkoşulları listelenmeyen varsa **önkoşul iletişim kutusu**, özel önyükleyici paketleri oluşturma ve bunları Visual Studio'ya ekleyin. Önkoşullar seçip **Önkoşullar iletişim kutusu**. Daha fazla bilgi için bkz: [önyükleyici paketleri oluşturma](../deployment/creating-bootstrapper-packages.md).  
  
 Varsayılan olarak, önyükleme için ClickOnce dağıtımı etkindir. ClickOnce dağıtımı için oluşturulan önyükleyici imzalanır. Bir bileşen için önyüklemeyi devre dışı bırakabilir, ancak yalnızca bileşen doğru sürümü, tüm hedef bilgisayarlarda zaten yüklü olduğundan emin olduğunuzda yapmalısınız.  
  
## <a name="bootstrapping-and-clickonce-deployment"></a>Önyükleme ve ClickOnce dağıtımı  
 Bir istemci bilgisayarda, bir uygulamayı yüklemeden önce [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildiriminde belirtilen belirli gereksinimleri karşıladığından emin olmak için istemci inceleyeceksiniz. Bunlar aşağıdakileri içerir:  
  
-   En az bir derleme bağımlılığı uygulama bildiriminde belirtilen ortak dil çalışma zamanı sürümü gereklidir.  
  
-   Gereken en düşük sürüm uygulama tarafından gerekli Windows işletim sisteminin uygulama belirtildiği gibi bildirim kullanarak `<osVersionInfo>` öğesi. (Bkz [ \<bağımlılık > öğesi](../deployment/dependency-element-clickonce-application.md))  
  
-   En düşük sürüm tüm derlemelerin derleme bağımlılığı bildirimleri derleme bildiriminde belirtildiği gibi genel derleme önbelleğinde (GAC) önceden yüklenmiş gerekir.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] eksik Önkoşullar algılayabilir ve bir önyükleyici kullanarak önkoşullar yükleyebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulamasına Önkoşullar yükleme](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md).  
  
> [!NOTE]
>  Gibi araçları tarafından oluşturulan bildirimlerdeki değerleri değiştirmek için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve MageUI.exe uygulama bildirimini bir metin düzenleyicisinde düzenleyin ve uygulama ve dağıtım bildirimlerini yeniden imzalama vermeniz gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: yeniden imzalama uygulama ve dağıtım bildirimlerini](../deployment/how-to-re-sign-application-and-deployment-manifests.md).  
  
 Uygulamanızı dağıtmak için Visual Studio ve ClickOnce'ı kullanırsanız, varsayılan olarak seçili önyükleyici paketleri çözümdeki .NET Framework sürümünü bağlıdır. Ancak, hedef .NET Framework sürümünü değiştirirseniz, seçeneklerinde güncelleştirmeniz gerekir **Önkoşullar iletişim kutusu** el ile.  
  
|Hedef .NET Framework'ü|Seçili önyükleyici paketleri|  
|---------------------------|------------------------------------|  
|.NET Framework 4 İstemci Profili|.NET Framework 4 İstemci Profili<br /><br /> Windows Installer 3.1|  
|.NET Framework 4|.NET Framework 4<br /><br /> Windows Installer 3.1|  
  
 İle [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım, tarafından oluşturulan Publish.htm sayfasında [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Yayımlama Sihirbazı'nı ya da yalnızca uygulamayı yükleyen bir bağlantı noktaları veya uygulama ve önyükleme bileşenleri yükler bağlantı.  
  
 Visual Studio'da ClickOnce Yayımlama Sihirbazı'nı veya Yayımla Sayfası kullanarak önyükleyici oluşturursanız, Setup.exe otomatik olarak imzalanır. Ancak, önyükleyici imzalamak için müşterinizin sertifikasını kullanmak istiyorsanız, dosyayı daha sonra imzalayabilirsiniz.  
  
## <a name="bootstrapping-and-msbuild"></a>Önyükleme ve MSBuild  
 Kullanmıyorsanız, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ancak uygulamalarınızı komut satırında derleme, oluşturabileceğiniz [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Microsoft Build Engine (MSBuild) görevi kullanılarak, uygulama önyüklemesi. Daha fazla bilgi için bkz: [GenerateBootstrapper görevi](../msbuild/generatebootstrapper-task.md).  
  
 Önyükleme alternatif olarak, Microsoft Systems Management Server (SMS) gibi bir elektronik yazılım dağıtım sistemi kullanarak bileşenleri önceden dağıtabilirsiniz.  
  
## <a name="bootstrapper-setupexe-command-line-arguments"></a>Önyükleyici (Setup.exe) komut satırı bağımsız değişkenleri  
 Tarafından oluşturulan Setup.exe [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve MSBuild görevleri komut satırı bağımsız değişkenleri aşağıdaki küçük kümesini destekler. Bunlar dışında önyükleme uygulaması tarafından sağlanan bağımsız değişkenler için uygulama yükleyicisi iletilir.  
  
 Önyükleyici seçenekleri değiştirirseniz, imzasız önyükleyici değiştirmek ve önyükleyici dosya daha sonra oturum gerekir.  
  
|Komut satırı bağımsız değişkeni|Açıklama|  
|---------------------------|-----------------|  
|**-?, -h, - Yardım**|Yardım iletişim kutusunu görüntüler.|  
|**-url, - componentsurl**|Saklı URL'yi ve bu ayarlama bileşenleri URL'sini gösterir.|  
|**-url =** `location`|Burada Setup.exe arar URL'sini ayarlar [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama.|  
|**-componentsurl =** `location`|Burada Setup.exe bağımlılıklar için aşağıdaki gibi görünür URL'sini ayarlar [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].|  
|**-homesite =** `true`**&#124;** `false`|Zaman `true`, satıcının sitesindeki tercih edilen konumdan bağımlılıkları indirir. Bu geçersiz kılmaları **- componentsurl** ayarı. Zaman `false`, tarafından belirtilen URL'den bağımlılıkları indirir **- componentsurl**.|  
  
## <a name="operating-system-support"></a>İşletim sistemi desteği  
 Windows Server 2008 Server Core veya Windows Server 2008 R2 Server düşük bakım sunucu ortamı ile sınırlı işlevsellik sağlayan Core, Visual Studio önyükleyici desteklenmiyor. Örneğin, .NET Framework üzerinde tam bağımlı Visual Studio özellikleri çalıştırılamıyor Sunucu Çekirdeği yükleme seçeneği yalnızca .NET Framework 3.5 Server Core profilini destekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce dağıtım stratejisini seçme](../deployment/choosing-a-clickonce-deployment-strategy.md)   
 [ClickOnce Güvenliği ve Dağıtımı](../deployment/clickonce-security-and-deployment.md)