---
title: Azure App Service’e yayımlama
ms.custom: ''
ms.date: 06/22/2018
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
ms.openlocfilehash: 3d15cc293f2b2b22b63e0af202bfcee8afa2cf13
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756002"
---
# <a name="publish-a-web-app-to-azure-app-service-using-visual-studio"></a>Visual Studio kullanarak Azure App Service için web uygulaması yayımlama

Kullanabileceğiniz **Yayımla** Azure uygulama hizmeti ya da Azure App Service (kapsayıcıları kullanma) Linux ASP.NET, ASP.NET Core, Node.js ve .NET Core uygulamaları yayımlamak için aracı. Python uygulamaları için adımları izleyin [Azure App Service'te yayımlama Python -](../python/publishing-python-web-applications-to-azure-from-visual-studio.md).

[!INCLUDE [quickstart-prereqs-azure](includes/quickstart-prereqs-azure.md)]

## <a name="publish-to-azure-app-service"></a>Azure App Service’e yayımlama

1. Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Yayımla** (veya **yapı** > **Yayımla** menü öğesi).

    ![Çözüm Gezgini'nde proje bağlam menüsünde Yayımla komutunu](../deployment/media/quickstart-publish.png "seçin yayımlama")

1. Tüm yayımlama profillerini daha önce yapılandırdıysanız **Yayımla** bölmesinde görünür, hangi servis talebi Seç **yeni profil oluşturmak**.

1. İçinde **yayımlama hedefi çekme** iletişim kutusunda, seçin **uygulama hizmeti**.

    ![Azure uygulama hizmeti seçin](../deployment/media/quickstart-publish-azure.png "Azure uygulama hizmeti seçin")

1. Seçin **yayımlama**. **App Service Oluştur** iletişim kutusu görüntülenir. Gerekirse, ardından varsayılan uygulama hizmet ayarlarını alanları doldurmak varsa, Azure hesabınızla oturum açın.

    ![Uygulama hizmeti oluşturma](../deployment/media/quickstart-publish-settings-app-service.png "Azure uygulama hizmeti oluşturma")

1. Seçin **oluşturma**. Visual Studio Azure uygulama hizmetiniz için uygulamayı dağıtır ve web uygulaması tarayıcınızda yükler. Proje Özellikleri **Yayımla** site URL'sini ve diğer ayrıntıları bölmesi gösterir.

    ![Bir profili Özet gösteren özelliği bölmesi yayımlama](../deployment/media/quickstart-publish-app-service-summary.png)

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıç Azure'a dağıtımı için bir yayımlama profili oluşturmak için Visual Studio kullanmayı öğrendiniz. Ayrıca bir yayımlamayı yapılandırabilirsiniz alarak profili Azure App Service ayarlarını yayımlayın.

> [!div class="nextstepaction"]
> [Yayımlama ayarlarını içeri aktarma ve Azure’a dağıtma](tutorial-import-publish-settings-azure.md)
