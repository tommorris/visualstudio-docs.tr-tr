---
title: "Hızlı Başlangıç - Cookiecutter Visual Studio kullanarak bir Python projesi oluşturun | Microsoft Docs"
description: "Visual Studio'da bir Cookiecutter şablonu kullanarak Python hızlı şekilde kullanmaya başlayın."
ms.custom: 
ms.date: 09/22/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: quickstart
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 4b9b7a51436eeeb67634714216f9a583de679a07
ms.sourcegitcommit: c0a2385a16cc4f47d2e1ff23d35c4da40f5605e0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
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
