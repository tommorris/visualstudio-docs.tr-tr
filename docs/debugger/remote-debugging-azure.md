---
title: Uzaktan hata ayıklama, IIS ve Azure üzerinde ASP.NET Core | Microsoft Docs
ms.custom: remotedebugging
ms.date: 05/21/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: a6c04b53-d1b9-4552-a8fd-3ed6f4902ce6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
- dotnetcore
- azure
ms.openlocfilehash: cc889accc116fb2115ae56155a190ed6ea2d3fc0
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37058447"
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

## <a name="remote_debug_azure_app_service"></a> Uzaktan hata ayıklama ASP.NET Core üzerinde bir Azure uygulama hizmeti

Hızlı bir şekilde Visual Studio'dan yayımlamak ve IIS tamamen sağlanan bir örneğine uygulamanızın hatalarını ayıklama. Ancak, IIS yapılandırmasını önceden ve onu özelleştiremezsiniz. Daha ayrıntılı yönergeler için bkz: [ASP.NET Core web uygulama dağıtmak için Visual Studio kullanarak Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs). (IIS özelleştirme yeteneği ihtiyacınız varsa, hata ayıklama deneyin bir [Azure VM](#remote_debug_azure_vm).) 

#### <a name="to-deploy-the-app-and-remote-debug-using-server-explorer"></a>Sunucu Gezgini kullanarak uzaktan hata ayıklama ve uygulama dağıtmak için

1. Visual Studio proje düğümüne sağ tıklayın ve seçin **Yayımla**.

    Tüm yayımlama profillerini daha önce yapılandırdıysanız **Yayımla** bölmesinde görünür. Tıklatın **yeni bir profil**.

1. Seçin **Azure App Service** gelen **Yayımla** iletişim kutusunda **Yeni Oluştur**ve yayımlamak için istemleri izleyin.

    Ayrıntılı yönergeler için bkz: [ASP.NET Core web uygulama dağıtmak için Visual Studio kullanarak Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs).

    ![Azure App Service’e yayımlama](../debugger/media/remotedbg_azure_app_service_profile.png)

1. Açık **Sunucu Gezgini** (**Görünüm** > **Sunucu Gezgini**), App Service örneğinde sağ tıklatın ve seçin **hata ayıklayıcıekleme**.

1. Çalışan ASP.NET uygulamasındaki bağlantısını **hakkında** sayfası.

    Visual Studio'da kesme noktası isabet.

    İşte bu kadar! Bu konudaki adımları geri kalanını uygulayın Azure VM temelinde uzaktan hata ayıklama için.

## <a name="remote_debug_azure_vm"></a> Uzaktan hata ayıklama ASP.NET Core Azure VM'de

Bir Azure VM için Windows Server oluşturabilir ve ardından yükleyin ve IIS ve diğer gerekli yazılımı bileşenleri yapılandırabilirsiniz. Bu, bir Azure App Service'e dağıtma değerinden daha uzun sürer ve bu öğreticinin geri kalan adımları izleyin gerektirir.

İlk olarak, açıklanan tüm adımları [yükleme ve çalıştırma IIS](/azure/virtual-machines/windows/quick-create-portal).

Ayrıca ağ güvenlik Grubu'na 80 numaralı bağlantı noktasını açtığınızda, bağlantı noktası 4022 için uzaktan hata ayıklayıcı açın. Böylece, daha sonra açmak zorunda kalmazsınız.

### <a name="app-already-running-in-iis-on-the-azure-vm"></a>Zaten Azure VM'de IIS içinde çalışan uygulama?

Bu makale Windows Server IIS temel yapılandırması ayarlama ve Visual Studio uygulama dağıtma adımları içerir. Bu adımları sunucu gerekli bileşenleri yüklü, uygulamanın doğru çalıştırabilir ve uzaktan hata ayıklama için hazır olduğundan emin olmak için dahil edilmiştir.

* Uygulamanız IIS çalıştıran ve yalnızca istiyorsanız uzaktan hata ayıklayıcı karşıdan yüklemek ve hata ayıklamayı başlatma, Git [indirin ve Windows Server'da uzak Araçları'nı yükleme](#BKMK_msvsmon).

* Emin olmak için Yardım istiyorsanız, uygulamanızın, dağıtılan, ayarlanır ve doğru ayıklanabilmesi, IIS çalıştıran, bu konudaki tüm adımları izleyin.

### <a name="update-browser-security-settings-on-windows-server"></a>Windows Server'da tarayıcı güvenlik ayarlarını güncelleştirme

Ardından (varsayılan olarak etkindir) Internet Explorer Artırılmış Güvenlik Yapılandırması etkinse, bazı etki alanlarına, bazı web sunucusu bileşenlerini yükleme sağlamak için güvenilir siteler olarak eklemeniz gerekebilir. Güvenilen siteler giderek eklemek **Internet Seçenekleri > Güvenlik > Güvenilen siteler > siteleri**. Şu etki alanlarına ekleyin.

- Microsoft.com
- go.microsoft.com
- download.microsoft.com
- IIS.NET

Yazılım yüklediğinizde, çeşitli web sitesi komut dosyaları ve kaynakları yükleme izni vermek için istekleri alabilirsiniz. Bu kaynakların bazıları gerekli değildir ancak işlemini basitleştirmek için tıklatın **Ekle** istendiğinde.

### <a name="install-aspnet-core-on-windows-server"></a>ASP.NET Core Windows Server yükleme

1. Yükleme [.NET Core Windows Server barındırma](https://aka.ms/dotnetcore-2-windowshosting) barındıran sistemde paket. Paket .NET çekirdeği çalışma zamanı, .NET Core kitaplığı ve ASP.NET Core Modülü'nü yükleyecek. Daha fazla ayrıntılı yönergeler için bkz: [IIS yayımlama](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration).

    > [!NOTE]
    > Sistem Internet bağlantısı yoksa, edinme ve yükleme *[Microsoft Visual C++ 2015 Redistributable](https://www.microsoft.com/download/details.aspx?id=53840)* .NET Core Windows Server barındırma paketini yüklemeden önce.

3. Sistemi yeniden başlatın (veya yürütme **net stop edildi /y** arkasından **net start w3svc** sistem yolu değişiklik seçmek için bir komut isteminden).

## <a name="choose-a-deployment-option"></a>Bir dağıtım seçeneği seçin

IIS uygulama dağıtmak için yardıma gereksinim duyarsanız, bu seçenekleri göz önünde bulundurun:

* IIS'de bir yayımlama ayarları dosyası oluşturarak ve Visual Studio ayarları içeri aktarma dağıtın. Bazı senaryolarda, uygulamanızı dağıtmak için hızlı bir yolu budur. Yayımlama ayarları dosyası oluşturduğunuzda, izinler IIS'de otomatik olarak ayarlanır.

* Yerel bir klasöre yayımlama ve çıktı tarafından tercih edilen bir yöntem IIS üzerinde hazırlanmış uygulama klasöre kopyalama dağıtın.

## <a name="optional-deploy-using-a-publish-settings-file"></a>(İsteğe bağlı) Yayımlama ayarları dosyası kullanarak dağıtın

Bu seçeneği kullanabilirsiniz yayımlama ayarları dosyası oluşturun ve Visual Studio'ya içeri aktarma.

> [!NOTE]
> Bu dağıtım yöntemi, Web dağıtımı kullanır. Web dağıtımı el ile Visual Studio ayarları içeri aktarma yerine yapılandırmak istiyorsanız, barındırma sunucuları için Web dağıtımı 3.6 Web dağıtımı 3.6 yerine yükleyebilirsiniz. Ancak, Web dağıtımı el ile yapılandırırsanız, sunucudaki bir uygulama klasörü izinleri ve doğru değerlerin ile yapılandırılmış olduğundan emin olun gerekecektir (bkz [yapılandırma ASP.NET Web sitesi](#BKMK_deploy_asp_net)).

### <a name="install-and-configure-web-deploy-for-hosting-servers-on-windows-server"></a>Yükleme ve Windows Server üzerinde barındırma sunucuları için Web dağıtımı yapılandırma

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/install-web-deploy-with-hosting-server.md)]

### <a name="create-the-publish-settings-file-in-iis-on-windows-server"></a>Windows Server'da IIS'de yayımlama ayarları dosyası oluşturma

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/create-publish-settings-iis.md)]

### <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Visual Studio'da yayımlama ayarlarını içeri aktarın ve dağıtın

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/import-publish-settings-vs.md)]

Uygulama başarıyla dağıtıldıktan sonra otomatik olarak başlamanız gerekir. Uygulama Visual Studio'dan başlamazsa, IIS'de uygulamayı başlatın. ASP.NET Core için uygulama havuzu için alan emin olmanız gerekir. **DefaultAppPool** ayarlanır **yönetilen kod yok**.

1. İçinde **ayarları** iletişim kutusu, tıklayarak hata ayıklamayı etkinleştir **sonraki**, seçin bir **hata ayıklama** yapılandırma ve ardından **ek dosyaları Kaldır Hedef** altında **yayımlama dosyası** seçenekleri.

    > [!NOTE]
    > Bir yayın yapılandırma seçerseniz, hata ayıklamasını devre dışı *web.config* yayımladığınızda, dosya.

1. Tıklatın **kaydetmek** ve uygulamayı yeniden yayımlayın.

## <a name="optional-deploy-by-publishing-to-a-local-folder"></a>(İsteğe bağlı) Yerel bir klasöre yayımlama tarafından dağıtma

Powershell, RoboCopy, kullanarak IIS uygulama kopyalamak istediğiniz veya dosyaları el ile kopyalamak istiyorsanız uygulamanızı dağıtmak için bu seçeneği kullanın.

### <a name="BKMK_deploy_asp_net"></a> Windows Server bilgisayarında ASP.NET Web sitesi yapılandırması

İçeri aktarmakta olduğunuz yayımlama ayarları, bu bölümü atlayabilirsiniz.

1. Açık **Internet Information Services (IIS) Yöneticisi'ni** ve Git **siteleri**.

2. Sağ **varsayılan Web sitesi** düğümü ve select **uygulama Ekle**.

3. Ayarlama **diğer** alanı **MyASPApp** ve uygulama havuzu alana **yönetilen kod yok**. Ayarlama **fiziksel yolu** için **C:\Publish** (burada daha sonra dağıtacağınız ASP.NET projesi).

4. IIS Yöneticisi'nde site seçiliyken, seçin **izinleri Düzenle**ve bu IUSR, IIS_IUSRS ya da okuma ve yürütme hakları olan yetkili bir kullanıcının uygulama havuzu için yapılandırılan kullanıcı emin olun.

    Bu kullanıcılara erişim birini görmüyorsanız, okuma ve yürütme hakları olan bir kullanıcı olarak IUSR eklemek için adımları gidin.

### <a name="optional-publish-and-deploy-the-app-by-publishing-to-a-local-folder-from-visual-studio"></a>(İsteğe bağlı) Yayımlama ve uygulama yayımlayarak bir yerel klasöre Visual Studio'dan dağıtma

Web dağıtımı kullanmıyorsanız, yayımlama ve dosya sistemi veya diğer araçları kullanarak uygulamayı dağıtın. Dosya sistemi kullanan bir paket oluşturun ve ardından paketi el ile dağıtmak veya PowerShell, RoboCopy veya XCopy gibi diğer araçları kullanın. Bu bölümde, Web dağıtımı kullanmıyorsanız paket el ile Kopyalamakta olduğunuz varsayılmıştır.

[!INCLUDE [remote-debugger-deploy-app-local](../debugger/includes/remote-debugger-deploy-app-local.md)]

### <a name="BKMK_msvsmon"></a> İndirin ve Windows Server'da uzak Araçları'nı yükleme

Bu öğreticide, Visual Studio 2017 kullanıyoruz.

Uzaktan hata ayıklayıcı indirmeye sayfa açma konusunda sorun yaşıyorsanız, bkz: [dosya indirme engellemesini](../debugger/remote-debugging.md#unblock_msvsmon) Yardım için.

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
### <a name="BKMK_setup"></a> Windows Server'da uzaktan hata ayıklayıcı ayarlama

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> Gerektiğinde ek kullanıcılar için izinler eklemek için kimlik doğrulaması modunu değiştirme veya bağlantı noktası numarası uzaktan hata ayıklayıcı için bkz: [uzaktan hata ayıklayıcı yapılandırma](../debugger/remote-debugging.md#configure_msvsmon).

### <a name="BKMK_attach"></a> Visual Studio bilgisayardan ASP.NET uygulamasına ekleme

1. Visual Studio bilgisayarda hata ayıklamaya çalıştığınız çözümü açın (**MyASPApp** bu makaledeki adımları izliyorsanız).
2. Visual Studio'da sırasıyla **hata ayıklama > ekleme işlemi için** (Ctrl + Alt + P).

    > [!TIP]
    > Visual Studio 2017 ', daha önce iliştirilmiş kullanarak aynı işlemi yeniden ekleyebilirsiniz **hata ayıklama > işlem için yeniden bağlayın...** (Shift + Alt + P). 

3. Niteleyici alan kümesi'ne  **\<uzak bilgisayar adı >: 4022**.
4. Tıklatın **yenileme**.
    Bazı işlemler görünür görmelisiniz **kullanılabilir işlemler** penceresi.

    Herhangi bir işlem görmüyorsanız (bağlantı noktası gereklidir) uzak bilgisayar adı yerine IP adresini kullanarak deneyin. Kullanabileceğiniz `ipconfig` IPv4 adresini almak için komut satırında.

    Kullanmak istiyorsanız, **Bul** düğmesini gerekebilir [açmak UDP bağlantı noktası 3702](#bkmk_openports) sunucusunda.

5. Denetleme **işlemleri tüm kullanıcıları göster**.

6. Hızla bulmak için bir işlem adının ilk harfi yazın *dotnet.exe* (için ASP.NET Core).
   
   ASP.NET Core uygulaması için önceki işlemin adlandırılmıştı *dnx.exe*.

    ![RemoteDBG_AttachToProcess](../debugger/media/remotedbg_attachtoprocess_aspnetcore.png "RemoteDBG_AttachToProcess")

7. Tıklatın **Attach**.

8. Uzak bilgisayarın Web sitesini açın. Bir tarayıcıda Git **http://\<uzak bilgisayar adı >**.
    
    ASP.NET web sayfası görmeniz gerekir.
9. Çalışan ASP.NET uygulamasındaki bağlantısını **hakkında** sayfası.

    Visual Studio'da kesme noktası isabet.

### <a name="bkmk_openports"></a> Sorun giderme: Windows Server üzerinde gerekli bağlantı noktalarını açın

Çoğu kurulumları ASP.NET ve uzaktan hata ayıklayıcı yüklemesi tarafından gerekli bağlantı noktaları açıldı. Ancak, dağıtım sorunlarını giderme ve uygulamanın bir güvenlik duvarının arkasında barındırılan, doğru bağlantı noktalarının açık olduğunu doğrulayın gerekebilir.

Bir Azure VM aracılığıyla bağlantı noktalarını açmanız gerekir [ağ güvenlik grubu](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80-for-web-traffic). 

Gerekli bağlantı noktaları:

- 80 - IIS için gerekli
- 4022 - gerekli Visual Studio 2017 uzaktan hata ayıklama için (bkz [uzaktan hata ayıklayıcı bağlantı noktası atamaları](../debugger/remote-debugger-port-assignments.md) daha fazla bilgi için).
- 3702 - UDP bağlantı noktası (isteğe bağlı) bulma olanak tanır **Bul** düğmesini Visual Studio uzaktan hata ayıklayıcı eklerken.

Ayrıca, bu bağlantı noktaları ASP.NET yükleme tarafından zaten açılması gerekir:
- 8172 - (Visual Studio uygulama dağıtmak Web dağıtımı için gerekli isteğe bağlı)

