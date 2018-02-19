---
title: "Visual Studio'da Node.js ile çalışmaya başlama | Microsoft Docs"
ms.custom: 
ms.date: 11/30/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: 
ms.topic: tutorial
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: ghogen
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 1d91d46b20f82a1700c2d20639b3a8827c92bcb0
ms.sourcegitcommit: a07b789cc41ed72664f2c700c1f114476e7b0ddd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/19/2018
---
# <a name="getting-started-with-nodejs-in-visual-studio"></a>Visual Studio'da Node.js ile çalışmaya başlama
Bu öğreticide Visual Studio kullanarak Node.js geliştirme için basit bir Node.js web uygulaması oluşturma, bazı kodlar ekleyin, IDE bazı özellikleri keşfedin ve uygulamayı çalıştırın. Visual Studio henüz yüklemediyseniz, ücretsiz yükleme [burada](http://www.visualstudio.com).  

## <a name="create-a-project"></a>Proje oluşturma
İlk olarak, bir Node.js web uygulaması projesi oluşturacaksınız.

1. Visual Studio 2017'ni açın.  

2. Üst menü çubuğundan seçin **dosya** > **yeni** > **proje...** .  

3. İçinde **yeni proje** iletişim kutusunda, sol bölmede, genişletin **JavaScript**, ardından **Node.js**. Orta bölmede seçin **temel Azure Node.js Express 4 uygulama**, ardından **Tamam**.   

     Görmüyorsanız, **temel Azure Node.js Express 4 uygulama** proje şablonu, tıklatın **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu. Visual Studio yükleyicisi başlatır. Seçin **Node.js geliştirme** iş yükü, ardından **Değiştir**. 

    Visual Studio yeni çözüm oluşturur ve projenizin açar. **App.js** proje dosyası (sol bölme) Düzenleyicisi'nde açar. Visual Studio çözümler ve projeler bilmiyorsanız, bkz: [hızlı başlangıç: ilk Node.js uygulamanızı oluşturmak için Visual Studio](../ide/quickstart-nodejs.md).

4. Zaten yüklü Node.js çalışma zamanı yoksa, bu klasörden yüklenmesini [Node.js](https://nodejs.org/en/download/) Web sitesi.

    Genel olarak, Visual Studio yüklenmiş Node.js çalışma zamanı otomatik olarak algılar. Yüklü bir çalışma zamanı algılamazsa yüklü çalışma zamanı başvurmak için projenizi yapılandırabilirsiniz.

## <a name="add-some-code"></a>Bazı kodlar ekleyin

1. Çözüm Gezgini'nde (sağ bölme), görünümleri klasörünü açın, sonra index.pug açın.

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

1. Yollar klasöründe index.js açın.

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

1. Sonra `data`, türü `: get` ve IntelliSense, getData işlevi gösterir. Seçin `getData`.

    ![IntelliSense kullanma](../nodejs/media/tutorial-nodejs-intellisense.png) 

1. Virgül Kaldır (`,`) önce `"data"` ve ifade yeşil sözdizimi vurgulama bakın. Söz dizimi vurgulamayı üzerine gelin.

    ![Görünüm sözdizimi hatası](../nodejs/media/tutorial-nodejs-syntax-checking.png) 

    Bu ileti son satırının JavaScript yorumlayıcı virgül beklenen söyler (`,`).

1. Tıklatın **hata listesi** sekmesi.

    Uyarı ve dosya adı ve satır numarası ile birlikte açıklama bakın.

    ![Görünüm hata listesi](../nodejs/media/tutorial-nodejs-error-list.png)

1. Kod virgülle ekleyerek düzeltme (`,`) önce `"data"`.

## <a name="set-a-breakpoint"></a>Bir kesme noktası ayarlama

1. Aşağıdaki kod satırı ile bir kesme noktası ayarlamak için önce sol cilt payı index.js içinde'ı tıklatın:

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

1. Node.js etkileşimli seçerek penceresini **Görünüm** > **diğer pencereler** > **Node.js etkileşimli pencere**.

   ![Node.js etkileşimli penceresini açın](../nodejs/media/tutorial-nodejs-interactive-window.png)  

    Etkileşimli pencere kullanımı dahil olmak üzere kodda yapabileceğiniz her şeyi destekleyen `require()` deyimleri. Aşağıdaki ekran görüntüsünde kodda bir değişken tanımlar ve Node.js yorumlayıcı konumunu görüntüler.

   ![Node.js etkileşimli penceresi](../nodejs/media/tutorial-nodejs-interactive-window-example.png)  

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

- Daha fazla bilgi edinmek [Visual Studio için Node.js araçları](https://github.com/Microsoft/nodejstools/wiki)  
- Daha fazla bilgi edinmek [Visual Studio IDE](../ide/visual-studio-ide.md)  