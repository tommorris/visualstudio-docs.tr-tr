---
title: Yerel klasöre dağıtma
ms.custom: ''
ms.date: 06/22/2018
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, local folder
ms.assetid: adb461c4-812a-4b8c-b2ab-96002379f6a9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 517698aa2e042d74138579dae3633930b338cd61
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756281"
---
# <a name="deploy-an-app-to-a-local-folder-using-visual-studio"></a>Visual Studio kullanarak yerel bir klasöre uygulama dağıtmak

Kullanabileceğiniz **Yayımla** ASP.NET, ASP.NET Core, .NET Core ve Python uygulamaları bir yerel klasöre Visual Studio'dan yayımlamak için aracı. Node.js için adımları desteklenmektedir, ancak kullanıcı arabirimi farklıdır.

[!INCLUDE [quickstart-prereqs](includes/quickstart-prereqs.md)]

## <a name="deploy-to-a-local-folder"></a>Yerel klasöre dağıtma

1. Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Yayımla** (veya **yapı** > **Yayımla** menü öğesi).

    ![Çözüm Gezgini'nde proje bağlam menüsünde Yayımla komutunu](../deployment/media/quickstart-publish.png "seçin yayımlama")

1. Tüm yayımlama profillerini daha önce yapılandırdıysanız **Yayımla** bölmesinde görünür. Seçin **yeni profil oluşturmak**.

1. İçinde **yayımlama hedefi çekme** iletişim kutusunda, seçin **klasörü**.

    ![Yayımla hedef olarak yerel klasörü seç](../deployment/media/quickstart-publish-folder.png "Klasör Seç")

1. Bir yol girin veya seçin **Gözat** yerel klasörü belirtin.

1. Seçin **yayımlama**. Visual Studio projesi oluşturur ve belirtilen klasöre yayımlar. Proje Özellikleri **Yayımla** bölmesinde görünür, bir profil Özet gösterme.

    ![Bir profili Özet gösteren özelliği bölmesi yayımlama](../deployment/media/quickstart-publish-folder-summary.png)

1. Dağıtım ayarlarını yapılandırmak için seçin **yapılandırma** seçin ve Özet profilinde **ayarları** sekmesi.

    ![Profil ayarları](../deployment/media/quickstart-profile-settings.png "profil ayarları")

1. Hata ayıklama veya yayın bir yapılandırma dağıtmanız ve ardından gibi seçeneklerini yapılandırın **kaydetmek**.

1. Yeniden seçin **Yayımla**.

İstediğiniz şekilde yayımlanan dosyalarında dağıtın. Bunları paketini Örneğin, bir *.zip* dosya, bir basit Kopyala komutunu kullanın veya tercih ettiğiniz herhangi bir yükleme paketi ile birlikte dağıtın.

## <a name="next-steps"></a>Sonraki adımlar

- [Yayımla aracı ile .NET Core Uygulaması dağıtma](/dotnet/core/deploying/deploy-with-vs?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- [Bir masaüstü uygulamasını Microsoft Store için paketleme (Masaüstü Köprüsü)](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- (.NET) [.NET Framework ve uygulamaları dağıtma](/dotnet/framework/deployment/)
