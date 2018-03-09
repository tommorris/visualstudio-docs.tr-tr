---
title: "Visual Studio, 5. adım paketlerini yükleme Python ile çalışma | Microsoft Docs"
description: "Python paket Python ortamında yönetmek için Visual Studio'nun özellikleri gösteren Visual Studio içinde çalışmak için 5. adım çekirdek öğreticinin."
ms.custom: 
ms.date: 03/05/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 86068e56013bc62adad59e403c1e4a16c2cdfee9
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="step-5-installing-packages-in-your-python-environment"></a>5. adım: Python ortamınızda paketleri yükleniyor

**Önceki adımda: [Hata Ayıklayıcısı'ndaki kodu çalıştırma](tutorial-working-with-python-in-visual-studio-step-04-debugging.md)**

Python Geliştirici topluluğu kendi projelere dahil edebilirsiniz yararlı paketleri binlerce üretilen. Visual Studio, Python ortamlarda paketlerini yönetmek için bir kullanıcı Arabirimi sağlar.

1. Seçin **Görünüm > Diğer Pencereler > Python ortamları** menü komutu. **Python ortamları** penceresi Çözüm Gezgini eşe olarak açılır ve kullanılabilir farklı ortamlar için gösterir. Liste, Visual Studio Yükleyicisi ve ayrı olarak yüklediyseniz kullanılarak yüklenen her iki ortama içerir. Kalın ortamında yeni projeler için kullanılan varsayılan ortamıdır.

  ![Python ortamları penceresi](media/environments-default-view-blue.png)

1. Ortam **genel bakış** sekmesi, ortam yükleme klasörü ve yorumlayıcılar yanı sıra bu ortamda etkileşimli bir pencere için hızlı erişim sağlar. Örneğin, seçin **açık etkileşimli pencere** ve Visual Studio'da, belirli bir ortamın etkileşimli bir pencere görüntülenir.

1. Seçin **paketleri** sekmesine tıkladığınızda ortamda yüklü olan paketleri listesini görürsünüz.

  ![Bir ortamda yüklü olan paketleri](media/environments-installed-packages-blue.png)

1. Yükleme `matplotlib` arama alanına adı girerek, ardından seçin `pip install`

  ![Matplotlib ortama yükleme](media/environments-add-matplotlib1.png)

1. Bunu yapmak isteyip istemediğiniz sorulduğunda yüksekliğe olursunuz.

1. Paket yüklendikten sonra Python ortamları penceresinde görüntülenir. **X** paket sağındaki da kaldırır.

  ![Ortamında matplotlib yükleme tamamlama](media/environments-add-matplotlib2.png)

  Visual Studio yeni yüklenmiş paket için IntelliSense veritabanını oluşturuyor ortamı altında küçük ilerleme çubuğu gösterir. **IntelliSense** sekmesi ayrıca gösterir daha ayrıntılı bilgi. Veritabanı işlemi tamamlanana kadar IntelliSense özellikleri otomatik tamamlama ve sözdizimi denetimi gibi Not düzenleyicisinde bu paket için etkin olmayacaktır.

  Unutmayın **Visual Studio 2017 sürüm 15,6** daha sonra IntelliSense ile çalışmak için farklı ve daha hızlı bir yöntem kullanır ve bunu belirten üzerinde bir ileti görüntüler **IntelliSense** sekmesi.

1. İle yeni bir proje oluşturun **Dosya > Yeni > Proje**, "Python uygulama" şablonu seçme. Görüntülenen kod dosyasında kosinüsünü wave gibi önceki öğretici adımlar, yalnızca grafik olarak çizilen bu saat oluşturur aşağıdaki kodu yapıştırın:

    ```python
    import numpy as np     # installed with matplotlib
    import matplotlib.pyplot as plt
    from math import radians

    def main():
        x = np.arange(0, radians(1800), radians(12))
        plt.plot(x, np.cos(x), 'b')
        plt.show()

    main()
    ```

1. (F5) programla çalıştırma veya çıkış görmek için hata ayıklayıcı (Ctrl + F5) olmadan:

  ![Matplotlib örnek çıkış](media/environments-add-matplotlib3.png)

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Git ile çalışma](tutorial-working-with-python-in-visual-studio-step-06-working-with-git.md)

### <a name="going-deeper"></a>Daha derin gitme

- [Python ortamları](managing-python-environments-in-visual-studio.md)
