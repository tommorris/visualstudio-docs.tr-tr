---
title: Uygulama dağıtımının önkoşulları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7dbf2b552731b7bedb50ff71bc2fb8b64e8a1b10
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36233392"
---
# <a name="application-deployment-prerequisites"></a>Uygulama Dağıtımının Önkoşulları

Uygulamanızın yüklemek ve başarılı bir şekilde çalıştırılması için ilk uygulamanızı hedef bilgisayara bağımlı olduğu tüm bileşenlerini yükleyin. Örneğin, çoğu uygulamayı kullanılarak oluşturulan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] üzerinde bir bağımlılığa sahip [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Bu durumda, ortak dil çalışma zamanı doğru sürümde uygulama yüklenmeden önce hedef bilgisayarda mevcut olmalıdır.  
  
 Bu Önkoşullar seçebilirsiniz **Önkoşullar iletişim kutusu** ve .NET Framework ve diğer yeniden dağıtılabilir paketlerini, yüklemenin bir parçası olarak yükleyin. Bu yöntem olarak bilinen *önyükleme*. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Setup.exe, olarak da bilinen adlı bir Windows yürütülebilir programın oluşturduğu bir *önyükleyici*. Önyükleyici, uygulamanız çalışmadan önce bu önkoşulları yüklemek için sorumludur. Bu önkoşulları seçme hakkında daha fazla bilgi için bkz: [Önkoşullar iletişim kutusu](../ide/reference/prerequisites-dialog-box.md).  
  
 Her bir önyükleyici paketi önkoşuldur. Önyükleyici paketi dizin ve dosyaların önkoşulları nasıl yükleneceğini açıklayan bildirim dosyalarını içeren bir gruptur. Uygulama önkoşulları listelenmeyen varsa **önkoşul iletişim kutusu**, özel önyükleyici paketleri oluşturma ve bunları Visual Studio'ya ekleyin. Önkoşullar seçip **Önkoşullar iletişim kutusu**. Daha fazla bilgi için bkz: [önyükleyici paketleri oluşturma](../deployment/creating-bootstrapper-packages.md).  
  
 Varsayılan olarak, önyükleme için ClickOnce dağıtımı etkindir. ClickOnce dağıtımı için oluşturulan önyükleyici imzalanır. Bir bileşen için önyüklemeyi devre dışı bırakabilir, ancak yalnızca, eminseniz bileşen doğru sürümü zaten tüm hedef bilgisayarlarda yüklü.  
  
## <a name="bootstrapping-and-clickonce-deployment"></a>Önyükleme ve ClickOnce dağıtımı  
 Bir istemci bilgisayarda, bir uygulamayı yüklemeden önce [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildiriminde belirtilen gereksinimleri karşıladığından emin olmak için istemci inceler. Bu gereksinimleri aşağıdakileri içerir:  
  
-   En az bir derleme bağımlılığı uygulama bildiriminde belirtilen ortak dil çalışma zamanı sürümü gereklidir.  
  
-   Gereken en düşük sürüm uygulama tarafından gerekli Windows işletim sisteminin uygulama belirtildiği gibi bildirim kullanarak `<osVersionInfo>` öğesi. (Bkz [ \<bağımlılık > öğesi](../deployment/dependency-element-clickonce-application.md).)  
  
-   En düşük sürüm tüm derlemelerin derleme bağımlılığı bildirimleri derleme bildiriminde belirtildiği gibi genel derleme önbelleğinde (GAC) önceden yüklenmiş gerekir.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] eksik Önkoşullar algılayabilir ve bir önyükleyici kullanarak önkoşullar yükleyebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulamasıyla Önkoşulları Yükleme](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md).  
  
> [!NOTE]
>  Gibi araçları tarafından oluşturulan bildirimlerdeki değerleri değiştirmek için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve MageUI.exe uygulama bildirimini bir metin düzenleyicisinde düzenleyin ve uygulama ve dağıtım bildirimlerini yeniden imzalama vermeniz gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: yeniden, uygulama ve dağıtım bildirimlerini imzalama](../deployment/how-to-re-sign-application-and-deployment-manifests.md).  
  
 Uygulamanızı dağıtmak için Visual Studio ve ClickOnce'ı kullanırsanız, varsayılan olarak seçili önyükleyici paketleri çözümdeki .NET Framework sürümünü bağlıdır. Ancak, hedef .NET Framework sürümünü değiştirirseniz, seçeneklerinde güncelleştirmeniz gerekir **Önkoşullar iletişim kutusu** el ile.  
  
|Hedef .NET Framework'ü|Seçili önyükleyici paketleri|  
|---------------------------|------------------------------------|  
|.NET Framework 4 İstemci Profili|.NET Framework 4 İstemci Profili<br /><br /> Windows Installer 3.1|  
|.NET Framework 4|.NET Framework 4<br /><br /> Windows Installer 3.1|  
  
 İle [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım, tarafından oluşturulan Publish.htm sayfasında [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Yayımlama Sihirbazı'nı ya da yalnızca uygulamayı yükleyen bir bağlantı noktaları veya uygulama ve önyükleme bileşenleri yükler bağlantı.  
  
 Visual Studio'da ClickOnce Yayımlama Sihirbazı'nı veya Yayımla Sayfası kullanarak önyükleyici oluşturursanız, Setup.exe otomatik olarak imzalanır. Ancak, önyükleyici imzalamak için müşterinizin sertifikasını kullanmak istiyorsanız, dosyayı daha sonra imzalayabilirsiniz.  
  
## <a name="bootstrapping-and-msbuild"></a>Önyükleme ve MSBuild  
 Kullanmıyorsanız, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ancak bunun yerine uygulamalarınızın komut satırında derleme, oluşturabileceğiniz [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Microsoft Build Engine (MSBuild) görevi kullanılarak, uygulama önyüklemesi. Daha fazla bilgi için bkz: [GenerateBootstrapper görevi](../msbuild/generatebootstrapper-task.md).  
  
 Önyükleme alternatif olarak, Microsoft Systems Management Server (SMS) gibi bir elektronik yazılım dağıtım sistemi kullanarak bileşenleri önceden dağıtabilirsiniz.  
  
## <a name="bootstrapper-setupexe-command-line-arguments"></a>Önyükleyici (Setup.exe) komut satırı bağımsız değişkenleri  
 Tarafından oluşturulan Setup.exe [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve MSBuild görevleri komut satırı bağımsız değişkenleri aşağıdaki kümesini destekler. Başka bir bağımsız değişken uygulama yükleyicisi iletilir.  
  
 Önyükleyici seçenekleri değiştirirseniz, imzasız önyükleyici değiştirmek ve önyükleyici dosya daha sonra oturum açın.  
  
|Komut satırı bağımsız değişkeni|Açıklama|  
|---------------------------|-----------------|  
|**-?, -h, - Yardım**|Yardım iletişim kutusunu görüntüler.|  
|**-url, - componentsurl**|Saklı URL'yi ve bu ayarlama bileşenleri URL'sini gösterir.|  
|**-url =** `location`|Burada Setup.exe arar URL'sini ayarlar [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama.|  
|**-componentsurl =** `location`|Burada Setup.exe bağımlılıklar için aşağıdaki gibi görünür URL'sini ayarlar [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].|  
|**-homesite =** `true`**&#124;** `false`|Zaman `true`, satıcının sitesindeki tercih edilen konumdan bağımlılıkları indirir. Bu geçersiz kılmaları **- componentsurl** ayarı. Zaman `false`, tarafından belirtilen URL'den bağımlılıkları indirir **- componentsurl**.|  
  
## <a name="operating-system-support"></a>İşletim sistemi desteği  
 Bunlar düşük bakım sunucu ortamı ile sınırlı işlevsellik sağlayan olarak Visual Studio önyükleyici Windows Server 2008 Server Core veya Windows Server 2008 R2 Server Core üzerinde desteklenmiyor. Örneğin, Sunucu Çekirdeği yükleme seçeneği, yalnızca tam .NET Framework bağımlı Visual Studio özellikleri çalıştıramazsınız .NET Framework 3.5 Server Core profilini destekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce dağıtım stratejisini seçin](../deployment/choosing-a-clickonce-deployment-strategy.md)   
 [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md)