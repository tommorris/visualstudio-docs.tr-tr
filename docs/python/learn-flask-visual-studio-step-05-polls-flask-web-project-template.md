---
title: Öğretici - Visual Studio, adım 5 Flask öğrenin
description: Visual Studio projeleri, özellikle yoklamalar Flask Web projesi ve anketler Flask/Jade Web projesi şablonları özelliklerini bağlamında Flask temel bir kılavuz.
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
ms.openlocfilehash: 322e0bdc98751cda670206667cc8580bd498f682
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752514"
---
# <a name="tutorial-step-5-use-the-polls-flask-web-project-template"></a>Öğreticisi 5. adım: yoklamalar Flask Web projesi şablonunu kullanın

**Önceki adımda: [tam Flask Web projesi şablonunu kullanın](learn-flask-visual-studio-step-04-full-flask-project-template.md)**

Visual Studio'nun "Flask Web projesi" şablonu anladım şimdi üçüncü Flask şablon "Yoklamalar Flask Web, aynı kod temeli üzerinde derlemeler projesi" bakabilirsiniz.

Bu adımda, bilgi nasıl yapılır:

> [!div class="checklist"]
> - Proje şablonu oluşturma ve veritabanını başlatılamadı (adım 5 - 1)
> - (Adım 5-2) veri modelleri anlama
> - (5-3. adım) ve yedekleme veri depolarına anlama
> - Yoklama sonuçları ve ayrıntı görünümleri (5-4. adım) Anlama

Visual Studio de aynı uygulama oluşturur, ancak Jade uzantısı için Jinja şablon altyapısı kullanır "Yoklamalar Flask/Jade Web projesi" şablonu projeleri. Ayrıntılar için bkz [4. adım - Flask/Jade Web Proje şablonu](learn-flask-visual-studio-step-04-full-flask-project-template.md#the-flaskjade-web-project-template).

## <a name="step-5-1-create-the-project"></a>5 1. adım: Proje oluşturma

1. Visual Studio'da Git **Çözüm Gezgini**, bu öğreticide daha önce oluşturulan "LearningFlask" çözüme sağ tıklayın ve seçin **Ekle** > **yeni proje**. (Alternatif olarak, yeni bir çözüm kullanmak isteyip istemediğinizi seçin **dosya** > **yeni** > **proje** yerine.)

1. Yeni Proje iletişim kutusunda, aramak ve "Yoklamalar Flask Web projesi" şablonunu seçin, proje "FlaskPolls" çağırın ve seçmek **Tamam**.

1. Diğer proje şablonları gibi Visual Studio'da, "Yoklamalar Flask Web projesi" şablonu içerir bir `requirements.txt` , Visual Studio komut istemlerini ister where bu bağımlılıkların yüklemek için dosya. Seçeneği **sanal bir ortama yükleme**hem de **sanal ortam Ekle** iletişim kutusunda **oluşturma** Varsayılanları kabul etmek için. (Bu şablonu Flask ve bunun yanı sıra azure storage ve pymongo paketleri gerektirir; "yoklamalar Flask/Jade Web projesi" pyjade de gerekli.)

1. "FlaskPolls" projesini bu projeye sağ tıklayarak Visual Studio çözümü için varsayılan olacak şekilde ayarlayın **Çözüm Gezgini** ve seçerek **başlangıç projesi olarak ayarla**. Gösterilen başlangıç projesi içinde hata ayıklayıcı başlatıldığında ne çalıştırılan kalın.

1. Seçin **hata ayıklama > hata ayıklamayı Başlat** (F5) veya **Web sunucusu** sunucu çalıştırmak için araç çubuğunda:

    ![Visual Studio'da Web sunucusu Çalıştır araç çubuğu düğmesi](media/django/run-web-server-toolbar-button.png)

1. Şablon tarafından oluşturulan uygulama hakkında ev ve üst gezinti çubuğu'nu kullanma arasında gidin, ilgili kişi, üç sayfaları vardır. Bir veya iki farklı kısımlarını uygulama incelemek için dakika alın (hakkında ve iletişim sayfaları "Flask Web projesi için" çok benzer ve daha ayrıntılı ele alınan değil).

    ![Anketler Flask Web projesi uygulamasının tam görünümü](media/flask/step06-full-app-view.png)

1. Giriş sayfasında **örnek yoklamalar Oluştur** düğmesi başlatır açıklanan üç farklı anketler uygulamanın veri deposuyla `models/samples.json` sayfası. Varsayılan olarak, uygulamayı uygulama her başlatıldığında sıfırlama (gösterildiği gibi hakkında sayfasında), bir bellek içi veritabanı kullanır. Uygulama, aynı zamanda bu makalenin sonraki bölümlerinde açıklandığı gibi Azure Storage ve Mongo DB ile çalışmak için kodunu içerir.

1. Veri deposu başlatılmış sonra (gezinme çubuğu ve altbilgi okumanızdır göz ardı edilir) giriş sayfasında gösterildiği gibi farklı yoklamalarda oy kullanabilir:

    ![Veri deposu başlatıldıktan sonra yoklamalar uygulama görünümü](media/flask/step06-polls-initialized.png)

1. Bir yoklama seçerek belirli seçimlerini görüntüler:

    ![Bir yoklama için oy arabirimi](media/flask/step06-polls-voting-interface.png)

1. Oy sonra uygulamayı bir sonuçlar sayfası gösterir ve yeniden oy sağlar:

    ![Oylama sonra sonuçları görünümü](media/flask/step06-polls-results.png)

1. Aşağıdaki bölümlerde için çalışan uygulama bırakabilirsiniz.

    Uygulama durdurmak istiyorsanız ve [değişiklikleri kaynak denetimine](learn-flask-visual-studio-step-02-create-app.md#commit-to-source-control), ilk açmak **değişiklikleri** sayfasındaki **Takım Gezgini**, sanal ortama (klasörünü sağ tıklatın büyük olasılıkla `env`) ve seçin **bu yerel öğeleri Yoksay**.

### <a name="examine-the-project-contents"></a>Proje içeriğini inceleyin

Önce belirtildiği gibi. ne olduğu kadar "Yoklamalar Flask Web projesi" şablonu (ve "Yoklamalar Flask/Jade Web projesi" şablonu) oluşturulmuş bir projeyi Visual Studio diğer proje şablonlarını incelediniz ise bilgi sahibi olmanız gerekir. Bu makalede ek adımlar daha önemli değişiklikler ve eklemeler, veri modelleri ve ek görünümler özetler.

## <a name="step-5-2-understand-the-data-models"></a>5-2. adım: veri modelleri anlama

Uygulama veri modellerini yoklama ve içinde tanımlanan seçim adlı Python sınıflardır `models/__init__.py`. Bir yoklama seçim örneklerinin bir koleksiyonunu temsil kullanılabilir yanıtları bir soru temsil eder. Ayrıca, bir yoklama oy (için herhangi bir seçim) ve görünümleri oluşturmak için kullanılan istatistikleri hesaplamak için bir yöntem toplam sayısı tutar:

    ```python
    class Poll(object):
        """A poll object for use in the application views and repository."""
        def __init__(self, key=u'', text=u''):
            """Initializes the poll."""
            self.key = key
            self.text = text
            self.choices = []
            self.total_votes = None

        def calculate_stats(self):
            """Calculates some statistics for use in the application views."""
            total = 0
            for choice in self.choices:
                total += choice.votes
            for choice in self.choices:
                choice.votes_percentage = choice.votes / float(total) * 100 \
                    if total > 0 else 0
            self.total_votes = total

    class Choice(object):
        """A poll choice object for use in the application views and repository."""
        def __init__(self, key=u'', text=u'', votes=0):
            """Initializes the poll choice."""
            self.key = key
            self.text = text
            self.votes = votes
            self.votes_percentage = None
    ```

Bu veri modelleri sonraki adımda açıklanan veri depolarını yedekleme farklı türleriyle çalışmak için uygulamanın görünümleri izin genel soyutlamalar ' dir.

## <a name="step-5-3-understand-the-backing-data-stores"></a>5-3. adım: veri depoları destekleme anlama

"Yoklamalar Flask Web projesi" şablonu tarafından oluşturulan uygulama, bir veri deposu bellek, Azure tablo depolaması veya Mongo DB veritabanı karşı çalıştırabilirsiniz.

Veri depolama mekanizmasını şöyle çalışır:

1. Depo türü aracılığıyla belirtilen `REPOSITORY_NAME` "bellek", "azuretablestore" veya "mongodb" ayarlanabilir ortam değişkeni. Biraz kod `settings.py` varsayılan olarak "bellek" kullanarak adını alır. Yedekleme deposu değiştirmek istiyorsanız, ortam değişkenini ayarlamak ve uygulamayı yeniden başlatın gerekir.

    ```python
    from os import environ
    REPOSITORY_NAME = environ.get('REPOSITORY_NAME', 'memory')
    ```

1. `settings.py` Sonra başlatır kod bir `REPOSITORY_SETTINGS` nesnesi. Azure tablo deposu veya kara DB kullanmak istiyorsanız, gerekir önce bu veri depolarına başka bir yerde başlatın ve ardından uygulama Mağazası'na bağlanmak nasıl anlatın gerekli ortam değişkenlerini ayarlama:

    ```python
    if REPOSITORY_NAME == 'azuretablestorage':
        REPOSITORY_SETTINGS = {
            'STORAGE_NAME': environ.get('STORAGE_NAME', ''),
            'STORAGE_KEY': environ.get('STORAGE_KEY', ''),
            'STORAGE_TABLE_POLL': environ.get('STORAGE_TABLE_POLL', 'polls'),
            'STORAGE_TABLE_CHOICE': environ.get('STORAGE_TABLE_CHOICE', 'choices'),
        }
    elif REPOSITORY_NAME == 'mongodb':
        REPOSITORY_SETTINGS = {
            'MONGODB_HOST': environ.get('MONGODB_HOST', None),
            'MONGODB_DATABASE': environ.get('MONGODB_DATABASE', 'polls'),
            'MONGODB_COLLECTION': environ.get('MONGODB_COLLECTION', 'polls'),
        }
    elif REPOSITORY_NAME == 'memory':
        REPOSITORY_SETTINGS = {}
    else:
        raise ValueError('Unknown repository.')
    ```

1. İçinde `views.py`, uygulamayı başlatmak için bir fabrika yöntemini çağıran bir `Repository` veri deposunun adı ve ayarları kullanarak nesnesi:

    ```python
    from FlaskPolls.models import PollNotFound
    from FlaskPolls.models.factory import create_repository
    from FlaskPolls.settings import REPOSITORY_NAME, REPOSITORY_SETTINGS

    repository = create_repository(REPOSITORY_NAME, REPOSITORY_SETTINGS)
    ```

1. `factory.create_repository` Yöntemi içinde bulunan `models\factory.py`, hangi yalnızca uygun depo modülü içe aktarır ve ardından oluşturur bir `Repository` örneği:

    ```python
    def create_repository(name, settings):
        """Creates a repository from its name and settings. The settings
        is a dictionary where the keys are different for every type of repository.
        See each repository for details on the required settings."""
        if name == 'azuretablestorage':
            from .azuretablestorage import Repository
        elif name == 'mongodb':
            from .mongodb import Repository
        elif name == 'memory':
            from .memory import Repository
        else:
            raise ValueError('Unknown repository.')

        return Repository(settings)
    ```

1. Uygulamaları `Repository` her veri deposuna belirli sınıfı bulunabilir `models\azuretablestorage.py`, `models\mongodb.py`, ve `models\memory.py`. Azure storage uygulaması azure depolama paketi kullanır; Mongo DB uygulama pymongo paketi kullanır. Adım 5-1 belirtildiği gibi her iki paket proje şablonunun dahil edilen `requirements.txt` dosya. Ayrıntıları keşfetmek için okuyucu bir alıştırma olarak kalır.

Kısacası, `Repository` sınıfı soyutlar veri deposu ayrıntılarını ve seçin ve kullanılacak üç uygulamaları hangisinin yapılandırmak için çalışma zamanında uygulama ortam değişkenlerini kullanır.

Aşağıdaki adımları böylece isterseniz proje şablonu tarafından sağlanan üç daha farklı bir veri deposu için destek ekleyin:

1. Kopya `memory.py` yeni bir dosyaya böylece için temel arabirimi sahip `Repository` sınıfı.
1. Kullanmakta olduğunuz veri deposu uygun şekilde sınıfı uyarlamasını değiştirin.
1. Değiştirme `factory.py` başka bir tane eklemek için `elif` çalışmasını eklenen data store adını algılar ve uygun modülü içe aktarır.
1. Değiştirme `settings.py` başka bir ad tanımak için `REPOSITORY_NAME` ortam değişkeni ve başlatmak için `REPOSITORY_SETTINGS` uygun şekilde.

### <a name="seed-the-data-store-from-samplesjson"></a>Samples.json veri deposundan çekirdek

Başlangıçta, uygulamanın giriş sayfasını ileti "Hiçbir yoklamalar kullanılabilir" ile birlikte gösterecek şekilde tüm seçilen veri deposu hiçbir anketler, içerir, **örnek yoklamalar Oluştur** düğmesi. Ancak, düğme seçtikten sonra kullanılabilir yoklamalar görüntülemek için görünümü değiştirir. Bu anahtar koşullu etiketlerinde aracılığıyla olur `templates\index.html` (bazı boş satırlar verilmemiştir):

    ```html
    {% extends "layout.html" %}
    {% block content %}
    <h2>{{title}}.</h2>

    {% if polls %}
    <table class="table table-hover">
        <tbody>
            {% for poll in polls %}
            <tr>
                <td>
                    <a href="/poll/{{poll.key}}">{{poll.text}}</a>
                </td>
            </tr>
            {% endfor %}
        </tbody>
    </table>
    {% else %}
    <p>No polls available.</p>
    <br />
    <form action="/seed" method="post">
        <button class="btn btn-primary" type="submit">Create Sample Polls</button>
    </form>
    {% endif %}
    {% endblock %}
    ```

`polls` Şablon değişkeni gelen çağrısından `repository.get_polls`, döndüren bir şey veri deposu başlatılana dek.

Seçme **örnek yoklamalar Oluştur** düğmesi /seed URL'sine gider. Bu rota için işleyici tanımlanan `views.py`:

```python
@app.route('/seed', methods=['POST'])
def seed():
    """Seeds the database with sample polls."""
    repository.add_sample_polls()
    return redirect('/')
```

Çağrı `repository.add_sample_polls()` sona eriyor belirli birinde `Repository` uygulamalar için seçilen veri deposu. Her uygulama çağırır `_load_samples_json` yöntemi bulunan `models\__init__.py` yüklemek için `models\samples.json` dosya belleğe sonra gerekli oluşturmak için bu veri tekrarlanan `Poll` ve `Choice` veri deposunda nesneleri.

Bu işlem tamamlandıktan sonra `redirect('/')` deyiminde `seed` yöntemi giriş sayfasına gider. Çünkü `repository.get_polls` artık koşullu etiketlerinde bir veri nesnesi döndüren `templates\index.html` şimdi yoklamalar içeren bir tablo oluşturur.

### <a name="question-how-does-one-add-new-polls-to-the-app"></a>Soru: Nasıl bir yeni anketler uygulamaya ekler?

Yanıt: Proje şablonu aracılığıyla sağlanan uygulama ekleme veya düzenleme yoklamalar tesis içermez. Değiştirebileceğiniz `models\samples.json` yeni başlatma verileri oluşturmak için ancak bunu yaptığınızda anlamına veri deposunu sıfırlama. Düzenleme özellikleri uygulamak için yayması gerekir `Repository` gerekli oluşturmak için yöntem sınıfı arabirimiyle `Choice` ve `Poll` örnekleri, bu yöntemleri kullanan ek sayfalarında sonra bir kullanıcı Arabirimi uygulamak.

## <a name="step-5-4-understand-the-poll-detail-and-results-views"></a>Adım 5-4: yoklama ayrıntı ve sonuçları görünümleri anlama

Çoğu "Yoklamalar Flask Web projesi" ve "Yoklamalar Flask/Jade Web projesi" şablonları tarafından oluşturulan görünümlerini hakkında ve iletişim için görünümleri gibi sayfa, "Flask Web projesi" (veya "Flask/Jade Web projesi") şablonu tarafından oluşturulan görünümleri, çalıştığınız oldukça benzer ile bu öğreticinin önceki. Önceki bölümde, ayrıca başlatma düğmesi ya yoklamalar listesi göstermek için giriş sayfasının nasıl uygulandığı hakkında bilgi edindiniz.

Ne burada kalır oylama (ayrıntı) ve tek tek bir yoklama sonuçları görünümünü incelemektir.

Giriş sayfasından bir yoklama seçtiğinizde, uygulama için URL /poll/ gider\<anahtar\> nerede *anahtar* bir yoklama için benzersiz tanımlayıcı değil. İçinde `views.py` görebilirsiniz `details` işlevi bu URL hem GET hem de istekleri için yönlendirme işlemek üzere atanır. Kullanan de görebilirsiniz `<key>` URL rota hem aynı işleve bu formun tüm rotasını eşler ve aynı adı işlevi bağımsız değişken oluşturur:

```python
@app.route('/poll/<key>', methods=['GET', 'POST'])
def details(key):
    """Renders the poll details page."""
    error_message = ''
    if request.method == 'POST':
        try:
            choice_key = request.form['choice']
            repository.increment_vote(key, choice_key)
            return redirect('/results/{0}'.format(key))
        except KeyError:
            error_message = 'Please make a selection.'

    return render_template(
        'details.html',
        title='Poll',
        year=datetime.now().year,
        poll=repository.get_poll(key),
        error_message=error_message,
    )
```

Yoklama (GET istekleri) göstermek için bu işlevi yalnızca üzerine çağırır `templates\details.html`, yoklama 's tekrarlanan `choices` dizi, her biri için bir radyo düğmesi oluşturma.

```html
{% extends "layout.html" %}

{% block content %}

<h2>{{poll.text}}</h2>
<br />

{% if error_message %}
<p class="text-danger">{{error_message}}</p>
{% endif %}

<form action="/poll/{{poll.key}}" method="post">
    {% for choice in poll.choices %}
    <div class="radio">
        <label>
            <input type="radio" name="choice" id="choice{{choice.key}}" value="{{choice.key}}" />
            {{ choice.text }}
        </label>
    </div>
    {% endfor %}
    <br />
    <button class="btn btn-primary" type="submit">Vote</button>
</form>

{% endblock %}
```

Çünkü **oy** düğmesi bulunur `type="submit"`, seçerek geri yönlendirilir aynı URL'ye bir POST isteği oluşturur `details` kez daha işlev. Bu süre, ancak, seçimi form verileri ayıklar ve /results/ için yönlendiren\<seçim\>.

/Results/\<anahtar\> URL için yönlendirilmiş sonra `results` işlevi `views.py`, o yoklama 's çağırır `calculate_stats` yöntemi ve uygular `templates\results.html` işleme için:

```python
@app.route('/results/<key>')
def results(key):
    """Renders the results page."""
    poll = repository.get_poll(key)
    poll.calculate_stats()
    return render_template(
        'results.html',
        title='Results',
        year=datetime.now().year,
        poll=poll,
    )
```

`results.html` Kendi bölümü için şablon sadece yoklama 's seçimlerinde tekrarlanan ve her biri için bir ilerleme çubuğu oluşturur:

```html
{% extends "layout.html" %}

{% block content %}

<h2>{{poll.text}}</h2>
<br />

{% for choice in poll.choices %}
<div class="row">
    <div class="col-sm-5">{{choice.text}}</div>
    <div class="col-sm-5">
        <div class="progress">
            <div class="progress-bar" role="progressbar" aria-valuenow="{{choice.votes}}" aria-valuemin="0" aria-valuemax="{{poll.total_votes}}" style="width: {{choice.votes_percentage}}%;">
                {{choice.votes}}
            </div>
        </div>
    </div>
</div>
{% endfor %}

<br />
<a class="btn btn-primary" href="/poll/{{poll.key}}">Vote again?</a>

{% endblock %}
```

## <a name="next-steps"></a>Sonraki adımlar

> [!Note]
> Visual Studio çözümünüzü kaynak denetimine Bu öğreticinin boyunca yürüten, başka bir yürütme yapmak için iyi bir zamandır sunulmuştur. Çözümünüzü öğretici kaynak kodu github'da eşleşmesi gerekir: [Microsoft/python-örnek-vs-learning-flask](https://github.com/Microsoft/python-sample-vs-learning-flask).

Visual Studio'da "Boş Flask Web projesi", "[/Jade] Flask Web projesi" ve "Yoklamalar [/Jade] Flask Web projesi" şablonları tamamen şimdi incelediniz. Tüm şablonları, görünümleri kullanma ve yönlendirme gibi Flask öğrendiğinize ve yedekleme veri depolarına kullanmayı gördünüz. Artık tüm görünümler ve ihtiyacınız modelleri ile kendi web uygulaması üzerinde çalışmaya başlamak mümkün olması gerekir.

Bir web uygulaması geliştirme bilgisayarınızda çalışan uygulama müşterileriniz için kullanılabilir hale getirme yalnızca bir adımdır. Sonraki adımlar aşağıdaki görevler de dahil:

- Web uygulamasını Azure App Service gibi bir üretim sunucusu dağıtın. Bkz: [Azure App Service Yayımla](publishing-python-web-applications-to-azure-from-visual-studio.md), Flask uygulamalar için gereken belirli değişiklikler içerir.

- PostgreSQL, MySQL ve SQL Server'ın (bunların tümü Azure'da barındırılabilir) gibi başka bir üretim düzeyi veri deposunu kullanan bir depo uygulaması ekleyin. Aynı zamanda [Python için Azure SDK](azure-sdk-for-python.md) Cosmos DB yanı sıra tablolar ve BLOB'ları gibi Azure storage Hizmetleri ile çalışmak için.

- Bir hizmeti Visual Studio Team Services (VSTS) gibi bir sürekli tümleştirme/sürekli dağıtım ardışık ayarlayın. Kaynak denetimi (VSTS, GitHub veya başka bir yerde) ile çalışma ek olarak, otomatik olarak yayın için önkoşul olarak birim testleri çalıştırma ve ayrıca için dağıtmadan önce ek testler için hazırlama sunucusuna dağıtmak için ardışık düzenini yapılandırın VSTS olabilir Üretim. VSTS, ayrıca, App Insights gibi çözümlerini izleme ile tümleşir ve Çevik planlama araçları ile tüm döngüsü kapatır. Daha fazla bilgi için bkz.:

  - [CI/CD işlem hattı Python için Azure DevOps projeyle oluşturma.](/vsts/build-release/apps/cd/azure/azure-devops-project-python?view=vsts)
  - [Visual Studio Team Services (video, 11m 21s) ile Azure Python geliştirme](https://azure.microsoft.com/resources/videos/connect-2017-python-development-in-azure-with-visual-studio-team-services/).
