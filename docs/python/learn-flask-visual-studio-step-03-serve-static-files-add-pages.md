---
title: Öğretici - Visual Studio, adım 3 Flask öğrenin
description: Visual Studio projeleri, özellikle statik dosyaları işleme, sayfaları için uygulama ekleme ve şablon devralma kullanma gösteren bağlamında Flask temel bir kılavuz
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
ms.openlocfilehash: 384905370a16cbdcd9b4c9165f079bcbdf71a250
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752511"
---
# <a name="tutorial-step-3-serve-static-files-add-pages-and-use-template-inheritance"></a>Öğreticisi 3. adım: hizmet statik dosyalar, sayfa ekleyin ve şablon devralma kullanın

**Önceki adımda: [görünümlerle Flask uygulaması oluşturma ve sayfa şablonları](learn-flask-visual-studio-step-02-create-app.md)**

Bu öğreticinin önceki adımlarda kendi içinde bulunan HTML tek bir sayfayla en az bir Flask uygulaması oluşturma öğrendiniz. Modern web uygulamaları, ancak birçok sayfaları genellikle oluşurlar ve olun tutarlı stil ve davranışı sağlamak için CSS ve JavaScript dosyaları gibi paylaşılan kaynakları.

Bu adımda, bilgi nasıl yapılır:

> [!div class="checklist"]
> - Farklı türlerde uygun Demirbaş kod ile hızlı bir şekilde yeni dosyalar için Visual Studio öğe şablonları kullanın (adım 3 - 1)
> - (Adım 3-2, isteğe bağlı) kodundan statik dosyaları işleme
> - Bir uygulamaya (adım 3-3) ek sayfaları ekleme
> - (3-4. adım) sayfaları arasında kullanılan bir üstbilgi ve gezinti çubuğu oluşturmak için şablon devralma kullanın

## <a name="step-3-1-become-familiar-with-item-templates"></a>3 1. adım: öğe şablonları ile aşina

Flask Uygulama geliştirirken, genellikle çok daha fazla Python, HTML, CSS ve JavaScript dosyaları ekleyin. Her dosya türü için (sair dosyaların `web.config` dağıtım için gereken), Visual Studio'nun sağladığı uygun [öğe şablonlarını](python-item-templates.md) başlamanıza yardımcı olmak için.

Kullanılabilir şablonların görmek için Git **Çözüm Gezgini**, select öğesi oluşturmak istediğiniz klasörü sağ tıklatın **Ekle** > **yeni öğe**:

![Visual Studio'da yeni öğe iletişim ekleyin](media/flask/step03-add-new-item-dialog.png)

Bir şablonu kullanmak için istediğiniz şablonu seçin, dosya için bir ad belirtin ve seçin **Tamam**. Bu şekilde otomatik olarak bir öğe ekleme dosyayı Visual Studio projenize ekler ve değişiklikleri kaynak denetimi için işaretler.

### <a name="question-how-does-visual-studio-know-which-item-templates-to-offer"></a>Soru: nasıl Visual Studio hangi öğesi sunmak için şablonlar biliyor?

Yanıt: Visual Studio Proje dosyası (`.pyproj`) Python projesi olarak işaretler proje türü tanımlayıcısı içeriyor. Visual Studio Proje türü için uygun olan öğe şablonları göstermek için bu tür tanımlayıcı kullanır. Bu şekilde, çoğu, aralarında her zaman sıralamak için istemeden türleri proje için Visual Studio öğe şablonları zengin bir dizi sağlayabilir.

## <a name="step-3-2-serve-static-files-from-your-app"></a>3-2. adım: hizmet uygulamanızın statik dosyalar

(Tüm framework kullanarak) Python ile yerleşik bir web uygulamasında Python dosyalarınızı her zaman web ana bilgisayarın sunucusunda çalıştırın ve bir kullanıcının bilgisayarına hiçbir zaman iletilmez. Ana bilgisayar sunucusu yalnızca olarak sunar diğer dosyaları ancak, CSS ve JavaScript gibi tarayıcı tarafından özel olarak kullanıldığından-istenen ne zaman açıktır. Bu tür dosyaları "statik" dosyalar olarak adlandırılır ve Flask bunları otomatik olarak, kod yazmaya gerek sunabilir. HTML dosyaları içinde Örneğin, yalnızca statik dosyalar projede göreli bir yol kullanarak başvurabilirsiniz. Bu adım ilk bölümünde varolan sayfa şablonunuza bir CSS dosyası ekler.

Statik bir dosya koddan yerine getirmeleri için gereken zaman gibi bir API uç nokta uygulaması Flask adlı bir klasör içinde göreli yollar kullanarak dosyaları başvurmak olanak sağlayan kullanışlı bir yöntem sunmakla `static` (içinde proje kök). Bu adımdaki ikinci bölümü, bir basit statik veri dosyası kullanarak bu yöntemini gösterir.

Her iki durumda da, dosyaları altında düzenleyebilirsiniz `static` ancak ister.

### <a name="use-a-static-file-in-a-template"></a>Statik dosya olarak bir şablon kullanın

1. İçinde **Çözüm Gezgini**, Visual Studio projesi "HelloFlask" klasörüne sağ tıklayın, **Ekle** > **yeni klasör**ve klasörüadı`static`.

1. Sağ `static` klasörü ve select **Ekle** > **yeni öğe**. Görüntülenen iletişim kutusunda, "Stil" şablonunu seçin, dosya adı `site.css`seçip **Tamam**. `site.css` Dosya projede görünür ve Düzenleyicisi'nde açılır. Klasör yapısı aşağıdaki görüntüye benzer görünmelidir:

    ![Çözüm Gezgini'nde gösterildiği gibi statik dosya yapısı](media/flask/step03-static-file-structure.png)

1. Değiştir `site.css` aşağıdaki kodla ve dosyayı kaydedin:

    ```css
    .message {
        font-weight: 600;
        color: blue;
    }
    ```

1. Uygulamanın içeriğini değiştirin `templates/index.html` dosya ile değiştirir aşağıdaki kodu `<strong>` ile 2. adımda kullanılan öğe bir `<span>` başvuran `message` stil sınıfı. Bu şekilde stili sınıfını kullanarak öğeyi stil oluşturma çok daha fazla esneklik sağlar.

    ```html
    <html>
        <head>
            <title>{{ title }}</title>
            <link rel="stylesheet" type="text/css" href="/static/site.css" />
        </head>
        <body>
            <span class="message">{{ message }}</span>{{ content }}
        </body>
    </html>
    ```

1. Sonuçları gözlemlemek için projesini çalıştırın. İşiniz bittiğinde uygulamayı durdurun ve kaynak denetim isterseniz, değişiklikleri (açıklandığı gibi [2. adım](learn-flask-visual-studio-step-02-create-app.md#commit-to-source-control)).

### <a name="serve-a-static-file-from-code"></a>Statik bir dosya kodundan hizmet

Flask adlı bir işlev sağlar `serve_static_file` projenin içinde herhangi bir dosyaya başvuruda kodundan çağıran `static` klasör. Aşağıdaki işlem statik veri dosyası döndürür basit bir API uç noktası oluşturur).

1. Henüz yapmadıysanız, oluşturma bir `static` klasörü: içinde **Çözüm Gezgini**, Visual Studio projesi "HelloFlask" klasörüne sağ tıklayın, **Ekle**  >  **Yeni klasör**ve klasör adı `static`.

1. İçinde `static` klasörünü adlı statik bir JSON veri dosyası oluşturma `data.json` (anlamsız örnek verileri olan) aşağıdaki içeriğe sahip:

    ```json
    {
        "01": {
            "note" : "Data is very simple because we're demonstrating only the mechanism."
        }
    }
    ```

1. İçinde `views.py`, statik verileri kullanarak dosya döndürür rota/api/verileri içeren bir işlev eklemek `send_static_file` yöntemi:

    ```python
    @app.route('/api/data')
    def get_data():
      return app.send_static_file('data.json')
    ```

1. Uygulamayı çalıştırın ve statik dosya verdiğini görmek için / api/veri bitiş noktasına gidin. İşiniz bittiğinde uygulamayı durdurun.

### <a name="question-are-there-any-conventions-for-organizing-static-files"></a>Soru: statik dosyaları düzenleme için tüm kuralları var mı?

Yanıt: Diğer CSS, JavaScript ve HTML dosyalarında ekleyebilirsiniz, `static` klasörü ancak istiyor. Statik dosyaları düzenlemek için normal bir şekilde adlı alt klasörler oluşturmaktır `fonts`, `scripts`, ve `content` (için stil sayfaları ve diğer dosyaları).

### <a name="question-how-do-i-handle-url-variables-and-query-parameters-in-an-api"></a>Soru: nasıl ı URL değişkenleri ve bir API Sorgu parametrelerinin işler?

Yanıt: yanıt için 1-4. adımda bkz [Soru: nasıl Flask iş olan değişken URL yol ve sorgu parametreleri?](learn-flask-visual-studio-step-01-project-solution.md#qa-url-variables)

## <a name="step-3-3-add-a-page-to-the-app"></a>3-3. adım: uygulama için bir sayfa ekleyin

Uygulamaya başka bir sayfaya ekleme aşağıdaki anlamına gelir:

- Görünümü tanımlayan bir Python işlevi ekleyin.
- Sayfanın biçimlendirme için bir şablon ekleyin.
- Django projenin için gerekli yönlendirme eklemek `urls.py` dosya.

Aşağıdaki adımları "HelloFlask" proje ve giriş sayfasından bu sayfaya bağlantılar bir "About" sayfasında ekleyin:

1. İçinde **Çözüm Gezgini**, sağ `templates` klasöründe seçin **Ekle** > **yeni öğe**, "HTML sayfası" öğe şablonu seçin, dosya adı `about.html`seçip **Tamam**.

    > [!Tip]
    > Varsa **yeni öğe** komut çubuğunda görünmüyor **Ekle** menüsünde, böylece Visual Studio hata ayıklama modunu çıkar uygulama durduruldu emin olun.

1. Değiştir `about.html` (, yerine giriş sayfasına açık bağlantı basit bir gezinti çubuğu 3-4. adımda) aşağıdaki biçimlendirme ile:

    ```html
    <html>
        <head>
            <title>{{ title }}</title>
            <link rel="stylesheet" type="text/css" href="/static/site.css" />
        </head>
        <body>
            <div><a href="home">Home</a></div>
            {{ content }}
        </body>
    </html>
    ```

1. Uygulamanın açmak `views.py` dosya ve adlı bir işlev eklemek `about` şablonu kullanır:

    ```python
    @app.route('/about')
    def about():
        return render_template(
            "about.html",
            title = "About HelloFlask",
            content = "Example app page for Flask.")
    ```

1. Açık `templates/index.html` dosya ve aşağıdakileri ekleyin hemen içinde satır `<body>` hakkında sayfasına bağlantı kurmak için öğesi (yeniden, bu bağlantıyı adım 3-4 gezinti çubuğunda değiştirin):

    ```html
    <div><a href="about">About</a></div>
    ```

1. Kullanarak tüm dosyaları kaydetmek **dosya** > **Tümünü Kaydet** menü komutu, veya yalnızca basın veya Ctrl + Shift + S. (Visual Studio projesi çalıştırmaya dosyaları otomatik olarak kaydeder gibi teknik olarak, bu adım gerekli değildir. Bununla birlikte, hakkında bilgi edinmek için iyi bir komutu kadar!)

1. Sonuçları gözlemlemek ve sayfaları arasında gezinmeyi denetleme projeyi çalıştırın. İşiniz bittiğinde uygulamayı durdurun.

### <a name="question-does-the-name-of-a-page-function-matter-to-flask"></a>Soru: sayfa işlevin adını Flask için önemli mi?

Yanıt: Hayır, çünkü `@app.route` Flask çağıran bir yanıt oluşturmak için işlev URL'leri belirler oluşturma öğesi. Geliştiriciler genellikle işlevi rota adıyla, ancak bu tür eşleşen gerekli değildir.

## <a name="step-3-4-use-template-inheritance-to-create-a-header-and-nav-bar"></a>Adım 3-4: bir üstbilgi ve gezinti çubuğu oluşturmak için şablon devralma kullanın

Açık Gezinti bağlantıları her sayfada sahip olmak yerine modern web uygulamaları genellikle bir marka başlığı ve en önemli sayfa bağlantılar, açılır menüler ve benzeri sağlayan gezinti çubuğu kullanın. Üstbilgi ve gezinme çubuğu tüm sayfalardaki aynı olduğundan emin olmak için ancak, her sayfası şablonu aynı kodu tekrar etmek istemediğiniz. Bunun yerine, tek bir yerde, tüm sayfaların ortak bölümleri tanımlamak istersiniz.

Flask'ın şablon sistem (varsayılan olarak Jinja) birden çok şablon tarafından belirli öğeleri yeniden kullanmak için iki anlamına gelir sağlar: içerir ve devralma.

- *İçeren* sözdizimini kullanarak başvuran şablon belirli bir yerde eklediğiniz diğer sayfa şablonları `{% include <template_path> %}`. Kod yolunda dinamik olarak değiştirmek istiyorsanız bir değişken de kullanabilirsiniz. İçeren bir sayfa gövdesinde genellikle sayfasında belirli bir konumdaki paylaşılan şablonunda çekmek için kullanılır.

- *Devralma* kullanan `{% extends <template_path> %}` başına sayfa şablonunun başvuran şablon sonra bağlı derlemeler paylaşılan bir temel şablonu belirtin. Devralma paylaşılan düzeni, gezinme çubuğu tanımlamak için yaygın olarak kullanılır ve şablonları başvuran yalnızca eklemek veya adlı temel şablonu belirli alanlarında değiştirmek, diğer bir uygulamanın sayfaları için yapıları *blokları*.

Her iki durumda da `<template_path>` uygulamanın göreli olduğunu `templates` klasörü (`../` veya `./` de izin verilir).

Temel bir şablonu betimleyen *blokları* kullanarak `{% block <block_name> %}` ve `{% endblock %}` etiketler. Başvuran bir şablon daha sonra aynı blok ada sahip etiketleri kullanıyorsa blok içeriği, temel şablonu geçersiz.

Aşağıdaki adımlarda, devralma gösterilmektedir:

1. Uygulamasının `templates` klasörü, yeni bir HTML dosyası oluşturun (kullanarak **Ekle** > **yeni öğe** bağlam menüsü veya **Ekle**  >   **HTML sayfası**) olarak adlandırılan `layout.html`ve içeriğini biçimlendirme ile değiştirin. Bu şablon "içerik" adlı bir blok tüm değiştirmek için başvuran sayfa gereksinimi olan içerdiğini görebilirsiniz:

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="utf-8" />
        <title>{{ title }}</title>
        <link rel="stylesheet" type="text/css" href="/static/site.css" />
    </head>

    <body>
        <div class="navbar">
            <a href="/" class="navbar-brand">Hello Flask</a>
            <a href="{{ url_for('home') }}" class="navbar-item">Home</a>
            <a href="{{ url_for('about') }}" class="navbar-item">About</a>
        </div>

        <div class="body-content">
            {% block content %}
            {% endblock %}
            <hr/>
            <footer>
                <p>&copy; 2018</p>
            </footer>
        </div>
    </body>
    </html>
    ```

1. Uygulamanın aşağıdaki stiller ekleme `static/site.css` dosyası (burada esnek tasarım göstermek bu adımları uygulamayı denemeden değil; Bu yalnızca bir ilgi çekici sonuç oluşturmak için stillerdir):

    ```css
    .navbar {
        background-color: lightslategray;
        font-size: 1em;
        font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
        color: white;
        padding: 8px 5px 8px 5px;
    }

    .navbar a {
        text-decoration: none;
        color: inherit;
    }

    .navbar-brand {
        font-size: 1.2em;
        font-weight: 600;
    }

    .navbar-item {
        font-variant: small-caps;
        margin-left: 30px;
    }

    .body-content {
        padding: 5px;
        font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
    ```

1. Değiştirme `templates/index.html` temel şablona bakın ve içerik engellemeyi geçersiz. Devralma kullanarak, bu şablon basit olacağını görebilirsiniz:

    ```html
    {% extends "layout.html" %}
    {% block content %}
    <span class="message">{{ message }}</span>{{ content }}
    {% endblock %}
    ```

1. Değiştirme `templates/about.html` da temel şablona bakın ve içerik bloğuna geçersiz kılmak için:

    ```html
    {% extends "layout.html" %}
    {% block content %}
    {{ content }}
    {% endblock %}
    ```

1. Sonuçları gözlemlemek sunucuya çalıştırın. İşiniz bittiğinde sunucusunu kapatın.

    ![Gezinme çubuğu gösteren çalışan uygulama](media/flask/step03-nav-bar.png)

1. Uygulamaya yapılan önemli değişiklikler, bunun tekrar iyi bir zamandır olmasıdır [kaynak denetimi, değişiklikleri](learn-django-in-visual-studio-step-02-create-an-app.md#commit-to-source-control).

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Tam Flask Web projesi şablonu kullanın](learn-flask-visual-studio-step-04-full-flask-project-template.md)

## <a name="going-deeper"></a>Daha derin gitme

- Daha fazla yeteneklerini denetim akışı gibi Jinja şablonları için bkz: [Jinja şablonu Tasarımcısı belgelerine](http://jinja.pocoo.org/docs/2.10/templates) (jinja.pocoo.org)
- Kullanımıyla ilgili ayrıntılar için `url_for`, bkz: [url_for](http://flask.pocoo.org/docs/1.0/api/?highlight=url_for#flask.url_for) Flask uygulama nesnesi belgeleri (flask.pocoo.org) içinde
- Öğretici kaynak kodu github'da: [Microsoft/python-örnek-vs-learning-flask](https://github.com/Microsoft/python-sample-vs-learning-flask)