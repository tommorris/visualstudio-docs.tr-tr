---
title: Python projeleri için öğe şablonları
description: Başvuru listesini Ekle kullanılabilir olan Python proje öğesi şablonları > Visual Studio'da yeni öğe iletişim kutusu.
ms.date: 09/04/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 8319c99e5de12ce1c09a2c20fc5cf1b132f34092
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43776041"
---
# <a name="python-item-templates"></a>Python öğe şablonları

Öğe şablonları Python projelerinde kullanılabilir **proje** > **Yeni Öğe Ekle** menü komutu veya **Ekle**  >  **Yeni öğe** bağlam menüsü komutu **Çözüm Gezgini**.

![Yeni Öğe Ekle iletişim kutusu](media/project-item-templates.png)

Öğe için sağladığınız adı kullanarak, bir şablon genellikle bir veya daha fazla dosya ve klasör içindeki şu anda seçilen projede oluşturur (Bu klasöre seçer otomatik olarak bağlam menüsünü açmak için bir klasöre sağ tıklayarak). Öğe ekleme bunu içerir Visual Studio Proje ve öğe görünür **Çözüm Gezgini**.

Aşağıdaki tabloda, her öğe şablonu bir Python projesindeki etkisini kısaca açıklanır:

| Şablon | Hangi şablon oluşturur |
| --- | --- |
| **Boş Python dosyası** | Boş bir dosya ile *.py* uzantısı. |
| **Python sınıfı** | A *.py* tek bir boş Python sınıf tanımını içeren dosya. |
| **Python paketi** | İçeren bir klasörün bir  *\_ \_init\_\_.py* dosya. |
| **Test Jednotky Pythonu** | A *.py* tek birim testi dosyasını temel alarak `unittest` , çağrı birlikte iş çerçevesini `unittest.main()` dosyasında testleri çalıştırmak için. |
| **HTML sayfası** | Bir *.html* oluşan bir basit sayfa yapısı dosyasıyla bir `<head>` ve `<body>` öğesi. |
| **JavaScript** | Boş bir *.js* dosya. |
| **Stil sayfası** | A *.css* için boş bir stil içeren dosya `body`. |
| **Metin dosyası** | Boş bir *.txt* dosya. |
| **Django 1.9 uygulama**<br/>**Django 1.4 uygulama** | İçinde anlatıldığı gibi bir Django uygulaması çekirdek dosyalarını içeren uygulamanın adı taşıyan bir klasör [öğrenin Django Visual Studio'da, adım 2-2](learn-django-in-visual-studio-step-02-create-an-app.md#step-2-1-create-an-app-with-a-default-structure) Django 1.9 için. Django 1.4 için *geçişler* klasöründe *admin.py* dosyasını ve *apps.py* dosyası dahil değildir. |
| **Okno WPF v Ironpythonu** | İki yan yana dosyasından oluşan bir WPF penceresi: bir *.xaml* tanımlayan dosyası bir `<Window>` boş ile `<Grid>` öğesi ve ilişkili bir *.py* XAML kullanarak dosya yükleyen dosyası `wpf` kitaplığı. Genellikle, IronPython proje şablonlarından birini kullanarak oluşturulan bir proje içinde kullanılır. Bkz: [yönetme Python projeleri - proje şablonları](managing-python-projects-in-visual-studio.md#project-templates). |
| **Web rolü destek dosyaları** | A *bin* (seçilen klasördeki projesinde) bağımsız olarak proje kök klasöründe. Klasör varsayılan dağıtım betiğini içerir ve bir *web.config* Azure bulut hizmeti web rolleri için dosya. Şablon da içeren bir *readme.html* ayrıntılarını açıklayan dosya. |
| **Çalışan rolü destek dosyaları** | A *bin* (seçilen klasördeki projesinde) bağımsız olarak proje kök klasöründe. Klasörü ile birlikte varsayılan dağıtım veya başlatma betiği içeren bir *web.config* Azure bulut hizmeti çalışan rolleri için bir dosya. Şablon da içeren bir *readme.html* ayrıntılarını açıklayan dosya. |
| **Web.config Pro Azure (Fastcgı)** | A *web.config* dosyasının kullanarak uygulamalar için girdiler içeren bir [WSGI](https://wsgi.readthedocs.io/en/latest/) gelen bağlantıları işlemek için nesne. Bu dosya, genellikle Azure App Service gibi bir IIS web sunucusunda kök dağıtılır. Daha fazla bilgi için [Azure App Service'e yayımlama](publishing-python-web-applications-to-azure-from-visual-studio.md). |
| **Web.config Pro Azure (HttpPlatformHandler)** | A *web.config* bir yuvada gelen bağlantıları için dinlemek uygulamaları girişlerini içeren dosya. Bu dosya, genellikle Azure App Service gibi bir IIS web sunucusunda kök dağıtılır. Daha fazla bilgi için [Azure App Service'e yayımlama](publishing-python-web-applications-to-azure-from-visual-studio.md). |
| **Azure statik dosyaları web.config** | A *web.config* tipik olarak eklenen dosya bir *statik* bu klasör için işleme Python devre dışı bırakmak için klasöründen (veya diğer klasör içeren statik öğeleri). Bu yapılandırma dosyası yukarıdaki Fastcgı veya HttpPlatformHandler yapılandırma dosyalarından biri ile birlikte çalışır. Daha fazla bilgi için [Azure App Service'e yayımlama](publishing-python-web-applications-to-azure-from-visual-studio.md). |
| **Azure uzaktan hata ayıklama web.config** | A *web.config.debug* uzak WebSockets üzerinden ile birlikte hata ayıklamasını etkinleştirir dosya *Microsoft.PythonTools.WebRole.dll* ve *ptvsd* içeren klasör Uzaktan hata ayıklamayı etkinleştirmek için sunucuya dağıtmak için modülleri. Aynı yerde bu öğeyi oluşturma, *web.config* dosya. Daha fazla bilgi için [Python kodu azure'da uzaktan hata ayıklama](debugging-remote-python-code-on-azure.md). Ayrıca aşağıdaki nota bakın. |

> [!Note]
> Hata ayıklama eklerseniz *web.config* şablonu için proje ve planı Python uzaktan hata ayıklama kullanmanız gereken sitesinde yayımlamak **hata ayıklama** yapılandırma. Bu ayar, geçerli etkin çözüm yapılandırmasını ayrıdır ve her zaman varsayılan olarak **yayın**. Bunu değiştirmek için **ayarları** sekme ve kullanma **yapılandırma** birleşik giriş kutusunda **Yayımla** Sihirbazı. (Bkz [Azure belgeleri](https://azure.microsoft.com/develop/python/) oluşturma ve Azure Web Apps'e dağıtma hakkında daha fazla bilgi.)
>
> ![Yayımlama yapılandırmasını değiştirme](media/template-web-publish-config.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Python projeleri - proje şablonlarını yönetme](managing-python-projects-in-visual-studio.md#project-templates)
- [Python web projesi şablonları](python-web-application-project-templates.md)
- [Azure app Service'e yayımlama](publishing-python-web-applications-to-azure-from-visual-studio.md)
