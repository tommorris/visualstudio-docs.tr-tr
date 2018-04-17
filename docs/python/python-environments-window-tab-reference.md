---
title: Python ortamları penceresi başvurusu
description: Visual Studio'da Python ortamları penceresinde görünür sekmelerin her birinde ayrıntıları.
ms.custom: ''
ms.date: 03/05/2018
ms.technology:
- devlang-python
ms.devlang: python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: dcfb786f487f73665bd36f641075e0d31902ade6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="python-environments-window-tabs-reference"></a>Python ortamları penceresinde Sekme Başvurusu

Açmak için **Python ortamları** penceresi:

- Seçin **Görünüm > Diğer Pencereler > Python ortamları** menü komutu.
- Sağ **Python ortamları** düğümü seçip Çözüm Gezgini proje için **görünümü tüm Python ortamları**

Genişletirseniz **Python ortamları** yetecek kadar geniş penceresinde, bu seçenekleri ile çalışmak daha kolay bulabilirsiniz sekmeleri olarak gösterilir. Daha anlaşılır olması için bu makaledeki sekmeleri genişletilmiş görünümünde gösterilir.

![Python ortamları genişletilmiş penceresi görünümü](media/environments-expanded-view.png)

## <a name="overview-tab"></a>Genel Bakış sekmesi

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
| (Klasör ve program bağlantıları) | Ortam yükleme klasörü, Python.exe'yi yorumlayıcı ve pythonw.exe yorumlayıcı hızlı erişim sağlar. Windows Gezgini'nde ilk açılır, sonraki iki konsol penceresi açın. |

### <a name="startup-scripts"></a>Başlatma komut dosyaları

Günlük iş akışınızda etkileşimli pencerelerini kullanma gibi büyük olasılıkla düzenli olarak kullandığınız yardımcı işlevleri geliştirin. Örneğin, bir DataFrame Excel'de açılır bir işlev oluşturun ve böylece her zaman etkileşimli pencerede kullanılabilir bu kodu bir başlangıç komut dosyası olarak kaydedin.

Başlatma komut dosyaları içeri aktarmalar, işlev tanımları ve tam anlamıyla başka bir şey de dahil olmak üzere etkileşimli pencere yükler ve otomatik olarak çalıştırılan kodlar içerir. Bu tür komut dosyaları iki yolla başvurulur:

1. Bir ortam yüklediğinizde Visual Studio bir klasör oluşturur `Documents\Visual Studio 2017\Python Scripts\<environment>` nerede &lt;ortam&gt; ortamı adıyla eşleşen. Ortama özgü klasörüyle kolayca gidebilirsiniz **etkileşimli betikleri keşfedin** komutu. Bu ortam için etkileşimli pencere başlattığınızda yükler ve ne olursa olsun çalıştırır `.py` dosyaları burada alfabetik sırada bulunamadı.

1. **Komut dosyaları** denetim **Araçlar > Seçenekler > Python araçları > Etkileşimli Windows** sekmesini (bkz [etkileşimli windows seçenekleri](python-support-options-and-settings-in-visual-studio.md#interactive-windows-options)) ek bir belirtmek için tasarlanmıştır yüklenen ve tüm ortamlarda çalıştırmak başlatma komut dosyaları için bir klasör. Ancak, bu özellik şu anda çalışmıyor.

## <a name="configure-tab"></a>Yapılandır sekmesi

Mevcut ise, aşağıdaki tabloda açıklandığı gibi ayrıntıları içerir. Bu sekme yoksa, Visual Studio tüm ayrıntıları otomatik olarak yönetme anlamına gelir.

![Python ortamları Yapılandır sekmesi](media/environments-configure-tab.png)

| Alan | Açıklama |
| --- | --- |
| **Açıklama** | Ortam sağlamak için adı. |
| **Önek yolu** | Yorumlayıcı temel klasör konumu. Bu değer doldurma ve tıklatarak **otomatik algıla**, Visual Studio sizin için diğer alanları doldurun dener. |
| **Yorumlayıcı yolu** | Yolun yürütülebilir yorumlayıcı genellikle önekini yolu ve ardından `python.exe` |
| **Pencereli yorumlayıcı** | Önek yolu ve ardından konsol içi yürütülebilir dosya yolu, genellikle `pythonw.exe`. |
| **Kitaplık yolu**<br/>(varsa) | Standart Kitaplığı kökündeki belirtir ancak Visual Studio yorumlayıcı istek daha doğru bir yolu mümkün ise, bu değer yoksayılabilir. |
| **Dil sürümü** | Aşağı açılır menüden seçilen. |
| **Mimari** | Normal olarak algılandı ve otomatik olarak doldurulur, aksi halde 32 bit veya 64-bit belirtir. |
| **PATH ortam değişkeni** | Yorumlayıcı arama yolları bulmak için kullandığı ortam değişkeni. Visual Studio Proje arama yolları içeren Python başlatırken değişkenin değerini değiştirir. Bu özellik genellikle ayarlanmalı `PYTHONPATH`, ancak bazı yorumlayıcılar farklı bir değer kullanın. |

## <a name="packages-tab"></a>Paketleri sekmesi

*Ayrıca "PIP" önceki sürümlerde etiketli.*

Ayrıca aramak ve yenilerini (bağımlılıkları dahil) yüklemek sağlayarak ortamda yüklü paketleri yönetir.

Yüklü olan paketleri (yukarı ok) güncelleştirin ve (bir daire içinde X) kaldırmak için denetimleri ile paket görüntülenir:

![Python ortamları Paketleri sekmesi](media/environments-pip-tab-controls.png)

Bir arama terimi Pypı yüklü paketleri yanı sıra yüklü olan paketlerin listesini girme.

![Bir arama "num" Python ortamları Paketleri sekmesi](media/environments-pip-tab.png)

Tüm doğrudan da girebilirsiniz `pip install` bayrakları gibi dahil arama kutusuna komutu `--user` veya `--no-deps`.

Bir paket yükleme ortamı içindeki alt klasörleri oluşturur `Lib` klasör dosya sisteminde. Varsa, örneğin, Python 3.6 yüklü `c:\Python36`, içinde yüklü paketlerini `c:\Python36\Lib`; yüklü Anaconda3 varsa `c:\Program Files\Anaconda3` paketleri yüklenmiş sonra `c:\Program Files\Anaconda3\Lib`.

İkinci durumda, ortam dosya sisteminin korumalı alanında bulunduğundan `c:\Program Files`, Visual Studio çalıştırmanız gerekir `pip install` yükseltilmiş paket alt klasörleri oluşturmak izin vermek için. Yükseltme gerekli olduğunda, Visual Studio "Yönetici ayrıcalıkları yüklemek, güncelleştirme paketleri veya bu ortam için kaldırma için gerekli" istemini görüntüler:

![İsteminin paket yükleme için](media/environments-pip-elevate.png)

**Şimdi Yükselt** konu herhangi bir işletim sistemi izinlerini de ister. tek bir işlem için PIP için yönetimsel ayrıcalıklar verir. Seçme **yönetici ayrıcalıkları olmadan devam** yükleme paketi, ancak klasörleri ile çıkış gibi oluşturmaya çalışırken PIP başarısız denemeleri "hata: oluşturulamadı ' C:\Program Files\Anaconda3\Lib\site-packages\ PNG.PY': izni reddedildi. "

Seçme **her zaman yüklerken veya paketlerini kaldırma kullanımı ile yükseltme** iletişim ortam için söz konusu görüntülenmesini engeller. Yeniden görüntülenmesini iletişim sağlamak için şu adrese gidin **Araçlar > Seçenekler > Python araçları > Genel** ve düğmesini seçin **tüm kalıcı olarak gizli iletişim kutularını Sıfırla**.

Aynı sekmesi seçenekleri olduğunu, ayrıca seçebilirsiniz **her zaman PIP yönetici olarak çalıştır** iletişim kutusu tüm ortamlar için gizlemek için. Bkz: [seçenekler - Genel sekmesi](python-support-options-and-settings-in-visual-studio.md#general-options).

## <a name="intellisense-tab"></a>IntelliSense sekmesi

IntelliSense tamamlanma veritabanı geçerli durumunu gösterir:

![Python ortamları IntelliSense sekmesi](media/environments-intellisense-tab.png)

İçinde **Visual Studio 2017 sürüm 15,5** ve önceki sürümleri, bu kitaplık için derlendiği veritabanı IntelliSense tamamlamalar bağlıdır. Bir kitaplık yüklendiğinde, ancak biraz zaman alabilir ve kod yazmaya başladığınızda tam olmayabilir veritabanınızı oluşturmaya arka planda gerçekleştirilir. **Visual Studio 2017 sürüm 15,6** ve daha sonra etkinleştirmek özellikle seçmediğiniz sürece, veritabanı üzerinde dayanmayan tamamlamalar sağlamak için daha hızlı bir yöntem kullanır.

Visual Studio yeni bir ortam algılar (veya bir ekledikten sonra), kitaplık kaynak dosyaları çözümleyerek Veritabanını derlemek otomatik olarak başlar. Bu işlem herhangi bir yere bir saat veya yüklenenler bağlı olarak daha fazla bilgi için bir dakika sürebilir. (Anaconda, örneğin, birçok kitaplıkları ile gelir ve veritabanını derlemek için biraz zaman alır.) Tamamlandıktan sonra size IntelliSense ayrıntılı ve veritabanını yeniden yenileme gerekmez (ile **yenileme DB** düğmesi) daha fazla kitaplık yükleyene kadar.

Kendisi için veri henüz derlenmiş kitaplıkları ile işaretlenmiş bir **!**; bir ortam veritabanı tam, yoksa bir **!** Ayrıca, yanındaki ana ortamı listesinde görüntülenir.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da Python ortamları yönetme](managing-python-environments-in-visual-studio.md)
- [Proje için yorumlayıcıyı seçme](selecting-a-python-environment-for-a-project.md)
- [Bağımlılıklar için requirements.txt dosyasını kullanma](managing-required-packages-with-requirements-txt.md)
- [Arama yolları](search-paths.md)
