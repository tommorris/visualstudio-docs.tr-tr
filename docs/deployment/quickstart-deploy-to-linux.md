---
title: Linux üzerinde App Service'e yayımlama
ms.custom: ''
ms.date: 07/23/2018
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- azure
ms.openlocfilehash: 9f79cef595b3a58426b596fc1019c59b801a02d5
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39252368"
---
# <a name="publish-an-aspnet-core-app-to-app-service-on-linux-using-visual-studio"></a>Visual Studio kullanarak Linux üzerinde App Service'e bir ASP.NET Core uygulaması yayımlama

Kullanabileceğiniz **Yayımla** Linux üzerinde Azure App Service'e ASP.NET Core uygulamaları yayımlamak için aracı.

Kullanarak Linux üzerinde App Service'e dağıtım **Yayımla** aracı Visual Studio 2017 sürüm 15.7 gerektirir.

[!INCLUDE [quickstart-prereqs-azure-linux](includes/quickstart-prereqs-azure-linux.md)]

## <a name="publish-to-app-service-on-linux"></a>Linux üzerinde App Service'e yayımlama

1. Çözüm Gezgini'nde projeye sağ tıklayıp seçin **Yayımla** (veya **derleme** > **Yayımla** menü öğesi).

    ![Çözüm Gezgini'nde proje bağlam menüsünde Yayımla komutunu](../deployment/media/quickstart-publish.png "seçin yayımlama")

1. Tüm yayımlama profilleri, daha önce yapılandırdıysanız **Yayımla** bölmesi görünür, büyük/küçük harf hangi seçin **yeni profil oluşturma**.

1. İçinde **yayımlama hedefi seçin** iletişim kutusunda **App Service Linux**.

    ![Azure uygulama hizmeti seçin](../deployment/media/quickstart-publish-linux.png "Azure uygulama hizmeti seçin")

1. Seçin **yayımlama**. **App Service Oluştur** iletişim kutusu görüntülenir. Gerekirse, ardından varsayılan uygulama hizmeti ayarlarını alanları doldurun, size Azure hesabıyla oturum açın.

    ![App Service Oluştur](../deployment/media/quickstart-publish-settings-app-service-linux.png "Azure App Service oluştur")

1. Seçin **oluşturma**. Visual Studio için Azure App Service uygulama dağıtır ve tarayıcınızda web uygulaması yükler. Proje özelliklerini **Yayımla** site URL'sini ve diğer ayrıntıları bölmesi gösterir.

    ![Yayımlama profili Özet gösteren özellik bölmesi](../deployment/media/quickstart-publish-app-service-summary.png)

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta Linux üzerinde App Service'e dağıtımı için bir yayımlama profili oluşturmak için Visual Studio kullanmayı öğrendiniz. Azure'ı kullanarak Linux için yayımlama hakkında daha fazla bilgi isteyebilirsiniz.

> [!div class="nextstepaction"]
> [Linux uygulama hizmeti](/azure/app-service/containers/app-service-linux-intro)
