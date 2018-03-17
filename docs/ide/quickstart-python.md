---
title: "Hızlı Başlangıç: İlk Python web uygulamanızı oluşturmak için Visual Studio'yu kullanın. | Microsoft Docs"
description: "Visual Studio'da Falcon framework kullanarak basit bir web uygulaması derlemeler Python kullanarak kısa bir giriş."
ms.custom: 
ms.date: 03/14/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: 
ms.topic: quickstart
dev_langs:
- python
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 2b1880d95fcb4aae04d98171c8ee7df7373aaceb
ms.sourcegitcommit: 236c250bb97abdab99d00c6525d106fc0035d7d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2018
---
# <a name="quickstart-use-visual-studio-to-create-your-first-python-web-app"></a>Hızlı Başlangıç: Kullanım ilk Python web uygulamanızı oluşturmak için Visual Studio

Bu 5-10 dakikalık bir giriş Visual Studio tümleşik geliştirme ortamı (IDE), basit bir Python web uygulaması oluşturun. Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) ücretsiz yüklemek için sayfa. Yükleyicisi'nde seçtiğinizden emin olun **Python geliştirme** iş yükü.

## <a name="create-the-project"></a>Projeyi oluşturma

1. Visual Studio 2017'ni açın.

1. Üst menü çubuğundan seçin **Dosya > Yeni > Proje...** .

1. İçinde **yeni proje** iletişim kutusunda, sol bölmede, genişletin **yüklü**seçeneğini belirleyip **Python**.

1. Orta bölmede seçin **Web projesi**, proje "HelloPython" gibi bir ad verin ve ardından **Tamam**.

    ![Python Web Seçili proje ile yeni proje iletişim kutusu](media/quickstart-python-00-web-project.png)

    İşyeri dışında Python proje şablonları görmüyorsanız, İptal **yeni proje** iletişim kutusuna ve üst menü çubuğundan seçin **Araçlar > alma araçları ve özelliklerinin...**  Visual Studio yükleyicisi açın. Seçin **Python geliştirme** iş yükü, ardından **Değiştir**.

    ![Visual Studio yükleyicisi Python geliştirme iş yükü](../python/media/installation-python-workload.png)

1. Yeni Proje açılır **Çözüm Gezgini** sağ bölmede. Proje, bu noktada, diğer bir dosyaları içerdiği için boştur.

    ![Yeni oluşturulan boş proje gösteren Çözüm Gezgini](media/quickstart-python-01-empty-project.png)

**Soru bir Python uygulaması için Visual Studio Proje oluşturmanın avantajı nedir?**

Yanıt: Python uygulamaları, genellikle yalnızca klasörleri ve dosyaları kullanılarak tanımlanır, ancak uygulamalar daha büyük hale ve belki de JavaScript web uygulamaları için otomatik olarak oluşturulan dosyaları içeren vb. gibi bu yapı karmaşık olabilir. Visual Studio projesi bu karışıklığı yönetmenize yardımcı olur. Proje (bir `.pyproj` dosyası) kaynak ve projenizi ile ilişkili içerik dosyalarını tanımlar, her dosya için yapı bilgileri içerir, kaynak denetimi sistemleriyle tümleştirmeyi bilgilerini korur ve uygulamanızı düzenlemenize yardımcı olur mantıksal bileşenlerine.

## <a name="install-the-falcon-library"></a>Falcon kitaplığını yükle

Web uygulamalarında Python neredeyse her zaman birçok kullanılabilir Python kitaplıklarından birini yönlendirme web isteklerini ve yanıtlarını şekillendirme gibi alt düzey ayrıntıların işlemek için kullanır. Bu amaç için Visual Studio şablonları Bottle, Flask ve Django çerçeveleri kullanarak web uygulamaları için çeşitli sağlar.

Bu hızlı başlangıç ancak, Falcon bir paketi yükleme ve web uygulaması sıfırdan oluşturma işleminde deneyimi için kitaplığını kullanın. (Visual Studio şu anda Falcon özel şablonları dahil değildir.) Kolaylık olması için aşağıdaki adımları Falcon varsayılan genel ortamına yükleyin.

1. Genişletme **Python ortamları** proje için varsayılan ortamı görmek için proje düğümünde.

    ![Varsayılan ortam gösteren Çözüm Gezgini](media/quickstart-python-02-default-environment.png)

1. Ortam sağ tıklatıp **Python paketini yükle...** . Bu komut açar **Python ortamları** penceresinde **paketleri** sekmesi. Arama alanına "falcon" girin ve **"PIP yükle falcon" Pypı**. Sizden yönetici ayrıcalıkları kabul edin ve gözlemlemek **çıkış** ilerleme için Visual Studio penceresinde. (Bir istem genel ortam için paketler klasörü korumalı alanı içinde bulunduğu yükseltme gerçekleşir ister `c:\program files`.)

    ![Falcon kitaplığı yükleme](media/quickstart-python-03-install-package.png)

1. Bir kez yüklendikten sonra ortamında kitaplık görünür **Çözüm Gezgini**, yapabileceğiniz anlamına bunu Python kodu kullanın.

    ![Yüklü falcon kitaplığı](media/quickstart-python-04-package-installed.png)

Falcon hakkında daha fazla bilgi için ziyaret [falconframework.org](https://falconframework.org/).

Belirli bir proje için kitaplıkları yükleneceği kitaplıkları genel ortamında yüklemek yerine, geliştiriciler genellikle "sanal ortam" oluşturduğunuz unutmayın. Visual Studio birçok Python proje şablonlarını içeren bir `requirements.txt` şablonu bağımlı olduğu kitaplıkları listeler dosya. Bu şablonlardan birini proje oluşturma içine kitaplıkların yüklü bir sanal ortamın oluşturulmasını tetikler. Daha fazla bilgi için bkz: [sanal ortamlar kullanarak](../python/selecting-a-python-environment-for-a-project.md#using-virtual-environments).

## <a name="add-a-code-file"></a>Bir kod dosyası ekleme

Artık bir en az bir web uygulaması uygulamak için Python kodu biraz eklemek hazırsınız.

1. ' Nde projeye sağ **Çözüm Gezgini** seçip **Ekle > Yeni öğe...** .

1. Görüntülenen iletişim kutusunda, seçin **boş Python dosyası**, adlandırın `hello.py`seçip **Ekle**. Visual Studio dosya Düzenleyicisi penceresinde otomatik olarak açılır. (Genel olarak, **Ekle > Yeni öğe...**  komut dosyaları farklı türde bir projeye eklemek için bir yoldur harika öğe şablonları genellikle yararlı Demirbaş kod sağlayın.)

1. Aşağıdaki kodu kopyalayın ve yapıştırın `hello.py`:

    ```python
    import falcon

    # In Falcon, define a class for each resource and define on_* methods
    # where * is any standard HTTP methods in lowercase, such as on_get.

    class HelloResource:
        # In this application, the single HelloResource responds to only GET
        # requests, so it has only an on_get method.

        def on_get(self, req, resp):
            resp.status = falcon.HTTP_200  # 200 is the default
            resp.body = "Hello, Python!"

    # Resources are represented by long-lived class instances
    hello = HelloResource()

    # Instruct Falcon to route / and /hello to HelloResource. If you add
    # other resources, use api.add_route to define the desired
    # resource locators for them.
    api = falcon.API()
    api.add_route('/', hello)
    api.add_route('/hello', hello)

    if __name__ == "__main__":
        # Use Python's built-in WSGI reference implementation to run
        # a web server for the application.
        from wsgiref.simple_server import make_server

        # Run the web server on localhost:8080
        print("Starting web app server")
        srv = make_server('localhost', 8080, api)
        srv.serve_forever()
    ```

1. Bu kod yapıştırılan Visual Studio altında dalgalı gösterebilir `falcon` ilk satır hem de altındaki `wsgiref.simple.server` satırında 20. Visual Studio hala Bu modüller için IntelliSense veritabanı oluştururken bu göstergeleri görüntülenir.

Falcon hakkında daha fazla bilgi için bkz: [Falcon Quickstart](https://falcon.readthedocs.io/en/stable/user/quickstart.html) (falcon.readthedocs.io).

## <a name="run-the-application"></a>Uygulamayı çalıştırın

1. Sağ `hello.py` içinde **Çözüm Gezgini** seçip **başlangıç dosyası olarak ayarlamak**. Bu komut, uygulama çalışırken Python içinde başlatmak için kod dosyası tanımlar.

    ![Çözüm Gezgini'nde proje için başlangıç dosyası ayarı](media/quickstart-python-05-set-as-startup-file.png)

1. "Hello Python" projeye sağ **Çözüm Gezgini** seçip **özellikleri**. Ardından **hata ayıklama** sekmesinde ve ayarlama **bağlantı noktası numarası** özelliğine `8080`. Bu adım, Visual Studio bir tarayıcı ile başlatır sağlar `localhost:8080` rastgele bir bağlantı noktası kullanarak yerine.

1. Seçin **hata ayıklama > hata ayıklama olmadan Başlat** (dosyalara değişiklikleri kaydedin ve uygulamayı çalıştırmak için Ctrl + F5).

1. "Başlangıç web uygulaması sunucusu" iletisiyle bir komut penceresi görüntülenir, sonra bir tarayıcı penceresi açın `localhost:8080` iletisini görürseniz burada "Hello, Python!" GET isteğini da komut penceresinde görünür.

    Bir tarayıcı otomatik olarak açılmazsa, tercih ettiğiniz tarayıcıyı başlatın ve gidin `localhost:8080`.)

    Yalnızca Python etkileşimli Kabuk komut penceresinde görürseniz, bu pencereyi kısaca ekranda yanıp sönen varsa, ayarladığınız emin olun veya `hello.py` yukarıdaki 1. adımda başlangıç dosyası olarak.

1. Uygulama durdurmak için komut penceresini kapatın, sonra da tarayıcı penceresini kapatın.

## <a name="next-steps"></a>Sonraki adımlar

İçinde biraz Python ile Visual Studio IDE hakkında öğrendiğinize Bu hızlı başlangıç Tamamlanıyor tebrikler. Visual Studio'da etkileşimli penceresini kullanarak da dahil olmak üzere, veri görselleştirme, hata ayıklama ve Git ile çalışma, Python daha eksiksiz bir öğretici devam etmek için aşağıdaki düğmesini seçin.

> [!div class="nextstepaction"]
> [Öğretici: Visual Studio'da Python ile çalışmaya başlama](../python/tutorial-working-with-python-in-visual-studio-step-01-create-project.md).

- Hakkında bilgi edinin [Python web Visual Studio'da Uygulama Şablonları](../python/python-web-application-project-templates.md)
- Hakkında bilgi edinin [Python hata ayıklama](../python/debugging-python-in-visual-studio.md)
- Daha fazla bilgi edinmek [Visual Studio IDE](../ide/visual-studio-ide.md)
