---
title: Dağıtım özelliği turu
description: Visual Studio'dan uygulamaları dağıtmak için seçenekleriniz hakkında bilgi edinin.
ms.custom: mvc
ms.date: 11/26/2017
ms.technology: vs-ide-deployment
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
ms.openlocfilehash: e301131afc62b0564ca302adb9a079b42b52c5f8
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36234692"
---
# <a name="quickstart-first-look-at-deployment-in-visual-studio"></a>Hızlı Başlangıç: İlk Visual Studio'daki dağıtımı bakın

Bir uygulamayı, hizmeti ya da bileşeni dağıtarak bunu diğer bilgisayarlardaki, cihazlardaki, sunuculardaki ya da buluttaki yükleme için dağıtmış olursunuz. İhtiyacınız olan dağıtım türü için uygun yöntemi Visual Studio'da seçebilirsiniz. (Burada açıklanmamaktadır diğer dağıtım araçları komut satırı dağıtım veya NuGet gibi pek çok uygulama türlerini destekler.)

Adım adım dağıtım yönergeleri için bkz. Bir web uygulaması dağıtma ve en iyi dağıtım seçeneği Visual Studio'dan karar vermek için daha ayrıntılı bilgi ihtiyacınız varsa bkz [hangi yayımlama seçeneklerini benim için en uygun?](../ide/not-in-toc/web-publish-options.md).

## <a name="deploy-to-local-folder"></a>Yerel bir klasöre dağıtma

Yerel bir klasöre dağıtımına genellikle sınama veya başka bir aracı son dağıtım için kullanılacak bir aşamalı dağıtımına başlamak için kullanılır.

- **ASP.NET**, **ASP.NET Core**, **Node.js**, **Python**, ve. **NET çekirdek**: yerel bir klasöre dağıtmak için yayımlama Aracı'nı kullanın. Kullanılabilir seçenekler, uygulama türüne bağlıdır. Çözüm Gezgini'nde, projenize sağ tıklayın ve seçin **Yayımla**. (Daha önce tüm yayımlama profillerini yapılandırdıysanız, ardından'ı tıklatmalısınız **yeni profil oluşturmak**.) Ardından, seçin **klasörü**. Daha fazla bilgi için bkz: [bir yerel klasöre dağıtma](quickstart-deploy-to-local-folder.md).

    ![Seçin yayımlama](../deployment/media/quickstart-publish.png)

- **Visual C++ çalışma zamanı**: yerel dağıtım veya statik bağlama kullanarak Visual C++ çalışma zamanı dağıtabilirsiniz. Daha fazla bilgi için bkz: [dağıtma yerel Masaüstü uygulamaları (Visual C++)](/cpp/ide/deploying-native-desktop-applications-visual-cpp). 

## <a name="publish-to-azure"></a>Azure'a yayımlama

- **ASP.NET**, **ASP.NET Core**, **Python**, ve **Node.js**: Yayımla aracı hızlı bir şekilde Azure uygulama hizmeti veya bir Azure sanal uygulamaları dağıtmak için kullanabileceğiniz Makine. Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Yayımla**. (Daha önce tüm yayımlama profillerini yapılandırdıysanız, ardından'ı tıklatmalısınız **yeni profil oluşturmak**.) Yayımla iletişim kutusunda seçin **uygulama hizmeti** veya **Azure sanal makineleri**ve yapılandırma adımlarını izleyin.

    ![Azure uygulama hizmeti seçin](../deployment/media/quickstart-publish-azure.png "Azure uygulama hizmeti seçin")

    Visual Studio 2017 içinde sürüm 15.7, ASP.NET Core uygulamaları dağıtabilirsiniz **Linux için uygulama hizmeti**.

    Bir yayımlama profili Visual Studio için Azure App hizmetinden içe aktarma hakkında daha fazla bilgi için bkz: [yayımlama ayarlarını içeri aktarma ve Azure'a dağıtmak](../deployment/tutorial-import-publish-settings-azure.md).

    Hızlı bir giriş için bkz [Azure Yayımla](quickstart-deploy-to-azure.md). Ayrıca bkz [ASP.NET Core uygulama için Azure yayımlama](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs). Git kullanarak dağıtım için bkz: [ASP.NET Core Azure Git ile sürekli dağıtımını](/aspnet/core/publishing/azure-continuous-deployment).

    > [!NOTE]
    > Zaten bir Azure hesabınız yoksa, şunları yapabilirsiniz [burada oturum](https://azure.microsoft.com/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=doc&utm_campaign=visualstudio).

## <a name="publish-to-web-or-deploy-to-network-share"></a>Web'de Yayımla veya ağ paylaşımına dağıtma

- **ASP.NET**, **ASP.NET Core**, **Node.js**, ve **Python**: bir Web sitesine FTP veya Web dağıtımı kullanarak dağıtmak için yayımlama Aracı'nı kullanabilirsiniz. Daha fazla bilgi için bkz: [bir web sitesine dağıtma](quickstart-deploy-to-a-web-site.md).

    Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Yayımla**. (Daha önce tüm yayımlama profillerini yapılandırdıysanız, ardından'ı tıklatmalısınız **yeni profil oluşturmak**.) Yayımla aracında istediğiniz ve yapılandırma adımlarını izleyin seçeneğini belirleyin.

    ![IIS, FTP, vb. seçin.](../deployment/media/quickstart-publish-iis-ftp.png)

    Visual Studio'da yayımlama profilini içeri aktarma hakkında daha fazla bilgi için bkz: [yayımlama ayarlarını içeri aktarma ve IIS dağıtma](../deployment/tutorial-import-publish-settings-iis.md).

    Ayrıca, ASP.NET uygulamaları ve Hizmetleri, çeşitli diğer yollarla dağıtabilirsiniz. Daha fazla bilgi için bkz: [dağıtma ASP.NET web uygulamaları ve Hizmetleri](http://www.asp.net/aspnet/overview/deployment).

- **Visual C++ çalışma zamanı**: merkezi dağıtım kullanarak Visual C++ çalışma zamanı dağıtabilirsiniz. Daha fazla bilgi için bkz: [dağıtma yerel Masaüstü uygulamaları (Visual C++)](/cpp/ide/deploying-native-desktop-applications-visual-cpp). 

- **Windows Masaüstü** bir web sunucusuna veya ClickOnce dağıtımı kullanarak bir ağ dosya paylaşımı için bir Windows masaüstü uygulaması yayımlayabilirsiniz. Kullanıcılar, daha sonra uygulamayı tek bir tıklamayla yükleyebilir. Daha fazla bilgi için bkz: [ClickOnce kullanarak bir masaüstü uygulamasını dağıtmak](how-to-publish-a-clickonce-application-using-the-publish-wizard.md) ve [ClickOnce kullanarak yerel bir uygulama dağıtmak](/cpp/ide/clickonce-deployment-for-visual-cpp-applications).

## <a name="publish-to-microsoft-store"></a>Microsoft Mağazası'na yayımlamak

Visual Studio'dan dağıtım Microsoft Store için uygulama paketleri oluşturabilirsiniz.

- **UWP**: uygulamanızı paketleme ve menü öğelerini kullanarak dağıtın. Daha fazla bilgi için bkz: [Visual Studio kullanarak bir UWP uygulaması paketini](/windows/uwp/packaging/packaging-uwp-apps).

    ![Uygulama paketi oluşturma](../deployment/media/feature-tour-create-app-package.jpg)

- **Windows Masaüstü**: Microsoft Masaüstü köprüsü kullanarak Visual Studio 2017 sürüm 15.4 başlangıç Store dağıtabilirsiniz. Bunu yapmak için bir Windows Uygulama paketleme projesi oluşturarak başlayın. Daha fazla bilgi için bkz: [Microsoft Store (Masaüstü köprüsü) bir masaüstü uygulamasının paketini](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net).

    ![Masaüstü köprüsü](../deployment/media/feature-tour-desktop-bridge.png)

## <a name="deploy-to-a-device-uwp"></a>Bir aygıt (UWP) dağıtma

Bir cihazda test etmek için bir UWP uygulaması dağıtıyorsanız, bkz: [Visual Studio'da uzaktaki bir makinede çalıştırın UWP uygulamaları](../debugger/run-windows-store-apps-on-a-remote-machine.md).

## <a name="create-an-installer-package-windows-client"></a>Bir yükleyici paketi (Windows istemcisi) oluşturun.

Bir masaüstü uygulamasının karmaşık bir kurulum daha gerektirip gerektirmediğini [ClickOnce](how-to-publish-a-clickonce-application-using-the-publish-wizard.md) sağlayabilir bir yükleyici paketi, bir kurulum projesi ya da özel bir önyükleyici oluşturabilirsiniz.

- Bir MSI tabanlı WiX yükleyici kullanılarak oluşturulabilir [WiX Toolset Visual Studio 2017 uzantısı](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).

- [InstallShield](https://www.flexerasoftware.com/producer/products/software-installation/installshield-software-installer/tab/requirements) Flexera yazılımlardan Visual Studio 2017 (desteklenmiyor Community Edition) kullanılabilir. InstallShield Limited Edition artık Visual Studio ile eklenmiştir ve Visual Studio 2017 içinde desteklenmeyen unutmayın; danışın [Flexera yazılım](http://learn.flexerasoftware.com/content/IS-EVAL-InstallShield-Limited-Edition-Visual-Studio) gelecekteki kullanılabilirliği hakkında.

- Kurulum projesi (vdproj) oluşturmak istiyorsanız, yükleme [Visual Studio 2017 yükleyici projeleri uzantısı](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.MicrosoftVisualStudio2017InstallerProjects#overview).

- Önyükleyici bilinen bir genel yükleyici yapılandırarak Masaüstü uygulamaları için önkoşul bileşenlerini yükleyebilirsiniz. Daha fazla bilgi için bkz: [Uygulama dağıtımının önkoşulları](../deployment/application-deployment-prerequisites.md).

## <a name="deploy-to-test-lab"></a>Laboratuvar test etmek için dağıtma

Daha karmaşık geliştirme ve sınama sanal ortamlar uygulamalarınıza dağıtarak etkinleştirebilirsiniz. Daha fazla bilgi için bkz: [bir laboratuvar ortamında Test](../test/lab-management/using-a-lab-environment-for-your-application-lifecycle.md).

## <a name="devops-deployment"></a>DevOps dağıtımı

Bir ekip ortamında uygulamanızı sürekli dağıtımını etkinleştirmek için Visual Studio Team Services (VSTS) kullanabilirsiniz. Daha fazla bilgi için bkz: [derleme ve sürüm](/vsts/build-release/index) ve [Azure'a Dağıt](/vsts/deploy-azure/index).

## <a name="deployment-for-other-app-types"></a>Diğer uygulama türleri için dağıtım

| Uygulama türü | Dağıtım Senaryosu | Bağlantı |
| --- | --- | --- |
| **Office uygulaması** | Visual Studio'da Office için bir eklenti yayımlayabilirsiniz. | [Dağıtma ve yayımlama için Office Eklentisi](https://dev.office.com/docs/add-ins/publish/publish) |
| **WCF veya OData hizmeti**  | Bir web sunucusuna dağıtmak WCF RIA services diğer uygulamaları kullanabilir. | [Geliştirme ve WCF Veri Hizmetleri dağıtma](/dotnet/framework/data/wcf/developing-and-deploying-wcf-data-services) |
| **LightSwitch** | LightSwitch Visual Studio 2017 içinde artık desteklenmez, ancak hala Visual Studio 2015 ve daha önce dağıtılabilir. | [LightSwitch uygulamalarını dağıtma](http://msdn.microsoft.com/Library/4818d933-295c-4ecc-9148-7ad9ca28dcdb) | 

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, farklı uygulamalar için dağıtım seçeneklerini hızlı bir bakış sürdü. ASP.NET gibi bir web uygulaması dağıtıyorsanız, bazı Visual Studio'da kullanılabilir dağıtım seçenekleri hakkında daha ayrıntılı okuyun.

> [!div class="nextstepaction"]
> [Benim için en uygun Yayımlama seçenekleri nelerdir?](../ide/not-in-toc/web-publish-options.md)

