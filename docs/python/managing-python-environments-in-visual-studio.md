---
title: "Visual Studio'da Python ortamları yönetme | Microsoft Docs"
description: "Genel yönetmek için Visual Studio ve Python yorumlayıcılar yükleme, paketleri yükleme, arama yolları ayarlama ve ortamlar için Visual Studio Projeleri Yönetme özel ortamları ayarlama sanal ortamlar Python ortamları penceresini kullanma"
ms.custom: 
ms.date: 01/16/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 40f901c65872fe593457883c36f0d60bf7e2fd8a
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="python-environments"></a>Python ortamları

Bir Python *ortam* Python kodu çalıştırmak bir bağlam. Bir ortam bir yorumlayıcı, bir kitaplık (genellikle Python standart kitaplığı) ve yüklü paketler kümesini oluşur. Bu bileşenlerin, birlikte hangi dil yapıları ve sözdizimi geçerli olduğunu belirlemek hangi işletim sistemi işlevselliği erişebilir ve hangi paketleri kullanabilirsiniz.

Visual Studio'da, tüm kullanarak ortamlarınızı yönetmek [Python ortamları penceresi](#managing-python-environments-in-visual-studio) bu makalede anlatıldığı gibi. Verilen herhangi bir projeye için hata ayıklama, kod, denetimi sözdizimi çalıştırmak için kullanılacak bir ortam alma ve üye tamamlamalar görüntüleme seçin ve diğer görevler için yorumlayıcı özeldir ve kitaplıkların yüklü. Visual Studio ayrıca kod girerken otomatik tamamlanmasını sağlayan her ortam için IntelliSense veritabanını korur.

Visual Studio sanal ortamlar için de destek sağlar `requirements.txt` dosyaları ve arama yolları.

**Not**: Visual Studio'da Python yeniyseniz, gerekli arka plan için aşağıdaki makalelere bakın:

- [Visual Studio'da Python ile çalışma](overview-of-python-tools-for-visual-studio.md)
- [Visual Studio'da Python desteğini yükleme](installing-python-support-in-visual-studio.md)

## <a name="global-and-virtual-environments"></a>Genel ve sanal ortamlar

Python ortamları iki tür vardır: Genel ve sanal.

**Genel ortamları**: her Python yükleme (örneğin, Python 2.7, Python 3.6 ve Anaconda 4.4.0, bkz: [seçerek ve Python yorumlayıcılar yükleme](#selecting-and-installing-python-interpreters) kendi ortamı korur. Her ortam belirli Python Yorumlayıcı, kendi standart kitaplığı ve önceden yüklenmiş paket kümesini oluşur. Bir paket genel bir ortama yükleme bu ortam kullanarak tüm projeleri için kullanılabilir kılar. Ortamında bir dosya sistemini koruma alanında bulunuyorsa (içinde `c:\program files`, örneğin), sonra da paketler yönetici ayrıcalıkları gerektirir.

Genel ortamları, bilgisayardaki tüm projeleri için kullanılabilir. Visual Studio'da bir proje için farklı bir özellikle seçmediğiniz sürece, tüm projeleri için kullanılan varsayılan olarak genel bir ortam seçin. Daha fazla bilgi için bkz: [bir proje için bir ortam seçerek](#selecting-an-environment-for-a-project).

**Sanal ortamlar**: genel bir ortama yüklenmişse paketler bu ortam kullanan tüm projeleri için kullanılabilir olduğundan, iki proje uyumsuz paketleri veya aynı paketin farklı sürümlerini gerektirdiğinde çakışmaları oluşabilir. Sanal ortamlar bu gibi çakışmaları yorumlayıcı ve standart kitaplığı genel ortamından kullanarak ancak kendi yalıtılmış klasörleri paket depolarında koruma kaçının.

Visual Studio'da bir alt proje klasöründe depolanan belirli bir proje için sanal bir ortam oluşturabilirsiniz (bkz [sanal ortamları oluşturma](#creating-virtual-environments). Proje dosyası, aynı zamanda sanal ortam tanımlar. Visual Studio ayrıca, projenin bu sanal ortama yükleme herhangi bir paket kaydeder `requirements.txt` dosya. Proje sonra paylaşımı ve isteğe bağlı olarak diğer geliştiriciler bilgisayarlarında açarsanız, Visual Studio sanal ortamı yeniden oluşturmak için seçeneği sağlar.

### <a name="selecting-and-installing-python-interpreters"></a>Seçme ve Python yorumlayıcılar yükleniyor

Varsayılan olarak Visual Studio 2017 Python geliştirme iş yükü yükleme Python 3 (64 bit) yükler. İsteğe bağlı olarak 32-bit ve 64 bit sürümlerini Python 2, Python 3, Anaconda 2 ve Anaconda 3 ' ü yüklemek açıklandığı gibi seçebileceğiniz [yükleme](installing-python-support-in-visual-studio.md). Aşağıdaki tabloda listelenen yorumlayıcılar birini el ile de yükleyebilirsiniz.

Ve önceki sürümleri, Visual Studio 2015 için yorumlayıcılar biri el ile yüklemelisiniz.

Visual Studio (tüm sürümler) her kayıt defteri denetleyerek Python yorumlayıcı yüklü bir ortamda otomatik olarak oluşturur (aşağıdaki [CESARETLENDİRİCİ 514 - Python kayıt Windows kayıt defterinde](https://www.python.org/dev/peps/pep-0514/)). Visual Studio yüklü bir ortam algılamazsa bkz [bir ortam için varolan bir yorumlayıcı oluşturma](#creating-an-environment-for-an-existing-interpreter).

| Interpreter | Açıklama |
| --- | --- |
| [CPython](https://www.python.org/) | "Yerel" ve en sık kullanılan Yorumlayıcı, 32 bit ve 64 bit sürümleri (32-bit önerilir) içinde kullanılabilir. En son dil özellikleri, maksimum Python paket uyumluluk, hata ayıklama için tam destek ve birlikte çalışma içeren [IPython](http://ipython.org/). Ayrıca bkz: [Python 2 veya Python 3 kullanmalıyım?](http://wiki.python.org/moin/Python2orPython3). Visual Studio 2015 ve önceki Python 3.6 desteklemez ve "Python sürümü 3.6 desteklenmiyor" hata verebilirsiniz unutmayın. Python 3.5 veya önceki kullanmak yerine. |
| [IronPython](https://github.com/IronLanguages/ironpython2) | Bir .NET uygulaması sağlama C# /F #/ Visual Basic birlikte çalışabilirliği, Python, 32 bit ve 64 bit sürümlerinde kullanılabilir olan erişim .NET API'leri, hata ayıklama standart Python (ancak değil C++ karışık modda hata ayıklama için) ve IronPython karma / C# hata ayıklama. IronPython, ancak sanal ortamları desteklemez. |
| [Anaconda](https://www.continuum.io) | Bir açık veri bilimi platform tarafından Python gücü ve CPython ve zor yükleme paketleri en son sürümünü içerir. Aksi takdirde karar veremez, öneririz. |
| [PyPy](http://www.pypy.org/) | Uzun süre çalışan programlar ve performans tanımlamak burada durumlar için yararlı olan Python yüksek performans izleme JIT uyarlamasını verir ancak diğer çözümleri bulunamıyor. Visual Studio ile ancak sınırlı destek Works Gelişmiş hata ayıklama özellikleri için. |
| [Jython](http://www.jython.org/) | Python Java sanal makine'üzerinde (JVM) uygulaması. IronPython, Jython içinde çalışan kodu benzer Java sınıfları ve kitaplıkları ile etkileşim kurabilir, ancak birçok kitaplıkları için CPython hedeflenen kullanmanız mümkün olmayabilir. Visual Studio ile ancak sınırlı destek Works Gelişmiş hata ayıklama özellikleri için. |

Yeni formlar algılama Python ortamları için sağlamak istediğiniz geliştiriciler bkz [PTVS Ortam Algılama](https://github.com/Microsoft/PTVS/wiki/Extensibility-Environments) (github.com'u).

## <a name="managing-python-environments-in-visual-studio"></a>Visual Studio'da Python ortamları yönetme

Python ortamları penceresini açmak için seçin **Görünüm > Diğer Pencereler > Python ortamları** menü komutu ya da sağ tıklatma **Python ortamları** düğümü için Çözüm Gezgini'nde projeye ve seçin **görünümü tüm Python ortamları**:

![Çözüm Gezgini'nde görünümü tüm ortamlar komutu](media/environments-view-all.png)

Her iki durumda da, Python ortamları penceresi Çözüm Gezgini eşdüzey sekmeye gibi görünür:

![Python ortamları penceresi](media/environments-default-view.png)

Yukarıdaki örnekte, Python 3.4 (32-bit CPython) IronPython 2.7 32 bit ve 64 bit sürümleri ile birlikte yüklendiğini gösterir. Tüm yeni projeler için kullanılan Python 3.4 kalın olarak varsayılan ortamıdır. Python araçları Visual Studio için Visual Studio 2015 veya önceki yüklediniz, ancak bir Python yorumlayıcısı yüklemediniz listelenen ortamları görmüyorsanız, anlama (bkz [seçme ve Python yorumlayıcılar yükleme](#selecting-and-installing-python-interpreters) yukarıda). **+ Özel...**  komutu sağlar [bir ortam oluşturmak için varolan bir yorumlayıcı](#creating-an-environment-for-an-existing-interpreter).

Listelenen her ortam sağındaki bu ortam için etkileşimli bir pencere açılır bir denetimdir. Başka bir denetim bu ortam için IntelliSense veritabanı yenileyen görünebilir.

Ortamlar açılan Seçici için listesidir **genel bakış**, **paketleri**, ve **IntelliSense** daha sonra bu bölümde açıklanan seçenekleri. Genişletirseniz **Python ortamları** yetecek kadar geniş penceresinde, bu seçenekleri ile çalışmak daha kolay bulabilirsiniz sekmeleri olarak gösterilir:

![Python ortamları genişletilmiş penceresi görünümü](media/environments-expanded-view.png)

> [!Note]
> Visual Studio sistemi site paketleri seçeneği dikkate alır ancak ondan Visual Studio içinde değiştirmek için bir yol sağlamaz.

Visual Studio ortamlarda yönetme video giriş için bkz [yönetme Python ortamları](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=qrDmN4LWE_8305918567) (Microsoft Virtual Academy, 2m35s).

> [!VIDEO https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Managing-Python-Environments-qrDmN4LWE_8305918567]

### <a name="creating-an-environment-for-an-existing-interpreter"></a>Varolan bir yorumlayıcı için bir ortam oluşturma

Visual Studio bir yorumlayıcı bulamazsa (zaman, standart olmayan bir konumda yüklü olduğu gibi) oluşturabilir ve ortam olarak izler:

1. Seçin **+ özel...**  içinde [Python ortamları penceresi](#managing-python-environments-in-visual-studio), yeni bir ortam oluşturur ve açılır [ **yapılandırma** sekmesini](#configure-tab) aşağıda açıklanan.)

    ![Yeni bir özel ortamı için varsayılan görünüm](media/environments-custom-1.png)

1. Bir ortamda adı **açıklama** alan.
1. Girin veya gözatın yorumlayıcı yola **öneki yolu** alan.
1. Seçin **otomatik algıla** kalan alanları doldurun veya bunları el ile tamamlamanız Visual Studio için.
1. Seçin **Uygula** ortamı kaydetmek için.
1. Ortam kaldırmanız gerekirse, seçin **kaldırmak** komutunu **yapılandırma** sekmesi. Bu seçenek otomatik olarak algılanır ortamları sağlamaz. Daha fazla bilgi için sonraki bölüme bakın.

### <a name="moving-an-existing-interpreter"></a>Varolan bir yorumlayıcı taşıma

Dosya sisteminde yeni bir konuma varolan yorumlayıcı taşırsanız, Visual Studio değişikliği otomatik olarak algılamaz ve kendi ortamı el ile güncelleştirmeniz gerekir:

- İlk olarak bir ortam için o yorumlayıcı oluşturduysanız, bu ortam yeni konumunu gösterecek şekilde düzenleyin.

- İlk olarak otomatik olarak algılanır ortamı, Visual Studio inceler kayıt defteri girdileri oluşturulan ayrı yükleyici program ile bilgisayara yüklendi. Bu durumda, ilk Python yorumlayıcı orijinal konumuna geri yükleyin. Ardından, kayıt defteri girişlerini temizler yükleyicisini kullanarak kaldırın. Ardından istediğiniz konuma yorumlayıcı yeniden yükleyin. Yeniden başlatma Visual Studio ve otomatik yeni konumu algıla. Bu işlem, başka bir yan etkileri Yükleyicisi'nin düzgün şekilde uygulandığından emin sağlar.

### <a name="overview-tab"></a>Genel Bakış sekmesi

Temel bilgileri ve komutlar için ortamı sağlar:

![Python ortamları genel bakış sekmesi](media/environments-overview-tab.png)

| Komut | Açıklama |
| --- | --- |
| Bu ortam yeni projelere yönelik varsayılan yap | Visual Studio'nun IntelliSense veritabanı yüklenirken kısaca vermemesine neden olabilir etkin ortamını ayarlar. Birçok paketleriyle ortamlar için artık vermeyen olabilir. |
| Dağıtıcı Web sitesini ziyaret edin | Python dağıtımı tarafından sağlanan URL'yi bir tarayıcı açar. Python 3.x, örneğin, python.org için gider. |
| Açık etkileşimli penceresi | Açılır [etkileşimli (REPL) pencere](python-interactive-repl-in-visual-studio.md) Visual Studio içinde bu ortam için herhangi bir uygulama [başlatma komut dosyaları (aşağıya bakın)](#startup-scripts). |
| Etkileşimli betikleri keşfedin | Bkz: [başlatma komut dosyaları](#startup-scripts). |
| IPython etkileşimli mod kullanın | Ayarlandığında, varsayılan olarak IPython ile etkileşimli penceresi açılır. Bu etkin satır içi hem de Genişletilmiş IPython sözdizimi gibi çizer `name?` yardımını görüntülemek için ve `!command` Kabuk komutları için. Bu seçenek, bir Anaconda dağıtım olarak kullanarak ek paketleri gerektirdiğinde önerilir. Daha fazla bilgi için bkz: [kullanarak IPython etkileşimli penceresinde](interactive-repl-ipython.md). |
| PowerShell Aç | Yorumlayıcı bir PowerShell komut penceresinde başlatır. |
| (Klasör bağlantıları) | Ortam yükleme klasörü, Python.exe'yi yorumlayıcı ve pythonw.exe yorumlayıcı hızlı erişim sağlar. Windows Gezgini'nde ilk açılır, sonraki iki konsol penceresi açın. |

#### <a name="startup-scripts"></a>Başlatma komut dosyaları

Günlük iş akışınızda etkileşimli pencerelerini kullanma gibi büyük olasılıkla düzenli olarak kullandığınız yardımcı işlevleri geliştirin. Örneğin, bir DataFrame Excel'de açılır bir işlev oluşturun ve böylece her zaman etkileşimli pencerede kullanılabilir bu kodu bir başlangıç komut dosyası olarak kaydedin.

Başlatma komut dosyaları içeri aktarmalar, işlev tanımları ve tam anlamıyla başka bir şey de dahil olmak üzere etkileşimli pencere yükler ve otomatik olarak çalıştırılan kodlar içerir. Bu tür komut dosyaları iki yolla başvurulur:

1. Bir ortam yüklediğinizde Visual Studio bir klasör oluşturur `Documents\Visual Studio 2017\Python Scripts\<environment>` burada &lt;ortamı & gt' ortamı adıyla eşleşen. Ortama özgü klasörüyle kolayca gidebilirsiniz **etkileşimli betikleri keşfedin** komutu. Bu ortam için etkileşimli pencere başlattığınızda yükler ve ne olursa olsun çalıştırır `.py` dosyaları burada alfabetik sırada bulunamadı.

1. **Komut dosyaları** denetim **Araçlar > Seçenekler > Python araçları > Etkileşimli Windows** sekmesini (bkz [etkileşimli windows seçenekleri](python-support-options-and-settings-in-visual-studio.md#interactive-windows-options)) ek bir belirtmek için tasarlanmıştır yüklenen ve tüm ortamlarda çalıştırmak başlatma komut dosyaları için bir klasör. Ancak, bu özellik şu anda çalışmıyor.

### <a name="configure-tab"></a>Yapılandır sekmesi

Gösterilen, aşağıdaki tabloda açıklandığı gibi ayrıntıları içerir. Bu sekme yoksa, Visual Studio tüm ayrıntıları otomatik olarak yönetme anlamına gelir.

![Python ortamları Yapılandır sekmesi](media/environments-configure-tab.png)

| Alan | Açıklama |
| --- | --- |
| **Açıklama** | Ortam sağlamak için adı. |
| **Önek yolu** | Yorumlayıcı temel klasör konumu. Bu değer doldurma ve tıklatarak **otomatik algıla**, Visual Studio sizin için diğer alanları doldurun dener. |
| **Yorumlayıcı yolu** | Yolun yürütülebilir yorumlayıcı genellikle önekini yolu ve ardından`python.exe` |
| **Pencereli yorumlayıcı** | Önek yolu ve ardından konsol içi yürütülebilir dosya yolu, genellikle `pythonw.exe`. |
| **Kitaplık yolu** | Standart Kitaplığı kökündeki belirtir ancak Visual Studio yorumlayıcı istek daha doğru bir yolu mümkün ise, bu değer yoksayılabilir. |
| **Dil sürümü** | Aşağı açılır menüden seçilen. |
| **Mimari** | Normal olarak algılandı ve otomatik olarak doldurulur, aksi halde 32 bit veya 64-bit belirtir. |
| **PATH ortam değişkeni** | Yorumlayıcı arama yolları bulmak için kullandığı ortam değişkeni. Visual Studio Proje arama yolları içeren Python başlatırken değişkenin değerini değiştirir. Bu özellik genellikle ayarlanmalı `PYTHONPATH`, ancak bazı yorumlayıcılar farklı bir değer kullanın. |

### <a name="pip-tab"></a>PIP sekmesi

Ayrıca aramak ve yenilerini (bağımlılıkları dahil) yüklemek sağlayarak ortamda yüklü paketleri yönetir. Arama filtreleri, şu anda yüklü olan paketlerin ve [Pypı](https://pypi.python.org). Tüm doğrudan da girebilirsiniz `pip install` bayrakları gibi dahil arama kutusuna komutu `--user` veya `--no-deps`.

![Python ortamları PIP sekmesi](media/environments-pip-tab.png)

Bir paket yükleme ortamı içindeki alt klasörleri oluşturur `Lib` klasör dosya sisteminde. Varsa, örneğin, Python 3.6 yüklü `c:\Python36`, içinde yüklü paketlerini `c:\Python36\Lib`; yüklü Anaconda3 varsa `c:\Program Files\Anaconda3` paketleri yüklenmiş sonra `c:\Program Files\Anaconda3\Lib`.

İkinci durumda, ortam dosya sisteminin korumalı alanında bulunduğundan `c:\Program Files`, Visual Studio çalıştırmanız gerekir `pip install` yükseltilmiş paket alt klasörleri oluşturmak izin vermek için. Yükseltme gerekli olduğunda, Visual Studio "Yönetici ayrıcalıkları yüklemek, güncelleştirme paketleri veya bu ortam için kaldırma için gerekli" istemini görüntüler:

![İsteminin paket yükleme için](media/environments-pip-elevate.png)

**Şimdi Yükselt** konu herhangi bir işletim sistemi izinlerini de ister. tek bir işlem için PIP için yönetimsel ayrıcalıklar verir. Seçme **yönetici ayrıcalıkları olmadan devam** yükleme paketi, ancak klasörleri ile çıkış gibi oluşturmaya çalışırken PIP başarısız denemeleri "hata: oluşturulamadı ' C:\Program Files\Anaconda3\Lib\site-packages\ PNG.PY': izni reddedildi. "

Seçme **her zaman yüklerken veya paketlerini kaldırma kullanımı ile yükseltme** iletişim ortam için söz konusu görüntülenmesini engeller. Yeniden görüntülenmesini iletişim sağlamak için şu adrese gidin **Araçlar > Seçenekler > Python araçları > Genel** ve düğmesini seçin **tüm kalıcı olarak gizli iletişim kutularını Sıfırla**.

Aynı sekmesi seçenekleri olduğunu, ayrıca seçebilirsiniz **her zaman PIP yönetici olarak çalıştır** iletişim kutusu tüm ortamlar için gizlemek için. Bkz: [seçenekler - Genel sekmesi](python-support-options-and-settings-in-visual-studio.md#general-options).

### <a name="intellisense-tab"></a>IntelliSense sekmesi

IntelliSense tamamlanma veritabanı geçerli durumunu gösterir:

![Python ortamları IntelliSense sekmesi](media/environments-intellisense-tab.png)

Veritabanı tüm ortam kitaplıkları için meta verileri içerir ve IntelliSense hızını artırır ve bellek kullanımını azaltır. Visual Studio yeni bir ortam algılar (veya bir ekledikten sonra), kitaplık kaynak dosyaları çözümleyerek Veritabanını derlemek otomatik olarak başlar. Bu işlem herhangi bir yere bir saat veya yüklenenler bağlı olarak daha fazla bilgi için bir dakika sürebilir. (Anaconda, örneğin, birçok kitaplıkları ile gelir ve veritabanını derlemek için biraz zaman alır.) Tamamlandıktan sonra size IntelliSense ayrıntılı ve veritabanını yeniden yenileme gerekmez (ile **yenileme DB** düğmesi) daha fazla kitaplık yükleyene kadar.

Kendisi için veri henüz derlenmiş kitaplıkları ile işaretlenmiş bir **!**; bir ortam veritabanı tam, yoksa bir **!** Ayrıca, yanındaki ana ortamı listesinde görüntülenir.

## <a name="selecting-an-environment-for-a-project"></a>Bir proje için bir ortam seçme

Projeye özgü ortamları proje varsayılan genel ortam yoksayılıyor belirli bir ortamda her zaman çalıştığından emin olun. Örneğin, genel varsayılan ortam CPython olmakla birlikte bir proje IronPython ve genel ortamda yüklü olmayan belirli kitaplıkları gerektirir, ardından bir projeye özgü ortamı gereklidir.

Proje ortamları Çözüm Gezgini'nde Python ortamları düğümü altında listelenir. Kalın giriş şu anda etkin olan ve Visual Studio hata ayıklama, içeri aktarma ve üye tamamlamalar, sözdizimi denetimi ve bir ortam gerektiren diğer görevler için kullanır:

![Çözüm Gezgini'nde görüntülenen proje ortamları](media/environments-project.png)

Proje için farklı bir ortam etkinleştirmek için bu ortam sağ tıklatın ve seçin **etkinleştirme ortamı**.

Herhangi bir genel ortam sağ tıklayarak bir proje ortamı olarak eklenebilir **Python ortamları** ve seçerek **Ekle/Kaldır Python ortamları...** . Görüntülenen listeden seçin veya projenizde kullanılabilir konusu ortamlara seçimini kaldırın.

![Ekle/Kaldır Python ortamları iletişim](media/environments-add-remove.png)

Çözüm Gezgini'nde, yüklü paketleri (olanlar aktarıp ortam etkin olduğunda, kodunuzda kullanabilirsiniz) göstermek için ortam genişletebilirsiniz:

![Çözüm Gezgini'nde bir ortam için Python paketlerini](media/environments-installed-packages.png)

Yeni paketleri yüklemek için ortam sağ tıklayın, **Python paketini yükle...** ve istenen paketin adını girin. Gelen paket (ve bağımlılıklarını) indirilir [Python paket dizini (Pypı)](https://pypi.python.org/pypi), burada da kullanılabilir paketler için arama yapabilirsiniz. Visual Studio'nun durum çubuğu ve yükleme hakkında bilgi çıktı penceresinde gösterir. Bir paketi kaldırmak için sağ seçin **kaldırmak**.

> [!Note]
> Python'un paket yönetimi desteği şu anda çekirdek Python geliştirme ekibi tarafından geliştirilme değil. Görüntülenen girişler her zaman doğru olmayabilir ve yükleme ve kaldırma güvenilir veya kullanılabilir olmayabilir. Visual Studio varsa, PIP Paket Yöneticisi kullanır ve indirir ve gerektiğinde yükler. Visual Studio easy_install Paket Yöneticisi'ni de kullanabilirsiniz. PIP veya komut satırından easy_install kullanarak yüklü olan paketleri da görüntülenir.

> [!Tip]
> Paket yerel bileşenleri için kaynak kodunu içerir PIP nerede başarısız bir paketi yüklemek için yaygın bir durum olduğunda `*.pyd` dosyaları. Visual Studio yüklüyse gerekli sürümü, bu bileşenlerin PIP derlenemiyor. Bu durumda görüntülenen hata iletisi `error: Unable to find vcvarsall.bat`. `easy_install`önceden derlenmiş ikili dosyaları, genellikle indirebildiğini ve Python eski sürümleri için uygun bir derleyici indirebilirsiniz [http://aka.ms/VCPython27](http://aka.ms/VCPython27). Daha fazla ayrıntı için bkz: ["vcvarsallbat Bul kurulamıyor", sorunun nasıl](https://blogs.msdn.microsoft.com/pythonengineering/2016/04/11/unable-to-find-vcvarsall-bat/) üzerinde Python araçları takım Web günlüğü.

## <a name="creating-virtual-environments"></a>Sanal ortamları oluşturma

1. Sağ **Python ortamları** Çözüm Gezgini'nde ve select **sanal ortam Ekle...** , aşağıdaki yukarı getirir:

    ![Bir sanal ortam oluşturma](media/environments-add-virtual-1.png)

1. Proje yolu veya başka bir yerde oluşturmak için bir tam yol sanal ortam oluşturmak için bir ad belirtin. (Diğer araçları ile en fazla uyumluluk sağlamak için yalnızca harfler ve sayılar adı kullanın.)

1. Temel yorumlayıcı genel bir ortam seçin ve'ı tıklatın **oluşturma**. Varsa `pip` ve `virtualenv` veya `venv` paketler yok, indirilir ve yüklenir.

    Sağlanan yol var olan bir sanal ortama ise, temel yorumlayıcı algılanır ve Oluştur düğmesine değişikliklerini **Ekle**:

    ![Var olan bir sanal ortama ekleme](media/environments-add-virtual-2.png)

Var olan bir sanal ortama sağ tıklayarak da eklenebilir **Python ortamları** Çözüm Gezgini'nde ve seçme **varolan sanal ortam Ekle...** . Visual Studio kullanarak temel yorumlayıcı otomatik olarak algılar `orig-prefix.txt` ortam dosyasında `lib` dizin.

Bir sanal ortam projenize eklendikten sonra görünür **Python ortamları** penceresinde, etkinleştirebilir, herhangi bir ortamın gibi ve kendi paketleri yönetebilirsiniz. Sağ tıklatıp seçerek **kaldırmak** ortamı referansı kaldırır ya da ortam ve disk (ancak temel yorumlayıcı) tüm dosyaları siler.

Sanal ortamlar için bu bir dezavantajı Not bunlar sabit kodlanmış dosya yolları içerir ve bu nedenle kolayca paylaşılan veya değiştirilemez diğer geliştirme bilgisayarlara taşınan emin olan. Neyse ki, kullanabileceğiniz `requirements.txt` dosya kolayca ortamı geri yüklemek projenizi alıcılarını izin vermek için sonraki bölümde açıklandığı gibi.

## <a name="managing-required-packages-requirementstxt"></a>Gerekli paketleri (requirements.txt) yönetme

Bir proje başkalarıyla yapı sistemini kullanarak paylaşıyorsanız ya da planlıyorsanız [için Microsoft Azure yayımlama](python-azure-cloud-service-project-template.md), proje gerektiren dış paketler belirtmeniz gerekir. Kullanmak için önerilen yaklaşımdır bir [requirements.txt dosyasını](http://pip.readthedocs.org/en/latest/user_guide.html#requirements-files) (readthedocs.org) bağımlı paketler gerekli sürümlerini yükler PIP komutların listesini içerir.

Teknik olarak, dosya gereksinimleri izlemek için kullanılabilir (kullanarak `-r <full path to file>` bir paket yüklerken), ancak Visual Studio'nun sağladığı belirli desteği `requirements.txt`:

- İçeren bir proje yüklerse `requirements.txt` ve bu dosyada listelenen paketleri yüklemek isterseniz, genişletin **Python ortamları** düğümünde **Çözüm Gezgini**, sonra sağ bir ortam düğümü ve select **Requirements.txt'ten Yükle**:

    ![Requirements.txt'ten yükle](media/environments-requirements-txt-install.png)

- Projede yüklü tüm gerekli paketler zaten varsa, Çözüm Gezgini'nde bir ortam sağ tıklatın ve seçin **requirements.txt Oluştur** gerekli dosya oluşturulamadı. Dosya zaten mevcutsa güncelleştirmek için bir istem görüntülenir:

    ![Güncelleştirme requirements.txt seçenekleri](media/environments-requirements-txt-replace.png)

  - **Dosyanın tamamı yerine** tüm öğeleri, açıklamalar ve mevcut olan seçenekler kaldırır.
  - **Varolan girişleri yenileme** paket gereksinimlerini algılar ve, şu anda yüklü olan sürümle eşleştirmek için sürüm tanımlayıcıları güncelleştirir.
  - **Güncelleştirme ve girişleri ekleme** bulunur ve diğer tüm paketler dosyanın sonuna ekler gereksinimlere yeniler.

Çünkü `requirements.txt` dosyaları projenizin gereksinimleri donmasına yöneliktir, yüklü olan tüm paketlerin kesin sürümleriyle yazılır. Kesin sürümlerini kullanan başka bir bilgisayarda ortamınızı kolayca üretebileceği sağlar. PIP dışında bir yükleyici veya başka bir paketi bir bağımlılık olarak bir sürüm aralığı ile yüklenmiş olsa bile paketleri dahil edilir.

Varsa bir `requirements.txt` dosyasından yeni bir sanal ortam eklerken **sanal ortam Ekle** iletişim başka bir bilgisayardaki bir ortamı yeniden kolaylaşır paketleri otomatik olarak yüklemek için bir seçenek görüntüler:

![Requirements.txt ile sanal ortam oluşturma](media/environments-requirements-txt.png)

Bir paket pip tarafından yüklenemez ve görünür bir `requirements.txt` dosyası, tüm yükleme başarısız olur. Bu durumda, bu paket dışlanacak veya kullanılacak dosyasını el ile düzenleme [PIP'ın seçenekleri](http://pip.readthedocs.org/en/latest/reference/pip_install.html#requirements-file-format) yüklenebilir bir paketin sürümü için başvurmak için. Örneğin, kullanmayı tercih edebilirsiniz [ `pip wheel` ](http://pip.readthedocs.org/en/latest/reference/pip_wheel.html) bağımlılığı derlemek ve eklemek için `--find-links <path>` için seçenek, `requirements.txt`:

```output
C:\Project>pip wheel azure
Downloading/unpacking azure
    Running setup.py (path:C:\Project\env\build\azure\setup.py) egg_info for package azure

Building wheels for collected packages: azure
    Running setup.py bdist_wheel for azure
    Destination directory: c:\project\wheelhouse
Successfully built azure
Cleaning up...

C:\Project>type requirements.txt
--find-links wheelhouse
--no-index
azure==0.8.0

C:\Project>pip install -r requirements.txt -v
Downloading/unpacking azure==0.8.0 (from -r requirements.txt (line 3))
    Local files found: C:/Project/wheelhouse/azure-0.8.0-py3-none-any.whl
Installing collected packages: azure
Successfully installed azure
Cleaning up...
    Removing temporary dir C:\Project\env\build...
```

## <a name="search-paths"></a>Arama yolları

Tipik Python kullanımla `PYTHONPATH` ortam değişkeni (veya `IRONPYTHONPATH`, vs.) Modülü dosyaları için varsayılan arama yolu sağlar. Diğer bir deyişle, kullandığınızda, bir `from <name> import...` veya `import <name>` deyimi, Python için eşleşen bir ada sırayla aşağıdaki konumlarda arar:

1. Python'un yerleşik modüller.
1. Çalıştırmakta olduğunuz Python kodu içeren klasör.
1. "Geçerli ortam değişkeni tarafından tanımlanan modülü arama yolu" olarak. (Bkz [modülü arama yolu](https://docs.python.org/2/tutorial/modules.html#the-module-search-path) ve [ortam değişkenleri](https://docs.python.org/2/using/cmdline.html#envvar-PYTHONPATH) Python belge temel.)

Visual Studio arama path ortam değişkeni bile tüm sistem için değişken ayarlandığında ancak yok sayar. Göz ardı, aslında, tam olarak *çünkü* tüm sistem için ayarlanır ve bu nedenle otomatik olarak yanıtlanamaz bazı sorular başlatır: olan Python 2.7 veya Python 3.3 amacı başvurulan modülleri? Standart kitaplık modülleri geçersiz kılma olacak? Bu davranış, geliştirici farkındadır yoksa bir kötü amaçlı geçirme girişimi mı?

Visual Studio, böylece arama yolları doğrudan hem ortamları ve projeleri belirtmek için bir yol sağlar. Çalıştırın ya da hata ayıklama Visual Studio'da kod değerinde arama yolları alır `PYTHONPATH` (ve diğer eşdeğer değişkenleri). Arama yollarına ekleyerek, Visual Studio konumların kitaplıklarında inceler ve bunları (veritabanı kitaplıkları sayısına bağlı olarak biraz zaman alabilir oluşturmak) için IntelliSense veritabanları oluşturur.

Bir arama yolu eklemek için sağ **arama yolları** Çözüm Gezgini'nde, select öğesi **klasörü için arama yolu Ekle...** ve dahil etmek için klasörü seçin. Bu yol projeyle ilişkili herhangi bir ortam için kullanılır. (Hatalar ortamı Python 3 tabanlı ve Python 2.7 modülleri için bir arama yolu Ekle çalışırsanız görebilirsiniz.)

İle dosyaları bir `.zip` veya `.egg` uzantısı da eklenebilir arama yolları olarak seçerek **Zip arşivine arama yolu Ekle...** . Klasörlerle olduğu gibi bu dosyaların içeriğini taranan ve IntelliSense için kullanılabilir.

Aynı arama yolları kullanarak düzenli olarak ve içeriği genellikle değiştirmeyin, site paket klasörünüze yüklemek için daha etkili olabilir. Arama yolu ardından analiz ve IntelliSense veritabanında depolanan, her zaman hedeflenen ortamı ile ilişkili olması ve her projeye eklemek için bir arama yolu gerektirmez.
