---
title: İçeri aktararak için Azure yayımlama yayımlama ayarları
ms.custom: Create and import a publishing profile to deploy an application from Visual Studio to Azure App Service
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
ms.openlocfilehash: a0fcc9f6ec4143a757139a9e013f1a1f4dbe666e
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2018
---
# <a name="publish-an-application-to-azure-app-service-by-importing-publish-settings-in-visual-studio"></a>İçeri aktararak Azure App Service'e bir uygulama yayımlama Visual Studio'da yayımlama ayarları

Kullanabileceğiniz **Yayımla** aracı almak için uygulamanızı dağıtma ve yayımlama ayarları. Bu makalede, kullandığımız Azure uygulama hizmeti için yayınlama ayarlarını ancak kullanabilirsiniz içe aktarmak için benzer adımları yayımlama ayarlarını [IIS](../deployment/tutorial-import-publish-settings-iis.md). Bir yayımlama ayarları profili dağıtımı için Visual Studio her yüklemesi hizmetini el ile yapılandırma daha hızlı olabilir, bazı senaryolarda kullanın.

Visual Studio'da ASP.NET, ASP.NET Core ve .NET Core uygulamaları için aşağıdaki adımları uygulayın. Adımları Visual Studio 2017 sürüm 15,6 karşılık gelir.

Bu öğreticide şunları yapacaksınız:

> [!div class="checklist"]
> * Azure App hizmetinden bir yayımlama ayarları dosyası oluştur
> * Yayımlama ayarları dosyasını Visual Studio'ya içeri aktarma
> * Uygulama Azure App Service'e dağıtma

Yayımlama ayarları dosyası (*.publishsettings) bir yayımlama profili farklı (*.pubxml) Visual Studio'da oluşturuldu. Yayımlama ayarları dosyası Azure App Service tarafından oluşturulur ve ardından Visual Studio'ya aktarılabilir.

> [!NOTE]
> Yalnızca bir Visual Studio yayımlama profilini kopyalamak gerekiyorsa (\*.pubxml dosyası) bir yüklemesinden Visual Studio diğerine, yayımlama profili bulabilirsiniz  *\<profilename\>.pubxml*, içinde  *\\< projectname\>\Properties\PublishProfiles* yönetilen proje türleri için klasör. Web siteleri için kısmına bakın *\App_Data* klasör. Yayımlama profillerini MSBuild XML dosyalarıdır.

## <a name="prerequisites"></a>Önkoşullar

* Visual Studio yüklü olmalıdır ve **ASP.NET** ve **.NET Framework** geliştirme iş yükü. .NET Core uygulaması için etmeniz **.NET Core** iş yükü.

    Visual Studio henüz yüklemediyseniz, ücretsiz yükleme [burada](http://www.visualstudio.com).

* Bir Azure uygulama hizmeti oluşturun. Ayrıntılı yönergeler için bkz: [ASP.NET Core web uygulama dağıtmak için Visual Studio kullanarak Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs). 

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>Visual Studio'da yeni bir ASP.NET projesi oluşturma

1. Visual Studio çalıştıran bilgisayarda seçin **Dosya > Yeni proje**.

1. Altında **Visual C#** veya **Visual Basic**, seçin **Web**ve ardından Orta bölmede ya da **ASP.NET Web uygulaması (.NET Framework)** veya (C# yalnızca) **ASP.NET çekirdek Web uygulaması**ve ardından **Tamam**.

    Belirtilen proje şablonları görmüyorsanız tıklatın **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu. Visual Studio yükleyicisi başlatır. Yüklemelisiniz gerekli Visual Studio iş yüklerini tanımlamak için bu makaledeki önkoşullara bakın.

1. Ya da seçin **MVC** (.NET Framework) veya **Web uygulaması (Model-View-Controller)** (için .NET Core), emin olun **doğrulaması yok** seçilir ve ardından **Tamam**.

1. Gibi bir ad yazın **mywebapp şeklindedir** tıklatıp **Tamam**.

    Visual Studio projesi oluşturur.

1. Seçin **Yapı > Yapı çözümü** Projeyi derlemek için.

## <a name="create-the-publish-settings-file-in-azure-app-service"></a>Azure App Service'te yayımlama ayarları dosyası oluşturma

1. Azure portalında Azure uygulama hizmeti açın.

1. Tıklatın **Get yayımlama profili** ve profil yerel olarak kaydedin.

    ![Yayımlama profilini Al](../deployment/media/tutorial-azure-app-service-get-publish-profile.png)

    Bir dosyayla bir *.publishsettings* dosya uzantısı kaydettiğiniz bu konumda oluşturuldu. Aşağıdaki kod dosyasının (bir daha okunabilir biçimlendirme) kısmi bir örneği gösterir.

    ```xml
    <publishData>
      <publishProfile
        profileName="DeployASPDotNetCore - Web Deploy"
        publishMethod="MSDeploy"
        publishUrl="deployaspdotnetcore.scm.azurewebsites.net:443"
        msdeploySite="DeployASPDotNetCore"
        userName="$DeployASPDotNetCore"
        userPWD="abcdefghijklmnopqrstuzwxyz"
        destinationAppUrl="http://deployaspdotnetcore20180508031824.azurewebsites.net"
        SQLServerDBConnectionString=""
        mySQLDBConnectionString=""
        hostingProviderForumLink=""
        controlPanelLink="http://windows.azure.com"
        webSystem="WebSites">
        <databases />
      </publishProfile>
    </publishData>
    ```
    Genellikle, önceki *.publishsettings dosya Visual Studio'da bir FTP kullanarak dağıtmak için Web dağıtımı ve bir kullanarak dağıtmak için kullanabileceğiniz iki yayımlama profili içeriyor. Önceki kod, Web dağıtımı profilini gösterir. Profil içeri aktardığınızda her iki profil de daha sonra içeri aktarılacak.

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Visual Studio'da yayımlama ayarlarını içeri aktarın ve dağıtın

1. Visual Studio'da açın ASP.NET projesi olduğu bilgisayarda, Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Yayımla**.

1. Tüm yayımlama profillerini daha önce yapılandırdıysanız **Yayımla** bölmesinde görünür. Tıklatın **yeni profil oluşturmak**.

1. İçinde **yayımlama hedefi çekme** iletişim kutusu, tıklatın **profilini içeri aktarma**.

    ![Seçin yayımlama](../deployment/media/tutorial-publish-tool-import-profile.png)

1. Önceki bölümde oluşturduğunuz yayımlama ayarları dosyası konumuna gidin.

1. İçinde **alma yayımlama ayarları dosyası** iletişim kutusunda, önceki bölümde oluşturduğunuz profili seçin ve tıklayın **açık**.

1. İki alınan profillerinden birini seçin ve tıklayın **Yayımla**.

    Visual Studio dağıtım işlemi başlar ve çıktı penceresi ilerleme durumunu ve sonuçlarını gösterir.

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide bir yayımlama ayarları dosyası oluşturdunuz, Visual Studio'ya içeri aktarılan ve Azure App Service'e bir ASP.NET uygulaması dağıttınız.

> [!div class="nextstepaction"]
> [Dağıtıma ilk bakış](../deployment/deploying-applications-services-and-components.md)
