---
title: Öğretici - Visual Studio, 2. adım Flask öğrenin
description: Visual Studio projeleri, bir uygulama oluşturma ve görünümler ve şablonlar kullanarak özellikle adımları bağlamında Flask temel bir kılavuz.
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
ms.openlocfilehash: 9aeba681e1a4ab7bae77197d8af10a90f49a40d0
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752512"
---
# <a name="tutorial-step-2-create-a-flask-app-with-views-and-page-templates"></a>Öğreticisi 2. adım: görünümlerle Flask uygulaması oluşturma ve sayfa şablonları

**Önceki adımda: [Visual Studio Proje ve çözüm oluşturma](learn-flask-visual-studio-step-01-project-solution.md)**

Bu öğreticinin 1 adımından sahip bir bir sayfa ve tek bir dosyada tüm kodla Flask uygulamasıdır. Gelecekteki geliştirme için izin vermek için kodu yeniden düzenleyin ve sayfa şablonları için bir yapı oluşturmak en iyisidir. Özellikle, başlangıç kodu gibi diğer bölümlerinden kod uygulamanın görünümler için ayırmak istediğiniz.

Bu adımda, daha fazla bilgi nasıl yapılır:

> [!div class="checklist"]
> - Görünümleri başlatma kodundan ayırmak için uygulamanın kodu yeniden düzenleyin (Adım 2 - 1)
> - Bir sayfa şablonu (Adım 2-2) kullanarak görünüm işlemek

## <a name="step-2-1-refactor-the-project-to-support-further-development"></a>2-1. adım: daha fazla geliştirme desteği için projeyi yeniden Düzenle

"Boş Flask Web projesi" şablonu tarafından oluşturulan kodda tek bir sahip `app.py` tek bir görünüm yanında başlatma kodunu içeren dosya. Daha fazla geliştirme, bir uygulamanın birden çok görünümler ve şablonlar ile izin vermek için bu sorunları ayırmak en iyisidir.

1. Proje klasörünüzdeki adlı bir uygulama klasörü oluşturun `HelloFlask` ('nde projeye sağ **Çözüm Gezgini** seçip **Ekle** > **yeni klasör** .)

1. İçinde `HelloFlask` klasör adında bir dosya oluşturun `__init.py__` oluşturan aşağıdaki içeriğe sahip `Flask` örneği ve uygulamanın görünümler (sonraki adımda oluşturulan) yükler:

    ```python
    from flask import Flask
    app = Flask(__name__)

    import HelloFlask.views
    ```

1. İçinde `HelloFlask` klasör adında bir dosya oluşturun `views.py` aşağıdaki içeriğe sahip. Adı `views.py` önemlidir, çünkü kullandığınız `import HelloFlask.views` içinde `__init__.py`; adları eşleşmiyorsa çalışma zamanında bir hata görürsünüz.

    ```python
    from flask import Flask
    from HelloFlask import app

    @app.route('/')
    @app.route('/home')
    def home():
        return "Hello Flask!"
    ```

    Rotaya ve işlevi yeniden adlandırma yanı sıra `home`, bu kod app.py sayfa işleme koddan içerir ve içeri aktarır `app` içinde bildirilen nesne `__init__.py`.

1. Bir alt klasör oluşturun `HelloFlask` adlı `templates`, hangi kalan boş şu an için.

1. Projenin kök klasöründe, yeniden adlandırın `app.py` için `runserver.py`ve aşağıdaki kodu eşleşen içeriği yapın:

    ```python
    import os
    from HelloFlask import app    # Imports the code from HelloFlask/__init__.py

    if __name__ == '__main__':
        HOST = os.environ.get('SERVER_HOST', 'localhost')

        try:
            PORT = int(os.environ.get('SERVER_PORT', '5555'))
        except ValueError:
            PORT = 5555

        app.run(HOST, PORT)
    ```
1. Proje yapısı aşağıdaki görüntü gibi görünmelidir:

    ![Kodu yeniden düzenleme sonra proje yapısı](media/flask/step02-project-structure.png)

1. Seçin **hata ayıklama** > **hata ayıklamayı Başlat** (F5) veya **Web sunucusu** (farklılık may gördüğünüz tarayıcısı) araç çubuğunda uygulamayı başlatın ve bir tarayıcı açın. Her ikisi de deneyin / ve/ev URL rotaları.

1. Ayrıca, kodun çeşitli bölümlerine kesme noktalarını ayarlayın ve başlatma sırası izlemek için uygulamayı yeniden başlatın. Örneğin, bir kesme noktası'nın ilk satırlarının ayarlamak `runserver.py` ve `HelloFlask\__init__.py`ve `return "Hello Flask!"` satırından `views.py`. Uygulamayı yeniden başlatın (**hata ayıklama** > **yeniden**, Ctrl + F5'e ya da aşağıda gösterilen araç çubuğu düğmesi) ve kod (F10) adımını veya F5 kullanarak her kesme çalıştırın.

    ![Hata ayıklama araç çubuğunda Visual Studio'yu yeniden başlatın](media/debugging-restart-toolbar-button.png)

1. İşiniz bittiğinde uygulamayı durdurun.

### <a name="commit-to-source-control"></a>Kaynak denetimi Yürüt

Kodunuzu değişiklik yaptınız ve bunları başarılı bir şekilde test olduğundan, gözden geçirmek ve kaynak denetimi değişikliklerinizi uygulamak için çok fazla zaman sunulmuştur. Bu öğreticide sonraki adımlarda kaynak denetimine yeniden kaydetmek için uygun saati anımsatmak ve geri bu bölümüne bakın.

1. Gider değişiklikleri düğmesi (aşağıda yuvarlak içine alınmıştır) Visual Studio alt boyunca seçin **Takım Gezgini**.

    ![Visual Studio durum çubuğundaki Kaynak Denetim değişiklikleri düğmesi](media/flask/step02-source-control-changes-button.png)

1. İçinde **Takım Gezgini**, "Yeniden düzenleme kod" gibi bir yürütme ileti girin ve **tamamlama tüm**. Yürütme tamamlandığında, bir ileti görür "yürütme <hash> yerel olarak oluşturulmuş. Sunucuyla yaptığınız değişiklikleri paylaşmak için eşitleme." Değişiklikleri uzak deponuza iletin isteyip istemediğinizi seçin **eşitleme**seçeneğini belirleyip **itme** altında **giden işlemeleri**. Ayrıca, uzaktan Ftp'den önce birden çok yerel işlemeleri birikebilir.

    ![Takım Gezgini'nde uzak yürütmelerini gönderdiğiniz](media/flask/step02-source-control-push-to-remote.png)

### <a name="question-how-frequently-should-one-commit-to-source-control"></a>Soru: ne sıklıkta bir kaynak denetimi yürütme?

Yanıt: kaynak denetimi değişiklikleri yürütmeyi bir kayıt değişiklik günlüğü ve noktası oluşturur için gerekirse depo geri dönebilirsiniz. Her yürütme Ayrıca belirli değişikliklerinde incelenebilir. Git işlemeleri ucuz olduğundan, çok sayıda tek bir işleme dönüşene birikmesini üzere daha işlemeleri sık kullanılan daha iyidir. Açıkçası, tek tek dosyalar her küçük değişikliği kaydetmek için gerek yoktur. Genellikle, bir tamamlama bir özellik eklerken bu adımda yapılan veya bazı kodu yeniden düzenleme yapılan gibi bir yapı değiştirme olun. Ayrıca başkalarıyla ekibiniz ayrıntı için en iyi herkes için iş yürütme sayısı iade edin.

Ne sıklıkta yürüttükten ve ne sıklıkta uzak bir depo yürütmelerini gönderdiğiniz olan iki farklı sorunları. Uzak depoya göndermeden önce yerel depoda birden çok işlemeleri birikebilir. Yeniden, ne sıklıkta yürüttükten nasıl ekibinizin depo yönetmek istiyor üzerinde bağlıdır.

## <a name="step-2-2-use-a-template-to-render-a-page"></a>2-2. adım: bir sayfayı işlemek için bir şablon kullanın

`home` , O ana kadarki sahip işlevi `views.py` fazlası sayfası için bir düz metin HTTP yanıt oluşturur. Bununla birlikte, çoğu gerçek web sayfaları, genellikle canlı verileri birleştirmek zengin HTML sayfaları ile yanıtlayın. Aslında, bir işlev kullanarak görünüm tanımlamak için birincil içerik dinamik olarak oluşturmak için nedenidir.

Görünüm için dönüş değeri bir dize olduğundan, dinamik içeriği kullanarak bir dizede gibi herhangi bir HTML oluşturabilirsiniz. Ancak, verileri biçimlendirme ayırmak en iyi olduğundan, şablonda işaretleme yerleştirin ve kodda verileri tutmak daha iyi değildir.

1. Yeni başlayanlar Düzenle `views.py` bazı dinamik içerik sayfasıyla satır içi HTML kullanımları aşağıdaki kod içeriyor:

    ```python
    from datetime import datetime
    from flask import render_template
    from HelloFlask import app

    @app.route('/')
    @app.route('/home')
    def home():
        now = datetime.now()
        formatted_now = now.strftime("%A, %d %B, %Y at %X")

        html_content = "<html><head><title>Hello Flask</title></head><body>"
        html_content += "<strong>Hello Flask!</strong> on " + formatted_now
        html_content += "</body></html>"

        return html_content
    ```

1. Uygulamayı çalıştırın ve birkaç kez sayfayı yenileyin tarih/saat güncelleştirilir görmek için. İşiniz bittiğinde uygulamayı durdurun.

1. Bir şablon kullanmak üzere sayfa işleme dönüştürmek için adlı bir dosya oluşturun `index.html` içinde `templates` klasöründe aşağıdaki içeriğe sahip nerede `{{ content }}` bir yer tutucu ya da değiştirme belirteci (olarak da adlandırılan bir *Şablon değişkeni*) bir değer kodda sağladığınız:

    ```html
    <html>
        <head><title>Hello Flask</title></head>

        <body>
            {{ content }}
        </body>
    </html>
    ```

1. Değiştirme `home` kullanmak için işlevi `render_template` yük şablon ve yapılır "içerik" için bir değer sağlamanız için yer tutucu adıyla eşleşen adlandırılmış bir bağımsız değişken kullanma. Flask otomatik olarak arar şablonlarında `templates` oath şablona göre bu klasörü olabilmesi klasörü:

    ```python
    def home():
        now = datetime.now()
        formatted_now = now.strftime("%A, %d %B, %Y at %X")

        return render_template(
            "index.html",
            content = "<strong>Hello, Flask!</strong> on " + formatted_now)
    ```

1. Bkz: uygulama çalıştırma sonuçları ve görüntülendiğini satıriçi HTML olarak `content` değil değerini işlemek *olarak* HTML şablon motoru olduğundan (Jinja) otomatik olarak HTML içeriğini çıkışları. Kaçış otomatik yanlışlıkla güvenlik açıklarına ekleme saldırıları önlemek: geliştiriciler genellikle giriş sayfadan toplayın ve şablon yer tutucu aracılığıyla başka bir değer olarak kullanın. Kaçış Ayrıca, yeniden HTML kod dışında tutmak en iyi olduğunu anımsatıcısı görevi görür.

    Buna göre gözden `templates\index.html` her biçimlendirmesi içinde veri parçası için ayrı yer tutucuları içeren için:

    ```html
    <html>
        <head>
            <title>{{ title }}</title>
        </head>
        <body>
            <strong>{{ message }}</strong>{{ content }}
        </body>
    </html>
    ```

    Ardından güncelleştirme `home` işlevi için yer tutucu değerlerini sağlamak için:

    ```python
    def home():
        now = datetime.now()
        formatted_now = now.strftime("%A, %d %B, %Y at %X")

        return render_template(
            "index.html",
            title = "Hello Flask",
            message = "Hello, Flask!",
            content = " on " + formatted_now)
    ```

1. Yeniden düzgün işlenmiş çıkış görmek için uygulamayı çalıştırın.

    ![Şablon kullanılarak çalışan uygulama](media/flask/step02-result.png)

1. Kaynak Denetim ve uzak deponuza isterseniz, altında açıklandığı gibi güncelleştirmek için değişiklikleri [adım 2-1](#commit-to-source-control).

### <a name="question-do-page-templates-have-to-be-in-a-separate-file"></a>Soru: sayfa şablonları ayrı bir dosyaya olması gerekir mi?

Yanıt: şablonları genellikle ayrı HTML dosyalarında saklanır karşın, aynı zamanda bir satır içi şablon kullanabilirsiniz. Ayrı bir dosya kullanarak, ancak, biçimlendirme ve kodun arasında temiz bir ayrım korumak için önerilir.

### <a name="question-must-templates-use-the-html-file-extension"></a>Soru: şablonları .html dosya uzantısı kullanmalısınız?

Yanıt: `.html` her zaman için ilk bağımsız değişken dosyasında tam göreli yolunu tanımlamak için sayfa şablonu dosyalarının uzantısı tamamen isteğe bağlı `render_template` işlevi. Ancak, Visual Studio (ve diğer düzenleyicileri) genellikle ile kod tamamlama ve sözdizimi coloration gibi özellikleri size `.html` şablonları sayfasında olgu ağır dosyaları olmayan kesinlikle HTML.

Aslında, Django projeyle çalışırken, Visual Studio otomatik olarak düzenlediğiniz HTML dosyası gerçekte bir Django şablonu olduğunda algılar ve bazı otomatik tamamlama özellikleri sağlar. Örneğin, başlattığınızda bir Django sayfa şablonu yorum yazarak `{#`, Visual Studio otomatik olarak size kapanış `#}` karakter. **Açıklama Seçimi** ve **açıklamadan çıkarın seçimi** komutları (üzerinde **Düzenle** > **Gelişmiş** menü ve araç çubuğundaki) Ayrıca şablonu açıklamaları yerine HTML açıklamaları kullanın.

### <a name="question-when-i-run-the-project-i-see-an-error-that-the-template-cannot-be-found-whats-wrong"></a>Soru: Proje çalıştırdığınızda, şablonu bulunamıyor hatayla görüyorum. Ne oldu?

Yanıt: şablonu bulunamıyor hatalar görürseniz, Django projenin için uygulama eklediğinizden emin olun `settings.py` içinde `INSTALLED_APPS` listesi. Bu girişi uygulamanın içinde aramak için Django bilemezsiniz `templates` klasör.

### <a name="question-can-templates-be-organized-into-further-subfolders"></a>Soru: şablonları daha fazla alt klasörler halinde düzenlenebilir?

Yanıt: Evet, alt klasörler ve kullanabileceğiniz göreli yolu altında ardından `templates` çağrılarında `render_template`. Bunun yapılması, ad alanları şablonlarınızı için etkili bir şekilde oluşturmak için harika bir yoludur.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Statik dosyaları işleme, sayfa ekleyin ve şablon devralma kullanın](learn-flask-visual-studio-step-03-serve-static-files-add-pages.md)

## <a name="going-deeper"></a>Daha derin gitme

- [Flask hızlı başlangıç şablonlarını oluşturma -](http://flask.pocoo.org/docs/1.0/quickstart/#rendering-templates) (flask.pocoo.org)
- Öğretici kaynak kodu github'da: [Microsoft/python-örnek-vs-learning-flask](https://github.com/Microsoft/python-sample-vs-learning-flask)