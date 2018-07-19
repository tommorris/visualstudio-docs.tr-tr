---
title: Web dağıtımı kullanarak IIS'ye ASP.NET dağıtma
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
ms.openlocfilehash: 4705ca6e72001f8930e2fa4270515df53e1213a8
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39080856"
---
# <a name="deploy-aspnet-to-a-remote-iis-computer-using-web-deploy-in-visual-studio"></a>Visual Studio Web dağıtımı kullanarak uzak bir IIS bilgisayarına ASP.NET dağıtma

Bu makalede, ayarlamak ve bir Visual Studio 2017 ASP.NET MVC 4.5.2 uygulamasını yapılandırma ve IIS'ye dağıtma açıklanmaktadır. Bu makalede, temel bir Windows server IIS yapılandırmasını ayarlama ve uygulamayı Visual Studio'dan dağıtma adımlarını içerir. Sunucu bileşenleri yüklü zorunludur ve dağıtmaya hazır olduğundan emin olmak için bu adımları dahildir. Bir ASP.NET Core uygulaması dağıtıyorsanız, bazı adımlar farklıdır. ASP.NET Core uygulaması dağıtmak için bkz. [Yayımla alarak IIS uygulama yayımlama ayarları](../deployment/tutorial-import-publish-settings-iis.md) yönergeler için. ASP.NET ve ASP.NET Core bazı senaryolarda dağıtmak için daha hızlıdır alarak IIS yayımlama ayarları.

Bu yordamlar bu sunucu yapılandırmaları üzerinde test edilmiştir:
* Windows Server 2012 R2 ve IIS 8 (için Windows Server 2008 R2, server adımlarla farklı)

## <a name="create-the-aspnet-452-application-on-the-visual-studio-computer"></a>ASP.NET 4.5.2 oluşturun Visual Studio bilgisayardaki uygulama
  
1. Visual Studio çalıştıran bilgisayarda **dosya** > **yeni proje**.

1. Altında **Visual C#** veya **Visual Basic**, seçin **Web**, Orta bölmede seçin **ASP.NET Web uygulaması (.NET Framework)** ve ardından **Tamam**.

    Belirtilen proje şablonları görmüyorsanız tıklayın **açık Visual Studio yükleyicisi** sol bölmesinde bağlantıyı **yeni proje** iletişim kutusu. Visual Studio Yükleyicisi'ni başlatır. Yüklemelisiniz gerekli Visual Studio iş yüklerini tanımlamak için bu makaledeki önkoşullara bakın.

1. Seçin **MVC** (.NET Framework) emin olun **kimlik doğrulaması yok** seçilir ve ardından **Tamam**.

1. Gibi bir ad yazın **mywebapp şeklindedir** tıklatıp **Tamam**.

    Visual Studio projesi oluşturur.

1. Seçin **derleme** > **Çözümü Derle** Projeyi derlemek için.

## <a name="install-and-configure-iis-on-windows-server"></a>Yükleme ve Windows Server'da IIS yapılandırma

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>Windows Server'da tarayıcınızın güvenlik ayarlarını güncelleştirin

(Varsayılan olarak etkindir) Internet Explorer Artırılmış Güvenlik Yapılandırması etkinse, bazı web sunucusu bileşenlerini yükleme sağlamak için Güvenilen siteler bazı etki alanları eklemek gerekebilir. Güvenilen siteler giderek ekleme **Internet Seçenekleri** > **güvenlik** > **Güvenilen siteler** > **siteler** . Aşağıdaki etki alanlarını ekleyin.

- Microsoft.com
- go.microsoft.com
- download.microsoft.com
- IIS.NET

Yazılımı indirdiğinizde, çeşitli web sitesi komut dosyaları ve kaynakları yüklemeye izin vermek için istekleri alabilirsiniz. Bu kaynaklardan bazıları, gerekli değildir, ancak sürecini basitleştirmek için tıklatın **Ekle** istendiğinde.

## <a name="install-aspnet-45-on-windows-server"></a>ASP.NET 4.5, Windows Server yükleme

IIS üzerinde ASP.NET yüklemek için daha ayrıntılı bilgi isterseniz bkz [IIS 8.0 ASP.NET 3.5 ile ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

1. Sunucu Yöneticisi'nin sol bölmesinde, seçin **IIS**. Sunucuya sağ tıklayıp **Internet Information Services (IIS) Yöneticisi'ni**.

1. ASP.NET 4.5 yüklemek için Web Platformu Yükleyicisi (Webpı) kullanın (Windows Server 2012 R2'de sunucu düğümünden seçin **yeni Web Platformu bileşenlerini Al** ve ASP.NET için arama)

    ![RemoteDBG_IIS_AspNet_45](../debugger/media/remotedbg_iis_aspnet_45.png "RemoteDBG_IIS_AspNet_45")

    > [!NOTE]
    > Windows Server 2008 R2 kullanıyorsanız, bunun yerine şu komutu kullanarak ASP.NET 4'ü yükleyin:

     **C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -ir**

2. Sistemi yeniden başlatın (veya yürütme **net stop olan /y** ardından **net start w3svc** sistem YOLUNU bir değişiklik almak için bir komut isteminden).

## <a name="install-web-deploy-36-on-windows-server"></a>Windows Server'da 3.6 yükleme Web dağıtımı

[!INCLUDE [remote-debugger-install-web-deploy](../debugger/includes/remote-debugger-install-web-deploy.md)]

## <a name="configure-aspnet-web-site-on-the-windows-server-computer"></a>Windows Server bilgisayarında ASP.NET Web sitesi yapılandırma

1. Windows Gezgini'ni açın ve yeni bir klasör oluşturun **C:\Publish**, ASP.NET projesi daha sonra dağıtacağınız.

2. Zaten açık değilse, açmak **Internet Information Services (IIS) Yöneticisi'ni**. (Sunucu Yöneticisi'nin sol bölmesinde, seçin **IIS**. Sunucuya sağ tıklayıp **Internet Information Services (IIS) Yöneticisi'ni**.)

3. Altında **bağlantıları** sol bölmede, Git **siteleri**.

4. Seçin **varsayılan Web sitesi**, seçin **temel ayarları**, ayarlayıp **fiziksel yolu** için **C:\Publish**.

5. Sağ **varsayılan Web sitesi** düğümünü seçip alt **uygulama Ekle**.

6. Ayarlama **diğer** alanı **MyASPApp**, uygulama havuzu varsayılan değeri kabul edin (**DefaultAppPool**) ve **fiziksel yolu** için **C:\Publish**.

7. Altında **bağlantıları**seçin **uygulama havuzları**. Açık **DefaultAppPool** ve uygulama havuzu alanın ayarlanacağı **ASP.NET v4.0** (ASP.NET 4.5 uygulama havuzu için bir seçenek değildir).

8. IIS Yöneticisi'nde site seçiliyken, seçin **düzenleme izinleri**ve o IUSR, IIS_IUSRS veya uygulama havuzu okuma & yürütme hakları olan yetkili bir kullanıcı için yapılandırılan kullanıcı emin olun. Bu kullanıcılar hiçbiri mevcut olması durumunda, okuma ve yürütme hakları olan bir kullanıcı olarak IUSR'yi ekleyin.

## <a name="publish-and-deploy-the-app-using-web-deploy-from-visual-studio"></a>Yayımlama ve Web dağıtımı Visual Studio kullanarak uygulamayı dağıtma

[!INCLUDE [deploy-app-web-deploy](../deployment/includes/deploy-app-web-deploy.md)]

Ayrıca, bağlantı noktaları gidermeye ilişkin aşağıdaki bölümü okuyun gerekebilir.

## <a name="troubleshoot-open-required-ports-on-windows-server"></a>Sorun giderme: Windows Server üzerinde gerekli bağlantı noktaları açma

Çoğu ayarlar ASP.NET ve Web dağıtımı yüklemesi tarafından gerekli bağlantı noktalarının açıldığından. Ancak, bağlantı noktalarının açık olduğunu doğrulamak gerekebilir.

> [!NOTE]
> Bir Azure sanal makinesinde aracılığıyla bağlantı noktalarını açmanız gerekir [ağ güvenlik grubu](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80). 

Gerekli bağlantı noktaları:

* 80 - IIS için gerekli
* 8172 - uygulamayı Visual Studio'dan dağıtmak Web dağıtımı için gerekli

1. Windows Server üzerindeki bir bağlantı noktasını açmak için Aç **Başlat** menüsünde **Gelişmiş Güvenlik Özellikli Windows Güvenlik Duvarı**.

2. Ardından **gelen kuralları** > **yeni kural** > **bağlantı noktası**. Seçin **sonraki** altında **belirli yerel bağlantı noktaları**, bağlantı noktası numarasını girin, tıklayın **sonraki**, ardından **bağlantıya izin**, İleri'ye tıklayın ve ad ekleyin (**IIS**, **Web dağıtımı**, veya **msvsmon**) gelen kuralı için.

    Windows Güvenlik Duvarı yapılandırma hakkında ayrıntılı bilgi isterseniz bkz [uzaktan hata ayıklama için Windows Güvenlik Duvarı Yapılandırma](../debugger/configure-the-windows-firewall-for-remote-debugging.md).

3. Diğer gerekli bağlantı noktaları için ek kurallar oluşturun.

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, bir yayımlama ayarları dosyası oluşturuldu, Visual Studio'ya içe ve ASP.NET uygulaması IIS'e. İçeri aktararak dağıtabilirsiniz yayımlama ayarları.

> [!div class="nextstepaction"]
> [Dağıtma alarak IIS yayımlama ayarları](../deployment/tutorial-import-publish-settings-iis.md)
