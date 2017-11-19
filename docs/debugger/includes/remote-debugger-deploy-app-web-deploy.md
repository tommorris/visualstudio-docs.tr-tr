---
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.openlocfilehash: 27cff46f5a68ef28f247aa159a2b8be5db56b0fe
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
Web Platformu Yükleyicisi'ni kullanarak Web dağıtımı yüklediyseniz, Visual Studio uygulamasından doğrudan dağıtabilirsiniz.

1. Yönetici ayrıcalıklarıyla Visual Studio'yu başlatın ve projeyi yeniden açın.

    Web Dağıtımı'nı kullanarak uygulamanızı dağıtmak için yönetici ayrıcalıkları gerekir.

2. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Yayımla**.

3. İçin **yayımlama hedefi seçin**seçin **IIS, FTP, vb.** tıklatıp **Yayımla**.

    ![RemoteDBG_Publish_IISl](../media/remotedbg_iis_profile.png "RemoteDBG_Publish_IIS")

4. Düzeltme yapılandırma parametrelerini IIS ayarlarınızı girin.

    ![RemoteDBG_Publish_WebDeployl](../media/remotedbg_iis_webdeploy_config.png "RemoteDBG_Publish_WebDeploy")

    Bir ana bilgisayar adı olarak doğrulamak çalıştığınızda çözmezse sonraki bölümlerinde bulunan adımları **Server** metin kutusunda, IP adresi deneyin. Dahil `http://` bir önek olarak **Server** alan.  İçinde 80 numaralı bağlantı noktasını kullandığınızdan emin olun **Server** metin kutusuna ve bağlantı noktası 80 Güvenlik Duvarı'nda açık olduğundan emin olun.

6. Tıklatın **sonraki**, seçin bir **hata ayıklama** yapılandırması ve seçin **hedefteki ek dosyaları Kaldır** altında **yayımlama dosyası** Seçenekler.

    > [!NOTE]
    > Bir yayın yapılandırma seçerseniz yayımladığınızda, web.config dosyasında hata ayıklama devre dışı.

5. Tıklatın **önceki**ve ardından **doğrulama**. Bağlantı Kur doğrulanırsa yayımlamayı deneyebilirsiniz.

6. Tıklatın **Yayımla** uygulamayı yayımlamak için.

    Çıktı sekmesi yayımlama başarılı olur ve tarayıcınızı uygulama açılır gösterir.

    Web dağıtımı söz bir hata alırsanız, Web dağıtımı yükleme adımlarını yeniden denetleyin ve doğru bağlantı noktalarının açık olduğundan emin olun (Web dağıtımı da gerektirir bağlantı noktasını sunucuda açık olması 8172).

    Uygulama başarıyla dağıtır ancak düzgün çalışmıyorsa, IIS yapılandırmanızı, ASP.NET yüklemenizi veya Web sitesi yapılandırması ile ilgili bir sorun olabilir. Windows Server için daha özel hata iletileri IIS Web sitesini açın ve önceki adımları yeniden denetleyin.