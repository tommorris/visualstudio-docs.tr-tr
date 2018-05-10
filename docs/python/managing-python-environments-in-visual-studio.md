---
title: Python ortamları ve yorumlayıcılar yönetme
description: Genel, sanal yönetmek için Python ortamları penceresi ve Python yorumlayıcılar ve paketleri yükleme ve Visual Studio projelerine ortamları atama conda ortamları kullanın.
ms.date: 03/21/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: fbefd6a09537227f9b2343d2311dd1e68b9f0a23
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-create-and-manage-python-environments-in-visual-studio"></a>Oluşturma ve Visual Studio Python ortamlarında yönetme

Bir Python *ortam* conda ortamları ise, Python kodu çalıştırmak ve içeren genel, sanal bir bağlam. Bir ortam bir yorumlayıcı, bir kitaplık (genellikle Python standart kitaplığı) ve yüklü paketler kümesini oluşur. Bu bileşenlerin, birlikte hangi dil yapıları ve sözdizimi geçerli olduğunu belirlemek hangi işletim sistemi işlevselliği erişebilir ve hangi paketleri kullanabilirsiniz.

Windows, Visual Studio'da [Python ortamları penceresi](#the-python-environments-window) , bu makalede açıklanan penceredir burada bu ortamlarını yönetebilir ve yeni projeler için varsayılan olarak seçin. Verilen herhangi bir projeye için Ayrıca belirli bir ortam seçin yerine, varsayılan kullanın.

**Not**: Visual Studio'da Python yeniyseniz, gerekli arka plan için aşağıdaki makalelere bakın:

- [Visual Studio'da Python ile çalışma](overview-of-python-tools-for-visual-studio.md)
- [Visual Studio'da Python desteğini yükleme](installing-python-support-in-visual-studio.md)

Ayrıca başka bir deyişle Python kodu için ortamları yönetemez not yalnızca bir klasör kullanılarak açılır olarak **dosya** > **açık** > **klasörü** komutu. Bunun yerine, [var olan koddan Python projesi oluşturma](quickstart-01-python-in-visual-studio-project-from-existing-code.md) Visual Studio'nun ortam özellikleri keyfini için.

Bir ortamda paketleri yüklemek istiyorsanız, başvurmak [Paketleri sekmesi](python-environments-window-tab-reference.md#packages-tab).

## <a name="types-of-environments"></a>Tür ortamlarda

### <a name="global-environments"></a>Genel ortamları

Her bir Python yükleme (örneğin, Python 2.7, Python 3.6, Anaconda 4.4.0, vb., bkz: [seçerek ve Python yorumlayıcılar yükleme](installing-python-interpreters.md)) kendi genel ortam korur. Her ortam belirli Python Yorumlayıcı, kendi standart kitaplığı ve önceden yüklenmiş paket kümesini oluşur. Bir paket genel bir ortama yükleme bu ortam kullanarak tüm projeleri için kullanılabilir kılar. Ortamında bir dosya sistemini koruma alanında bulunuyorsa (içinde `c:\program files`, örneğin), sonra da paketler yönetici ayrıcalıkları gerektirir.

Genel ortamları, bilgisayardaki tüm projeleri için kullanılabilir. Visual Studio'da bir proje için farklı bir özellikle seçmediğiniz sürece, tüm projeleri için kullanılan varsayılan olarak genel bir ortam seçin. Daha fazla bilgi için bkz: [bir proje için bir ortam seçerek](selecting-a-python-environment-for-a-project.md).

### <a name="virtual-environments"></a>Sanal ortamlar

Genel bir ortama yüklenmişse paketler bu ortam kullanan tüm projeleri için kullanılabilir olduğundan, iki proje uyumsuz paketleri veya aynı paketin farklı sürümlerini gerektirdiğinde çakışmaları oluşabilir. Sanal ortamlar bu gibi çakışmaları yorumlayıcı ve standart kitaplığı genel ortamından kullanarak ancak kendi yalıtılmış klasörleri paket depolarında koruma kaçının.

Visual Studio'da bir alt proje klasöründe depolanan belirli bir proje için sanal bir ortam oluşturabilirsiniz. Visual Studio sağlayan bir komut oluşturmak için bir `requirements.txt` dosya sanal ortamdan ortamında diğer bilgisayarlar üzerinde yeniden kolaylaşır. Daha fazla bilgi için bkz: [sanal ortamlar kullanarak](selecting-a-python-environment-for-a-project.md#using-virtual-environments).

### <a name="conda-environments"></a>Conda ortamları

Conda ortam biri kullanılarak oluşturulan `conda` aracı veya Visual Studio 2017 sürüm 15.7 ve daha yüksek tümleşik conda yönetimi ile. (Anaconda veya Miniconda gerektirir; Visual Studio yükleyicisi anaconda kullanılabilir, bkz: [yükleme - Visual Studio 2017](installing-python-support-in-visual-studio.md#visual-studio-2017).)

> [!Note]
> Conda 4.4.8 conda ortamlar ile en iyi sonuçlar için kullanmak veya sonraki bir sürümü (conda sürümleri Anaconda sürümlerinden farklı). Visual Studio 2017 Yükleyicisi'nden Anaconda 5.1 yükleme

Conda ortamları depolandığı, conda sürümü ve diğer bilgileri görmek için çalıştırın `conda info` bir Anaconda komut isteminde (diğer bir deyişle, Anaconda yolunda olduğu bir komut istemi):

```bash
conda info
```
Conda ortam klasörleri şu şekilde görünür:

```output
       envs directories : c:\anaconda3\envs
                          C:\Users\user\AppData\Local\conda\conda\envs
                          C:\Users\user\.conda\envs
```

Conda ortamları bir projesiyle depolanmadığından, bunlar genel ortamlar için benzer şekilde davranır. Örneğin, bir conda ortamına yeni bir paket yükleme, paketin bu ortam kullanarak tüm projeleri için kullanılabilir hale getirir.

Visual Studio 2017 için sürüm 15.6 ve önceki sürümlerde, bunları el ile altında açıklandığı gibi göstererek conda ortamları kullanabilirsiniz [el ile varolan bir ortama tanımlamanız](#manually-identify-an-existing-environment).

Visual Studio 2017 15.7 ve sonraki sürümleri conda ortamları otomatik olarak algılar ve bunları görüntüler **Python ortamları** sonraki bölümde açıklandığı gibi penceresi.

## <a name="the-python-environments-window"></a>Python ortamları penceresi

Visual Studio bildiği ortamları görüntülenen **Python ortamları** penceresi. , Penceresini açmak için aşağıdaki yöntemlerden birini kullanın:

- Seçin **Görünüm** > **diğer pencereler** > **Python ortamları** menü komutu.
- Sağ **Python ortamları** düğümü seçip Çözüm Gezgini proje için **görünümü tüm Python ortamları**:

    ![Çözüm Gezgini'nde görünümü tüm ortamlar komutu](media/environments-view-all.png)

Her iki durumda da **Python ortamları** Çözüm Gezgini eşdüzey sekmeye olarak pencere görünür:

![Python ortamları penceresi](media/environments-default-view.png)

Tüm yeni projeler için Visual Studio kullanan Python 3.6 kalın olarak varsayılan ortamıdır. Herhangi bir türde herhangi bir listelenen ortam varsayılan olarak kullanılabilir.

Gördüğünüz gibi belirli yüklemesi seçilen yorumlayıcısı penceresinin alt kısmındaki komutları uygulamak içinde `C:\Python36-32` (kalın varsayılan ortam Anaconda yüklemenin parçası olan). Beklediğiniz bir ortam görmüyorsanız bkz [el ile varolan bir ortama tanımlamanız](#manually-identify-an-existing-environment).

Listelenen her ortam sağındaki bu ortam için etkileşimli bir pencere açılır bir denetimdir. (Visual Studio 2017 15,5 ve önceki sürümlerinde, başka bir denetim görünür, bu ortam için IntelliSense veritabanı yeniler. Bkz: [ortamları penceresi başvuru](python-environments-window-tab-reference.md#intellisense-tab) veritabanı hakkındaki ayrıntılar için).

Ortamlar açılan Seçici için listesidir **genel bakış**, **paketleri**, ve **IntelliSense** açıklanan seçenekler [Python ortamları Pencere sekme başvurusu](python-environments-window-tab-reference.md). Ayrıca, genişletirseniz **Python ortamları** yetecek kadar geniş penceresinde, bu seçenekleri ile çalışmak daha kolay bulabilirsiniz sekmeleri olarak gösterilir:

![Python ortamları genişletilmiş penceresi görünümü](media/environments-expanded-view.png)

Yukarıdaki resimde ortamlar oluşturmak için ek komutlar yanı sıra belirli bu bilgisayarda ortamlar tam listesini görebilirsiniz.

> [!Note]
> Visual Studio sistemi site paketleri seçeneği dikkate alır ancak ondan Visual Studio içinde değiştirmek için bir yol sağlamaz.

|   |   |
|---|---|
| ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin") | [(Microsoft Virtual Academy) bir video izlemek](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=qrDmN4LWE_8305918567) (2 m 35s) Visual Studio'da Python ortamları üzerinde.|

### <a name="what-if-no-environments-appear"></a>Ne hiçbir ortamları görünür?

Hiçbir ortamları görünüyorsa, herhangi bir Python yüklemesi standart konumlarda algılamak Visual Studio başarısız anlamına gelir. Örneğin, edebilirsiniz Visual Studio 2017 yüklü, ancak Python iş yükü için yükleyici seçenekleri tüm yorumlayıcı seçeneklerinde temizlendi. Benzer şekilde, Visual Studio 2015 veya önceki bir sürümünü yüklemiş olabilir ancak bir yorumlayıcı el ile yüklemedi (bkz [yükleme Python yorumlayıcılar](installing-python-interpreters.md)).

Bilgisayarınızda bir Python yorumlayıcısı var ancak Visual Studio (tüm sürümler) değil algılaması yeniden kullanın biliyorsanız **+ özel...**  konumuna el ile belirtmek için komutu. Sonraki bölüme bakın [el ile varolan bir ortama tanımlamanız](#manually-identify-an-existing-environment).

> [!Tip]
> Visual Studio güncelleştirmeleri Python 2.7.11'i için python.org gelen yükleyicileri kullanarak 2.7.14 yükseltme gibi varolan bir yorumlayıcı algılar. Eski ortam yükleme işlemi sırasında kaybolur **Python ortamları** yerinde güncelleştirme görünmeden önce listesi.
>
> Ancak, el ile bir yorumlayıcı ve dosya sistemi kullanılarak ortamına taşırsanız, Visual Studio yeni konumu bilemezsiniz. Daha fazla bilgi için bkz: [bir yorumlayıcı taşıma](installing-python-interpreters.md#moving-an-interpreter).

< a name = "el ile tanımlama-bir-varolan-ortam ></a>

## <a name="manually-identify-an-existing-environment"></a>El ile varolan bir ortama tanımlayın

(Visual Studio 2017 sürüm 15.6 ve önceki conda ortamlar dahil) standart olmayan bir konumda yüklü bir ortam belirlemek için aşağıdaki adımları kullanın:

1. Seçin **+ özel** içinde **Python ortamları** açılır pencere **yapılandırma** sekmesi:

    ![Yeni bir özel ortamı için varsayılan görünüm](media/environments-custom-1.png)

1. Bir ortamda adı **açıklama** alan.

1. Girin veya gözatın (kullanarak **... ***) yorumlayıcı yola **öneki yolu** alan.

1. Visual Studio (örneğin, bir conda ortamı için aşağıda yolu) bu konumda bir Python yorumlayıcısı algılarsa, sağlayan **otomatik algıla** komutu. Seçerek **otomatik algıla* kalan alanları tamamlar. Bu alanlar el ile tamamlayabilirsiniz.

    ![Otomatik Algıla komutu etkinleştirme](media/environments-custom-2.png)

    ![Otomatik Algıla kullandıktan sonra ortamı alanlarının tamamlama](media/environments-custom-3.png)

1. Alanları istediğiniz değerleri içeren bir kez seçin **Uygula** yapılandırmayı kaydetmek için. Ortam gibi diğer Visual Studio içinde artık kullanabilirsiniz.

1. El ile tanımlanan ortam kaldırmanız gerekirse, seçin **kaldırmak** komutunu **yapılandırma** sekmesi. Bu seçenek otomatik olarak algılanır ortamları sağlamaz. Daha fazla bilgi için bkz: [yapılandırma sekmesinden](python-environments-window-tab-reference.md#configure-tab).

## <a name="create-a-conda-environment"></a>Conda ortam oluşturma

*Visual Studio 2017 15.7 ve sonraki sürümleri.*

1. Seçin **+ Oluştur conda ortam** içinde **Python ortamları** açılır penceresi bir **oluştur yeni conda ortamı** sekmesi:

    ![Yeni bir conda ortamı için sekmesi oluştur](media/environments-conda-1.png)

1. Ortamında için bir ad girin **adı** alanında, bir taban Python yorumlayıcısı seçin **Python** alan ve select **oluşturma**.

1. **Çıkış** penceresi oluşturmayı tamamladıktan sonra birkaç CLI yönergeler içeren yeni bir ortam için ilerleyişi gösterir:

    ![Başarılı bir şekilde oluşturulduktan conda ortamı](media/environments-conda-2.png)

1. Visual Studio içinde açıklandığı gibi herhangi bir ortam olduğu gibi bir proje için bir conda ortamı etkinleştirebilirsiniz [bir proje için bir ortam seçerek](selecting-a-python-environment-for-a-project.md).

1. Ortamında paketleri yüklemek için kullandığınız [Paketleri sekmesi](python-environments-window-tab-reference.md#packages-tab).

## <a name="see-also"></a>Ayrıca bkz.

- [Python yorumlayıcılar yükleme](installing-python-interpreters.md)
- [Proje için yorumlayıcıyı seçme](selecting-a-python-environment-for-a-project.md)
- [Bağımlılıklar için requirements.txt dosyasını kullanma](managing-required-packages-with-requirements-txt.md)
- [Arama yolları](search-paths.md)
- [Python ortamları penceresi başvurusu](python-environments-window-tab-reference.md)