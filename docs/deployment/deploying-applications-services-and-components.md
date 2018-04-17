---
title: Dağıtım genel bakış - Visual Studio | Microsoft Docs
description: Visual Studio'dan uygulamaları dağıtmak için seçenekleriniz hakkında bilgi edinin.
ms.custom: mvc
ms.date: 11/26/2017
ms.technology:
- vs-ide-deployment
ms.topic: quickstart
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- .NET applications, deploying
- components [Visual Studio], deploying
- installers
- publishing
- deploying applications [Visual Studio]
- deploying applications [Visual Studio], about deploying applications
- components [.NET Framework], deploying
ms.assetid: 63fcdd5b-2e54-4210-9038-65bc23167725
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5d4367c5daad9c8514f472fe759d1dba9fb7e357
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="quickstart-first-look-at-deployment-in-visual-studio"></a>Hızlı Başlangıç: İlk Visual Studio'daki dağıtımı bakın

Bir uygulamayı, hizmeti ya da bileşeni dağıtarak bunu diğer bilgisayarlardaki, cihazlardaki, sunuculardaki ya da buluttaki yükleme için dağıtmış olursunuz. İhtiyacınız olan dağıtım türü için uygun yöntemi Visual Studio'da seçebilirsiniz. (Burada açıklanmamaktadır diğer dağıtım araçları komut satırı dağıtım veya NuGet gibi pek çok uygulama türlerini destekler.)

Adım adım yönergeler için bkz.

### <a name="deploy-to-local-folder"></a>Yerel bir klasöre dağıtma

- **ASP.NET**, **ASP.NET Core**, **Node.js**, **Python**, ve **.NET Core**: yerel bir klasöre dağıtmak için yayımlama Aracı'nı kullanın. Kullanılabilir seçenekler, uygulama türüne bağlıdır. Çözüm Gezgini'nde, projenize sağ tıklayın ve seçin **Yayımla**ve ardından **klasörü**. Daha fazla bilgi için bkz: [bir yerel klasöre dağıtma](quickstart-deploy-to-local-folder.md).

    ![Seçin yayımlama](../deployment/media/quickstart-publish.png)

- **Visual C++ çalışma zamanı**: yerel dağıtım veya statik bağlama kullanarak Visual C++ çalışma zamanı dağıtabilirsiniz. Daha fazla bilgi için bkz: [dağıtma yerel Masaüstü uygulamaları (Visual C++)](/cpp/ide/deploying-native-desktop-applications-visual-cpp). 

### <a name="publish-to-web-or-deploy-to-network-share"></a>Web'de Yayımla veya ağ paylaşımına dağıtma

- **ASP.NET**, **ASP.NET Core**, **Node.js**, **Python**, ve **.NET Core**: Yayımla aracı dağıtmak için kullanabileceğiniz bir FTP veya Web dağıtımı kullanarak Web sitesi. Daha fazla bilgi için bkz: [bir web sitesine dağıtma](quickstart-deploy-to-a-web-site.md).

    Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Yayımla**. Yayımla aracında istediğiniz ve yapılandırma adımlarını izleyin seçeneğini belirleyin.

    ![IIS, FTP, vb. seçin.](../deployment/media/quickstart-publish-iis-ftp.png)

    Ayrıca, ASP.NET uygulamaları ve Hizmetleri, çeşitli diğer yollarla dağıtabilirsiniz. Daha fazla bilgi için bkz: [dağıtma ASP.NET web uygulamaları ve Hizmetleri](http://www.asp.net/aspnet/overview/deployment).

- **Visual C++ çalışma zamanı**: merkezi dağıtım kullanarak Visual C++ çalışma zamanı dağıtabilirsiniz. Daha fazla bilgi için bkz: [dağıtma yerel Masaüstü uygulamaları (Visual C++)](/cpp/ide/deploying-native-desktop-applications-visual-cpp). 

- **Windows Masaüstü** bir web sunucusuna veya ClickOnce dağıtımı kullanarak bir ağ dosya paylaşımı için bir Windows masaüstü uygulaması yayımlayabilirsiniz. Kullanıcılar, daha sonra uygulamayı tek bir tıklamayla yükleyebilir. Daha fazla bilgi için bkz: [ClickOnce kullanarak bir masaüstü uygulamasını dağıtmak](how-to-publish-a-clickonce-application-using-the-publish-wizard.md) ve [ClickOnce kullanarak yerel bir uygulama dağıtmak](/cpp/ide/clickonce-deployment-for-visual-cpp-applications).

### <a name="publish-to-azure"></a>Azure'a yayımlama

- **ASP.NET, ASP.NET Core, Python, Node.js ve .NET Core** web uygulamaları: Azure uygulama hizmeti veya bir Azure sanal makine için hızlı bir şekilde uygulamaları dağıtmak için yayımlama aracını kullanabilirsiniz. Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Yayımla**. Yayımla iletişim kutusunda seçin **Microsoft Azure App Service** veya **Microsoft Azure sanal makineleri**ve yapılandırma adımlarını izleyin.

    ![Azure uygulama hizmeti seçin](../deployment/media/quickstart-publish-azure.png "Azure uygulama hizmeti seçin")

    Bir Azure sanal makinesine yayımlamak için sağa kaydırın ve seçin **Microsoft Azure sanal makineleri**.

    Hızlı bir giriş için bkz [Azure Yayımla](quickstart-deploy-to-azure.md). Ayrıca bkz [ASP.NET Core uygulama için Azure yayımlama](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs). Git kullanarak dağıtım için bkz: [ASP.NET Core Azure Git ile sürekli dağıtımını](/aspnet/core/publishing/azure-continuous-deployment).

    > [!NOTE]
    > Zaten bir Azure hesabınız yoksa, şunları yapabilirsiniz [burada oturum](https://azure.microsoft.com/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=doc&utm_campaign=visualstudio).

- Diğer **Azure Hizmetleri**: belirli bkz [Azure hizmeti](/azure/#pivot=products) Visual Studio tarafından desteklenen farklı dağıtım seçenekleri için belgeleri.

### <a name="publish-to-microsoft-store"></a>Microsoft Mağazası'na yayımlamak

Visual Studio'dan dağıtım Microsoft Store için uygulama paketleri oluşturabilirsiniz.

- **UWP**: uygulamanızı paketleme ve menü öğelerini kullanarak dağıtın. Daha fazla bilgi için bkz: [Visual Studio kullanarak bir UWP uygulaması paketini](/windows/uwp/packaging/packaging-uwp-apps).

    ![Uygulama paketi oluşturma](../deployment/media/feature-tour-create-app-package.jpg)

- **Windows Masaüstü**: Microsoft Masaüstü köprüsü kullanarak Visual Studio 2017 sürüm 15.4 başlangıç Store dağıtabilirsiniz. Bunu yapmak için bir Windows Uygulama paketleme projesi oluşturarak başlayın. Daha fazla bilgi için bkz: [Microsoft Store (Masaüstü köprüsü) bir masaüstü uygulamasının paketini](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net).

    ![Masaüstü köprüsü](../deployment/media/feature-tour-desktop-bridge.png)

### <a name="create-an-installer-package-windows-client"></a>Bir yükleyici paketi (Windows istemcisi) oluşturun.

- Bir MSI tabanlı WiX yükleyici kullanılarak oluşturulabilir [WiX Toolset Visual Studio 2017 uzantısı](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).

- [InstallShield](https://www.flexerasoftware.com/producer/products/software-installation/installshield-software-installer/tab/requirements) Flexera yazılımlardan Visual Studio 2017 (desteklenmiyor Community Edition) kullanılabilir. InstallShield Limited Edition artık Visual Studio ile eklenmiştir ve Visual Studio 2017 içinde desteklenmeyen unutmayın; danışın [Flexera yazılım](http://learn.flexerasoftware.com/content/IS-EVAL-InstallShield-Limited-Edition-Visual-Studio) gelecekteki kullanılabilirliği hakkında.

- Kurulum projesi (vdproj) oluşturmak istiyorsanız, yükleme [Visual Studio 2017 yükleyici projeleri uzantısı](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.MicrosoftVisualStudio2017InstallerProjects#overview).

- Önyükleyici bilinen bir genel yükleyici yapılandırarak Masaüstü uygulamaları için önkoşul bileşenlerini yükleyebilirsiniz. Daha fazla bilgi için bkz: [Uygulama dağıtımının önkoşulları](../deployment/application-deployment-prerequisites.md).

### <a name="deploy-to-test-lab"></a>Laboratuvar test etmek için dağıtma

Daha karmaşık geliştirme ve sınama sanal ortamlar uygulamalarınıza dağıtarak etkinleştirebilirsiniz. Daha fazla bilgi için bkz: [bir laboratuvar ortamında Test](../test/lab-management/using-a-lab-environment-for-your-application-lifecycle.md).

### <a name="devops-deployment"></a>DevOps dağıtımı

Bir ekip ortamında uygulamanızı sürekli dağıtımını etkinleştirmek için Visual Studio Team Services (VSTS) kullanabilirsiniz. Daha fazla bilgi için bkz: [derleme ve sürüm](/vsts/build-release/index) ve [Azure'a Dağıt](/vsts/deploy-azure/index).

### <a name="deployment-for-other-app-types"></a>Diğer uygulama türleri için dağıtım

| Uygulama türü | Dağıtım Senaryosu | Bağlantı |
| --- | --- | --- |
| **Office uygulaması** | Visual Studio'da Office için bir eklenti yayımlayabilirsiniz. | [Dağıtma ve yayımlama için Office Eklentisi](https://dev.office.com/docs/add-ins/publish/publish) |
| **WCF veya OData hizmeti**  | Bir web sunucusuna dağıtmak WCF RIA services diğer uygulamaları kullanabilir. | [Geliştirme ve WCF Veri Hizmetleri dağıtma](/dotnet/framework/data/wcf/developing-and-deploying-wcf-data-services) |
| **LightSwitch** | LightSwitch Visual Studio 2017 içinde artık desteklenmez, ancak hala Visual Studio 2015 ve daha önce dağıtılabilir. | [LightSwitch uygulamalarını dağıtma](http://msdn.microsoft.com/Library/4818d933-295c-4ecc-9148-7ad9ca28dcdb) | 

