---
title: Node.js ve tepki uygulaması oluşturma
description: Bu öğreticide, Visual Studio için Node.js araçları kullanarak bir uygulama oluşturun
ms.custom: mvc
ms.date: 05/23/2018
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
ms.openlocfilehash: 8ea6494cbf71cced24ead52cd091500578b25f8c
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089821"
---
# <a name="tutorial-create-a-nodejs-and-react-app-in-visual-studio"></a>Öğretici: Visual Studio'da bir Node.js ve tepki uygulaması oluşturma

Visual Studio kolayca bir Node.js projesi oluşturun ve IntelliSense ve Node.js destekleyen diğer yerleşik özellikleri deneyimi sağlar. Bu öğreticide Visual Studio için Visual Studio şablonundan bir Node.js web uygulaması projesi oluşturun. Ardından, tepki kullanarak basit bir uygulama oluşturun.

Bu öğreticide, bilgi nasıl yapılır:
> [!div class="checklist"]
> * Node.js projesi oluşturma
> * Npm paket ekleme
> * Uygulamanıza tepki kod ekleme
> * Transpile JSX
> * Hata ayıklayıcıyı Ekle

## <a name="prerequisites"></a>Önkoşullar

* Visual Studio yüklü 2017 ve Node.js geliştirme iş yükü olması gerekir.

    Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

    Gerekiyorsa iş yükü yükleyin ancak zaten Visual Studio varsa, seçin **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu. Visual Studio yükleyicisi başlatır. Seçin **Node.js geliştirme** iş yükü, ardından **Değiştir**.

* Node.js çalışma zamanı yüklü olması gerekir.

    Bu öğretici 8.11.2 sürümle test edilmiştir.

    LTS sürümünden yüklü yoksa, yükleme [Node.js](https://nodejs.org/en/download/) Web sitesi. Genel olarak, Visual Studio yüklenmiş Node.js çalışma zamanı otomatik olarak algılar. Yüklü bir çalışma zamanı algılamazsa yüklü çalışma zamanı özellikleri sayfasında başvurmak için projenizi yapılandırabilirsiniz (bir proje oluşturduktan sonra proje düğümüne sağ tıklayın ve seçin **özellikleri**).

## <a name="create-a-project"></a>Proje oluşturma

İlk olarak, bir Node.js web uygulaması projesi oluşturun.

1. Visual Studio 2017'ni açın.

1. Üst menü çubuğundan seçin **dosya** > **yeni** > **proje**.

1. İçinde **yeni proje** iletişim kutusunda, sol bölmede, genişletin **JavaScript**ve ardından **Node.js**. Orta bölmede seçin **boş Node.js Web uygulaması**, bir ad yazın **NodejsWebAppBlank**ve ardından **Tamam**.

     Görmüyorsanız, **boş Node.js Web uygulaması** proje şablonu, Node.js geliştirme iş yükü önce yüklemeniz gerekir.

    Visual Studio yeni çözüm oluşturur ve projenizin açar.

    ![Çözüm Gezgini'nde node.js projesi](../nodejs/media/tutorial-nodejs-react-project-structure.png)

    * Kalın olarak vurgulanmış olan, vermiş adını kullanarak projenize **yeni proje** iletişim kutusu. Dosya sisteminde, bu proje tarafından temsil edilen bir *.njsproj* proje klasörünüzdeki dosya. Özellikler ve projeye sağ tıklayıp seçerek projeyle ilişkili ortam değişkenleri ayarlayabilirsiniz **özellikleri**. Proje dosyası Node.js projesi kaynağına özel değişiklikler yapmaz beri gidiş diğer geliştirme araçları ile yapabilirsiniz.

    * En üst düzeyinde varsayılan olarak, projenizin aynı ada sahip bir, çözümüdür. Tarafından temsil edilen bir çözüm bir *.sln* dosya diskte, bir veya daha fazla ilgili projeleri için bir kapsayıcıdır.

    * Npm düğüm herhangi bir yüklü npm paket gösterir. Arayın ve iletişim kutusunu kullanarak npm paket yüklemek için npm düğümünü sağ tıklayabilirsiniz.

    * Proje dosyaları gibi *server.js* proje düğümünün altında görünür. *Server.js* proje başlangıç dosyasıdır.

## <a name="add-npm-packages"></a>Npm paket ekleme

Bu uygulama npm modülleri düzgün çalışması için bir dizi gerektirir.

* tepki
* tepki dom
* Express
* yol
* TS yükleyicisi
* typescript
* webpack
* webpack-cli

1. Çözüm Gezgini'nde (sağ bölme), sağ **npm** proje düğümünde ve **yüklemek yeni npm paketler**.

    İçinde **yükleme yeni npm paketler** iletişim kutusu, seçebilirsiniz en güncel paket sürümünü yükleyin veya bir sürüm belirtin. Bu paketleri geçerli sürümünü yüklemek, ancak daha sonra beklenmeyen hatalarla karşılaşırsanız çalıştırmak isterseniz, daha sonra Bu adımlarda açıklanan tam paketi sürümleri yüklemeniz gerekebilir.

1. İçinde **yükleme yeni npm paket** iletişim kutusu, tepki paketi için arama yapın ve seçin **paket yükleme** yükleyin.

    ![Npm paket yüklemek için](../nodejs/media/tutorial-nodejs-react-install-packages.png)

    Seçin **çıkış** paket yükleme ilerleme durumunu görmek için penceresini (seçin **Npm** içinde **Göster çıktı** alan). Yüklendiğinde, paketin altında görünür **npm** düğümü.

    Projenin *package.json* dosya, Paket sürümü de dahil olmak üzere yeni paket bilgilerle güncelleştirilir.

1. Arayın ve paketleri geri kalanı eklemek için kullanıcı arabirimini kullanmak yerine bir seferde bir başvurularında package.json. Değiştir `dependencies` bu kodu bir bölümle:

    ```js
    "dependencies": {
      "express": "4.16.2",
      "path": "0.12.7",
      "react": "16.4.0",
      "react-dom": "16.4.0",
      "ts-loader": "4.0.1",
      "typescript": "2.7.2",
      "webpack": "4.1.1",
      "webpack-cli": "2.0.11"
    }
    ```

1. Sağ **npm** projenizi düğümünde ve **güncelleştirmesi npm paketleri**.

    Seçin **çıkış** paketleri yükleme ilerleme durumunu görmek için penceresi. Yükleme birkaç dakika sürebilir ve sonuçları hemen göremeyebilirsiniz.

    Burada, onlar yüklendikten sonra Çözüm Gezgini'nde göründükleri gibi npm modülleri bulunmaktadır.

    ![npm paket](../nodejs/media/tutorial-nodejs-react-npm-modules.png)

    > [!NOTE]
    > Komut satırını kullanarak npm paketleri yüklemek tercih ederseniz, proje düğümüne sağ tıklayın ve seçin **burada açık bir komut istemi**. Paketleri yüklemek için standart Node.js komutları kullanın.

## <a name="add-project-files"></a>Proje Dosyaları Ekle

Bu adımlarda, dört yeni dosyalar projenize ekleyin.

* *app.TSX*
* *webpack-config.js*
* *index.HTML*
* *tsconfig.json*

Bu basit uygulama için proje kök dizininde yeni proje dosyalarını ekleyin. (Çoğu uygulamalarında genellikle alt klasörlere dosyaları ekleyin ve göreli yol başvuruları buna uygun olarak ayarlamak.)

1. Çözüm Gezgini'nde projeye sağ **NodejsWebAppBlank** ve **Ekle** > **yeni öğe**.

1. İçinde **Yeni Öğe Ekle** iletişim kutusunda, seçin **TypeScript JSX dosya**, bir ad yazın *app.tsx*seçip **Tamam**.

1. Eklemek için bu adımları yineleyin *webpack config.js*. TypeScript JSX dosya yerine **JavaScript dosyası**.

1. Eklemek için aynı adımı tekrarlayın *index.html* projeye. Bir JavaScript dosyası yerine seçin **HTML dosyası**.

1. Eklemek için aynı adımı tekrarlayın *tsconfig.json* projeye. Bir JavaScript dosyası yerine seçin **TypeScript JSON yapılandırma dosyası**.

## <a name="add-app-code"></a>Uygulama kodu ekleyin

1. Açık *server.js* ve kodu aşağıdaki kodla değiştirin:

    ```javascript
    'use strict';
    var path = require('path');
    var express = require('express');

    var app = express();

    var staticPath = path.join(__dirname, '/');
    app.use(express.static(staticPath));

    // Allows you to set port in the project properties.
    app.set('port', process.env.PORT || 3000);

    var server = app.listen(app.get('port'), function() {
        console.log('listening');
    });
    ```

   Önceki kod Express Node.js web uygulaması sunucunuz olarak başlatmak için kullanır. Bu kod, Proje Özellikleri'nde yapılandırılan bağlantı noktası numarası için bağlantı noktasını ayarlar (varsayılan olarak, bağlantı noktası özelliklerinde 1337 yapılandırılır). Proje özelliklerini açmak için Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **özellikleri**.

1. Açık *app.tsx* ve aşağıdaki kodu ekleyin:

    ```javascript
    declare var require: any

    var React = require('react');
    var ReactDOM = require('react-dom');

    class Hello extends React.Component {
        render() {
            return (
                <h1>Welcome to React!!</h1>
            );
        }
    }

    ReactDOM.render(<Hello />, document.getElementById('root'));
    ```

    Önceki kod, basit bir ileti görüntüler JSX söz dizimini ve tepki kullanır.

1. Açık *index.html* ve değiştirme **gövde** bölümü aşağıdaki kod ile:

    ```html
    <body>
        <div id="root"></div>
        <!-- scripts -->
        <script src="./dist/app-bundle.js"></script>
    </body>
    ```

    Bu HTML sayfası yükler *uygulama bundle.js*, JSX ve tepki kod transpiled düz JavaScript içerir. Şu anda *uygulama bundle.js* boş bir dosyadır. Sonraki bölümde transpile kodu seçeneklerini yapılandırın.

## <a name="configure-webpack-and-typescript-compiler-options"></a>Webpack ve TypeScript derleyici seçeneklerini yapılandırın

Önceki adımlarda eklediğiniz *webpack config.js* projeye. Ardından, webpack yapılandırma kodu ekleyin. Girdi dosyası belirten bir basit webpack yapılandırma ekleyeceksiniz (*app.tsx*) ve bir çıktı dosyası (*uygulama bundle.js*) paketleme ve transpiling JSX düz JavaScript için. Transpiling için Ayrıca bazı TypeScript derleyici seçenekleri yapılandırın. Bu kod webpack ve TypeScript derleyici bir giriş olarak yönelik temel bir yapılandırmadır.

1. Çözüm Gezgini'nde açık *webpack config.js* ve aşağıdaki kodu ekleyin.

    ```json
    module.exports = {
        devtool: 'source-map',
        entry: "./app.tsx",
        mode: "development",
        output: {
            filename: "./app-bundle.js"
        },
        resolve: {
            extensions: ['.Webpack.js', '.web.js', '.ts', '.js', '.jsx', '.tsx']
        },
        module: {
            rules: [
                {
                    test: /\.tsx$/,
                    exclude: /(node_modules|bower_components)/,
                    use: {
                        loader: 'ts-loader'
                    }
                }
            ]
        }
    }
    ```

    Webpack yapılandırma kodu Webpack transpile JSX TypeScript yükleyicisine kullanılacağını söyler.

1. Açık *tsconfig.json* ve varsayılan kod TypeScript derleyici seçeneklerini belirtir. aşağıdaki kodla değiştirin:

    ```json
    {
      "compilerOptions": {
        "noImplicitAny": false,
        "module": "commonjs",
        "noEmitOnError": true,
        "removeComments": false,
        "sourceMap": true,
        "target": "es5",
        "jsx": "react"
      },
      "exclude": [
        "node_modules"
      ],
      "files": [
        "app.tsx"
      ]
    }
    ```

    *app.TSX* kaynak dosya olarak belirtildi.

## <a name="transpile-the-jsx"></a>Transpile JSX

1. Çözüm Gezgini'nde, proje düğümüne sağ tıklayın ve seçin **burada açık bir komut istemi**.

1. Komut isteminde aşağıdaki komutu yazın:

    `node_modules\.bin\webpack app.tsx --config webpack-config.js`

    Komut İstemi penceresini sonucu gösterir.

    ![Webpack Çalıştır](../nodejs/media/tutorial-nodejs-react-run-webpack.png)

    Önceki çıkış yerine herhangi bir hata görürseniz, uygulamanızı çalışmadan önce çözmeniz gerekir. Npm Paket sürümü Bu öğreticide gösterilen sürümlerinden farklı ise, hataların bir kaynak olabilir. Hataları düzeltin yollarından biri önceki adımlarda gösterilen tam sürümünü kullanmaktır. Ayrıca, bir veya daha fazla bu paketi sürümleri kullanım dışı bırakıldı ve bir hatayla sonuçlanır, hataları düzeltmek için daha yeni bir sürümünü yüklemeniz gerekebilir.

1. Çözüm Gezgini'nde, proje düğümüne sağ tıklayın ve seçin **Ekle** > **varolan bir klasörü**, ardından *dağ* klasörü seçin  **Klasörü seçin**.

    Visual Studio ekler *dağ* klasörünü içeren projeye *uygulama bundle.js* ve *uygulama bundle.js.map*.

1. Açık *uygulama bundle.js* transpiled JavaScript kodu görmek için.

1. Dışarıdan değiştirilmiş dosyaları yeniden yüklemek isteyip istemediğiniz sorulduğunda seçin **Tümüne Evet**.

    ![Değiştirilen dosyalar yükleme](../nodejs/media/tutorial-nodejs-react-reload-files.png)

Her zaman yaptığınız değişiklikler *app.tsx*, webpack komutunu çalıştırmanız gerekir.

## <a name="run-the-app"></a>Uygulama Çalıştırma

1. Chrome geçerli hata ayıklama hedefi olarak seçildiğinden emin olun.

    ![Hata ayıklama hedefi olarak Chrome seçin](../nodejs/media/tutorial-nodejs-react-debug-target.png)

1. Uygulamayı çalıştırmak için basın **F5** (**hata ayıklama** > **hata ayıklamayı Başlat**) veya yeşil ok tuşunu.

    Hata ayıklayıcı dinlediği bağlantı noktasını gösteren bir Node.js konsol penceresi açılır.

    Visual Studio Başlangıç dosyayı başlatarak uygulamayı başlatır *server.js*.

    ![Tarayıcıda çalışan tepki](../nodejs/media/tutorial-nodejs-react-running-react.png)

1. Tarayıcı penceresini kapatın.

1. Konsol penceresini kapatın.

## <a name="set-a-breakpoint-and-run-the-app"></a>Bir kesme noktası ayarlama ve uygulama çalıştırma

1. İçinde *server.js*, sol tarafındaki cilt payı tıklayın `staticPath` bildirimi bir kesme noktası ayarlamak için:

    ![Bir kesme noktası ayarlama](../nodejs/media/tutorial-nodejs-react-set-breakpoint.png)

    Kesme noktaları güvenilir hata ayıklama en temel ve temel özelliğidir. Bir kesme noktası değişkenlerin değerleri veya bellek davranışını göz olabilmesi için Visual Studio çalışan kodunuzu nereye askıya almanız veya kod dalı çalıştırmak destekleyip desteklemediğini belirtir.

1. Uygulamayı çalıştırmak için basın **F5** (**hata ayıklama** > **hata ayıklamayı Başlat**).

    Hata ayıklayıcı kesme noktasında, duraklatır (sarı olarak geçerli deyimi işaretli) ayarlama. Şimdi, uygulama durumu şu anda, kapsamındaki değişkenleri üzerine gelerek hata ayıklayıcı windows gibi kullanarak inceleyebilirsiniz **Yereller** ve **izleme** windows.

1. Tuşuna **F5** uygulamaya devam etmek için.

1. Chrome geliştirici araçları kullanmak istiyorsanız, basın **F12**. DOM inceleyin ve JavaScript konsolunu kullanarak uygulama ile etkileşim kurmak için bu araçları kullanabilirsiniz.

1. Web tarayıcısı ve konsolu kapatın.

## <a name="set-and-hit-a-breakpoint-in-the-client-side-react-code"></a>Ayarlanmış ve istemci tarafı tepki kodda bir kesme noktası isabet

Önceki bölümde, sunucu tarafı Node.js kodu hata ayıklayıcısı ekli. Hata ayıklayıcı Visual Studio'dan ekleyin ve istemci tarafı tepki kodda kesme noktası isabet, hata ayıklayıcı doğru işlemi tanımlamak için Yardım gerekiyor. Bunu yapmanın bir yolu burada verilmiştir.

1. Tüm Chrome pencerelerini kapatın.

1. Açık **çalıştırmak** Windows komutunu **Başlat** düğmesi (sağ tıklatın ve seçin **çalıştırmak**) ve aşağıdaki komutu girin:

    `chrome.exe --remote-debugging-port=9222`

    Bu, Chrome hata ayıklama etkin durumdayken başlatır.

1. Geçiş için Visual Studio ve bir kesme noktası kümesinde *uygulama bundle.js* kod `render()` işlev aşağıdaki çizimde gösterildiği gibi:

    ![Bir kesme noktası ayarlama](../nodejs/media/tutorial-nodejs-react-set-breakpoint-client-code.png)

1. Visual Studio'da hata ayıklama hedefi olarak seçilen Chrome ile basın **Ctrl**+**F5** (**hata ayıklama** > **hata ayıklama olmadan Başlat** ) tarayıcıda uygulamayı çalıştırmak için.

    Uygulamayı yeni bir tarayıcı sekmesinde açar.

1. Seçin **hata ayıklama** > **işleme iliştirilemiyor**.

1. İçinde **ekleme işlemi için** iletişim kutusunda, seçin **Webkit kod** içinde **ekleme** alanında, yazın **chrome** ve filtre kutusuna filtrelemek için Arama sonuçları.

1. Doğru konak Chrome işlemine (Bu örnekte 1337) bağlantı noktası seçin seçip **Attach**.

    ![İşleme iliştirilemiyor](../nodejs/media/tutorial-nodejs-react-attach-to-process.png)

    Visual Studio'da DOM Gezgini ve JavaScript konsolu açtığınızda, hata ayıklayıcı doğru eklenmiş bildiğiniz. Bu hata ayıklama araçları Chrome geliştirici araçları ve kenar için F12 araçları benzerdir.

    > [!NOTE]
    > Hata ayıklayıcıyı Ekle değil ve "işleme iliştirilemiyor yüklenemiyor. ileti görüyorsanız Bir işlem geçerli durumu geçerli değil. ", hata ayıklama modu Chrome başlatmadan önce tüm Chrome örneklerini kapatmak için Görev Yöneticisi'ni kullanın. Chrome uzantıları çalıştıran ve tam hata ayıklama modu engelliyor.

1. Kesme noktası koduyla zaten yürütülen olduğundan, kesme noktası isabet, tarayıcı sayfayı yenileyin.

    Hata ayıklayıcıda duraklatıldı olsa da, değişkenlerinden bekleyerek ve hata ayıklayıcı windows kullanarak, uygulama durumunu inceleyebilirsiniz. Hata ayıklayıcı kod üzerinden adımla ilerletebilirsiniz (**F5**, **F10**, ve **F11**).

    Her ikisinde kesme noktası isabet *uygulama bundle.js* veya eşlenen konumunda *app.tsx*ortamı ve tarayıcı durumuna bağlı olarak. Her iki durumda da kod üzerinden adım ve değişkenleri inceleyin.

    * Kodda içine bölün gerekiyorsa *app.tsx* ve bunu kullanmak **ekleme işlemi için** hata ayıklayıcısını önceki adımlarda açıklandığı gibi. Dinamik olarak üretilen açmak *app.tsx* açarak dosya Çözüm Gezgini'nden **betik belgelerini** > **app.tsx**, bir kesme noktası ayarlayın ve Yenile tarayıcınızda sayfası (kesme noktaları, gibi veren kod satırında kesme noktası belirleyerek `return` deyimi veya `var` bildirim).

        Alternatif olarak, kodda içine bölün gerekiyorsa *app.tsx* ve bunu, kullanmayı deneyin `debugger;` deyiminde *app.tsx*, veya bunun yerine Chrome Geliştirici Araçları'nda kesme noktalarını ayarlayın.

    * Kodda içine bölün gerekiyorsa *uygulama bundle.js* ve bunu, kaynak eşleme dosyası Kaldır *uygulama bundle.js.map*.

    > [!TIP]
    > Aşağıdaki adımları izleyerek ilk kez işleme iliştirilemiyor sonra hızlı bir şekilde Visual Studio 2017 aynı işlem seçerek iliştirebilirsiniz **hata ayıklama** > **işlem için yeniden bağlayın**.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Uygulama Azure App Service'e dağıtma](../deployment/quickstart-deploy-to-azure.md)

Bu öğreticide, Node.js ve tepki uygulama, transpile JSX ve hata ayıklama nasıl oluşturulacağı hakkında bilgi edindiniz. Daha fazla bilgi için bkz: [github'da Visual Studio için Node.js Araçları](https://github.com/Microsoft/nodejstools).