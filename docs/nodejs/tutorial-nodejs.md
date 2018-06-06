---
title: Node.js ve hızlı uygulama oluşturma
description: Bu öğreticide, Visual Studio için Node.js araçları kullanarak bir uygulama oluşturun
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
ms.openlocfilehash: c364c977ebd7f1160bd9265f2a0228bd2e514442
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765836"
---
# <a name="tutorial-create-a-nodejs-and-express-app-in-visual-studio"></a>Öğretici: Visual Studio'da bir Node.js ve hızlı uygulama oluşturma
Node.js ve Express kullanarak Visual Studio geliştirme için bu öğreticideki basit bir Node.js web uygulaması oluşturma, bazı kodlar ekleyin, IDE özelliklerinden bazıları keşfedin ve uygulamayı çalıştırın. Visual Studio henüz yüklemediyseniz, ücretsiz yükleme [burada](http://www.visualstudio.com).

Bu öğreticide, bilgi nasıl yapılır:
> [!div class="checklist"]
> * Node.js projesi oluşturma
> * Bazı kodlar ekleyin
> * IntelliSense kod düzenlemek için kullanın
> * Uygulama Çalıştırma
> * Hata ayıklayıcı kesme noktası isabet

## <a name="before-you-begin"></a>Başlamadan önce

Burada, bazı temel kavramları tanıtmak için bir hızlı sık sorulan sorular verilmiştir.

### <a name="what-is-nodejs"></a>Node.js nedir?

Node.js JavaScript sunucu tarafı yürüten bir sunucu tarafı JavaScript çalışma zamanı ortamıdır.

### <a name="what-is-npm"></a>Npm nedir?

npm, Node.js için varsayılan paket yöneticisidir. Paket Yöneticisi, yayımlama ve kaynak kodu Node.js kitaplıkların paylaşmak programcıları için kolaylaştırır ve yükleme, güncelleştirme ve kaldırma kitaplıkların kolaylaştırmak için tasarlanmıştır.

### <a name="what-is-express"></a>Express nedir?

Express web uygulamaları oluşturmak için Node.js için sunucu çerçevesi olarak kullanılan bir web Uygulama Çerçevesi ' dir. Express kullanmanıza olanak verir (eski adıyla Jade) Pug gibi bir kullanıcı Arabirimi oluşturmak için farklı ön uç çerçeveleri seçin. Bu öğreticide pug kullanılır.

## <a name="prerequisites"></a>Önkoşullar

* Visual Studio yüklü 2017 ve Node.js geliştirme iş yükü olması gerekir.

    Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

    İş yükü yüklenir ancak tıklatın Visual Studio zaten gerektiğinde **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu (seçin **dosya**  >  **Yeni** > **proje**). Visual Studio yükleyicisi başlatır. Seçin **Node.js geliştirme** iş yükü, ardından **Değiştir**.

* Node.js çalışma zamanı yüklü olması gerekir.

    LTS sürümünden yüklü yoksa, yükleme [Node.js](https://nodejs.org/en/download/) Web sitesi. Genel olarak, Visual Studio yüklenmiş Node.js çalışma zamanı otomatik olarak algılar. Yüklü bir çalışma zamanı algılamazsa yüklü çalışma zamanı özellikleri sayfasında başvurmak için projenizi yapılandırabilirsiniz (bir proje oluşturduktan sonra proje düğümüne sağ tıklayın ve seçin **özellikleri**).

    Bu öğretici 8.10.0 Node.js ile test edilmiştir.

## <a name="create-a-new-nodejs-project"></a>Yeni bir Node.js projesi oluşturma

Visual Studio yönetir dosyaları tek bir uygulama için bir *proje*. Proje kaynak kodu, kaynakları ve yapılandırma dosyalarını içerir.

Bu öğreticide, Node.js ve hızlı uygulama için bir kod içeren basit bir proje ile başlar.

1. Visual Studio 2017'ni açın.

1. Üst menü çubuğundan seçin **dosya** > **yeni** > **proje**.

1. İçinde **yeni proje** iletişim kutusunda, sol bölmede, genişletin **JavaScript**ve ardından **Node.js**. Orta bölmede seçin **temel Azure Node.js Express 4 uygulama** ve ardından **Tamam**.

     Görmüyorsanız, **temel Azure Node.js Express 4 uygulama** proje şablonu, yüklemelisiniz **Node.js geliştirme** iş yükü ilk (yönergeler önkoşullara bakın).

    Visual Studio yeni çözüm oluşturur ve projenize sağ bölmede açar. *App.js* proje dosyası (sol bölme) Düzenleyicisi'nde açar.

    ![Proje yapısı](../nodejs/media/tutorial-project-structure.png)

    (1) vurgulanan **kalın** , vermiş adı kullanarak, proje **yeni proje** iletişim kutusu. Dosya sisteminde, bu proje tarafından temsil edilen bir *.njsproj* proje klasörünüzdeki dosya. Özellikler ve projeye sağ tıklayıp seçerek projeyle ilişkili ortam değişkenleri ayarlayabilirsiniz **özellikleri**. Proje dosyası özel Node.js projesi kaynağına değişiklik değil çünkü gidiş diğer geliştirme araçları ile yapabilirsiniz.

    (2) en üst düzeyinde, projenizin aynı ada sahip varsayılan bir çözüm bulunur. Tarafından temsil edilen bir çözüm bir *.sln* dosya diskte, bir veya daha fazla ilgili projeleri için bir kapsayıcıdır.

    (3) npm düğüm herhangi bir yüklü npm paket gösterir. Npm aramak ve bir iletişim kutusu veya yükleme kullanarak npm paketleri yüklemek ve güncelleştirme ayarları kullanarak paketleri düğüme sağ *package.json* ve npm düğümü seçeneklerinde sağ tıklatın.

    (4) *package.json* tarafından npm Paket bağımlılıklarını ve yerel olarak yüklü olan paketleri paket sürümlerini yönetmek için kullanılan bir dosya.

    (5) project dosyaları gibi *app.js* proje düğümünün altında görünür. *app.js* proje başlangıç dosyası ve diğer bir deyişle neden olarak görüntülersiniz **kalın**. Proje dosyasında sağ tıklayıp seçerek başlangıç dosyası ayarlayabilirsiniz **Node.js başlangıç dosyası ayarlı**.

1. Açık **npm** düğümü ve tüm gerekli npm paketler mevcut olduğundan emin olun.

    Herhangi bir paket (ünlem işareti simgesi) eksikse, sağ tıklayarak **npm** düğümü seçin **npm paket yükleme eksik**.

## <a name="add-some-code"></a>Bazı kodlar ekleyin

Uygulama için ön uç JavaScript çerçevesini Pug kullanır. Pug HTML olarak derler basit biçimlendirme kodu kullanır. (Pug görüntüleme altyapısı olarak ayarlandığında *app.js*. Görünüm altyapısı ayarlar kodu *app.js* olan `app.set('view engine', 'pug');`.)

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

    Önceki kod, dinamik olarak bir başlık ve Hoş Geldiniz iletisi içeren bir HTML sayfası oluşturmak için kullanılır. Sayfa ayrıca her bir düğmesine bastığınızda, değişiklikleri görüntüyü görüntülemek için kod içerir.

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

    Bu kod size dinamik olarak üretilen HTML sayfasına geçer bir veri nesnesi oluşturur.

1. Değiştir `router.get` işlev çağrısı ile aşağıdaki kodu:

    ```js
    router.get('/', function (req, res) {
        res.render('index', { title: 'Express', "data" });
    });
    ```
    
    Önceki kod Express yönlendirici nesnesini kullanarak geçerli sayfa ayarlar ve sayfaya başlık ve veri nesnesi geçirme sayfasını işler. *İndex.pug* dosyasında belirtilir ne zaman yükleme sayfası olarak burada *index.js* çalıştırır. *index.js* varsayılan rotada olarak yapılandırılan *app.js* kod (gösterilmez).

    Visual Studio birkaç özelliklerini göstermek için size bir hata kodu içeren satırında yer `res.render`. Uygulamayı çalıştırmadan önce hatayı düzeltmek gerekir. Biz, sonraki bölümde hatayı düzeltin.

## <a name="use-intellisense"></a>IntelliSense kullanma

IntelliSense kod yazarken, size yardımcı olur Visual Studio bir araçtır.

1. İçinde *index.js*, kodu içeren satırı gidin `res.render`.

1. İmlecinizi sonra yerleştirin `data` dize, yazın `: get` ve IntelliSense size gösterir `getData` kod içinde tanımlanan işlevi. Seçin `getData`.

    ![IntelliSense kullanma](../nodejs/media/tutorial-nodejs-intellisense.png)

1. Virgül Kaldır (`,`) önce `"data"` ve ifade yeşil sözdizimi vurgulama bakın. Söz dizimi vurgulamayı üzerine gelin.

    ![Görünüm sözdizimi hatası](../nodejs/media/tutorial-nodejs-syntax-checking.png)

    Bu ileti son satırının JavaScript yorumlayıcı virgül beklenen söyler (`,`).

1. Alt bölmede **hata listesi** sekmesi.

    Uyarı ve dosya adı ve satır numarası ile birlikte açıklama bakın.

    ![Görünüm hata listesi](../nodejs/media/tutorial-nodejs-error-list.png)

1. Kod virgülle ekleyerek düzeltme (`,`) önce `"data"`.

    Düzeltilen, kod satırı aşağıdaki gibi görünmelidir: `res.render('index', { title: 'Express', "data": getData() });`

## <a name="set-a-breakpoint"></a>Bir kesme noktası ayarlama

Visual Studio hata ayıklayıcısı ekli uygulama çalıştırma olacak. Biz bunu yapmadan önce bir kesme noktası belirleyerek gerekir.

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

    ![Değişkenleri inceleme](../nodejs/media/tutorial-nodejs-inspect-variables.png)

1. Tuşuna **F5** (**hata ayıklama** > **devam**) devam etmek için.

    Uygulamayı tarayıcıda açılır.

    Tarayıcı penceresinde görürsünüz "title"Hoş Geldiniz Express"ilk paragrafa Express ve".

1. Farklı görüntüleri göstermek için düğmeler'i tıklatın.

    ![Tarayıcıda çalışan uygulama](../nodejs/media/tutorial-nodejs-running-in-browser.png)

1. Web tarayıcısını kapatın.

## <a name="optional-publish-to-azure-app-service"></a>(İsteğe bağlı) Azure App Service'te yayımlama

1. Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Yayımla**.

   ![Azure App Service’e yayımlama](../nodejs/media/tutorial-nodejs-publish-to-azure.png)

1. Seçin **Microsoft Azure uygulama hizmeti**.

    İçinde **uygulama hizmeti** iletişim kutusunda, Azure hesabınızda oturum açın ve mevcut Azure aboneliklerine bağlanma.

1. Bir aboneliği seçin, seçin veya bir kaynak grubu oluşturmak, seçin veya bir uygulama hizmeti düzlemi oluşturmak için kalan adımları izleyin ve sonra için Azure yayımlama isteyip istemediğiniz sorulduğunda adımları izleyin. Daha ayrıntılı yönergeler için bkz: [Yayımla web kullanarak Azure Web sitesine dağıtmak](https://github.com/Microsoft/nodejstools/wiki/Publish-to-Azure-Website-using-Web-Deploy).

1. **Çıkış** penceresi Azure'a dağıtma hakkında ilerleme durumunu gösterir.

    Başarılı dağıtım üzerinde uygulamanızı Azure App Service içinde çalışan bir tarayıcıda açılır. Görüntüyü görüntülemek için bir düğmeye tıklayın.

   ![Azure App Service içinde çalışan uygulama](../nodejs/media/tutorial-nodejs-running-in-azure.png)

Bu öğreticiyi tamamlamak Tebrikler!

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, oluşturmak ve Express kullanarak bir Node.js uygulaması çalıştırmak ve hata ayıklayıcıyı kullanma bir kesme noktası isabet öğrendiniz.

> [!div class="nextstepaction"]
> [Visual Studio için node.js araçları](https://github.com/Microsoft/nodejstools)