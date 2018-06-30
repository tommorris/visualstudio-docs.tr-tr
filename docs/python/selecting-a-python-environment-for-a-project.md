---
title: Python yorumlayıcı ve ortamınız için bir proje seçme
description: Visual Studio projesi artı sanal ortamları oluşturma yönergeleri için kullanılacak Python ortamı atama.
ms.date: 06/27/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 0c38436c5cf3d89b4224fbdbe9bd072f2a6c10d0
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117114"
---
# <a name="how-to-assign-which-python-environment-is-used-for-a-project"></a>Proje için hangi Python ortamı atamak nasıl kullanılır

Bir Python projesindeki tüm kod belirli bir ortam bağlamında çalışır. Visual Studio bu ortam hata ayıklama, içeri aktarma ve üye tamamlamalar, sözdizimi denetimi ve bir ortam gerektiren diğer görevler için de kullanır.

Visual Studio'daki tüm yeni Python projeleri başlangıçta altında görünür varsayılan genel ortamı kullanmak üzere yapılandırılmış **Python ortamları** Çözüm Gezgini'nde düğümü:

![Çözüm Gezgini'nde gösterilen genel varsayılan Python ortamı](media/environments-project.png)

Bir proje için ortam değiştirmek için sağ tıklatın **Python ortamları** düğümü ve select **Ekle/Kaldır Python ortamları...** . Görüntülenen listeden da içeren genel, sanal ve conda ortamları seçin altında görüntülenmesini istediğiniz tüm olanları **Python ortamları** düğümü:

![Ekle/Kaldır Python ortamları iletişim](media/environments-add-remove.png)

Seçtiğinizde, bundan sonra **Tamam**, seçilen tüm ortamlar görünür **Python ortamları** düğümü. Şu anda etkinleştirilmiş ortam kalın olarak görünür:

![Çözüm Gezgini'nde gösterilen birden çok Python ortamı](media/environments-project-multiple.png)

Farklı bir ortam hızlı bir şekilde etkinleştirmek için bu ortamı adını sağ tıklatın ve seçin **etkinleştirme ortamı**. Tercih ettiğiniz proje ile kaydedilir ve gelecekte projeyi açtığınızda, ortamda etkinleştirilir. Tüm seçenekleri temizlerseniz **Ekle/Kaldır Python ortamları** iletişim kutusunda, Visual Studio genel varsayılan ortamını etkinleştirir.

Bağlam menüsünde **Python ortamları** düğüm ayrıca ek komutlar sağlar:

| Komut | Açıklama |
| --- | --- |
| Sanal ortam Ekle... | Projede yeni bir sanal ortam oluşturma işlemi başlar. Bkz: [sanal bir ortam oluşturmak](#create-a-virtual-environment). |
| Var olan sanal ortama Ekle... | Bir sanal ortam içeren bir klasör seçmenizi ister ve altındaki listesine ekler **Python ortamları**, ancak etkinleştirmez. Bkz: [ActivateAdd var olan bir sanal ortama](#activate-an-existing-virtual-environment). |
| Conda ortam oluştur... | Geçiş yapar **Python ortamları** *penceresi* , ortam için bir ad girin ve temel yorumlayıcı belirtin. |

## <a name="using-virtual-environments"></a>Sanal ortamlar kullanarak

Bir sanal özel bir Python yorumlayıcısı benzersiz bir bileşimi ve diğer genel ve conda ortamlarından farklı belirli kitaplıkların ortamıdır. Bir sanal ortam projeye özeldir ve proje klasöründe saklanır. Ortam yüklü kitaplıkları ile birlikte bu klasörde bir `pyvenv.cfg` ortam yolunu belirtir. dosya *temel yorumlayıcı* dosya sistemindeki başka bir yerde. (Diğer bir deyişle, bir sanal ortam Yorumlayıcı, yalnızca bir bağlantı kopyasını içermiyor.) 

Bir sanal ortam kullanmanın bir avantajı, zaman içinde proje geliştirdikçe sanal ortam her zaman projenin tam bağımlılıkları yansıtır ' dir. (Paylaşılan genel ortamı Öte yandan, içeren herhangi bir sayıda kitaplıkları, bunları projenizde veya kullanıp kullanmayacağınızı.) Daha sonra kolayca oluşturabileceğiniz bir `requirements.txt` sonra bu bağımlılıkların başka bir geliştirme veya üretim bilgisayara yeniden yüklemek için kullanılan sanal ortam dosyasından. Daha fazla bilgi için bkz: [requirements.txt ile gerekli paketleri yönetme](managing-required-packages-with-requirements-txt.md).

Visual Studio'da içeren bir projeyi açtığınızda bir `requirements.txt` dosya, Visual Studio otomatik olarak ister sanal ortamı yeniden oluşturmak için seçeneği sağlar. Visual Studio değil yüklü bilgisayarda, Azure App Service gibi kullanabilirsiniz `pip install -r requirements.txt` paketlerini geri yüklemek için (Bu işlem üzerinde açıklanan [yönetme Python Azure App Service'te](managing-python-on-azure-app-service.md)).

Bir sanal ortam temel yorumlayıcı sabit kodlanmış bir yoluna içerdiğinden ve ortamı kullanarak yeniden oluşturabilirsiniz çünkü `requirements.txt`, genellikle kaynak denetimi tüm sanal ortamın klasöründen atlayın.

Aşağıdaki bölümlerde, var olan bir sanal ortama projesinde etkinleştirmek ve yeni bir sanal ortam oluşturma açıklanmaktadır.

Visual Studio'da bir sanal ortam diğer gibi bir proje için etkin hale getirilebilir **Python ortamları** düğümünde **Çözüm Gezgini**.

Bir sanal ortam projenize eklendikten sonra görünür **Python ortamları** penceresi. Sonra onu gibi herhangi bir ortamın etkinleştirebilir ve kendi paketleri yönetebilirsiniz.

### <a name="create-a-virtual-environment"></a>Sanal ortam oluşturma

Yeni bir sanal ortam doğrudan Visual Studio'dan aşağıdaki gibi oluşturabilirsiniz:

1. Sağ **Python ortamları** Çözüm Gezgini'nde ve select **sanal ortam Ekle...** , aşağıdaki iletişim kutusunu getirir:

    ![Bir sanal ortam oluşturma](media/environments-add-virtual-1.png)

1. İçinde **sanal ortam konumunu** alanında, sanal ortam için bir yol belirtin. Yalnızca bir adı belirtirseniz, sanal ortamı geçerli projede bu ada sahip bir alt klasörü içinde oluşturulur.

1. Bir ortam temel yorumlayıcı seçip **oluşturma**. Visual Studio ortamında yapılandırır ve tüm gerekli paketleri indirir bir ilerleme çubuğu görüntüler. Sanal ortam bu noktada, görünür **Python ortamları** içeren proje penceresi.

1. Sanal ortam varsayılan olarak etkinleştirilmez. Proje için etkinleştirmek için sağ tıklatın ve seçin **etkinleştirme ortamı**.

> [!Note]
> Konum yolu var olan bir sanal ortama tanımlıyorsa, Visual Studio temel yorumlayıcı otomatik olarak algılar (kullanarak `orig-prefix.txt` ortam dosyasında `lib` dizini) ve Oluştur düğmesine dönüşür **Ekle**.
>
> Varsa bir `requirements.txt` dosyası mevcut bir sanal ortam eklerken **sanal ortam Ekle** iletişim başka bir bilgisayardaki bir ortamı yeniden kolaylaşır paketleri otomatik olarak yüklemek için bir seçenek görüntüler:
>
> ![Requirements.txt ile sanal ortam oluşturma](media/environments-requirements-txt.png)
>
> Kullanılan gibi her iki durumda da sonucu aynı ise **varolan sanal ortam Ekle...**  komutu.

### <a name="activate-an-existing-virtual-environment"></a>Var olan bir sanal ortama etkinleştir

Başka bir sanal ortam zaten oluşturduysanız, proje için şu şekilde etkinleştirebilirsiniz:

1. Sağ **Python ortamları** Çözüm Gezgini'nde ve select **varolan sanal ortam Ekle...** .

1. İçinde **Gözat** görünür, sanal ortamı içeren klasörü seçin ve seçmek için Bul iletişim **Tamam**. Visual Studio algılarsa bir `requirements.txt` dosyası bu ortamda, bu paketleri yüklenip yüklenmeyeceğini sorar.

1. Birkaç dakika sonra sanal ortam altında görüntülenir. **Python ortamları** Çözüm Gezgini'nde düğümü. Sanal ortam varsayılan olarak etkinleştirilmez, bu nedenle sağ tıklatın ve seçin **etkinleştirme ortamı**.

### <a name="remove-a-virtual-environment"></a>Bir sanal ortam Kaldır

1. Çözüm Gezgini'nde, sanal ortama sağ tıklatıp **kaldırmak**.

1. Visual Studio kaldırın veya sanal ortamı silmek ister. Seçme **kaldırmak** projeye kullanılamaz hale getirir, ancak dosya sisteminde bırakır. Seçme **silmek** hem ortamı projeden kaldırır ve dosya sisteminden siler. Temel yorumlayıcı etkilenmez.

## <a name="view-installed-packages"></a>Görünüm yüklü paketleri

Çözüm Gezgini'nde, hızlı bir şekilde (almak ve ortam etkin olduğunda bu paketleri, kodunuzda kullanmak anlamına gelir), ortamda yüklü olan paketleri görüntülemek için belirli herhangi bir ortamın 's düğümünü genişletin:

![Çözüm Gezgini'nde bir ortam için Python paketlerini](media/environments-installed-packages.png)

Yeni paketleri yüklemek için ortam sağ tıklatın ve seçin **Python paketini yükle...**  geçmek için **paketleri** sekmesinde **Python ortamları** penceresi. Bir arama girin terim (genellikle paket adı) ve Visual Studio eşleşen paketleri görüntüler.

Visual Studio içinde gelen yüklenen paketler (ve bağımlılıklarını) [Python paket dizini (Pypı)](https://pypi.org), burada da kullanılabilir paketler için arama yapabilirsiniz. Visual Studio'nun durum çubuğu ve çıktı penceresi yükleme hakkında bilgi gösterir. Bir paketi kaldırmak için sağ seçin **kaldırmak**.

Görüntülenen girişler her zaman doğru olmayabilir ve yükleme ve kaldırma güvenilir veya kullanılabilir olmayabilir unutmayın. Visual Studio varsa, PIP Paket Yöneticisi kullanır ve indirir ve gerektiğinde yükler. Visual Studio easy_install Paket Yöneticisi'ni de kullanabilirsiniz. Kullanarak yüklü olan paketleri `pip` veya `easy_install` komut satırından da görüntülenir.

Ayrıca Visual Studio kullanarak şu anda desteklemiyor Not `conda` conda ortamına paketleri yüklemek için. Kullanım `conda` komuttan satır yerine.

> [!Tip]
> Paket yerel bileşenleri için kaynak kodunu içerir PIP nerede başarısız bir paketi yüklemek için yaygın bir durum olduğunda `*.pyd` dosyaları. Visual Studio yüklüyse gerekli sürümü, bu bileşenlerin PIP derlenemiyor. Bu durumda görüntülenen hata iletisi `error: Unable to find vcvarsall.bat`. `easy_install` önceden derlenmiş ikili dosyaları, genellikle indirebildiğini ve Python eski sürümleri için uygun bir derleyici indirebilirsiniz [ http://aka.ms/VCPython27 ](http://aka.ms/VCPython27). Daha fazla ayrıntı için bkz: ["vcvarsallbat Bul kurulamıyor", sorunun nasıl](https://blogs.msdn.microsoft.com/pythonengineering/2016/04/11/unable-to-find-vcvarsall-bat/) üzerinde Python araçları takım Web günlüğü.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da Python ortamları yönetme](managing-python-environments-in-visual-studio.md)
- [Bağımlılıklar için requirements.txt dosyasını kullanma](managing-required-packages-with-requirements-txt.md)
- [Arama yolları](search-paths.md)
- [Python ortamları penceresi başvurusu](python-environments-window-tab-reference.md)