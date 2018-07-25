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
ms.openlocfilehash: e0268c2e65cd08274c2267ad2a4969f6015cbaf4
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233753"
---
# <a name="publish-an-aspnet-core-app-to-app-service-on-linux-using-visual-studio"></a>Visual Studio kullanarak Linux üzerinde App Service'e bir ASP.NET Core uygulaması yayımlama

Kullanabileceğiniz **Yayımla** Linux üzerinde Azure App Service'e ASP.NET Core uygulamaları yayımlamak için aracı.

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
