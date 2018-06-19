---
title: Öğretici - Visual Studio, adım 5 Django öğrenin
description: Visual Studio projeleri, Django Web projesi şablonları tarafından sağlanan gibi özel kimlik doğrulama özelliklerini bağlamında Django temel bir kılavuz.
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
ms.openlocfilehash: e2c5f9461eafa83551ba15c36d8ef212922a52ff
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103144"
---
# <a name="tutorial-step-5-authenticate-users-in-django"></a>Öğreticisi 5. adım: Django kullanıcıların kimlik doğrulaması

**Önceki adımda: [tam Django Web projesi şablonunu kullanın](learn-django-in-visual-studio-step-04-full-django-project-template.md)**

Kimlik doğrulama web uygulamaları için ortak bir gereksinimi olduğundan, "Django Web projesi" şablonu temel kimlik doğrulaması akışı içerir. (Bu öğretici 6. adımında açıklandığı "Yoklamalar Django Web projesi" şablonu da aynı akışı içerir.) Django proje şablonlardan herhangi birini kullanırken, Visual Studio kimlik doğrulaması için gerekli olan tüm modülleri Django projenin içerir. `settings.py`.

Bu adımda, öğrenin:

> [!div class="checklist"]
> - Visual Studio şablonları sağlanan kimlik doğrulama akışı kullanma (adım 5 - 1)

## <a name="step-5-1-use-the-authentication-flow"></a>5 1. adım: kimlik doğrulaması akışı kullanın

Aşağıdaki adımları kimlik doğrulaması akışı uygulamanız ve söz konusu proje bölümlerini açıklamaktadır:

1. ' Ndaki yönergeleri zaten ardından varsa `readme.html` süper kullanıcı (Yönetici) hesabı oluşturmak için bunu şimdi yapın proje kök dosyasında.

1. Visual Studio kullanarak uygulamayı çalıştırın **hata ayıklama** > **hata ayıklamayı Başlat** (F5). Uygulama tarayıcıda görüntülendiğinde, gözlemlemek **oturum** sağ üst tarafındaki gezinme çubuğu üzerinde görüntülenir.

    ![Django Web projesi uygulama sayfasında oturum açma denetimi](media/django/step05-login-control.png)

1. Açık `templates/app/layout.html` ve görüntülendiğini `<div class="navbar ...>` ögesinin etiket `{% include app/loginpartial.html %}`. `{% include %}` Etiketi dahil dosyasının içeriğini bu noktada içeren şablondaki çekmesini Django'nın şablon sistem bildirir.

1. Açık `templates/app/loginpartial.html` ve nasıl koşullu etiket kullandığı uyun `{% if user.is_authenticated %}` ile birlikte bir `{% else %}` etiketi olup kullanıcı kimliğini doğrulamasından bağlı olarak farklı kullanıcı Arabirimi öğeleri oluşturmak için:

    ```html
    {% if user.is_authenticated %}
    <form id="logoutForm" action="/logout" method="post" class="navbar-right">
        {% csrf_token %}
        <ul class="nav navbar-nav navbar-right">
            <li><span class="navbar-brand">Hello {{ user.username }}!</span></li>
            <li><a href="javascript:document.getElementById('logoutForm').submit()">Log off</a></li>
        </ul>
    </form>

    {% else %}

    <ul class="nav navbar-nav navbar-right">
        <li><a href="{% url 'login' %}">Log in</a></li>
    </ul>

    {% endif %}
    ```

1. Hiçbir kullanıcı uygulamayı ilk kez başlattığınızda doğrulandığı yalnızca "Oturum" bağlantı "login" göreli yolu için bu şablonu kodu oluşturur. Belirtilmiş `urls.py` önceki bölümde gösterildiği gibi bu rota eşlenmiş `django.contrib.auth.views.login` belirtilen aşağıdaki veri görünümü:

    ```python
    {
        'template_name': 'app/login.html',
        'authentication_form': app.forms.BootstrapAuthenticationForm,
        'extra_context':
        {
            'title': 'Log in',
            'year': datetime.now().year,
        }
    }
    ```

    Burada, `template_name` şablon için oturum açma sayfasında, bu durumda tanımlayan `templates/app/login.html`. `extra_context` Özelliği, şablon için verilen varsayılan bağlam verileri eklenir. Son olarak, `authentication_form` oturum açma ile kullanmak için bir form sınıfı belirtiyor ' olarak göründüğü şablonunda `form` nesnesi. Varsayılan değer `AuthenticationForm` (gelen `django.contrib.auth.views`); Visual Studio Proje şablonu yerine uygulamanın içinde tanımlanan formun kullanır `forms.py` dosyası:

    ```python
    from django import forms
    from django.contrib.auth.forms import AuthenticationForm
    from django.utils.translation import ugettext_lazy as _

    class BootstrapAuthenticationForm(AuthenticationForm):
        """Authentication form which uses boostrap CSS."""
        username = forms.CharField(max_length=254,
                                   widget=forms.TextInput({
                                       'class': 'form-control',
                                       'placeholder': 'User name'}))
        password = forms.CharField(label=_("Password"),
                                   widget=forms.PasswordInput({
                                       'class': 'form-control',
                                       'placeholder':'Password'}))
    ```

    Gördüğünüz gibi bu formu sınıfın türetildiği `AuthenticationForm` ve özellikle yer tutucu metin eklemek için kullanıcı adı ve parola alanları geçersiz kılar. Visual Studio şablon, büyük olasılıkla parola gücünü doğrulama ekleme gibi form özelleştirme istersiniz, varsayım açık bu kodu içerir.

1. Ne zaman gezinmenizi oturum açma sayfasına daha sonra uygulama işler `login.html` şablonu. Değişkenleri `{{ form.username }}` ve `{{ form.password }}` işleme `CharField` gelen forms `BootstrapAuthenticationForm`. Bu hizmetleri eklemek isterseniz, doğrulama hataları ve sosyal oturum açmalar için hazır bir öğesi göstermek için yerleşik bir bölümü yoktur.

    ```html
    {% extends "app/layout.html" %}

    {% block content %}

    <h2>{{ title }}</h2>
    <div class="row">
        <div class="col-md-8">
            <section id="loginForm">
                <form action="." method="post" class="form-horizontal">
                    {% csrf_token %}
                    <h4>Use a local account to log in.</h4>
                    <hr />
                    <div class="form-group">
                        <label for="id_username" class="col-md-2 control-label">User name</label>
                        <div class="col-md-10">
                            {{ form.username }}
                        </div>
                    </div>
                    <div class="form-group">
                        <label for="id_password" class="col-md-2 control-label">Password</label>
                        <div class="col-md-10">
                            {{ form.password }}
                        </div>
                    </div>
                    <div class="form-group">
                        <div class="col-md-offset-2 col-md-10">
                            <input type="hidden" name="next" value="/" />
                            <input type="submit" value="Log in" class="btn btn-default" />
                        </div>
                    </div>
                    {% if form.errors %}
                    <p class="validation-summary-errors">Please enter a correct user name and password.</p>
                    {% endif %}
                </form>
            </section>
        </div>
        <div class="col-md-4">
            <section id="socialLoginForm"></section>
        </div>
    </div>

    {% endblock %}
    ```

1. Formu gönderdiğinde, Django (Süper kullanıcı kimlik bilgileri gibi) sağladığınız kimlik bilgilerini doğrulamak çalışır. Kimlik doğrulama başarısız olursa, aynı sayfa üzerinde kalır ancak `form.errors` true olarak ayarlanmış. Kimlik doğrulaması başarılı olursa, Django "İleri" alanında göreli URL gider `<input type="hidden" name="next" value="/" />`, bu durumda olduğu giriş sayfası (`/`).

1. Şimdi, ne zaman giriş sayfası işlenen yeniden `user.is_authenticated` özelliği true ise ne zaman `loginpartial.html` şablonu işlenir. Sonuç olarak, bir "Hello (kullanıcı adı)" iletisi ve "Oturumunu" bakın. Kullanabileceğiniz `user.is_authenticated` kimlik doğrulaması denetlemek için uygulamanın diğer bölümlerinde.

    ![Django Web projesi uygulama sayfasında Hello ileti ve oturum kapatma denetimi](media/django/step05-logoff-control.png)

1. Kimliği doğrulanmış kullanıcının belirli kaynaklara erişmek için yetkili olup olmadığını denetlemek için veritabanınızın, kullanıcı için kullanıcıya özgü izinleri almak gerekir. Daha fazla ayrıntı için bkz: [Django kimlik doğrulama sistemini kullanarak](https://docs.djangoproject.com/en/2.0/topics/auth/default/#permissions-and-authorization) (Django belgeleri).

1. Süper kullanıcı veya yönetici, özellikle, "/admin/" göreli URL'ler kullanarak yerleşik Django yönetici arabirimleri erişim yetkisi ve "/ admin/doc /". Bu arabirimleri etkinleştirmek için Django projenin açın `urls.py` ve açıklamaları aşağıdaki girişleri kaldırın:

    ```python
    from django.conf.urls import include
    from django.contrib import admin
    admin.autodiscover()

    # ...
    urlpatterns = [
        # ...
        url(r'^admin/doc/', include('django.contrib.admindocs.urls')),
        url(r'^admin/', include(admin.site.urls)),
    ]
    ```

    Uygulamasını yeniden başlattığınızda, "/admin/" gidin ve "/ Yönetici/doc /" ve ek kullanıcı hesapları oluşturmak gibi görevleri gerçekleştirebilir.

    ![Django yönetici arabirimi](media/django/step05-administrator-interface.png)

1. Kimlik doğrulaması akışı için son bölümü kapatmadan. İçinde gördüğünüz `loginpartial.html`, **oturumunu** bağlantı göreli URL için yalnızca bir POST yapar "/ oturum açma", yerleşik görünüm tarafından işlenen `django.contrib.auth.views.logout`. Bu görünümde herhangi bir UI göstermez ve yalnızca giriş sayfasına gider (gösterildiği gibi `urls.py` için "^ oturum kapatma$" deseni). Oturum kapatma sayfasını görüntülemek istiyorsanız, önce aşağıdaki gibi "þablon_adý" özellik ekleme ve "next_page" özelliği kaldırmak için URL deseni değiştirin:

    ```python
    url(r'^logout$',
        django.contrib.auth.views.logout,
        {
            'template_name': 'app/loggedoff.html',
            # 'next_page': '/',
        },
        name='logout')
    ```

    Ardından oluşturun `templates/app/loggedoff.html` (en az) aşağıdaki içeriğe sahip:

    ```html
    {% extends "app/layout.html" %}
    {% block content %}
    <h3>You have been logged off</h3>
    {% endblock %}
    ```

    Sonucu şu şekilde görünür:

    ![Eklenen sayfadan oturum](media/django/step05-logged-off-page.png)

1. Tüm bittiğinde, sunucunun durdurun ve bir kez daha, kaynak denetimine değişiklikleri.

### <a name="question-what-is-the-purpose-of-the--crsftoken--tag-that-appears-in-the-form-elements"></a>Soru: amacı nedir {% crsf_token %} etiketi, görünür \<form\> öğeleri?

Yanıt: `{% crsf_token %}` etiketi içeren Django'nın yerleşik [siteler arası istek sahtekarlığı (crsf) koruma](https://docs.djangoproject.com/en/2.0/ref/csrf/) (Django belgeleri). POST, PUT ya da DELETE istek yöntemleri, form ve şablon işleme işlevi gibi içerir herhangi bir öğeye bu etiketi ekleyin (`render`) gerekli koruma ekler.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Yoklamalar Django Web projesi şablonu kullanın](learn-django-in-visual-studio-step-06-polls-django-web-project-template.md)

## <a name="going-deeper"></a>Daha derin gitme

- [Django kullanıcı kimlik doğrulaması](https://docs.djangoproject.com/en/2.0/topics/auth/) (docs.djangoproject.com)
- Öğretici kaynak kodu github'da: [Microsoft/python-örnek-vs-learning-django](https://github.com/Microsoft/python-sample-vs-learning-django)