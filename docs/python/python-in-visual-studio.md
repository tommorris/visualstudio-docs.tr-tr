---
title: Visual Studio'da Python | Microsoft Docs
ms.custom: 
ms.date: 09/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: hero-article
caps.latest.revision: "11"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: f831aa683efdacc8a01ffbf5ef5a280c1a95f9e3
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/14/2017
---
# <a name="working-with-python-in-visual-studio"></a>Visual Studio'da Python ile çalışma

Python güvenilir, esnek, kolay öğrenmek için tüm işletim sistemlerinde kullanımına yönelik ücretsiz ve sağlam Geliştirici topluluğu ve pek çok ücretsiz kitaplıkları tarafından desteklenen popüler bir programlama dilidir. Python geliştirme, web uygulamaları, web Hizmetleri, Masaüstü uygulamaları, komut dosyası ve bilimsel hesaplama dahil olmak üzere tüm yolla destekler ve birçok üniversiteler, bilimcilerine, rasgele geliştiriciler ve profesyonel geliştiricilere benzer tarafından kullanılır. Üzerinde dili hakkında daha fazla bilgiyi [python.org](https://www.python.org) ve [yeni başlayanlar için Python](https://www.python.org/about/gettingstarted/).

Visual Studio Windows sağlar [açık kaynak](https://github.com/Microsoft/ptvs) Python geliştirme ve veri bilimi iş yüklerini (Visual Studio 2017) aracılığıyla Python dil ve Visual Studio Uzantısı (Visual Studio 2015 için boş Python araçları desteği ve önceki sürüm). Python Mac için Visual Studio şu anda desteklenmez, ancak Mac ve Linux Visual Studio Code ile kullanılabilir (bkz [soru- cevap aşağıda](#questions-and-answers).

Başlamak için:

- İzleyin [yükleme yönergeleri](installation.md) Python iş yükü çalışma ayarlamak için
- Bir veya daha fazla proje oluşturmak için hızlı başlangıç ipuçları gidin. Emin değilseniz, başlayın [bir şablondan bir proje oluştur](quickstart-02-project-from-template.md).
- İzleyin [Visual Studio'da Python ile çalışma](vs-tutorial-01-01.md) baştan sona tam bir deneyim Öğreticisi.
- Ardından Python güvenlikle ilgili özellikler ve Visual Studio kendisini özelliklerini keşfetmek için aşağıdaki bağlantıları kullanın.

| Özellik | Açıklama | Genel Visual Studio belgeleri | 
| --- | --- | --- |
| [Visual Studio Proje sistemi](python-projects.md) | Örtük olarak Çekmeleri web sayfaları, JavaScript, uygulama kodu, test kodu tanımlamak açık denetim verirken Python kodu bir klasör yapısını, komut dosyaları, vb. oluşturun. | [Visual Studio’da Çözümler ve Projeler](../ide/solutions-and-projects-in-visual-studio.md) |
| [Proje şablonları](python-projects.md#project-templates) | Proje yapısı konsol, web, Azure, veri bilimi ve diğer proje türleri için hızlı bir şekilde oluşturur | [Visual Studio şablonları](../ide/creating-project-and-item-templates.md#visual-studio-templates) |
| Birden çok yorumlayıcı desteği | CPython ve IronPython çeşitli sürümlerini destekler. | yok |
| IPython desteği | Satır içi çizimler, .NET ve Windows Presentation Foundation (WPF) için REPL IPython/Jupyter için destek içerir. | yok |
| [Zengin düzenleme, IntelliSense ve kod kavrama](code-editing.md) | Tüm kod ve kitaplıklarını arasında otomatik tamamlama söz dizimi renklendirme içeren [kod biçimlendirme](code-formatting.md), imza Yardım, sınıf görünümü gidin tanımı, tüm başvuruları Bul, kod parçacıkları [yeniden düzenleme](code-refactoring.md), [ PyLint](code-pylint.md)ve daha fazlası. | [Kod ve Metin Düzenleyici'de Kod Yazma](../ide/writing-code-in-the-code-and-text-editor.md) |
| [Etkileşimli penceresi](interactive-repl.md) | Hızlı bir REPL deneyimi Python için kolayca kodunuzu bir kısmı vurgulayın ve etkileşimli penceresine gönderme olanağı sağlar. | yok |
| [Tam özellikli hata ayıklama](debugging.md) | Hata ayıklama yapılabilir olan veya varolan bir yürütülebilir dosyada hata ayıklama özelliği de dahil olmak üzere bir Visual Studio projesi olmayan [Python/C++ karışık mod hata ayıklaması](debugging-mixed-mode.md), [uzaktan hata ayıklama](debugging-cross-platform-remote.md) Windows/Linux/Mac için [Azure'a uzaktan hata ayıklama](debugging-azure-remote.md)ve etkileşimli pencereye hata ayıklama. | [Visual Studio'da hata ayıklama](../debugger/debugging-in-visual-studio.md) |
| [Kapsamlı Raporlama ile Profil Araçları](profiling.md) | Ne zaman farklı profil çalıştırmalarını arasındaki performans Karşılaştırılacak özelliği de dahil, uygulamanızda harcandığını araştırır. | [Profil Araçları](../profiling/profiling-tools.md) (tüm Visual Studio profil özellikleri Python için kullanılabilir) |
| [Birim test araçları](unit-testing.md) | Bul, çalıştırmak, Visual Studio Test Gezgini testlerinde yönetmek ve kolayca birim testleri hata ayıklama. | [Birim testi kodunuz](../test/unit-test-your-code.md) |

Python iş yükü de içeren [Python için Azure SDK](azure-sdk-for-python.md), Windows, Mac OS X ve Linux uygulamalardan Azure Hizmetleri kullanma basitleştirir.

Kısa bir video giriş için bkz [Visual Studio için Python Araçları](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121) ilgili Microsoft Virtual Academy (yaklaşık 22 dakika toplam). 

> [!VIDEO https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Installing-Visual-Studio-Python-Support-go1id3LWE_1705918567]


## <a name="questions-and-answers"></a>Sorular ve yanıtlar

**Q. Python desteği Mac için Visual Studio ile var mı?**

BİR. Değil şu anda rağmen istenen üzerinde [UserVoice](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac/suggestions/18670291-python-tools-for-visual-studio-mac). [Mac için Visual Studio](https://docs.microsoft.com/visualstudio/mac/) belgelerine destekliyor mu geliştirme geçerli türlerini tanımlar. Bu arada, Visual Studio Code Windows, Mac ve Linux [çalışır kullanılabilir uzantıları yoluyla Python ile iyi](https://code.visualstudio.com/docs/languages/python).

**Q. Ne Python ile kullanıcı Arabirimi oluşturmak için kullanabilir miyim?**

BİR. Bu alandaki ana bir tekliftir [Qt proje](https://www.qt.io/qt-for-application-development/), olarak bilinen Python için bağlamalarla [PySide (resmi bağlama)](http://wiki.qt.io/PySide) (Ayrıca bkz. [PySide indirmeleri](https://download.qt.io/official_releases/pyside/.)) ve [ PyQt](https://wiki.python.org/moin/PyQt). Şu anda herhangi belirli araçları UI geliştirme için Visual Studio'da Python desteği içermez.

**Q. Python proje tek başına yürütülebilir dosya oluşturabilir mi?**

BİR. Python ile kod Visual Studio ile web sunucuları gibi uygun bir Python özellikli ortamda isteğe bağlı çalıştığı bir yorumlama dili genellikle içindir. Visual Studio kendisini şu anda temelde katıştırılmış bir Python yorumlayıcısı sahip bir program anlamına gelir bir tek başına yürütülebilir oluşturulacağı anlamına gelir sağlamaz. Ancak, yürütülebilir dosyalar açıklandığı gibi oluşturmak için çeşitli anlamına gelir Python topluluk içinde vardır [StackOverflow](http://stackoverflow.com/questions/5458048/how-to-make-a-python-script-standalone-executable-to-run-without-any-dependency). CPython de destekler yerel bir uygulama içinde yerleşik blog gönderisi konusunda açıklandığı gibi [kullanarak CPython'ın gömülebilir ZIP dosyasını](https://blogs.msdn.microsoft.com/pythonengineering/2016/04/26/cpython-embeddable-zip-file/).

## <a name="features-matrix"></a>Özellikler Matrisi

Python desteği açıklandığı gibi aşağıdaki Visual Studio sürümlerinde yüklenebilir [Yükleme Kılavuzu](installation.md):

- [Visual Studio 2017 (tüm sürümler)](https://www.visualstudio.com/vs/)
- [Visual Studio 2015 (tüm sürümler)] (https://www.visualstudio.com/en-us/downloads/visual-studio-2015-downloads-vs)
- Visual Studio 2013 Community Edition
- Web, güncelleştirme 2 veya üzeri için Visual Studio 2013 Express
- Masaüstü, güncelleştirme 2 veya üzeri için Visual Studio 2013 Express
- Visual Studio 2013'ün (Pro sürümü veya üzeri)
- Visual Studio 2012 (Pro sürümü veya üzeri)
- Visual Studio 2010 SP1 (Pro sürümü veya üzeri; .NET 4.5 gerekiyor)

Visual Studio sürümü tarafından desteklenen özellikler:

| Python desteği | 2017 | 2015 | 2013 Comm | 2013 Masaüstü | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Birden çok yorumlayıcılar Yönetimi | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Popüler yorumlayıcılar otomatik algıla | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Özel yorumlayıcılar ekleme | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Sanal ortamlar | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| PIP/kolay yükleme | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Proje sistemi | 2017 | 2015 | 2013 Comm | 2013 Masaüstü | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
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

1. Visual Studio Araçları Git uzantısı, kullanılabilir VS 2012 Git desteğini kullanılabilir [Visual Studio Galerisi](http://visualstudiogallery.msdn.microsoft.com/abafc7d6-dcaa-40f4-8a5e-d6724bdb980c).

2. Dağıtımı için Azure Web sitesi gerektirir [.NET 2.1 - VS 2010 SP1 için Azure SDK](http://go.microsoft.com/fwlink/?LinkId=313855).  Sonraki sürümlerde VS 2010 desteklemez.

3. Azure Web rolü ve çalışan rolü için destek gerektiren [.NET 2.3 - VS 2012 için Azure SDK](http://go.microsoft.com/fwlink/?LinkId=323511) veya sonraki bir sürümü.

4. Azure Web rolü ve çalışan rolü için destek gerektiren [.NET 2.3 - VS 2013 için Azure SDK](http://go.microsoft.com/fwlink/?LinkId=323510) veya sonraki bir sürümü.

5. Django Şablon Düzenleyicisi'nde Visual Studio 2013 güncelleştirme 2 yükleyerek çözülmüş bilinen bazı sorunlar vardır.

6. Windows 8 veya sonraki sürümünü gerektirir. Web için Visual Studio 2013 Express ekleme işlemi iletişim sahip değil, ancak Azure Web sitesi uzaktan hata ayıklama sunucu Gezgini'nde Attach hata ayıklayıcısı (Python) komutunu kullanarak yine de mümkündür. Uzaktan hata ayıklama gerektirir [.NET 2.3 - VS 2013 için Azure SDK](http://go.microsoft.com/fwlink/?LinkId=323510) veya sonraki bir sürümü.

7. Windows 8 veya sonraki sürümünü gerektirir. Hata ayıklayıcısını (Python) Sunucu Gezgininde komut gerektirir [.NET 2.3 - VS 2013 için Azure SDK](http://go.microsoft.com/fwlink/?LinkId=323510) veya sonraki bir sürümü.

8. Windows 8 veya sonraki sürümünü gerektirir.

## <a name="additional-resources"></a>Ek kaynaklar

- [Kinect oyunlar PyKinect kullanarak Python ile yazma](https://github.com/Microsoft/PTVS/wiki/PyKinect) (GitHub wiki)
- [IIS ve Python arasında Wfastcgı köprü](https://pypi.python.org/pypi/wfastcgi) (python.org)
- [Microsoft Virtual Academy boş Python kursları](https://mva.microsoft.com/search/SearchResults.aspx#!q=python)
- [Microsoft sanal Akademi üst Python sorular](https://aka.ms/mva-top-python-questions)
