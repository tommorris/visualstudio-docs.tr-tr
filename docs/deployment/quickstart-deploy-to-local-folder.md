---
title: "Yerel bir klasöre - Visual Studio dağıtma | Microsoft Docs"
ms.custom: 
ms.date: 11/22/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: quickstart
helpviewer_keywords:
- deployment, local folder
ms.assetid: adb461c4-812a-4b8c-b2ab-96002379f6a9
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4e575a6d885b079c1c5afd0af6cbdadcd1d38d96
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="deploy-a-web-app-or-net-core-app-to-a-local-folder-using-the-visual-studio-publish-tool"></a>Bir web uygulaması veya .NET Core uygulama Visual Studio yayımlama aracını kullanarak yerel bir klasöre dağıtma

Kullanabileceğiniz **Yayımla** yerel bir klasöre uygulamanızı yayımlamak için aracı. 

ASP.NET, ASP.NET Core, .NET Core ve Visual Studio'da Python uygulamalar için şu adımları uygulayın. Node.js için adımları desteklenmektedir, ancak kullanıcı arabirimi farklıdır.

## <a name="create-a-new-project"></a>Yeni bir proje oluşturma 

1. Visual Studio'da, **Dosya > Yeni proje**.

1. Altında **Visual C#** veya **Visual Basic**, seçin **.NET Core**ve ardından Orta bölmede **konsol uygulaması (.NET Core)**.

1. Gibi bir ad yazın **MyLocalApp** tıklatıp **Tamam**.

    Visual Studio projesi oluşturur.

## <a name="deploy-to-a-local-folder"></a>Yerel bir klasöre dağıtma

1. Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Yayımla**.

    ![Seçin yayımlama](../deployment/media/quickstart-publish.png "seçin yayımlama")

1. İçinde **Yayımla** bölmesinde seçin **klasörü**.

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

- [Yayımla aracı ile .NET Core Uygulaması dağıtma](/dotnet/core/deploying/deploy-with-vs)
- [Bir masaüstü uygulamasını Microsoft Store için paketleme (Masaüstü Köprüsü)](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)
- (.NET) [.NET Framework ve uygulamaları dağıtma](/dotnet/framework/deployment/)
