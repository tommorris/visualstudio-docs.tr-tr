---
title: "Visual Studio'da Python için proje şablonları Web | Microsoft Docs"
ms.custom: 
ms.date: 07/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "11"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload: python
ms.openlocfilehash: 67132298bd8c6cf61027f01dab795f57b302b108
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="python-web-project-templates"></a>Python web projesi şablonları

Python Visual Studio Proje şablonları ve çeşitli çerçeveleri işlemek üzere yapılandırılmış bir hata ayıklama başlatıcısı aracılığıyla Bottle, Flask ve Django çerçeveleri geliştirme web projeleri destekler. Genel de kullanabilirsiniz **Web projesi** Piramit gibi diğer çerçeveler için şablon.

Visual Studio çerçeveleri kendilerini içermez. Projeye sağ tıklayıp seçerek ayrı olarak çerçeveler komutunu yüklemelisiniz **Python > yükleme/yükseltme framework...** .

Çalıştırdığınızda, bir şablondan oluşturulan bir proje (üzerinden erişilen gibi **Dosya > Yeni > Proje...** ) rastgele seçili yerel bağlantı noktası ile bir web sunucusu başlatan, hata ayıklama sırasında varsayılan tarayıcınızı açar ve Microsoft Azure yayımlama doğrudan sağlar.

![Yeni web projesi şablonları](media/template-web-new-project.png)

Bottle, Flask ve Django şablonları her başlangıç sitesi bazı sayfaları ve statik dosyaları içerir. Bu kodu çalıştırmak ve (burada bazı ayarları gereken ortamından elde edilebilir) sunucusu yerel olarak hata ayıklama yeterli olduğundan ve Microsoft Azure'a dağıtmak için (burada bir [WSGI uygulama](http://www.python.org/dev/peps/pep-3333/) nesnenin sağlanması gerekiyor).

Bir proje çerçeveye özel şablonu oluştururken, PIP kullanarak gerekli paketleri yüklemenize yardımcı olması için bir iletişim kutusu görüntülenir. Ayrıca kullanmanızı öneririz bir [sanal ortam](python-environments.md#virtual-environments) doğru bağımlılıkları dahil; böylece web projeleri için yayımladığınızda, web sitenizi:

![İletişim kutusu için bir proje şablonu paketleri gerekli](media/template-web-requirements-txt-wizard.png)

Microsoft Azure App Service'e dağıtırken Python sürümünü seçin bir [site uzantısı](https://aka.ms/PythonOnAppService) ve paketleri el ile yükleyin. Ayrıca, Azure App Service yaptığından **değil** paketleri otomatik olarak yüklemek bir `requirements.txt` dosya Visual Studio'dan dağıtıldığında, yapılandırma ayrıntılarını izleyin [aka.ms/PythonOnAppService](https://aka.ms/PythonOnAppService).

Microsoft Azure bulut Hizmetleri *mu* Destek `requirements.txt` dosya. [Azure bulut hizmeti projeleri](template-azure-cloud-service.md) Ayrıntılar için.

## <a name="debugging"></a>Hata Ayıklama

Hata ayıklama için bir web projesi başlatıldığında, Visual Studio web sunucusuna yerel olarak başlatır ve bu adresi ve bağlantı noktası için varsayılan tarayıcı açar. Ek seçenekleri belirtmek için projeye sağ tıklayın, seçin **özellikleri**seçip **Web Başlatıcısı** sekmesi:

  ![Genel web şablonu için Web Başlatıcısı özellikleri](media/template-web-launcher-properties.png)

İçinde **hata ayıklama** Grup:

- **Arama yolları**, **komut dosyası değişkenleri**, **yorumlayıcı bağımsız değişkenleri**, ve **yorumlayıcı yolu**: Bu seçenekleri aynıdır [normal hata ayıklama](debugging.md)
- **URL başlatma**: tarayıcınızda açıldığında URL'yi belirtir. İçin varsayılan olarak `localhost`.
- **Bağlantı noktası numarası**: URL (bir otomatik olarak varsayılan olarak Visual Studio seçer) belirtilmemişse kullanılacak bağlantı noktası. Bu ayar, varsayılan değerini geçersiz kılmanıza olanak sağlar `SERVER_PORT` şablonları tarafından yerel hata ayıklama sunucunun dinlediği bağlantı noktasını yapılandırmak için kullanılan ortam değişkeni.

Özelliklerinde **sunucu komutu Çalıştır** ve **Debug sunucu komutunu** (ikinci resim Göster nedir aşağıda) grupları belirlemek web sunucusu nasıl kurulur. Birçok çerçevelerini geçerli projenin dışında bir komut dosyası kullanımı gerektirdiğinden, komut dosyası burada yapılandırılabilir ve başlangıç modülünün adını parametre olarak geçirilebilir.

- **Komut**: Python komut dosyası olabilir (`*.py` dosyası), modül adı (gibi `python.exe -m module_name`), veya tek satırlık bir kod (gibi `python.exe -c "code"`). Aşağı açılan değer, bu tür kullanılmaya gösterir.
- **Bağımsız değişkenler**: Bu bağımsız değişkenler aşağıdaki komut komut satırında geçirilir.
- **Ortam**: yeni satır ile ayrılmış bir listesini `NAME=VALUE` çiftleri ortam değişkenleri belirtme. Bu değişkenler, ortam, bağlantı noktası numarasını ve arama yolları gibi değiştirebilir ve böylece bu değerleri üzerine yazabilir tüm özellikleri sonra ayarlanır.

Herhangi bir proje özelliği veya ortam değişkeni MSBuild sözdizimiyle örneğin belirtilebilir: `$(StartupFile) --port $(SERVER_PORT)`.
`$(StartupFile)`Başlangıç dosyanın göreli yolu ve `{StartupModule}` alınabilir başlangıç dosyasının adıdır. `$(SERVER_HOST)`ve `$(SERVER_PORT)` tarafından belirlenen normal ortam değişkenleri **başlatma URL** ve **bağlantı noktası numarası** özellikleri, otomatik olarak ya da **ortam** özellik.

> [!Note]
> Değerler **sunucu komutu Çalıştır** ile kullanılan **hata ayıklama > Start Server** komut veya Ctrl-F5; değerler **Debug sunucu komutunu** grup ilekullanılan**Hata ayıklama > hata ayıklama sunucu başlangıç** komut veya F5.

### <a name="sample-bottle-configuration"></a>Örnek Bottle yapılandırma

**Bottle Web projesi** şablon gerekli yapılandırma mu Demirbaş kod içerir. İçeri aktarılan bottle uygulama bu kodu eklemeniz gerekmez, ancak bu durumda aşağıdaki ayarları yüklü kullanarak uygulamayı başlatın `bottle` Modülü:

- **Sunucu komutu çalıştırmak** Grup:
  - **Komut**: `bottle` (Modülü)
  - **Bağımsız değişkenler**:`--bind=%SERVER_HOST%:%SERVER_PORT% {StartupModule}:app`

- **Sunucu komutu hata ayıklama** Grup:
  - **Komut**: `bottle` (Modülü)
  - **Bağımsız değişkenler**`--debug --bind=%SERVER_HOST%:%SERVER_PORT% {StartupModule}:app`

`--reload` Seçeneği, Visual Studio hata ayıklama için kullanırken önerilmez.

### <a name="sample-pyramid-configuration"></a>Örnek Piramit yapılandırma

Piramit uygulamalar, kullanarak şu anda en iyi oluşturulur `pcreate` komut satırı aracı. Uygulama oluşturulduktan sonra kullanarak alınabileceği [varolan Python kodu](python-projects.md#creating-a-project-from-existing-files) şablonu. Bunu yaptıktan sonra seçin **Genel Web projesi** özelleştirme seçeneklerini yapılandırmak için. Bu ayarlar sanal bir ortama Piramit yüklü olduğu varsayılmaktadır `..\env`.

- **Hata ayıklama** Grup:
  - **Sunucu bağlantı noktası**: 6543 (veya ne olursa olsun .ini dosyalarında yapılandırılır)

- **Sunucu komutu çalıştırmak** Grup:
  - Komut: `..\env\scripts\pserve-script.py` (komut)
  - Bağımsız değişkenler:`Production.ini`

- **Sunucu komutu hata ayıklama** Grup:
    - Komut: `..\env\scripts\pserve-script.py` (komut)
    - Bağımsız değişkenler:`Development.ini`

> [!Tip]
> Yapılandırmanıza gerek **çalışma dizini** özelliği projenizin Piramit uygulamalar genellikle bir dizin düzeyinde kaynak ağacın üstüne derin olduğundan.

### <a name="other-configurations"></a>Diğer yapılandırmalar

Paylaşma veya başka bir framework ayarlarını isteği istiyorsanız açmak istediğiniz başka bir framework ayarlarını varsa bir [GitHub sorunu](https://github.com/Microsoft/PTVS/issues).

## <a name="publishing-to-azure-app-service"></a>Azure uygulama hizmeti yayımlama

Azure uygulama hizmeti yayımlamak için birincil iki yolu vardır. İlk olarak, kaynak denetiminden dağıtım diğer diller için olduğu gibi aynı şekilde açıklandığı gibi kullanılabilir [Azure belgelerine](http://azure.microsoft.com/en-us/documentation/articles/web-sites-publish-source-control/). Doğrudan Visual Studio'dan yayımlamak için projeye sağ tıklayın ve seçin **Yayımla**:

![Komut bir projenin bağlam menüsünde Yayımla](media/template-web-publish-command.png)

Komut seçerek, sihirbaz, bir web sitesi oluşturma konusunda size yardımcı olacaktır veya içeri aktarma yayımlama sonra Önizleme ayarları, dosyaları ve bir uzak sunucuya yayımlamayı değiştirilebilir.

Uygulama hizmeti bir site oluşturduğunuzda, Python ve sitenizi bağımlı herhangi bir paket yüklemeniz gerekir. İlk sitenizi yayımlayın, ancak Python yapılandırmadığınız sürece çalışmaz.

Uygulama hizmeti Python yüklemek için kullanmanızı öneririz [site uzantıları](http://www.siteextensions.net/packages?q=Tags%3A%22python%22) (siteextensions.net). Bu uzantılar kopyalarıdır [resmi sürümleri](https://www.python.org) en iyi duruma getirilmiş ve Azure App Service için paketlenmiş Python.

Bir site uzantısı üzerinden dağıtılabilir [Azure portal](https://portal.azure.com/). Seçin **geliştirme araçları > uzantıları** uygulama hizmetiniz seçin dikey **Ekle**ve Python öğeleri bulmak için listede ilerleyin:

![Azure portalında site uzantısı Ekle](media/template-web-site-extensions.png)

JSON dağıtım şablonları kullanıyorsanız, site uzantısı, sitenizin bir kaynak olarak belirtebilirsiniz:

```json
{
    "resources": [
    {
        "apiVersion": "2015-08-01",
        "name": "[parameters('siteName')]",
        "type": "Microsoft.Web/sites",
        ...
    },
    "resources": [
    {
        "apiVersion": "2015-08-01",
        "name": "python352x64",
        "type": "siteextensions",
        "properties": { },
        "dependsOn": [
            "[resourceId('Microsoft.Web/sites', parameters('siteName'))]"
        ]
    },
    ...
}
```

Son olarak, aracılığıyla oturum [geliştirme konsol](https://github.com/projectkudu/kudu/wiki/Kudu-console) ve oradan site uzantısı yükleyin.

Şu anda, paketleri yüklemek için önerilen yöntem geliştirme konsol site uzantısı yükleyip PIP doğrudan Yürütülüyor sonra kullanmaktır. Python tam yolunu kullanarak önemli olduğu veya yanlış bir yürütme ve genelde sanal bir ortama kullanmaya gerek yoktur. Örneğin:

```command
c:\Python35\python.exe -m pip install -r D:\home\site\wwwroot\requirements.txt

c:\Python27\python.exe -m pip install -r D:\home\site\wwwroot\requirements.txt
```

Azure App Service'e dağıtıldığında, siteniz Microsoft IIS çalıştırır. IIS ile çalışmak üzere sitenizi etkinleştirmek için en az bir eklemeniz `web.config` dosya. Kullanılabilir şablonlar bazı ortak dağıtım hedefleri için kullanılabilir projeye sağ tıklayıp seçerek **Ekle > Yeni öğe...**  (iletişim aşağıya bakın) ve bu yapılandırmalar diğer kullanımlar için kolayca değiştirilebilir. Bkz: [IIS yapılandırma başvurusu](https://www.iis.net/configreference) kullanılabilen yapılandırma ayarları hakkında bilgi için.

![Azure öğe şablonları](media/template-web-azure-items.png)

Kullanılabilir öğeler şunlardır:

- Azure web.config (Fastcgı): ekler bir `web.config` zaman uygulamanızı sağlayan dosya bir [WSGI](https://wsgi.readthedocs.io/en/latest/) gelen bağlantıları işlemek için nesne.
- Azure web.config (HttpPlatformHandler): ekler bir `web.config` olduğunda, uygulamanızın gelen bağlantılar için bir yuvada dinler dosyası.
- Azure statik dosyaları web.config: olduğunda yukarıdaki birini `web.config` dosyaları, uygulamanız tarafından işlenen dışlamak için bir alt dizine dosyasına ekleyin.
- Azure uzaktan hata ayıklama web.config: WebSockets üzerinden uzaktan hata ayıklama için gerekli dosyaları ekler.
- Web rolü destek dosyalarını: Bulut hizmeti web rolleri için varsayılan dağıtım betikleri içerir.
- Çalışan rolü destek dosyalarını: varsayılan dağıtım ve başlatma komut dosyaları için bulut hizmeti çalışan rolleri içerir.

Hata ayıklama eklerseniz `web.config` şablonu projenizde veya Python uzaktan hata ayıklama kullanmak için plan için "Hata ayıklama" yapılandırmasında yayınlamanıza vermeniz gerekir. Bu ayar geçerli etkin çözüm yapılandırmasından ayrı ve her zaman "Yayın" varsayılan olarak Değiştirmek için açık **ayarları** sekmesinde ve kullanmak **yapılandırma** birleşik giriş kutusu Yayımlama Sihirbazı'nda (bkz [Azure belgelerine](https://azure.microsoft.com/develop/python/) oluşturma hakkında daha fazla bilgi için ve Azure Web uygulamaları dağıtmak için):

![Yayımla yapılandırmasını değiştirme](media/template-web-publish-config.png)

**Microsoft Azure bulut hizmeti projesine dönüştürme** komutu (aşağıdaki görüntü), çözümünüz için bir bulut hizmeti projesini ekler. Bu proje kullanılacak sanal makineler ve hizmetler için yapılandırma ve dağıtım ayarlarını içerir. Kullanım **Yayımla** bulut hizmetlerine; dağıtmak için bulut projesi komutunu **Yayımla** Python proje komutunda hala Web sitelerine dağıtır. Bkz: [Azure bulut hizmeti projeleri](template-azure-cloud-service.md) daha fazla ayrıntı için.

![Microsoft Azure bulut hizmeti projesi komutuna Dönüştür](media/template-web-convert-menu.png)
