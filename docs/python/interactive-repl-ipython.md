---
title: Visual Studio'da IPython REPL | Microsoft Docs
ms.custom: 
ms.date: 07/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: d33765a2c70f6c58759e2722b04d770b6f8822a6
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2018
---
# <a name="using-ipython-in-the-interactive-window"></a>Etkileşimli pencerede IPython kullanma

Visual Studio etkileşimli penceresini IPython modunda etkileşimli paralel bilgi işlem özellikleri olan bir Gelişmiş henüz kullanıcı dostu etkileşimli geliştirme ortamıdır. Bu konuda tüm normal, Visual Studio etkileşimli penceresinde IPython kullanarak kılavuzluk [etkileşimli pencere](interactive-repl.md) özellikleri de kullanılabilir duruma gelir.

Bu kılavuzda, olmalıdır [Anaconda](https://www.continuum.io) IPython ve gerekli kitaplıkları içeren yüklü ortamı.

> [!Note]
> IronPython IPython, siz bunu etkileşimli seçenekleri formdaki seçebilirsiniz olgusuna karşın desteklemez. Daha fazla bilgi için bkz: [özellik isteği](https://github.com/Microsoft/PTVS/issues/84).

1. Açık Visual Studio, Python ortamları penceresine anahtarı (**Görünüm > Diğer Pencereler > Python ortamları**) ve IPython başlatıldığında görünen Python ortamı seçin.

1. Bakmak **paketleri** (veya **PIP**) sekmesini ve emin `IPython` ve `matplotlib` listelenir. Yoksa, bunları burada yükleyin.

1. Seçin **genel bakış** sekmesinde ve seçin **kullanım IPython etkileşimli mod.** (Visual Studio 2015'te seçin **etkileşimli seçenekleri yapılandırın** açmak için **seçenekleri** iletişim kutusunda, ardından **etkileşimli mod** IPython ve seçin **Tamam** ).

1. Seçin **açık etkileşimli pencere** IPython modunda etkileşimli penceresi getirmek için. Etkileşimli mod yalnızca değiştirdiyseniz penceresi sıfırlamanız gerekebilir; yalnızca Enter tuşuna basın gerekebilir bir >>> istemi belirir.

    ![IPython modunda etkileşimli penceresi](media/ipython-repl-03.png)

1. Aşağıdaki kodu girin:

  ```python
  x = linspace(0, 5, 10)
  y = x ** 2
  plot(x, y, 'r', x, x ** 3, 'g', x, x ** 4, 'b')
  ```

1. Son satırı girdikten sonra (hangi sağ alt köşesinde üzerinde sürükleyerek boyutlandırabilirsiniz) bir satır içi grafik görmelisiniz isterseniz.

    ![Satır içi grafik etkileşimli penceresinde](media/ipython-repl-04.png)

1. Kod Düzenleyicisi'nde yazabilirsiniz REPL içinde yazmak yerine seçin, sağ tıklatın ve seçin **çok etkileşimli Gönder** komutu (veya Ctrl-Enter tuşuna basın). Aşağıdaki kod düzenleyicisinde Ctrl-A, ardından etkileşimli penceresine gönderen ile seçerek yeni bir dosyaya yapıştırmayı deneyin. (Visual Studio Ara ya da kısmi grafikleri vermiş önlemek için bir birim olarak kod gönderir unutmayın. Ayrıca, seçili için farklı bir ortam açık bir Python projeniz yoksa, Visual Studio ne olursa olsun ortamı varsayılan olarak seçilen için etkileşimli bir pencere açılır unutmayın **Python ortamları** penceresi.)

    ```python
    from mpl_toolkits.mplot3d import Axes3D
    import matplotlib.pyplot as plt
    import numpy as np
    fig = plt.figure()
    ax = fig.add_subplot(111, projection='3d')
    for c, z in zip(['r', 'g', 'b', 'y'], [30, 20, 10, 0]):
        xs = np.arange(20)
        ys = np.random.rand(20)
        # You can provide either a single color or an array. To demonstrate this,
        # the first bar of each set will be colored cyan.
        cs = [c] * len(xs) 
        cs[0] = 'c' 
        ax.bar(xs, ys, zs=z, zdir='y', color=cs, alpha=0.8)

    ax.set_xlabel('X') 
    ax.set_ylabel('Y') 
    ax.set_zlabel('Z') 
    plt.show()
    ```

    ![Kod Düzenleyicisi'nden etkileşimli penceresine gönderme](media/ipython-repl-05.png)

1. Etkileşimli penceresinin dışında grafikleri görmek için bunun yerine kodu çalıştırmak **hata ayıklama > hata ayıklama olmadan Başlat** komutu.

IPython değişkeni değiştirme sistem Kabuk kaçış gibi birçok diğer yararlı özellikleri yakalama çıktı, vb. vardır. Başvurmak [IPython belgelerine](http://ipython.org/documentation.html) daha fazla bilgi için.

## <a name="related-topics"></a>İlgili konular

- Jupyter kolayca ve yükleme olmadan kullanmak için ücretsiz olarak deneyin [Azure not defterlerini barındırılan hizmeti](https://notebooks.azure.com/) tutun ve defterlerinizi başkalarıyla paylaşmanızı sağlayan.

- Jupyter (önceki adıyla IPython da bilinir), kendi Windows veya Linux sanal makineye Azure üzerinde de çalıştırabilirsiniz. Ayrıntılar için bkz [bir Azure VM Jupyter yükleme ve Jupyter not defteri Azure üzerinde çalışan oluşturuluyor.](/azure/virtual-machines/virtual-machines-linux-jupyter-notebook).
