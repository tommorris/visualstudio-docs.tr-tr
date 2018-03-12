---
title: "Python ortamları ve Visual Studio yorumlayıcılar yönetme | Microsoft Docs"
description: "Genel yönetmek için Visual Studio ve Python yorumlayıcılar yükleme, paketleri yükleme, arama yolları ayarlama ve ortamlar için Visual Studio Projeleri Yönetme özel ortamları ayarlama sanal ortamlar Python ortamları penceresini kullanma"
ms.custom: 
ms.date: 03/05/2018
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
ms.openlocfilehash: 558ce58461b27bc9a86906278602d00d96377c63
ms.sourcegitcommit: 3285243d6c0521266053340fe06505885d12178b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2018
---
# <a name="managing-python-environments-in-visual-studio"></a>Visual Studio'da Python ortamları yönetme

Bir Python *ortam* conda ortamları ise, Python kodu çalıştırmak ve içeren genel, sanal bir bağlam. Bir ortam bir yorumlayıcı, bir kitaplık (genellikle Python standart kitaplığı) ve yüklü paketler kümesini oluşur. Bu bileşenlerin, birlikte hangi dil yapıları ve sözdizimi geçerli olduğunu belirlemek hangi işletim sistemi işlevselliği erişebilir ve hangi paketleri kullanabilirsiniz.

Windows, Visual Studio'da [Python ortamları](#managing-python-environments-in-visual-studio) , bu makalede açıklanan penceredir burada bu ortamlarını yönetebilir ve yeni projeler için varsayılan olarak seçin. Verilen herhangi bir projeye için Ayrıca belirli bir ortam seçin yerine, varsayılan kullanın.

**Not**: Visual Studio'da Python yeniyseniz, gerekli arka plan için aşağıdaki makalelere bakın:

- [Visual Studio'da Python ile çalışma](overview-of-python-tools-for-visual-studio.md)
- [Visual Studio'da Python desteğini yükleme](installing-python-support-in-visual-studio.md)

Ayrıca başka bir deyişle Python kodu için ortamları yönetemez not yalnızca bir klasör kullanılarak açılır olarak **Dosya > Aç > klasör** komutu. Bunun yerine, [var olan koddan Python projesi oluşturma](quickstart-01-python-in-visual-studio-project-from-existing-code.md) Visual Studio'nun ortam özellikleri keyfini için.

## <a name="types-of-environments"></a>Tür ortamlarda

### <a name="global-environments"></a>Genel ortamları

Her bir Python yükleme (örneğin, Python 2.7, Python 3.6, Anaconda 4.4.0, vb., bkz: [seçerek ve Python yorumlayıcılar yükleme](installing-python-interpreters.md)) kendi genel ortam korur. Her ortam belirli Python Yorumlayıcı, kendi standart kitaplığı ve önceden yüklenmiş paket kümesini oluşur. Bir paket genel bir ortama yükleme bu ortam kullanarak tüm projeleri için kullanılabilir kılar. Ortamında bir dosya sistemini koruma alanında bulunuyorsa (içinde `c:\program files`, örneğin), sonra da paketler yönetici ayrıcalıkları gerektirir.

Genel ortamları, bilgisayardaki tüm projeleri için kullanılabilir. Visual Studio'da bir proje için farklı bir özellikle seçmediğiniz sürece, tüm projeleri için kullanılan varsayılan olarak genel bir ortam seçin. Daha fazla bilgi için bkz: [bir proje için bir ortam seçerek](selecting-a-python-environment-for-a-project.md).

### <a name="virtual-environments"></a>Sanal ortamlar

Genel bir ortama yüklenmişse paketler bu ortam kullanan tüm projeleri için kullanılabilir olduğundan, iki proje uyumsuz paketleri veya aynı paketin farklı sürümlerini gerektirdiğinde çakışmaları oluşabilir. Sanal ortamlar bu gibi çakışmaları yorumlayıcı ve standart kitaplığı genel ortamından kullanarak ancak kendi yalıtılmış klasörleri paket depolarında koruma kaçının.

Visual Studio'da bir alt proje klasöründe depolanan belirli bir proje için sanal bir ortam oluşturabilirsiniz (bkz [sanal ortamları oluşturma](selecting-a-python-environment-for-a-project.md#creating-a-virtual-environment). Proje dosyası, aynı zamanda sanal ortam tanımlar. Visual Studio ayrıca, projenin bu sanal ortama yükleme herhangi bir paket kaydeder `requirements.txt` dosya. Proje sonra paylaşımı ve isteğe bağlı olarak diğer geliştiriciler bilgisayarlarında açarsanız, Visual Studio sanal ortamı yeniden oluşturmak için seçeneği sağlar.

### <a name="conda-environments"></a>Conda ortamları

Conda ortam biri kullanılarak oluşturulan `conda` aracı. Conda ortamları tipik olarak depolanır `envs` klasör Anaconda yükleme ve bu nedenle act benzer şekilde çok genel ortamlar içinde. Örneğin, bir conda ortamına yeni bir paket yükleme, paketin bu ortam kullanarak tüm projeleri için kullanılabilir hale getirir.

Visual Studio şu anda otomatik olarak conda ortamları algılamazsa, ancak kendisine el ile Visual Studio gösterebilir. Bkz: [el ile varolan bir ortama tanımlayan](#manually-identifying-an-existing-environment).

## <a name="the-python-environments-window"></a>Python ortamları penceresi

Visual Studio bildiği ortamları görüntülenen **Python ortamları** penceresi. , Penceresini açmak için aşağıdaki yöntemlerden birini kullanın:

- Seçin **Görünüm > Diğer Pencereler > Python ortamları** menü komutu.
- Sağ **Python ortamları** düğümü seçip Çözüm Gezgini proje için **görünümü tüm Python ortamları**:

    ![Çözüm Gezgini'nde görünümü tüm ortamlar komutu](media/environments-view-all.png)

Her iki durumda da **Python ortamları** Çözüm Gezgini eşdüzey sekmeye olarak pencere görünür:

![Python ortamları penceresi](media/environments-default-view.png)

Yukarıdaki resimde, Visual Studio Anaconda 5.0.0 birlikte Python 3.6 (32 bit) iki yüklemeleri algılanan gösterir.

Kalın varsayılan ortamında Python tüm yeni projeler için Visual Studio kullanan 3.6 (Anaconda yüklemesi bu durumda parçası), ' dir. Seçilen Python görebilirsiniz, siz yorumlayıcı olduğu belirli yüklemesinde 3.6 penceresinin alt kısmındaki komutları uygulamak `C:\Python36-32`. Beklediğiniz bir ortam görmüyorsanız bkz [el ile varolan bir ortama tanımlayan](#manually-identifying-an-existing-environment).

Listelenen her ortam sağındaki bu ortam için etkileşimli bir pencere açılır bir denetimdir. Bu ortam için IntelliSense veritabanı yeniler başka bir denetim görüntülenebilir (bkz [ortamları penceresi başvuru](python-environments-window-tab-reference.md#intellisense-tab) veritabanı hakkındaki ayrıntılar için).

Ortamlar açılan Seçici için listesidir **genel bakış**, **paketleri**, ve **IntelliSense** açıklanan seçenekler [Python ortamları Pencere sekme başvurusu](python-environments-window-tab-reference.md). Ayrıca, genişletirseniz **Python ortamları** yetecek kadar geniş penceresinde, bu seçenekleri ile çalışmak daha kolay bulabilirsiniz sekmeleri olarak gösterilir:

![Python ortamları genişletilmiş penceresi görünümü](media/environments-expanded-view.png)

> [!Note]
> Visual Studio sistemi site paketleri seçeneği dikkate alır ancak ondan Visual Studio içinde değiştirmek için bir yol sağlamaz.

|   |   |
|---|---|
| ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin") | [(Microsoft Virtual Academy) bir video izlemek](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=qrDmN4LWE_8305918567) (2 m 35s) Visual Studio'da Python ortamları üzerinde.|

### <a name="what-if-no-environments-appear"></a>Ne hiçbir ortamları görünür?

Hiçbir ortamları görünüyorsa, herhangi bir Python yüklemesi standart konumlarda algılamak Visual Studio başarısız anlamına gelir. Örneğin, edebilirsiniz Visual Studio 2017 yüklü, ancak Python iş yükü için yükleyici seçenekleri tüm yorumlayıcı seçeneklerinde temizlendi. Benzer şekilde, Visual Studio 2015 veya önceki bir sürümünü yüklemiş olabilir ancak bir yorumlayıcı el ile yüklemedi (bkz [seçme ve Python yorumlayıcılar yükleme](installing-python-interpreters.md)).

Bilgisayarınızda bir Python yorumlayıcısı var ancak Visual Studio (tüm sürümler) değil algılaması yeniden kullanın biliyorsanız **+ özel...**  konumuna el ile belirtmek için komutu. Sonraki bölüme bakın [el ile varolan bir ortama tanımlayan](#manually-identifying-an-existing-environment).

> [!Tip]
> Visual Studio güncelleştirmeleri Python 2.7.11'i için python.org gelen yükleyicileri kullanarak 2.7.14 yükseltme gibi varolan bir yorumlayıcı algılar. Eski ortam yükleme işlemi sırasında kaybolur **Python ortamları** yerinde güncelleştirme görünmeden önce listesi.
>
> Ancak, el ile bir yorumlayıcı ve dosya sistemi kullanılarak ortamına taşırsanız, Visual Studio yeni konumu bilemezsiniz. Daha fazla bilgi için bkz: [bir yorumlayıcı taşıma](installing-python-interpreters.md#moving-an-interpreter).

## <a name="manually-identifying-an-existing-environment"></a>El ile varolan bir ortama tanımlama

Conda ortamlar dahil standart olmayan bir konumda yüklü bir ortam belirlemek için aşağıdaki adımları kullanın:

1. Seçin **+ özel...**  içinde **Python ortamları** açılır pencere **yapılandırma** sekmesi:

    ![Yeni bir özel ortamı için varsayılan görünüm](media/environments-custom-1.png)

1. Bir ortamda adı **açıklama** alan.

1. Girin veya gözatın (kullanarak **... ***) yorumlayıcı yola **öneki yolu** alan.

1. Visual Studio (örneğin, bir conda ortamı için aşağıda yolu) bu konumda bir Python yorumlayıcısı algılarsa, sağlayan **otomatik algıla** komutu. Seçerek **otomatik algıla* kalan alanları tamamlar. Bu alanlar el ile tamamlayabilirsiniz.

    ![Otomatik Algıla komutu etkinleştirme](media/environments-custom-2.png)

    ![Otomatik Algıla kullandıktan sonra ortamı alanlarının tamamlama](media/environments-custom-3.png)

1. Alanları istediğiniz değerleri içeren bir kez seçin **Uygula** yapılandırmayı kaydetmek için. Ortam gibi diğer Visual Studio içinde artık kullanabilirsiniz.

1. El ile tanımlanan ortam kaldırmanız gerekirse, seçin **kaldırmak** komutunu **yapılandırma** sekmesi. Bu seçenek otomatik olarak algılanır ortamları sağlamaz. Daha fazla bilgi için bkz: [yapılandırma sekmesinden](python-environments-window-tab-reference.md#configure-tab).

## <a name="see-also"></a>Ayrıca bkz.

- [Python yorumlayıcılar yükleme](installing-python-interpreters.md)
- [Proje için yorumlayıcıyı seçme](selecting-a-python-environment-for-a-project.md)
- [Bağımlılıklar için requirements.txt dosyasını kullanma](managing-required-packages-with-requirements-txt.md)
- [Arama yolları](search-paths.md)
- [Python ortamları penceresi başvurusu](python-environments-window-tab-reference.md)