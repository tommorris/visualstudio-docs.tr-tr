---
title: "Bir proje için bir ortam seçme | Microsoft Docs"
description: "Visual Studio Çözüm Gezgini'nde, belirli bir Python yorumlayıcısı (ortamı) için her zaman kullanım verilen her proje için varsayılan ortam yoksayılıyor atayabilirsiniz. Ayrıca, oluşturabilir ve sanal ortamlarını yönetebilir."
ms.custom: 
ms.date: 02/20/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 6f422cc60638b7eed4a5b42516e7496c4a6f6209
ms.sourcegitcommit: c0a2385a16cc4f47d2e1ff23d35c4da40f5605e0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="selecting-a-python-interpreter-and-environment-for-use-in-a-project"></a>Bir Python yorumlayıcısı ve ortam kullanmak için bir proje ile seçme

Bir Python projesindeki tüm kod belirli bir ortam bağlamında çalışır. Visual Studio bu ortam hata ayıklama, içeri aktarma ve üye tamamlamalar, sözdizimi denetimi ve bir ortam gerektiren diğer görevler için de kullanır.

Visual Studio'daki tüm yeni Python projeleri başlangıçta altında görünür varsayılan genel ortamı kullanmak üzere yapılandırılmış **Python ortamları** Çözüm Gezgini'nde düğümü:

![Çözüm Gezgini'nde gösterilen genel varsayılan Python ortamı](media/environments-project.png)

Diğer ortamlara sanal ortamlar dahil olmak üzere bu proje için kullanılabilir hale getirebilirsiniz. Herhangi bir anda yalnızca bir ortam etkinleştirilebilir.

## <a name="using-global-environments"></a>Genel ortamlar kullanarak

Belirli genel ortamları proje kullanılabilir hale getirmek için (conda ortamlar dahil [el ile tanımlanan](managing-python-environments-in-visual-studio.md#manually-identifying-an-existing-environment)), sağ **Python ortamları** düğümü ve select **Ekle/Kaldır Python ortamları...** . Görüntülenen listeden istenilen ortamları seçin:

![Ekle/Kaldır Python ortamları iletişim](media/environments-add-remove.png)

Seçtiğinizde, bundan sonra **Tamam**, seçilen tüm ortamlar görünür **Python ortamları** düğümü. Şu anda etkin ortam kalın olarak görünür:

![Çözüm Gezgini'nde gösterilen birden çok Python ortamı](media/environments-project-multiple.png)

Farklı bir ortam etkinleştirmek için ortam adı sağ tıklatın ve seçin **etkinleştirme ortamı**. Tercih ettiğiniz proje ile kaydedilir ve gelecekte projeyi açtığınızda, ortamda etkinleştirilir.

Tüm seçenekleri temizlerseniz **Ekle/Kaldır Python ortamları** iletişim kutusunda, Visual Studio genel varsayılan ortamını etkinleştirir.

## <a name="using-virtual-environments"></a>Sanal ortamlar kullanarak

Bir sanal özel bir Python yorumlayıcısı benzersiz bir bileşimi ve diğer genel ve conda ortamlarından farklı belirli kitaplıkların ortamıdır. Projede belirli gereksinimlere sahip ve bu ihtiyaçları karşılamak için diğer ortamlara değiştirmek istemiyorsanız, genellikle bir sanal ortam kullanın.

Bir sanal ortam projenize eklendikten sonra görünür **Python ortamları** penceresinde, etkinleştirebilir, herhangi bir ortamın gibi ve kendi paketleri yönetebilirsiniz.

Sanal ortamlar için bu bir dezavantajı Not bunlar sabit kodlanmış dosya yolları içerir ve bu nedenle kolayca paylaşılan veya değiştirilemez diğer geliştirme bilgisayarlara taşınan emin olan. Neyse ki, kullanabileceğiniz `requirements.txt` kolayca ortamı geri yüklemek projenizi alıcılarını izin vermek için dosya. Daha fazla bilgi için bkz: [requirements.txt ile gerekli paketleri yönetme](managing-required-packages-with-requirements-txt.md).

### <a name="activating-an-existing-virtual-environment"></a>Var olan bir sanal ortama etkinleştirme

Başka bir sanal ortam zaten oluşturduysanız, proje için şu şekilde etkinleştirebilirsiniz:

1. Sağ **Python ortamları** Çözüm Gezgini'nde ve select **varolan sanal ortam Ekle...** .

1. İçinde **Gözat** görünür, sanal ortamı içeren klasörü seçin ve seçmek için Bul iletişim **Tamam**. Visual Studio algılarsa bir `requirements.txt` dosyası bu ortamda, bu paketleri yüklenip yüklenmeyeceğini sorar.

1. Birkaç dakika sonra sanal ortam altında görüntülenir. **Python ortamları** Çözüm Gezgini'nde düğümü. Sanal ortam varsayılan olarak etkinleştirilmez, bu nedenle sağ tıklatın ve seçin **etkinleştirme ortamı**.

### <a name="creating-a-virtual-environment"></a>Bir sanal ortam oluşturma

Yeni bir sanal ortam doğrudan Visual Studio'dan aşağıdaki gibi oluşturabilirsiniz:

1. Sağ **Python ortamları** Çözüm Gezgini'nde ve select **sanal ortam Ekle...** , aşağıdaki iletişim kutusunu getirir:

    ![Bir sanal ortam oluşturma](media/environments-add-virtual-1.png)

1. İçinde **sanal ortam konumunu** alanında, sanal ortam için bir yol belirtin. Yalnızca bir adı belirtirseniz, sanal ortamı geçerli projede bu ada sahip bir alt klasörü içinde oluşturulur.

1. Bir ortam temel yorumlayıcı seçip **oluşturma**. Visual Studio ortamında yapılandırır ve tüm gerekli paketleri indirir bir ilerleme çubuğu görüntüler. Sanal ortam bu noktada görünür **Python ortamları** içeren proje penceresi.

1. Sanal ortam varsayılan olarak etkinleştirilmez. Proje için etkinleştirmek için sağ tıklatın ve seçin **etkinleştirme ortamı**.

> [!Note]
> Konum yolu var olan bir sanal ortama tanımlıyorsa, Visual Studio temel yorumlayıcı otomatik olarak algılar (kullanarak `orig-prefix.txt` ortam dosyasında `lib` dizini) ve Oluştur düğmesine dönüşür **Ekle**.
>
> Varsa bir `requirements.txt` dosyası mevcut bir sanal ortam eklerken **sanal ortam Ekle** iletişim başka bir bilgisayardaki bir ortamı yeniden kolaylaşır paketleri otomatik olarak yüklemek için bir seçenek görüntüler:
>
> ![Requirements.txt ile sanal ortam oluşturma](media/environments-requirements-txt.png)
>
> Kullanılan gibi her iki durumda da sonucu aynı ise **varolan sanal ortam Ekle...**  komutu.

### <a name="remove-a-virtual-environment"></a>Bir sanal ortam Kaldır

1. Çözüm Gezgini'nde, sanal ortama sağ tıklatıp **kaldırmak**.

1. Visual Studio kaldırın veya sanal ortamı silmek ister. Seçme **kaldırmak** projeye kullanılamaz hale getirir, ancak dosya sisteminde bırakır. Seçme **silmek** hem ortamı projeden kaldırır ve dosya sisteminden siler. Temel yorumlayıcı etkilenmez.

## <a name="viewing-installed-packages"></a>Görüntüleme yüklü paketleri

Çözüm Gezgini'nde, hızlı bir şekilde (almak ve ortam etkin olduğunda bu paketleri, kodunuzda kullanmak anlamına gelir), ortamda yüklü olan paketleri görüntülemek için belirli herhangi bir ortamın 's düğümünü genişletin:

![Çözüm Gezgini'nde bir ortam için Python paketlerini](media/environments-installed-packages.png)

Yeni paketleri yüklemek için ortam sağ tıklatın ve seçin **Python paketini yükle...**  geçmek için **paketleri** sekmesinde **Python ortamları** penceresi. Bir arama girin terim (genellikle paket adı) ve Visual Studio eşleşen paketleri görüntüler.

Visual Studio içinde gelen yüklenen paketler (ve bağımlılıklarını) [Python paket dizini (Pypı)](https://pypi.python.org/pypi), burada da kullanılabilir paketler için arama yapabilirsiniz. Visual Studio'nun durum çubuğu ve çıktı penceresi yükleme hakkında bilgi gösterir. Bir paketi kaldırmak için sağ seçin **kaldırmak**.

Görüntülenen girişler her zaman doğru olmayabilir ve yükleme ve kaldırma güvenilir veya kullanılabilir olmayabilir unutmayın. Visual Studio varsa, PIP Paket Yöneticisi kullanır ve indirir ve gerektiğinde yükler. Visual Studio easy_install Paket Yöneticisi'ni de kullanabilirsiniz. Kullanarak yüklü olan paketleri `pip` veya `easy_install` komut satırından da görüntülenir.

Ayrıca Visual Studio kullanarak şu anda desteklemiyor Not `conda` conda ortamına paketleri yüklemek için. Kullanım `conda` komuttan satır yerine.

> [!Tip]
> Paket yerel bileşenleri için kaynak kodunu içerir PIP nerede başarısız bir paketi yüklemek için yaygın bir durum olduğunda `*.pyd` dosyaları. Visual Studio yüklüyse gerekli sürümü, bu bileşenlerin PIP derlenemiyor. Bu durumda görüntülenen hata iletisi `error: Unable to find vcvarsall.bat`. `easy_install` önceden derlenmiş ikili dosyaları, genellikle indirebildiğini ve Python eski sürümleri için uygun bir derleyici indirebilirsiniz [http://aka.ms/VCPython27](http://aka.ms/VCPython27). Daha fazla ayrıntı için bkz: ["vcvarsallbat Bul kurulamıyor", sorunun nasıl](https://blogs.msdn.microsoft.com/pythonengineering/2016/04/11/unable-to-find-vcvarsall-bat/) üzerinde Python araçları takım Web günlüğü.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da Python ortamları yönetme](managing-python-environments-in-visual-studio.md)
- [Bağımlılıklar için requirements.txt dosyasını kullanma](managing-required-packages-with-requirements-txt.md)
- [Arama yolları](search-paths.md)
- [Python ortamları penceresi başvurusu](python-environments-window-tab-reference.md)