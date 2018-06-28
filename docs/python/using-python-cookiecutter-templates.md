---
title: Python için CookieCutter uzantısı
description: Visual Studio için Python kodu şablonları bulmak ve bu şablonlardan proje oluşturmak için grafik Cookiecutter uzantısı destekler.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: a4cee1acbeeafb1360912f1f7342310a51ad54ff
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37058470"
---
# <a name="using-the-cookiecutter-extension"></a>Cookiecutter uzantısını kullanma

[Cookiecutter](https://cookiecutter.readthedocs.io/en/latest/) şablonları bulmak, şablon seçenekleri giriş ve projeler ve dosyaları oluşturmak için bir grafik kullanıcı arabirimi sağlar. Visual Studio 2017 ile eklemiştir ve Visual Studio'nun önceki sürümleri ayrı olarak yüklenebilir.

Cookiecutter gerektirir Python 3.3 veya üzeri (32 bit veya 64 bit) veya Anaconda 3 4.2 veya üzeri (32 bit veya 64 bit). Uygun bir Python yorumlayıcısı kullanılabilir değilse, Visual Studio bir uyarı görüntüler. Visual Studio çalışırken bir Python yorumlayıcısı yüklerseniz, yeni yüklenen yorumlayıcı algılamak için Cookiecutter araç çubuğundaki Giriş düğmesini tıklatın. (Bkz [Python ortamları](managing-python-environments-in-visual-studio.md) genel ortamları hakkında daha fazla bilgi için.)

Bir kez yüklendikten sonra seçin **Görünüm > Cookiecutter Explorer** onun penceresi açmak için:

![Cookiecutter ana penceresi](media/cookiecutter-overview.png)

## <a name="cookiecutter-workflow"></a>Cookiecutter iş akışı

İzleyen bölümlerde açıklanan aynıdır, Cookiecutter çalışmak gözatma ve bir şablonu seçilmesi, yerel bilgisayarınıza kopyalama seçeneklerini ayarlama ve bu şablondan kod oluşturma işlemi kullanır.

### <a name="browsing-templates"></a>Gözatma şablonları

Cookiecutter giriş sayfası aşağıdaki gruplara ayrılmış aralarından seçim yapabileceğiniz şablonları listesini görüntüler:

| Grup | Açıklama |
| --- | --- |
| Yüklü | Yerel bilgisayarınızda yüklü şablonlar. Çevrimiçi bir şablon kullanıldığında, kendi deposu için bir alt klasörü otomatik olarak kopyalanmış `~/.cookiecutters`. Seçili yüklü şablon basarak silebilirsiniz **Del**. |
| Önerilen | Şablonları önerilen akıştan yüklendi. Varsayılan akış Microsoft tarafından seçkin. Bkz: [Cookiecutter seçenekleri](#cookiecutter-options) aşağıda akış özelleştirme hakkında bilgi. |
| GitHub | Cookiecutter anahtar sözcüğü için GitHub arama sonuçları. Sonuçları github'dan gelen geri anlatır, daha fazla sonuç mevcutsa, **yük daha fazla** listesinin sonunda görüntülenir. |
| Özel | Özel bir konuma arama kutusuna girdiğinizde, bu grupta belirir. Yerel diskinize GitHub deposuna tam yolunu yazın veya bir klasörün tam yolunu kullanabilirsiniz. |

### <a name="cloning"></a>Kopyalama

Ardından bir şablonu seçtiğinizde, **sonraki**, Cookiecutter çalışabilmesi için yerel bir kopya yapar.

Bir şablondan seçerseniz **önerilen** veya **GitHub** gruplar veya arama kutusuna özel bir URL girin ve bu şablonu seçin, kopyalanabilen ve yerel bilgisayarınızda yüklü. Bu şablon önceki Visual Studio oturumunda yüklediyseniz, otomatik olarak silinir ve en son sürüm kopyalanamıyor.

Bir şablondan seçerseniz **yüklü** grubuna veya arama kutusuna özel klasör yolu girin ve bu şablonu seçin Visual Studio Şablon Kopyalama olmadan yükler.

> [!Important]
> Cookiecutter Şablonları altında tek bir klasör kopyalandığı `~/.cookiecutters`. Her alt klasör GitHub kullanıcı adı dahil değildir git deposu adından sonra adlandırılır. Aynı ada sahip farklı yazarların gelen farklı şablonlar kopyalarsanız çakışmaları ortaya çıkabilir. Bu durumda, Cookiecutter aynı ada sahip farklı bir şablonla mevcut şablonun üzerine yazılmasını engeller. Diğer şablon yüklemek için önce varolan bir silmeniz gerekir.

### <a name="setting-template-options"></a>Şablon seçeneklerini ayarlama

Şablon yerel olarak yüklendikten sonra Cookiecutter Cookiecutter diğer seçenekleri ile birlikte dosyaları oluşturmak için istediğiniz belirtebileceğiniz bir seçenekleri sayfasında görüntüler:

![Cookiecutter Seçenekleri sayfası](media/cookiecutter-template-options.png)

Her Cookiecutter şablon seçenekleri kendi kümesini tanımlar ve her biri (her girişi alanında önerilen metin olarak gösterilir) için varsayılan bir değer belirtir. Genellikle diğer seçenekleri kullanan dinamik bir değer olduğunda bir kod parçacığı varsayılan bir değer olabilir. 

Belirli seçenekler için varsayılan değerleri olan bir kullanıcı yapılandırma dosyası özelleştirmek kullanılabilir. Cookiecutter uzantısı bir kullanıcı yapılandırma dosyası algıladığında, Kullanıcı Yapılandırması'nın varsayılan değerlerle şablonun varsayılan değerlerini geçersiz kılar. Bu davranış içinde ele alınmıştır [Kullanıcı Yapılandırması](https://cookiecutter.readthedocs.io/en/latest/advanced/user_config.html) Cookiecutter belgelerine bölümü.

Şablon sonra kod oluşturma, ek bir çalıştırmak için belirli Visual Studio görevleri belirtiyorsa **tamamlanma ek görevleri çalıştırmak** seçeneği dışında bu görevleri kabul etmek izin veren görünür. En yaygın görevlerin bir web tarayıcısı açın, düzenleyicide açık dosyalar, bağımlılıkları yükler ve benzeri için kullanılır.

### <a name="create"></a>Create

Seçeneklerinizi ayarladıktan sonra seçin **oluşturma** (bir uyarı görünür çıkış klasörü boş değilse) kodu oluşturmak için. Şablonun çıkışıyla tanıdık ve dosyaların üzerine yazılması sizin için sorun varsa, uyarıyı yok sayabilirsiniz. Aksi takdirde seçin **iptal**, boş bir klasör belirtin ve sonra el ile oluşturulan dosyalar boş çıkış klasörüne kopyalayın.

Dosyalar başarıyla oluşturulduktan sonra Cookiecutter dosyalarında açmak için bir seçenek sağlar **Çözüm Gezgini**:

![Cookiecutter gösteren Çözüm Gezgini komutu](media/cookiecutter-files-created.png)

## <a name="cookiecutter-options"></a>Cookiecutter seçenekleri

Cookiecutter seçenekleri aracılığıyla kullanılabilen **Araçlar > Seçenekler > Cookiecutter**:

![Cookiecutter seçenekleri](media/cookiecutter-tools-options.png)

| Seçenek | Açıklama |
| --- | --- |
| Akış URL'si önerilir | Önerilen şablonlarının konumunu akış. Bir URL veya bir yerel dosya yolu olabilir. URL Microsoft seçkin varsayılan akış kullanmak için boş bırakın. Akış şablon konumları, satır başı tarafından ayrılmış basit bir listesini sağlar. Seçkin akışa değişiklik isteğinde bulunmak için bir çekme isteği karşı olun [GitHub kaynağında](https://github.com/Microsoft/PTVS/blob/master/Python/Product/Cookiecutter/CookiecutterFeed.txt). |
| Yardımı Göster | Pencerenin üst kısmındaki Cookiecutter Yardım bilgi çubuğunun görünürlüğünü denetler. |

## <a name="optimizing-cookiecutter-templates-for-visual-studio"></a>Visual Studio için en iyi duruma getirme Cookiecutter şablonları

Temel bir Cookiecutter şablon yazma bkz [Cookiecutter belgelerine](https://cookiecutter.readthedocs.io/en/latest/first_steps.html). Visual Studio Cookiecutter uzantısı Cookiecutter v1.4 için oluşturulan şablonlar destekler.

Şablon değişkenleri varsayılan çizmeye (dize veya listesi) veri türüne bağlıdır:

- Dizesi: Değişken adı, değer ve varsayılan değerini gösteren bir filigran girileceği metin kutusu etiketi. Araç İpucu metin kutusundaki varsayılan değeri gösterir.
- Listesi: Değişken adı, bir değer seçmek için açılan kutu etiketi. Birleşik giriş kutusu araç ipucu varsayılan değerini gösterir.

Bu işleme hakkında ek meta verilerde belirterek geliştirmek mümkündür, `cookiecutter.json` Visual Studio belirli (ve Cookiecutter CLI tarafından yoksayılan) dosyası. Tüm özellikleri isteğe bağlıdır:

| Özellik | Açıklama |
| --- | --- |
| Etiketle | Değişken adı yerine bir değişken Düzenleyicisi'ni yukarıda görünen belirtir. |
| Açıklama | Bu değişken için varsayılan değer yerine düzenleme denetimindeki görünen araç ipucu belirtir. |
| URL | URL gösteren araç ipucu içeren bir köprü etiketi değiştirir. Köprüyü tıklatarak kullanıcının varsayılan tarayıcı bu URL'yi açar. |
| Seçici | Bir değişken için Düzenleyicisi özelleştirmesini sağlar. Şu seçicileri şu anda desteklenir:<ul><li>`string`: Standart metin kutusu, dizeler için varsayılan değer.</li><li>`list`: Standart birleşik giriş kutusu, varsayılan listeler.</li><li>`yesno`: Arasında seçim yapma birleşik giriş kutusu `y` ve `n`, dizeleri.</li><li>`odbcConnection`: Bir veritabanı bağlantı iletişim kutusunu açar, bir "..." düğmesi metin kutusu.</li></ul> |

Örnek:

```json
{
    "site_name": "web-app",
    "python_version": ["3.5.2", "2.7.12"],
    "use_azure": "y",

    "_visual_studio": {
        "site_name": {
            "label": "Site name",
            "description": "E.g. <site-name>.azurewebsites.net (can only contain alphanumeric characters and `-`)"
        },
        "python_version": {
            "label": "Python version",
            "description": "The version of Python to run the site on"
        },
        "use_azure" : {
            "label": "Use Azure",
            "description": "Include Azure deployment files",
            "selector": "yesno",
            "url": "https://azure.microsoft.com"
        }
    }
}
```

### <a name="running-visual-studio-tasks"></a>Visual Studio görevleri çalıştırma

Cookiecutter adlı bir özelliği olan *Post-Generate Kancalarını* sağlayan dosya oluşturulduktan sonra rasgele Python kodu çalıştırmak için. Esnek rağmen Visual Studio kolay erişim izin vermez.

Örneğin, bir dosyayı Visual Studio düzenleyicisinde ya da kendi web tarayıcısında açın veya Visual Studio, bir sanal ortam oluşturmak ve paket gereksinimlerini yüklemek için kullanıcıdan kullanıcı arabirimini tetikleyicisi isteyebilirsiniz.

Bu senaryolar izin vermek için Visual Studio genişletilmiş meta verilerde arar `cookiecutter.json` Çözüm Gezgini'nde veya dosyaları var olan bir projeye eklendikten sonra oluşturulan dosyalar kullanıcı açıldıktan sonra çalıştırılacak komut açıklar. (Kullanıcı temizleyerek çalışan görevlerin dışında yeniden tercih edebilirsiniz **tamamlanma ek görevleri çalıştırmak** şablonu seçeneklerinde.)

Örnek:

```json
"_visual_studio_post_cmds": [
    {
        "name": "File.OpenFile",
        "args": "{{cookiecutter._output_folder_path}}\\readme.txt"
    },
    {
        "name": "Cookiecutter.ExternalWebBrowser",
        "args": "https://docs.microsoft.com"
    },
    {
        "name": "Python.InstallProjectRequirements",
        "args": "{{cookiecutter._output_folder_path}}\\dev-requirements.txt"
    }
]
```

Komutları adıyla belirtilen ve Visual Studio yerelleştirilmiş yüklemelerini üzerinde çalışmak için yerelleştirilmemiş (İngilizce) adı kullanmanız gerekir. Test ve Visual Studio komut penceresinde komut adlarının keşfedin.

Tek bir bağımsız değişken geçirmek istiyorsanız, önceki örnekte gibi bir dize olarak belirtin.

Bağımsız değişken geçirmek gerekmiyorsa, boş bir dize bırakın veya JSON öğesinden çıkarın:

```json
"_visual_studio_post_cmds": [
    {
        "name": "View.WebBrowser"
    }
]
```

Bir dizi için birden fazla bağımsız değişkenini kullanın. Anahtarlar için anahtarı ve değeri ayrı bağımsız değişkenleriyle bölme ve uygun tırnak içine almak kullanın. Örneğin:

```json
"_visual_studio_post_cmds": [
    {
        "name": "File.OpenFile",
        "args": [
            "{{cookiecutter._output_folder_path}}\\read me.txt",
            "/e:",
            "Source Code (text) Editor"
        ]
    }
]
```

Bağımsız değişkenler diğer Cookiecutter değişkenlere başvurabilir. İç Yukarıdaki örneklerde `_output_folder_path` değişkeni oluşturulan dosyalar için mutlak bir yol oluşturmak için kullanılır.

Unutmayın `Python.InstallProjectRequirements` yalnızca dosya varolan bir projesine eklenirken works komutu. Bu sınırlama, çünkü komutu, Çözüm Gezgini'nde Python projesi tarafından işlenir ve Çözüm Gezgini'nde sırada - klasör görünümü ileti almak için proje bulunmaktadır. Gelecek sürümlerinden sınırlaması win kaldırmak (ve daha iyi klasör görünümü genel desteklemek) umuyoruz.

## <a name="troubleshooting"></a>Sorun giderme

### <a name="error-loading-template"></a>Hata yükleme şablonu

İçinde geçersiz veri türleri, boolean gibi bazı şablonlar kullanabilecek kendi `cookiecutter.json`. Bu tür örnekleri seçerek şablon yazarı rapor **sorunları** şablonu Bilgi bölmesinde bağlantı.

### <a name="hook-script-failed"></a>Kanca komut başarısız oldu

Bazı şablonlar Cookiecutter kullanıcı Arabirimi ile uyumlu olmayan sonrası oluşturma komut dosyaları kullanabilirsiniz. Örneğin, kullanıcı girişi için bir terminal Konsolu olmaması nedeniyle başarısız sorgu komutlar.

### <a name="hook-script-not-supported-on-windows"></a>Kanca betik Windows desteklenmiyor

Son betik ise `.sh`, sonra da, Windows bilgisayarınızdaki bir uygulamayla ilişkili olmayabilir. Uyumlu bir uygulamayı Windows Mağazası'nda bulmak için isteyen bir Windows iletişim kutusu görebilirsiniz.

### <a name="templates-with-known-issues"></a>Şablonları ile ilgili bilinen sorunlar

Kopya hataları:

- **wildfish/cookiecutter-django-crud** (geçersiz karakter `|` alt klasör adı)
- **cookiecutter pyvanguard** (geçersiz karakter `|` alt klasör adı)

Yükleme Hataları:

- **chrisdev/wagtail-cookiecutter-foundation** (bir boolean türü içinde cookiecutter.json kullanır)
- **cookiecutter/quintoandar-android** (hiçbir şablon klasör)

Hataları çalıştırın:

- **iknite/cookiecutter-ansible-role** (son kanca betik, konsol giriş gerektirir)
- **benregn/cookiecutter-django-ansible** (Jinja hatası)

Kullanır bash (önemli değildir):

- **openstack-dev/cookiecutter**
