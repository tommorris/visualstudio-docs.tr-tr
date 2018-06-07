---
title: Öğretici - Visual Studio, 4. adım Django öğrenin
description: Visual Studio projeleri, özellikle Django Web projesi şablon tarafından sağlanan özellikleri bağlamında Django temel bir kılavuz.
ms.date: 04/25/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: b03cfca6a575cf9c91b1e60b0e44212388cc7611
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750369"
---
# <a name="tutorial-step-4-use-the-full-django-web-project-template"></a>Öğreticisi 4. adım: tam Django Web projesi şablonunu kullanın

**Önceki adımda: [hizmet statik dosyalar, sayfa ekleyin ve şablon devralma kullanın](learn-django-in-visual-studio-step-03-serve-static-files-and-add-pages.md)**

Visual Studio "Boş Django Web projesi" şablonunun üzerine bir uygulama oluşturarak Django temelleri incelediniz, "Django Web projesi" şablon tarafından üretilen eksiksiz uygulama kolayca anlayabilirsiniz.

Bu konuda, şimdi adım:

> [!div class="checklist"]
> - "Django Web projesi" şablonu kullanarak daha eksiksiz bir Django web uygulaması oluşturma ve proje yapısını inceleyin (adım 4 - 1)
> - Taban sayfası şablondan devralır üç sayfaların oluşan proje şablonu tarafından oluşturulan sayfa şablonları ve görünümler anlamak ve jQuery ve önyükleme (4-2. adım) gibi statik JavaScript kitaplıklarını kullanır
> - (4-3. adım) şablonu tarafından sağlanan URL yönlendirmeyi anlama

Şablon ayrıca adım 5'te kapsanan temel kimlik doğrulaması sağlar.

## <a name="step-4-1-create-a-project-from-the-template"></a>4-1. adım: bir proje şablonu oluşturma

1. Visual Studio'da Git **Çözüm Gezgini**, bu öğreticide daha önce oluşturulan "LearningDjango" çözüme sağ tıklayın ve seçin **Ekle** > **yeni proje**. (Alternatif olarak, yeni bir çözüm kullanmak isteyip istemediğinizi seçin **dosya** > **yeni** > **proje** yerine.)

1. Yeni Proje iletişim kutusunda, aramak ve "Django Web projesi" şablonunu seçin, proje "DjangoWeb" arayın ve seçin **Tamam**.

1. Şablonu yeniden içerdiğinden bir `requirements.txt` dosyası, Visual Studio bu bağımlılıkların yükleneceği sorar. Seçeneği **sanal bir ortama yükleme**hem de **sanal ortam Ekle** iletişim kutusunda **oluşturma** Varsayılanları kabul etmek için.

1. Visual Studio sanal ortamı kurma tamamlandıktan sonra görüntülenen'ndaki yönergeleri izleyin `readme.html` Django süper kullanıcı (diğer bir deyişle, bir yönetici) oluşturmak için. Yalnızca Visual Studio projesine sağ tıklatın ve **Python** > **Django süper kullanıcı oluşturma** komutunu ve ardından yönergeleri izleyin. Kullanıcı adı ve parola kimlik doğrulaması özelliklerini kullanan zaman kullandıkça kaydettiğinizden emin olun.

1. "DjangoWeb" projesini bu projeye sağ tıklayarak Visual Studio çözümü için varsayılan olacak şekilde ayarlayın **Çözüm Gezgini** ve seçerek **başlangıç projesi olarak ayarla**. Gösterilen başlangıç projesi içinde hata ayıklayıcı başlatıldığında ne çalıştırılan kalın.

    ![Başlangıç projesi olarak DjangoWeb proje gösteren Çözüm Gezgini](media/django/step04-second-project-in-solution-set-as-startup-project.png)

1. Seçin **hata ayıklama** > **hata ayıklamayı Başlat** (F5) veya **Web sunucusu** sunucu çalıştırmak için araç çubuğunda:

    ![Visual Studio'da Web sunucusu Çalıştır araç çubuğu düğmesi](media/django/run-web-server-toolbar-button.png)

1. Şablon tarafından oluşturulan uygulama hakkında ev ve hangi gezinme çubuğu kullanarak arasında gezinme ilgili kişi, üç sayfaları vardır. Bir veya iki farklı kısımlarını uygulama incelemek için dakika alın. Üzerinden uygulama kimlik doğrulaması yapmak için **oturum** komutu, daha önce oluşturduğunuz süper kullanıcı kimlik bilgilerini kullanın.

    ![Django Web projesi uygulamasının tam tarayıcı görünümü](media/django/step04-full-app-desktop-view.png)

1. "Django Web projesi" şablonu tarafından oluşturulan uygulama önyükleme için mobil form faktörleri düzenler esnek düzenini kullanır. Dar bir görünüme tarayıcıya içerik dikey işler ve gezinme çubuğu menü simgesinde kapatır şekilde yeniden boyutlandırın, bu yanıt verdiğini görmek için:

    ![Django Web projesi uygulamasının mobil (dar) görünümü](media/django/step04-full-app-mobile-view.png)

1. Aşağıdaki bölümlerde için çalışan uygulama bırakabilirsiniz.

    Uygulama durdurmak istiyorsanız ve [değişiklikleri kaynak denetimine](learn-django-in-visual-studio-step-02-create-an-app.md#commit-to-source-control), ilk açmak **değişiklikleri** sayfasındaki **Takım Gezgini**, sanal ortama (klasörünü sağ tıklatın büyük olasılıkla `env`) ve seçin **bu yerel öğeleri Yoksay**.

### <a name="examine-what-the-template-creates"></a>Ne şablon oluşturur inceleyin

Geniş düzeyde "Django Web projesi" şablonu aşağıdaki yapısını oluşturur:

- Proje kök dosyaları:
  - `manage.py`, Django yönetim yardımcı programı.
  - `db.sqlite3`, varsayılan bir SQLite veritabanı.
  - `requirements.txt` Django bir bağımlılığı içeren 1.x.
  - `readme.html`, Visual Studio projesi oluşturduktan sonra görüntülenen bir dosya. Önceki bölümde belirtildiği gibi uygulama için süper kullanıcı (Yönetici) hesabı oluşturmak için buradaki yönergeleri izleyin.
- `app` Klasör görünümleri, modelleri, testleri, formlar, şablonları ve statik dosyaları (bkz. adım 4-2) de dahil olmak üzere tüm uygulama dosyaları içerir. Genellikle daha farklı bir uygulama adı kullanmak üzere bu klasörünü yeniden adlandırın.
- `DjangoWeb` (Django Proje) klasör tipik Django proje dosyalarını içerir: `__init.py__`, `settings.py`, `urls.py`, ve `wsgi.py`. Proje şablonunu kullanarak `settings.py` uygulama ve veritabanı dosyası için zaten yapılandırıldı ve `urls.py` oturum açma formu dahil olmak üzere tüm uygulama sayfaları yolları ile zaten yapılandırılmış.

### <a name="question-is-it-possible-to-share-a-virtual-environment-between-visual-studio-projects"></a>Soru: bir sanal ortam Visual Studio projeleri arasında paylaşmak mümkün mü?

Yanıt: Evet, ancak farklı projelere olası zaman içinde farklı paketler kullanın ve paylaşılan bir sanal ortam kullanan tüm projeleri için tüm paketler bu nedenle içermelidir tanıma ile bunu.

Bununla birlikte, varolan bir sanal ortam kullanmak için aşağıdakileri yapın:

1. Visual Studio'da bağımlılıkları yüklemek isteyip istemediğiniz sorulduğunda seçin **ı bunları kendim yükleyecek** seçeneği.
1. İçinde **Çözüm Gezgini**, sağ **Python ortamları** düğümü ve select **var olan sanal ortama Ekle**.
1. Gidin ve sanal ortam içeren klasörü seçin ve ardından seçin **Tamam**.

## <a name="step-4-2-understand-the-views-and-page-templates-created-by-the-project-template"></a>4-2. adım: görünümleri anlamak ve sayfa proje şablonu tarafından oluşturulan şablonlar

Projeyi çalıştırdığınızda gözlemlemek gibi uygulamayı üç görünüm içerir: hakkında ev ve başvurun. Bu görünümler için kod bulunan `app/views` klasör. Her görünüm işlevi yalnızca çağırır `django.shortcuts.render` yoluyla bir şablon ve basit sözlük nesnesi. Örneğin, hakkında sayfası tarafından ele `about` işlevi:

```python
def about(request):
    """Renders the about page."""
    assert isinstance(request, HttpRequest)
    return render(
        request,
        'app/about.html',
        {
            'title':'About',
            'message':'Your application description page.',
            'year':datetime.now().year,
        }
    )
```

Şablonları uygulamanın içinde bulunan `templates/app` klasörü (ve genellikle yeniden adlandırmak istediğiniz `app` gerçek uygulamanız adına). Temel şablonu `layout.html`, en yoğun olduğu. Tüm gerekli statik dosyaları (JavaScript ve CSS) başvuruyor, "diğer geçersiz kılma sayfaları ve"betikleri"adlı başka bir blok sağlar içeriğe" adlı bir blok tanımlar. Aşağıdaki parçalarını açıklama `layout.html` bu belirli alanları göster:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />

    <!-- Define a viewport for Bootstrap's responsive rendering -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{ title }} - My Django Application</title>

    {% load staticfiles %}
    <link rel="stylesheet" type="text/css" href="{% static 'app/content/bootstrap.min.css' %}" />
    <link rel="stylesheet" type="text/css" href="{% static 'app/content/site.css' %}" />
    <script src="{% static 'app/scripts/modernizr-2.6.2.js' %}"></script>
</head>
<body>
    <!-- Navbar omitted -->

    <div class="container body-content">

<!-- "content" block that pages are expected to override -->
{% block content %}{% endblock %}
        <hr/>
        <footer>
            <p>&copy; {{ year }} - My Django Application</p>
        </footer>
    </div>

<!-- Additional scripts; use the "scripts" block to add page-specific scripts.  -->
    <script src="{% static 'app/scripts/jquery-1.10.2.js' %}"></script>
    <script src="{% static 'app/scripts/bootstrap.js' %}"></script>
    <script src="{% static 'app/scripts/respond.js' %}"></script>
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

İçinde `templates/app` klasördür ayrıca dördüncü sayfasında `login.html`, birlikte `loginpartial.html` içine duruma `layout.html` kullanarak `{% include %}`. Bu şablon dosyalarını 5. adım kimlik doğrulaması ele alınmıştır.

### <a name="question-can--block--and--endblock--be-indented-in-the-django-page-template"></a>Soru: can {engelleme %} % ve {% endblock %} Django sayfa şablonunda girintili?

Yanıt: blok etiketleri, belki de bunları kendi uygun üst öğeler içinde hizalamak için girinti Evet, Django sayfası şablonlarını düzgün çalışır. Bunlar, açıkça nereye yerleştirileceğini görebilmeniz için Visual Studio Proje şablonu tarafından oluşturulan sayfa şablonlarında girintili değil.

## <a name="step-4-3-understand-the-url-routing-created-by-the-template"></a>4-3. adım: şablon tarafından oluşturulan URL yönlendirmeyi anlama

Django projenin `urls.py` "Django Web projesi" şablonu tarafından oluşturulan dosyasıyla aşağıdaki kod içerir:

```python
from datetime import datetime
from django.conf.urls import url
import django.contrib.auth.views

import app.forms
import app.views

urlpatterns = [
    url(r'^$', app.views.home, name='home'),
    url(r'^contact$', app.views.contact, name='contact'),
    url(r'^about$', app.views.about, name='about'),
    url(r'^login/$',
        django.contrib.auth.views.login,
        {
            'template_name': 'app/login.html',
            'authentication_form': app.forms.BootstrapAuthenticationForm,
            'extra_context':
            {
                'title': 'Log in',
                'year': datetime.now().year,
            }
        },
        name='login'),
    url(r'^logout$',
        django.contrib.auth.views.logout,
        {
            'next_page': '/',
        },
        name='logout'),
]
```

İlk üç URL desenlerini doğrudan eşleme `home`, `contact`, ve `about` uygulamanın görünümlerde `views.py` dosya. Desenler `^login/$` ve `^logout$`, diğer el, uygulama tanımlı görünümler yerine yerleşik Django görünümlerini kullanın. Çağrıları `url` yöntemi de görünümü özelleştirmek için fazladan verileri içerir. 5. adım bu çağrıları inceler.

### <a name="question-in-the-project-i-created-why-does-the-about-url-pattern-uses-about-instead-of-about-as-shown-here"></a>Soru: projedeki neden "about" URL deseni kullanır oluşturdum, ' ^ hakkında ' yerine ' ^ $' aşağıda gösterildiği gibi?

Yanıt: Normal ifadede sonunda '$' eksikliği birçok sürümlerinde proje şablonu, basit bir gözetim alınamadı. Mükemmel "about" adlı bir sayfaya için URL deseni çalışır, ancak izleyen ' $' URL deseni de URL'lerle eşleşir "yaklaşık django = gibi", "about09876", "aboutoflaughter" ve bu nedenle üzerinde. Sondaki '$' ile eşleşen bir URL deseni oluşturmak için burada gösterilen *yalnızca* "hakkında".

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Django kullanıcıların kimlik doğrulaması](learn-django-in-visual-studio-step-05-django-authentication.md)

## <a name="going-deeper"></a>Daha derin gitme

- [İlk Django uygulamanız yazma, Bölüm 4 - formlar ve genel görünümler](https://docs.djangoproject.com/en/2.0/intro/tutorial04/) (docs.djangoproject.com)
- Öğretici kaynak kodu github'da: [Microsoft/python-örnek-vs-learning-django](https://github.com/Microsoft/python-sample-vs-learning-django)
