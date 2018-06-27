---
title: Öğretici - Visual Studio, 2. adım Django öğrenin
description: Visual Studio projeleri, bir uygulama oluşturma ve görünümler ve şablonlar kullanarak özellikle adımları bağlamında Django temel bir kılavuz.
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
ms.openlocfilehash: e7e8989c9c122791fea840f30835be1c090a8972
ms.sourcegitcommit: 4e605891d0dfb3ab83150c17c074bb98dba29d15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36947514"
---
# <a name="step-2-create-a-django-app-with-views-and-page-templates"></a>2. adım: bir Django uygulaması görünümleri ve sayfa şablonları oluşturma

**Önceki adımda: [Visual Studio Proje ve çözüm oluşturma](learn-django-in-visual-studio-step-01-project-and-solution.md)**

Ne, o ana kadarki Visual Studio projesi olan bir Django yalnızca site düzeyi bileşenlerinin sahip *proje*, bir veya daha fazla Django çalıştırabilirsiniz *uygulamaları*. Sonraki adım, tek bir sayfayla ilk uygulamanızı oluşturmaktır.

Bu adımda, daha fazla bilgi nasıl yapılır:

> [!div class="checklist"]
> - Tek bir sayfayla bir Django uygulaması oluşturma (Adım 2 - 1)
> - Django projeden (Adım 2-2) uygulamayı çalıştırın
> - HTML (2-3. adım) kullanarak görünüm işlemek
> - Django sayfa şablonu (Adım 2-4) kullanarak görünüm işlemek

## <a name="step-2-1-create-an-app-with-a-default-structure"></a>2-1. adım: bir uygulama ile bir varsayılan yapısı oluşturun

Belirli bir amaç için ilgili dosyaları içeren ayrı bir Python paket bir Django uygulamasıdır. Django proje bir web ana bilgisayarı herhangi bir tek etki alanı adından ayrı giriş noktası sayısını kullanılabileceği olgu yansıtan herhangi bir sayıda uygulamaları içerebilir. Örneğin, contoso.com gibi bir etki alanı için bir Django projesini www.contoso.com için bir uygulama, da support.contoso.com için ikinci bir uygulama ve docs.contoso.com için üçüncü bir uygulama içerebilir. Bu durumda, Django proje site düzeyinde URL Yönlendirme ve ayarları işleme (içinde kendi `urls.py` ve `settings.py` dosyaları), her uygulamanın kendi ayrı stil ve davranış kendi iç yönlendirmesi, görünümler, modelleri, statik dosyalar varken ve yönetim arabirim.

Django uygulamasını, genellikle standart bir dosya kümesi ile başlar. Visual Studio öğe şablonları aynı amaca hizmet eder bir tümleşik menü komutu ile birlikte bir Django projesi içinde Django uygulamayı başlatmak için sağlar:

- : Şablonları **Çözüm Gezgini**, projeye sağ tıklayın ve seçin **Ekle** > **yeni öğe**. İçinde **Yeni Öğe Ekle** iletişim kutusunda, seçin "Django 1.9 uygulama" şablonu belirtin uygulamayı adına **adı** alan ve select **Tamam**.

- Tümleşik komutu: içinde **Çözüm Gezgini**, projeye sağ tıklayın ve seçin **Ekle** > **Django uygulamasını**. Bu komut için bir ad ister ve Django 1.9 uygulamasını oluşturur.

    ![Django uygulama eklemek için menü komutu](media/django/step02-add-django-app-command.png)

Her iki yöntemi kullanarak, "HelloDjangoApp" adlı bir uygulama oluşturun. Sonuç, projenize aşağıdaki tabloda açıklanan öğeleri içeren bu ada sahip bir klasördür.

![Çözüm Gezgini'nde Django uygulama dosyaları](media/django/step02-django-app-in-solution-explorer.png)

| Öğe | Açıklama |
| --- | --- |
| `__init__.py` | Uygulamayı bir paket olarak tanımlayan dosya. |
| `migrations` | Django modelleri yapılan değişikliklerle hizalamak için veritabanı güncelleştirme komut dosyalarını depolayan klasör. Böylece geçerli modelleri eşleşir Django'nın Geçiş Araçları veritabanının önceki bir sürüme daha sonra gerekli değişiklikleri uygulayın. Odağınız modeller üzerinde tutmak geçişler kullanarak ve temel veritabanı şeması işlemek Django sağlayabilirsiniz. Geçişler, 6. adımda ele alınmıştır; şu an için yalnızca klasörde bir `__init__.py` (klasörü kendi Python paket tanımlar gösteren) dosyası. |
| `templates` | Tek bir dosyayı içeren Django sayfa şablonlar için bir klasör `index.html`. İçine bir sayfayı dinamik olarak oluşturmak için bilgileri görünümleri ekleyebilirsiniz HTML bloklarını şablonlarıdır. Şablon "değişkenleri," gibi sayfa `{{ content }}` içinde `index.html`, bu makalenin sonraki bölümlerinde (2. adım) açıklandığı gibi dinamik değerler için yer tutucuları olan. Genellikle Django uygulamaları, uygulama adı ile eşleşen bir alt klasöre yerleştirerek kendi şablonlar için bir ad alanı oluşturun. |
| `admin.py` | Uygulama genişletmek Python dosyası yönetim görmek için kullanılan ve düzenleme verileri bir veritabanında (adım 6'ya bakın) arabirim. Başlangıçta, bu dosyayı deyimi yalnızca içeriyor `from django.contrib import admin`. Varsayılan olarak, Django standart bir yönetim arabirimi girişleri aracılığıyla Django projenin içerir `settings.py` uncommenting mevcut girişlere göre açabilirsiniz dosya `urls.py`. |
| `apps.py` | (Bu tablodan sonraki, aşağıya bakın) uygulaması için yapılandırma sınıfı tanımlayan bir Python dosyası. |
| `models.py` | Modelleri olan İşlevler, görünümleri uygulamanın temel veritabanıyla etkileşim tarafından tanımlanan veri nesneleri (adım 6 bakın). Django veritabanı bağlantı katmanı sunar, böylece uygulamalar kendilerini bu ayrıntılarla ilgilendiren gerek yoktur. `models.py` Dosya Modellerinizi oluşturulacağı varsayılan yerinde olduğundan ve başlangıçta deyimi yalnızca içeriyor `from django.db import models`. |
| `tests.py` | Birim testleri temel yapısını içeren bir Python dosyası. |
| `views.py` | Genellikle, web bir HTTP isteği almak ve bir HTTP yanıt sayfalarını düşüncelerinizi görünümlerdir. Görünümleri genellikle web tarayıcıları nasıl görüntüleneceği hakkında bilmeniz HTML olarak işlemenizi, ancak bir görünüm mutlaka (Ara formu gibi) görünür olmak zorunda değildir. Bir görünümü olan sorumluluğundadır tarayıcıya göndermek için HTML oluşturmak için bir Python işlevi tarafından tanımlanır. `views.py` Dosya görünümleri oluşturmak için varsayılan yerinde olduğundan ve başlangıçta deyimi yalnızca içeriyor `from django.shortcuts import render`. |

İçeriğini `app.py` adı "HelloDjangoApp" kullanırken aşağıdaki gibi görünür:

```python
from django.apps import AppConfig

class HelloDjangoAppConfig(AppConfig):
    name = 'HelloDjango'
```

### <a name="question-is-creating-a-django-app-in-visual-studio-any-different-from-creating-an-app-on-the-command-line"></a>Soru: Django uygulamasını Visual Studio komut satırında bir uygulama oluşturma herhangi farklı oluşturuyor?

Yanıt: Çalışan **Ekle** > **Django uygulamasını** komut veya kullanarak **Ekle** > **yeni öğe** Django uygulama Şablon üreten Django komutu aynı dosyaları `manage.py startapp <app_name>`. Visual Studio'da uygulama oluşturmanın avantajı, uygulama klasörünü ve tüm dosyaları projeye otomatik olarak tümleştirilir ' dir. Projenizde herhangi bir sayıda uygulamaları oluşturmak için aynı Visual Studio komutu kullanabilirsiniz.

## <a name="step-2-2-run-the-app-from-the-django-project"></a>2-2. adım: uygulama Django projeden çalıştırma

Visual Studio'da projeyi yeniden çalıştırırsanız, bu noktada (araç çubuğu düğmesini kullanarak veya **hata ayıklama** > **hata ayıklamayı Başlat**), yine varsayılan sayfasına bakın. Bir uygulamaya özgü sayfası tanımlamak ve uygulama Django projeye eklemek gerektiği için hiçbir uygulama içeriği görünür:

1. İçinde `HelloDjangoApp` klasörü Değiştir `views.py` aşağıdaki "index" adlı bir görünümü tanımlayan kodu eşleştirmek için:

    ```python
    from django.shortcuts import render
    from django.http import HttpResponse

    def index(request):
        return HttpResponse("Hello, Django!")
    ```

1. İçinde `BasicProject` (oluşturulmuş 1. adım), klasör değiştirme `urls.py` en az (tutabilirsiniz yönergeli açıklamaları isterseniz) aşağıdaki kodu eşleştirmek için:

    ```python
    from django.conf.urls import include, url
    import HelloDjangoApp.views

    # Django processes URL patterns in the order they appear in the array
    urlpatterns = [
        url(r'^$', HelloDjangoApp.views.index, name='index'),
        url(r'^home$', HelloDjangoApp.views.index, name='home'),
    ]
    ```

    Hangi Django yönlendirir belirli site göreli URL'leri görünümler her URL deseni açıklar (diğer bir deyişle, sonraki bölümü "https://www.domain.com/"). İlk giriş `urlPatterns` normal ifade ile başlayan `^$` site kökü için yönlendirme "/". İkinci giriş `^home$` özellikle yönlendirir "/ Ev". Herhangi bir sayıda aynı görünüm üretim akışlarına sahip olabilir.

1. "Hello, Django!" projeyi yeniden iletisini görmek için çalıştırın Görünüm tarafından tanımlandığı şekilde. İşiniz bittiğinde sunucusunu durdurun.

### <a name="commit-to-source-control"></a>Kaynak denetimi Yürüt

Kodunuzu değişiklik yaptınız ve bunları başarılı bir şekilde test olduğundan, gözden geçirmek ve kaynak denetimi değişikliklerinizi uygulamak için çok fazla zaman sunulmuştur. Bu öğreticide sonraki adımlarda kaynak denetimine yeniden kaydetmek için uygun saati anımsatmak ve geri bu bölümüne bakın.

1. Gider değişiklikleri düğmesi (aşağıda yuvarlak içine alınmıştır) Visual Studio alt boyunca seçin **Takım Gezgini**.

    ![Visual Studio durum çubuğundaki Kaynak Denetim değişiklikleri düğmesi](media/django/step02-source-control-changes-button.png)

1. İçinde **Takım Gezgini**, "ilk Django uygulaması oluşturma"gibi bir kaydetme iletisi girin ve **tamamlama tüm**. Yürütme tamamlandığında, bir ileti görür "yürütme <hash> yerel olarak oluşturulmuş. Sunucuyla yaptığınız değişiklikleri paylaşmak için eşitleme." Değişiklikleri uzak deponuza iletin isteyip istemediğinizi seçin **eşitleme**seçeneğini belirleyip **itme** altında **giden işlemeleri**. Ayrıca, uzaktan Ftp'den önce birden çok yerel işlemeleri birikebilir.

    ![Takım Gezgini'nde uzak yürütmelerini gönderdiğiniz](media/django/step02-source-control-push-to-remote.png)

### <a name="question-what-is-the-r-prefix-before-the-routing-strings-for"></a>Soru: Yönlendirme dizeleri için önce 'r' öneki nedir?

Yanıt: Python dizesinde 'r' öneki "ham,", Python dize içinde herhangi bir karakteri kaçış değil bildirir anlamına gelir. Normal ifadeler birçok özel karakterler kullanmak için 'r' önekini kullanarak bu dizelerin bir dizi içeriyorsa değerinden okumak kolaylaştırır '\' kaçış karakteri.

### <a name="question-what-do-the--and--characters-mean-in-the-url-routing-entries"></a>Soru: ne ^ ve $ karakterleri anlamı URL yönlendirme girişleri?

Yanıt: URL desenlerini tanımlayan normal ifadelerde ^ "satır başına" anlamına gelir ve "yeniden URL'leri olduğu site köküne göre satırın sonuna," $ anlamına gelir (aşağıdaki bölümü `https://www.domain.com/`). Normal ifade `^$` etkili bir şekilde anlamına gelir "boş" ve bu nedenle tam URL ile eşleşip `https://www.domain.com/` (hiçbir şey site köküne eklenir). Desen `^home$` tam olarak eşleşen `https://www.domain.com/home/`. (Django kullanılmıyor sonunda / desen eşleştirme.)

Normal bir ifade sondaki $ kullanmazsanız olduğu gibi `^home`, URL desenle eşleşen sonra *herhangi* "home", "Ev ödevleri", "yerimizle" ve "home192837" gibi "home" ile başlayan URL.

Farklı Normal ifadelerle denemek için çevrimiçi araçları gibi deneyin [regex101.com](https://regex101.com) adresindeki [pythex.org](http://www.pythex.org).

## <a name="step-2-3-render-a-view-using-html"></a>2-3. adım: HTML kullanarak görünüm işlemek

`index` , O ana kadarki sahip işlevi `views.py` fazlası sayfası için bir düz metin HTTP yanıt oluşturur. Çoğu gerçek web sayfaları, doğal olarak, genellikle canlı verileri birleştirmek zengin HTML sayfaları ile yanıt verir. Oluşturulan içeriği dinamik olarak gerçekten, bir işlev kullanarak görünüm tanımlamak için birincil neden olduğundan.

Çünkü bağımsız değişkeni `HttpResponse` yalnızca bir dize bir dize gibi herhangi bir HTML yukarı oluşturabilirsiniz. Basit bir örnek olarak değiştirmek `index` aşağıdaki kodla işlevi (varolan tutma `from` deyimleri), sayfayı yenileyin her zaman, güncelleştirilen dinamik içerik kullanarak bir HTML yanıtını oluşturur:

```python
from datetime import datetime

def index(request):
    now = datetime.now()

    html_content = "<html><head><title>Hello, Django</title></head><body>"
    html_content += "<strong>Hello Django!</strong> on " + now.strftime("%A, %d %B, %Y at %X")
    html_content += "</body></html>"

    return HttpResponse(html_content)
```

Projeyi yeniden aşağıdakine benzer bir ileti görmek için "**Hello Django!** Pazartesi, 16 Nisan, 2018 16:28:10 üzerinde ". Zamanını güncelleştirin ve içerik her istek ile oluşturulan olduğunu onaylamak için sayfayı yenileyin. İşiniz bittiğinde sunucusunu durdurun.

> [!Tip]
> Proje durdurup kısayolunu kullanmaktır **hata ayıklama** > **yeniden** menü komutu (Ctrl + Shift + F5) veya hata ayıklama araç çubuğundaki yeniden düğmesi:
>
> ![Hata ayıklama araç çubuğunda Visual Studio'yu yeniden başlatın](media/debugging-restart-toolbar-button.png)

## <a name="step-2-4-render-a-view-using-a-page-template"></a>Adım 2-4: bir sayfa şablonu kullanarak görünüm işlemek

Kod oluşturma HTML için çok küçük sayfaları düzgün çalışır, ancak sayfaları daha karmaşık aldıkça genellikle sayfanızı (birlikte, CSS ve JavaScript dosyaları başvurular) statik HTML bölümlerini "içine sonra eklediğiniz sayfasını şablon olarak" dinamik sürdürmek istediğiniz kod tarafından oluşturulmuş içerik. Önceki bölümde, yalnızca tarih ve saat `now.strftime` çağrıdır dinamik, diğer tüm içeriği bir sayfa şablonunda yerleştirilebilen anlamına gelir.

Django sayfası şablonu tarafından işaretleriyle "değişkenleri" olarak adlandırılan değiştirme belirteçleri herhangi bir sayıda içerebilir HTML bloğudur `{{` ve `}}`, olarak `{{ content }}`. Django'nın şablon modülü değişkenleri kodda sağlayan dinamik içerik ile sonra değiştirir.

Aşağıdaki adımlarda, sayfa şablonlarının kullanımı gösterilmektedir:

1. Altında `BasicProject` Django projenin, açık içeren klasör `settings.py` dosya ve uygulama adı, "HelloDjangoApp" ekleyebilirsiniz `INSTALLED_APPS` listesi. Uygulama listesine ekleme, Django proje adının bir uygulama içeren bir klasör olduğunu söyler:

    ```python
    INSTALLED_APPS = [
        'HelloDjangoApp',
        # Other entries...
    ]
    ```

1. Ayrıca, `settings.py`, emin olun `TEMPLATES` nesnesini içeren yüklü bir uygulamanın şablonlarında aramak için Django bildirir (varsayılan olarak dahil), aşağıdaki satırı `templates` klasörü:

    ```json
    'APP_DIRS': True,
    ```

1. İçinde `HelloDjangoApp` klasörü, açık `templates/index.html` bir değişkeni, içerdiği izlemek için sayfa şablon dosyası `{{ content }}`:

    ```html
    <html>
    <head><title></title></head>

    <body>

    {{ content }}

    </body>
    </html>
    ```

1. İçinde `HelloDjangoApp` klasörü, açık `views.py` ve değiştirme `index` işlevini kullanan aşağıdaki kodu kullanarak `django.shortcuts.render` yardımcı işlevi. `render` Yardımcısı, sayfa şablonları ile çalışmak için basitleştirilmiş bir arabirim sağlar. Var olan tüm tuttuğunuzdan emin olun `from` deyimleri.

    ```python
    from django.shortcuts import render   # Added for this step

    def index(request):
        now = datetime.now()

        return render(
            request,
            "index.html",  # Relative path from the 'templates' folder to the template file
            {
                'content': "<strong>Hello Django!</strong> on " + now.strftime("%A, %d %B, %Y at %X")
            }
        )
    ```

    İlk bağımsız değişken `render`, gördüğünüz gibi uygulamanın içinde şablon dosyası için göreli yol üzerinden izlenen istek nesnesi `templates` klasör. Bir şablon dosyası destekliyorsa, görünüm için uygunsa olarak adlandırılır. Üçüncü bağımsız değişkeni `render` şablon başvurduğu değişkenleri sözlüğü ise. Nesneler sözlükte içerebilir, şablon bir değişkende durumda başvurabilirsiniz `{{ object.property }}`.

1. Projeyi çalıştırın ve çıktıyı inceleyin. 2-2, şablon çalıştığını gösteren görülen bu adıma benzer bir ileti görürsünüz.

    Ancak, HTML olarak kullandığınız gözlemlemek `content` özelliği, çünkü yalnızca düz metin olarak işleyen `render` işlevi otomatik olarak bu HTML çıkışları. Kaçış otomatik yanlışlıkla güvenlik açıklarına ekleme saldırıları önlemek: geliştiriciler genellikle giriş sayfadan toplayın ve şablon yer tutucu aracılığıyla başka bir değer olarak kullanın. Kaçış Ayrıca, yeniden HTML sayfası şablonu ve kod dışında tutmak en iyi olduğunu anımsatıcısı görevi görür. Neyse ki, bu ek değişkenleri oluşturmak üzere bir basit konudur gerektiğinde. Örneğin, değiştirme `templates/index.html` sayfa başlığı ve tutar sayfa şablonunun tüm biçimlendirme ekler aşağıdaki biçimlendirme eşleştirmek için:

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

    Ardından yazma `index` işlevi sayfa şablonunda tüm değişkenlerin değerlerini sağlamak için aşağıdaki gibi görüntüleyin:

    ```python
    def index(request):
        now = datetime.now()

        return render(
            request,
            "index.html",  # Relative path from the 'templates' folder to the template file
            {
                'title' : "Hello Django",
                'message' : "Hello Django!",
                'content' : " on " + now.strftime("%A, %d %B, %Y at %X")
            }
        )
    ```

1. Sunucu stop ve projeyi yeniden başlatın ve sayfa artık doğru şekilde oluşturulduğunu inceleyin:

    ![Şablon kullanılarak çalışan uygulama](media/django/step02-result.png)

1. <a name="template-namespacing"></a>Son adım olarak, bir ad oluşturur ve projeye eklemiş olabileceğiniz diğer uygulamalarla olası çakışmaları ortadan kaldırır, uygulamanızın aynı adlı bir alt klasör içine şablonlarınızı taşıyın. Diğer bir deyişle, bir alt klasöründe oluşturun `templates` adlı `HelloDjangoApp`, taşıma `index.html` o alt klasörü içine ve değiştirme `index` görüntülemek şablonun yeni yoluna başvurmak için işlevi `HelloDjangoApp/index.html`. Projeyi çalıştırın, sayfanın düzgün işler doğrulayın ve sunucusunu durdurun.

1. Kaynak Denetim ve uzak deponuza isterseniz, altında açıklandığı gibi güncelleştirmek için değişiklikleri [adım 2-2](#commit-to-source-control).

### <a name="question-do-page-templates-have-to-be-in-a-separate-file"></a>Soru: sayfa şablonları ayrı bir dosyaya olması gerekir mi?

Yanıt: şablonları genellikle ayrı HTML dosyalarında saklanır karşın, aynı zamanda bir satır içi şablon kullanabilirsiniz. Ayrı bir dosya kullanarak, ancak, biçimlendirme ve kodun arasında temiz bir ayrım korumak için önerilir.

### <a name="question-must-templates-use-the-html-file-extension"></a>Soru: şablonları .html dosya uzantısı kullanmalısınız?

Yanıt: `.html` için sayfa şablon dosyalarını uzantıdır tamamen isteğe bağlı ikinci bağımsız değişkeni dosyasında tam göreli yolunu her zaman belirttikleri `render` işlevi. Ancak, Visual Studio (ve diğer düzenleyicileri) genellikle ile kod tamamlama ve sözdizimi coloration gibi özellikleri size `.html` şablonları sayfasında olgu ağır dosyaları olmayan kesinlikle HTML.

Aslında, Django projeyle çalışırken, Visual Studio otomatik olarak düzenlediğiniz HTML dosyası gerçekte bir Django şablonu olduğunda algılar ve bazı otomatik tamamlama özellikleri sağlar. Örneğin, başlattığınızda bir Django sayfa şablonu yorum yazarak `{#`, Visual Studio otomatik olarak size kapanış `#}` karakter. **Açıklama Seçimi** ve **açıklamadan çıkarın seçimi** komutları (üzerinde **Düzenle** > **Gelişmiş** menü ve araç çubuğundaki) Ayrıca şablonu açıklamaları yerine HTML açıklamaları kullanın.

### <a name="question-when-i-run-the-project-i-see-an-error-that-the-template-cannot-be-found-whats-wrong"></a>Soru: Proje çalıştırdığınızda, şablonu bulunamıyor hatayla görüyorum. Ne oldu?

Yanıt: şablonu bulunamıyor hatalar görürseniz, Django projenin için uygulama eklediğinizden emin olun `settings.py` içinde `INSTALLED_APPS` listesi. Bu girişi uygulamanın içinde aramak için Django bilemezsiniz `templates` klasör.

### <a name="question-why-is-template-namespacing-important"></a>Soru: Şablon namespacing neden önemlidir?

Yanıt: Django başvurulan bir şablon göründüğünde `render` işlevi, göreli yolu ile eşleşen bulduğu ilk ne olursa olsun dosyasını kullanır. Aynı projede şablonları için aynı klasör yapısını kullanan birden fazla Django uygulamalar varsa, o uygulama tek bir şablon başka bir uygulamadan kasıtsız olarak kullanacağınız olasıdır. Bu tür hatalarını önlemek için her zaman bir uygulamanın altında bir alt klasör oluştur `templates` tüm yinelemesinden kaçınmak için uygulama adıyla eşleşen klasör.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Statik dosyaları işleme, sayfa ekleyin ve şablon devralma kullanın](learn-django-in-visual-studio-step-03-serve-static-files-and-add-pages.md)

## <a name="go-deeper"></a>Derinlemesine

- [İlk Django uygulamanız yazma, bölüm 1 - görünümleri](https://docs.djangoproject.com/en/2.0/intro/tutorial01/#write-your-first-view) (docs.djangoproject.com)
- Daha fazla Django şablonları, içerir gibi ve yeteneklerini devralma için bkz: [Django şablonu dili](https://docs.djangoproject.com/en/2.0/ref/templates/language/) (docs.djangoproject.com)
- [Normal ifade eğitim üzerinde inLearning](https://www.linkedin.com/learning/topics/regular-expressions) (LinkedIn)
- Öğretici kaynak kodu github'da: [Microsoft/python-örnek-vs-learning-django](https://github.com/Microsoft/python-sample-vs-learning-django)