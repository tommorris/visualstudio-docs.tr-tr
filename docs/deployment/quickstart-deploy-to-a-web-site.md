---
title: Bir Web sitesine - Visual Studio yayımlama | Microsoft Docs
ms.custom: ''
ms.date: 11/22/2017
ms.technology:
- vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
ms.assetid: fc82b1f1-d342-4b82-9a44-590479f0a895
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 43b6bacc45d78d1d246f6a91d13549ccc96b276a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="publish-a-web-app-or-a-net-core-app-to-a-web-site-using-the-visual-studio-publish-tool"></a>Visual Studio yayımlama Aracı'nı kullanarak bir web sitesi için bir web uygulaması veya .NET Core uygulama yayımlama

Kullanabileceğiniz **Yayımla** ASP.NET uygulamaları bir Web sitesine yayımlamak için aracı.

ASP.NET, ASP.NET Core, .NET Core ve Visual Studio'da Python uygulamalar için şu adımları uygulayın. Node.js için adımları desteklenmektedir, ancak kullanıcı arabirimi farklıdır.

## <a name="create-a-new-project"></a>Yeni bir proje oluşturma 

1. Visual Studio'da, **Dosya > Yeni proje**.

1. Altında **Visual C#** veya **Visual Basic**, seçin **Web**ve ardından Orta bölmede ya da **ASP.NET Web uygulaması (.NET Framework)**veya (C# yalnızca) **ASP.NET çekirdek Web uygulaması**ve ardından **Tamam**.

1. Seçin **MVC**, olduğundan emin olun **doğrulaması yok** seçilir ve ardından **Tamam**.

1. Gibi bir ad yazın **mywebapp şeklindedir** tıklatıp **Tamam**.

    Visual Studio projesi oluşturur.

1. Seçin **Yapı > Yapı çözümü** Projeyi derlemek için.

## <a name="publish-to-a-web-site"></a>Bir web sitesi için yayımlama

1. Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Yayımla**.

    ![Seçin yayımlama](../deployment/media/quickstart-publish-aspnet.png "seçin yayımlama")

1. İçinde **Yayımla** bölmesinde seçin **IIS, FTP, vb**.

    ![IIS, FTP, vb.'ı seçin.](../deployment/media/quickstart-publish-iis-ftp.png "IIS seçin, FTP, vs.")

1. Tıklatın **yayımlama**.

    Profil yayımlama Ayarları iletişim kutusu açılır.

    ![Klasörü seçin](../deployment/media/quickstart-publish-settings-web.png "klasörü seçin")

1. İçinde **yayımlama yöntemi** alanında, aşağıdaki gibi bir yöntem seçin **Web dağıtımı** veya **FTP**.

    Gördüğünüz ayarları sonraki yayımlama yönteminize karşılık gelir.

1. Yayımlama yöntemi için gereken ayarları yapılandırın ve tıklatın **bağlantıyı doğrula**.

    Sunucu veya hedef kullanılabilir ve ayarlarınızın doğru olduğunu, bağlantı belirten bir ileti doğrulanır ve yayımlamaya hazır görürsünüz.

    ![Bağlantınızı doğrulama](../deployment/media/quickstart-publish-web-deploy.png "bağlantınızı doğrulama")

1. Diğer dağıtım ayarlarını yapılandırmak istiyorsanız, **ayarları**.

    Hata ayıklama veya yayın bir yapılandırma dağıtmanız ve ardından gibi seçeneklerini yapılandırabilirsiniz **kaydetmek**. Uzaktan hata ayıklama yaptığınız, hata ayıklama yapılandırmasını gereklidir.

1. Yayımlamak için tıklatın **Yayımla**.

    Çıktı penceresi dağıtımının ilerleme durumunu ve sonuçlarını gösterir.

## <a name="next-steps"></a>Sonraki adımlar

- [IIS’ye ASP.NET dağıtma](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)
