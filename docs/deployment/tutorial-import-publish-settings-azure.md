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
ms.openlocfilehash: 88dc37e555f6ceb30584d4a1c17b96506219631a
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766746"
---
# <a name="publish-an-application-to-azure-app-service-by-importing-publish-settings-in-visual-studio"></a>İçeri aktararak Azure App Service'e bir uygulama yayımlama Visual Studio'da yayımlama ayarları

Kullanabileceğiniz **Yayımla** aracı almak için uygulamanızı dağıtma ve yayımlama ayarları. Bu makalede, kullandığımız Azure uygulama hizmeti için yayınlama ayarlarını ancak kullanabilirsiniz içe aktarmak için benzer adımları yayımlama ayarlarını [IIS](../deployment/tutorial-import-publish-settings-iis.md). Bir yayımlama ayarları profili dağıtımı için Visual Studio her yüklemesi hizmetini el ile yapılandırma daha hızlı olabilir, bazı senaryolarda kullanın.

Visual Studio'da ASP.NET, ASP.NET Core ve .NET Core uygulamaları için aşağıdaki adımları uygulayın. Ayrıca içeri aktarabilirsiniz için yayınlama ayarlarını [Python](/visualstudio/python/publishing-python-web-applications-to-azure-from-visual-studio) uygulamalar. Adımları Visual Studio 2017 sürüm 15,6 karşılık gelir.

Bu öğreticide şunları yapacaksınız:

> [!div class="checklist"]
> * Azure App hizmetinden bir yayımlama ayarları dosyası oluştur
> * Yayımlama ayarları dosyasını Visual Studio'ya içeri aktarma
> * Uygulama Azure App Service'e dağıtma

Yayımlama ayarları dosyası (*\*.publishsettings*) bir yayımlama profili farklı (*\*.pubxml*) Visual Studio'da oluşturuldu. Yayımlama ayarları dosyası Azure App Service tarafından oluşturulur ve ardından Visual Studio'ya aktarılabilir.

> [!NOTE]
> Yalnızca bir Visual Studio yayımlama profilini kopyalamak gerekiyorsa (*\*.pubxml* dosyası) bir yüklemesinden Visual Studio diğerine, yayımlama profili bulabilirsiniz  *\<profilename\>.pubxml*,  *\\< projectname\>\Properties\PublishProfiles* yönetilen proje türleri için klasör. Web siteleri için kısmına bakın *\App_Data* klasör. Yayımlama profillerini MSBuild XML dosyalarıdır.

## <a name="prerequisites"></a>Önkoşullar

* Visual Studio 2017 yüklü olması gerekir ve **ASP.NET** ve. **NET Framework** geliştirme iş yükü. Ayrıca bir .NET Core uygulaması için gerekir. **NET çekirdek** iş yükü.

    Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

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

[!INCLUDE [import publish settings](../deployment/includes/import-publish-settings-vs.md)]

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide bir yayımlama ayarları dosyası oluşturdunuz, Visual Studio'ya içeri aktarılan ve Azure App Service'e bir ASP.NET uygulaması dağıttınız. Visual Studio'da yayımlama seçeneklerini genel bir bakış isteyebilirsiniz.

> [!div class="nextstepaction"]
> [Dağıtıma ilk bakış](../deployment/deploying-applications-services-and-components.md)
