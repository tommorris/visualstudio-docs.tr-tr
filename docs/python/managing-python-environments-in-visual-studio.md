---
title: Python ortamları ve yorumlayıcılarını yönetin
description: Genel, sanal yönetmek için Python ortamları penceresi ve Python yorumlayıcılarını ve paketleri yükleme ve Visual Studio projelerine ortamları atama conda ortamları kullanın.
ms.date: 07/23/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 2b134dc54e2af31bb7d9fcb3f1dcdf3d31f799b5
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2018
ms.locfileid: "39232224"
---
# <a name="how-to-create-and-manage-python-environments-in-visual-studio"></a>Oluşturma ve Visual Studio'da Python ortamlarını yönetme

Bir Python *ortam* conda ortamları ise, Python kodunu çalıştırma ve içeren genel, sanal bir bağlamı. Bir ortam yorumlayıcıyı, bir kitaplık (genellikle Python standart kitaplığı) ve yüklü paketleri kümesi oluşur. Bu bileşenler birlikte hangi dil yapıları ve söz dizimi geçerli olduğunu belirler hangi işletim sistemi işlevselliği erişebilir ve hangi paketler kullanabilirsiniz.

Windows üzerinde Visual Studio'da [Python ortamları penceresi](#the-python-environments-window) penceresinde, bu makalede açıklandığı gibi burada bu ortamlarını yönetin ve yeni projeler için varsayılan olarak seçin. Verilen herhangi bir proje için ayrıca [belirli bir ortam seçin](selecting-a-python-environment-for-a-project.md) yerine varsayılan kullanın.

**Not**: Visual Studio'da Python yeniyseniz, gerekli arka plan için aşağıdaki makalelere bakın:

- [Visual Studio'da Python ile çalışma](overview-of-python-tools-for-visual-studio.md)
- [Visual Studio'da Python desteğini yükleme](installing-python-support-in-visual-studio.md)

Ayrıca diğer bir deyişle Python kodu için ortamları yönetemez Not açılan yalnızca bir klasör olarak **dosya** > **açık** > **klasör** komutu. Bunun yerine, [varolan koddan bir Python projesi oluşturma](quickstart-01-python-in-visual-studio-project-from-existing-code.md) ortamı özellikleri Visual Studio'nun yararlanabilmek için.

Bir ortamda paketleri yüklemek isterseniz, başvurmak [paketleri sekmesinde başvuru](python-environments-window-tab-reference.md#packages-tab).

## <a name="types-of-environments"></a>Çeşitli ortamlarda

### <a name="global-environments"></a>Genel ortam

Her bir Python yükleme (örneğin, Python 2.7, Python 3.6, Anaconda 4.4.0, vs. bkz [seçme ve Python yorumlayıcılarını yükleme](installing-python-interpreters.md)) kendi genel ortam tutar. Her ortam, belirli bir Python yorumlayıcısı, kendi standart kitaplığı ve bir dizi önceden yüklenmiş paketler oluşur. Genel bir ortama bir paket yükleme o ortamı kullanarak tüm projeleri için kullanılabilir yapar. Ortamı bir dosya sistemini koruma alanında bulunuyorsa, (içinde `c:\program files`, örneğin), sonra da paketleri yüklemek için yönetici ayrıcalıkları gerekiyor.

Genel ortamları, bilgisayardaki tüm projeleri için kullanılabilir. Visual Studio'da bir proje için başka bir özellikle seçmediğiniz sürece, tüm projeler için kullanılan varsayılan olarak genel bir ortam seçin. Daha fazla bilgi için [bir proje için bir ortam seçerek](selecting-a-python-environment-for-a-project.md).

### <a name="virtual-environments"></a>Sanal ortamlar

Genel bir ortama yüklenmişse paketleri bu ortamda kullanan tüm projeler için kullanılabilir olmadığından, iki proje uyumsuz paketler veya aynı paketin farklı sürümlerini gerektiğinde çakışmaları oluşabilir. Sanal ortamlar bu gibi çakışmaları yorumlayıcı ve genel bir ortamdan standart Kitaplığı'nı kullanarak ancak kendi yalıtılmış klasörleri paket depolarında koruma kaçının.

Visual Studio'da bir alt proje klasöründe depolanan belirli bir proje için sanal bir ortam oluşturabilirsiniz. Visual Studio sağlar oluşturmak için bir komutu bir `requirements.txt` dosyasından sanal ortam, diğer bilgisayarlardaki ortamı yeniden kolaylaştırır. Daha fazla bilgi için [sanal ortamları kullanarak](selecting-a-python-environment-for-a-project.md#using-virtual-environments).

### <a name="conda-environments"></a>Conda ortamları

Conda ortam biridir kullanılarak oluşturulan `conda` aracı veya tümleşik conda Yönetimi'nde Visual Studio 2017 sürüm 15.7 ve üzeri. (Anaconda veya Miniconda gerektirir; Visual Studio yükleyicisi anaconda kullanılabilir, bkz: [yükleme - Visual Studio 2017](installing-python-support-in-visual-studio.md#visual-studio-2017).)

> [!Note]
> Conda ortamları ile en iyi sonuçları almak için conda 4.4.8 kullanın veya üzeri (conda sürümleri Anaconda sürümlerinden farklı). Anaconda 5.1 Visual Studio 2017 Yükleyicisi'nden yükleme

Conda ortamları depolandığı, conda sürümü ve diğer bilgileri görmek için şunu çalıştırın `conda info` bir Anaconda komut isteminde (diğer bir deyişle, Anaconda yolu olduğu bir komut istemi):

```cli
conda info
```

Conda ortam klasörlerinizi şu şekilde görünür:

```output
       envs directories : c:\anaconda3\envs
                          C:\Users\user\AppData\Local\conda\conda\envs
                          C:\Users\user\.conda\envs
```

Conda ortamları içeren bir proje depolanmadığından bunlar genel ortamlara benzer şekilde davranır. Örneğin, conda ortamına yeni bir paket yükleme, paketin bu ortam kullanarak tüm projeleri için kullanılabilir hale getirir.

İçin Visual Studio 2017 sürüm 15.6 ve önceki sürümleri, kendisine altında açıklandığı gibi manuel olarak işaret ederek conda ortamları kullanabilirsiniz [el ile bir ortamı tanımlamanız](#manually-identify-an-existing-environment).

Visual Studio 2017 sürüm 15.7 ve üzeri conda ortamları otomatik olarak algılar ve bunları görüntüler **Python ortamları** sonraki bölümde açıklandığı gibi penceresi.

## <a name="the-python-environments-window"></a>Python ortamları penceresi

Visual Studio bildiği ortamlar görüntülenir **Python ortamları** penceresi. , Penceresini açmak için aşağıdaki yöntemlerden birini kullanın:

- Seçin **görünümü** > **diğer Windows** > **Python ortamları** menü komutu.
- Sağ **Python ortamları** seçip Çözüm Gezgini'nde bir proje düğümü **tüm Python ortamları görüntüleme**:

    ![Çözüm Gezgini görünümü tüm ortamları komutu](media/environments-view-all.png)

Her iki durumda da **Python ortamları** Çözüm Gezgini için eşdüzey sekme olarak penceresi görüntülenir:

![Python ortamları penceresi](media/environments-default-view.png)

Visual Studio aşağıdaki [CESARETLENDİRİCİ 514](https://www.python.org/dev/peps/pep-0514/) kayıt defterini kullanarak yüklü ortamları tanımlamak için. Listenin beklenen bir ortamda görmüyorsanız bkz [el ile bir ortamı tanımlamanız](#manually-identify-an-existing-environment).

Listeden bir ortam gösterilir çeşitli özellikler ve o ortama ait komutları **genel bakış** sekmesi. Örneğin, yukarıdaki görüntüde Yorumlayıcı'nın konumunun gördüğünüz `C:\Python36-32`. Farklı sekmelere gibi geçmek için ortamları listesinin altındaki açılır listede kullanmak **paketleri**, ve **IntelliSense**. Bu sekmeler açıklanan [Python ortamları penceresi sekme başvurusu](python-environments-window-tab-reference.md).

Bir ortam seçerek herhangi bir yolla etkinleştirmez. Kalın listesinde gösterilen varsayılan ortamı, tüm yeni projeler için Visual Studio kullanan etkin ortamıdır. Farklı bir ortama etkinleştirmek için kullandığınız **varsayılan ortama yeni projeler için bunu yap** komutu. Bir proje bağlamında farklı bir ortam her zaman etkinleştirebilirsiniz. Daha fazla bilgi için [bir proje için bir ortam seçerek](selecting-a-python-environment-for-a-project.md).

Listelenen her bir ortamın sağa bu ortam için etkileşimli bir pencere açan bir denetimdir. (Visual Studio 2017 15.5 ve önceki sürümlerinde, başka bir denetimde görünür, bu ortam için IntelliSense veritabanı yeniler. Bkz: [ortamları penceresi sekme başvurusu](python-environments-window-tab-reference.md#intellisense-tab) veritabanı hakkındaki ayrıntılar için).

> [!Tip]
> Genişlettiğinizde **Python ortamları** penceresinde yetecek kadar geniş bir irdelemesi çalışmak daha kullanışlı bulabilirsiniz ortamlarınızda görünümünü alın.
>
> ![Python ortamları penceresi Genişletilmiş Görünümü](media/environments-expanded-view.png)

> [!Note]
> Visual Studio sistem site paketleri seçeneği uyar olsa da, bunu Visual Studio içinden gelen değiştirmek için bir yol sağlamaz.

|   |   |
|---|---|
| ![video kamera simgesini film](../install/media/video-icon.png "bir video izleyin") | [(Microsoft Virtual Academy) videoyu](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=qrDmN4LWE_8305918567) (2 dk. 35s) Visual Studio'da Python ortamlarında.|

### <a name="what-if-no-environments-appear"></a>Peki ortamı yok görünüyor?

Ortam görünüyorsa, standart konumda herhangi bir Python yüklemelerini algılamak Visual Studio başarısız anlamına gelir. Örneğin, edebilirsiniz Visual Studio 2017 yüklü, ancak Python iş yükü için yükleyici seçenekleri tüm yorumlayıcı seçeneklerinde temizlenir. Benzer şekilde, Visual Studio 2015 veya önceki bir sürümünü yüklemiş olabilirsiniz ancak yorumlayıcıyı el ile yüklenmedi (bkz [yükleme Python yorumlayıcılarını](installing-python-interpreters.md)).

Python yorumlayıcısı bilgisayarınızda yüklü, ancak Visual Studio (herhangi bir sürüm) değil, algılayabilir, ardından kullanmak biliyorsanız **+ özel...**  konumuna el ile belirtmek için komutu. Sonraki bölüme bakın [el ile bir ortamı tanımlamanız](#manually-identify-an-existing-environment).

> [!Tip]
> Visual Studio güncelleştirmeleri Python 2.7.11'i için yükleyicileri python.org gelen kullanarak 2.7.14 yükseltme gibi mevcut bir yorumlayıcı algılar. Eski ortam yükleme işlemi sırasında kaybolur **Python ortamları** yerinde güncelleştirme görünmeden önce listesi.
>
> Ancak, el ile yorumlayıcıyı ve dosya sistemi kullanılarak ortam taşırsanız, Visual Studio yeni konuma bilemezsiniz. Daha fazla bilgi için [yorumlayıcıyı taşıma](installing-python-interpreters.md#moving-an-interpreter).

## <a name="fix-or-delete-invalid-environments"></a>Düzeltme ya da geçersiz ortamları silme

Visual Studio, bir ortam için kayıt defteri girdileri bulur, ancak yorumlayıcı yolu geçersiz, Python ortamları pencerenin üstü çizili yazı tipi adıyla gösterir:

![Geçersiz bir ortam gösteren Python ortamları penceresi](media/environments-invalid-entry.png)

Korumak istediğiniz ortam düzeltmek için önce kendi Yükleyicisi'nin kullanmayı deneyin **onarım** işlem. Yükleyicileri standart Python 3.x, örneğin, bu seçenek içerir.

Bir ortam düzeltmek için Onar seçeneğini yok veya geçersiz bir ortam kaldırmak için doğrudan kayıt defterini değiştirmek için aşağıdaki adımları kullanın. Kayıt defterinde değişiklik yaptığınızda visual Studio Python ortamları penceresi otomatik olarak güncelleştirir.

1. Çalıştırma `regedit.exe`.
1. Gidin `HKEY_LOCAL_MACHINE\SOFTWARE\Python` 32-bit yorumlayıcılar için veya `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Python` 64-bit yorumlayıcılar için. IronPython için aranacak `IronPython` yerine.
1. Dağıtım yapınızla eşleşen düğümünü `PythonCore` CPython için veya `ContinuumAnalytics` Anaconda için. IronPython için sürüm numarası düğümünü genişletin.
1. Altındaki değerleri inceleyin `InstallPath` düğüm:

    ![Tipik bir CPython yüklemesi için kayıt defteri girişleri](media/environments-registry-entries.png)

    - Ortam bilgisayarınızda hala devam ediyorsa, değiştirin `ExecutablePath` doğru konuma. Ayrıca düzeltmek `(Default)` ve `WindowedExecutablePath` değerleri gerektiği şekilde.
    - Ortam artık bilgisayarınızda varsa ve Python ortamlarını penceresinden kaldırmak istediğiniz üst düğümü Sil `InstallPath`, gibi `3.6` yukarıdaki resimde.

<a name="manually-identifying-an-existing-environment"></a>

## <a name="manually-identify-an-existing-environment"></a>El ile bir ortamı tanımlayın

(Visual Studio 2017 sürüm 15.6 ve önceki conda ortamları dahil olmak üzere) standart olmayan bir konumda yüklü olduğu bir ortamı tanımlamak için aşağıdaki adımları kullanın:

1. Seçin **+ özel** içinde **Python ortamları** açılır penceresinde **yapılandırma** sekmesinde:

    ![Yeni özel bir ortam için varsayılan görünüm](media/environments-custom-1.png)

1. Ortamda için bir ad girin **açıklama** alan.

1. Girin veya gözatın (kullanarak **... ***) yorumlayıcıda yoluna **ön ek yolu** alan.

1. Visual Studio bu konuma (örneğin, yol conda ortamı için aşağıda gösterilen) bir Python yorumlayıcısı algılarsa, bağlayabileceğinizi **otomatik algıla** komutu. Seçme **otomatik algıla* kalan alanları tamamlar. Bu alanları el ile tamamlayabilirsiniz.

    ![Otomatik Algıla komutu etkinleştirme](media/environments-custom-2.png)

    ![Otomatik Algıla kullandıktan sonra ortamı alanlarının tamamlama](media/environments-custom-3.png)

1. Alanları istediğiniz değerleri içeren bir kez seçin **Uygula** yapılandırmayı kaydetmek için. Artık Visual Studio içindeki diğer gibi ortam kullanabilirsiniz.

1. El ile tanımlanan ortam kaldırmanız gerekirse, seçin **Kaldır** komutunu **yapılandırma** sekmesi. Bu seçenek otomatik olarak algılanan ortamları sağlamaz. Daha fazla bilgi için [yapılandırma sekmesinden](python-environments-window-tab-reference.md#configure-tab).

## <a name="create-a-conda-environment"></a>Conda ortamı oluşturma

*Visual Studio 2017 sürüm 15.7 ve üzeri.*

1. Seçin **+ conda ortam Oluştur** içinde **Python ortamları** açılır penceresinde bir **yeni conda ortam Oluştur** sekmesinde:

    ![Yeni bir conda ortamı için sekmesinde oluşturun](media/environments-conda-1.png)

1. Ortamda için bir ad girin **adı** alanında, temel bir Python yorumlayıcısı içinde seçin **Python** alan ve seçim **Oluştur**.

1. **Çıkış** penceresi oluşturma işlemi tamamlandıktan sonra birkaç CLI yönergeleri ile yeni bir ortam için ilerleme durumunu gösterir:

    ![Conda ortam oluşturma başarılı](media/environments-conda-2.png)

1. Visual Studio içinde herhangi bir ortam üzerinde açıklandığı gibi bir proje için bir conda ortamı etkinleştirebilir [bir proje için bir ortam seçerek](selecting-a-python-environment-for-a-project.md).

1. Ortamınıza paketleri yüklemek için kullanın [paketleri sekmesinde](python-environments-window-tab-reference.md#packages-tab).

## <a name="see-also"></a>Ayrıca bkz.

- [Python yorumlayıcılarını yükleme](installing-python-interpreters.md)
- [Proje için yorumlayıcıyı seçme](selecting-a-python-environment-for-a-project.md)
- [Bağımlılıklar için requirements.txt dosyasını kullanma](managing-required-packages-with-requirements-txt.md)
- [Arama yolları](search-paths.md)
- [Python ortamları penceresi başvurusu](python-environments-window-tab-reference.md)
