---
title: Uzaktan hata ayıklama Uzak IIS bilgisayarda ASP.NET | Microsoft Docs
ms.custom: remotedebugging
ms.date: 05/21/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 9cb339b5-3caf-4755-aad1-4a5da54b2a23
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 759615311478f1b428edc2a800c61b9252a3a84a
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34746864"
---
# <a name="remote-debug-aspnet-on-a-remote-iis-computer"></a>Uzaktan hata ayıklama Uzak IIS bilgisayarda ASP.NET
IIS'ye dağıtılan bir ASP.NET uygulaması hata ayıklamak için yükleme ve uygulamanızı dağıtıldığı bilgisayarda Uzak araçları çalıştırın ve ardından Visual Studio'dan çalışan uygulamanıza ekleyin.

![Uzaktan hata ayıklayıcı bileşenleri](../debugger/media/remote-debugger-aspnet.png "Remote_debugger_components")

Bu kılavuz, ayarlama ve Visual Studio 2017 ASP.NET MVC 4.5.2 uygulama yapılandırma, IIS dağıtma ve Visual Studio uzaktan hata ayıklayıcı Ekle açıklanmaktadır.

> [!NOTE]
> Uzaktan ASP.NET Core yerine hata ayıklama, bkz: [bir IIS bilgisayarda uzaktan hata ayıklama ASP.NET Core](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md). Azure App Service için kolayca dağıtın ve hata ayıklama kullanarak IIS önceden yapılandırılmış bir örneğinde [anlık görüntü hata ayıklayıcı](../debugger/debug-live-azure-applications.md) (.NET 4.6.1 gerekli) ya da [Server Explorer'dan hata ayıklayıcı ekleme](../debugger/remote-debugging-azure.md).

Bu yordamlar bu sunucu yapılandırmaları test edilmiştir:
* Windows Server 2012 R2 ve IIS 8 (Windows Server 2008 R2'için sunucu adımları farklıdır)

## <a name="requirements"></a>Gereksinimler

Uzaktan hata ayıklayıcı, Windows Server 2008 Service Pack 2 ile başlayarak Windows Server'da desteklenir. Gereksinimlerinin tam listesi için bkz: [gereksinimleri](../debugger/remote-debugging.md#requirements_msvsmon).

> [!NOTE]
> Bir proxy üzerinden bağlı iki bilgisayar arasında hata ayıklama desteklenmiyor. Bir yüksek gecikme veya çevirmeli Internet gibi düşük bant genişlikli bağlantısı veya Internet üzerinden ülkelerde arasında hata ayıklama önerilmez ve başarısız olabilir veya edilemeyecek yavaş.

## <a name="app-already-running-in-iis"></a>IIS zaten çalışan uygulama?

Bu makale Windows Server IIS temel yapılandırması ayarlama ve Visual Studio uygulama dağıtma adımları içerir. Sunucu bileşenlerinin yüklü, uygulamanın doğru çalıştırabilir ve uzaktan hata ayıklama için hazır olduğunu istedi emin olmak için aşağıdaki adımları eklenmiştir.

* Uygulamanız IIS çalıştıran ve yalnızca istiyorsanız uzaktan hata ayıklayıcı karşıdan yüklemek ve hata ayıklamayı başlatma, Git [indirin ve Windows Server'da uzak Araçları'nı yükleme](#BKMK_msvsmon).

* Emin olmak için Yardım istiyorsanız, uygulamanızın, dağıtılan, ayarlanır ve doğru ayıklanabilmesi, IIS çalıştıran, bu konudaki tüm adımları izleyin.

## <a name="create-the-aspnet-452-application-on-the-visual-studio-computer"></a>ASP.NET 4.5.2 oluşturmak Visual Studio bilgisayardaki uygulama
  
1. Yeni bir ASP.NET MVC uygulaması oluşturun. (**Dosya > Yeni > Proje**seçeneğini belirleyip ** Visual C# > Web > ASP.NET Web uygulaması. İçinde **ASP.NET 4.5.2** şablonları bölümünde, select **MVC**. Olduğundan emin olun **Docker desteğini etkinleştir** seçilmemiş ve **kimlik doğrulaması** ayarlanır **doğrulaması yok**. Proje adı **MyASPApp**.)

2. HomeController.cs dosyasını açın ve bir kesme noktası kümesinde `About()` yöntemi.

## <a name="bkmk_configureIIS"></a> IIS yükle ve Windows Server'da Yapılandır

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>Windows Server'da tarayıcı güvenlik ayarlarını güncelleştirme

Ardından (varsayılan olarak etkindir) Internet Explorer Artırılmış Güvenlik Yapılandırması etkinse, bazı etki alanlarına, bazı web sunucusu bileşenlerini yükleme sağlamak için güvenilir siteler olarak eklemeniz gerekebilir. Güvenilen siteler giderek eklemek **Internet Seçenekleri > Güvenlik > Güvenilen siteler > siteleri**. Şu etki alanlarına ekleyin.

- Microsoft.com
- go.microsoft.com
- download.microsoft.com
- IIS.NET

Yazılım yüklediğinizde, çeşitli web sitesi komut dosyaları ve kaynakları yükleme izni vermek için istekleri alabilirsiniz. Bu kaynakların bazıları gerekli değildir ancak işlemini basitleştirmek için tıklatın **Ekle** istendiğinde.

## <a name="BKMK_deploy_asp_net"></a> Windows Server'da ASP.NET 4.5 yükleyin

IIS üzerinde ASP.NET yüklemek için daha ayrıntılı bilgi isterseniz bkz [IIS 8.0 kullanarak ASP.NET 3.5 ve ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

1. Sunucu Yöneticisi'nin sol bölmesinde, seçin **IIS**. Sunucuya sağ tıklayın ve seçin **Internet Information Services (IIS) Yöneticisi'ni**.

1. ASP.NET 4.5 yüklemek için Web Platformu Yükleyicisi (Webpı) kullanın (Windows Server 2012 R2'de sunucu düğümünden diğerine seçin **yeni Web Platformu bileşenlerini Al** ve ASP.NET için arama yapın)

    ![RemoteDBG_IIS_AspNet_45](../debugger/media/remotedbg_iis_aspnet_45.png "RemoteDBG_IIS_AspNet_45")

    > [!NOTE]
    > Windows Server 2008 R2 kullanıyorsanız, bunun yerine bu komutu kullanarak ASP.NET 4'ü yükleyin:

     **C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -ir**

2. Sistemi yeniden başlatın (veya yürütme **net stop edildi /y** arkasından **net start w3svc** sistem yolu değişiklik seçmek için bir komut isteminden).

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

Uygulama başarıyla dağıtıldıktan sonra otomatik olarak başlamanız gerekir. Uygulama Visual Studio'dan başlamazsa, IIS'de uygulamayı başlatın.

1. İçinde **ayarları** iletişim kutusu, tıklayarak hata ayıklamayı etkinleştir **sonraki**, seçin bir **hata ayıklama** yapılandırma ve ardından **ek dosyaları Kaldır Hedef** altında **yayımlama dosyası** seçenekleri.

    > [!NOTE]
    > Bir yayın yapılandırma seçerseniz, hata ayıklamasını devre dışı *web.config* yayımladığınızda, dosya.

1. Tıklatın **kaydetmek** ve uygulamayı yeniden yayımlayın.

## <a name="optional-deploy-by-publishing-to-a-local-folder"></a>(İsteğe bağlı) Yerel bir klasöre yayımlama tarafından dağıtma

Powershell, RoboCopy, kullanarak IIS uygulama kopyalamak istediğiniz veya dosyaları el ile kopyalamak istiyorsanız uygulamanızı dağıtmak için bu seçeneği kullanın.

### <a name="BKMK_deploy_asp_net"></a> Windows Server bilgisayarında ASP.NET Web sitesi yapılandırması

1. Windows Gezgini'ni açın ve yeni bir klasör oluşturun **C:\Publish**, ASP.NET projesi daha sonra dağıtacağı.

2. Zaten açık değilse, açmak **Internet Information Services (IIS) Yöneticisi'ni**. (Sunucu Yöneticisi'nin sol bölmesinde, seçin **IIS**. Sunucuya sağ tıklayın ve seçin **Internet Information Services (IIS) Yöneticisi'ni**.)

3. Altında **bağlantıları** sol bölmede, Git **siteleri**.

4. Seçin **varsayılan Web sitesi**, seçin **temel ayarları**ve **fiziksel yolu** için **C:\Publish**.

5. Sağ **varsayılan Web sitesi** düğümü ve select **uygulama Ekle**.

6. Ayarlama **diğer** alanı **MyASPApp**, uygulama havuzu Varsayılanları kabul (**DefaultAppPool**) ve ayarlayın **fiziksel yolu** için **C:\Publish**.

7. Altında **bağlantıları**seçin **uygulama havuzları**. Açık **DefaultAppPool** ve uygulama havuzu alanı ayarlamak **ASP.NET v4.0** (ASP.NET 4.5 uygulama havuzu için bir seçenek değildir).

8. IIS Yöneticisi'nde site seçiliyken, seçin **izinleri Düzenle**ve bu IUSR, IIS_IUSRS ya da okuma ve yürütme hakları olan yetkili bir kullanıcının uygulama havuzu için yapılandırılan kullanıcı emin olun. Bu kullanıcılar hiçbiri mevcut değilse, okuma ve yürütme hakları olan bir kullanıcı olarak IUSR ekleyin.

### <a name="publish-and-deploy-the-app-by-publishing-to-a-local-folder-from-visual-studio"></a>Yayımlama ve uygulama yayımlayarak bir yerel klasöre Visual Studio'dan dağıtma

Ayrıca, yayımlama ve dosya sistemi veya diğer araçları kullanarak uygulamayı dağıtın.

1. (ASP.NET 4.5.2) Web.config dosyasının doğru sürümü .NET Framework'ün gösterdiğinden emin olun.  Örneğin, ASP.NET 4.5.2 hedefliyorsanız, bu sürüm web.config dosyasında listelendiğinden emin olun.
  
    ```xml
    <system.web>
      <compilation debug="true" targetFramework="4.5.2" />
      <httpRuntime targetFramework="4.5.2" />
      <httpModules>
        <add name="ApplicationInsightsWebTracking" type="Microsoft.ApplicationInsights.Web.ApplicationInsightsHttpModule, Microsoft.AI.Web" />
      </httpModules>
    </system.web>
  
    ```

    Örneğin, ASP.NET 4 4.5.2 yerine yüklerseniz sürüm 4.0 olmalıdır.

[!INCLUDE [remote-debugger-deploy-app-local](../debugger/includes/remote-debugger-deploy-app-local.md)]

## <a name="BKMK_msvsmon"></a> İndirin ve Windows Server'da uzak Araçları'nı yükleme

Bu öğreticide, Visual Studio 2017 kullanıyoruz.

Uzaktan hata ayıklayıcı indirmeye sayfa açma konusunda sorun yaşıyorsanız, bkz: [dosya indirme engellemesini](../debugger/remote-debugging.md#unblock_msvsmon) Yardım için.

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

> [!TIP]
> Bazı senaryolarda, bir dosya paylaşımından uzaktan hata ayıklayıcı çalıştırmak için etkili olabilir. Daha fazla bilgi için bkz: [dosya paylaşımından uzaktan hata ayıklayıcı çalıştırmak](../debugger/remote-debugging.md#fileshare_msvsmon).
  
## <a name="BKMK_setup"></a> Windows Server'da uzaktan hata ayıklayıcı ayarlama

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> Gerektiğinde ek kullanıcılar için izinler eklemek için kimlik doğrulaması modunu değiştirme veya bağlantı noktası numarası uzaktan hata ayıklayıcı için bkz: [uzaktan hata ayıklayıcı yapılandırma](../debugger/remote-debugging.md#configure_msvsmon).

Uzaktan hata ayıklayıcı bir hizmet olarak çalışması hakkında daha fazla bilgi için bkz: [uzaktan hata ayıklayıcı bir hizmet olarak çalışması](../debugger/remote-debugging.md#bkmk_configureService).

## <a name="BKMK_attach"></a> Visual Studio bilgisayardan ASP.NET uygulamasına ekleme

1. Visual Studio bilgisayarda hata ayıklamaya çalıştığınız çözümü açın (**MyASPApp** bu makaledeki adımları izliyorsanız).
2. Visual Studio'da sırasıyla **hata ayıklama > ekleme işlemi için** (Ctrl + Alt + P).

    > [!TIP]
    > Visual Studio 2017 ', daha önce iliştirilmiş kullanarak aynı işlem için iliştirebilirsiniz **hata ayıklama > işlem için yeniden bağlayın...** (Shift + Alt + P). 

3. Niteleyici alan kümesi'ne  **\<uzak bilgisayar adı >: 4022**.
4. Tıklatın **yenileme**.
    Bazı işlemler görünür görmelisiniz **kullanılabilir işlemler** penceresi.

    Herhangi bir işlem görmüyorsanız (bağlantı noktası gereklidir) uzak bilgisayar adı yerine IP adresini kullanarak deneyin. Kullanabileceğiniz `ipconfig` IPv4 adresini almak için komut satırında.

5. Denetleme **işlemleri tüm kullanıcıları göster**.
6. Hızla bulmak için bir işlem adının ilk harfi yazın **w3wp.exe** ASP.NET 4.5 için.

    ![RemoteDBG_AttachToProcess](../debugger/media/remotedbg_attachtoprocess.png "RemoteDBG_AttachToProcess")

7. Tıklatın **ekleme**

8. Uzak bilgisayarın Web sitesini açın. Bir tarayıcıda Git **http://\<uzak bilgisayar adı >**.
    
    ASP.NET web sayfası görmeniz gerekir.
9. Çalışan ASP.NET uygulamasındaki bağlantısını **hakkında** sayfası.

    Visual Studio'da kesme noktası isabet.

## <a name="bkmk_openports"></a> Sorun giderme: Windows Server üzerinde gerekli bağlantı noktalarını açın

Çoğu kurulumları ASP.NET ve uzaktan hata ayıklayıcı yüklemesi tarafından gerekli bağlantı noktaları açıldı. Ancak, bağlantı noktalarının açık olduğunu doğrulamak gerekebilir.

> [!NOTE]
> Bir Azure VM aracılığıyla bağlantı noktalarını açmanız gerekir [ağ güvenlik grubu](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80). 

Gerekli bağlantı noktaları:

- 80 - IIS için gerekli
- 8172 - (Visual Studio uygulama dağıtmak Web dağıtımı için gerekli isteğe bağlı)
- 4022 - gerekli Visual Studio 2017 uzaktan hata ayıklama için (bkz [uzaktan hata ayıklayıcı bağlantı noktası atamaları](../debugger/remote-debugger-port-assignments.md) ayrıntılı bilgi için.
- 3702 - UDP bağlantı noktası (isteğe bağlı) bulma olanak tanır **Bul** düğmesini Visual Studio uzaktan hata ayıklayıcı eklerken.

1. Windows Server'da bir bağlantı noktası açmak için Aç **Başlat** menüsü, arama **Gelişmiş Güvenlik Özellikli Windows Güvenlik Duvarı**.

2. Ardından **gelen kuralları > Yeni Kural > bağlantı noktası**. Seçin **sonraki** ve altında **belirli yerel bağlantı noktaları**, bağlantı noktası numarasını girin, tıklatın **sonraki**, ardından **bağlantıya izin**, İleri'ye tıklayın ve ad ekleyin (**IIS**, **Web dağıtımı**, veya **msvsmon**) gelen kuralı için.

    Windows Güvenlik duvarını yapılandırma hakkında daha ayrıntılı bilgi isterseniz bkz [uzaktan hata ayıklama için Windows Güvenlik Duvarı Yapılandırma](../debugger/configure-the-windows-firewall-for-remote-debugging.md).

3. Diğer gerekli bağlantı noktaları için ek kurallar oluşturun.