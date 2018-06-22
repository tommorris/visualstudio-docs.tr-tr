---
title: Windows Visual Studio'da Python desteği'ne genel bakış
description: Visual Studio'da Windows (PTVS Visual Studio için Python araçları olarak da bilinir) en iyi Python IDE kolaylaştırarak, Python özelliklerinin özeti.
ms.date: 05/07/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: overview
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 7384bbdb136038cf73914e9743f56790c2150ca6
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36281215"
---
# <a name="working-with-python-in-visual-studio-on-windows"></a>Windows Visual Studio'da Python ile çalışma

Python güvenilir, esnek, kolay öğrenmek için tüm işletim sistemlerinde kullanımına yönelik ücretsiz ve sağlam Geliştirici topluluğu ve pek çok ücretsiz kitaplıkları tarafından desteklenen popüler bir programlama dilidir. Python geliştirme, web uygulamaları, web Hizmetleri, Masaüstü uygulamaları, komut dosyası ve bilimsel hesaplama, dahil olmak üzere tüm yolla destekler ve birçok üniversiteler, bilimcilerine, rasgele geliştiriciler ve profesyonel geliştiricilere benzer tarafından kullanılır. Üzerinde dili hakkında daha fazla bilgiyi [python.org](https://www.python.org) ve [yeni başlayanlar için Python](https://www.python.org/about/gettingstarted/).

Visual Studio Windows'da güçlü bir Python IDE ' dir. Visual Studio sağlar [açık kaynak](https://github.com/Microsoft/ptvs) Python geliştirme ve veri bilimi iş yüklerini (Visual Studio 2017) üzerinden Python dil ve Visual Studio uzantısı için boş Python araçları desteği (Visual Studio 2015 ve daha önce).

Python Mac için Visual Studio şu anda desteklenmez, ancak Mac ve Linux Visual Studio Code ile kullanılabilir (bkz [sorular ve yanıtlar](#questions-and-answers)).

Başlamak için:

- İzleyin [yükleme yönergeleri](installing-python-support-in-visual-studio.md) Python iş yükü çalışma ayarlamak için.
- Visual Studio Python özelliklerini bu makalede bölümlerine tanıyın. Ayrıca [video serisi (Microsoft Virtual Academy) izleme](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121) giriş (toplam 22 dakika) Visual Studio'da Python için.
- Bir veya daha fazla proje oluşturmak için hızlı başlangıç ipuçları gidin. Emin değilseniz, başlayın [Flask ile bir web uygulaması oluşturma](../ide/quickstart-python.md?context=visualstudio/python/default).
- İzleyin [Visual Studio'da Python ile çalışma](tutorial-working-with-python-in-visual-studio-step-01-create-project.md) baştan sona tam bir deneyim Öğreticisi.

## <a name="support-for-multiple-interpreters"></a>Birden çok yorumlayıcılar desteği

Visual Studio'nun **Python ortamları** (aşağıda bir geniş, Genişletilmiş görünümde gösterilen) penceresi tüm genel Python ortamları, conda ortamları ve sanal ortamları yönetmek için tek bir yer sağlar. Visual Studio otomatik olarak standart konumlarda Python yüklemelerini algılar ve özel yüklemeler yapılandırmanıza olanak sağlar. Her ortam ile kolayca paketleri yönetebilir, bu ortam için etkileşimli bir pencere aç ve ortam klasörlere erişim.

![Genişletilmiş Görünüm Python ortamları penceresi](media/environments-expanded-view.png)

Daha fazla bilgi için:

- Video (2m 35s): [Python ortamları yönetme](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=qrDmN4LWE_8305918567)
- Belgeler: [yönetme Python ortamları](managing-python-environments-in-visual-studio.md)
- Belgeler: [Python ortamları penceresi başvurusu](python-environments-window-tab-reference.md)

## <a name="rich-editing-intellisense-and-code-comprehension"></a>Zengin düzenleme, IntelliSense ve kod kavrama

Visual Studio söz dizimi renklendirme, tüm kod ve kitaplıklarını arasında otomatik tamamlama kod biçimlendirme dahil birinci sınıf bir Python Düzenleyicisi sağlar, imza Yardım, yeniden düzenleme, (aşağıda gösterilen), linting ve ipuçlarını yazın. Visual Studio sınıf görünümü gibi benzersiz özellikleri de sağlar, tanımı, tüm başvuruları Bul ve kod parçacıkları gidin. Doğrudan ile tümleştirme [etkileşimli pencere](#interactive-window) hızlı bir şekilde önceden bir dosyaya kaydedilir Python kodu geliştirmenize yardımcı olur.

![Visual Studio'da Python kodu için kod tamamlamalar](media/code-editing-completions-simple.png)

Daha fazla bilgi için:

- Video (2m 30s): [düzenleme Python kodu](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=r2iQH5LWE_4605918567)
- Belgeler: [düzenleme Python kodu](editing-python-code-in-visual-studio.md)
- Belgeler: [kod biçimlendirme](formatting-python-code.md)
- Belgeler: [yeniden düzenleme](refactoring-python-code.md)
- Belgeler: [Linting](linting-python-code.md)
- Genel Visual Studio özellik belgeleri: [Kod Düzenleyicisi özellikleri](../ide/writing-code-in-the-code-and-text-editor.md)

## <a name="interactive-window"></a>Etkileşimli penceresi

Visual Studio için bilinen her Python ortamı için ayrı bir komut istemi kullanmak yerine Visual Studio içinde doğrudan bir Python yorumlayıcısı için aynı etkileşimli (REPL) ortamında kolayca açabilirsiniz. De ortamlar arasında kolayca geçiş yapabilirsiniz.

![Visual Studio'da Python etkileşimli penceresi](media/interactive-window.png)

Visual Studio ayrıca Python kod düzenleyicisini ve etkileşimli pencere arasında sıkı tümleştirme sağlar. **Ctrl + Enter** klavye kısayolu rahat kod (veya kod bloğu) Düzenleyicisi'nde geçerli satırının etkileşimli penceresine gönderir ve ardından sonraki satırı (veya blok) taşır. **Ctrl + Enter** kolayca hata ayıklayıcı çalıştırmak zorunda kalmadan kodlarda adım sağlar. Ayrıca aynı tuş vuruşu ile etkileşimli penceresinde seçili kod Gönder ve kolayca etkileşimli penceresinden kod düzenleyicisine yapıştırın. Birlikte, bu özellikler, etkileşimli penceresinde kod kesimi ayrıntılarını çıkışı çalışma ve kolayca Düzenleyicisi dosyasında sonuçları kaydetmek izin verir.

Visual Studio IPython/Jupytr satır içi çizimler, .NET ve Windows Presentation Foundation (WPF) dahil olmak üzere REPL içinde de destekler.

Daha fazla bilgi için:

- Video (2m 22s: [Python etkileşimli penceresi](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=gJYKY5LWE_4605918567)
- Belgeler: [etkileşimli penceresi](python-interactive-repl-in-visual-studio.md)
- Belgeler: [IPython Visual Studio'da](interactive-repl-ipython.md)

## <a name="project-system-and-project-and-item-templates"></a>Proje sistemi ve proje ve öğe şablonları

Visual Studio zamanla büyüdükçe proje karmaşıklığını yönetmenize yardımcı olur. Bir klasör yapısını çok daha bir projedir: anlayarak içerir birbirleriyle nasıl ilişkili olduğunu ve nasıl farklı dosya kullanılır. Visual Studio, uygulama kodu ayırt etmek, kod, web sayfaları, JavaScript, yapı komut dosyaları vb., dosya uygun özellikleri etkinleştiren test yardımcı olur. Visual Studio çözümü, ayrıca, bir Python projesi ve C++ uzantısı projesi gibi birden çok ilgili projeleri yönetmenize yardımcı olur.

![Python ve C++ projeleri içeren bir Visual Studio çözümü](media/projects-solution-explorer-two-projects.png)

Proje ve öğe şablonları projeleri ve dosyaların farklı türleri ayarlama, önemli ölçüde zaman kaydetme ve karmaşık ve hatalara eğilimli ayrıntılarını yönetme gereksinimini azaltır işlemini otomatikleştirir. Visual Studio, web, Azure, veri bilimi, konsolu ve diğer dosyalar gibi Python sınıfları, birim testleri, Azure web yapılandırması, HTML ve hatta Django uygulamaları için şablonlar birlikte proje türleri için şablonlar sağlar.

[![Visual Studio'da Python proje ve öğe şablonları](media/project-and-item-templates.png)](media/project-and-item-templates.png)

Daha fazla bilgi için:

- Belgeler: [yönetme Python projeleri](managing-python-projects-in-visual-studio.md)
- Belgeler: [öğe şablonları başvurusu](python-item-templates.md)
- Belgeler: [Python proje şablonları](managing-python-projects-in-visual-studio.md#project-templates)
- Belgeler: [C++ ve Python ile çalışma](working-with-c-cpp-python-in-visual-studio.md)
- Genel Visual Studio özellik belgeleri: [proje ve öğe şablonları](../ide/creating-project-and-item-templates.md#visual-studio-templates)
- Genel Visual Studio özellik belgeleri: [çözümler ve projeler Visual Studio'da](../ide/solutions-and-projects-in-visual-studio.md)

## <a name="full-featured-debugging"></a>Tam özellikli hata ayıklama

Visual Studio'nun gücü kendi güçlü hata ayıklayıcı biridir. Python için özel olarak, Visual Studio Python/C++ karışık mod hata ayıklaması, Linux üzerinde uzaktan hata ayıklama, Azure üzerinde uzaktan hata ayıklama, etkileşimli pencereye hata ayıklama ve Python birim testleri hata ayıklama içerir.

![Bir özel durum açılan gösteren Python için Visual Studio hata ayıklayıcısı](media/debugging-exception-popup.png)

Daha fazla bilgi için:

- Video: [Python 3 m 32s hata ayıklama](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=Ep5dp5LWE_3805918567)
- Belgeler: [Python hata ayıklama](debugging-python-in-visual-studio.md)
- Belgeler: [Python/C++ karışık mod hata ayıklaması](debugging-mixed-mode-c-cpp-python-in-visual-studio.md)
- Belgeler: [Linux'ta uzaktan hata ayıklama](debugging-python-code-on-remote-linux-machines.md)
- Belgeler: [Azure üzerinde uzaktan hata ayıklama](debugging-remote-python-code-on-azure.md)
- Genel Visual Studio özellik belgeleri: [Visual Studio hata ayıklayıcısı özelliği turu](../debugger/debugger-feature-tour.md)

## <a name="profiling-tools-with-comprehensive-reporting"></a>Kapsamlı Raporlama ile Profil Araçları

Profil oluşturma saati uygulamanızdaki nasıl harcandığını araştırır. Visual Studio ile CPython tabanlı yorumlayıcılar profil destekler ve farklı profil çalıştırmalarını arasındaki performans karşılaştırma yeteneğini içerir.

[![Python projesi için Visual Studio profil oluşturucu sonuçları](media/profiling-results.png)](media/profiling-results.png)

Daha fazla bilgi için:

- Video: [Python 3 m 00s profil oluşturma](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=s6FoC6LWE_1005918567)
- Belgeler: [Python Profil Araçları](profiling-python-code-in-visual-studio.md)
- Genel Visual Studio özellik belgeleri: [Profil özelliği Turu](../profiling/profiling-feature-tour.md). (Tüm Visual Studio profil özellikleri, Python için kullanılabilir).

## <a name="unit-testing-tools"></a>Birim test araçları

Bul, çalıştırmak, Visual Studio Test Gezgini testlerinde yönetmek ve kolayca birim testleri hata ayıklama.

![Python birim testi Visual Studio'da hata ayıklama](media/unit-test-debugging.png)

Daha fazla bilgi için:

- Video: [Python 2 m 31s test etme](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=hb46k6LWE_405918567)
- Belgeler: [birim test için Python araçları](unit-testing-python-in-visual-studio.md)
- Genel Visual Studio özellik belgeleri: [birim testi kodunuzu](../test/unit-test-your-code.md).

## <a name="publishing-to-azure-and-azure-sdk-for-python"></a>Azure ve Azure yayımlama için Python SDK'sı

Visual Studio, web uygulamaları ve bulut Hizmetleri için Azure yayımlama için tümleşik destek sağlar. Visual Studio içerir temel `web.config` öğe şablonlarını dinamik ve statik içerik. Python iş yükü ayrıca Windows, Mac OS X ve Linux uygulamaları Süren Azure hizmetlerinden basitleştirir Python için Azure SDK'sı içerir.

![Visual Studio'da Python uygulamayı Azure'a yayımlama](media/azure-publish-dialog.png)

Daha fazla bilgi için:

- Belgeler: [Azure'a yayımlama](publishing-python-web-applications-to-azure-from-visual-studio.md)
- Belgeler: [Python için Azure SDK](azure-sdk-for-python.md)

## <a name="python-training-on-microsoft-virtual-academy"></a>Microsoft Virtual Academy üzerinde Python eğitim

|   |   |
|---|---|
| ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin") | <ul><li>[Python ile programlamaya giriş](https://mva.microsoft.com/en-US/training-courses/introduction-to-programming-with-python-8360?l=lqhuMxFz_8904984382)</li><li>[Python başlangıç: Dizeler ve İşlevler](https://mva.microsoft.com/en-US/training-courses/python-beginner-strings-and-functions-18015)</li><li>[Python temelleri: Listesi ve döngüler](https://mva.microsoft.com/en-US/training-courses/python-fundamentals-lists-and-loops-18019)</li><li>[Üst Python sorular](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121)</li></ul> |

## <a name="questions-and-answers"></a>Sorular ve yanıtlar

**Q. Python desteği Mac için Visual Studio ile var mı?**

BİR. Şu anda değil, ancak en fazla istek oy kullanabilir [UserVoice](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac/suggestions/18670291-python-tools-for-visual-studio-mac). [Mac için Visual Studio](/visualstudio/mac/) belgelerine destekliyor mu geliştirme geçerli türlerini tanımlar. Bu arada, Visual Studio Code Windows, Mac ve Linux [çalışır kullanılabilir uzantıları yoluyla Python ile iyi](https://code.visualstudio.com/docs/languages/python).

**Q. Ne Python ile kullanıcı Arabirimi oluşturmak için kullanabilir miyim?**

BİR. Bu alandaki ana bir tekliftir [Qt proje](https://www.qt.io/qt-for-application-development/), olarak bilinen Python için bağlamalarla [PySide (resmi bağlama)](http://wiki.qt.io/PySide) (Ayrıca bkz. [PySide indirmeleri](https://download.qt.io/official_releases/pyside/.)) ve [ PyQt](https://wiki.python.org/moin/PyQt). Şu anda herhangi belirli araçları UI geliştirme için Visual Studio'da Python desteği içermez.

**Q. Python proje tek başına yürütülebilir dosya oluşturabilir mi?**

BİR. Python ile kod Visual Studio ile web sunucuları gibi uygun bir Python özellikli ortamda isteğe bağlı çalıştığı bir yorumlama dili genellikle içindir. Visual Studio kendisini şu anda temelde katıştırılmış bir Python yorumlayıcısı sahip bir program anlamına gelir bir tek başına yürütülebilir oluşturulacağı anlamına gelir sağlamaz. Ancak, yürütülebilir dosyalar açıklandığı gibi oluşturmak için çeşitli anlamına gelir Python topluluk içinde vardır [StackOverflow](http://stackoverflow.com/questions/5458048/how-to-make-a-python-script-standalone-executable-to-run-without-any-dependency). CPython de destekler yerel bir uygulama içinde yerleşik blog gönderisi konusunda açıklandığı gibi [kullanarak CPython'ın gömülebilir ZIP dosyasını](https://blogs.msdn.microsoft.com/pythonengineering/2016/04/26/cpython-embeddable-zip-file/).

## <a name="features-matrix"></a>Özellikler Matrisi

Python özellikleri açıklandığı gibi aşağıdaki Visual Studio sürümlerinde yüklenebilir [Yükleme Kılavuzu](installing-python-support-in-visual-studio.md):

- [Visual Studio 2017 (tüm sürümler)](https://visualstudio.microsoft.com/vs/)
- Visual Studio 2015 (tüm sürümler)
- Visual Studio 2013 Community Edition
- Web, güncelleştirme 2 veya üzeri için Visual Studio 2013 Express
- Masaüstü, güncelleştirme 2 veya üzeri için Visual Studio 2013 Express
- Visual Studio 2013'ün (Pro sürümü veya üzeri)
- Visual Studio 2012 (Pro sürümü veya üzeri)
- Visual Studio 2010 SP1 (Pro sürümü veya üzeri; .NET 4.5 gerekiyor)

Visual Studio 2015 ve önceki kullanılabilir [visualstudio.com/vs/older-downloads/](https://visualstudio.microsoft.com/vs/older-downloads/).

> [!Important]
> Özelliklerin tam olarak desteklenir ve yalnızca en son sürümü Visual Studio için sağlanmıştır. Özellikleri, eski sürümlerinde kullanılabilir, ancak etkin bir şekilde korunmuyor.

| Python desteği | 2017 | 2015 | 2013 Comm | 2013 Masaüstü | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Birden çok yorumlayıcılar yönetme | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Popüler yorumlayıcılar otomatik algıla | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Özel yorumlayıcılar ekleme | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Sanal ortamlar | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| PIP/kolay yükleme | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Proje Sistemi | 2017 | 2015 | 2013 Comm | 2013 Masaüstü | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Var olan koddan yeni proje | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Tüm dosyaları göster | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Kaynak denetimi | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Git tümleştirmesi | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004;<sup>1</sup> | &#10007; |
<br/>

| Düzenleme | 2017 | 2015 | 2013 Comm | 2013 Masaüstü | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| söz dizimi vurgulama | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Otomatik Tamamlama | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| İmza Yardım | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Hızlı bilgi | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Nesne Tarayıcısı/sınıf görünümü | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Gezinti çubuğu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Tanıma gitme | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Gidin | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Tüm Başvuruları Bul | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Otomatik Girinti | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Kod biçimlendirme | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Yeniden Düzenle - yeniden adlandır | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Yeniden Düzenle - ayıklama yöntemi | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Yeniden Düzenle - alma Ekle/Kaldır | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| PyLint | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Etkileşimli penceresi | 2017 | 2015 | 2013 Comm | 2013 Masaüstü | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Etkileşimli penceresi | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Satır içi grafikleri ile IPython | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Masaüstü | 2017 | 2015 | 2013 Comm | 2013 Masaüstü | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Windows konsol uygulaması | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| IronPython WPF (ile XAML Tasarımcısı) | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| IronPython Windows Forms | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Web | 2017 | 2015 | 2013 Comm | 2013 Masaüstü | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Django web projesi | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Bottle web projesi | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Flask web projesi | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Genel web projesi | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Azure | 2017 | 2015 | 2013 Comm | 2013 Masaüstü | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Web sitesine dağıtma | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004;<sup>2</sup> |
| Web rolü için dağıtma | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
| Çalışan rolü için dağıtma | ? | ? | ? | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
| Azure öykünücüsünde çalıştırın | ? | ? | ? | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
| Uzaktan hata ayıklama | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>6</sup> | &#10004;<sup>8</sup> | &#10004;<sup>8</sup> | &#10007; |
| Sunucu Gezgini ekleme | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>7</sup> | &#10004;<sup>7</sup> | &#10007; | &#10007; |
<br/>

| Django şablonları | 2017 | 2015 | 2013 Comm | 2013 Masaüstü | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Hata Ayıklama | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Otomatik Tamamlama | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>5</sup> | &#10004;<sup>5</sup> | &#10004; | &#10004; |
| CSS ve JavaScript için otomatik olarak tamamlama | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>5</sup> | &#10004;<sup>5</sup> | &#10007; | &#10007; |
<br/>

| Hata Ayıklama | 2017 | 2015 | 2013 Comm | 2013 Masaüstü | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Hata Ayıklama | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Projeyi olmadan hata ayıklama | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Hata ayıklama - düzenlemeye ekleme | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; |
| Karışık mod hata ayıklaması | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
| Uzaktan hata ayıklama (Windows, Mac OS X, Linux) | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; |
| Hata ayıklama etkileşimli penceresi | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

<a name="matrix-profiling"></a>

| Profil Oluşturma | 2017 | 2015 | 2013 Comm | 2013 Masaüstü | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Profil Oluşturma | &#10004; | &#10004; | &#10004; | &#10007; | &#10007; | &#10004; | &#10004; | &#10004; |
<br/>

| Test | 2017 | 2015 | 2013 Comm | 2013 Masaüstü | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Test Gezgini | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
| Testi çalıştırma | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
| Test hata ayıklama | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
<br/>

1. Visual Studio 2012 için Git desteği, Git uzantısı, kullanılabilir için Visual Studio Araçları kullanılabilir [Visual Studio Galerisi](http://visualstudiogallery.msdn.microsoft.com/abafc7d6-dcaa-40f4-8a5e-d6724bdb980c).

1. Dağıtımı için Azure Web sitesi gerektirir [.NET 2.1 - Visual Studio 2010 SP1 için Azure SDK](http://go.microsoft.com/fwlink/?LinkId=313855). Sonraki sürümleri, Visual Studio 2010 desteklemez.

1. Azure Web rolü ve çalışan rolü için destek gerektiren [.NET 2.3 - VS 2012 için Azure SDK](http://go.microsoft.com/fwlink/?LinkId=323511) veya sonraki bir sürümü.

1. Azure Web rolü ve çalışan rolü için destek gerektiren [.NET 2.3 - VS 2013 için Azure SDK](http://go.microsoft.com/fwlink/?LinkId=323510) veya sonraki bir sürümü.

1. Django Şablon Düzenleyicisi'nde Visual Studio 2013 güncelleştirme 2 yükleyerek çözülmüş bilinen bazı sorunlar vardır.

1. Windows 8 veya sonraki sürümünü gerektirir. Web için Visual Studio 2013 Express ekleme işlemi iletişim sahip değil, ancak Azure Web sitesi uzaktan hata ayıklama sunucu Gezgini'nde Attach hata ayıklayıcısı (Python) komutunu kullanarak yine de mümkündür. Uzaktan hata ayıklama gerektirir [.NET 2.3 - Visual Studio 2013 için Azure SDK](http://go.microsoft.com/fwlink/?LinkId=323510) veya sonraki bir sürümü.

1. Windows 8 veya sonraki sürümünü gerektirir. Hata ayıklayıcısını (Python) Sunucu Gezgininde komut gerektirir [.NET 2.3 - Visual Studio 2013 için Azure SDK](http://go.microsoft.com/fwlink/?LinkId=323510) veya sonraki bir sürümü.

1. Windows 8 veya sonraki sürümünü gerektirir.

## <a name="additional-resources"></a>Ek kaynaklar

- [IIS ve Python arasında Wfastcgı köprü](https://pypi.org/p/wfastcgi) (pypi.org)
- [Microsoft Virtual Academy boş Python kursları](https://mva.microsoft.com/search/SearchResults.aspx#!q=python)
- [Microsoft sanal Akademi üst Python sorular](https://aka.ms/mva-top-python-questions)
