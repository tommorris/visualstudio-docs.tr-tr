---
title: "Uzaktan hata ayıklama ASP.NET Core Uzak IIS bilgisayarda | Microsoft Docs"
ms.custom: remotedebugging
ms.date: 08/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 573a3fc5-6901-41f1-bc87-557aa45d8858
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: c4069290a8a788bd4c36166a3d7720f61f263d69
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="remote-debug-aspnet-core-on-a-remote-iis-computer-in-visual-studio-2017"></a>Visual Studio 2017 bir uzak IIS bilgisayarda uzaktan hata ayıklama ASP.NET Çekirdeği
IIS'ye dağıtılan bir ASP.NET uygulaması hata ayıklamak için yükleme ve uygulamanızı dağıtıldığı bilgisayarda Uzak araçları çalıştırın ve ardından Visual Studio'dan çalışan uygulamanıza ekleyin.

![Uzaktan hata ayıklayıcı bileşenleri](../debugger/media/remote-debugger-aspnet.png "Remote_debugger_components")

Bu kılavuz, ayarlama ve Visual Studio 2017 ASP.NET çekirdek yapılandırma, IIS dağıtma ve Visual Studio uzaktan hata ayıklayıcı Ekle açıklanmaktadır. Uzaktan hata ayıklama için ASP.NET 4.5.2, bkz: [bir IIS bilgisayarda uzaktan hata ayıklama ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md). Ayrıca, dağıtmak ve Azure kullanarak IIS hata ayıklama. Daha fazla bilgi için bkz: [uzaktan hata ayıklama Azure üzerinde](../debugger/remote-debugging-azure.md).

Bu yordamlar bu sunucu yapılandırmaları test edilmiştir:
* Windows Server 2012 R2 ve IIS 8
* Windows Server 2016 ve IIS 10

## <a name="requirements"></a>Gereksinimler

Bir proxy üzerinden bağlı iki bilgisayar arasında hata ayıklama desteklenmiyor. Bir yüksek gecikme veya çevirmeli Internet gibi düşük bant genişlikli bağlantısı veya Internet üzerinden ülkelerde arasında hata ayıklama önerilmez ve başarısız olabilir veya edilemeyecek yavaş. Gereksinimlerinin tam listesi için bkz: [gereksinimleri](../debugger/remote-debugging.md#requirements_msvsmon).

## <a name="create-the-aspnet-core-application-on-the-visual-studio-2017-computer"></a>Visual Studio 2017 bilgisayarda ASP.NET Core uygulaması oluşturma 

1. Yeni bir ASP.NET Core uygulaması oluşturun. (**Dosya > Yeni > Proje**seçeneğini belirleyip **Visual C# > Web > ASP.NET çekirdek Web uygulaması**).

    İçinde **ASP.NET Core** şablonları bölümünde, select **Web uygulaması**.

2. Olduğundan emin olun **ASP.NET Core 2.0** seçildiğinde, **Docker desteğini etkinleştir** olan **değil** seçili ve **kimlik doğrulaması** ayarlanır **Kimlik doğrulaması yok**.

3. Proje adı **MyASPApp** tıklatıp **Tamam** yeni bir çözüm oluşturmak için.

4. About.cshtml.cs dosyasını açın ve bir kesme noktası kümesinde `OnGet` yöntemi (eski şablonlarında, bunun yerine HomeController.cs açın ve kesme kümesinde `About()` yöntemi).

## <a name="bkmk_configureIIS"></a>IIS yükle ve Windows Server'da Yapılandır

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>Windows Server'da tarayıcı güvenlik ayarlarını güncelleştirme

Güvenlik ayarlarınıza bağlı olarak, bu öğreticide anlatılan yazılım kolayca indirebilirsiniz şekilde tarayıcınıza aşağıdaki Güvenilen siteler eklemek için zamandan tasarruf. Bu sitelere erişimi gerekebilir:

- Microsoft.com
- go.microsoft.com
- download.microsoft.com
- VisualStudio.com

Internet Explorer kullanıyorsanız, Güvenilen siteler giderek ekleyebileceğiniz **Internet Seçenekleri > Güvenlik > Güvenilen siteler > siteleri**. Bu adımlar, tarayıcılar için farklıdır. (Uzaktan hata ayıklayıcı daha eski bir sürümü my.visualstudio.com karşıdan yüklemeniz gerekiyorsa, bazı ek Güvenilen siteler oturum açmak için gereklidir.)

Yazılım yüklediğinizde, çeşitli web sitesi komut dosyaları ve kaynakları yükleme izni vermek için istekleri alabilirsiniz. Çoğu durumda, bu ek kaynakları yazılımı yüklemeniz gerekmez.

## <a name="install-aspnet-core-on-windows-server"></a>ASP.NET Core Windows Server yükleme

1. Yükleme [.NET Core Windows Server barındırma](https://aka.ms/dotnetcore-2-windowshosting) barındıran sistemde paket. Paket .NET çekirdeği çalışma zamanı, .NET Core kitaplığı ve ASP.NET Core Modülü'nü yükler. Daha fazla ayrıntılı yönergeler için bkz: [IIS yayımlama](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration).

    > [!NOTE]
    > Sistem Internet bağlantısı yoksa, edinme ve yükleme  *[Microsoft Visual C++ 2015 Redistributable](https://www.microsoft.com/download/details.aspx?id=53840)*  .NET Core Windows Server barındırma paketini yüklemeden önce.

3. Sistemi yeniden başlatın (veya yürütme **net stop edildi /y** arkasından **net start w3svc** sistem yolu değişiklik seçmek için bir komut isteminden).

## <a name="BKMK_install_webdeploy"></a>(İsteğe bağlı) Windows Server'da 3.6 yükleme Web dağıtımı

[!INCLUDE [remote-debugger-install-web-deploy](../debugger/includes/remote-debugger-install-web-deploy.md)]

## <a name="BKMK_deploy_asp_net"></a>Windows Server bilgisayarında ASP.NET Web sitesi yapılandırması

1. Windows Gezgini'ni açın ve yeni bir klasör oluşturun **C:\Publish**, ASP.NET projesi daha sonra dağıtacağı.

2. Açık **Internet Information Services (IIS) Yöneticisi**. (Sunucu Yöneticisi'nin sol bölmesinde, seçin **IIS**. Sunucuya sağ tıklayın ve seçin **Internet Information Services (IIS) Yöneticisi'ni**.)

3. Altında **bağlantıları** sol bölmede, Git **siteleri**.

4. Seçin **varsayılan Web sitesi**, seçin **temel ayarları**ve **fiziksel yolu** için **C:\Publish**.

4. Sağ **varsayılan Web sitesi** düğümü ve select **uygulama Ekle**.

5. Ayarlama **diğer** alanı **MyASPApp**, uygulama havuzu Varsayılanları kabul (**DefaultAppPool**) ve ayarlayın **fiziksel yolu** için **C:\Publish**.

6. Altında **bağlantıları**seçin **uygulama havuzları**. Açık **DefaultAppPool** ve uygulama havuzu alanı ayarlamak **yönetilen kod yok**.

7. Yeni site IIS Yöneticisi'nde sağ tıklayın, seçin **izinleri Düzenle**ve bu IUSR, IIS_IUSRS veya web uygulamasına erişim okuma ve yürütme hakları olan yetkili bir kullanıcı için yapılandırılan kullanıcı emin olun.

    Bu kullanıcılara erişim birini görmüyorsanız, okuma ve yürütme hakları olan bir kullanıcı olarak IUSR eklemek için adımları gidin.

## <a name="bkmk_webdeploy"></a>(İsteğe bağlı) Yayımlama ve Web dağıtımı Visual Studio'dan kullanarak uygulamayı dağıtma

[!INCLUDE [remote-debugger-deploy-app-web-deploy](../debugger/includes/remote-debugger-deploy-app-web-deploy.md)]

## <a name="optional-publish-and-deploy-the-app-by-publishing-to-a-local-folder-from-visual-studio"></a>(İsteğe bağlı) Yayımlama ve uygulama yayımlayarak bir yerel klasöre Visual Studio'dan dağıtma

Ayrıca, yayımlama ve dosya sistemi veya diğer araçları kullanarak uygulamayı dağıtın.

[!INCLUDE [remote-debugger-deploy-app-local](../debugger/includes/remote-debugger-deploy-app-local.md)]

## <a name="BKMK_msvsmon"></a>İndirin ve Windows Server'da uzak Araçları'nı yükleme

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

> [!TIP]
> Bazı senaryolarda, bir dosya paylaşımından uzaktan hata ayıklayıcı çalıştırmak için etkili olabilir. Daha fazla bilgi için bkz: [dosya paylaşımından uzaktan hata ayıklayıcı çalıştırmak](../debugger/remote-debugging.md#fileshare_msvsmon).
  
## <a name="BKMK_setup"></a>Windows Server'da uzaktan hata ayıklayıcı ayarlama

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> Gerektiğinde ek kullanıcılar için izinler eklemek için kimlik doğrulaması modunu değiştirme veya bağlantı noktası numarası uzaktan hata ayıklayıcı için bkz: [uzaktan hata ayıklayıcı yapılandırma](../debugger/remote-debugging.md#configure_msvsmon).

Uzaktan hata ayıklayıcı bir hizmet olarak çalışması hakkında daha fazla bilgi için bkz: [uzaktan hata ayıklayıcı bir hizmet olarak çalışması](../debugger/remote-debugging.md#bkmk_configureService).

## <a name="BKMK_attach"></a>Visual Studio bilgisayardan ASP.NET uygulamasına ekleme

1. Visual Studio bilgisayarda açın **MyASPApp** çözümü.
2. Visual Studio'da sırasıyla **hata ayıklama > ekleme işlemi için** (Ctrl + Alt + P).

    > [!TIP]
    > Visual Studio 2017 ', daha önce iliştirilmiş kullanarak aynı işlem için iliştirebilirsiniz **hata ayıklama > işlem için yeniden bağlayın...** (Shift + Alt + P). 

3. Niteleyici alan kümesi'ne  **\<uzak bilgisayar adı >: 4022**.
4. Tıklatın **yenileme**.
    Bazı işlemler görünür görmelisiniz **kullanılabilir işlemler** penceresi.

    Herhangi bir işlem görmüyorsanız (bağlantı noktası gereklidir) uzak bilgisayar adı yerine IP adresini kullanarak deneyin. Kullanabileceğiniz `ipconfig` IPv4 adresini almak için komut satırında.

    Kullanmak istiyorsanız, **Bul** düğmesini gerekebilir [açmak UDP bağlantı noktası 3702](#bkmk_openports) sunucusunda.

5. Denetleme **işlemleri tüm kullanıcıları göster**.
6. Hızla bulmak için bir işlem adının ilk harfi yazın **dotnet.exe** (için ASP.NET Core).

    ![RemoteDBG_AttachToProcess](../debugger/media/remotedbg_attachtoprocess_aspnetcore.png "RemoteDBG_AttachToProcess")

7. Tıklatın **Attach**.

8. Uzak bilgisayarın Web sitesini açın. Bir tarayıcıda Git **http://\<uzak bilgisayar adı >**.
    
    ASP.NET web sayfası görmeniz gerekir.

9. Çalışan ASP.NET uygulamasındaki bağlantısını **hakkında** sayfası.

    Visual Studio'da kesme noktası isabet.

## <a name="bkmk_openports"></a>Sorun giderme: Windows Server üzerinde gerekli bağlantı noktalarını açın

Çoğu kurulumları ASP.NET ve uzaktan hata ayıklayıcı yüklemesi tarafından gerekli bağlantı noktaları açıldı. Ancak, bağlantı noktalarının açık olduğunu doğrulamak gerekebilir.

> [!NOTE]
> Bir Azure VM aracılığıyla bağlantı noktalarını açmanız gerekir [ağ güvenlik grubu](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80). 

Gerekli bağlantı noktaları:

- 80 - IIS için gerekli
- 4022 - gerekli Visual Studio 2017 uzaktan hata ayıklama için (bkz [uzaktan hata ayıklayıcı bağlantı noktası atamaları](../debugger/remote-debugger-port-assignments.md) ayrıntılı bilgi için.
- 8172 - (Visual Studio uygulama dağıtmak Web dağıtımı için isteğe bağlı) gereklidir.
- 3702 - UDP bağlantı noktası (isteğe bağlı) bulma olanak tanır **Bul** düğmesini Visual Studio uzaktan hata ayıklayıcı eklerken.

1. Windows Server'da bir bağlantı noktası açmak için Aç **Başlat** menüsü, arama **Gelişmiş Güvenlik Özellikli Windows Güvenlik Duvarı**.

2. Ardından **gelen kuralları > Yeni Kural > bağlantı noktası**ve ardından **sonraki**. (UDP 3702 için seçin **giden kuralları** yerine.)

3. Altında **belirli yerel bağlantı noktaları**, bağlantı noktası numarasını girin, tıklatın **sonraki**.

4. Tıklatın **bağlantıya izin**, tıklatın **sonraki**.

5. Bağlantı noktası için Etkinleştir'i tıklatın bir veya daha fazla ağ türlerini **sonraki**.

    Seçtiğiniz türü uzak bilgisayarın bağlı olduğu ağ eklemeniz gerekir.
6. Ad ekleyin (örneğin, **IIS**, **Web dağıtımı**, veya **msvsmon**) tıklatın ve gelen kuralı için **son**.

    Yeni kuralınıza kuralları gelen veya giden kuralları listesinde görmeniz gerekir.

    Windows Güvenlik duvarını yapılandırma hakkında daha ayrıntılı bilgi isterseniz bkz [uzaktan hata ayıklama için Windows Güvenlik Duvarı Yapılandırma](../debugger/configure-the-windows-firewall-for-remote-debugging.md).

3. Diğer gerekli bağlantı noktaları için ek kurallar oluşturun.
