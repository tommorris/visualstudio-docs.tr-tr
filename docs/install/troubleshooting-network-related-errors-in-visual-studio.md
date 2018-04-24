---
title: Yüklediğinizde veya Visual Studio kullandığınızda ağ ile ilgili sorun giderme
description: Yüklediğinizde veya bir güvenlik duvarı veya proxy sunucunun Visual Studio'yu kullanma karşılaşabileceğiniz ağ veya proxy ilgili hataları çözümler bulabilirsiniz.
ms.custom: ''
ms.date: 02/12/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: troubleshooting
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
- list of domains, locations, URLs, Visual Studio
- proxy errors, Visual Studio
ms.assetid: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 41fed015f4ad80c3c3b74bc77ea3b9cc6ed8eb18
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="troubleshooting-network-related-errors-when-you-install-or-use-visual-studio"></a>Yüklediğinizde veya Visual Studio kullandığınızda ağ ile ilgili sorun giderme

Yüklediğinizde veya bir güvenlik duvarı veya proxy sunucunun Visual Studio'yu kullanma karşılaşabileceğiniz en tipik ağ veya proxy ilgili hataları biz çözümleri açıyor.

## <a name="error-proxy-authorization-required"></a>Hata: "Proxy kimlik doğrulaması gerekli"

Bu hata genellikle kullanıcılar bir proxy sunucu üzerinden Internet'e bağlı ve proxy sunucusu için bazı ağ kaynaklarına Visual Studio yapar çağrıları engeller oluşur.

### <a name="to-fix-this-proxy-error"></a>Bu proxy hatayı düzeltmek için

- Visual Studio'yu yeniden başlatın. Proxy kimlik doğrulaması iletişim kutusu görünür. İletişim kutusunda istendiğinde, kimlik bilgilerinizi girin.

- Visual Studio'yu yeniden başlatmayı sorunu çözmezse, proxy sunucusu için http kimlik bilgileri istenmez olabilir:&#47;&#47;go.microsoft.com adresleri ancak bunu yapar &#42;. visualStudio.com adresleri. Bu sunucular için Visual Studio tüm oturum açma senaryoları engellemesini kaldırmak için aşağıdaki URL'ler uygulamaları güvenilir listeye almayı göz önünde bulundurun:

    - &#42;. windows.net

    - &#42;.microsoftonline.com

    - &#42;. visualstudio.com

    - &#42;. microsoft.com

    - &#42;. live.com

- Aksi takdirde http kaldırabilirsiniz:&#47;&#47;go.microsoft.com adres beyaz liste böylece http için proxy kimlik doğrulaması iletişim kutusu görüntülenir:&#47;&#47;go.microsoft.com adresi ve Visual Studio olduğunda sunucu uç noktaları yeniden.

    VEYA

- Varsayılan kimlik bilgilerinizi proxy ile kullanmak istiyorsanız, aşağıdaki eylemleri gerçekleştirebilirsiniz:

    1. Bul **devenv.exe.config** (devenv.exe yapılandırma dosyası) içinde: **%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE** veya **% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE**.

    1. Yapılandırma dosyasında bulmak `<system.net>` engelleme ve sonra bu kodu ekleyin:

        ```xml
        <defaultProxy enabled="true" useDefaultCredentials="true">
            <proxy bypassonlocal="True" proxyaddress=" HYPERLINK "http://<yourproxy:port#" http://<yourproxy:port#>"/>
        </defaultProxy>
        ```

        Ağınızda için doğru proxy adresi eklemelisiniz `proxyaddress="<http://<yourproxy:port#>`.

    VEYA

- ' Ndaki yönergeleri de izleyebilirsiniz [doğrulanmış bir Web Proxy bağlanma](http://blogs.msdn.com/b/rido/archive/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy.aspx) nasıl proxy kullanmanıza olanak sağlayacak kodu ekleneceğini gösterir blog yayını.

## <a name="error-the-underlying-connection-was-closed"></a>Hata: "arka plandaki bağlantı kesildi"

Bir güvenlik duvarı olan özel bir ağda Visual Studio kullanıyorsanız, Visual Studio bazı ağ kaynaklarına bağlanmak mümkün olmayabilir. Bu kaynaklar, oturum açma ve lisans, NuGet ve Azure Hizmetleri için Visual Studio Team Services (VSTS) içerebilir. Visual Studio bu kaynaklardan biri bağlanamazsa, aşağıdaki hata iletisini görebilirsiniz:

  **Temel alınan bağlantı kapatıldı: Gönder beklenmeyen bir hata oluştu**

Visual Studio, ağ kaynaklarına bağlanmak için Aktarım Katmanı Güvenliği (TLS) 1.2 protokolünü kullanır. Visual Studio TLS 1.2 kullandığı durumlarda bazı özel ağlar üzerindeki güvenlik gereçlerinin bazı sunucu bağlantılarını Engellemesi.

### <a name="to-fix-this-connection-error"></a>Bu bağlantı hatayı düzeltmek için

Aşağıdaki URL'ler için bağlantılar sağlar:

- https:&#47;&#47;management.core.windows.net

- https:&#47;&#47;app.vssps.visualstudio.com

- https:&#47;&#47;login.microsoftonline.com

- https:&#47;&#47;login.live.com

- https:&#47;&#47;go.microsoft.com

- https:&#47;&#47;graph.windows.net

- https:&#47;&#47;app.vsspsext.visualstudio.com

- &#42;. azurewebsites.net (Azure bağlantıları için)

- &#42;. visualstudio.com

- CDN.vsassets.io (ana içerik teslim ağı veya CDN, içerik)

- &#42;. gallerycdn.vsassets.io (ana bilgisayar VSTS uzantıları)

- static2.sharepointonline.com (Visual Studio yazı tipleri gibi Office UI doku paketi kullanır ana bilgisayar kaynakları)

- &#42;. nuget.org (NuGet bağlantılar için)

 > [!NOTE]
 > Özel olarak sahip olunan NuGet sunucu URL'leri bu listede dahil. % APPData%\Nuget\NuGet.Config kullanmakta olduğunuz NuGet sunucularını denetleyebilirsiniz.

## <a name="get-support"></a>Destek alma

Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımları yükleme hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:

* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunlarını izlemek ve yanıtlar bulmak [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/).
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio). (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Studio’yu bir güvenlik duvarı veya ara sunucusunun arkasına yükleme ve burada kullanma](install-and-use-visual-studio-behind-a-firewall-or-proxy-server.md)
* [Visual Studio Yönetici Kılavuzu](visual-studio-administrator-guide.md)
* [Visual Studio 2017 yükleyin](install-visual-studio.md)
