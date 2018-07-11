---
title: Python ortamları penceresi başvurusu
description: Her Visual Studio'da Python ortamları penceresinde görünen sekmeler ayrıntıları.
ms.date: 05/25/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: d4adc1ac472bb05affa547d795690dc7143655fd
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "34572130"
---
# <a name="python-environments-window-tabs-reference"></a>Python ortamları penceresi Sekme Başvurusu

Açmak için **Python ortamları** penceresi:

- Seçin **Görünüm > diğer Windows > Python ortamları** menü komutu.
- Sağ **Python ortamları** seçip Çözüm Gezgini'nde bir proje düğümü **tüm Python ortamları görüntüleme**

Genişletirseniz **Python ortamları** yetecek kadar geniş penceresinde bu seçenekler ile çalışmak daha kullanışlı bulabilirsiniz sekmeler olarak gösterilir. Daha anlaşılır olması için bu makaledeki sekmeleri Genişletilmiş görünümde gösterilir.

![Python ortamları penceresi Genişletilmiş Görünümü](media/environments-expanded-view.png)

## <a name="overview-tab"></a>Genel Bakış sekmesi

Ortam için temel bilgileri ve komutları sağlar:

![Python ortamları genel bakış sekmesi](media/environments-overview-tab.png)

| Komut | Açıklama |
| --- | --- |
| Bu ortama yeni projeler için varsayılan yapın. | Visual Studio neden olabilecek etkin ortam ayarlar (2017 sürüm 15.5 ve öncesi) IntelliSense veritabanı yüklenirken kısa bir süreliğine duyuracağı olacak. Birçok paketleriyle ortamları daha uzun süre duyuracağı olabilir. |
| Dağıtıcı Web sitesini ziyaret edin | Python dağıtım tarafından sağlanan URL bir tarayıcı açar. Python 3.x, örneğin, için python.org gider. |
| Açık etkileşimli penceresi | Açılır [etkileşimli (REPL) penceresi](python-interactive-repl-in-visual-studio.md) Visual Studio'daki bu ortam için tüm uygulama [başlatma komut dosyaları (aşağıya bakın)](#startup-scripts). |
| Etkileşimli betiklerini keşfedin | Bkz: [başlatma komut dosyaları](#startup-scripts). |
| Ipython etkileşimli modu kullanın | Ayarlandığında, varsayılan olarak Ipython ile etkileşimli penceresi açılır. Bu etkin satır içi yanı sıra genişletilmiş Ipython sözdizimi gibi çizim `name?` yardımını görüntülemek için ve `!command` Kabuk komutları için. Bir Anaconda dağıtım olarak kullanarak ek paketler gerektirdiğinde bu seçeneği önerilir. Daha fazla bilgi için [kullanarak Ipython etkileşimli pencerede](interactive-repl-ipython.md). |
| PowerShell ile Aç | Bir PowerShell komut penceresinde yorumlayıcı başlatır. |
| (Klasör ve program bağlantılar) | Ortamın yükleme klasörü, python.exe yorumlayıcı ve pythonw.exe yorumlayıcı hızlı erişim sağlar. Windows Gezgini'nde ilk açılır, sonraki iki konsol penceresi açın. |

### <a name="startup-scripts"></a>Başlatma komut dosyaları

Etkileşimli pencere, gündelik iş akışınızı kullandıkça, büyük olasılıkla düzenli olarak kullandığınız yardımcı işlevleri geliştirin. Örneğin, bir veri çerçevesi Excel'de açılır bir işlev oluşturma ve her zaman etkileşimli pencerede kullanılabilir, böylece bu kod bir başlangıç dosyası olarak kaydedin.

Başlatma komut dosyaları içeri aktarmalar, işlev tanımları ve tam anlamıyla diğer her şey dahil olmak üzere etkileşimli pencere yükler ve otomatik olarak çalışan kodu içerir. Bu komut iki yolla başvurulur:

1. Bir ortam yüklediğinizde Visual Studio, bir klasör oluşturur. `Documents\Visual Studio 2017\Python Scripts\<environment>` burada &lt;ortam&gt; ortam adıyla aynıdır. Ortama özgü klasöre kolayca gezinebilirsiniz **etkileşimli betiklerini keşfedin** komutu. Bu ortam için etkileşimli pencereye başlattığınızda, yükler ve her şeyi çalıştırır `.py` dosyaları alfabetik sırayla burada bulunur.

1. **Betikleri** denetim **araçları > Seçenekler > Python araçları > Etkileşimli bir Windows** sekmesini (bkz [etkileşimli windows seçenekleri](python-support-options-and-settings-in-visual-studio.md#interactive-windows-options)) bir ek belirtmek için tasarlanmıştır yüklenen ve tüm ortamlarda çalıştırabilirsiniz başlatma komut dosyaları klasörü. Ancak, bu özellik şu anda çalışmıyor.

## <a name="configure-tab"></a>Yapılandır sekmesi

Varsa, aşağıdaki tabloda açıklandığı gibi ayrıntıları içerir. Bu sekme yoksa, Visual Studio otomatik olarak tüm ayrıntıları yönetiyor anlamına gelir.

![Python ortamları Yapılandır sekmesi](media/environments-configure-tab.png)

| Alan | Açıklama |
| --- | --- |
| **Açıklama** | Ortamı sağlamak için adı. |
| **Ön ek yolu** | Yorumlayıcı temel klasörün konumu. Bu değer doldurma ve tıklatarak **otomatik algıla**, Visual Studio sizin için diğer alanları doldurun dener. |
| **Cesta k interpretu** | Yolun yürütülebilir Yorumlayıcı, genellikle ön ek yolu ardından `python.exe` |
| **Pencereli yorumlayıcı** | Ön ek yolu ve ardından konsol içi yürütülebilir dosya yolu, genellikle `pythonw.exe`. |
| **Kitaplık yolu**<br/>(varsa) | Standart Kitaplığı'nın kökünü belirtir ancak bu değer, Visual Studio yorumlayıcı istek daha doğru bir yolu erişebiliyorsa yoksayılabilir. |
| **Dil sürümü** | Aşağı açılan menüden seçim. |
| **Mimari** | Normal olarak algılandı ve otomatik olarak doldurulur, aksi halde, 32 bit veya 64-bit belirtir. |
| **PATH ortam değişkeni** | Ortam değişkenini yorumlayıcı arama yollarını bulmak için kullanır. Visual Studio, projenin arama yollarını içeren Python başlatırken değişkenin değerini değiştirir. Bu özellik genellikle ayarlanmalıdır `PYTHONPATH`, ancak bazı yorumlayıcılarını farklı bir değer kullanın. |

## <a name="packages-tab"></a>Paketleri sekmesi

*Ayrıca önceki sürümlerinde "pip" etiketli.*

Pip, ayrıca arayın ve yenilerini (tüm bağımlılıklar dahil olmak üzere) yükleme kullanan bir ortamda yüklü paketleri yönetir. Visual Studio 2017 sürüm 15.7 ve üzeri, bir **paketleri (Conda)** sekmesi görüntülenir, bunun yerine conda Paket Yöneticisi'ni kullanır. (Bu seçenek görmüyorsanız, seçenek kümesi **Araçları** > **seçenekleri** > **Python** > **Deneysel**   >  **Conda Paket Yöneticisi'ni (PIP) yerine kullanılabilir olduğunda** ve Visual Studio'yu yeniden başlatın.)

Paket zaten yüklü olan paketleri denetimleri (yukarı ok) güncelleştirme ve kaldırma (daire içinde X) ile görünür:

![Python ortamları Paketleri sekmesi](media/environments-pip-tab-controls.png)

Bir arama terimi filtreleri Pypı yüklü paketleri yanı sıra yüklü paketleri listesi giriliyor.

![Python ortamları paketleri sekmesinde "num" bir arama özelliğiyle](media/environments-pip-tab.png)

Yukarıdaki görüntüde görebileceğiniz gibi arama sonuçlarının arama terimiyle eşleşen paket sayısı Göster; İlk listede, ancak bir komutu çalıştırmak için giriştir `pip install <name>` doğrudan. Üzerinde kullanıyorsanız **paketleri (Conda)** sekmesinde, bunun yerine bkz `conda install <name>`:

![Yükleme komutunu bir conda gösteren Conda Paketleri sekmesi](media/environments-conda-tab-install.png)

Her iki durumda da, yükleme paket adından sonra arama kutusuna bağımsız değişken ekleyerek özelleştirebilirsiniz. Bağımsız değişkenler eklediğinizde gösterir arama sonuçlarının `pip install` veya `conda install` arama kutusuna içeriğine göre ve ardından:

![Pip ve conda yükleme komutları bağımsız değişkenleri kullanma](media/environments-pip-tab-arguments.png)

Bir paket yükleme oluşturur ortamın içindeki `Lib` dosya sisteminde klasör. Varsa, örneğin, Python 3.6 yüklü `c:\Python36`, içinde yüklü paketleri `c:\Python36\Lib`; yüklü Anaconda3 varsa `c:\Program Files\Anaconda3` paketleri yüklenmiş sonra `c:\Program Files\Anaconda3\Lib`.

### <a name="granting-administrator-privileges-for-package-install"></a>Paket için ekibi tarafından verilmesinin yönetici ayrıcalıkları yükleyin

Paketleri gibi dosya sistemi, korumalı bir alanda bulunan bir ortama yüklerken `c:\Program Files\Anaconda3\Lib`, Visual Studio çalıştırmanız gerekir `pip install` paket alt klasörler oluşturmak üzere izin vermek için yükseltilmiş. Yükseltme gerekli olduğunda, Visual Studio'yu "Yönetici ayrıcalıkları yüklemek, güncelleştirmek ya da bu ortam için paketleri kaldırmak için gerekli olabilecek" istemi görüntüler:

![Paket yüklemesi için yükseltme istemi](media/environments-pip-elevate.png)

**Şimdi Yükselt** konu herhangi bir işletim sistemi için izinleri de ister. tek bir işlem için pip için yönetici ayrıcalıkları verir. Seçme **yönetici ayrıcalıkları olmadan devam** girişimleri paketini yükleme ancak klasörleri gibi çıkış oluşturmaya çalışırken pip başarısız "hatası: değil oluşturabilirsiniz ' C:\Program Files\Anaconda3\Lib\site-packages\ PNG.PY': izin reddedildi. "

Seçme **her zaman yüklerken veya paketlerini kaldırma yükseltmesine** iletişim ortamı için söz konusu görüntülenmesini engeller. İletişim kutusunu yeniden görünür hale getirmek için Git **Araçlar > Seçenekler > Python araçları > Genel** ve düğmeyi seçin **tüm kalıcı olarak gizli iletişim kutuları sıfırlama**.

Aynı sekmesi seçenekleri içeren de seçebilirsiniz **her zaman pip yönetici olarak çalıştır** tüm ortamlar için iletişim başlatmasını bastırmak için. Bkz: [seçenekleri - Genel sekmesi](python-support-options-and-settings-in-visual-studio.md#general-options).

### <a name="security-restrictions-with-older-versions-of-python"></a>Python'ın eski sürümleriyle birlikte güvenlik kısıtlamaları

3.1 ve 3.2, Python 2.6 kullanırken Visual Studio "nedeniyle güvenlik kısıtlamaları, internet'ten yükleme Python'ın bu sürümünde çalışmayabilir" uyarısı gösterilir:

![Python eski sürümü yükleme kısıtlamaları iletisi pip hakkında](media/environments-old-version-restriction.png)

Uyarıya neden olan Python, bu eski sürümleriyle `pip install` desteği için Aktarım güvenliği Katmanı (TLS) 1.2, paket kaynağından paketleri yüklemek için gerekli olan içermiyor pypi.org. Özel bir Python yapılar destekleyebilir TLS 1.2 durumda `pip install` işe yarayabilir.

Uygun olabilir `get-pip.py` bir paket için [bootstrap.pypa.io](https://bootstrap.pypa.io/), el ile paket indirme [pypi.org](https://pypi.org/)ve ardından bu yerel bir kopyasından paketini yükleyin.

Ancak yalnızca Python 2.7 veya 3.3 durumu uyarısı görünmez + yükseltmek için önerilir.

## <a name="intellisense-tab"></a>IntelliSense sekmesi

IntelliSense tamamlanma veritabanı geçerli durumunu gösterir:

![Python ortamları IntelliSense sekmesi](media/environments-intellisense-tab.png)

- İçinde **Visual Studio 2017 sürüm 15.5** ve bu kitaplık için derlenmiş olan bir veritabanını daha önce IntelliSense tamamlamaları bağlıdır. Veritabanı oluşturma arka planda gerçekleştirilir, bu kitaplığa yüklendiğinde, ancak biraz zaman alabilir ve kod yazmaya başladığınızda tam olmayabilir.
- **Visual Studio 2017 sürüm 15.6** ve daha sonra veritabanı üzerinde varsayılan olarak bağlı olmayan tamamlamaları sağlamak için daha hızlı bir yöntem kullanır. Bu nedenle sekme olarak etiketlenmiş **IntelliSense [veritabanı devre dışı]**. Veritabanı seçeneğini temizleyerek etkinleştirebilirsiniz **Araçları** > **seçenekleri** > **Python**  >   **Deneysel** > **ortamları için yeni stil IntelliSense kullanma**.

Visual Studio yeni bir ortam algılar (veya bir ekledikten sonra), veritabanı, kitaplık kaynak dosyalarını analiz ederek derlemek otomatik olarak başlar. Bu işlem, herhangi bir yere bir saat veya yüklenenler bağlı olarak daha fazla bilgi için bir dakika sürebilir. (Anaconda, örneğin, birçok kitaplıkları ile gelir ve veritabanını derlemek için biraz zaman alır.) Tamamlandıktan sonra size ayrıntılı IntelliSense ve veritabanını yeniden yenileme gerekmez (ile **Yenile DB** düğmesi) daha fazla kitaplıklarını yüklemek kadar.

Kendisi için veriler henüz derlenmiş kitaplıkları ile işaretlenmiş bir **!**; tam bir ortamın veritabanı yoksa bir **!** Ayrıca yanında ana ortam listesinde görünür.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da Python ortamlarını yönetme](managing-python-environments-in-visual-studio.md)
- [Proje için yorumlayıcıyı seçme](selecting-a-python-environment-for-a-project.md)
- [Bağımlılıklar için requirements.txt dosyasını kullanma](managing-required-packages-with-requirements-txt.md)
- [Arama yolları](search-paths.md)
