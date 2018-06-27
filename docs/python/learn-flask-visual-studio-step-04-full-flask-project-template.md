---
title: Öğretici - Visual Studio, 4. adım Flask öğrenin
description: Visual Studio projeleri, özellikle Flask Web projesi ve Flask/Jade Web projesi şablonları tarafından sağlanan özellikler bağlamında Flask temel bir kılavuz.
ms.date: 05/25/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: c463fdde3c22986211ed7345c3552b288516a4de
ms.sourcegitcommit: 4e605891d0dfb3ab83150c17c074bb98dba29d15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36947513"
---
# <a name="step-4-use-the-full-flask-web-project-template"></a>4. adım: tam Flask Web projesi şablonunu kullanma

**Önceki adımda: [hizmet statik dosyalar, sayfa ekleyin ve şablon devralma kullanın](learn-flask-visual-studio-step-03-serve-static-files-add-pages.md)**

Visual Studio "Boş Flask uygulama projesi" şablonunun üzerine bir uygulama oluşturarak Flask temelleri incelediniz, "Flask Web projesi" şablon tarafından üretilen eksiksiz uygulama kolayca anlayabilirsiniz.

Bu konuda, şimdi adım:

> [!div class="checklist"]
> - "Flask Web projesi" şablonu kullanarak daha eksiksiz bir Flask web uygulaması oluşturma ve proje yapısını inceleyin (adım 4 - 1)
> - Taban sayfası şablondan devralır üç sayfaların oluşan proje şablonu tarafından oluşturulan sayfa şablonları ve görünümler anlamak ve jQuery ve önyükleme (4-2. adım) gibi statik JavaScript kitaplıklarını kullanır
> - (4-3. adım) şablonu tarafından sağlanan URL yönlendirmeyi anlama

Bu makalede, projenin"Flask Web Jinja yerine Jade şablon altyapısını kullanarak" aynı olan bir uygulamayı hazırlayan "Flask/Jade Web projesi" şablonu için de geçerlidir. Ek ayrıntılar bu makalenin sonundaki dahil edilir.

## <a name="step-4-1-create-a-project-from-the-template"></a>4-1. adım: bir proje şablonu oluşturma

1. Visual Studio'da Git **Çözüm Gezgini**, bu öğreticide daha önce oluşturulan "LearningFlask" çözüme sağ tıklayın ve seçin **Ekle** > **yeni proje**. (Alternatif olarak, yeni bir çözüm kullanmak isteyip istemediğinizi seçin **dosya** > **yeni** > **proje** yerine.)

1. Yeni Proje iletişim kutusunda, aramak ve "Flask Web projesi" şablonunu seçin, proje "FlaskWeb" arayın ve seçin **Tamam**.

1. Şablonu yeniden içerdiğinden bir `requirements.txt` dosyası, Visual Studio bu bağımlılıkların yükleneceği sorar. Seçeneği **sanal bir ortama yükleme**hem de **sanal ortam Ekle** iletişim kutusunda **oluşturma** Varsayılanları kabul etmek için.

1. Visual Studio sanal ortamı kurma tamamlandıktan sonra "FlaskWeb" projesini bu projeye sağ tıklayarak Visual Studio çözümü için varsayılan olacak şekilde ayarlayın **Çözüm Gezgini** ve seçerek **olarak ayarlayın Başlangıç projesi**. Gösterilen başlangıç projesi içinde hata ayıklayıcı başlatıldığında ne çalıştırılan kalın.

    ![Başlangıç projesi olarak FlaskWeb proje gösteren Çözüm Gezgini](media/flask/step04-second-project-in-solution-set-as-startup-project.png)

1. Seçin **hata ayıklama** > **hata ayıklamayı Başlat** (F5) veya **Web sunucusu** sunucu çalıştırmak için araç çubuğunda:

    ![Visual Studio'da Web sunucusu Çalıştır araç çubuğu düğmesi](media/flask/run-web-server-toolbar-button.png)

1. Şablon tarafından oluşturulan uygulama hakkında ev ve hangi gezinme çubuğu kullanarak arasında gezinme ilgili kişi, üç sayfaları vardır. Bir veya iki farklı kısımlarını uygulama incelemek için dakika alın. Üzerinden uygulama kimlik doğrulaması yapmak için **oturum** komutu, daha önce oluşturduğunuz süper kullanıcı kimlik bilgilerini kullanın.

    ![Flask Web projesi uygulamasının tam tarayıcı görünümü](media/flask/step04-full-app-desktop-view.png)

1. "Flask Web projesi" şablonu tarafından oluşturulan uygulama önyükleme için mobil form faktörleri düzenler esnek düzenini kullanır. Dar bir görünüme tarayıcıya içerik dikey işler ve gezinme çubuğu menü simgesinde kapatır şekilde yeniden boyutlandırın, bu yanıt verdiğini görmek için:

    ![Flask Web projesi uygulamasının mobil (dar) görünümü](media/flask/step04-full-app-mobile-view.png)

1. Aşağıdaki bölümlerde için çalışan uygulama bırakabilirsiniz.

    Uygulama durdurmak istiyorsanız ve [değişiklikleri kaynak denetimine](learn-flask-visual-studio-step-02-create-app.md#commit-to-source-control), ilk açmak **değişiklikleri** sayfasındaki **Takım Gezgini**, sanal ortama (klasörünü sağ tıklatın büyük olasılıkla `env`) ve seçin **bu yerel öğeleri Yoksay**.

### <a name="examine-what-the-template-creates"></a>Ne şablon oluşturur inceleyin

"Flask Web projesi" şablon yapısı oluşturur. İçeriği, önceki adımlarda oluşturduğunuz için çok benzer. "Flask Web projesi" şablonu daha fazla yapı içerdiği farktır `static` klasörü için esnek tasarım çünkü jQuery ve önyükleme içerir. Şablon, ayrıca bir kişi sayfası ekler. Bu öğreticinin önceki adımları uyguladıysanız, genel olarak, her şeyi şablon bilgi sahibi olmanız gerekir.

- Proje kök dosyaları:
  - `runserver.py`, uygulama geliştirme Server'da çalıştırılacak bir komut dosyası.
  - `requirements.txt` bir bağımlılığı Flask içeren 0.x.
- `FlaskWeb` Klasörü tüm uygulama dosyalarını içerir:
  - `__init.py__` uygulama kodu bir Python modülü olarak işaretler, Flask nesnesi oluşturur ve uygulamanın görünümleri alır.
  - `views.py` sayfaları işlemek için kod içerir.
  - `static` Adlı alt klasörde `content` (CSS dosyaları), `fonts` (yazı tipi dosyaları) ve `scripts` (JavaScript dosyaları).
  - `templates` Klasörünü içeren bir `layout.html` temel şablonu ile birlikte `about.html`, `contact.html`, ve `index.html` belirli sayfalar için her genişletmek `layout.html`.

### <a name="question-is-it-possible-to-share-a-virtual-environment-between-visual-studio-projects"></a>Soru: bir sanal ortam Visual Studio projeleri arasında paylaşmak mümkün mü?

Yanıt: Evet, ancak farklı projelere olası zaman içinde farklı paketler kullanın ve paylaşılan bir sanal ortam kullanan tüm projeleri için tüm paketler bu nedenle içermelidir tanıma ile bunu.

Bununla birlikte, varolan bir sanal ortam kullanmak için aşağıdakileri yapın:

1. Visual Studio'da bağımlılıkları yüklemek isteyip istemediğiniz sorulduğunda seçin **ı bunları kendim yükleyecek** seçeneği.
1. İçinde **Çözüm Gezgini**, sağ **Python ortamları** düğümü ve select **var olan sanal ortama Ekle**.
1. Gidin ve sanal ortam içeren klasörü seçin ve ardından seçin **Tamam**.

## <a name="step-4-2-understand-the-views-and-page-templates-created-by-the-project-template"></a>4-2. adım: görünümleri anlamak ve sayfa proje şablonu tarafından oluşturulan şablonlar

Projeyi çalıştırdığınızda gözlemlemek gibi uygulamayı üç görünüm içerir: hakkında ev ve başvurun. Bu görünümler için kod bulunan `FlaskWeb/views.py`. Her görünüm işlevi yalnızca çağırır `flask.render_template` yoluyla bir şablon ve şablona vermek değerleri için bağımsız değişken listesi. Örneğin, hakkında sayfası tarafından ele `about` işlevi (olan oluşturma öğesi sağlayan yönlendirme URL):

```python
@app.route('/about')
def about():
    """Renders the about page."""
    return render_template(
        'about.html',
        title='About',
        year=datetime.now().year,
        message='Your application description page.'
    )
```

`home` Ve `contact` işlevleri benzer dekoratörler ve biraz farklı bağımsız değişkenlerle neredeyse aynı.

Şablonları uygulamanın içinde bulunan `templates` klasör. Temel şablonu `layout.html`, en yoğun olduğu. Tüm gerekli statik dosyaları (JavaScript ve CSS) başvuruyor, "diğer geçersiz kılma sayfaları ve"betikleri"adlı başka bir blok sağlar içeriğe" adlı bir blok tanımlar. Aşağıdaki parçalarını açıklama `layout.html` bu belirli alanları göster:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />

    <!-- Define a viewport for Bootstrap's responsive rendering -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{ title }} - My Flask Application</title>

    <link rel="stylesheet" type="text/css" href="/static/content/bootstrap.min.css" />
    <link rel="stylesheet" type="text/css" href="/static/content/site.css" />
    <script src="/static/scripts/modernizr-2.6.2.js"></script>
</head>

<body>
    <!-- Navbar omitted -->

    <div class="container body-content">
        <!-- "content" block that pages are expected to override -->
        {% block content %}{% endblock %}
        <hr />
        <footer>
            <p>&copy; {{ year }} - My Flask Application</p>
        </footer>
    </div>

    <!-- Additional scripts; use the "scripts" block to add page-specific scripts.  -->
    <script src="/static/scripts/jquery-1.10.2.js"></script>
    <script src="/static/scripts/bootstrap.js"></script>
    <script src="/static/scripts/respond.js"></script>
    {% block scripts %}{% endblock %}

</body>
</html>
```

Tek tek sayfa şablonları `about.html`, `contact.html`, ve `index.html`, her genişletmek temel şablonu `layout.html`. `about.html` en kolayıdır ve gösterir `{% extends %}` ve `{% block content %}` etiketler:

```html
{% extends "app/layout.html" %}

{% block content %}

<h2>{{ title }}.</h2>
<h3>{{ message }}</h3>

<p>Use this area to provide additional information.</p>

{% endblock %}
```

`index.html` ve `contact.html` "içerik" bloğundaki lengthier içerik sağlamak ve aynı yapısını kullanın.

## <a name="the-flaskjade-web-project-template"></a>Flask/Jade Web Proje şablonu

Bu makalenin başlangıcında belirtildiği gibi Visual Studio "Flask Web projesi" tarafından üretilen için görsel olarak aynı olan bir uygulama oluşturur bir "Flask/Jade Web projesi" şablonu sağlar. Birincil fark daha kısa bir dil ile aynı kavramları uygulayan Jinja uzantısıdır Jade şablon motoru kullanmasıdır. Özellikle, Jade içine etiketleri yerine anahtar sözcükleri kullanır {Condition sınırlayıcıları, örneğin ve CSS stilleri ve anahtar sözcükleri kullanarak HTML öğeleri bakın sağlar.

Jade etkinleştirmek için proje şablonu ilk pyjade paketinde içeren `requirements.txt`. 

Uygulamanın `__init__.py` dosyası için bir satır içerir

    ```python
    app.jinja_env.add_extension('pyjade.ext.jinja.PyJadeExtension')
    ```
İçinde `templates` klasörü, gördüğünüz `.jade` yerine dosyaları `.html` şablonları ve görünümlerde `views.py` çağrılarını için bu dosyalarda başvurmak `flask.render_template`. Aksi takdirde görünümleri kod aynıdır.

Aşağıdakilerden birini açma `.jade` dosyaları bir şablon daha kısa bir ifade görebilirsiniz. Örneğin, içeriği işte `templates/layout.jade` "Flask/Jade Web projesi" şablonu tarafından oluşturulan olarak:

    ```jade
    doctype html
    html
      head
        meta(charset='utf-8')
        meta(name='viewport', content='width=device-width, initial-scale=1.0')
        title #{title} - My Flask/Jade Application
        link(rel='stylesheet', type='text/css', href='/static/content/bootstrap.min.css')
        link(rel='stylesheet', type='text/css', href='/static/content/site.css')
        script(src='/static/scripts/modernizr-2.6.2.js')
      body
        .navbar.navbar-inverse.navbar-fixed-top
          .container
            .navbar-header
              button.navbar-toggle(type='button', data-toggle='collapse', data-target='.navbar-collapse')
                span.icon-bar
                span.icon-bar
                span.icon-bar
              a.navbar-brand(href='/') Application name
            .navbar-collapse.collapse
              ul.nav.navbar-nav
                li
                  a(href='/') Home
                li
                  a(href='/about') About
                li
                  a(href='/contact') Contact
        .container.body-content
          block content
          hr
          footer
            p &copy; #{year} - My Flask/Jade Application

        script(src='/static/scripts/jquery-1.10.2.js')
        script(src='/static/scripts/bootstrap.js')
        script(src='/static/scripts/respond.js')

        block scripts
    ```

Burada da içeriğini `templates/about.jade`, kullanımını gösteren `#{ <name>}` yer tutucuları için:

    ```jade
    extends layout

    block content
      h2 #{title}.
      h3 #{message}
      p Use this area to provide additional information.
    ```

Jinja ve Jade sözdizimleri hangisinin sizin için en iyi görmek için deneme çekinmeyin.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Anketler Flask Web projesi şablonu](learn-flask-visual-studio-step-05-polls-flask-web-project-template.md)

## <a name="go-deeper"></a>Derinlemesine

- [İlk Flask uygulamanızı yazma, Bölüm 4 - formlar ve genel görünümler](https://docs.djangoproject.com/en/2.0/intro/tutorial04/) (docs.djangoproject.com)
- [Jade GitHib (belge) üzerinde](https://github.com/liuliqiang/pyjade) (github.com'u)
- Öğretici kaynak kodu github'da: [Microsoft/python-örnek-vs-learning-flask](https://github.com/Microsoft/python-sample-vs-learning-flask)