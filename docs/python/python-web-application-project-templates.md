---
title: Python için Web Uygulama Şablonları
description: Visual Studio şablonları Python yapılandırmaları hata ayıklama ve Azure App Service'te yayımlama da dahil olmak üzere Bottle, Flask ve Django çerçeveler kullanılarak yazılmış web uygulamaları için genel bakış.
ms.date: 04/17/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 6d76bc7868c78b1def09376cb2382aa39cff1cda
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2018
---
# <a name="python-web-application-project-templates"></a>Python web uygulaması proje şablonları

Python Visual Studio Proje şablonları ve çeşitli çerçeveleri işlemek üzere yapılandırılmış bir hata ayıklama başlatıcısı aracılığıyla Bottle, Flask ve Django çerçeveleri geliştirme web projeleri destekler. Bu şablonlar dahil bir `requirements.txt` gerekli bağımlılıkları bildirmek için dosya. Bir proje bu şablonlardan birini oluştururken, Visual Studio bu paketleri yüklemenizi ister (bkz [proje gereksinimlerini yükleme](#installing-project-requirements) bu makalenin ilerisinde yer).

Genel "Web projesi" Şablon Piramit gibi diğer çerçeveler için de kullanabilirsiniz. Bu durumda, hiçbir çerçeveleri şablonla yüklenir. Bunun yerine, proje için kullanmakta olduğunuz ortamına gerekli paketleri yüklemek (bkz [yönetme Python ortamları](managing-python-environments-in-visual-studio.md)).

## <a name="using-a-project-template"></a>Proje şablonunu kullanarak

Kullanarak bir şablon bir proje oluşturmadan **dosya** > **yeni** > **proje**. Web projeleri için şablonlar görmek için seçin **Python** > **Web** iletişim kutusunun sol tarafında. Tercih ettiğiniz bir şablon seçin, adları sağlama proje ve çözüm için bir çözüm dizini ve Git deposu için seçenekleri ayarlayın ve seçin **Tamam**.

![Web uygulamaları için yeni proje iletişim kutusu](media/projects-new-project-dialog-web.png)

Daha önce belirtildiği genel "Web projesi" şablonu yalnızca boş bir Visual Studio projesi kod ve Python proje olması dışında hiçbir varsayımlar sağlar. "Azure bulut hizmeti" şablonu hakkında daha fazla bilgi için bkz: [Python için Azure bulut hizmeti projeleri](python-azure-cloud-service-project-template.md).python-azure-cloud-service-project-template.md

Tüm Şablonları Bottle, Flask ve Django web çerçevesinde temel alır ve aşağıdaki bölümlerde açıklandığı gibi üç genel gruba ayrılır. Bu şablonlardan birini tarafından oluşturulan uygulamaları çalıştırmak ve uygulama yerel olarak hata ayıklama için yeterli kodunu içerir. Her biri de gerekli sağlar [WSGI uygulama nesnesini](http://www.python.org/dev/peps/pep-3333/) (python.org) için [Azure App Service'e dağıtma](publishing-python-web-applications-to-azure-from-visual-studio.md).

### <a name="blank-group"></a>Boş grubu

Bir proje ile daha fazla tüm "Boş (framework) Web projesi" şablonlar oluşturabilir veya daha az en az Demirbaş kod ve gerekli bağımlılıkları bildirilen bir `requirements.txt` dosyası.

| Şablon | Açıklama |
| --- | --- |
| Boş Bottle Web projesi | En az bir uygulamada oluşturur `app.py` için bir giriş sayfası ile `/` ve `/hello/<name>` görüntülemektedir sayfa `<name>` çok kısa satır içi sayfa şablonu kullanarak. |
| Boş Django Web projesi | Çekirdek Django sitesi yapısını ancak hiçbir Django uygulamaları ile Django projesi oluşturur. Daha fazla bilgi için bkz: [Django şablonları](python-django-web-application-project-template.md) ve [öğrenme Django adım 1](learn-django-in-visual-studio-step-01-project-and-solution.md). |
| Boş Flask Web projesi | Bir tek "Hello World!" ile en az bir uygulama oluşturur için sayfa `/`. Bu uygulamanın ayrıntılı adımlarını izleyerek sonucunu benzer [hızlı başlangıç: ilk Python web uygulamanızı oluşturmak için Visual Studio](../ide/quickstart-python.md?context=visualstudio/python/default).

### <a name="web-group"></a>Web grubu

Tüm "(Framework) Web projesi" şablonları, seçilen framework bakılmaksızın aynı bir tasarım ile bir başlangıç web uygulaması oluşturun. Uygulama giriş, sahip bir gezinme çubuğu ve önyükleme kullanarak esnek tasarım birlikte hakkında ve iletişim sayfaları. Her uygulama sunucusu statik dosyaları (CSS, JavaScript ve yazı tipleri) için uygun şekilde yapılandırıldığından ve çerçevesi için uygun bir sayfa şablonu mekanizması kullanır.

| Şablon | Açıklama |
| --- | --- |
| Bottle Web projesi | Yalnızca statik dosyalar içerdiği bir uygulama oluşturur `static` klasörü ve kodda aracılığıyla işlenmesini `app.py`. Tek tek sayfaları için yönlendirme içinde barındırılan `routes.py`ve `views` klasörü sayfası şablonları içerir.|
| Django Web projesi | Django proje ve üç sayfaları, kimlik doğrulama desteği ve bir SQLite veritabanı (ancak hiçbir veri modelleri) ile Django uygulamasını oluşturur. Daha fazla bilgi için bkz: [Django şablonları](python-django-web-application-project-template.md) ve [öğrenme Django adım 4](learn-django-in-visual-studio-step-04-full-django-project-template.md). |
| Flask Web projesi | Yalnızca statik dosyalar içerdiği bir uygulama oluşturur `static` klasör. Kod `views.py` işler sayfası şablonlarını içinde yer alan Jinja altyapısını kullanarak yönlendirme `templates` klasör. `runserver.py` Dosyası başlangıç kodu sağlar. |
| Flask/Jade Web projesi | "Flask Web projesi" şablonu ancak Jade şablon motoru kullanarak uygulamayı olarak oluşturur. |

### <a name="polls-group"></a>Anketler grubu

"Yoklamalar (framework) Web projesi" şablonları ilgili farklı yoklama soruları üzerinden kullanıcıların oy bir başlangıç web uygulaması oluşturun. Her uygulama anketler ve kullanıcı yanıtlarını yönetmek için bir veritabanını kullanmak için "Web" proje şablonlarını yapısı oluşturur. Uygun veri modelleri dahil uygulamalar ve sayfa ("/ çekirdek"), özel bir uygulama yoklamalar dan yükleyen bir `samples.json` dosyası.

| Şablon | Açıklama |
| --- | --- |
| Anketler Bottle Web projesi | Bellek içi veritabanı, MongoDB veya kullanılarak yapılandırılan Azure Table Storage karşı çalıştırabilirsiniz bir uygulama oluşturur `REPOSITORY_NAME` ortam değişkeni. Veri modelleri ve veri deposu kodu bulunan `models` klasörünü ve `settings.py` dosyası, hangi veri deposu kullanıldığını belirlemek için kod içerir. |
| Yoklamalar Django Web projesi | Django proje ve bir Django uygulamayla üç sayfaları ve bir SQLite veritabanı oluşturur. Kimliği doğrulanmış yönetici oluşturmak ve anketler yönetmek izin vermek için Django yönetim arabirimini özelleştirmeleri içerir. Daha fazla bilgi için bkz: [Django şablonları](python-django-web-application-project-template.md) ve [öğrenme Django adım 6](learn-django-in-visual-studio-step-06-polls-django-web-project-template.md). |
| Anketler Flask Web projesi | Bellek içi veritabanı, MongoDB veya kullanılarak yapılandırılan Azure Table Storage karşı çalıştırabilirsiniz bir uygulama oluşturur `REPOSITORY_NAME` ortam değişkeni. Veri modelleri ve veri deposu kodu bulunan `models` klasörünü ve `settings.py` dosyası, hangi veri deposu kullanıldığını belirlemek için kod içerir. Uygulama için sayfa şablonları Jinja altyapısı kullanır. |
| Anketler Flask/Jade Web projesi | "Yoklamalar Flask Web projesi" şablonu ancak Jade şablon motoru kullanarak uygulamayı olarak oluşturur. |

## <a name="installing-project-requirements"></a>Proje gereksinimlerini yükleme

Bir proje çerçeveye özel şablonu oluştururken, PIP kullanarak gerekli paketleri yüklemenize yardımcı olması için bir iletişim kutusu görüntülenir. Ayrıca kullanmanızı öneririz bir [sanal ortam](selecting-a-python-environment-for-a-project.md#using-virtual-environments) doğru bağımlılıkları dahil; böylece web projeleri için yayımladığınızda, web sitenizi:

![İletişim kutusu için bir proje şablonu paketleri gerekli](media/template-web-requirements-txt-wizard.png)

Kaynak denetimi kullanıyorsanız, bu ortam yalnızca kullanılarak yeniden oluşturulması gibi genellikle sonra sanal ortam klasörü atlayın `requirements.txt`. Klasörü dışlamak için en iyi yolu ilk seçmektir **ı bunları kendim yükleyecek** isteminde yukarıda gösterilen, ardından otomatik tamamlama sanal ortamı oluşturmadan önce devre dışı bırakın. Ayrıntılar için bkz [öğrenme Django Öğreticisi - 1-2 ve 1-3 adımları](learn-django-in-visual-studio-step-01-project-and-solution.md#step-1-2-examine-the-git-controls-and-publish-to-a-remote-repository)

Microsoft Azure App Service'e dağıtırken Python sürümünü seçin bir [site uzantısı](https://aka.ms/PythonOnAppService) ve paketleri el ile yükleyin. Ayrıca, Azure App Service yaptığından **değil** paketleri otomatik olarak yüklemek bir `requirements.txt` dosya Visual Studio'dan dağıtıldığında, yapılandırma ayrıntılarını izleyin [aka.ms/PythonOnAppService](https://aka.ms/PythonOnAppService).

Microsoft Azure bulut Hizmetleri *mu* Destek `requirements.txt` dosya. Bkz: [Azure bulut hizmeti projeleri](python-azure-cloud-service-project-template.md) Ayrıntılar için.

## <a name="debugging"></a>Hata Ayıklama

Hata ayıklama için bir web projesi başlatıldığında, Visual Studio rastgele bir bağlantı noktasında bir yerel web sunucusu başlatır ve bu adresi ve bağlantı noktası için varsayılan tarayıcı açar. Ek seçenekleri belirtmek için projeye sağ tıklayın, seçin **özellikleri**seçip **Web Başlatıcısı** sekmesi:

![Genel web şablonu için Web Başlatıcısı özellikleri](media/template-web-launcher-properties.png)

İçinde **hata ayıklama** Grup:

- **Arama yolları**, **komut dosyası değişkenleri**, **yorumlayıcı bağımsız değişkenleri**, ve **yorumlayıcı yolu**: Bu seçenekleri aynıdır [normal hata ayıklama](debugging-python-in-visual-studio.md)
- **URL başlatma**: tarayıcınızda açıldığında URL'yi belirtir. İçin varsayılan olarak `localhost`.
- **Bağlantı noktası numarası**: URL (bir otomatik olarak varsayılan olarak Visual Studio seçer) belirtilmemişse kullanılacak bağlantı noktası. Bu ayar, varsayılan değerini geçersiz kılmanıza olanak sağlar `SERVER_PORT` şablonları tarafından yerel hata ayıklama sunucunun dinlediği bağlantı noktasını yapılandırmak için kullanılan ortam değişkeni.

Özelliklerinde **sunucu komutu Çalıştır** ve **Debug sunucu komutunu** (ikinci resim Göster nedir aşağıda) grupları belirlemek web sunucusu nasıl kurulur. Birçok çerçevelerini geçerli projenin dışında bir komut dosyası kullanımı gerektirdiğinden, komut dosyası burada yapılandırılabilir ve başlangıç modülünün adını parametre olarak geçirilebilir.

- **Komut**: Python komut dosyası olabilir (`*.py` dosyası), modül adı (gibi `python.exe -m module_name`), veya tek satırlık bir kod (gibi `python.exe -c "code"`). Aşağı açılan değer, bu tür kullanılmaya gösterir.
- **Bağımsız değişkenler**: Bu bağımsız değişkenler aşağıdaki komut komut satırında geçirilir.
- **Ortam**: yeni satır ile ayrılmış bir listesini `NAME=VALUE` çiftleri ortam değişkenleri belirtme. Bu değişkenler, ortam, bağlantı noktası numarasını ve arama yolları gibi değiştirebilir ve böylece bu değerleri üzerine yazabilir tüm özellikleri sonra ayarlanır.

Herhangi bir proje özelliği veya ortam değişkeni MSBuild sözdizimiyle örneğin belirtilebilir: `$(StartupFile) --port $(SERVER_PORT)`.
`$(StartupFile)` Başlangıç dosyanın göreli yolu ve `{StartupModule}` alınabilir başlangıç dosyasının adıdır. `$(SERVER_HOST)` ve `$(SERVER_PORT)` tarafından belirlenen normal ortam değişkenleri **başlatma URL** ve **bağlantı noktası numarası** özellikleri, otomatik olarak ya da **ortam** özelliği.

> [!Note]
> Değerler **sunucu komutu Çalıştır** ile kullanılan **hata ayıklama > Start Server** komut veya Ctrl-F5; değerler **Debug sunucu komutunu** grup ilekullanılan**Hata ayıklama > hata ayıklama sunucu başlangıç** komut veya F5.

### <a name="sample-bottle-configuration"></a>Örnek Bottle yapılandırma

**Bottle Web projesi** şablon gerekli yapılandırma mu Demirbaş kod içerir. İçeri aktarılan bottle uygulama bu kodu eklemeniz gerekmez, ancak bu durumda aşağıdaki ayarları yüklü kullanarak uygulamayı başlatın `bottle` Modülü:

- **Sunucu komutu çalıştırmak** Grup:
  - **Komut**: `bottle` (Modülü)
  - **Bağımsız değişkenler**: `--bind=%SERVER_HOST%:%SERVER_PORT% {StartupModule}:app`

- **Sunucu komutu hata ayıklama** Grup:
  - **Komut**: `bottle` (Modülü)
  - **Bağımsız değişkenler** `--debug --bind=%SERVER_HOST%:%SERVER_PORT% {StartupModule}:app`

`--reload` Seçeneği, Visual Studio hata ayıklama için kullanırken önerilmez.

### <a name="sample-pyramid-configuration"></a>Örnek Piramit yapılandırma

Piramit uygulamalar, kullanarak şu anda en iyi oluşturulur `pcreate` komut satırı aracı. Uygulama oluşturulduktan sonra kullanarak alınabileceği [varolan Python kodu](managing-python-projects-in-visual-studio.md#creating-a-project-from-existing-files) şablonu. Bunu yaptıktan sonra seçin **Genel Web projesi** özelleştirme seçeneklerini yapılandırmak için. Bu ayarlar sanal bir ortama Piramit yüklü olduğu varsayılmaktadır `..\env`.

- **Hata ayıklama** Grup:
  - **Sunucu bağlantı noktası**: 6543 (veya ne olursa olsun .ini dosyalarında yapılandırılır)

- **Sunucu komutu çalıştırmak** Grup:
  - Komut: `..\env\scripts\pserve-script.py` (komut)
  - Bağımsız değişkenler: `Production.ini`

- **Sunucu komutu hata ayıklama** Grup:
  - Komut: `..\env\scripts\pserve-script.py` (komut)
  - Bağımsız değişkenler: `Development.ini`

> [!Tip]
> Büyük olasılıkla yapılandırmanıza gerek **çalışma dizini** özelliği projenizin Piramit uygulamalar genellikle proje kökü altındaki bir klasör olduğundan.

### <a name="other-configurations"></a>Diğer yapılandırmalar

Paylaşma veya başka bir framework ayarlarını isteği istiyorsanız açmak istediğiniz başka bir framework ayarlarını varsa bir [GitHub sorunu](https://github.com/Microsoft/PTVS/issues).

## <a name="convert-a-project-to-azure-cloud-service"></a>Azure bulut hizmeti için bir proje Dönüştür

**Microsoft Azure bulut hizmeti projesine dönüştürme** komutu (aşağıdaki görüntü), çözümünüz için bir bulut hizmeti projesini ekler. Bu proje kullanılacak sanal makineler ve hizmetler için yapılandırma ve dağıtım ayarlarını içerir. Kullanım **Yayımla** bulut hizmetlerine; dağıtmak için bulut projesi komutunu **Yayımla** Python proje komutunda hala Web sitelerine dağıtır. Daha fazla bilgi için bkz: [Azure bulut hizmeti projeleri](python-azure-cloud-service-project-template.md).

![Microsoft Azure bulut hizmeti projesi komutuna Dönüştür](media/template-web-convert-menu.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Python öğesi şablonları başvurusu](python-item-templates.md)
- [Azure App Service’e yayımlama](publishing-python-web-applications-to-azure-from-visual-studio.md)
