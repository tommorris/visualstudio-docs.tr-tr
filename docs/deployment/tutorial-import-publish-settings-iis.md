---
title: Yayımla alarak IIS yayımlama ayarları
ms.custom: Create and import a publishing profile to deploy an application from Visual Studio to IIS
ms.date: 05/07/2018
ms.technology: vs-ide-deployment
ms.topic: tutorial
helpviewer_keywords:
- deployment, publish settings
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1db8ca68453cff105f2bbefcd384b8afa9efea9d
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2018
---
# <a name="publish-an-application-to-iis-by-importing-publish-settings-in-visual-studio"></a>İçeri aktararak IIS uygulama yayımlama Visual Studio'da yayımlama ayarları

Kullanabileceğiniz **Yayımla** aracı almak için uygulamanızı dağıtma ve yayımlama ayarları. Bu makalede, kullandığımız IIS ayarlarını yayımlamak ancak kullanabilirsiniz içe aktarmak için benzer adımları için yayımlama ayarları [Azure App Service](../deployment/tutorial-import-publish-settings-azure.md). Bir yayımlama ayarları profili el ile Visual Studio'nun her bir yükleme dağıtımı IIS yapılandırma daha hızlı olabilir, bazı senaryolarda kullanın.

Visual Studio'da ASP.NET, ASP.NET Core ve .NET Core uygulamaları için aşağıdaki adımları uygulayın. Adımları Visual Studio 2017 sürüm 15,6 karşılık gelir.

Bu öğreticide şunları yapacaksınız:

> [!div class="checklist"]
> * Yayımlama ayarları dosyası oluşturabilmesi IIS yapılandırma
> * Yayımlama ayarları dosyası oluşturma
> * Yayımlama ayarları dosyasını Visual Studio'ya içeri aktarma
> * IIS uygulama dağıtma

Yayımlama ayarları dosyası (\*.publishsettings) bir yayımlama profili farklı (\*.pubxml) Visual Studio'da oluşturuldu. Yayımlama ayarları dosyası IIS veya Azure uygulama hizmeti tarafından oluşturulan veya el ile oluşturulabilir ve ardından Visual Studio'ya aktarılabilir.

> [!NOTE]
> Yalnızca bir Visual Studio yayımlama profilini kopyalamak gerekiyorsa (\*.pubxml dosyası) bir yüklemesinden Visual Studio diğerine, yayımlama profili bulabilirsiniz  *\<profilename\>.pubxml*, içinde  *\\< projectname\>\Properties\PublishProfiles* yönetilen proje türleri için klasör. Web siteleri için kısmına bakın *\App_Data* klasör. Yayımlama profillerini MSBuild XML dosyalarıdır.

## <a name="prerequisites"></a>Önkoşullar

* Visual Studio yüklü olmalıdır ve **ASP.NET** ve **.NET Framework** geliştirme iş yükü. .NET Core uygulaması için etmeniz **.NET Core** iş yükü.

    Visual Studio henüz yüklemediyseniz, ücretsiz yükleme [burada](http://www.visualstudio.com).

    Bu makaledeki adımlarda Visual Studio 2017 üzerinde temel alır

* IIS yayımlama ayarları dosyası oluşturmak için doğru yapılandırılmış IIS 8.0 Web sunucusu rolü ve her iki ASP.NET 4.5 ile Windows Server 2012 çalıştıran başka bir bilgisayara veya ASP.NET Core yüklü olmalıdır. ASP.NET Core için bkz: [IIS yayımlama](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration). ASP.NET 4.5 için bkz: [IIS 8.0 kullanarak ASP.NET 3.5 ve ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>Visual Studio'da yeni bir ASP.NET projesi oluşturma

1. Visual Studio çalıştıran bilgisayarda seçin **Dosya > Yeni proje**.

1. Altında **Visual C#** veya **Visual Basic**, seçin **Web**ve ardından Orta bölmede ya da **ASP.NET Web uygulaması (.NET Framework)** veya (C# yalnızca) **ASP.NET çekirdek Web uygulaması**ve ardından **Tamam**.

    Belirtilen proje şablonları görmüyorsanız tıklatın **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu. Visual Studio yükleyicisi başlatır. Yüklemelisiniz gerekli Visual Studio iş yüklerini tanımlamak için bu makaledeki önkoşullara bakın.

1. Ya da seçin **MVC** (.NET Framework) veya **Web uygulaması (Model-View-Controller)** (için .NET Core), emin olun **doğrulaması yok** seçilir ve ardından **Tamam**.

1. Gibi bir ad yazın **mywebapp şeklindedir** tıklatıp **Tamam**.

    Visual Studio projesi oluşturur.

1. Seçin **Yapı > Yapı çözümü** Projeyi derlemek için.

## <a name="install-and-configure-web-deploy-on-windows-server"></a>Yükleme ve Windows Server'da Web dağıtımı yapılandırma

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/install-web-deploy-with-hosting-server.md)]

## <a name="create-the-publish-settings-file-in-iis-on-windows-server"></a>Windows Server'da IIS'de yayımlama ayarları dosyası oluşturma

1. IIS, sağ **varsayılan Web sitesi**, seçin **dağıtma** > **yapılandırma Web dağıtımı yayımlama**.

    ![Web dağıtımı yapılandırma yapılandırma](../deployment/media/tutorial-configure-web-deploy-publishing.png)

1. İçinde **yapılandırma Web dağıtımı yayımlama** iletişim kutusunda, ayarları inceleyin.

1. Tıklatın **Kurulum**.

    İçinde **sonuçları** paneli, erişim haklarını çıktısında verildi belirtilen kullanıcı ve, bir dosya bir *.publishsettings* dosya uzantısı, gösterilen konumda oluşturuldu iletişim kutusu.

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <publishData>
      <publishProfile
        publishUrl="https://myhostname:8172/msdeploy.axd"
        msdeploySite="Default Web Site"
        destinationAppUrl="http://myhostname:80/"
        mySQLDBConnectionString=""
        SQLServerDBConnectionString=""
        profileName="Default Settings"
        publishMethod="MSDeploy"
        userName="myhostname\myusername" />
    </publishData>
    ```

    Windows Server ve IIS yapılandırmasına bağlı olarak farklı değerler görürsünüz. Birkaç ayrıntılarını gördüğünüz değerleri şunlardır:

    * *Msdeploy.axd* başvurulan dosya `publishUrl` dinamik olarak oluşturulan HTTP işleyicisi için bir dosya Web dağıtımı bir özniteliktir. (Test amacıyla, `http://myhostname:8172` genellikle de çalışır.)
    * `publishUrl` Bağlantı noktası için Web dağıtımı için varsayılan olmayan bağlantı noktası 8172, genellikle ayarlanır.
    * `destinationAppUrl` Bağlantı noktası, IIS için varsayılan bağlantı noktası 80, genellikle ayarlanır.
    * Visual Studio'da (daha sonraki adımlarda) konak adını kullanarak uzak ana bilgisayara bağlanmak erişemiyorsanız ana bilgisayar adı yerine IP adresi sınayın.

    > [!NOTE]
    > Bir Azure VM'de çalışan IIS yayımlıyorsa, Web dağıtımı ve IIS bağlantı noktalarının ağ güvenlik grubu listesinde açılması gerekir. Ayrıntılı bilgi için bkz: [yükleme ve çalıştırma IIS](/azure/virtual-machines/windows/quick-create-portal#open-port-80-for-web-traffic).

1. Bu dosyayı Visual Studio çalıştırdığınız bilgisayara kopyalayın.

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Visual Studio'da yayımlama ayarlarını içeri aktarın ve dağıtın

1. Visual Studio'da açın ASP.NET projesi olduğu bilgisayarda, Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Yayımla**.

1. Tüm yayımlama profillerini daha önce yapılandırdıysanız **Yayımla** bölmesinde görünür. Tıklatın **yeni profil oluşturmak**.

1. İçinde **yayımlama hedefi çekme** iletişim kutusu, tıklatın **profilini içeri aktarma**.

    ![Seçin yayımlama](../deployment/media/tutorial-publish-tool-import-profile.png)

1. Önceki bölümde oluşturduğunuz yayımlama ayarları dosyası konumuna gidin.

1. İçinde **alma yayımlama ayarları dosyası** iletişim kutusu, gidin ve önceki bölümde oluşturduğunuz profili seçin ve tıklayın **açık**.

    Visual Studio dağıtım işlemi başlar ve çıktı penceresi ilerleme durumunu ve sonuçlarını gösterir.

    Herhangi bir dağıtım hataları alırsanız tıklatın **ayarları** ayarlarını düzenlemek için. Ayarları değiştirin ve tıklayın **doğrulama** yeni ayarlarını test etmek için.

    ![Yayımla aracı ayarlarını düzenleyin](../deployment/media/tutorial-configure-publish-settings-in-tool.png)

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide bir yayımlama ayarları dosyası oluşturdunuz, Visual Studio'ya içeri aktarılan ve IIS bir ASP.NET uygulaması dağıttınız.

> [!div class="nextstepaction"]
> [Dağıtıma ilk bakış](../deployment/deploying-applications-services-and-components.md)
