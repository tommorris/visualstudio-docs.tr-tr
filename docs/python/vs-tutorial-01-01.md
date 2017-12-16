---
title: "Visual Studio'da Python ile çalışma, 1. adım | Microsoft Docs"
ms.custom: 
ms.date: 09/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: get-started-article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 07a0b5dbcbb32f7ae8bb7fb4045b55d6aa954f37
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/14/2017
---
# <a name="working-with-python-in-visual-studio"></a>Visual Studio'da Python ile çalışma

Python güvenilir, esnek, kolay öğrenmek için tüm işletim sistemlerinde kullanımına yönelik ücretsiz ve sağlam Geliştirici topluluğu ve pek çok ücretsiz kitaplıkları tarafından desteklenen popüler bir programlama dilidir. Dil geliştirme, web uygulamaları, web Hizmetleri, Masaüstü uygulamaları, komut dosyası ve bilimsel hesaplama dahil olmak üzere tüm yolla destekler ve birçok üniversiteler, bilimcilerine, rasgele geliştiriciler ve profesyonel geliştiricilere benzer tarafından kullanılır.

Visual Studio Python için birinci sınıf dil desteği sağlar. Bu öğretici, aşağıdaki adımlarda size yol gösterir:

- [Adım 0: yükleme](vs-tutorial-01-00.md)
- [1. adım: Python proje (Bu konuda) oluşturma](#step-1-create-a-new-python-project)
- [2. adım: Yazma ve iş için Visual Studio IntelliSense görmek için kodu çalıştırma](vs-tutorial-01-02.md)
- [3. adım: etkileşimli REPL penceresinde daha fazla kod oluşturma](vs-tutorial-01-03.md)
- [4. adım: Visual Studio Hata Ayıklayıcısı'ndaki tamamlanmış programı çalıştırın](vs-tutorial-01-04.md)
- [5. adım: paketleri yükleme ve Python ortamları yönetme](vs-tutorial-01-05.md)
- [6. adım: Git ile çalışma](vs-tutorial-01-06.md)

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio 2017 yüklü Python iş yükü ile. Bkz: [adım 0](vs-tutorial-01-00.md) yönergeler için.

## <a name="step-1-create-a-new-python-project"></a>1. adım: yeni bir Python projesi oluşturma

A *proje* Visual Studio kaynak kod, kaynaklar, yapılandırmaları vb. dahil olmak üzere tek bir uygulama oluşturmak için bir araya gelmesi tüm dosyaları nasıl yönetir. Bir proje testini biçimlendirir ve projenin tüm dosyaların yanı sıra birden çok proje arasında paylaşılan dış kaynaklar arasındaki ilişkiyi korur. Bu nedenle, projeyi uygulamanızın harcamadan genişletin ve yalnızca bir projenin ilişkileri geçici klasörlerde yönetme komutlar daha çok daha kolay büyüme, metin dosyaları ve hatta kendi fikrinizi sağlar.

Bu öğreticide tek ve boş kod dosyasını içeren basit bir proje ile başlar.

1. Visual Studio'da seçin **Dosya > Yeni > Proje** (Ctrl + Shift + N), hangi getirir **yeni proje** iletişim. Burada şablonları Gözat farklı diller arasında sonra projeniz için bir tane seçin ve Visual Studio dosyaların nerede yerleştirir belirtin.

1. Python şablonları görüntülemek için seçin **yüklü > Python** sol veya "Python" için arama. Arama'yı kullanarak dilleri ağaç konumunda anımsayamadığınızda, bir şablon bulmak için harika bir yoludur.

    ![Gösterilen Python projeleri ile yeni proje iletişim kutusu](media/vs-getting-started-python-01-new-project.png)

    Python desteği Visual Studio Proje şablonları, Bottle, Flask ve Django çerçeveleri kullanarak web uygulamaları dahil olmak üzere çeşitli nasıl içerir dikkat edin. Bu kılavuzda amaçları doğrultusunda, Bununla birlikte, boş bir proje ile başlayalım.

1. Seçin **Python uygulama** şablonu, proje için bir ad belirtin ve seçin **Tamam**. 

1. Birkaç dakika sonra Visual Studio Proje yapısında gösterir **Çözüm Gezgini** penceresi (1). Varsayılan kod dosyası (2) düzenleyicisinde açın. Özellikler penceresi (3), Çözüm Gezgini'nde tam konumuna diskteki dahil olmak üzere, seçili öğe için ek bilgileri görüntülemek için de görünür.

    ![Python proje ile Çözüm Gezgini](media/vs-getting-started-python-02-windows.png)

1. Dosya ve klasörleri projenizde burada Gözat olduğu Solution Explorer ile tanımak için birkaç dakika alın.

    ![Çeşitli özelliklerini göstermek için genişletilmiş Çözüm Gezgini](media/vs-getting-started-python-03-solution-explorer.png)

    (1) kalın olarak vurgulanan yeni proje iletişim kutusuna verdiğiniz adla kullanarak projenize ' dir. Diskte, bu proje tarafından temsil edilen bir `.pyproj` proje klasörünüzdeki dosya.

    (2) üstünde düzeyinde bir *çözüm*, varsayılan olarak projenizi aynı ada sahip. Tarafından temsil edilen bir çözüm bir `.sln` dosya diskte, bir veya daha fazla ilgili projeleri için bir kapsayıcıdır. Örneğin, Python uygulamanız için bir C++ uzantısı yazarsanız, bu C++ projesi içinde aynı çözüm bulunması. Çözüm ayrıca ayrılmış sınama programlar projelerde yanı sıra bir web hizmeti için bir proje içermiyor olabilir. 

    (3) altında projenizin kaynak dosyalarına bakın, bu tek bir durumda `.py` dosya. Bir dosya seçmek özelliklerini Özellikler penceresinde görüntüler. Bir dosyayı çift kararlaştırdığı bir yolla bu dosya için uygun olan açar.

    (4) de altında projedir **Python ortamları** düğümü. Genişletilmiş olduğunda kullanılabilen kullanılabilir Python yorumlayıcılar bakın. Bu ortamına (5) yüklü kitaplıkları görmek için bir yorumlayıcı düğümünü genişletin.

    Bir düğüm veya uygulanabilir komutların menüsüne erişmek için Çözüm Gezgininde öğenin sağ tıklayın. Örneğin, **yeniden adlandırma** komutu bir düğüm veya proje ve çözüm dahil olmak üzere öğe adını değiştirmenize olanak verir.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Yazma ve kodu çalıştırma](vs-tutorial-01-02.md)

## <a name="going-deeper"></a>Daha derin gitme

- [Visual Studio'da Python projeleri](python-projects.md).
- [Python.org Python dil hakkında bilgi edinin](https://www.python.org)
- [Yeni başlayanlar için Python](https://www.python.org/about/gettingstarted/) (python.org)
- [Microsoft Virtual Academy boş Python kursları](https://mva.microsoft.com/search/SearchResults.aspx#!q=python)
- [Microsoft sanal Akademi üst Python sorular](https://aka.ms/mva-top-python-questions)
