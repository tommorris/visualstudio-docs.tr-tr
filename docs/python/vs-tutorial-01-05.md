---
title: "Visual Studio'da Python ile çalışma, 5. adım | Microsoft Docs"
ms.custom: 
ms.date: 09/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: get-started-article
ms.assetid: 69e51c46-9a10-4d6f-9f74-2d1385beb1ac
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 30f89023d09ab90cae2698de976eaef44165b0fb
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="step-5-installing-packages-in-your-python-environment"></a>5. adım: Python ortamınızda paketleri yükleniyor

**Önceki adımda: [Hata Ayıklayıcısı'ndaki kodu çalıştırma](vs-tutorial-01-04.md)**

Python Geliştirici topluluğu kendi projelere dahil edebilirsiniz yararlı paketleri binlerce üretilen. Visual Studio, Python ortamlarda paketlerini yönetmek için bir kullanıcı Arabirimi sağlar.

1. Seçin **Görünüm > Diğer Pencereler > Python ortamları** menü komutu. **Python ortamları** penceresi Çözüm Gezgini eşe olarak açılır ve kullanılabilir farklı ortamlar için gösterir. Liste, Visual Studio Yükleyicisi ve ayrı olarak yüklediyseniz kullanılarak yüklenen her iki ortama içerir. Kalın ortamında yeni projeler için kullanılan varsayılan ortamıdır.

  ![Python ortamları penceresi](media/environments-default-view-blue.png)

1. Ortam **genel bakış** sekmesi, ortam yükleme klasörü ve yorumlayıcılar yanı sıra bu ortamda etkileşimli bir pencere için hızlı erişim sağlar. Örneğin, seçin **açık etkileşimli pencere** ve Visual Studio'da, belirli bir ortamın etkileşimli bir pencere görüntülenir.

1. Seçin **paketleri** sekmesine tıkladığınızda ortamda yüklü olan paketleri listesini görürsünüz.

  ![Bir ortamda yüklü olan paketleri](media/environments-installed-packages-blue.png)

1. Yükleme `matplotlib` arama alanına adı girerek, ardından seçin`pip install`

  ![Matplotlib ortama yükleme](media/environments-add-matplotlib1.png)

1. Bunu yapmak isteyip istemediğiniz sorulduğunda yüksekliğe olursunuz.
 
1. Paket yüklendikten sonra Python ortamları penceresinde görüntülenir. **X** paket sağındaki da kaldırır. 

  ![Ortamında matplotlib yükleme tamamlama](media/environments-add-matplotlib2.png)

  Visual Studio yeni yüklenmiş paket için IntelliSense veritabanını oluşturuyor ortamı altında küçük ilerleme çubuğu gösterir. **IntelliSense** sekmesi ayrıca gösterir daha ayrıntılı bilgi. Veritabanı işlemi tamamlanana kadar IntelliSense özellikleri otomatik tamamlama ve sözdizimi denetimi gibi Not düzenleyicisinde bu paket için etkin olmayacaktır.

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


## <a name="next-steps"></a>Sonraki Adımlar

> [!div class="nextstepaction"]
> [Git ile çalışma](vs-tutorial-01-06.md)

### <a name="going-deeper"></a>Daha derin gitme
- [Python ortamları](python-environments.md)
