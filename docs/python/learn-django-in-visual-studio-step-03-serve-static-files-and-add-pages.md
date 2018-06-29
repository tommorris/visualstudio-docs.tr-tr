---
title: Öğretici - Visual Studio, adım 3 Django öğrenin
description: Visual Studio projeleri, özellikle statik dosyaları işleme, sayfaları için uygulama ekleme ve şablon devralma kullanma gösteren bağlamında Django temel bir kılavuz
ms.date: 06/27/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 558353fcae63172273e4e2070a51dfafdea6913e
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089593"
---
# <a name="step-3-serve-static-files-add-pages-and-use-template-inheritance"></a>3. adım: statik dosyaları işleme, sayfa ekleyin ve şablon devralma kullanın

**Önceki adımda: [görünümlerle bir Django uygulaması oluşturma ve sayfa şablonları](learn-django-in-visual-studio-step-02-create-an-app.md)**

Bu öğreticinin önceki adımlarda kendi içinde bulunan HTML tek bir sayfayla en az bir Django uygulaması oluşturma öğrendiniz. Modern web uygulamaları, ancak birçok sayfaları genellikle oluşurlar ve olun tutarlı stil ve davranışı sağlamak için CSS ve JavaScript dosyaları gibi paylaşılan kaynakları.

Bu adımda, bilgi nasıl yapılır:

> [!div class="checklist"]
> - Farklı türlerde uygun Demirbaş kod ile hızlı bir şekilde yeni dosyalar için Visual Studio öğe şablonları kullanın (adım 3 - 1)
> - Statik dosyalar (adım 3-2) hizmet vermeye Django projeyi yapılandırın
> - Bir uygulamaya (adım 3-3) ek sayfaları ekleme
> - (3-4. adım) sayfaları arasında kullanılan bir üstbilgi ve gezinti çubuğu oluşturmak için şablon devralma kullanın

## <a name="step-3-1-become-familiar-with-item-templates"></a>3 1. adım: öğe şablonları ile aşina

Django Uygulama geliştirirken, genellikle çok daha fazla Python, HTML, CSS ve JavaScript dosyaları ekleyin. Her dosya türü için (sair dosyaların `web.config` dağıtım için gereken), Visual Studio'nun sağladığı uygun [öğe şablonlarını](python-item-templates.md) başlamanıza yardımcı olmak için.

Kullanılabilir şablonların görmek için Git **Çözüm Gezgini**, select öğesi oluşturmak istediğiniz klasörü sağ tıklatın **Ekle** > **yeni öğe**:

![Visual Studio'da yeni öğe iletişim ekleyin](media/django/step03-add-new-item-dialog.png)

Bir şablonu kullanmak için istediğiniz şablonu seçin, dosya için bir ad belirtin ve seçin **Tamam**. Bu şekilde otomatik olarak bir öğe ekleme dosyayı Visual Studio projenize ekler ve değişiklikleri kaynak denetimi için işaretler.

### <a name="question-how-does-visual-studio-know-which-item-templates-to-offer"></a>Soru: nasıl Visual Studio hangi öğesi sunmak için şablonlar biliyor?

Yanıt: Visual Studio Proje dosyası (`.pyproj`) Python projesi olarak işaretler proje türü tanımlayıcısı içeriyor. Visual Studio Proje türü için uygun olan öğe şablonları göstermek için bu tür tanımlayıcı kullanır. Bu şekilde, çoğu, aralarında her zaman sıralamak için istemeden türleri proje için Visual Studio öğe şablonları zengin bir dizi sağlayabilir.

## <a name="step-3-2-serve-static-files-from-your-app"></a>3-2. adım: hizmet uygulamanızın statik dosyalar

(Tüm framework kullanarak) Python ile yerleşik bir web uygulamasında Python dosyalarınızı her zaman web ana bilgisayarın sunucusunda çalıştırın ve bir kullanıcının bilgisayarına hiçbir zaman iletilmez. Ana bilgisayar sunucusu yalnızca olarak sunar diğer dosyaları ancak, CSS ve JavaScript gibi tarayıcı tarafından özel olarak kullanıldığından-istenen ne zaman açıktır. Bu tür dosyaları "statik" dosyalar olarak adlandırılır ve Django bunları otomatik olarak, kod yazmaya gerek sunabilir.

Uygulamanın statik dosyalar hizmet vermek için varsayılan bir Django proje yapılandırılmış `static` Django projenin bu satırları sayesinde klasörü `settings.py`:

```python
# Static files (CSS, JavaScript, Images)
# https://docs.djangoproject.com/en/1.9/howto/static-files/

STATIC_URL = '/static/'

STATIC_ROOT = posixpath.join(*(BASE_DIR.split(os.path.sep) + ['static']))
```

İçinde herhangi bir klasör yapısını kullanarak dosyaları düzenleme `static` ister ve ardından dosyaları başvurmak için bu klasörün içinde göreli yollar kullanın. Bu işlem göstermek için aşağıdaki adımları CSS dosyası uygulamaya ekleyin, sonra bu stil kullanmak `index.html` şablonu:

1. İçinde **Çözüm Gezgini**, Visual Studio projesi "HelloDjangoApp" klasörüne sağ tıklayın, **Ekle** > **yeni klasör**ve klasörüadı`static`.

1. Sağ `static` klasörü ve select **Ekle** > **yeni öğe**. Görüntülenen iletişim kutusunda, "Stil" şablonunu seçin, dosya adı `site.css`seçip **Tamam**. `site.css` Dosya projede görünür ve Düzenleyicisi'nde açılır. Klasör yapısı aşağıdaki görüntüye benzer görünmelidir:

    ![Çözüm Gezgini'nde gösterildiği gibi statik dosya yapısı](media/django/step03-static-file-structure.png)

1. Değiştir `site.css` aşağıdaki kodla ve dosyayı kaydedin:

    ```css
    .message {
        font-weight: 600;
        color: blue;
    }
    ```

1. Uygulamanın içeriğini değiştirin `templates/HelloDjangoApp/index.html` dosya ile değiştirir aşağıdaki kodu `<strong>` ile 2. adımda kullanılan öğe bir `<span>` başvuran `message` stil sınıfı. Bu şekilde stili sınıfını kullanarak öğeyi stil oluşturma çok daha fazla esneklik sağlar. (Henüz taşınsa `index.html` bir alt klasöre içine `templates`, başvurmak [şablonu namespacing](learn-django-in-visual-studio-step-02-create-an-app.md#template-namespacing) 2. adımda.)

    ```html
    <html>
        <head>
            <title>{{ title }}</title>
            {% load staticfiles %} <!-- Instruct Django to load static files -->
            <link rel="stylesheet" type="text/css" href="{% static 'site.css' %}" />
        </head>
        <body>
            <span class="message">{{ message }}</span>{{ content }}
        </body>
    </html>
    ```

1. Sonuçları gözlemlemek için projesini çalıştırın. İşiniz bittiğinde sunucusunu durdurun ve kaynak denetim isterseniz, değişiklikleri (açıklandığı gibi [2. adım](learn-django-in-visual-studio-step-02-create-an-app.md#commit-to-source-control)).

### <a name="question-what-is-purpose-of-the--load-staticfiles--tag"></a>Soru: {staticfiles %} etiketi % yük? amacı nedir

Yanıt: `{% load staticfiles %}` satırı statik dosyalar gibi öğeleri başvuran önce gerekli `<head>` ve `<body>`. Bu bölümde gösterilen örnekte, "staticfiles" ne kullanmanıza olanak sağlayan olan bir özel Django şablonu etiketi kümesine, başvuruda `{% static %}` statik dosyaları başvurmak için sözdizimi.  Olmadan `{% load staticfiles %}`, uygulama çalıştığında bir özel durum görürsünüz.

### <a name="question-are-there-any-conventions-for-organizing-static-files"></a>Soru: statik dosyaları düzenleme için tüm kuralları var mı?

Yanıt: Diğer CSS, JavaScript ve HTML dosyalarında ekleyebilirsiniz, `static` klasörü ancak istiyor. Statik dosyaları düzenlemek için normal bir şekilde adlı alt klasörler oluşturmaktır `fonts`, `scripts`, ve `content` (için stil sayfaları ve diğer dosyaları). Her durumda, göreli yolda dosyasında bu klasörleri dahil etmeyi unutmayın `{% static %}` başvuruları.

## <a name="step-3-3-add-a-page-to-the-app"></a>3-3. adım: uygulama için bir sayfa ekleyin

Uygulamaya başka bir sayfaya ekleme aşağıdaki anlamına gelir:

- Görünümü tanımlayan bir Python işlevi ekleyin.
- Sayfanın biçimlendirme için bir şablon ekleyin.
- Django projenin için gerekli yönlendirme eklemek `urls.py` dosya.

Aşağıdaki adımları "HelloDjangoApp" proje ve giriş sayfasından bu sayfaya bağlantılar bir "About" sayfasında ekleyin:

1. İçinde **Çözüm Gezgini**, sağ `templates/HelloDjangoApp` klasöründe seçin **Ekle** > **yeni öğe**, "HTML sayfası" öğe şablonu seçin, dosya adı `about.html`seçip **Tamam**.

    > [!Tip]
    > Varsa **yeni öğe** komut çubuğunda görünmüyor **Ekle** menüsünde, böylece Visual Studio hata ayıklama modunu çıkar Sunucu durduruldu emin olun.

1. Değiştir `about.html` (, yerine giriş sayfasına açık bağlantı basit bir gezinti çubuğu 3-4. adımda) aşağıdaki biçimlendirme ile:

    ```html
    <html>
        <head>
            <title>{{ title }}</title>
            {% load staticfiles %}
            <link rel="stylesheet" type="text/css" href="{% static 'site.css' %}" />
        </head>
        <body>
            <div><a href="home">Home</a></div>
            {{ content }}
        </body>
    </html>
    ```

1. Uygulamanın açmak `views.py` dosya ve adlı bir işlev eklemek `about` şablonu kullanır:

    ```python
    def about(request):
        return render(
            request,
            "HelloDjangoApp/about.html",
            {
                'title' : "About HelloDjangoApp",
                'content' : "Example app page for Django."
            }
        )
    ```

1. Django projenin açmak `urls.py` dosya ve aşağıdaki satırı ekleyin `urlPatterns` dizi:

    ```python
    url(r'^about$', HelloDjangoApp.views.about, name='about'),
    ```

1. Açık `templates/HelloDjangoApp/index.html` aşağıdaki satırı ekleyin ve dosya `<body>` hakkında sayfasına bağlantı kurmak için öğesi (yeniden, bu bağlantıyı adım 3-4 gezinti çubuğunda değiştirin):

    ```html
    <div><a href="about">About</a></div>
    ```

1. Kullanarak tüm dosyaları kaydetmek **dosya** > **Tümünü Kaydet** menü komutu, veya yalnızca basın veya Ctrl + Shift + S. (Visual Studio projesi çalıştırmaya dosyaları otomatik olarak kaydeder gibi teknik olarak, bu adım gerekli değildir. Bununla birlikte, hakkında bilgi edinmek için iyi bir komutu kadar!)

1. Sonuçları gözlemlemek ve sayfaları arasında gezinmeyi denetleme projeyi çalıştırın. İşiniz bittiğinde sunucusunu kapatın.

### <a name="question-i-tried-using-index-for-the-link-to-the-home-page-but-it-didnt-work-why"></a>Soru: t giriş sayfasına bağlantı için "dizin" kullanarak çalıştı, ancak işe yaramadı. Neden?

Yanıt: Rağmen görünümü işlev içinde `views.py` adlı `index`, Django projenin desenleri yönlendirme URL `urls.py` dosya "dizin" dizesiyle eşleşen normal bir ifade içermiyor. Bu dize eşleşmesi için düzeni için başka bir girdi eklemeniz gerekir `^index$`.

Sonraki bölümde gösterildiği gibi kullanmak daha iyi `{% url '<pattern_name>' %}` başvurmak için sayfa şablonu etiketinde *adı* içinde servis talebi Django oluşturan uygun URL sizin için bir desen. Örneğin, `<div><a href="home">Home</a></div>` içinde `about.html` ile `<div><a href="{% url 'index' %}">Home</a></div>`. 'Dizini' kullanımını çalışır burada ilk URL deseni çünkü `urls.py` aslında, 'dizin' adlı (tarafından virtue, `name='index'` bağımsız değişkeni). Ayrıca 'giriş' İkinci düzeni başvurmak için kullanabilirsiniz.

## <a name="step-3-4-use-template-inheritance-to-create-a-header-and-nav-bar"></a>Adım 3-4: bir üstbilgi ve gezinti çubuğu oluşturmak için şablon devralma kullanın

Açık Gezinti bağlantıları her sayfada sahip olmak yerine modern web uygulamaları genellikle bir marka başlığı ve en önemli sayfa bağlantılar, açılır menüler ve benzeri sağlayan gezinti çubuğu kullanın. Üstbilgi ve gezinme çubuğu tüm sayfalardaki aynı olduğundan emin olmak için ancak, her sayfası şablonu aynı kodu tekrar etmek istemediğiniz. Bunun yerine, tek bir yerde, tüm sayfaların ortak bölümleri tanımlamak istersiniz.

Django'nın şablon sistem birden fazla şablon belirli öğeleri yeniden kullanmak için iki anlamına gelir sağlar: içerir ve devralma.

- *İçeren* sözdizimini kullanarak başvuran şablon belirli bir yerde eklediğiniz diğer sayfa şablonları `{% include <template_path> %}`. Kod yolunda dinamik olarak değiştirmek istiyorsanız bir değişken de kullanabilirsiniz. İçeren bir sayfa gövdesinde genellikle sayfasında belirli bir konumdaki paylaşılan şablonunda çekmek için kullanılır.

- *Devralma* kullanan `{% extends <template_path> %}` başına sayfa şablonunun başvuran şablon sonra bağlı derlemeler paylaşılan bir temel şablonu belirtin. Devralma paylaşılan düzeni, gezinme çubuğu tanımlamak için yaygın olarak kullanılır ve şablonları başvuran yalnızca eklemek veya adlı temel şablonu belirli alanlarında değiştirmek, diğer bir uygulamanın sayfaları için yapıları *blokları*.

Her iki durumda da `<template_path>` uygulamanın göreli olduğunu `templates` klasörü (`../` veya `./` de izin verilir).

Temel bir şablon kullanarak blokları betimleyen `{% block <block_name> %}` ve `{% endblock %}` etiketler. Başvuran bir şablon daha sonra aynı blok ada sahip etiketleri kullanıyorsa blok içeriği, temel şablonu geçersiz.

Aşağıdaki adımlarda, devralma gösterilmektedir:

1. Uygulamasının `templates/HelloDjangoApp` klasörü, yeni bir HTML dosyası oluşturun (kullanarak **Ekle** > **yeni öğe** bağlam menüsü veya **Ekle**  >   **HTML sayfası**) olarak adlandırılan `layout.html`ve yerine kendi biçimlendirme ile. Bu şablon "içerik" adlı bir blok tüm değiştirmek için başvuran sayfa gereksinimi olan içerdiğini görebilirsiniz:

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="utf-8" />
        <title>{{ title }}</title>
        {% load staticfiles %}
        <link rel="stylesheet" type="text/css" href="{% static 'site.css' %}" />
    </head>

    <body>
        <div class="navbar">
           <a href="/" class="navbar-brand">Hello Django</a>
           <a href="{% url 'home' %}" class="navbar-item">Home</a>
           <a href="{% url 'about' %}" class="navbar-item">About</a>
        </div>

        <div class="body-content">
    {% block content %}{% endblock %}
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

1. Değiştirme `templates/HelloDjangoApp/index.html` temel şablona bakın ve içerik engellemeyi geçersiz. Devralma kullanarak, bu şablon basit olacağını görebilirsiniz:

    ```html
    {% extends "HelloDjangoApp/layout.html" %}
    {% block content %}
    <span class="message">{{ message }}</span>{{ content }}
    {% endblock %}
    ```

1. Değiştirme `templates/HelloDjangoApp/about.html` da temel şablona bakın ve içerik bloğuna geçersiz kılmak için:

    ```html
    {% extends "HelloDjangoApp/layout.html" %}
    {% block content %}
    {{ content }}
    {% endblock %}
    ```

1. Sonuçları gözlemlemek sunucuya çalıştırın. İşiniz bittiğinde sunucusunu kapatın.

    ![Gezinme çubuğu gösteren çalışan uygulama](media/django/step03-nav-bar.png)

1. Önemli değişiklikler uygulamaya yapılan olduğundan, onu yeniden için zamanıdır [kaynak denetimi, değişiklikleri](learn-django-in-visual-studio-step-02-create-an-app.md#commit-to-source-control).

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Tam Django Web projesi şablonunu kullanın](learn-django-in-visual-studio-step-04-full-django-project-template.md)

## <a name="go-deeper"></a>Derinlemesine

- [Web uygulamasını Azure App Service'e dağıtma](publishing-python-web-applications-to-azure-from-visual-studio.md)
- [İlk Django uygulamanız yazma, 3 (görünümler) Kısım](https://docs.djangoproject.com/en/2.0/intro/tutorial03/) (docs.djangoproject.com)
- Daha fazla yeteneklerini denetim akışı gibi Django şablonları için bkz: [Django şablonu dili](https://docs.djangoproject.com/en/2.0/ref/templates/language/) (docs.djangoproject.com)
- Kullanımıyla ilgili tam Ayrıntılar için `{% url %}` etiketlemek için bkz: [url](https://docs.djangoproject.com/en/2.0/ref/templates/builtins/#url) içinde [yerleşik şablon etiketleri ve Django şablonları başvurusu için filtreleri](https://docs.djangoproject.com/en/2.0/ref/templates/builtins/) (docs.djangoproject.com)
- Öğretici kaynak kodu github'da: [Microsoft/python-örnek-vs-learning-django](https://github.com/Microsoft/python-sample-vs-learning-django)