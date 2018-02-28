---
title: "Azure App Service'te - Visual Studio yayımlama | Microsoft Docs"
ms.custom: 
ms.date: 11/22/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
ms.assetid: fc82b1f1-d342-4b82-9a44-590479f0a895
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- azure
ms.openlocfilehash: 52da1a2e618d9ececa1c8fd0d90a86e651cd7fde
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="publish-an-aspnet-or-aspnet-core-app-to-azure-app-service-using-visual-studio"></a>Visual Studio kullanarak Azure App Service için ASP.NET veya ASP.NET Core uygulama yayımlama

Kullanabileceğiniz **Yayımla** Azure App Service ASP.NET, ASP.NET Core, Python, Node.js ve .NET Core uygulamaları yayımlamak için aracı.

Zaten bir Azure hesabınız yoksa, şunları yapabilirsiniz [burada oturum](https://azure.microsoft.com/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=doc&utm_campaign=visualstudio).

## <a name="create-a-new-project"></a>Yeni bir proje oluşturma 

1. Visual Studio'da, **Dosya > Yeni proje**.

1. Altında **Visual C#** veya **Visual Basic**, seçin **Web**ve ardından Orta bölmede ya da **ASP.NET Web uygulaması (.NET Framework)**veya (C# yalnızca) **ASP.NET çekirdek Web uygulaması**ve ardından **Tamam**.

1. Seçin **MVC**, olduğundan emin olun **doğrulaması yok** seçilir ve ardından **Tamam**.

1. Gibi bir ad yazın **mywebapp şeklindedir** tıklatıp **Tamam**.

    Visual Studio projesi oluşturur.

1. Seçin **Yapı > Yapı çözümü** Projeyi derlemek için.

## <a name="publish-to-azure-app-service"></a>Azure App Service'te yayımlama

1. Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Yayımla**.

    ![Seçin yayımlama](../deployment/media/quickstart-publish-aspnet.png "seçin yayımlama")

1. İçinde **Yayımla** bölmesinde seçin **Microsoft Azure App Service**.

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

- [Bir ASP.NET Core uygulamayı Azure'a dağıtma](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs)
- [Git ile Azure’a sürekli ASP.NET Core dağıtımı](/aspnet/core/publishing/azure-continuous-deployment)
