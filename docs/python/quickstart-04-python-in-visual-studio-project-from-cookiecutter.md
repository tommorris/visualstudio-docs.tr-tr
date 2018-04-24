---
title: Hızlı Başlangıç - Cookiecutter kullanarak bir Python projesi oluşturma
description: Bu Hızlı Başlangıç için Python Cookiecutter şablonu kullanarak bir Visual Studio projesi oluşturun.
ms.date: 09/22/2017
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: quickstart
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: c8e4ec1691dc1826fa6772d6d69723659245cece
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="quickstart-create-a-project-from-a-cookiecutter-template"></a>Hızlı Başlangıç: Proje Cookiecutter Şablondan Oluştur

Seçtiğiniz sonra [Python desteği Visual Studio 2017 yüklü](installing-python-support-in-visual-studio.md), GitHub için yayımlanan birçok bir Cookiecutter şablondan yeni bir proje oluşturmak kolaydır. [Cookiecutter](https://cookiecutter.readthedocs.io/en/latest/) şablonları bulmak, şablon seçenekleri giriş ve projeler ve dosyaları oluşturmak için bir grafik kullanıcı arabirimi sağlar. Visual Studio 2017 ile eklemiştir ve Visual Studio'nun önceki sürümleri ayrı olarak yüklenebilir.

1. Bu Hızlı Başlangıç için önce burada gösterilen Cookiecutter şablonu için gereken Python paketlerini içerir Anaconda3 Python dağıtımı yükleyin. Visual Studio yükleyicisi, belirleyin **Değiştir**, seçeneklerini genişletin **Python geliştirme** sağ tarafında ve select "Anaconda3" (32 bit veya 64 bit). Yükleme Internet hızınıza bağlı olarak biraz zaman alabilir ancak bu gerekli paketleri yüklemek için en basit yolu olduğunu unutmayın.

1. Visual Studio'yu başlatın.

1. Seçin **Dosya > Yeni > Cookiecutter gelen...** . Bu komut, burada şablonları göz atabilirsiniz Visual Studio'da bir pencere açılır. 

    ![Cookiecutter şablondan yeni proje](media/projects-from-cookiecutter1.png)

1. "Microsoft/python-sklearn-sınıflandırıcı-cookiecutter" şablonu seçili sonra seçin **sonraki**. (İşlemi ilk kez Cookiecutter kullandığınızda birkaç dakika sürebilir.)

1. Sonraki adımda, yeni projede için bir konum ayarlamak **oluşturmak için** alan sonra select **oluşturma**.

    ![İkinci adım Cookiecutter kullanarak, proje özelliklerini ayarlama](media/projects-from-cookiecutter2.png)

1. İşlem tamamlandığında, "Dosyaları başarıyla oluşturuldu." iletisini görürsünüz Komutu seçin **Çözüm Gezgini'nde açık** projeyi açın.

1. CTRL + F5 tuşuna basın veya seçin **hata ayıklama > hata ayıklama olmadan Başlat** programı çalıştırmak için. 

    ![Python sklearn sınıflandırıcı cookiecutter şablon proje çıktısı](media/projects-from-cookiecutter4.png)

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Öğretici: Visual Studio'da Python ile çalışma](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Cookiecutter uzantısını kullanma](using-python-cookiecutter-templates.md)
- [El ile varolan bir Python yorumlayıcısı tanımlayan](managing-python-environments-in-visual-studio.md#manually-identifying-an-existing-environment).
- [Python desteği Visual Studio 2015 ve daha önce yükleme](installing-python-support-in-visual-studio.md).
- [Konumları yüklemek](installing-python-support-in-visual-studio.md#install-locations).
