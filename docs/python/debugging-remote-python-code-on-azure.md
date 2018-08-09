---
title: Azure uzaktan hata ayıklama ile Python
description: Visual Studio'yu bir Python uygulaması, uzaktan hata ayıklama için kullanılacak bir Azure uygulama hizmetini yapılandırma
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 1e3e70675901128ed6b8d118e54dc10ddee152a5
ms.sourcegitcommit: 96a6d1f16d06ca28d309d05b6e9fbd52f628cdbc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40008625"
---
# <a name="remotely-debug-python-code-on-azure"></a>Azure'da Python kodu uzaktan hata ayıklama

[Visual Studio'da Python desteği](installing-python-support-in-visual-studio.md) üzerinde Azure App Service'te çalışan bir Python kodu uzaktan hata ayıklama özelliği içerir. Visual Studio hata ayıklayıcı Protokolü HTTP üzerinden kullanıma sunan bir proxy sağlanılır basit uzaktan hata ayıklama aksine, bu senaryo hedef bilgisayarda TCP üzerinden doğrudan erişilebilir değil. Otomatik olarak Web şablonu kullanılarak oluşturulan projeler bu proxy oluşturulan yapılandırma *web.debug.config* dosya. Uzaktan hata ayıklama da etkindir yayımladığınızda, bir **hata ayıklama** sitesinde açıklandığı projenizin yapılandırmasını [Azure App Service'e yayımlama](publishing-python-web-applications-to-azure-from-visual-studio.md).

App service'inizin Azure uzaktan hata ayıklama web yuvalarını kullandığından, yuva etkinleştirilmelidir [Azure portalında](https://portal.azure.com) giderek **ayarları** > **uygulama ayarları**  ve kapatma **genel ayarlar** > **Web yuvaları** için **üzerinde**, ardından seçerek **Kaydet**değişikliği uygulamak için. (Unutmayın **hata ayıklama** ayarları Python hata ayıklama için uygulanmaz.)

![Azure portalında Web yuvalarını etkinleştirme](media/azure-remote-debugging-enable-web-sockets.png)

## <a name="attach-with-server-explorer"></a>Sunucu Gezgini ile ekleme

Projenizi düzgün şekilde dağıtıldığından ve web yuvaları, etkin, iliştirebileceği App Service'ten sonra **Sunucu Gezgini** Visual Studio'daki (**görünümü** > **SunucuGezgini**). Sitenizi altında bulun **Azure** > **App Service** ve uygun kaynak grubu, sağ tıklatın ve seçin **hata ayıklayıcısı ekleme (Python)**. ( **Hata ayıklayıcı iliştirmek** komut IIS altında çalışan .NET uygulamaları için olan ve yalnızca Python uygulamanızı yanı sıra, ortak sunuculuk .NET kodu kullanışlıdır.)

Visual Studio alabilir, doğrudan bir dizi doğrudan ekleme hakkında yönergeler için aşağıda açıklanan şekilde [ek sunucu Gezgini olmadan](#attach-without-server-explorer). Görmüyorsanız, **hata ayıklayıcısı ekleme (Python)** komut veya Visual Studio başarısız sitenize eklemek için bkz: [Python ve Azure için uzaktan hata ayıklama sorun giderici](debugging-remote-python-code-on-azure-troubleshooting.md).

İliştirme başarılı olursa, Visual Studio hata ayıklayıcı görünümüne geçer. Araç çubuğu gibi ayıklanan işlemin gösteren bir `wss://` URI'si:

![Bir Azure uygulama hizmeti Web sitesi hata ayıklama](media/azure-remote-debugging-attached.png)

Bağlandıktan sonra hata ayıklama deneyimini çoğunlukla bazı kısıtlamalar hata ayıklama normal uzak aynıdır. Özellikle, gelen istekleri işleyen ve Python kodu aracılığıyla Fastcgı devreder IIS web sunucusunu 90 saniye olarak varsayılan olarak istek işleme için bir zaman aşımı vardır. İstek işleme (örneğin, bir kesme noktasında duraklatıldıktan işlemi) nedeniyle bu zaman aşımı süresinden daha uzun sürerse, IIS, hata ayıklama oturumunu sona erdirme işlemi sonlandırır. 

## <a name="attach-without-server-explorer"></a>Sunucu Gezgini ekleme

App Service için doğrudan hata ayıklayıcıyı iliştirmek için Visual Studio sitenizde dağıtır WebSocket proxy bilgileri sayfasında yönergelerini izleyin  *\<site_url > / ptvsd* gibi  *ptvsdemo.azurewebsites.NET/ptvsd*. Bu sayfa ayrıca ziyaret proxy doğru şekilde yapılandırıldığını doğrular:

![Azure uzaktan hata ayıklama proxy'si bilgileri sayfası](media/azure-remote-debugging-proxy-info-page.png)

Belirtildiği gibi gizli kod kullanarak bir URL oluşturun *web.debug.config*, projenizi yayımlanan her zaman yeniden. Bu dosya varsayılan olarak gizlidir **Çözüm Gezgini** ve bu nedenle tüm dosyaları göster projeye dahil değil, veya ayrı bir düzenleyicide açın. Dosyayı açtıktan sonra adlı appSetting değerinde Ara `WSGI_PTVSD_SECRET`:

![Bir Azure App Service'te hata ayıklayıcı uç nokta belirleniyor](media/azure-remote-debugging-secret.png)

Şu an ayarlamalısınız biçiminde URL `wss://<secret>@<site_name>.azurewebsites.net/ptvsd` burada değiştirin &lt;gizli&gt; ve &lt;site_name&gt; , belirli değerleri içeren bir dize içinde.

Hata ayıklayıcıyı iliştirmek için seçin **hata ayıklama** > **iliştirme**seçin **Python uzaktan hata ayıklama** içinde **aktarım**açılır listesinde, URL'sini girin **niteleyicisi textbox**basın **Enter**. Visual Studio App Service'e başarıyla bağlantı kurabiliyorsanız, tek bir Python işlem listesinde gösterilir. Seçin ve ardından **iliştirme** hata ayıklamayı başlatmak için:

![Ek İliştir iletişim kullanarak bir Azure web sitesine iliştirin](media/azure-remote-debugging-manual-attach.png)
