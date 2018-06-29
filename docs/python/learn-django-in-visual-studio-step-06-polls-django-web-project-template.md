---
title: Öğretici - Visual Studio, adım 6 Django öğrenin
description: Visual Studio projeleri, özellikle yönetimsel özelleştirme gibi yoklamalar Django Web projesi şablonu özelliklerini bağlamında Django temel bir kılavuz.
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
ms.openlocfilehash: d88f1e258bf8aa9801555c256f825841fff9d476
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089509"
---
# <a name="step-6-use-the-polls-django-web-project-template"></a>6. adım: yoklamalar Django Web projesi şablonu kullanın

**Önceki adımda: [Django kullanıcıların kimlik doğrulaması](learn-django-in-visual-studio-step-05-django-authentication.md)**

Visual Studio'nun "Django Web projesi" şablonu anladım şimdi üçüncü Django şablon "Yoklamalar Django Web aynı kod temeli üzerinde oluşturur ve bir veritabanı ile çalışmayı gösteren projesi", bakabilirsiniz.

Bu adımda, bilgi nasıl yapılır:

> [!div class="checklist"]
> - Proje şablonu oluşturma ve veritabanını başlatılamadı (adım 6 - 1)
> - Veri modelleri (adım 6-2) Anlama
> - Geçişleri (6-3. adım) uygulayın
> - Proje şablonu (adım 6-4) tarafından oluşturulan sayfa şablonları ve görünümler anlama
> - Özel Yönetim Arabirimi (adım 6-5) oluşturma

Bu şablon kullanılarak oluşturulan bir proje ne izleyerek almanız için benzer [ilk Django uygulamanız yazma](https://docs.djangoproject.com/en/2.0/intro/tutorial01/) Django belgeleri Öğreticisi. Web uygulaması yoklamalar görüntülemek ve bunları, anketler üzerinden yönetebileceğiniz bir özel yönetim arabirimi ile birlikte oy kişiler olanak sağlayan ortak bir sitesi oluşur. "Django Web projesi" şablon olarak aynı kimlik doğrulama sistemini kullanır ve aşağıdaki bölümlerde Django modelleri keşfedilen olarak uygulayarak veritabanının daha fazla kullanılmasını sağlar.

## <a name="step-6-1-create-the-project-and-initialize-the-database"></a>6-1. adım: Proje oluşturma ve veritabanını başlatılamadı

1. Visual Studio'da Git **Çözüm Gezgini**, bu öğreticide daha önce oluşturulan "LearningDjango" çözüme sağ tıklayın ve seçin **Ekle** > **yeni proje**. (Alternatif olarak, yeni bir çözüm kullanmak isteyip istemediğinizi seçin **dosya** > **yeni** > **proje** yerine.)

1. Yeni Proje iletişim kutusunda, aramak ve "Yoklamalar Django Web projesi" şablonunu seçin, proje "DjangoPolls" arayın ve seçin **Tamam**.

1. Diğer proje şablonları gibi Visual Studio'da, "Yoklamalar Django Web projesi" şablonu içeren bir `requirements.txt` , Visual Studio komut istemlerini ister where bu bağımlılıkların yüklemek için dosya. Seçeneği **sanal bir ortama yükleme**hem de **sanal ortam Ekle** iletişim kutusunda **oluşturma** Varsayılanları kabul etmek için.

1. Python sanal ortamı kurma tamamlandıktan sonra görüntülenen'ndaki yönergeleri izleyin `readme.html` veritabanını başlatılamadı ve Django süper kullanıcı (diğer bir deyişle, bir yönetici) oluşturmak için. Önce "DjangoPolls" projeye sağ adımlardır **Çözüm Gezgini**seçin **Python** > **Django geçirmek** , sonra komutu Projeyi tekrar sağ tıklayın, **Python** > **Django süper kullanıcı oluşturma** komut ve yönergeleri izleyin. (Süper kullanıcı ilk oluşturmayı denerseniz, veritabanı henüz başlatılmamış olduğundan bir hata görürsünüz.)

1. "DjangoPolls" projesini bu projeye sağ tıklayarak Visual Studio çözümü için varsayılan olacak şekilde ayarlayın **Çözüm Gezgini** ve seçerek **başlangıç projesi olarak ayarla**. Gösterilen başlangıç projesi içinde hata ayıklayıcı başlatıldığında ne çalıştırılan kalın.

1. Seçin **hata ayıklama > hata ayıklamayı Başlat** (F5) veya **Web sunucusu** sunucu çalıştırmak için araç çubuğunda:

    ![Visual Studio'da Web sunucusu Çalıştır araç çubuğu düğmesi](media/django/run-web-server-toolbar-button.png)

1. Şablon tarafından oluşturulan uygulama hakkında ev ve üst gezinti çubuğu'nu kullanma arasında gidin, ilgili kişi, üç sayfaları vardır. Bir veya iki farklı kısımlarını uygulama incelemek için dakika alın (hakkında ve iletişim sayfaları "Django Web projesi için" çok benzer ve daha ayrıntılı ele alınan değil).

    ![Yoklamalar Django Web projesi uygulamasının tam tarayıcı görünümü](media/django/step06-full-app-view.png)

1. Ayrıca **Yönetim** yönetim arabirimini yalnızca yetkili olduğunu göstermek için bir oturum açma ekranı görüntüler gezinti çubuğunda bağlantı kimlik doğrulaması yöneticileri. Süper kullanıcı kimlik bilgilerini kullanın ve yönlendirilen "/ Yönetici" sayfasında, bu proje şablonunu kullanarak, varsayılan olarak etkindir.

    ![Yoklamalar Django Web projesi uygulamasının yönetim görünümü](media/django/step06-polls-administrative-interface.png)

1. Aşağıdaki bölümlerde için çalışan uygulama bırakabilirsiniz.

    Uygulama durdurmak istiyorsanız ve [değişiklikleri kaynak denetimine](learn-django-in-visual-studio-step-02-create-an-app.md#commit-to-source-control), ilk açmak **değişiklikleri** sayfasındaki **Takım Gezgini**, sanal ortama (klasörünü sağ tıklatın büyük olasılıkla `env`) ve seçin **bu yerel öğeleri Yoksay**.

### <a name="examine-the-project-contents"></a>Proje içeriğini inceleyin

Önce belirtildiği gibi. ne olduğu kadar "Yoklamalar Django Web projesi" şablondan oluşturulmuş bir projeyi Visual Studio diğer proje şablonlarını incelediniz ise bilgi sahibi olmanız gerekir. Bu makalede ek adımlar daha önemli değişiklikler ve eklemeler, veri modelleri ve ek görünümler özetler.

### <a name="question-what-does-the-django-migrate-command-do"></a>Soru: Django geçirmek komutu ne yapar?

Yanıt: **Django geçirmek** komutu özellikle çalışır `manage.py migrate` komut dosyalarını çalıştırır komut içinde `app/migrations` önceden çalıştırılmış henüz klasör. Bu durumda, komutu çalıştırır `0001_initial.py` veritabanında gerekli şema ayarlamak için bu klasördeki komut dosyası.

Geçiş komut tarafından oluşturulan `manage.py makemigrations` uygulamanın tarar komutu `models.py` dosya, veritabanının geçerli durumu için karşılaştırır ve geçerli modelleri eşleştirmek için veritabanı şeması geçirmek için gereken komut dosyalarını oluşturur. Güncelleştirme ve zaman içinde Modellerinizi değiştirirken bu Django çok güçlü özelliğidir. Oluşturma ve geçişin çalıştırılması, modelleri ve veritabanı biraz güçlükle eşitleme tutun.

Bu makalenin sonraki bölümlerinde 6-3. adımda geçiş ile çalışır.

## <a name="step-6-2-understand-data-models"></a>6-2. adım: veri modelleri anlama

Yoklama ve seçim, adlandırılmış uygulama modellerini tanımlanan `app/models.py`. Her türeyen bir Python sınıftır `django.db.models.Model` ve yöntemlerini kullanan `models` gibi sınıf `CharField` ve `IntegerField` veritabanı sütun eşleme modelinde alanlarını tanımlamak için.

```python
from django.db import models
from django.db.models import Sum

class Poll(models.Model):
    """A poll object for use in the application views and repository."""
    text = models.CharField(max_length=200)
    pub_date = models.DateTimeField('date published')

    def total_votes(self):
        """Calculates the total number of votes for this poll."""
        return self.choice_set.aggregate(Sum('votes'))['votes__sum']

    def __unicode__(self):
        """Returns a string representation of a poll."""
        return self.text

class Choice(models.Model):
    """A poll choice object for use in the application views and repository."""
    poll = models.ForeignKey(Poll)
    text = models.CharField(max_length=200)
    votes = models.IntegerField(default=0)

    def votes_percentage(self):
        """Calculates the percentage of votes for this choice."""
        total = self.poll.total_votes()
        return self.votes / float(total) * 100 if total > 0 else 0

    def __unicode__(self):
        """Returns a string representation of a choice."""
        return self.text
```

Gördüğünüz gibi bir yoklama açıklama tutar kendi `text` alan ve bir yayımın Tarih içinde `pub_date`. Bu alanlar yoklama veritabanındaki mevcut yalnızca olanlardır; `total_votes` çalışma zamanında hesaplanmış alan.

Seçim bir yoklama ile ilgili `poll` alan, bir tanım içeriyor `text`ve bu seçenek için bir sayımı tutar `votes`. `votes_percentage` Alanını çalışma zamanında hesaplanır ve veritabanında bulunamadı.

Alan türlerinin tam listesi `CharField` (sınırlı metin) `TextField` (sınırsız metin), `EmailField`, `URLField`, `DateTimeField`, `IntegerField`, `DecimalField`, `BooleanField`, `ForeignKey`, ve `ManyToMany`. Her bir alan gibi bazı öznitelikler alır `max_length`. `blank=True` Özniteliği anlamına gelir Bu alan isteğe bağlıdır; olur `null=true` değeri isteğe bağlı olduğu anlamına gelir. Ayrıca bir `choices` veri gösterimini/değer tanımlama grubu dizisindeki değerleri sınırlar özniteliği. (Bkz [Model alanı başvurusu](https://docs.djangoproject.com/en/2.0/ref/models/fields/) Django belgelerinde.)

Tam olarak ne inceleyerek veritabanında depolanır onaylayabilirsiniz `db.sqlite3` gibi bir araç kullanarak proje dosyasında [SQLite tarayıcı](http://sqlitebrowser.org/). Veritabanında bir yabancı anahtar alanı ister bkz `poll` seçenek model olarak depolanan `poll_id`; Django işleme eşleme otomatik olarak.

Genel olarak, Django veritabanınızda çalışmak Django sizin adınıza temel alınan veritabanı yönetebilmeniz için özel olarak modelleri arasında çalışma anlamına gelir.

### <a name="seed-the-database-from-samplesjson"></a>Çekirdek samples.json veritabanından

Başlangıçta, veritabanı hiçbir yoklamalar içerir. Konumunda bir yönetim arabirimi kullanabilirsiniz "/ admin" yoklar el ile eklemek için URL ve ayrıca "/ üretim" sayfasında uygulamanın içinde tanımlanan yoklamalar çekirdek veritabanı eklemek için çalışan sitesinde ziyaret edebilirsiniz `samples.json` dosya.

Django projenin `urls.py` eklenen bir URL deseni sahip `url(r'^seed$', app.views.seed, name='seed'),`. `seed` Görünümünde `app/views.py` yükler `samples.json` dosya ve gerekli model nesneleri oluşturur. Django sonra otomatik olarak eşleşen kayıtları temel veritabanında oluşturur.

Kullanımına dikkat edin `@login_required` görünüm için yetki düzeyini belirtmek için oluşturma öğesi.

```python
@login_required
def seed(request):
    """Seeds the database with sample polls."""
    samples_path = path.join(path.dirname(__file__), 'samples.json')
    with open(samples_path, 'r') as samples_file:
        samples_polls = json.load(samples_file)

    for sample_poll in samples_polls:
        poll = Poll()
        poll.text = sample_poll['text']
        poll.pub_date = timezone.now()
        poll.save()

        for sample_choice in sample_poll['choices']:
            choice = Choice()
            choice.poll = poll
            choice.text = sample_choice
            choice.votes = 0
            choice.save()

    return HttpResponseRedirect(reverse('app:home'))
```

Etkisini görmek için önce görmek için uygulama hiçbir yoklamalar çalıştırma henüz mevcut. "/ Üretim" URL'yi ziyaret edin ve uygulamayı giriş sayfasına geri döndüğünde yoklamaları kullanılabilir duruma gelmiş görmeniz gerekir. Yeniden ham inceleyin çekinmeyin `db.sqlite3` dosyası gibi bir araçla [SQLite tarayıcı](http://sqlitebrowser.org/).

![Kapsanan bir veritabanı ile yoklamalar Django Web projesi uygulama](media/django/step06-app-with-seeded-database.png)

### <a name="question-is-it-possible-to-initialize-the-database-using-the-django-administrative-utility"></a>Soru: veritabanını başlatılamadı mümkün Django yönetim yardımcı programı kullanıyor mu?

Yanıt: Evet, kullanabileceğiniz [django yönetim loaddata komutu](https://docs.djangoproject.com/en/1.9/ref/django-admin/#loaddata) dengeli dağıtım sayfanın uygulama gibi aynı görevi gerçekleştirmenin. Bir tam web uygulaması üzerinde çalışırken, iki yöntemlerinin bir birleşimini kullanabilirsiniz: komut satırından bir veritabanını başlatılamadı sonra çekirdek sayfada herhangi bir rastgele JSON göndermek bir API burada yerine bağlı olan bir sabit kodlanmış dosyayı dönüştürmek.

## <a name="step-6-3-use-migrations"></a>6-3. adım: geçişler kullanın

Ne zaman çalıştırıldığı `manage.py makemigrations` (Visual Studio'da bağlam menüsünü kullanarak) komutunu projesi oluşturduktan sonra Django oluşturulan dosya `app/migrations/0001_initial.py` dosya. Bu dosya, ilk veritabanı tablolarını oluşturur bir komut dosyası içerir.

Kaçınılmaz olarak Modellerinizi için zaman içinde değişiklik çünkü Django temel alınan veritabanı şeması bu modelleri ile güncel tutmanızı kolaylaştırır. Genel iş akışı aşağıdaki gibidir:

1. Modellerinde değişiklik, `models.py` dosya.
1. Visual Studio'da'nde projeye sağ **Çözüm Gezgini** seçip **Python** > **Django olun geçişler** komutu. Bu komut, komut dosyalarında oluşturur, daha önce açıklandığı gibi `app/migrations` veritabanı geçerli durumunu yeni duruma geçirmek için.
1. Komut dosyalarını da asıl veritabanını uygulamak için projeyi tekrar sağ tıklayın ve seçin **Python** > **Django geçirmek**.

Geçiş komutu çalıştırdığınızda, Django hangi geçişler gerekli uygular, Django verilen herhangi bir veritabanı için hangi geçiş uygulanmadı izler. Yeni, boş bir veritabanı oluşturursanız, örneğin, geçirme komutunu çalıştırarak geçerli Modellerinizi ile güncel her geçiş komut dosyası uygulayarak taşır. Birden çok model değişiklikleri yapın ve geliştirme bilgisayarındaki geçişler oluşturmak, benzer şekilde, daha sonra toplu geçişler üretim veritabanınız üretim sunucunuzda geçirme komutu çalıştırarak uygulayabilirsiniz. Django yeniden üretim veritabanının son geçiş bu yana oluşturulan geçiş betikleri geçerlidir.

Bir model değiştirme etkisini görmek için aşağıdaki adımları deneyin:

1. Yoklama modelinde isteğe bağlı Yazar alanı eklemek `app/models.py` sonra aşağıdaki satırı ekleyerek `pub_date` isteğe bağlı bir eklemek için alanı `author` alan:

    ```python
    author = models.CharField(max_length=100, blank=True)
    ```

1. Dosyayı kaydedin, sonra "DjangoPolls" projeye sağ **Çözüm Gezgini** seçip **Python** > **Django olun geçişler** komutu.
1. Seçin **proje** > **tüm dosyaları göster** yeni oluşturulan komut dosyasında görmek için komutu `migrations` klasör adı ile başlayan, `002_auto_`. Dosya ve seçin, sağ tıklatma **projeye dahil et**. Ardından **proje** > **tüm dosyaları göster** yeniden orijinal görünüme geri yüklemek için. (Aşağıda ikinci soruyu Ayrıntılar için bu adımı bakın.)
1. İsterseniz, nasıl Django önceki model durumu yeni bir durum değişikliği komutlar incelemek için bu dosyayı açın.
1. Visual Studio projesi tekrar sağ tıklayın ve seçin **Python** > **Django geçirmek** veritabanına değişiklikleri uygulamak için.
1. İsterseniz, veritabanını Değişikliği onaylamak için uygun bir görüntüleyicide açın.

Genel olarak, Django'nın geçiş özelliğini hiç veritabanı şemanızı el ile yönettiğiniz anlamına gelir. Yalnızca Modellerinizi için değişiklik, geçiş komut dosyaları oluşturmak ve bunları geçirme komutuyla uygulayabilirsiniz.

### <a name="question-what-happens-if-i-forget-to-run-the-migrate-command-after-making-changes-to-models"></a>Soru: modellerine değişiklikleri yaptıktan sonra geçirme komutu çalıştırmak unutursanız ne olur?

Yanıt: modelleri veritabanında nedir eşleşmiyorsa, Django uygun özel durumları ile çalışma zamanında başarısız olur. Önceki bölümde gösterilen model değişikliği geçirmek unutursanız, örneğin, bir hata göreceğiniz "gibi bir sütun yok: app_poll.author":

![Ne zaman bir model değişikliği geçirildi gösterilen hata](media/django/step06-exception-when-forgetting-to-migrate.png)biçimindeki telefon numarasıdır.

### <a name="question-why-doesnt-solution-explorer-show-newly-generated-scripts-after-running-django-make-migrations"></a>Soru: Django olun geçişler çalıştırdıktan sonra Çözüm Gezgini yeni oluşturulan Göster komut neden değil mi?

Yanıt: rağmen yeni oluşturulan komut mevcut `app/migrations` klasörü uygulanır çalıştırırken **Django geçirmek** komutu, bunlar görünmez otomatik **Çözüm Gezgini** çünkü Bunlar için Visual Studio projesi eklendiniz değil. Onları görünür yapmak için önce seçin **proje** > **tüm dosyaları göster** menü komutunu veya aşağıdaki resimde gösterilen araç çubuğu düğmesi. Bu komut neden **Çözüm Gezgini** projeye eklenmediğini öğeleri için bir noktalı anahat simgesini kullanarak proje klasöründen tüm dosyaları göstermek için. Ekleme ve seçmek için istediğiniz dosyaları sağ **projeye dahil et**, hangi de içeren bunları sonraki yürütme kaynak denetimiyle.

![Çözüm Gezgini'nde proje komutu dahil](media/django/step06-include-migrations-script-in-project.png)

### <a name="question-can-i-see-what-migrations-would-be-applied-before-running-the-migrate-command"></a>Soru: hangi geçişler geçirme komutunu çalıştırmadan önce uygulanacak görebilirim?

Yanıt: Evet, kullan [django yönetim showmigrations komutu](https://docs.djangoproject.com/en/2.0/ref/django-admin/#showmigrations).

## <a name="step-6-4-understand-the-views-and-page-templates-created-by-the-project-template"></a>Adım 6-4: görünümleri anlamak ve sayfa proje şablonu tarafından oluşturulan şablonlar

Çoğu "Yoklamalar Django Web projesi" şablon tarafından oluşturulan görünümlerini hakkında ve iletişim için görünümleri gibi sayfa, "Django Web projesi" şablonu ile oluşturulan görünümleri, çalıştığınız ile Bu öğreticide daha önce oldukça benzer. Uygulama kendi giriş sayfası olarak modellerinin, kullanır yapmasıdır Yoklamalarda farklıdır oylama ve yoklama sonuçları görüntülemek için sayfa eklendi.

İlk satır Django projenin başından itibaren `urlpatterns` içinde dizi `urls.py` dosyasıdır daha fazlasını bir basit bir uygulama görünümüne yönlendirme. Bunun yerine, uygulamanın içinde kendi çeker `urls.py` dosyası:

```python
from django.conf.urls import url, include
import app.views

urlpatterns = [
    url(r'^', include('app.urls', namespace="app")),
    # ..
]
```

`app/urls.py` Dosya biraz daha ilginç yönlendirme kod (Açıklama eklenen) içeriyorsa:

```python
urlpatterns = [
    # Home page routing
    url(r'^$',
        app.views.PollListView.as_view(
            queryset=Poll.objects.order_by('-pub_date')[:5],
            context_object_name='latest_poll_list',
            template_name='app/index.html',),
        name='home'),

    # Routing for a poll page, which use URLs in the form <poll_id>/,
    # where the id number is captured as a group named "pk".
    url(r'^(?P<pk>\d+)/$',
        app.views.PollDetailView.as_view(
            template_name='app/details.html'),
        name='detail'),

    # Routing for <poll_id>/results pages, again using a capture group
    # named pk.
    url(r'^(?P<pk>\d+)/results/$',
        app.views.PollResultsView.as_view(
            template_name='app/results.html'),
        name='results'),

    # Routing for <poll_id>/vote pages, with the capture group named
    # poll_id this time, which becomes an argument passed to the view.
    url(r'^(?P<poll_id>\d+)/vote/$', app.views.vote, name='vote'),
]
```

Burada kullanılan daha karmaşık normal ifadeler bilmiyorsanız ifadenin içine yapıştırabilirsiniz [regex101.com](https://regex101.com/) düz dilde bir açıklama için. (Eğik kaçış gerekir `/` ters eğik çizgi ekleyerek `\` daha önce; kaçışı nedeniyle python'da gerekli değil `r` "ham" anlamına gelen dize öneki).

Django, söz dizimi içinde `?P<name>pattern` adlı bir grup oluşturur `name`, hangi geçirilen bağımsız değişken olarak göründükleri sırada için görünümleri. Daha önce gösterilen kodda `PollsDetailView` ve `PollsResultsView` adlı bir bağımsız değişken alma `pk` ve `app.views.vote` adlı bir bağımsız değişken alan `poll_id`.

Görünümleri çoğunu görünüm işlevinde yalnızca doğrudan başvurular olmadığını da görebilirsiniz `app/views.py`. Bunun yerine, çoğu türetilen, aynı dosya sınıfında başvurmak `django.views.generic.ListView` veya `django.views.generic.DetailView`. Temel sınıflar sağlar `as_view` ele yöntemleri bir `template_name` şablonunu belirlemek için bağımsız değişken. `ListView` Giriş sayfası için kullanılan temel sınıfı da bekliyor bir `queryset` verileri içeren özellik ve `context_object_name` kullanmak istediğiniz verilere şablonunda, bu durumda başvurmak üzere değişken adında özellik `latest_poll_list`.

İnceleyebilirsiniz artık `PollListView` giriş sayfası için tanımlanan şekilde de `app/views.py`:

```python
class PollListView(ListView):
    """Renders the home page, with a list of all polls."""
    model = Poll

    def get_context_data(self, **kwargs):
        context = super(PollListView, self).get_context_data(**kwargs)
        context['title'] = 'Polls'
        context['year'] = datetime.now().year
        return context
```

Burada yapılır olan Görünüm çalışır (yoklama ile) ve geçersiz kılmalar model tanımlamak için `get_context_data` ekleme yöntemi `title` ve `year` değerleri bağlama.

Şablon çekirdek (`templates/app/index.html`) aşağıdaki gibidir:

```html
{% if latest_poll_list %}
<table class="table table-hover">
    <tbody>
        {% for poll in latest_poll_list %}
        <tr>
            <td>
                <a href="{% url 'app:detail' poll.id %}">{{poll.text}}</a>
            </td>
        </tr>
        {% endfor %}
    </tbody>
</table>
{% else %}
<!-- ... other content omitted ... -->
{% endif %}
```

Basitçe, şablon yoklama nesneleri listesini alır `latest_poll_list`ve yoklama 's kullanarak her yoklama bağlantı içeren bir tablo satırının oluşturmak için bu listeyi dolaşır `text` değeri. İçinde `{% url %}` etiketi, "app:detail" url desende başvurduğu `app/urls.py` ", kullanarak ayrıntı" adlı `poll.id` bağımsız değişken olarak. Bunun etkisi Django uygun desen kullanan bir URL oluşturur ve bağlantısını kullanan ' dir. Bu bit gelecekteki sağlama anlamına gelir, bu URL deseni dilediğiniz zaman ve oluşturulan bağlantılar otomatik olarak değiştirebilir, eşleşecek şekilde güncelleştirin.

`PollDetailView` Ve `PollResultsView` sınıfları `app/views.py` (burada gösterilmiyor) neredeyse aynı konum `PollListView` öğesinden türetilen dışında `DetailView` yerine. Kendi ilgili şablonları `app/templates/details.html` ve `app/templates/results.html` çeşitli HTML denetimlerini içinde modellerinden uygun alanları yerleştirin. Bir benzersiz parçada `details.html` bir yoklama seçenekleri içinde bulunan olan bir HTML formu gönderildiğinde /vote URL'sine bir POST yapar. Daha önce görüldüğü gibi bu URL deseni yönlendirilir `app.views.vote`, hangi gerçekleştirilir gibi (Not `poll_id` yeniden yönlendirme bu görünüm için kullanılan normal ifade adlandırılmış bir grupta mı bağımsız değişkeni):

```python
def vote(request, poll_id):
    """Handles voting. Validates input and updates the repository."""
    poll = get_object_or_404(Poll, pk=poll_id)
    try:
        selected_choice = poll.choice_set.get(pk=request.POST['choice'])
    except (KeyError, Choice.DoesNotExist):
        return render(request, 'app/details.html', {
            'title': 'Poll',
            'year': datetime.now().year,
            'poll': poll,
            'error_message': "Please make a selection.",
    })
    else:
        selected_choice.votes += 1
        selected_choice.save()
        return HttpResponseRedirect(reverse('app:results', args=(poll.id,)))
```

Burada, görünümü diğer sayfalar gibi ilgili kendi şablonu yoktur. Bunun yerine, yoklama (birisi "oy/1a2b3c" gibi bir URL'sini girer olasılığına) yok, 404 yanıtı gösteren seçili yoklama doğrular. Ardından, voted seçimi yoklama için geçerli olduğundan emin olur. Aksi takdirde, `except` bloğu yalnızca bir hata iletisiyle yeniden Ayrıntılar sayfası oluşturur. Seçimi geçerliyse, görünüm oy hesaplar ve sonuçları sayfasına yönlendirir.

## <a name="step-6-5-create-a-custom-administration-interface"></a>6-5. adım: özel yönetim arabirimi oluşturma

Son "Yoklamalar Django Web projesi" şablonu varsayılan Django yönetim arabirimi, 6-1. adım altında bu makalede daha önce gösterildiği gibi özel uzantılara parçalarıdır. Varsayılan arabirim kullanıcı ve Grup Yönetimi sağlar, ancak hiçbir şey için daha fazla. Anketler proje şablonu de yoklamalar yönetmenize olanak özellikleri ekler.

Öncelikle, URL düzenleri Django projenin `urls.py` sahip `url(r'^admin/', include(admin.site.urls)),` varsayılan olarak; dahil "Yönetici/doc" deseni de tarafından kılınmıştır bulunmaktadır.

Uygulamanın dosya içeriyorsa `admin.py`, eklenmesi, sayesinde bir yönetim arabirimi ziyaret ettiğinizde, Django otomatik olarak çalışan `django.contrib.admin` içinde `INSTALLED_APPS` dizisi `settings.py`. Bu dosya kodda proje şablonu tarafından sağlanan şu şekildedir:

```python
from django.contrib import admin
from app.models import Choice, Poll

class ChoiceInline(admin.TabularInline):
    """Choice objects can be edited inline in the Poll editor."""
    model = Choice
    extra = 3

class PollAdmin(admin.ModelAdmin):
    """Definition of the Poll editor."""
    fieldsets = [
        (None, {'fields': ['text']}),
        ('Date information', {'fields': ['pub_date']}),
    ]
    inlines = [ChoiceInline]
    list_display = ('text', 'pub_date')
    list_filter = ['pub_date']
    search_fields = ['text']
    date_hierarchy = 'pub_date'

admin.site.register(Poll, PollAdmin)
```

Gördüğünüz gibi `PollAdmin` sınıfı türer `django.contrib.admin.ModelAdmin` ve adlarından kullanarak kendi alan sayısını özelleştirir `Poll` yönettiği modeli. Bu alanlar üzerinde açıklanan [ModelAdmin seçenekleri](https://docs.djangoproject.com/en/2.0/ref/contrib/admin/#modeladmin-options) Django belgelerinde.

Çağrı `admin.site.register` ardından o sınıfın modele bağlanır (`Poll`) ve yönetim arabirimi içerir. Genel sonuç aşağıda gösterilmiştir:

![Yoklamalar Django Web projesi uygulamasının yönetim görünümü](media/django/step06-polls-administrative-interface.png)

## <a name="next-steps"></a>Sonraki adımlar

> [!Note]
> Visual Studio çözümünüzü kaynak denetimine Bu öğreticinin boyunca yürüten, başka bir yürütme yapmak için iyi bir zamandır sunulmuştur. Çözümünüzü öğretici kaynak kodu github'da eşleşmesi gerekir: [Microsoft/python-örnek-vs-learning-django](https://github.com/Microsoft/python-sample-vs-learning-django).

Visual Studio'da "Boş Django Web projesi", "Django Web projesi" ve "Yoklamalar Django Web projesi" şablonları tamamen şimdi incelediniz. Tüm görünümler ve şablonlar kullanarak gibi Django öğrendiğinize ve yönlendirme, kimlik doğrulama ve veritabanı modelleri kullanarak denedikten. Artık tüm görünümler ve ihtiyacınız modelleri kendi web uygulaması oluşturmak mümkün olması gerekir.

Bir web uygulaması geliştirme bilgisayarınızda çalışan uygulama müşterileriniz için kullanılabilir hale getirme yalnızca bir adımdır. Sonraki adımlar aşağıdaki görevler de dahil:

- Web uygulamasını Azure App Service gibi bir üretim sunucusu dağıtın. Bkz: [Azure App Service Yayımla](publishing-python-web-applications-to-azure-from-visual-studio.md), Django uygulamaları için gereken belirli değişiklikler içerir.

- Adlı bir şablon oluşturarak 404 sayfasını özelleştirme `templates/404.html`. Varsa, Django varsayılan bir yerine bu şablonu kullanır. Daha fazla bilgi için bkz: [hata görünümleri](https://docs.djangoproject.com/en/2.0/ref/views/#error-views) Django belgelerinde.

- Birim testleri yazma `tests.py`; başlangıç noktaları bunlar için Visual Studio Proje şablonları sağlar ve daha fazla bilgi bulunabilir [ilk Django uygulamanız bölümü 5 - sınama yazma](https://docs.djangoproject.com/en/2.0/intro/tutorial05/) ve [Djangotestetme](https://docs.djangoproject.com/en/2.0/topics/testing/) Django belgelerinde.

- Uygulama SQLite bir üretim düzeyinde veri deposuna PostgreSQL, MySQL ve SQL Server'ın (bunların tümü Azure'da barındırılabilir) gibi değiştirin. Açıklandığı gibi [SQLite kullanmak ne zaman](https://www.sqlite.org/whentouse.html) (sqlite.org) SQLite düşük veya Orta trafiğe sahip sitelere en fazla 100 K isabet/gün ile düzgün çalışır, ancak daha yüksek birimler için önerilmez. Ayrıca tek bir bilgisayara sınırlı, bu nedenle kullanılamaz Yük Dengeleme ve coğrafi çoğaltma gibi herhangi bir çok sunuculu senaryoda. Diğer veritabanlarını Django'nın desteği hakkında daha fazla bilgi için bkz: [Veritabanı Kurulumu](https://docs.djangoproject.com/en/2.0/intro/tutorial02/#database-setup). Aynı zamanda [Python için Azure SDK](azure-sdk-for-python.md) tabloları ve blobları gibi Azure storage Hizmetleri ile çalışmak için.

- Bir hizmeti Visual Studio Team Services (VSTS) gibi bir sürekli tümleştirme/sürekli dağıtım ardışık ayarlayın. Kaynak denetimi (VSTS, GitHub veya başka bir yerde) ile çalışma ek olarak, otomatik olarak yayın için önkoşul olarak birim testleri çalıştırma ve ayrıca için dağıtmadan önce ek testler için hazırlama sunucusuna dağıtmak için ardışık düzenini yapılandırın VSTS olabilir Üretim. VSTS, ayrıca, App Insights gibi çözümlerini izleme ile tümleşir ve Çevik planlama araçları ile tüm döngüsü kapatır. Daha fazla bilgi için bkz.:

  - [CI/CD işlem hattı Python için Azure DevOps projeyle oluşturma.](/vsts/build-release/apps/cd/azure/azure-devops-project-python?view=vsts)
  - [Visual Studio Team Services (video, 11m 21s) ile Azure Python geliştirme](https://azure.microsoft.com/resources/videos/connect-2017-python-development-in-azure-with-visual-studio-team-services/).

