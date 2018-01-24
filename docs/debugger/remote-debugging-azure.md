---
title: "Uzaktan hata ayıklama, IIS ve Azure üzerinde ASP.NET Core | Microsoft Docs"
ms.custom: remotedebugging
ms.date: 08/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6c04b53-d1b9-4552-a8fd-3ed6f4902ce6
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- aspnet
- dotnetcore
- azure
ms.openlocfilehash: 22b7724a6eee2c31de1bf64f12a040e042972e96
ms.sourcegitcommit: 65f85389047c5a1938b6d5243ccba8d4f14362ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2018
---
# <a name="remote-debug-aspnet-core-on-iis-in-azure-in-visual-studio-2017"></a>Visual Studio 2017 Azure'da IIS'de ASP.NET çekirdeğinde uzaktan hata ayıklama

Bu kılavuz, ayarlama ve Visual Studio 2017 ASP.NET Core uygulama yapılandırma, Azure kullanılarak IIS'ye dağıtma ve Visual Studio uzaktan hata ayıklayıcı Ekle açıklanmaktadır.

Azure üzerinde uzaktan hata ayıklama için önerilen yol, senaryoya bağlıdır:

* Azure App Service'te ASP.NET Core hata ayıklamak için bkz: [anlık görüntü hata ayıklayıcı kullanarak hata ayıklama Azure uygulamaları](../debugger/debug-live-azure-applications.md). Bu önerilen bir yöntemdir.
* Azure App Service'te daha geleneksel hata ayıklama özelliklerini kullanarak ASP.NET Core hata ayıklamak için bu konudaki adımları takip edin (bölümüne bakın [uzaktan hata ayıklama Azure uygulama hizmeti](#remote_debug_azure_app_service)).

    Bu senaryoda, uygulamanızı Visual Studio'dan Azure dağıtmanız gerekir, ancak el ile yüklemek veya IIS ya da (Bu bileşenlerin noktalı çizgilerle gösterilir) uzaktan hata ayıklayıcı, aşağıdaki çizimde gösterildiği gibi yapılandırmak gerekmez.

    ![Uzaktan hata ayıklayıcı bileşenleri](../debugger/media/remote-debugger-azure-app-service.png "Remote_debugger_components")

* IIS üzerinde bir Azure VM hata ayıklamak için bu konudaki adımları takip edin (bölümüne bakın [uzaktan hata ayıklama Azure VM'de](#remote_debug_azure_vm)). Bu, özelleştirilmiş bir IIS yapılandırmasını kullanmanıza olanak sağlar, ancak Kurulum ve dağıtım adımlarını daha karmaşıktır.

    Bir Azure VM için uygulamanızı Visual Studio'dan Azure dağıtmanız gerekir ve ayrıca IIS rolünü ve uzaktan hata ayıklayıcı el ile yüklemek aşağıdaki çizimde gösterildiği gibi gerekir.

    ![Uzaktan hata ayıklayıcı bileşenleri](../debugger/media/remote-debugger-azure-vm.png "Remote_debugger_components")

* Azure Service Fabric ASP.NET Çekirdeğinde hata ayıklamak için bkz: [uzak Service Fabric uygulama hata ayıklama](/azure/service-fabric/service-fabric-debugging-your-application#debug-a-remote-service-fabric-application).

> [!WARNING]
> Bu öğreticide adımları tamamladıktan sonra oluşturduğunuz Azure kaynaklarını sildiğinizden emin olun. Bu şekilde, gereksiz ücretlerinin yansıtılmasını önleyebilirsiniz.


### <a name="requirements"></a>Gereksinimler

Bir proxy üzerinden bağlı iki bilgisayar arasında hata ayıklama desteklenmiyor. Bir yüksek gecikme veya çevirmeli Internet gibi düşük bant genişliği bağlantısı veya Internet üzerinden ülkelerde arasında hata ayıklama önerilmez ve başarısız olabilir veya edilemeyecek yavaş. Gereksinimlerinin tam listesi için bkz: [gereksinimleri](../debugger/remote-debugging.md#requirements_msvsmon).

## <a name="create-the-aspnet-core-application-on-the-visual-studio-2017-computer"></a>Visual Studio 2017 bilgisayarda ASP.NET Core uygulaması oluşturma 

1. Yeni bir ASP.NET Core uygulaması oluşturun. (Seçin **Dosya > Yeni > Proje**seçeneğini belirleyip **Visual C# > Web > ASP.NET çekirdek Web uygulaması**).

    İçinde **ASP.NET Core** şablonları bölümünde, select **Web uygulaması**.

2. Olduğundan emin olun **ASP.NET Core 2.0** seçildiğinde, **Docker desteğini etkinleştir** olan **değil** seçili ve **kimlik doğrulaması** ayarlanır **Kimlik doğrulaması yok**.

3. Proje adı **MyASPApp** tıklatıp **Tamam** yeni bir çözüm oluşturmak için.

4. About.cshtml.cs dosyasını açın ve bir kesme noktası kümesinde `OnGet` yöntemi (eski şablonlarında, bunun yerine HomeController.cs açın ve kesme kümesinde `About()` yöntemi).

## <a name="remote_debug_azure_app_service"></a>Uzaktan hata ayıklama ASP.NET Core üzerinde bir Azure uygulama hizmeti

Hızlı bir şekilde Visual Studio'dan yayımlamak ve IIS tamamen sağlanan bir örneğine uygulamanızın hatalarını ayıklama. Ancak, IIS yapılandırmasını önceden ve onu özelleştiremezsiniz. Daha ayrıntılı yönergeler için bkz: [ASP.NET Core web uygulama dağıtmak için Visual Studio kullanarak Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs). (IIS özelleştirme yeteneği ihtiyacınız varsa, hata ayıklama deneyin bir [Azure VM](#BKMK_azure_vm).) 

#### <a name="to-deploy-the-app-and-remote-debug-using-server-explorer"></a>Sunucu Gezgini kullanarak uzaktan hata ayıklama ve uygulama dağıtmak için

1. Visual Studio proje düğümüne sağ tıklayın ve seçin **Yayımla**.

2. Seçin **Microsoft Azure App Service** gelen **Yayımla** iletişim kutusunda **Yeni Oluştur**ve yayımlamak için istemleri izleyin.

    Ayrıntılı yönergeler için bkz: [ASP.NET Core web uygulama dağıtmak için Visual Studio kullanarak Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs).

3. Açık **Sunucu Gezgini** (**Görünüm** > **Sunucu Gezgini**), App Service örneğinde sağ tıklatın ve seçin **hata ayıklayıcıekleme**.

4. Çalışan ASP.NET uygulamasındaki bağlantısını **hakkında** sayfası.

    Visual Studio'da kesme noktası isabet.

    İşte bu kadar! Bu konudaki adımları geri kalanını uygulayın Azure VM temelinde uzaktan hata ayıklama için.

## <a name="remote_debug_azure_vm"></a>Uzaktan hata ayıklama ASP.NET Core Azure VM'de

Bir Azure VM için Windows Server oluşturabilir ve ardından yükleyin ve IIS ve diğer gerekli yazılımı bileşenleri yapılandırabilirsiniz. Bu, bir Azure App Service'e dağıtma değerinden daha uzun sürer ve bu öğreticinin geri kalan adımları izleyin gerektirir.

İlk olarak, açıklanan tüm adımları [yükleme ve çalıştırma IIS](/azure/virtual-machines/virtual-machines-windows-hero-role).

Ayrıca ağ güvenlik Grubu'na 80 numaralı bağlantı noktasını açtığınızda, bağlantı noktası 4022 için uzaktan hata ayıklayıcı açın. Böylece, daha sonra açmak zorunda kalmazsınız.

### <a name="update-browser-security-settings-on-windows-server"></a>Windows Server'da tarayıcı güvenlik ayarlarını güncelleştirme

Tarayıcı güvenlik ayarlarınızı bağlı olarak, bu öğreticide anlatılan yazılım kolayca indirebilirsiniz şekilde tarayıcınıza aşağıdaki Güvenilen siteler eklemek için zamandan tasarruf. Bu sitelere erişimi gerekebilir:

- microsoft.com
- go.microsoft.com
- download.microsoft.com
- visualstudio.com

Internet Explorer kullanıyorsanız, Güvenilen siteler giderek ekleyebileceğiniz **Internet Seçenekleri > Güvenlik > Güvenilen siteler > siteleri**. Bu adımlar, tarayıcılar için farklıdır. (Uzaktan hata ayıklayıcı daha eski bir sürümü my.visualstudio.com karşıdan yüklemeniz gerekiyorsa, bazı ek Güvenilen siteler oturum açmak için gereklidir.)

Yazılım yüklediğinizde, çeşitli web sitesi komut dosyaları ve kaynakları yükleme izni vermek için istekleri alabilirsiniz. Çoğu durumda, bu ek kaynakları yazılımı yüklemeniz gerekmez.

### <a name="install-aspnet-core-on-windows-server"></a>ASP.NET Core Windows Server yükleme

1. Yükleme [.NET Core Windows Server barındırma](https://aka.ms/dotnetcore-2-windowshosting) barındıran sistemde paket. Paket .NET çekirdeği çalışma zamanı, .NET Core kitaplığı ve ASP.NET Core Modülü'nü yükleyecek. Daha fazla ayrıntılı yönergeler için bkz: [IIS yayımlama](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration).

    > [!NOTE]
    > Sistem Internet bağlantısı yoksa, edinme ve yükleme  *[Microsoft Visual C++ 2015 Redistributable](https://www.microsoft.com/download/details.aspx?id=53840)*  .NET Core Windows Server barındırma paketini yüklemeden önce.

3. Sistemi yeniden başlatın (veya yürütme **net stop edildi /y** arkasından **net start w3svc** sistem yolu değişiklik seçmek için bir komut isteminden).

### <a name="BKMK_install_webdeploy"></a>(İsteğe bağlı) Windows Server'da 3.6 yükleme Web dağıtımı

[!INCLUDE [remote-debugger-install-web-deploy](../debugger/includes/remote-debugger-install-web-deploy.md)]

### <a name="BKMK_deploy_asp_net"></a>Windows Server bilgisayarında ASP.NET Web sitesi yapılandırması

1. Açık **Internet Information Services (IIS) Yöneticisi'ni** ve Git **siteleri**.

2. Sağ **varsayılan Web sitesi** düğümü ve select **uygulama Ekle**.

3. Ayarlama **diğer** alanı **MyASPApp** ve uygulama havuzu alana **yönetilen kod yok**. Ayarlama **fiziksel yolu** için **C:\Publish** (burada daha sonra dağıtacağınız ASP.NET projesi).

4. IIS Yöneticisi'nde site seçiliyken, seçin **izinleri Düzenle**ve bu IUSR, IIS_IUSRS ya da okuma ve yürütme hakları olan yetkili bir kullanıcının uygulama havuzu için yapılandırılan kullanıcı emin olun.

    Bu kullanıcılara erişim birini görmüyorsanız, okuma ve yürütme hakları olan bir kullanıcı olarak IUSR eklemek için adımları gidin.

### <a name="bkmk_webdeploy"></a>(İsteğe bağlı) Yayımlama ve Web dağıtımı Visual Studio'dan kullanarak uygulamayı dağıtma

Web Platformu Yükleyicisi'ni kullanarak Web dağıtımı yüklediyseniz, Visual Studio uygulamasından doğrudan dağıtabilirsiniz.

1. Yükseltilmiş ayrıcalıklarla Visual Studio'yu başlatın ve projeyi yeniden açın.

    Bu Web Dağıtımı'nı kullanarak uygulamanızı dağıtmak için gerekli.

2. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Yayımla**.

3. İçin **yayımlama hedefi seçin**seçin **Microsoft Azure sanal makinesi** tıklatıp **Yayımla**.

    ![RemoteDBG_Publish_IISl](../debugger/media/remotedbg_azure_vm_profile.png "RemoteDBG_Publish_IIS")

4. İletişim kutusunda, daha önce oluşturduğunuz Azure VM'yi seçin.

4. Azure VM ve IIS ayarlarınızı düzeltme yapılandırma parametrelerini girin.

    ![RemoteDBG_Publish_WebDeployl](../debugger/media/remotedbg_iis_webdeploy_config.png "RemoteDBG_Publish_WebDeploy")

    Bir ana bilgisayar adı olarak doğrulamak çalıştığınızda çözmezse sonraki bölümlerinde bulunan adımları **Server** metin kutusunda, IP adresi deneyin. İçinde 80 numaralı bağlantı noktasını kullandığınızdan emin olun **Server** metin kutusuna ve bağlantı noktası 80 Güvenlik Duvarı'nda açık olduğundan emin olun.

6. Tıklatın **sonraki**, seçin bir **hata ayıklama** yapılandırması ve seçin **hedefteki ek dosyaları Kaldır** altında **yayımlama dosyası** Seçenekler.

5. Tıklatın **önceki**ve ardından **doğrulama**. Bağlantı Kur doğrulanırsa yayımlamayı deneyebilirsiniz.

6. Tıklatın **Yayımla** uygulamayı yayımlamak için.

    Çıktı sekmesi yayımlama başarılı olur ve uygulama tarayıcınızın açılır gösterir.

    Web dağıtımı söz bir hata alırsanız, Web dağıtımı yükleme adımlarını yeniden denetle ve emin olun [doğru bağlantı noktaları açık](#bkmk_openports) sunucudaki.

    Uygulama başarıyla dağıtır ancak düzgün çalışmıyorsa, IIS ve Visual Studio projenizi ASP.NET aynı sürümünü kullanarak yeniden denetleyin. Diğer bir deyişle sorunda değil, IIS yapılandırmasını veya Web sitesi yapılandırması ile ilgili bir sorun olabilir. Windows Server için daha özel hata iletileri IIS Web sitesini açın ve önceki adımları yeniden denetleyin.

### <a name="optional-publish-and-deploy-the-app-by-publishing-to-a-local-folder-from-visual-studio"></a>(İsteğe bağlı) Yayımlama ve uygulama yayımlayarak bir yerel klasöre Visual Studio'dan dağıtma

Web dağıtımı kullanmıyorsanız, yayımlama ve dosya sistemi veya diğer araçları kullanarak uygulamayı dağıtın. Dosya sistemi kullanan bir paket oluşturun ve ardından paketi el ile dağıtmak veya PowerShell, RoboCopy veya XCopy gibi diğer araçları kullanın. Bu bölümde, Web dağıtımı kullanmıyorsanız paket el ile Kopyalamakta olduğunuz varsayılmıştır.

[!INCLUDE [remote-debugger-deploy-app-local](../debugger/includes/remote-debugger-deploy-app-local.md)]

### <a name="BKMK_msvsmon"></a>İndirin ve Windows Server'da uzak Araçları'nı yükleme

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
### <a name="BKMK_setup"></a>Windows Server'da uzaktan hata ayıklayıcı ayarlama

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> Gerektiğinde ek kullanıcılar için izinler eklemek için kimlik doğrulaması modunu değiştirme veya bağlantı noktası numarası uzaktan hata ayıklayıcı için bkz: [uzaktan hata ayıklayıcı yapılandırma](../debugger/remote-debugging.md#configure_msvsmon).

### <a name="BKMK_attach"></a>Visual Studio bilgisayardan ASP.NET uygulamasına ekleme

1. Visual Studio bilgisayarda açın **MyASPApp** çözümü.
2. Visual Studio'da sırasıyla **hata ayıklama > ekleme işlemi için** (Ctrl + Alt + P).

    > [!TIP]
    > Visual Studio 2017 ', daha önce iliştirilmiş kullanarak aynı işlemi yeniden ekleyebilirsiniz **hata ayıklama > işlem için yeniden bağlayın...** (Shift+Alt+P). 

3. Niteleyici alan kümesi'ne  **\<uzak bilgisayar adı >: 4022**.
4. Tıklatın **yenileme**.
    Bazı işlemler görünür görmelisiniz **kullanılabilir işlemler** penceresi.

    Herhangi bir işlem görmüyorsanız (bağlantı noktası gereklidir) uzak bilgisayar adı yerine IP adresini kullanarak deneyin. Kullanabileceğiniz `ipconfig` IPv4 adresini almak için komut satırında.

    Kullanmak istiyorsanız, **Bul** düğmesini gerekebilir [açmak UDP bağlantı noktası 3702](#bkmk_openports) sunucusunda.

5. Denetleme **işlemleri tüm kullanıcıları göster**.
6. Hızla bulmak için bir işlem adının ilk harfi yazın **dotnet.exe** (için ASP.NET Core).
    >Not: bir ASP.NET Core uygulaması için önceki işlem adı dnx.exe oluştu.

    ![RemoteDBG_AttachToProcess](../debugger/media/remotedbg_attachtoprocess_aspnetcore.png "RemoteDBG_AttachToProcess")

7. Tıklatın **Attach**.

8. Uzak bilgisayarın Web sitesini açın. Bir tarayıcıda Git **http://\<uzak bilgisayar adı >**.
    
    ASP.NET web sayfası görmeniz gerekir.
9. Çalışan ASP.NET uygulamasındaki bağlantısını **hakkında** sayfası.

    Visual Studio'da kesme noktası isabet.

### <a name="bkmk_openports"></a>Sorun giderme: Windows Server üzerinde gerekli bağlantı noktalarını açın

Çoğu kurulumları ASP.NET ve uzaktan hata ayıklayıcı yüklemesi tarafından gerekli bağlantı noktaları açıldı. Ancak, dağıtım sorunlarını giderme ve uygulamanın bir güvenlik duvarının arkasında barındırılan, doğru bağlantı noktalarının açık olduğunu doğrulayın gerekebilir.

Bir Azure VM aracılığıyla bağlantı noktalarını açmanız gerekir [ağ güvenlik grubu](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80). 

Gerekli bağlantı noktaları:

- 80 - IIS için gerekli
- 4022 - gerekli Visual Studio 2017 uzaktan hata ayıklama için (bkz [uzaktan hata ayıklayıcı bağlantı noktası atamaları](../debugger/remote-debugger-port-assignments.md) daha fazla bilgi için).
- 3702 - UDP bağlantı noktası (isteğe bağlı) bulma olanak tanır **Bul** düğmesini Visual Studio uzaktan hata ayıklayıcı eklerken.

Ayrıca, bu bağlantı noktaları ASP.NET yükleme tarafından zaten açılması gerekir:
- 8172 - (Visual Studio uygulama dağıtmak Web dağıtımı için gerekli isteğe bağlı)

