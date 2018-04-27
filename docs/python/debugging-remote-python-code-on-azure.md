---
title: Uzaktan hata ayıklama Python ile Azure
description: Visual Studio bir Python uygulaması, uzaktan hata ayıklama için kullanılacak bir Azure uygulama hizmeti yapılandırmak nasıl.
ms.date: 07/12/2017
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 11a624ec6582e5e07e51de6d4ab29b84dc53d4a1
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2018
---
# <a name="remotely-debugging-python-code-on-azure"></a>Azure üzerinde uzaktan hata ayıklama Python kodu

[Visual Studio'da Python desteği](installing-python-support-in-visual-studio.md) uzaktan hata ayıklama Azure uygulama hizmeti üzerinde çalışan Python kodu özelliğini içerir. Visual Studio hata ayıklayıcısı Protokolü HTTP üzerinden kullanıma sunan bir proxy sağlayan şekilde basit uzaktan hata ayıklama aksine, bu senaryonun hedef bilgisayarda TCP üzerinden doğrudan erişilebilir değil. Web şablonu kullanılarak otomatik olarak oluşturulan projeleri bu proxy oluşturulan yapılandırma `web.debug.config` dosya. Uzaktan hata ayıklama de etkinleştirilir [Azure uygulama hizmeti yayımlamayı] açıklandığı gibi bir hata ayıklama yapılandırması proje yayımladığınızda (publishing-python-web-applications-to-azure-from-visual-studio.md.

Uygulama hizmetiniz için Azure uzaktan hata ayıklama web yuvalarını kullandığından, yuva etkinleştirilmelidir [Azure portal](https://portal.azure.com) giderek **ayarlar > Uygulama ayarları** ve kapatma  **Genel Ayarlar > Web yuvaları** için **üzerinde**, ardından seçerek **kaydetmek** değişikliği uygulamak için. (Unutmayın **hata ayıklama** ayarları Python hata ayıklama için uygulanmaz.)

![Azure portalında Web yuvalarını etkinleştirme](media/azure-remote-debugging-enable-web-sockets.png)

Projenizi düzgün bir şekilde dağıtıldıktan sonra etkin web yuvalarını iliştirebilirsiniz uygulama hizmetinden için **Sunucu Gezgini** Visual Studio'da (**Görünüm > Sunucu Gezgini**). Sitenizi altında bulun **Azure > uygulama hizmeti** ve geçerli kaynak grubu, sağ tıklatın ve seçin **Attach hata ayıklayıcısı (Python)**. ( **Attach hata ayıklayıcı** komutu, IIS altında çalışan .NET uygulamaları için geçerlidir ve yalnızca Python uygulamanızı yanı sıra, barındırmayı .NET kod durumlarda kullanışlıdır.)

Visual Studio alabilir, doğrudan ekleme yönergeleri kümesine doğrudan aşağıda açıklandığı gibi [Sunucu Gezgini ekleme](#attaching-without-server-explorer). Görmüyorsanız, **Attach hata ayıklayıcısı (Python)** komut veya Visual Studio başarısız sitenize eklemek için bkz: [sorun giderme Azure uzaktan hata ayıklama](debugging-remote-python-code-on-azure-troubleshooting.md).

Ekleme başarılı olursa, Visual Studio hata ayıklayıcısı görünümüne geçirir. Araç gibi ayıklanacak işlemi gösteren bir `wss://` URI:

![Bir Azure uygulama hizmeti Web sitesi hata ayıklama](media/azure-remote-debugging-attached.png)

Bağlandıktan sonra hata ayıklama deneyimini genellikle birkaç kısıtlamalar hata ayıklama normal uzak aynıdır. Özellikle, gelen istekleri işleyen ve bunları Python kodu Fastcgı aracılığıyla temsilciler IIS web sunucusu 90 saniye olarak varsayılan olarak istek işleme için bir zaman aşımı vardır. İstek işleme (örneğin, bir kesme noktasında duraklatıldıktan işlemi) nedeniyle bu zaman aşımından uzun sürüyorsa, IIS hata ayıklama oturumu sona erdirme işlemi sonlandırır. 

## <a name="attaching-without-server-explorer"></a>Sunucu Gezgini ekleme

Hata ayıklayıcı doğrudan App Service'e eklemek için Visual Studio sitenizde dağıtır WebSocket proxy bilgileri sayfasında verilen yönergeleri izleyin `<site_url>/ptvsd` gibi `ptvsdemo.azurewebsites.net/ptvsd`. Bu sayfa ayrıca ziyaret proxy doğru şekilde yapılandırıldığını doğrular:

![Azure uzaktan hata ayıklama proxy bilgileri sayfası](media/azure-remote-debugging-proxy-info-page.png)

Belirtildiği gibi gizli anahtarından kullanarak bir URL oluşturması `web.debug.config`, projenizin yayımlanan her zaman yeniden. Bu dosya, Çözüm Gezgini'nde varsayılan olarak gizlidir ve projenizde dahil değil, bu nedenle tüm dosyaları göster ya da ayrı bir düzenleyicide açın. Dosyayı açtıktan sonra adlı appSetting değerinde Ara `WSGI_PTVSD_SECRET`:

![Bir Azure uygulama hizmeti hata ayıklayıcı uç belirleme](media/azure-remote-debugging-secret.png)

Şu an ayarlamalısınız formunda URL `wss://<secret>@<site_name>.azurewebsites.net/ptvsd` burada değiştirdiğiniz &lt;gizli&gt;ve &lt;site_name&gt; , belirli değerleri içeren dizesinde.

Hata ayıklayıcı eklemek için seçin **hata ayıklama > ekleme işlemi için**seçin **Python uzaktan hata ayıklama** içinde **aktarım** açılan listesinde, URL'de girin  **Niteleyici textbox**, ve Enter tuşuna basın. Visual Studio için uygulama hizmeti başarıyla bağlanabiliyorsa listeden tek bir Python işlemi gösterilmektedir. Seçin ve ardından **Attach** hata ayıklamayı başlatmak için:

![Bir Azure web sitesi eklemek için işlem iletişim kutusuna Attach kullanma](media/azure-remote-debugging-manual-attach.png)
