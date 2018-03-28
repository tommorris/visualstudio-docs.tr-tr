---
title: Hızlı Başlangıç - bir şablon kullanarak Visual Studio'da Python projesi oluşturun | Microsoft Docs
description: Python için temel bir Flask uygulama yerleşik şablonu kullanarak bir Visual Studio projesi oluşturarak hızlı şekilde kullanmaya başlayın.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: ''
ms.topic: quickstart
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 41b677dc41202012ba09908edf3110961139f416
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
---
# <a name="quickstart-create-a-python-project-from-a-template-in-visual-studio"></a>Hızlı Başlangıç: Visual Studio'da bir şablondan bir Python projesi oluşturma

Seçtiğiniz sonra [Python desteği Visual Studio 2017 yüklü](installing-python-support-in-visual-studio.md), şablonları, çeşitli kullanarak yeni bir Python proje oluşturmak kolaydır. Bu hızlı başlangıç bir şablon kullanarak basit bir Flask uygulaması oluşturursunuz. Elde edilen proje el ile oluşturduğunuz proje benzer [hızlı başlangıç - Flask ile bir web uygulaması oluşturma](../ide/quickstart-python.md).

1. Visual Studio 2017 başlatın.

1. Üst menü çubuğundan seçin **Dosya > Yeni > Proje...** , ardından **yeni proje** "boş flask" iletişim Ara Orta listesinde "Boş Flask Web projesi" şablonunu seçin, proje bir ad verin ve seçin **Tamam**:

    ![Boş Flask Web projesi şablonu ile yeni bir proje oluşturma](media/quickstart-python-06-blank-flask-template.png)

1. "Bu proje dış paketler gerekir." bildiren bir iletişim kutusu ister Visual Studio Şablonun içerdiği için bu iletişim kutusu görünür bir `requirements.txt` dosya Flask üzerinde bir bağımlılık belirtme. Visual Studio paketleri otomatik olarak yükleyebilir ve bunları yükleme seçeneğini verir *sanal ortam*. Sanal bir ortam kullanarak önerilir bir genel ortamına, bu nedenle select yükleme üzerinden **sanal bir ortama yükleme** devam etmek için.

    ![Flask sanal bir ortama yükleme](media/quickstart-python-07-install-into-virtual-environment.png)

1. Visual Studio görüntüler **sanal ortam Ekle** iletişim. Varsayılanı kabul etmek ve seçin **oluşturma**, tüm yükseltme istekleri için onay.

    > [!Tip]
    > Bir proje başladığınızda, çoğu Visual Studio şablonları yapmak için davet gibi yüksek oranda hemen, sanal bir ortam oluşturmak için önerilir. Kitaplıkları ekleyip gibi sanal ortamlar, projenizin tam gereksinimlerini zamanla güncelleştirin. Daha sonra kolayca oluşturabileceğiniz bir `requirements.txt` bu bağımlılıkların (zaman kullanarak denetim kaynağı gibi) diğer geliştirme bilgisayarlar üzerinde yeniden yüklemek için kullandığınız dosya ve Proje üretim sunucusuna dağıtırken. Sanal ortamları ve bunların avantajları hakkında daha fazla bilgi için bkz: [sanal ortamlar kullanarak](../python/selecting-a-python-environment-for-a-project.md#using-virtual-environments) ve [requirements.txt ile gerekli paketleri yönetme](../python/managing-required-packages-with-requirements-txt.md).

1. Visual Studio bu ortam oluşturduktan sonra konum **Çözüm Gezgini** olduğunu görmek için bir `app.py` ile birlikte dosya `requirements.txt`. Açık `app.py` şablon kodu gibi içinde sağlamıştır görmek için [hızlı başlangıç - Flask ile bir web uygulaması oluşturma](../ide/quickstart-python.md), iki bölümleri eklendi.

    İlk satırı olan `wsgi_app = app.wsgi_app` , yararlı olabilir bir uygulama bir web ana bilgisayara dağıtırken.

    İkinci ana bilgisayarı ve bağlantı noktası üzerinden bunları kodlamak yerine ortam değişkenleri ayarlamanıza olanak veren başlangıç kodudur. Bu kod, kodunu değiştirmeden geliştirme ve üretim makinelerde yapılandırma kolayca denetlemenizi sağlar:

    ```python
    if __name__ == '__main__':
        import os
        HOST = os.environ.get('SERVER_HOST', 'localhost')
        try:
            PORT = int(os.environ.get('SERVER_PORT', '5555'))
        except ValueError:
            PORT = 5555
        app.run(HOST, PORT)
    ```

1. Seçin **hata ayıklama > hata ayıklama olmadan Başlat** uygulamayı çalıştırın ve bir tarayıcı penceresinde açmak için `localhost:5555`.

**Soru: Visual Studio hangi bir Python şablonları sunar?**

**Yanıt**: yüklü Python yüküyle Visual Studio Proje şablonları olanları için de dahil olmak üzere çeşitli sağlar [Flask, Bottle ve Django web çerçeveleri](../python/python-web-application-project-templates.md), Azure bulut Hizmetleri, farklı makine öğrenme senaryolar ve Python uygulaması içeren varolan bir klasör yapısından bir proje oluşturmak için bir şablon bile. Bunlar üzerinden erişim **Dosya > Yeni > Proje...**  seçerek iletişim kutusu **Python** dil düğümünü ve alt düğümlerini.

Visual Studio ayrıca dosya çeşitli sağlar veya *öğe şablonlarını* Python sınıfı, bir Python paket, Python birim testi, web.config dosyaları ve daha hızlı bir şekilde oluşturmak için. Açık bir Python projeniz varsa, öğe şablonları üzerinden erişim **Proje > Yeni Öğe Ekle...**  menü komutu.

Şablonları kullanarak önemli zamandan tasarruf ne zaman bir proje başlangıç veya bir dosya oluşturmak ve aynı zamanda farklı uygulama türleri hakkında bilgi edinin ve yapıları kod için kullanışlı bir yoludur. Bunlar sunar ile tanımak için çeşitli şablonlardan projeler ve öğeler oluşturmak için birkaç dakika sürebilir yararlıdır.

**Soru: Ayrıca Cookiecutter şablonları kullanabilir miyim?**

**Yanıt**: Evet! Aslında, Visual Studio aracılığıyla hakkında bilgi alabilirsiniz Cookiecutter doğrudan tümleştirmesi sağlayan [hızlı başlangıç: Cookiecutter şablondan bir proje oluşturma](../python/quickstart-04-python-in-visual-studio-project-from-cookiecutter.md).

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Öğretici: Visual Studio'da Python ile çalışma](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

## <a name="see-also"></a>Ayrıca bkz.

- [El ile varolan bir Python yorumlayıcısı tanımlayan](managing-python-environments-in-visual-studio.md#manually-identifying-an-existing-environment).
- [Python desteği Visual Studio 2015 ve daha önce yükleme](installing-python-support-in-visual-studio.md).
- [Konumları yüklemek](installing-python-support-in-visual-studio.md#install-locations).
