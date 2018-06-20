---
title: Azure App Service'te - Visual Studio yayımlama | Microsoft Docs
ms.custom: ''
ms.date: 11/22/2017
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
ms.assetid: fc82b1f1-d342-4b82-9a44-590479f0a895
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- azure
ms.openlocfilehash: f28de642d6a1f4f9071099593f990c6197ed34ec
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36234757"
---
# <a name="publish-an-aspnet-or-aspnet-core-app-to-azure-app-service-using-visual-studio"></a>Visual Studio kullanarak Azure App Service için ASP.NET veya ASP.NET Core uygulama yayımlama

Kullanabileceğiniz **Yayımla** Azure App Service ASP.NET, ASP.NET Core, Python, Node.js ve .NET Core uygulamaları yayımlamak için aracı.

Zaten bir Azure hesabınız yoksa, şunları yapabilirsiniz [burada oturum](https://azure.microsoft.com/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=doc&utm_campaign=visualstudio).

## <a name="prerequisites"></a>Önkoşullar

* Visual Studio 2017 yüklü olması gerekir ve **ASP.NET ve web geliştirme** iş yükü ve. **NET masaüstü geliştirme** iş yükü. .NET Core uygulama için gereksinim duyduğunuz. **NET çekirdek** iş yükü.

    Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

## <a name="create-a-new-project"></a>Yeni bir proje oluşturma 

1. Visual Studio'da, **dosya** > **yeni proje**.

1. Altında **Visual C#** veya **Visual Basic**, seçin **Web**ve ardından Orta bölmede ya da **ASP.NET Web uygulaması (.NET Framework)** veya (C# yalnızca) **ASP.NET çekirdek Web uygulaması**ve ardından **Tamam**.

1. Seçin **MVC** (veya tercih **Web uygulaması (Model-View-Controller)** .NET Core için), olduğundan emin olun **doğrulaması yok** seçilir ve ardından **Tamam** .

1. Gibi bir ad yazın **mywebapp şeklindedir** tıklatıp **Tamam**.

    Visual Studio projesi oluşturur.

1. Seçin **yapı** > **yapı çözümü** Projeyi derlemek için.

## <a name="publish-to-azure-app-service"></a>Azure App Service’e yayımlama

1. Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Yayımla**.

    ![Seçin yayımlama](../deployment/media/quickstart-publish-aspnet.png "seçin yayımlama")

1. Tüm yayımlama profillerini daha önce yapılandırdıysanız **Yayımla** bölmesinde görünür. Tıklatın **yeni profil oluşturmak**.

1. İçinde **yayımlama hedefi çekme** iletişim kutusunda, seçin **uygulama hizmeti**.

    ![Azure uygulama hizmeti seçin](../deployment/media/quickstart-publish-azure.png "Azure uygulama hizmeti seçin")

1. Tıklatın **yayımlama**.

    **App Service Oluştur** iletişim kutusu görüntülenir.

    ![Uygulama hizmeti oluşturma](../deployment/media/quickstart-publish-settings-app-service.png "Azure uygulama hizmeti oluşturma")
    
1. Visual Studio'ya imzalanmamışsa oturum açın ve ardından varsayılan uygulama hizmet ayarlarını alanları doldurun.

    Profil yayımlama Ayarları iletişim kutusu açılır.

    ![Klasörü seçin](../deployment/media/quickstart-publish-settings-web.png "klasörü seçin")

    Bu iletişim kutusunda, kullanmakta olduğunuz aboneliği seçin, seçin veya bir Azure kaynak grubu, vb. oluşturun.

1. **Oluştur**'u tıklatın.

    Visual Studio Azure uygulama hizmetiniz için uygulamayı dağıtır ve web uygulaması tarayıcınızda yükler.

    Özet olarak **Yayımla** bölmesinde, yeni Azure App Service için Site URL'sini bakın.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıç Azure'a dağıtımı için bir yayımlama profili oluşturmak için Visual Studio kullanmayı öğrendiniz. Ayrıca bir yayımlamayı yapılandırabilirsiniz alarak profili Azure App Service ayarlarını yayımlayın.

> [!div class="nextstepaction"]
> [Yayımlama ayarlarını içeri aktarma ve Azure’a dağıtma](tutorial-import-publish-settings-azure.md)
