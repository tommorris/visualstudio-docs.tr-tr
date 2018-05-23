---
title: Öğretici - Visual Studio, 1. adım Django öğrenin
description: Visual Studio projeleri bağlamında Django temel bir kılavuz, Django geliştirme için Visual Studio destek gösteren sağlar.
ms.date: 05/03/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 82f7de8649e36c03f1ae1004c01c93dd7580b3a1
ms.sourcegitcommit: cc88ccc6aacebe497899fab05d243a65053e194c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
---
# <a name="tutorial-step-1-get-started-with-the-django-web-framework-in-visual-studio"></a>Öğreticisi 1. adım: Visual Studio Django web framework kullanmaya başlama

[Django](https://www.djangoproject.com/) hızlı, güvenli ve ölçeklenebilir bir web geliştirme için tasarlanmış bir çerçevedir üst düzey Python. Bu öğreticide Visual Studio, Django tabanlı web uygulamaları oluşturulmasını kolaylaştırmak için sağlar proje şablonları bağlamında Django framework araştırır.

Bu öğreticide, bilgi nasıl yapılır:

> [!div class="checklist"]
> - "Boş Django Web projesi" şablonu (1. adım) kullanarak Git deposunda bir temel Django projesi oluşturma
> - Bir sayfayla bir Django uygulaması oluşturma ve bir şablonu (2. adım) kullanarak bu sayfayı işlemek
> - Statik dosyaları işleme, sayfa ekleyin ve şablon devralma (adım 3) kullanın
> - Birden çok sayfa ve esnek tasarım (4. adım) bir uygulama oluşturmak için Django Web projesi şablonu kullanın
> - Kullanıcılar (5. adım) kimlik doğrulaması
> - Modeller, veritabanı geçişler ve özelleştirmeleri yönetim arabirimi (6. adım) kullanan bir uygulama oluşturmak için yoklamalar Django Web projesi şablonu kullanın

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio 2017 aşağıdaki seçeneklere sahip:
  - **Python geliştirme** iş yükü (**iş yükü** yükleyici sekmesinde). Yönergeler için bkz: [yükleme Python desteği Visual Studio'da](installing-python-support-in-visual-studio.md).
  - **Windows için Git** ve **Visual Studio için GitHub uzantısı** üzerinde **bileşenleri tek tek** altında sekmesinde **kod Araçları**.

Ayrıntılar ne (özellikle farklı Django framework'ün önceki sürümleriyle) bu öğreticideki açıklanan alanından farklı olabilir ancak Django proje şablonları da Visual Studio için Python Araçları'nın tüm eski sürümlerini dahil edilir.

### <a name="visual-studio-projects-and-django-projects"></a>"Visual Studio projeleri" ve "Django projeler"

Django terminolojisinde "dağıttığınız tam web uygulaması oluşturmak için bir web ana bilgisayarı için bir veya daha fazla uygulamalar" ile birlikte birkaç site düzeyinde yapılandırma dosyalarını, "Django proje" oluşur. Aynı uygulama birden fazla Django projesinde olabilir ve Django proje birden fazla uygulama içerebilir.

Visual Studio projesi, kendi bölümü için birden çok uygulama ile birlikte Django proje içerebilir. Bu öğreticide yalnızca bir "projeye" başvuruyor her basitleştirmek amacıyla, Visual Studio projesi başvuruyor. Web uygulaması "Django proje" bölümünü başvurduğunda, özellikle "Django proje" kullanır.

Bu öğretici süresince her biri tek bir Django uygulamayı içeren üç ayrı Django projeleri, içeren tek bir Visual Studio çözüm oluşturacaksınız. Aynı Çözümdeki projeler tutarak kolayca geri ve İleri karşılaştırma için farklı dosyalar arasında geçiş yapabilirsiniz.

## <a name="step-1-1-create-a-visual-studio-project-and-solution"></a>1-1. adım: Visual Studio Proje ve çözüm oluşturma

Komut satırından Django ile çalışırken, genellikle bir proje çalıştırarak başlattığınız `django-admin startproject <project_name>` komutu. Visual Studio'da "Boş Django Web projesi" şablonu kullanarak bir Visual Studio Proje ve çözüm içinde aynı yapısını sağlar.

1. Visual Studio'da seçin **dosya** > **yeni** > **proje**"Django" için arama yapın ve seçin **boş Django Web projesi**  şablonu. (Şablon ayrıca altında bulunan **Python** > **Web** sol listesinde.)

    ![Boş Django Web projesi için Visual Studio'da yeni proje iletişim kutusu](media/django/step01-new-blank-project.png)

1. İletişim kutusunun altındaki alanlara (önceki grafikte gösterildiği gibi) aşağıdaki bilgileri girin ve ardından **Tamam**:

    - **Ad**: "BasicProject" için Visual Studio projesi adını ayarlayın. Bu ad Django proje için de kullanılır.
    - **Konum**: Visual Studio çözüm ve proje oluşturmak bir konum belirtin.
    - **Çözüm**: Bu denetimin varsayılan "yeni çözüm oluştur" seçeneğine ayarlı bırakın.
    - **Çözüm adı**: "LearningDjango", birden çok proje için bir kapsayıcı olarak Bu öğreticide çözüm için uygun olduğu ayarlayın.
    - **Çözüm için dizin oluşturma**: bırakın (varsayılan) ayarlayın.
    - **Yeni bir Git deposu oluşturursunuz**: Visual Studio çözümü oluşturduğunda, yerel bir Git deposu oluşturur, böylece (temizleyin varsayılan olarak etkindir) bu seçeneği belirleyin. Bu seçeneği görmüyorsanız, Visual Studio 2017 yükleyiciyi çalıştırın ve Windows için Git ve GitHub uzantısı Visual Studio için eklemek **bileşenleri tek tek** altında sekmesinde **kod Araçları**.

1. Bir süre sonra "Bu proje gerektiren dış paketler" belirten bir iletişim kutusuyla ister Visual Studio (aşağıda gösterilen). Şablonun içerdiği için bu iletişim kutusu görünür bir `requirements.txt` en son Django 1.x paketini başvuran dosya. (Seçin **gerekli paketleri Göster** tam bağımlılıkları görmek için.)

    ![Komut istemi bildiren proje dış paketler gerektirir](media/django/step01-requirements-prompt-install-myself.png)

1. Seçeneğini **ı bunları kendim yükleyecek**. Kısa süre içinde kaynak denetiminden dışlandı emin olmak için sanal ortamı oluşturun. (Ortamı her zaman oluşturulabilir `requirements.txt`.)

## <a name="step-1-2-examine-the-git-controls-and-publish-to-a-remote-repository"></a>1-2. adım: Git denetimleri inceleyin ve uzak bir depo yayımlama

Seçtiğiniz çünkü **oluştur yeni Git deposu** içinde **yeni proje** iletişim kutusunda, proje zaten yerel kaynak denetimine taahhüt oluşturma işlemi tamamlandıktan hemen sonra. Bu adımda, Visual Studio'nun Git denetimleriyle öğrenmeniz ve **Takım Gezgini** kaynak denetimiyle çalışma penceresi.

1. Visual Studio ana penceresinin alt köşedeki Git denetimlere inceleyin. Soldan sağa, bu denetimlerin unpushed tamamlama, kaydedilmemiş değişiklikler, havuzu ve geçerli dal adını göster:

    ![Visual Studio penceresinde Git denetimleri](media/django/step01-git-controls.png)

    > [!Note]
    > Seçmezseniz, **oluştur yeni Git deposu** içinde **yeni proje** iletişim kutusunda, Git denetimlerini göster yalnızca bir **eklemek için kaynak denetimi** yerel oluşturur komutu Depo.
    >
    > ![Ekleme kaynak denetimi görünür Visual Studio'da bir deposu oluşturduysanız değil](media/django/step01-git-add-to-source-control.png)

1. Değişiklikleri düğmesini seçin ve Visual Studio açılır kendi **Takım Gezgini** penceresinde **değişiklikleri** sayfası. Yeni oluşturulan proje zaten kaynak denetimi otomatik olarak kaydedilmiş olduğundan bekleyen değişiklikleri görmüyorum.

    ![Takım Gezgini penceresi değişiklikleri sayfasında](media/django/step01-team-explorer-changes.png)

1. Visual Studio durum çubuğunda açmak için ("2" olan yukarı ok) unpushed işlemeleri düğmesini seçin **eşitleme** sayfasındaki **Takım Gezgini**. Yalnızca yerel deposu olduğundan, sayfa için farklı uzak depoları depo yayımlamak için kolay seçenekler sunar.

    ![Takım Gezgini penceresi gösteren Git deposu için kullanılabilir seçenekleri kaynak denetimi](media/django/step01-team-explorer.png)

    Kendi projeleri için hangi hizmetin seçebilirsiniz. Bu öğretici GitHub, burada öğreticinin tamamlanmış örnek kodu korunur kullanımını göstermektedir [Microsoft/python-örnek-vs-learning-django](https://github.com/Microsoft/python-sample-vs-learning-django) deposu.

1. Herhangi bir seçerken **Yayımla** denetimleri **Takım Gezgini** daha fazla bilgi için ister. Örneğin, Bu öğretici için örnek yayımlama sırasında depo ilk olarak, bu durumda oluşturulması gerekiyordu **anında uzak depoya** seçeneği deponun URL ile kullanıldı.

    ![Var olan bir uzak depoya gönderilmesi için Takım Gezgini penceresi](media/django/step01-push-to-github.png)

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

Projeniz için kaynak denetimi yapılandırdıktan, proje için gerekli Django paketlerini içeren sanal ortam oluşturabilirsiniz. Daha sonra **Takım Gezgini** kaynak denetiminden ortam klasörü dışlamak için.

1. İçinde **Çözüm Gezgini**, sağ **Python ortamları** düğümü ve select **sanal ortam Ekle**.

    ![Çözüm Gezgini'nde sanal ortam komut ekleme](media/django/step01-add-virtual-environment-command.png)

1. Bir **sanal ortam Ekle** iletişim kutusu görüntülenirse, "Requirements.txt dosyasını bulduk." belirten bir ileti Bu ileti, Visual Studio sanal ortamı yapılandırmak için bu dosyayı kullandığını gösterir.

    ![Sanal ortama Ekle iletişim kutusu requirements.txt iletisi](media/django/step01-add-virtual-environment-found-requirements.png)

1. Seçin **oluşturma** Varsayılanları kabul etmek için. (İsterseniz, sanal ortamı adını da alt klasörünü adını yalnızca Değişeni değiştirebileceğiniz ancak `env` standart bir kuraldır.)

1. Visual Studio indirmeleri ve paketleri, yani Django için birkaç bin dosyalarında sayıda alt klasörler hakkında genişletme yükler yönetici ayrıcalıkları onay istenirse, sonra birkaç dakika endişelenmeyin! Visual Studio'da ilerleme durumunu görebilirsiniz **çıkış** penceresi. Beklerken, soru bölümlerde ponder.

1. Visual Studio Git denetimleri (durum çubuğunda), değişiklikleri göstergeyi seçin (gösterir "99 *") açan **değişiklikleri** sayfasındaki **Takım Gezgini**.

    Sanal ortam oluşturma duruma değişiklikleri binlerce içinde ancak siz (veya herhangi başka proje kopyalama) ortamından her zaman yeniden oluşturabilirsiniz hiçbirini dahil kaynak denetiminde gerekmez `requirements.txt`.

    Sanal ortam dışlamak için sağ `env` klasörü ve select **bu yerel öğeleri Yoksay**.

    ![Kaynak denetimi değişikliklerinin sanal bir ortamda yoksayılıyor](media/django/step01-ignore-local-items.png)

1. Sanal ortam çıkardıktan sonra yalnızca kalan proje dosyasına değişir ve `.gitignore`. `.gitignore` Dosya sanal ortam klasörü için eklenen bir giriş içerir. Bir sonraki fark görmek için bu dosyaya çift tıklayın

1. Bir kaydetme iletisi girin ve **tamamlama tüm** düğmesine ve ardından isterseniz uzak deponuza işlemeleri anında iletme.

### <a name="question-why-do-i-want-to-create-a-virtual-environment"></a>Soru: Neden t sanal bir ortam oluşturmak istiyor musunuz?

Yanıt: Bir sanal ortam, uygulamanızın tam bağımlılıkları yalıtmak için harika bir yoludur. Bu tür yalıtım genel bir Python ortamı içindeki çakışmaları ortadan kaldırır ve test etme ve işbirliği yardımları. Bir uygulama geliştirirken zaman içinde çok yararlı Python paketlerini, herhangi bir sayı neredeyse şaşmaz biçimde getirin. Paket bir projeye özgü sanal ortamda tutarak, projenin kolayca güncelleştirebilirsiniz `requirements.txt` kaynak denetiminde içerilen bu ortamı tanımlayan dosya. Proje, derleme sunucuları, dağıtım sunucuları ve diğer geliştirme bilgisayarlar dahil olmak üzere diğer bilgisayarlara, kopyalanan yalnızca kullanarak ortamını yeniden daha kolaydır `requirements.txt` (olduğu neden ortamı kaynak denetiminde olması gerekmez). Daha fazla bilgi için bkz: [sanal ortamlar kullanarak](selecting-a-python-environment-for-a-project.md#using-virtual-environments).

### <a name="question-how-do-i-remove-a-virtual-environment-thats-already-committed-to-source-control"></a>Soru: Nasıl zaten kaynak denetimi için kaydedilmiş bir sanal ortam kaldırabilirim?

Yanıt: İlk olarak, düzenleme, `.gitignore` klasörü dışlamak için dosya: açıklamayı içeren sonunda bölüm Bul `# Python Tools for Visual Studio (PTVS)` ve sanal ortam klasörü için yeni bir satır ekleyin `/BasicProject/env`. (Visual Studio dosyasında göstermiyor çünkü **Çözüm Gezgini**, kullanarak doğrudan açmadan **dosya** > **açmak**  >   **Dosya** menü komutu. Dosyasını da açabilirsiniz **Takım Gezgini**: üzerinde **ayarları** sayfasında, **deposu ayarları**gidin **öznitelikleri dosyaları&yoksay** bölümünde ve ardından **Düzenle** bağlantısına `.gitignore`.)

İkinci olarak, bir komut penceresi açın, gibi klasöre gidin `BasicProject` sanal ortam klasörü gibi içeren `env`, çalıştırıp `git rm -r env`. Ardından bu komut satırından değişiklikleri (`git commit -m 'Remove venv'`) veya gelen **değişiklikleri** sayfasında **Takım Gezgini**.

## <a name="step-1-4-examine-the-boilerplate-code"></a>1-4. adım: Demirbaş kod inceleyin

Proje oluşturma işlemi tamamlandıktan sonra Demirbaş Django proje kodunu incelemek (olduğu yeniden CLI komutu tarafından oluşturulan aynı `django-admin startproject <project_name>`).

1. Projenizde köküdür `manage.py`, Visual Studio Proje başlangıç dosyası olarak otomatik olarak ayarlayan Django komut satırı yönetim yardımcı programı. Kullanarak komut satırı yardımcı programını çalıştırın `python manage.py <command> [options]`. Ortak Django görevler için Visual Studio uygun menü komutlarını sağlar. ' Nde projeye sağ **Çözüm Gezgini** seçip **Python** listesini görmek için. Bu komutların Bu öğretici esnasında karşılaştığınız.

    ![Bağlam menüsü bir Python Django komutlarını proje](media/django/step01-django-commands-menu.png)

1. Projenizde bir klasör aynı projesi olarak adlandırılır. Temel Django proje dosyalarını içerir:

    - `__init.py`: Python bu klasör bir Python paket olduğunu söyler boş bir dosya.
    - `wsgi.py`: projenizi hizmet WSGI uyumlu web sunucuları için bir giriş noktası. Genellikle bu dosyanın özel olarak bırakın-web sunucuları için üretim kancaları sağladığı aynıdır.
    - `settings.py`: bir web uygulaması geliştirme sırasında değiştirme Django proje ayarlarını içerir.
    - `urls.py`: geliştirme sırasında aynı zamanda değiştirmeniz Django projesi için içindekiler tablosu içerir.

    ![Çözüm Gezgini'nde Django proje dosyaları](media/django/step01-django-project-in-solution-explorer.png)

1. Daha önce belirtildiği gibi Visual Studio şablon de ekler bir `requirements.txt` dosyayı projenize Django paket bağımlılığı belirtme. Bu dosyasının varlığı, ilk proje oluşturulurken sanal bir ortam oluşturmak için davet ' dir.

### <a name="question-can-visual-studio-generate-a-requirementstxt-file-from-a-virtual-environment-after-i-install-other-packages"></a>Soru: diğer paketleri yüklendikten sonra Visual Studio requirements.txt dosyasını sanal ortamdan oluşturabilir miyim?

Yanıt: Evet. Genişletme **Python ortamları** düğümü, sanal ortamınıza sağ tıklatın ve seçin **requirements.txt Oluştur** komutu. Bu komut düzenli kullanmak üzere kendi iyi ortamı değiştirin ve yürütme değişiklikler `requirements.txt` yanı sıra bu ortamda bağımlı herhangi bir kod değişiklikleri kaynak denetimi. Derleme sunucusundaki sürekli tümleştirme ayarladıysanız, ortamı değiştirmek her dosya ve değişiklikleri oluşturmanız gerekir.

## <a name="step-1-5-run-the-empty-django-project"></a>1-5. adım: boş Django projesi çalıştırma

1. Visual Studio'da seçin **hata ayıklama** > **hata ayıklamayı Başlat** (F5) veya **Web sunucusu** (farklılık may gördüğünüz tarayıcısı) araç çubuğunda:

    ![Visual Studio'da Web sunucusu Çalıştır araç çubuğu düğmesi](media/django/run-web-server-toolbar-button.png)

1. Çalıştıran bir sunucuda anlamına gelir komutunu çalıştırarak `manage.py runserver <port>`, Django'nın yerleşik geliştirme sunucusu başlatır. Visual Studio "hata ayıklayıcısını başlatmak üzere başarısız" içeren bir ileti sağ tıklayın, herhangi bir başlatma dosyası sahip hakkında diyorsa `manage.py` içinde **Çözüm Gezgini** seçip **başlangıç dosyası olarak ayarlamak**.

1. Sunucu başlattığınızda, aynı zamanda görüntüler sunucu günlüğü'nü açın bir konsol penceresi görürsünüz. Visual Studio otomatik olarak bir tarayıcı penceresinde açar `http://localhost:<port>`. Ancak, Django proje hiçbir uygulama olduğundan, Django ne kadar elinizde düzgün çalıştığını kabul etmek için yalnızca bir varsayılan sayfa gösterir:

    ![Django proje varsayılan görünümü](media/django/step01-first-run-success.png)

1. İşiniz bittiğinde, konsol penceresini kapatarak ya da kullanarak sunucu stop **hata ayıklama** > **durdurma hata ayıklama** Visual Studio'da komutu.

### <a name="question-is-django-a-web-server-as-well-as-a-framework"></a>Soru: Django web sunucularının yanı sıra bir çerçeve mi?

Yanıt: Evet ve Hayır. Django geliştirme amacıyla kullanılan bir yerleşik web sunucusu yok. Bu web sunucusu gibi ne zaman web uygulamasını yerel olarak çalıştırdığınızda ne kullanılır Visual Studio'da hata ayıklama. Ancak, bir web ana bilgisayara dağıttığınızda, ana bilgisayarın web sunucusu yerine Django kullanır. `wsgi.py` Django proje modülünde üretim sunucularına takma mvc'deki.

### <a name="question-whats-the-difference-between-using-the-debug-menu-commands-and-the-server-commands-on-the-projects-python-submenu"></a>Soru: Hata ayıklama menü komutları ve sunucu komutları projenin Python menüdeki kullanma arasındaki fark nedir?

Yanıt: ek olarak **hata ayıklama** menü komutları ve araç çubuğu düğmeleri, sunucu kullanarak başlatabilirsiniz **Python** > **Server'i** veya **Python** > **Run hata ayıklama sunucusu** projenin bağlam menüsündeki komutlar. Her iki komutları çalıştıran sunucunun yerel URL'sini (localhost:port) bkz bir konsol penceresi açın. Ancak, bir tarayıcı bu URL'yi ile el ile açmanız gerekir ve hata ayıklama server çalıştıran otomatik olarak Visual Studio hata ayıklayıcısı başlamaz. Kullanmak istiyorsanız, bir hata ayıklayıcısı çalışan işlemi daha sonra iliştirebilirsiniz **hata ayıklama** > **ekleme işlemi için** komutu.

## <a name="next-steps"></a>Sonraki adımlar

Bu noktada, temel Django proje uygulamalardan içermiyor. Sonraki adımda bir uygulama oluşturun. Genellikle Django uygulamaları Django proje'den fazla ile çalışmak için şu anda Demirbaş dosyaları hakkında daha fazla bilmeniz gerek yoktur.

> [!div class="nextstepaction"]
> [Görünümleri ve sayfa şablonları ile Django uygulaması oluşturma](learn-django-in-visual-studio-step-02-create-an-app.md)

## <a name="going-deeper"></a>Daha derin gitme

- Django proje kodunu: [ilk Django uygulamanız yazma, bölüm 1](https://docs.djangoproject.com/en/2.0/intro/tutorial01/) (docs.djangoproject.com)
- Yönetim yardımcı programı: [django yönetim ve manage.py](https://docs.djangoproject.com/en/2.0/ref/django-admin/) (docs.djangoproject.com)
- Öğretici kaynak kodu github'da: [Microsoft/python-örnek-vs-learning-django](https://github.com/Microsoft/python-sample-vs-learning-django)
