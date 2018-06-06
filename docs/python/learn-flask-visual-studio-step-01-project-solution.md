---
title: Öğretici - Visual Studio, 1. adım Flask öğrenin
description: Visual Studio projeleri bağlamında Flask temel bir kılavuz.
ms.date: 06/04/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 2420beaa7f200ca281e04189667c1534e2a0f991
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752510"
---
# <a name="tutorial-step-1-get-started-with-the-flask-web-framework-in-visual-studio"></a>Öğreticisi 1. adım: Visual Studio'da Flask web çerçevesi kullanmaya başlama

[Flask](http://flask.pocoo.org/) URL Yönlendirme ve sayfa işleme için temel bilgileri sağlayan bir basit Python web uygulamaları için çerçevedir.

Form doğrulama, veritabanı Özet, kimlik doğrulama vb. gibi özellikleri doğrudan sağlamadığından flask "mikro" framework adı verilir. Bu özellikler bunun yerine Flask adlı özel Python paketlerini tarafından sağlanan *uzantıları*. Böylece Flask kendisini parçası oldukları gibi görünür uzantıları Flask ile sorunsuz şekilde tümleşir. Örneğin, Flask kendisini bir sayfa şablon motoru sağlamaz. Şablon Bu öğreticide gösterildiği gibi Jinja ve Jade, gibi uzantıları tarafından sağlanır.

Bu öğreticide, bilgi nasıl yapılır:

> [!div class="checklist"]
> - "Boş Flask Web projesi" şablonu (1. adım) kullanarak Git deposunda bir temel Flask projesi oluşturma
> - Bir sayfayla Flask uygulaması oluşturma ve bir şablonu (2. adım) kullanarak bu sayfayı işlemek
> - Statik dosyaları işleme, sayfa ekleyin ve şablon devralma (adım 3) kullanın
> - Birden çok sayfa ve esnek tasarım (4. adım) bir uygulama oluşturmak için Flask Web projesi şablonu kullanın
> - Çeşitli depolama seçenekleri (Azure depolama, MongoDB veya bellek) kullanan bir yoklama uygulama oluşturmak için yoklamalar Flask Web projesi şablonunu kullanın.

Bu adımları boyunca üç ayrı projeleri içeren tek bir Visual Studio çözümü oluşturun. Visual Studio ile birlikte farklı Flask proje şablonları kullanarak projesi oluşturun. Aynı Çözümdeki projeler tutarak kolayca geri ve İleri karşılaştırma için farklı dosyalar arasında geçiş yapabilirsiniz.

> [!Note]
> Bu öğretici farklıdır [Flask Quickstart](../ide/quickstart-python.md?context=visualstudio/python/default) içeren farklı Flask kullanmak için kendi projeleri için daha kapsamlı başlangıç sağlamak proje şablonları işaretleyin nasıl Flask hakkında daha fazla de hakkında bilgi edineceksiniz. Örneğin, proje şablonlarını otomatik olarak Flask paketi bir proje oluşturulurken yüklemek yerine, paketi başlangıcın gösterildiği gibi el ile yüklemek için gerek.

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio 2017 Windows aşağıdaki seçeneklere sahip:
  - **Python geliştirme** iş yükü (**iş yükü** yükleyici sekmesinde). Yönergeler için bkz: [yükleme Python desteği Visual Studio'da](installing-python-support-in-visual-studio.md).
  - **Windows için Git** ve **Visual Studio için GitHub uzantısı** üzerinde **bileşenleri tek tek** altında sekmesinde **kod Araçları**.

Bu öğreticide ele gelen ayrıntıları değişebilir ancak flask proje şablonları Visual Studio için Python Araçları'nın tüm eski sürümlerini dahil edilir.

Python geliştirme Visual Studio şu anda Mac için desteklenmiyor Mac ve Linux üzerinde kullanmak [Visual Studio Code Python uzantı](https://code.visualstudio.com/docs/python/python-tutorial).

## <a name="step-1-1-create-a-visual-studio-project-and-solution"></a>1-1. adım: Visual Studio Proje ve çözüm oluşturma

1. Visual Studio'da seçin **dosya** > **yeni** > **proje**"Flask" için arama yapın ve seçin **boş Flask Web projesi**  şablonu. (Şablon ayrıca altında bulunan **Python** > **Web** sol listesinde.)

    ![Boş Flask Web projesi için Visual Studio'da yeni proje iletişim kutusu](media/flask/step01-new-blank-project.png)

1. İletişim kutusunun altındaki alanlara (önceki grafikte gösterildiği gibi) aşağıdaki bilgileri girin ve ardından **Tamam**:

    - **Ad**: "BasicProject" için Visual Studio projesi adını ayarlayın. Bu ad Flask proje için de kullanılır.
    - **Konum**: Visual Studio çözüm ve proje oluşturmak bir konum belirtin.
    - **Çözüm adı**: "LearningFlask", birden çok proje için bir kapsayıcı olarak Bu öğreticide çözüm için uygun olduğu ayarlayın.
    - **Çözüm için dizin oluşturma**: bırakın (varsayılan) ayarlayın.
    - **Yeni bir Git deposu oluşturursunuz**: Visual Studio çözümü oluşturduğunda, yerel bir Git deposu oluşturur, böylece (temizleyin varsayılan olarak etkindir) bu seçeneği belirleyin. Bu seçeneği görmüyorsanız, Visual Studio 2017 yükleyiciyi çalıştırın ve Windows için Git ve GitHub uzantısı Visual Studio için eklemek **bileşenleri tek tek** altında sekmesinde **kod Araçları**.

1. Bir süre sonra "Bu proje gerektiren dış paketler" belirten bir iletişim kutusuyla ister Visual Studio (aşağıda gösterilen). Şablonun içerdiği için bu iletişim kutusu görünür bir `requirements.txt` en son Flask 1.x paketini başvuran dosya. (Seçin **gerekli paketleri Göster** tam bağımlılıkları görmek için.)

    ![Komut istemi bildiren proje dış paketler gerektirir](media/tutorials-common/step01-requirements-prompt-install-myself.png)

1. Seçeneğini **ı bunları kendim yükleyecek**. Kısa süre içinde kaynak denetiminden dışlandı emin olmak için sanal ortamı oluşturun. (Ortamı her zaman oluşturulabilir `requirements.txt`.)

## <a name="step-1-2-examine-the-git-controls-and-publish-to-a-remote-repository"></a>1-2. adım: Git denetimleri inceleyin ve uzak bir depo yayımlama

Seçtiğiniz çünkü **oluştur yeni Git deposu** içinde **yeni proje** iletişim kutusunda, proje zaten yerel kaynak denetimine taahhüt oluşturma işlemi tamamlandıktan hemen sonra. Bu adımda, Visual Studio'nun Git denetimleriyle öğrenmeniz ve **Takım Gezgini** kaynak denetimiyle çalışma penceresi.

1. Visual Studio ana penceresinin alt köşedeki Git denetimlere inceleyin. Soldan sağa, bu denetimlerin unpushed tamamlama, kaydedilmemiş değişiklikler, havuzu ve geçerli dal adını göster:

    ![Visual Studio penceresinde Git denetimleri](media/flask/step01-git-controls.png)

    > [!Note]
    > Seçmezseniz, **oluştur yeni Git deposu** içinde **yeni proje** iletişim kutusunda, Git denetimlerini göster yalnızca bir **eklemek için kaynak denetimi** yerel oluşturur komutu Depo.
    >
    > ![Ekleme kaynak denetimi görünür Visual Studio'da bir deposu oluşturduysanız değil](media/tutorials-common/step01-git-add-to-source-control.png)

1. Değişiklikleri düğmesini seçin ve Visual Studio açılır kendi **Takım Gezgini** penceresinde **değişiklikleri** sayfası. Yeni oluşturulan proje zaten kaynak denetimi otomatik olarak kaydedilmiş olduğundan bekleyen değişiklikleri görmüyorum.

    ![Takım Gezgini penceresi değişiklikleri sayfasında](media/flask/step01-team-explorer-changes.png)

1. Visual Studio durum çubuğunda açmak için ("2" olan yukarı ok) unpushed işlemeleri düğmesini seçin **eşitleme** sayfasındaki **Takım Gezgini**. Yalnızca yerel deposu olduğundan, sayfa için farklı uzak depoları depo yayımlamak için kolay seçenekler sunar.

    ![Takım Gezgini penceresi gösteren Git deposu için kullanılabilir seçenekleri kaynak denetimi](media/flask/step01-team-explorer.png)

    Kendi projeleri için hangi hizmetin seçebilirsiniz. Bu öğretici GitHub, burada öğreticinin tamamlanmış örnek kodu korunur kullanımını göstermektedir [Microsoft/python-örnek-vs-learning-flask](https://github.com/Microsoft/python-sample-vs-learning-flask) deposu.

1. Herhangi bir seçerken **Yayımla** denetimleri **Takım Gezgini** daha fazla bilgi için ister. Örneğin, Bu öğretici için örnek yayımlama sırasında depo ilk olarak, bu durumda oluşturulması gerekiyordu **anında uzak depoya** seçeneği deponun URL ile kullanıldı.

    ![Var olan bir uzak depoya gönderilmesi için Takım Gezgini penceresi](media/flask/step01-push-to-github.png)

    Varolan bir depo yoksa **GitHub Yayımla** ve **anında Visual Studio Team Services** seçenekleri doğrudan Visual Studio'dan oluşturmak olanak sağlar.

1. Bu öğreticide çalışırken, düzenli aralıklarla denetimleri tamamlama ve anında iletme değişiklikler Visual Studio kullanarak alýþkanlýk içine alın. Bu öğretici uygun noktalarda anımsatır.

> [!Tip]
> İçinde hızlı bir şekilde gezinmek için **Takım Gezgini**, kullanılabilir sayfaların açılır menü görmek için ("Değişiklikler" veya "Gönderme" Yukarıdaki görüntüleri okur) üstbilgisini seçin.

### <a name="question-what-are-some-advantages-of-using-source-control-from-the-beginning-of-a-project"></a>Soru: Proje başlangıcı kaynak denetiminden kullanmanın bazı yararları nelerdir?

Yanıt: Öncelikle, özellikle uzak bir depo da kullanıyorsanız başlangıçta, kaynak denetimi kullanarak normal şirket dışı yedeklemeyi projenizin sağlar. Bir proje üzerinde yalnızca koruma aksine bir yerel dosya sistemi kaynak denetimi de tam değişiklik geçmişini ve tek bir dosyayı veya tüm proje önceki bir duruma geri dönmek için kolay yeteneği sağlar. Değişiklik geçmişini gerileme (test başarısızlıklarının) nedenini belirlemeye yardımcı olur. Ayrıca, birden çok kişi üzerinde çalışıyorsanız, proje yönettiği gibi üzerine yazar ve çakışma çözümü sağlar kaynak denetimi esastır. Son olarak, temelde Otomasyon biçimidir, kaynak denetimi, iyi otomatikleştirme derlemeleri, test ve yayın yönetimi için ayarlar. Proje için DevOps kullanmanın ilk adımı gerçekten olduğu ve girişi engelleri kadar düşük olduğundan, gerçekten başına kaynak denetiminden kullanmayacak şekilde bir neden yoktur.

Daha fazla tartışma için kaynak denetimini Otomasyon olarak bkz [gerçekte kaynak: rol, depoları DevOps içinde](https://msdn.microsoft.com/magazine/mt763232), bir makale MSDN mobil uygulamalar için yazılmış dergisi web uygulamaları için de geçerlidir.

### <a name="question-can-i-prevent-visual-studio-from-auto-committing-a-new-project"></a>Soru: Visual Studio otomatik-yeni bir proje uygulamadan gelen önleyebilirim?

Yanıt: Evet. Otomatik Tamamlama devre dışı bırakmak için Git **ayarları** sayfasındaki **Takım Gezgini**seçin **Git** > **genel ayarları**, Temizle Etiketli seçeneği **değişiklikleri birleştirme sonra varsayılan olarak**seçeneğini belirleyip **güncelleştirme**.

## <a name="step-1-3-create-the-virtual-environment-and-exclude-it-from-source-control"></a>1-3. adım: sanal ortam oluşturmak ve kaynak denetiminden çıkarma

Projeniz için kaynak denetimi yapılandırdıktan, proje gerektirir gerekli Flask paketlerini sanal ortamı oluşturabilirsiniz. Daha sonra **Takım Gezgini** kaynak denetiminden ortam klasörü dışlamak için.

1. İçinde **Çözüm Gezgini**, sağ **Python ortamları** düğümü ve select **sanal ortam Ekle**.

    ![Çözüm Gezgini'nde sanal ortam komut ekleme](media/flask/step01-add-virtual-environment-command.png)

1. Bir **sanal ortam Ekle** iletişim kutusu görüntülenirse, "Requirements.txt dosyasını bulduk." belirten bir ileti Bu ileti, Visual Studio sanal ortamı yapılandırmak için bu dosyayı kullandığını gösterir.

    ![Sanal ortama Ekle iletişim kutusu requirements.txt iletisi](media/tutorials-common/step01-add-virtual-environment-found-requirements.png)

1. Seçin **oluşturma** Varsayılanları kabul etmek için. (İsterseniz, sanal ortamı adını da alt klasörünü adını yalnızca Değişeni değiştirebileceğiniz ancak `env` standart bir kuraldır.)

1. Visual Studio indirmeleri ve paketleri, yani Flask ve bağımlılıklarını için 100'den klasörlerdeki binlerce dosyalarla ilgili genişletme yükler yönetici ayrıcalıkları onay istenirse, sonra birkaç dakika bekleyin. Visual Studio'da ilerleme durumunu görebilirsiniz **çıkış** penceresi. Beklerken, soru bölümlerde ponder. Üzerinde Flask'ın bağımlılıkları açıklamasını görebilirsiniz [Flask yükleme](http://flask.pocoo.org/docs/1.0/installation/#installation) sayfa (flask.pcocoo.org).

1. Visual Studio Git denetimleri (durum çubuğunda), değişiklikleri göstergeyi seçin (gösterir "99\*") açan **değişiklikleri** sayfasındaki **Takım Gezgini**.

    Sanal ortam oluşturma duruma değişiklikleri yüzlerce ancak siz (veya herhangi başka proje kopyalama) ortamından her zaman yeniden oluşturabilirsiniz hiçbirini dahil kaynak denetiminde gerekmez `requirements.txt`.

    Sanal ortam dışlamak için sağ `env` klasörü ve select **bu yerel öğeleri Yoksay**.

    ![Kaynak denetimi değişikliklerinin sanal bir ortamda yoksayılıyor](media/flask/step01-ignore-local-items.png)

1. Sanal ortam çıkardıktan sonra yalnızca kalan proje dosyasına değişir ve `.gitignore`. `.gitignore` Dosya sanal ortam klasörü için eklenen bir giriş içerir. Bir sonraki fark görmek için bu dosyaya çift tıklayın

1. Bir kaydetme iletisi girin ve **tamamlama tüm** düğmesine ve ardından isterseniz uzak deponuza işlemeleri anında iletme.

### <a name="question-why-do-i-want-to-create-a-virtual-environment"></a>Soru: Neden t sanal bir ortam oluşturmak istiyor musunuz?

Yanıt: Bir sanal ortam, uygulamanızın tam bağımlılıkları yalıtmak için harika bir yoludur. Bu tür yalıtım genel bir Python ortamı içindeki çakışmaları ortadan kaldırır ve test etme ve işbirliği yardımları. Bir uygulama geliştirirken zaman içinde çok yararlı Python paketlerini, herhangi bir sayı neredeyse şaşmaz biçimde getirin. Paket bir projeye özgü sanal ortamda tutarak, projenin kolayca güncelleştirebilirsiniz `requirements.txt` kaynak denetiminde içerilen bu ortamı tanımlayan dosya. Proje, derleme sunucuları, dağıtım sunucuları ve diğer geliştirme bilgisayarlar dahil olmak üzere diğer bilgisayarlara, kopyalanan yalnızca kullanarak ortamını yeniden daha kolaydır `requirements.txt` (olduğu neden ortamı kaynak denetiminde olması gerekmez). Daha fazla bilgi için bkz: [sanal ortamlar kullanarak](selecting-a-python-environment-for-a-project.md#using-virtual-environments).

### <a name="question-how-do-i-remove-a-virtual-environment-thats-already-committed-to-source-control"></a>Soru: Nasıl zaten kaynak denetimi için kaydedilmiş bir sanal ortam kaldırabilirim?

Yanıt: İlk olarak, düzenleme, `.gitignore` klasörü dışlamak için dosya: açıklamayı içeren sonunda bölüm Bul `# Python Tools for Visual Studio (PTVS)` ve sanal ortam klasörü için yeni bir satır ekleyin `/BasicProject/env`. (Visual Studio dosyasında göstermiyor çünkü **Çözüm Gezgini**, kullanarak doğrudan açmadan **dosya** > **açmak**  >   **Dosya** menü komutu. Dosyasını da açabilirsiniz **Takım Gezgini**: üzerinde **ayarları** sayfasında, **deposu ayarları**gidin **öznitelikleri dosyaları&yoksay** bölümünde ve ardından **Düzenle** bağlantısına `.gitignore`.)

İkinci olarak, bir komut penceresi açın, gibi klasöre gidin `BasicProject` sanal ortam klasörü gibi içeren `env`, çalıştırıp `git rm -r env`. Ardından bu komut satırından değişiklikleri (`git commit -m 'Remove venv'`) veya gelen **değişiklikleri** sayfasında **Takım Gezgini**.

## <a name="step-1-4-examine-the-boilerplate-code"></a>1-4. adım: Demirbaş kod inceleyin

1. Proje oluşturma işlemi tamamlandıktan sonra çözümü görmek ve proje **Çözüm Gezgini**, projenin yalnızca iki dosya içerir burada `app.py` ve `requirements.txt`:

    ![Çözüm Gezgini'nde boş Flask proje dosyaları](media/flask/step01-blank-flask-project-in-solution-explorer.png)

1. Daha önce belirtildiği gibi `requirements.txt` dosyasını Flask paket bağımlılığı belirtir. Bu dosyasının varlığı, ilk proje oluşturulurken sanal bir ortam oluşturmak için davet ' dir.

1. Tek `app.py` dosyası üç bölümden içerir. İlk bir `import` Flask, bir örneğini oluşturmak için bildirimi `Flask` değişkenine atanan sınıfı `app`ve ardından atama bir `wsgi_app` (bir web ana bilgisayara dağıtırken yararlıdır, ancak şu anda kullanılmayan) değişkeni:

    ```python
    from flask import Flask
    app = Flask(__name__)

    # Make the WSGI interface available at the top level so wfastcgi can get it.
    wsgi_app = app.wsgi_app
    ```

1. Dosya sonunda ikinci bölümü, belirli bir ana bilgisayarı ve bağlantı noktası değerlerini ortam değişkenlerini (localhost:5555 için varsayılan değer olarak) alınan Flask geliştirme sunucusu başlar, isteğe bağlı kodunun bitidir:

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

1. Üçüncü bir URL için bir işlev atar kodunun kısa bir bit yönlendirmek, işlevi URL tarafından tanımlanan kaynağa sağlar anlamına olur. Flask'ın kullanarak yolları tanımlayın `@app.route` olmayan site kök göreli URL, bağımsız değişken oluşturma öğesi. Kod içinde gördüğünüz işlevi burada işlemek için bir tarayıcı için yeterli olan yalnızca bir metin dizesi döndürür. İzleyeceğiniz adımlarda daha zengin HTML sayfaları oluşturmak.

    ```python
    @app.route('/')
    def hello():
        """Renders a sample page."""
        return "Hello World!"
    ```

### <a name="question-what-is-the-purpose-of-the-name-argument-to-the-flask-class"></a>Soru: amacı nedir __adı__ Flask sınıfı bağımsız değişkeni?

Yanıt: Bağımsız değişkeni uygulamanın modülü veya paket adıdır ve Flask şablonları, statik dosyalar ve uygulamaya ait diğer kaynaklar için bulacağınız. Tek bir modülünde yer alan uygulamalar için `__name__` her zaman doğru değeridir. Ayrıca, hata ayıklama bilgisi gerektiren uzantılar için de önemlidir. Daha fazla bilgi ve ek bağımsız değişkenler için bkz: [Flask sınıfı belgelerine](http://flask.pocoo.org/docs/1.0/api/#flask.Flask) (flask.pocoo.org).

### <a name="question-can-a-function-have-more-than-one-route-decorator"></a>Soru: bir işlev birden fazla yol oluşturma öğesi olabilir mi?

Yanıt: Evet, birden çok yol aynı işlevi hizmet veriyorsa, istediğiniz sayıda dekoratörler kullanabilirsiniz. Örneğin, kullanılacak `hello` işlevi her ikisi için de "/" ve "/ hello", aşağıdaki kodu kullanın:

```python
@app.route('/')
@app.route('/hello')
def hello():
    """Renders a sample page."""
    return "Hello World!"
```

<a name="qa-url-variables"></a>

### <a name="question-how-does-flask-work-with-variable-url-routes-and-query-parameters"></a>Soru: değişken URL rotaları ve sorgu parametreleri Flask nasıl çalışır?

Yanıt: herhangi bir değişkeni ile işaretler bir yolu, `<variable_name>`, ve Flask adlandırılmış bir bağımsız değişken kullanma işlevi değişkeni geçirir. Değişkeni URL yolunu veya bir sorgu parametresinde bir parçası olabilir. Örneğin, bir rota biçiminde `'/hello/<name>` adlı bir dize bağımsız değişkeni oluşturur `name` işlevi ve kullanarak `?message=<msg>` için verilen değer rotada ayrıştırır "message =" sorgu parametresi ve işlev olarak geçirir `msg`:

```python
@app.route('/hello/<name>?message=<msg>')
def hello(name, msg):
    return "Hello " + name + "! Message is " + msg + "."
```

Türünü değiştirmek için değişken ile önek `int`, `float`, `path` (hangi kabul klasör adları ayırmak için eğik çizgi), ve `uuid`. Ayrıntılar için bkz [değişken kuralları](http://flask.pocoo.org/docs/1.0/quickstart/#variable-rules) Flask belgelerinde.

Sorgu parametreleri aracılığıyla da `request.args` özelliği, özellikle ile `request.args.get` yöntemi. Daha fazla bilgi için bkz: [istek nesnesi](http://flask.pocoo.org/docs/1.0/quickstart/#the-request-object) Flask belgelerinde.

### <a name="question-can-visual-studio-generate-a-requirementstxt-file-from-a-virtual-environment-after-i-install-other-packages"></a>Soru: diğer paketleri yüklendikten sonra Visual Studio requirements.txt dosyasını sanal ortamdan oluşturabilir miyim?

Yanıt: Evet. Genişletme **Python ortamları** düğümü, sanal ortamınıza sağ tıklatın ve seçin **requirements.txt Oluştur** komutu. Bu komut düzenli kullanmak üzere kendi iyi ortamı değiştirin ve yürütme değişiklikler `requirements.txt` yanı sıra bu ortamda bağımlı herhangi bir kod değişiklikleri kaynak denetimi. Derleme sunucusundaki sürekli tümleştirme ayarladıysanız, ortamı değiştirmek her dosya ve değişiklikleri oluşturmanız gerekir.

## <a name="step-1-5-run-the-project"></a>1-5. adım: Proje çalıştırın

1. Visual Studio'da seçin **hata ayıklama** > **hata ayıklamayı Başlat** (F5) veya **Web sunucusu** (farklılık may gördüğünüz tarayıcısı) araç çubuğunda:

    ![Visual Studio'da Web sunucusu Çalıştır araç çubuğu düğmesi](media/tutorials-common/run-web-server-toolbar-button.png)

1. Her iki komut bir rastgele bağlantı noktası numarası bağlantı noktası ortam değişkenine atar ve ardından çalıştıran `python app.py`. Kod içinde Flask'ın geliştirme sunucusu bu bağlantı noktasını kullanarak uygulamayı başlatır. Visual Studio "hata ayıklayıcısını başlatmak üzere başarısız" içeren bir ileti sağ tıklayın, herhangi bir başlatma dosyası sahip hakkında diyorsa `app.py` içinde **Çözüm Gezgini** seçip **başlangıç dosyası olarak ayarlamak**.

1. Sunucusu başlatıldığında görüntüleyen sunucu günlüğü'nü açın bir konsol penceresine bakın. Visual Studio sonra bir tarayıcı otomatik olarak açılır `http://localhost:<port>`, burada tarafından işlenen ileti görürsünüz `hello` işlevi:

    ![Flask proje varsayılan görünümü](media/flask/step01-first-run-success.png)

1. İşiniz bittiğinde, konsol penceresini kapatarak ya da kullanarak sunucu stop **hata ayıklama** > **durdurma hata ayıklama** Visual Studio'da komutu.

### <a name="question-whats-the-difference-between-using-the-debug-menu-commands-and-the-server-commands-on-the-projects-python-submenu"></a>Soru: Hata ayıklama menü komutları ve sunucu komutları projenin Python menüdeki kullanma arasındaki fark nedir?

Yanıt: ek olarak **hata ayıklama** menü komutları ve araç çubuğu düğmeleri, sunucu kullanarak başlatabilirsiniz **Python** > **Server'i** veya **Python** > **Run hata ayıklama sunucusu** projenin bağlam menüsündeki komutlar. Her iki komutları çalıştıran sunucunun yerel URL'sini (localhost:port) bkz bir konsol penceresi açın. Ancak, bir tarayıcı bu URL'yi ile el ile açmanız gerekir ve hata ayıklama server çalıştıran otomatik olarak Visual Studio hata ayıklayıcısı başlamaz. Kullanmak istiyorsanız, bir hata ayıklayıcısı çalışan işlemi daha sonra iliştirebilirsiniz **hata ayıklama** > **ekleme işlemi için** komutu.

## <a name="next-steps"></a>Sonraki adımlar

Bu noktada, temel Flask proje başlangıç kodunu ve aynı dosyada sayfa kodunu içerir. Bu iki sorunları ayırmak ve şablonları kullanarak HTML ve verileri de ayırmak için en iyisidir.

> [!div class="nextstepaction"]
> [Görünümleri ve sayfa şablonları ile Flask uygulaması oluşturma](learn-flask-visual-studio-step-02-create-app.md)

## <a name="going-deeper"></a>Daha derin gitme

- [Flask Hızlı Başlangıç](http://flask.pocoo.org/docs/1.0/quickstart/) (flask.pocoo.org)
- Öğretici kaynak kodu github'da: [Microsoft/python-örnek-vs-learning-flask](https://github.com/Microsoft/python-sample-vs-learning-flask)
