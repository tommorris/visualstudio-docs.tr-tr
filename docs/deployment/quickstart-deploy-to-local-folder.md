---
title: Yerel bir klasöre - Visual Studio dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 05/08/2018
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
ms.openlocfilehash: 48c9e38a0e3a1bcc5a12ed764c43747b27a5e303
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36283370"
---
# <a name="deploy-a-web-app-or-net-core-app-to-a-local-folder-using-the-visual-studio-publish-tool"></a>Bir web uygulaması veya .NET Core uygulama Visual Studio yayımlama aracını kullanarak yerel bir klasöre dağıtma

Kullanabileceğiniz **Yayımla** yerel bir klasöre uygulamanızı yayımlamak için aracı.

ASP.NET, ASP.NET Core, .NET Core ve Visual Studio'da Python uygulamalar için şu adımları uygulayın. Node.js için adımları desteklenmektedir, ancak kullanıcı arabirimi farklıdır.

## <a name="prerequisites"></a>Önkoşullar

* Visual Studio 2017 yüklü olması gerekir ve. **NET masaüstü geliştirme** iş yükü ve. **NET çekirdek** iş yükü.

    Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

## <a name="create-a-new-project"></a>Yeni bir proje oluşturma

1. Visual Studio'da, **dosya** > **yeni proje**.

1. Altında **Visual C#** veya **Visual Basic**, seçin **.NET Core**ve ardından, Orta bölmede **konsol uygulaması (.NET Core)**.

1. Gibi bir ad yazın **MyLocalApp** tıklatıp **Tamam**.

    Visual Studio projesi oluşturur.

## <a name="deploy-to-a-local-folder"></a>Yerel klasöre dağıtma

1. Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Yayımla**.

    ![Seçin yayımlama](../deployment/media/quickstart-publish.png "seçin yayımlama")

1. Tüm yayımlama profillerini daha önce yapılandırdıysanız **Yayımla** bölmesinde görünür. Tıklatın **yeni profil oluşturmak**.

1. İçinde **yayımlama hedefi çekme** iletişim kutusunda, seçin **klasörü**.

    ![Klasörü seçin](../deployment/media/quickstart-publish-folder.png "klasörü seçin")

1. Bir yol girin veya ' **Gözat** bir yerel klasöre gidin.

1. Tıklatın **yayımlama**.

    Visual Studio projesi oluşturur ve belirtilen klasöre yayımlar.

    Yayımla bölmesini bir profili özetini gösterir.

1. Dağıtım ayarlarını yapılandırmak için tıklatın **ayarları** Özet profilinde.

    ![Profil ayarları](../deployment/media/quickstart-profile-settings.png "profil ayarları")

1. Hata ayıklama veya yayın bir yapılandırma dağıtmanız ve ardından gibi seçeneklerini yapılandırın **kaydetmek**.

1. Yeniden yayımlamak için tıklatın **Yayımla**.

İstediğiniz şekilde yayımlanan dosyalarında dağıtın. Örneğin, bir ZIP dosyası paketini, basit Kopyala komutunu kullanın veya tercih ettiğiniz herhangi bir yükleme paketi ile dağıtabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- [Yayımla aracı ile .NET Core Uygulaması dağıtma](/dotnet/core/deploying/deploy-with-vs?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- [Bir masaüstü uygulamasını Microsoft Store için paketleme (Masaüstü Köprüsü)](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- (.NET) [.NET Framework ve uygulamaları Dağıt...](/dotnet/framework/deployment/)
