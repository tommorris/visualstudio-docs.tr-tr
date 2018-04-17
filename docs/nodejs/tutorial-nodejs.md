---
title: Node.js ve hızlı uygulama - Visual Studio oluşturma | Microsoft Docs
description: Bu öğreticide, Visual Studio Node.js ve hızlı bir uygulama oluşturma
ms.custom: ''
ms.date: 03/13/2018
ms.technology: vs-nodejs
ms.topic: tutorial
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: douge
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 47bf06fabba9197029831382b6ad6e9068e7829c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="tutorial-create-a-nodejs-and-express-app-in-visual-studio"></a>Öğretici: Visual Studio'da bir Node.js ve hızlı uygulama oluşturma
Node.js ve Express kullanarak Visual Studio geliştirme için bu öğreticideki basit bir Node.js web uygulaması oluşturma, bazı kodlar ekleyin, IDE özelliklerinden bazıları keşfedin ve uygulamayı çalıştırın. Visual Studio henüz yüklemediyseniz, ücretsiz yükleme [burada](http://www.visualstudio.com).

Bu öğreticide, bilgi nasıl yapılır:
> [!div class="checklist"]
> * Node.js projesi oluşturma
> * Bazı kodlar ekleyin
> * IntelliSense kullanma
> * Uygulama Çalıştırma
> * Bir kesme noktası isabet

## <a name="prerequisites"></a>Önkoşullar

* Visual Studio yüklüyse ve Node.js geliştirme iş yükü olması gerekir.

    Visual Studio henüz yüklemediyseniz, ücretsiz yükleme [burada](http://www.visualstudio.com).

    İş yükü yüklenir ancak tıklatın Visual Studio zaten gerektiğinde **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu. Visual Studio yükleyicisi başlatır. Seçin **Node.js geliştirme** iş yükü, ardından **Değiştir**.

* Node.js çalışma zamanı yüklü olması gerekir.

    LTS sürümünden yüklü yoksa, yükleme [Node.js](https://nodejs.org/en/download/) Web sitesi. Genel olarak, Visual Studio yüklenmiş Node.js çalışma zamanı otomatik olarak algılar. Yüklü bir çalışma zamanı algılamazsa yüklü çalışma zamanı özellikleri sayfasında başvurmak için projenizi yapılandırabilirsiniz (bir proje oluşturduktan sonra proje düğümüne sağ tıklayın ve seçin **özellikleri**).

    Bu öğretici 8.10.0 Node.js ile test edilmiştir.

## <a name="create-a-project"></a>Proje oluşturma
İlk olarak, bir Node.js web uygulaması projesi oluşturacaksınız.

1. Visual Studio 2017'ni açın.

1. Üst menü çubuğundan seçin **dosya** > **yeni** > **proje...** .

1. İçinde **yeni proje** iletişim kutusunda, sol bölmede, genişletin **JavaScript**ve ardından **Node.js**. Orta bölmede seçin **temel Azure Node.js Express 4 uygulama**ve ardından **Tamam**.

     Görmüyorsanız, **temel Azure Node.js Express 4 uygulama** proje şablonu, yüklemelisiniz **Node.js geliştirme** iş yükü ilk.

    Visual Studio yeni çözüm oluşturur ve projenizin açar. *App.js* proje dosyası (sol bölme) Düzenleyicisi'nde açar.

    - Kalın olarak vurgulanmış olan, vermiş adını kullanarak projenize **yeni proje** iletişim kutusu. Dosya sisteminde, bu proje tarafından temsil edilen bir *.njsproj* proje klasörünüzdeki dosya. Özellikler ve projeye sağ tıklayıp seçerek projeyle ilişkili ortam değişkenleri ayarlayabilirsiniz **özellikleri**. Proje dosyası özel Node.js projesi kaynağına değişiklik değil çünkü gidiş diğer geliştirme araçları ile yapabilirsiniz.

    - En üst düzeyinde varsayılan olarak, projenizin aynı ada sahip bir, çözümüdür. Tarafından temsil edilen bir çözüm bir *.sln* dosya diskte, bir veya daha fazla ilgili projeleri için bir kapsayıcıdır.

    - Npm düğüm herhangi bir yüklü npm paket gösterir. Arayın ve iletişim kutusunu kullanarak npm paket yüklemek için npm düğümünü sağ tıklayabilirsiniz.

    - Proje dosyaları gibi *app.js* proje düğümünün altında görünür. *app.js* proje başlangıç dosyasıdır.

1. Açık **npm** düğümü ve tüm gerekli npm paketler mevcut olduğundan emin olun.

    Herhangi bir (ünlem işareti simgesi) yoksa, sağ tıklayarak **npm** düğümü seçin **npm paket yükleme eksik**.

## <a name="add-some-code"></a>Bazı kodlar ekleyin

1. Çözüm Gezgini'nde (sağ bölme), görünümleri klasörünü açın, sonra açın *index.pug*.

1. İçeriği aşağıdaki biçimlendirme ile değiştirin.

    ```js
    extends layout

    block content
      h1= title
      p Welcome to #{title}
      script.
        var f1 = function() { document.getElementById('myImage').src='#{data.item1}' }
      script.
        var f2 = function() { document.getElementById('myImage').src='#{data.item2}' }
      script.
        var f3 = function() { document.getElementById('myImage').src='#{data.item3}' }

      button(onclick='f1()') One!
      button(onclick='f2()') Two!
      button(onclick='f3()') Three!
      p
      a: img(id='myImage' height='200' width='200' src='')
    ```

1. Yollar klasöründe açın *index.js*.

1. Çağırmadan önce aşağıdaki kodu ekleyin `router.get`:

    ```js
    var getData = function () {
        var data = {
            'item1': 'http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-76.jpg',
            'item2': 'http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-77.jpg',
            'item3': 'http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-78.jpg'
        }
        return data;
    }
    ````

1. Değiştir `router.get` işlev çağrısı ile aşağıdaki kodu:

    ```js
    router.get('/', function (req, res) {
        res.render('index', { title: 'Express', "data" });
    });
    ```

    Kodu içeren satırda bir hata var. `res.render`. Uygulamayı çalıştırmadan önce sorunu gidermek gerekir. Biz, sonraki bölümde hatayı düzeltin.

## <a name="use-intellisense"></a>IntelliSense kullanma

1. İçinde *index.js*, kodu içeren satırı gidin `res.render`.

1. Sonra `data` dize, yazın `: get` ve IntelliSense gösterir, `getData` işlevi. Seçin `getData`.

    ![IntelliSense kullanma](../nodejs/media/tutorial-nodejs-intellisense.png)

1. Virgül Kaldır (`,`) önce `"data"` ve ifade yeşil sözdizimi vurgulama bakın. Söz dizimi vurgulamayı üzerine gelin.

    ![Görünüm sözdizimi hatası](../nodejs/media/tutorial-nodejs-syntax-checking.png)

    Bu ileti son satırının JavaScript yorumlayıcı virgül beklenen söyler (`,`).

1. Tıklatın **hata listesi** sekmesi.

    Uyarı ve dosya adı ve satır numarası ile birlikte açıklama bakın.

    ![Görünüm hata listesi](../nodejs/media/tutorial-nodejs-error-list.png)

1. Kod virgülle ekleyerek düzeltme (`,`) önce `"data"`.

## <a name="set-a-breakpoint"></a>Bir kesme noktası ayarlama

1. İçinde *index.js*, aşağıdaki kod satırı ile bir kesme noktası ayarlamak için önce sol cilt payı'ı tıklatın:

    `res.render('index', { title: 'Express', "data": getData() });`

    Kesme noktaları güvenilir hata ayıklama en temel ve temel özelliğidir. Bir kesme noktası değişkenlerin değerleri veya bellek davranışını göz olabilmesi için Visual Studio çalışan kodunuzu nereye askıya almanız veya kod dalı çalıştırmak destekleyip desteklemediğini belirtir.

    ![Bir kesme noktası ayarlama](../nodejs/media/tutorial-nodejs-set-breakpoint.png)

## <a name="run-the-application"></a>Uygulamayı çalıştırın

1. Hata ayıklama araç çubuğundaki hata ayıklama hedefi seçin.

    ![Hata ayıklama hedefi seçin](../nodejs/media/tutorial-nodejs-deploy-target.png)

1. Tuşuna **F5** (**hata ayıklama** > **hata ayıklamayı Başlat**) uygulamayı çalıştırın.

    Hata ayıklayıcı ayarladığınız kesme noktasında duraklatır. Şimdi, uygulama durumunu denetleyebilirsiniz.

1. Üzerine gelerek `getData` bir DataTip içinde özelliklerini görmek için

    ![Değişkenleri inceleyin.](../nodejs/media/tutorial-nodejs-inspect-variables.png)

1. Tuşuna **F5** (**hata ayıklama** > **devam**) devam etmek için.

    Uygulamayı tarayıcıda açılır.

    Tarayıcı penceresinde görürsünüz "title"Hoş Geldiniz Express"ilk paragrafa Express ve".

1. Farklı görüntüleri göstermek için düğmeler'i tıklatın.

    ![Tarayıcıda çalışan uygulama](../nodejs/media/tutorial-nodejs-running-in-browser.png)

1. Web tarayıcısını kapatın.

## <a name="optional-publish-to-azure-app-service"></a>(İsteğe bağlı) Azure App Service'te yayımlama

1. Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Yayımla**.

   ![Azure App Service'te yayımlama](../nodejs/media/tutorial-nodejs-publish-to-azure.png)

1. Seçin **Microsoft Azure uygulama hizmeti**.

    İçinde **uygulama hizmeti** iletişim kutusunda, Azure hesabınızda oturum açın ve mevcut Azure aboneliklerine bağlanma.

1. Bir aboneliği seçin, seçin veya bir kaynak grubu oluşturmak, seçin veya bir uygulama hizmeti düzlemi oluşturmak için kalan adımları izleyin ve sonra için Azure yayımlama isteyip istemediğiniz sorulduğunda adımları izleyin. Daha ayrıntılı yönergeler için bkz: [Azure Web sitesi için Web dağıtımı kullanarak yayımla](https://github.com/Microsoft/nodejstools/wiki/Publish-to-Azure-Website-using-Web-Deploy).

1. **Çıkış** penceresi Azure'a dağıtma hakkında ilerleme durumunu gösterir.

    Başarılı dağıtım üzerinde uygulamanızı Azure App Service içinde çalışan bir tarayıcıda açılır. Görüntüyü görüntülemek için bir düğmeye tıklayın.

   ![Azure App Service içinde çalışan uygulama](../nodejs/media/tutorial-nodejs-running-in-azure.png)

Bu öğreticiyi tamamlamak Tebrikler!

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, oluşturmak ve Express kullanarak bir Node.js uygulaması çalıştırmak ve hata ayıklayıcıyı kullanma bir kesme noktası isabet öğrendiniz.

> [!div class="nextstepaction"]
> [Visual Studio için Node.js Araçları](https://github.com/Microsoft/nodejstools)