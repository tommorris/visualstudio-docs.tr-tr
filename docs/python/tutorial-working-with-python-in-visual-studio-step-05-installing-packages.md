---
title: Python Öğreticisi 5. adım, yükleme paketleri ile çalışma
description: 5. adımı çekirdek kılavuzun Visual Studio'da Python ortamı paketleri yönetmek için Visual Studio'nun özellikleri gösteren, Python özelliklerinin.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: fdc37c35d2563780804c38fb6a74e1574cfaa6ad
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45546686"
---
# <a name="step-5-install-packages-in-your-python-environment"></a>5. adım: Python ortamınızda paketleri yükleme

**Önceki adımda: [hata ayıklayıcıda kod çalıştırma](tutorial-working-with-python-in-visual-studio-step-04-debugging.md)**

Python Geliştirici topluluğu kendi projelerine birleştirebilirsiniz yararlı paketleri binlerce hazırlamıştır. Visual Studio için Python ortamlarınızda paketlerini yönetmek için bir kullanıcı Arabirimi sağlar.

1. Seçin **görünümü** > **diğer Windows** > **Python ortamları** menü komutu. **Python ortamları** penceresi açılır bir eşler arası olarak **Çözüm Gezgini** ve farklı ortamlar için gösterilir. Bu liste, yüklediğiniz Visual Studio Yükleyicisi ve ayrı olarak yüklenenler kullanarak her iki ortama içerir. Yeni projeler için kullanılan varsayılan ortam kalın ortamıdır.

  ![Python ortamları penceresi](media/environments-default-view-blue.png)

1. Ortamın **genel bakış** sekmesi, hızlı erişim sağlar bir **etkileşimli** konusu ortamın ortam yükleme klasörü ve yorumlayıcılarını birlikte penceresi. Örneğin, **açık etkileşimli pencere** ve bir **etkileşimli** penceresi, belirli bir ortam için Visual Studio'da görünür.

1. Seçin **paketleri** sekmesine tıkladığınızda ortamda şu anda yüklü olan paketleri listesini görürsünüz.

  ![Bir ortamda yüklü paketler](media/environments-installed-packages-blue.png)

1. Yükleme `matplotlib` arama alanına adı girerek, ardından **pip yükleme**

  ![Matplotlib ortama yükleme](media/environments-add-matplotlib1.png)

1. Bunu yapmak isteyip istemediğiniz sorulduğunda yükseltmesi için onay vermiş olursunuz.

1. Paket yüklendikten sonra görünür **Python ortamları** penceresi. **X** paket sağında da kaldırır.

  ![Ortamda matplotlib yükleme tamamlama](media/environments-add-matplotlib2.png)

  Visual Studio yeni yüklenen paket için IntelliSense veritabanını oluşturuyor belirtmek için ortamı altındaki küçük ilerleme çubuğu görünür. **IntelliSense** sekme ayrıca gösterir daha ayrıntılı bilgiler. Veritabanı işlemi tamamlanana kadar IntelliSense özelliklerini otomatik tamamlama ve sözdizimi denetimi gibi Not Düzenleyici o paket için etkin olmayacaktır.

  Unutmayın **Visual Studio 2017 sürüm 15.6** daha sonra IntelliSense ile çalışmak için farklı ve daha hızlı bir yöntemi kullanır ve açık belirlememişse bu bağlamda bir ileti görüntüler **IntelliSense** sekmesi.

1. Kullanarak yeni bir proje oluşturun **dosya** > **yeni** > **proje**u seçerek **Python uygulaması** şablonu. Görünen kod dosyasında, yalnızca bu kez grafik olarak çizilen bir cosine wave gibi önceki öğretici adımlarını oluşturan aşağıdaki kodu yapıştırın:

    ```python
    from math import radians
    import numpy as np     # installed with matplotlib
    import matplotlib.pyplot as plt

    def main():
        x = np.arange(0, radians(1800), radians(12))
        plt.plot(x, np.cos(x), 'b')
        plt.show()

    main()
    ```

1. Programı çalıştırın (**F5**) veya hata ayıklayıcı olmadan (**Ctrl**+**F5**) çıktıyı görmek için:

  ![Matplotlib örnek çıktısı](media/environments-add-matplotlib3.png)

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [Git ile çalışma](tutorial-working-with-python-in-visual-studio-step-06-working-with-git.md)

## <a name="go-deeper"></a>Daha ayrıntılı şekilde inceleyin

- [Python ortamları](managing-python-environments-in-visual-studio.md)
