---
title: Python projeleri için öğe şablonları
description: Bir başvuru listesi Ekle kullanılabilen Python proje öğesi şablonları > Visual Studio'da yeni öğe iletişim kutusu.
ms.date: 04/25/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 9811905e842eeb62399ef3b88558ee0286b05c84
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2018
ms.locfileid: "32032814"
---
# <a name="python-item-templates"></a>Python öğe şablonları

Öğe şablonları Python projelerinde kullanılabilen **proje** > **Yeni Öğe Ekle** menü komutu veya **Ekle**  >  **Yeni öğe** bağlam menüsü komutunu **Çözüm Gezgini**.

![Yeni Öğe Ekle iletişim kutusu](media/project-item-templates.png)

Öğe için sağladığınız adı kullanarak, bir şablon genellikle bir veya daha fazla dosya ve klasör içindeki şu anda seçili projede oluşturur (Bu klasör seçer bağlam menüsü otomatik olarak getirmek için bir klasöre sağ tıklayarak). Bir öğe eklemeyi içerir, Visual Studio Proje ve öğe görünür **Çözüm Gezgini**.

Aşağıdaki tabloda, her bir Python proje öğesi şablonda etkisini kısaca açıklanmaktadır:

| Şablon | Şablonu oluşturur |
| --- | --- |
| Boş Python dosyası | Boş bir dosya ile `.py` uzantısı. |
| Python sınıfı | A `.py` tek bir boş Python sınıf tanımını içeren dosya. |
| Python paket | İçeren bir klasör bir `__init.py__` dosyası. |
| Python birim testi | A `.py` tek birim testi dosyasıyla temel alarak `unittest` yapılan bir çağrı birlikte framework `unittest.main()` dosyasında testleri çalıştırmak için. |
| HTML sayfası | Bir `.html` oluşan basit sayfa yapısı dosyayla bir `<head>` ve `<body>` öğesi. |
| JavaScript | Boş bir `.js` dosyası. |
| Stil sayfası | A `.css` için boş bir stil içeren dosya `body` |
| Metin dosyası | Boş bir `.txt` dosyası. |
| Django 1.9 uygulama<br/>Django 1.4 uygulama | Açıklandığı gibi bir Django uygulaması için çekirdek dosyalarını içeren uygulama adı taşıyan bir klasör [öğrenme Django Visual Studio'da, adım 2-2](learn-django-in-visual-studio-step-02-create-an-app.md#step-2-1-create-an-app-with-a-default-structure) Django 1.9 için. Django 1.4 için `migrations` klasörünü `admin.py` dosyası ve `apps.py` dosya dahil değildir. |
| IronPython WPF penceresi | İki yan yana dosyadan oluşan bir WPF penceresi: bir `.xaml` tanımlayan dosyası bir `<Window>` boş bir ile `<Grid>` öğesi ve ilişkili bir `.py` XAML kullanarak dosya yükler dosya `wpf` kitaplığı. Genellikle, IronPython proje şablonlarından birini kullanarak oluşturulan bir proje içinde kullanılır. Bkz: [yönetme Python projeleri - proje şablonları](managing-python-projects-in-visual-studio.md#project-templates). |
| Web rolü destek dosyaları | A `bin` (Proje seçili klasöründe) bağımsız olarak proje kök klasöründe. Klasörü varsayılan dağıtım betiğini içerir ve bir `web.config` dosyası Azure bulut hizmeti web rolleri için. Şablon de içeren bir `readme.html` ilişkin ayrıntılar açıklanmaktadır dosya. |
| Çalışan rolü destek dosyaları | A `bin` (Proje seçili klasöründe) bağımsız olarak proje kök klasöründe. İle birlikte varsayılan dağıtım ve başlatma komut dosyası, klasörü içeren bir `web.config` Azure bulut hizmeti çalışan rolleri için dosya. Şablon de içeren bir `readme.html` ilişkin ayrıntılar açıklanmaktadır dosya. |
| Azure web.config (Fastcgı) | A `web.config` dosyasının kullanan uygulamalar için girdiler içeren bir [WSGI](https://wsgi.readthedocs.io/en/latest/) gelen bağlantıları işlemek için nesne. Bu dosya, genellikle Azure uygulama hizmeti gibi IIS çalıştıran bir web sunucusunun kök dağıtılır. Daha fazla bilgi için bkz: [Azure App Service'te yayımlama](publishing-python-web-applications-to-azure-from-visual-studio.md). |
| Azure web.config (HttpPlatformHandler) | A `web.config` gelen bağlantılar için bir yuvadaki dinleme uygulamaları girişlerini içeren dosya. Bu dosya, genellikle Azure uygulama hizmeti gibi IIS çalıştıran bir web sunucusunun kök dağıtılır. Daha fazla bilgi için bkz: [Azure App Service'te yayımlama](publishing-python-web-applications-to-azure-from-visual-studio.md). |
| Azure statik dosyaları web.config | A `web.config` tipik olarak eklenen dosya bir `static` bu klasör için işleme Python devre dışı bırakmak için klasör (veya diğer klasör içeren statik öğeleri). Bu yapılandırma dosyası Fastcgı veya HttpPlatformHandler yapılandırma dosyaları yukarıdaki biri ile birlikte çalışır. Daha fazla bilgi için bkz: [Azure App Service'te yayımlama](publishing-python-web-applications-to-azure-from-visual-studio.md). |
| Azure uzaktan hata ayıklama web.config | A `web.config.debug` uzak WebSockets üzerinden alongside hata ayıklamasını etkinleştirir dosya `Microsoft.PythonTools.WebRole.dll` ve `ptvsd` uzaktan hata ayıklamayı etkinleştirmek için sunucuya dağıtmak için modülleri içeren klasör. Aynı yerde bu öğeyi oluşturmak, `web.config` dosya. Daha fazla bilgi için bkz: [uzaktan hata ayıklama Python kodu Azure üzerinde](debugging-remote-python-code-on-azure.md). Ayrıca aşağıdaki nota bakın. |

> [!Note]
> Hata ayıklama eklerseniz `web.config` Şablonu proje ve Python uzaktan hata ayıklama kullanılacak planı "Hata ayıklama" yapılandırmasında yayınlamanıza vermeniz gerekir. Bu ayar geçerli etkin çözüm yapılandırmasından ayrı ve her zaman "Yayın" varsayılan olarak Değiştirmek için açık **ayarları** sekmesinde ve kullanmak **yapılandırma** Yayımlama Sihirbazı'nda açılan kutusu. (Bkz [Azure belgelerine](https://azure.microsoft.com/develop/python/) Azure Web uygulamalar oluşturma ve dağıtma hakkında daha fazla bilgi için.)
>
> ![Yayımla yapılandırmasını değiştirme](media/template-web-publish-config.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Python projeleri - proje şablonları yönetme](managing-python-projects-in-visual-studio.md#project-templates)
- [Python web projesi şablonları](python-web-application-project-templates.md)
- [Azure app Service'e yayımlama](publishing-python-web-applications-to-azure-from-visual-studio.md)