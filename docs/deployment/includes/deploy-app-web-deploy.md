---
title: Web dağıtımı kullanarak dağıtma
description: Visual Studio'da Web Dağıtımı'nı kullanarak bir uygulamayı dağıtma
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: 4ef232e64f308699c73c60cbe5b155f1d4ebb725
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34794229"
---
Web Platformu Yükleyicisi'ni kullanarak Web dağıtımı yüklediyseniz, Visual Studio uygulamasından doğrudan dağıtabilirsiniz.

1. Yönetici ayrıcalıklarıyla Visual Studio'yu başlatın ve projeyi yeniden açın.

    Web Dağıtımı'nı kullanarak uygulamanızı dağıtmak için yönetici ayrıcalıkları gerekir.

1. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Yayımla**.

    Tüm yayımlama profillerini daha önce yapılandırdıysanız **Yayımla** bölmesinde görünür. Tıklatın **yeni bir profil**.

1. İçin **yayımlama hedefi seçin**seçin **IIS, FTP, vb.** tıklatıp **Yayımla**.

    ![RemoteDBG_Publish_IISl](../../debugger/media/remotedbg_iis_profile.png "RemoteDBG_Publish_IIS")

1. Düzeltme yapılandırma parametrelerini IIS ayarlarınızı girin.

    ![RemoteDBG_Publish_WebDeployl](../../debugger/media/remotedbg_iis_webdeploy_config.png "RemoteDBG_Publish_WebDeploy")

    Bir ana bilgisayar adı olarak doğrulamak çalıştığınızda çözmezse sonraki bölümlerinde bulunan adımları **Server** metin kutusunda, IP adresi deneyin. Dahil `http://` bir önek olarak **Server** alan.  İçinde 80 numaralı bağlantı noktasını kullandığınızdan emin olun **Server** metin kutusuna ve 80 numaralı bağlantı noktası ve bağlantı noktası 8172 Güvenlik Duvarı'nda açık olduğundan emin olun.

1. Seçin **doğrulamak**. Bağlantı Kur doğrulanırsa yayımlamayı deneyebilirsiniz.

1. Tıklatın **Yayımla** uygulamayı yayımlamak için.

    Çıktı sekmesi yayımlama başarılı olur ve tarayıcınızı uygulama açılır gösterir.

    Web dağıtımı söz bir hata alırsanız, Web dağıtımı yükleme adımlarını yeniden denetleyin ve doğru bağlantı noktalarının açık olduğundan emin olun (Web dağıtımı da gerektirir bağlantı noktasını sunucuda açık olması 8172).

    Uygulama başarıyla dağıtır ancak düzgün çalışmıyorsa, IIS yapılandırmanızı, ASP.NET yüklemenizi veya Web sitesi yapılandırması ile ilgili bir sorun olabilir. Windows Server için daha özel hata iletileri IIS Web sitesini açın ve önceki adımları yeniden denetleyin.
