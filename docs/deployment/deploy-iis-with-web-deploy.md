---
title: ASP.NET Web dağıtımı kullanarak IIS dağıtma
ms.custom: ''
ms.date: 06/04/2018
ms.technology: vs-ide-deployment
ms.topic: tutorial
ms.assetid: 9cb339b5-3caf-4755-aad1-4a5da54b2a23
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 87dc6c4152cd2f162880256b9b8372e04142913c
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36233522"
---
# <a name="deploy-aspnet-to-a-remote-iis-computer-using-web-deploy-in-visual-studio"></a>ASP.NET Web dağıtımı Visual Studio kullanarak uzak bir IIS bilgisayarına dağıtın

Bu makalede, IIS ilkesi ayarlayın ve Visual Studio 2017 ASP.NET MVC 4.5.2 uygulamayı yapılandırın ve açıklanmaktadır. Bu makale Windows Server IIS temel yapılandırması ayarlama ve Visual Studio uygulama dağıtma adımları içerir. Sunucu bileşenlerinin yüklü istedi ve dağıtmak için hazır olduğundan emin olmak için aşağıdaki adımları eklenmiştir. Bir ASP.NET Core uygulama dağıtıyorsanız, bazı adımlar farklıdır. ASP.NET Core uygulama dağıtmak için bkz: [Yayımla alarak IIS bir uygulamaya yayımlama ayarları](../deployment/tutorial-import-publish-settings-iis.md) yönergeler için. ASP.NET ve ASP.NET Core bazı senaryolarda dağıtmak için daha hızlıdır alarak IIS yayımlama ayarları.

Bu yordamlar bu sunucu yapılandırmaları test edilmiştir:
* Windows Server 2012 R2 ve IIS 8 (Windows Server 2008 R2'için sunucu adımları farklıdır)

## <a name="create-the-aspnet-452-application-on-the-visual-studio-computer"></a>ASP.NET 4.5.2 oluşturmak Visual Studio bilgisayardaki uygulama
  
1. Visual Studio çalıştıran bilgisayarda seçin **dosya** > **yeni proje**.

1. Altında **Visual C#** veya **Visual Basic**, seçin **Web**ve ardından Orta bölmede ya da **ASP.NET Web uygulaması (.NET Framework)** ve ardından **Tamam**.

    Belirtilen proje şablonları görmüyorsanız tıklatın **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu. Visual Studio yükleyicisi başlatır. Yüklemelisiniz gerekli Visual Studio iş yüklerini tanımlamak için bu makaledeki önkoşullara bakın.

1. Seçin **MVC** (.NET Framework) emin olun **doğrulaması yok** seçilir ve ardından **Tamam**.

1. Gibi bir ad yazın **mywebapp şeklindedir** tıklatıp **Tamam**.

    Visual Studio projesi oluşturur.

1. Seçin **yapı** > **yapı çözümü** Projeyi derlemek için.

## <a name="install-and-configure-iis-on-windows-server"></a>IIS yükle ve Windows Server'da Yapılandır

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>Windows Server'da tarayıcı güvenlik ayarlarını güncelleştirme

Ardından (varsayılan olarak etkindir) Internet Explorer Artırılmış Güvenlik Yapılandırması etkinse, bazı etki alanlarına, bazı web sunucusu bileşenlerini yükleme sağlamak için güvenilir siteler olarak eklemeniz gerekebilir. Güvenilen siteler giderek eklemek **Internet Seçenekleri** > **güvenlik** > **Güvenilen siteler** > **siteler** . Şu etki alanlarına ekleyin.

- Microsoft.com
- go.microsoft.com
- download.microsoft.com
- IIS.NET

Yazılım yüklediğinizde, çeşitli web sitesi komut dosyaları ve kaynakları yükleme izni vermek için istekleri alabilirsiniz. Bu kaynakların bazıları gerekli değildir ancak işlemini basitleştirmek için tıklatın **Ekle** istendiğinde.

## <a name="install-aspnet-45-on-windows-server"></a>Windows Server'da ASP.NET 4.5 yükleyin

IIS üzerinde ASP.NET yüklemek için daha ayrıntılı bilgi isterseniz bkz [IIS 8.0 kullanarak ASP.NET 3.5 ve ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

1. Sunucu Yöneticisi'nin sol bölmesinde, seçin **IIS**. Sunucuya sağ tıklayın ve seçin **Internet Information Services (IIS) Yöneticisi'ni**.

1. ASP.NET 4.5 yüklemek için Web Platformu Yükleyicisi (Webpı) kullanın (Windows Server 2012 R2'de sunucu düğümünden diğerine seçin **yeni Web Platformu bileşenlerini Al** ve ASP.NET için arama yapın)

    ![RemoteDBG_IIS_AspNet_45](../debugger/media/remotedbg_iis_aspnet_45.png "RemoteDBG_IIS_AspNet_45")

    > [!NOTE]
    > Windows Server 2008 R2 kullanıyorsanız, bunun yerine bu komutu kullanarak ASP.NET 4'ü yükleyin:

     **C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -ir**

2. Sistemi yeniden başlatın (veya yürütme **net stop edildi /y** arkasından **net start w3svc** sistem yolu değişiklik seçmek için bir komut isteminden).

## <a name="install-web-deploy-36-on-windows-server"></a>Windows Server'da 3.6 yükleme Web dağıtımı

[!INCLUDE [remote-debugger-install-web-deploy](../debugger/includes/remote-debugger-install-web-deploy.md)]

## <a name="configure-aspnet-web-site-on-the-windows-server-computer"></a>Windows Server bilgisayarında ASP.NET Web sitesi yapılandırması

1. Windows Gezgini'ni açın ve yeni bir klasör oluşturun **C:\Publish**, ASP.NET projesi daha sonra dağıtacağı.

2. Zaten açık değilse, açmak **Internet Information Services (IIS) Yöneticisi'ni**. (Sunucu Yöneticisi'nin sol bölmesinde, seçin **IIS**. Sunucuya sağ tıklayın ve seçin **Internet Information Services (IIS) Yöneticisi'ni**.)

3. Altında **bağlantıları** sol bölmede, Git **siteleri**.

4. Seçin **varsayılan Web sitesi**, seçin **temel ayarları**ve **fiziksel yolu** için **C:\Publish**.

5. Sağ **varsayılan Web sitesi** düğümü ve select **uygulama Ekle**.

6. Ayarlama **diğer** alanı **MyASPApp**, uygulama havuzu Varsayılanları kabul (**DefaultAppPool**) ve ayarlayın **fiziksel yolu** için **C:\Publish**.

7. Altında **bağlantıları**seçin **uygulama havuzları**. Açık **DefaultAppPool** ve uygulama havuzu alanı ayarlamak **ASP.NET v4.0** (ASP.NET 4.5 uygulama havuzu için bir seçenek değildir).

8. IIS Yöneticisi'nde site seçiliyken, seçin **izinleri Düzenle**ve bu IUSR, IIS_IUSRS ya da okuma ve yürütme hakları olan yetkili bir kullanıcının uygulama havuzu için yapılandırılan kullanıcı emin olun. Bu kullanıcılar hiçbiri mevcut değilse, okuma ve yürütme hakları olan bir kullanıcı olarak IUSR ekleyin.

## <a name="publish-and-deploy-the-app-using-web-deploy-from-visual-studio"></a>Yayımlama ve Web dağıtımı Visual Studio'dan kullanarak uygulamayı dağıtma

[!INCLUDE [deploy-app-web-deploy](../deployment/includes/deploy-app-web-deploy.md)]

Ayrıca, bağlantı sorunlarını giderme konusunda aşağıdaki bölümü okuyun gerekebilir.

## <a name="troubleshoot-open-required-ports-on-windows-server"></a>Sorunlarını giderme: Windows Server gerekli bağlantı noktalarını açmanız

Çoğu kurulumları ASP.NET ve Web dağıtımı yüklemesi tarafından gerekli bağlantı noktaları açıldı. Ancak, bağlantı noktalarının açık olduğunu doğrulamak gerekebilir.

> [!NOTE]
> Bir Azure VM aracılığıyla bağlantı noktalarını açmanız gerekir [ağ güvenlik grubu](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80). 

Gerekli bağlantı noktaları:

* 80 - IIS için gerekli
* 8172 - Visual Studio uygulama dağıtmak Web dağıtımı için gerekli

1. Windows Server'da bir bağlantı noktası açmak için Aç **Başlat** menüsü, arama **Gelişmiş Güvenlik Özellikli Windows Güvenlik Duvarı**.

2. Ardından **gelen kuralları** > **yeni kural** > **bağlantı noktası**. Seçin **sonraki** ve altında **belirli yerel bağlantı noktaları**, bağlantı noktası numarasını girin, tıklatın **sonraki**, ardından **bağlantıya izin**, İleri'ye tıklayın ve ad ekleyin (**IIS**, **Web dağıtımı**, veya **msvsmon**) gelen kuralı için.

    Windows Güvenlik duvarını yapılandırma hakkında daha ayrıntılı bilgi isterseniz bkz [uzaktan hata ayıklama için Windows Güvenlik Duvarı Yapılandırma](../debugger/configure-the-windows-firewall-for-remote-debugging.md).

3. Diğer gerekli bağlantı noktaları için ek kurallar oluşturun.

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide bir yayımlama ayarları dosyası oluşturdunuz, Visual Studio'ya içeri aktarılan ve IIS bir ASP.NET uygulaması dağıttınız. İçeri aktararak dağıtabilirsiniz yayımlama ayarları.

> [!div class="nextstepaction"]
> [Dağıtmak alarak IIS yayımlama ayarları](../deployment/tutorial-import-publish-settings-iis.md)
