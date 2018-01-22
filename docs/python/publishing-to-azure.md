---
title: "Visual Studio'dan Azure App Service'e bir Python uygulama yayımlama | Microsoft Docs"
ms.custom: 
ms.date: 09/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: 32e2f0d889bac5313201fd65bf98ce2a8243a284
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2018
---
# <a name="publishing-to-azure-app-service"></a>Azure uygulama hizmeti yayımlama

Visual Studio doğrudan doğrudan Azure App Service'e bir Python web uygulaması yayımlama yeteneği sağlar. Azure uygulama hizmeti yayımlamayı anlamına gelir sunucuya gerekli dosyaları kopyalanıyor ve uygun bir ayar `web.config` nasıl uygulamanızı başlatmak web sunucusuna bildirir dosya. 

Yayımlama işlemi, Visual Studio 2015 ve Visual Studio 2017 arasında farklılık gösterir. Özellikle, Visual Studio 2015 oluşturulmasını da dahil olmak üzere bu adımlardan bazıları otomatikleştirir `web.config`, ancak bu Otomasyon uzun vadeli esneklik ve denetim sınırlar. Visual Studio 2017 daha fazla el ile yapılacak adımlar gerektirir, ancak Python ortamınız üzerinde daha kesin denetim sağlar. Her iki seçenek aşağıda açıklanmıştır.

Bu konuda:

- [Önkoşulları](#prerequisites)
- [Bir Azure uygulama hizmeti oluşturma](#create-an-azure-app-service)
- [Python uygulama hizmetini yapılandırma](#configure-python-on-azure-app-service)
- [Uygulama hizmeti - Visual Studio 2017 yayımlama](#publish-to-app-service---visual-studio-2017)
- [Uygulama hizmeti - Visual Studio 2015 yayımlama](#publish-to-app-service---visual-studio-2015)
- [Uygulama hizmeti uzaktan hata ayıklama](#remote-debugging-on-azure-app-service)

> [!Note]
> Visual Studio 2015 ve Visual Studio 2017 arasındaki değişiklikleri arka planda için bkz: blog yayını, [Visual Studio 2017 Azure'da Yayımla](https://blogs.msdn.microsoft.com/pythonengineering/2016/12/12/publish-to-azure-in-vs-2017/).

## <a name="prerequisites"></a>Önkoşullar

Bu kılavuz için Bottle, Flask ve Django çerçevesinde tabanlı bir web uygulaması projesi gerekir. Henüz bir proje yok ve yayımlama işlemi denemek istiyorsanız bir basit test projesi gibi oluşturun:

1. Visual Studio'da seçin **Dosya > Yeni > Proje**, "Bottle" için arama yapın, seçin **Bottle Web projesi**belirtin ve ad proje için bir yol tıklatıp **Tamam**. (Bottle şablonu ile Python geliştirme iş yükü bulunur; bkz [yükleme](installing-python-support-in-visual-studio.md).)

1. Seçerek dış paketleri yüklemek için istemleri izleyin **sanal bir ortama yükleme** ve sanal ortam için tercih edilen temel yorumlayıcı. Uygulama hizmeti yüklü Python sürümü ile bu seçenek genellikle Bul.

1. F5 tuşuna basarak veya seçerek projeyi yerel olarak test **hata ayıklama > hata ayıklamayı Başlat**.

## <a name="create-an-azure-app-service"></a>Bir Azure uygulama hizmeti oluşturma

Yayımlama için bir hedef uygulama hizmeti gerektirir. Bu amaç için bir Azure aboneliği kullanarak bir uygulama hizmeti oluşturabilir veya geçici bir siteyi kullanabilirsiniz.

Zaten bir aboneliğiniz yoksa, başlayan bir [ücretsiz tam Azure hesap](https://azure.microsoft.com/free/), Azure Hizmetleri için geniştir iadeleri içerir. Ayrıca olmayı göz önünde bulundurun [Visual Studio geliştirme Essentials](https://azure.microsoft.com/pricing/member-offers/vs-dev-essentials/), hangi size $25 kredi tam yıl her ay.

> [!Tip]
> Hesabınızı doğrulamak kredi kartı için Azure ister rağmen kart ücret alınmaz. Ayrıca bir [harcama sınırı](/azure/billing/billing-spending-limit) hiçbir ek ücret gerçekleşmesini garanti etmek için ücretsiz kredinizi eşittir. Ayrıca, Azure ücretsiz uygulama hizmeti sonraki bölümde açıklandığı gibi basit bir sınama uygulamaları için idealdir planı katmanı sağlar.

### <a name="using-a-subscription"></a>Bir aboneliği kullanma

Bir etkin Azure aboneliği ile bir uygulama hizmeti boş bir Web uygulaması ile aşağıdaki gibi oluşturun:

1. Adresinde oturum açın [portal.azure.com](https://portal.azure.com).
1. Seçin **+ yeni**seçeneğini belirleyip **Web + mobil** arkasından **Web uygulaması**.
1. Web uygulaması için bir ad belirtin, bırakın **kaynak grubu** "Yeni Oluştur" için ve **Windows** işletim sistemi olarak.
1. Seçin **App service planı/konumu**seçin **Yeni Oluştur**ve bir ad ve konum belirtin. Ardından **fiyatlandırma katmanı**, doğru aşağı kaydırın ve seçin **F1 ücretsiz** planlama, basın **seçin**, ardından **Tamam** ve ardından **Oluşturma**.
1. (İsteğe bağlı) Uygulama hizmeti oluşturulduktan sonra dosyayı bulun, seçin **Get yayımlama profili**ve dosyayı yerel olarak kaydedin.

### <a name="using-a-temporary-app-service"></a>Geçici bir uygulama hizmeti kullanma

Geçici bir uygulama hizmeti bir Azure aboneliğine gerek duymadan aşağıdaki gibi oluşturun:

1. Tarayıcınızı açın [try.azurewebsites.net](https://try.azurewebsites.net).
1. Seçin **Web uygulaması** uygulama türü için ardından **sonraki**.
1. Seçin **boş Site**, ardından **oluşturma**.
1. Tercih ettiğiniz sosyal olarak oturum açma bilgileriyle oturum açın ve kısa bir süre sonra sitenizin görüntülenen URL'de hazırdır.
1. Seçin **yayımlama profili indirme** kaydedip `.publishsettings` daha sonra kullanmak dosya.

## <a name="configure-python-on-azure-app-service"></a>Azure uygulama hizmeti Python yapılandırın

Bir uygulama hizmeti boş bir sahip olduktan sonra Web çalışan uygulama (veya aboneliğinizdeki ücretsiz bir sitede), açıklandığı gibi Python seçilen sürümünü yükleyin [yönetme Python Azure App Service'te](managing-python-on-azure-app-service.md). Visual Studio 2017 yayımlama için bu konuda açıklandığı gibi yüklü olan site uzantısı Python yorumlayıcı tam yolunu kaydedin.

İsterseniz, ayrıca yükleyebilirsiniz `bottle` işlemi bu yönergeleri kullanarak diğer parçası Bu izlenecek adımları şekilde, paketin yüklü olarak paketi.

## <a name="publish-to-app-service---visual-studio-2017"></a>Uygulama hizmeti - Visual Studio 2017 yayımlama

Azure App Service için Visual Studio 2017 kopyalarından sunucuya projenizdeki yalnızca dosyaları yayımlama. Bu nedenle, sunucu ortamı yapılandırmak için gerekli dosyaları oluşturmak için gereklidir.

1. Visual Studio'da **Çözüm Gezgini**, projeye sağ tıklayın ve seçin **Ekle > Yeni öğe...* . Görüntülenen iletişim kutusunda, "Azure web.config (Fast CGI)" şablonu ve select Tamam seçme. Bu oluşturur bir `web.config` proje kök dosyasında.

1. Değiştirme `PythonHandler` girişi `web.config` böylece sunucuda Python yükleme yolunu eşleşir. Örneğin, Python 3.6.1 x64 giriş aşağıdaki gibi görünmelidir:

    ```xml
    <system.webServer>
      <handlers>
        <add name="PythonHandler" path="*" verb="*" modules="FastCgiModule"
            scriptProcessor="D:\home\Python361x64\python.exe|D:\home\Python361x64\wfastcgi.py"
            resourceType="Unspecified" requireAccess="Script"/>
      </handlers>
    </system.webServer>
    ```

1. Ayarlama `WSGI_HANDLER` girişi `web.config` framework için uygun şekilde kullanmakta olduğunuz:

    - **Bottle**: sonra parantez eklemek `app.wsgi_app` aşağıda gösterildiği gibi. Bu nesne bir işlev olduğundan bu gereklidir (bkz: `app.py`) yerine bir değişkeni:

        ```xml
        <!-- Bottle apps only -->
        <add key="WSGI_HANDLER" value="app.wsgi_app()"/>
        ```

    - **Flask**: değişiklik `WSGI_HANDLER` değeri `<project_name>.app` burada `<project_name>` projenizin adını eşleşir. Bakarak tam tanımlayıcı bulabilirsiniz `from <project_name> import app` deyiminde `runserver.py`. Örneğin, "FlaskAzurePublishExample" adlı projesi, giriş şu şekilde görünür:

        ```xml
        <!-- Flask apps only: change the project name to match your app -->
        <add key="WSGI_HANDLER" value="FlaskAzurePublishExample.app"/>
        ```

    - **Django**: iki değişiklik için gereken `web.config` Django uygulamaları için. İlk olarak, değişiklik `WSGI_HANDLER` değeri `django.core.wsgi.get_wsgi_application()` (nesne `wsgi.py` dosyası):

        ```xml
        <!-- Django apps only -->
        <add key="WSGI_HANDLER" value="django.core.wsgi.get_wsgi_application()"/>
        ```

        İkinci olarak, için aşağıda aşağıdaki girişi ekleyin `WSGI_HANDLER`değiştirerek `DjangoAzurePublishExample` projenizin adına sahip:

        ```xml
        <add key="DJANGO_SETTINGS_MODULE" value="DjangoAzurePublishExample.settings" />
        ```

1. **Yalnızca Django uygulamaları**: projenizin adına eşleşen klasöründe açın `settings.py` ve site URL'si etki alanınıza ekleyin `ALLOWED_HOSTS` aşağıda gösterildiği gibi 'vspython test 02.azurewebsites .net', URL'SİYLE Elbette değiştirin:

    ```python
    # Change the URL to your specific site
    ALLOWED_HOSTS = ['vspython-test-02.azurewebsites.net']
    ```

    Hata dizi sonuçlarında URL'nizi eklemek için hata "DisallowedHost / geçersiz HTTP_HOST başlığı: '\<site URL'si\>'. Eklemeniz gerekebilir '\<site URL'si\>' ALLOWED_HOSTS için. "

1. İçinde **Çözüm Gezgini**, projenizin aynı adlı klasörü genişletin, sağ `static` klasöründe seçin **Ekle > Yeni öğe...** , "Azure statik web.config dosyaları" şablonunu seçin ve Seç **Tamam**. Bu eylem başka oluşturur `web.config` içinde `static` bu klasör için işleme Python devre dışı bırakır klasör. Bu yapılandırma, varsayılan web sunucusu için Python uygulama kullanmak yerine statik dosyaları için istekleri gönderir.

1. Visual Studio, projenizin sonra kaydedin **Çözüm Gezgini**, projeye sağ tıklayın ve seçin **Yayımla**.

1. İçinde **Yayımla** görünen sekmesini yayımlama hedefi seçin:

    a. Azure aboneliğiniz: seçin **Microsoft Azure App Service**, ardından **var olanı Seç** arkasından **Yayımla**. Uygulama hizmeti ve uygun abonelik seçebilirsiniz bir iletişim kutusu görüntülenir. Uygulama hizmeti görünmüyorsa, indirilen yayımlama profili için geçici bir uygulama hizmeti aşağıda açıklandığı gibi kullanın.

    ![Azure 1. adım için Visual Studio 2017 mevcut abonelikleri yayımlama](media/tutorials-common-publish-1a-2017.png)

    b. Geçici bir uygulama hizmeti üzerinde try.azurewebsites.net kullanıyorsanız veya aksi halde bir yayımlama profili kullanmak gerekirse, seçin  **>**  bulmak için Denetim **içe profil**, bu seçenek, ardından seçin seçin **Yayımla**. Bu konumunu ister `.publishsettings` dosyasını indirdiğiniz daha önce.

    ![Azure 1. adım için Visual Studio 2017 geçici uygulama hizmeti yayımlama](media/tutorials-common-publish-1b-2017.png)

1. Visual Studio yayımlama durumu "Web yayımlama etkinliğini" penceresinde ve yayımlama penceresinde görüntüler. Yayımlama tamamlandıktan sonra varsayılan tarayıcı site URL'sini açar. URL de Yayımla penceresinde görüntülenir.

1. Tarayıcı oturum açtığında, "İç sunucu hatası oluştuğundan sayfa görüntülenemiyor." iletisini görürseniz Bu ileti, Python ortamınıza sunucu tam olarak, bu durumda aşağıdaki adımları uygulayın yapılandırılmadığını gösterir:

    a. Yeniden bakın [yönetme Python Azure App Service'te](managing-python-on-azure-app-service.md), Python uzantı yüklü site uygun olduğundan emin olun.

    b. Python yorumlayıcı yolunu denetleyin, `web.config` dosya. Yolu, seçilen site uzantısı yükleme konumunu tam olarak eşleşmelidir.

    c. Kudu, uygulamanızın içinde listelenen herhangi bir paket yükseltmek için konsolu `requirements.txt` dosyası: kullanılan aynı Python klasöre gidin `web.config`, gibi `/home/python361x64`, ve açıklandığı gibi aşağıdaki komutu çalıştırın [Kudu konsol](managing-python-on-azure-app-service.md#azure-app-service-kudu-console)bölümü:

    ```command
    python -m pip install --upgrade -r /home/site/wwwroot/requirements.txt
    ```

    Bu komutu çalıştırdığınızda izni hatalar görürseniz, site uzantısı klasörünüzde komutu çalıştırdığınız bir kez daha denetleyin ve *değil* bir uygulama hizmetin varsayılan Python yükleme klasöründeki. Bu varsayılan ortamları değiştirilemiyor çünkü paketleri yüklemeye çalışırken kesinlikle başarısız olur.

    d. Ayrıntılı hata çıktı için aşağıdaki satırı ekleyin `web.config` içinde `<system.webServer>` daha ayrıntılı hata çıkışı sağlar düğümü:

    ```xml
    <httpErrors errorMode="Detailed"></httpErrors>
    ```

    e. Uygulama hizmeti yeni paketler yüklendikten sonra yeniden deneyin. Yeniden başlatma değiştirilirken gerekli değil `web.config`, uygulama hizmeti otomatik yaptığı gibi her yeniden `web.config` değişiklikler.

    > [!Tip] 
    > Uygulamanızın herhangi bir değişiklik yaparsanız `requirements.txt` dosya, artık bu dosyada listelenen paketleri yüklemek için yeniden Kudu konsol kullandığınızdan emin olun. 

1. Sunucu ortamı tam olarak yapılandırdıktan sonra tarayıcıda sayfayı yenileyin ve web uygulaması görünmelidir.

    ![Uygulama hizmeti Bottle, Flask ve Django uygulamaları yayımlama sonuçları](media/azure-publish-results.png)

## <a name="publishing-to-app-service---visual-studio-2015"></a>Uygulama hizmeti - Visual Studio 2015 için yayımlama

> [!Note] 
> Bu işlemin kısa bir video bulunabilir [Visual Studio Python eğitmen: bir Web sitesi oluşturmanın](https://www.youtube.com/watch?v=FJx5mutt1uk&list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff&index=6) (youtube.com, 3m10s).

1. İçinde **Çözüm Gezgini**, proje seçme sağ **Yayımla**.

1. İçinde **Yayımla** iletişim kutusunda **Microsoft Azure App Service**:

  ![Azure adım 1 yayımlama](media/tutorials-common-publish-1.png)

1. Bir hedef seçin:

    - Bir Azure aboneliğiniz varsa, seçin **Microsoft Azure App Service** yayımlama hedefi olarak ardından aşağıdaki iletişim kutusunda var olan bir uygulama hizmetini seçin veya seçin **yeni** yeni bir tane oluşturmak için.
    - Try.azurewebsites.net geçici bir siteden kullanıyorsanız, seçin **alma** göz sonra yayımlama hedefi olarak `.publishsettings` dosyası karşıdan site ve select **Tamam**.

1. Uygulama hizmeti ayrıntıları görünür **Yayımla** iletişim kutusu **bağlantı** sekmesini tıklatın.

  ![Azure adım 2 Yayımla](media/tutorials-common-publish-2.png)

1. Seçin **sonraki >** ek ayarlarını gözden geçirmek için gerektiği gibi. Planlıyorsanız, [Python kodunuzu Azure üzerinde uzaktan hata ayıklama](debugging-azure-remote.md), ayarlamalısınız **yapılandırma** için **hata ayıklama**

1. Seçin **yayımlama**. Uygulamanızın Azure'a dağıtıldığında, varsayılan tarayıcınız, bu sitede açılır. 

Bu işlemin bir parçası olarak, Visual Studio ayrıca aşağıdaki adımları gerçekleştirir:

- Oluşturma bir `web.config` dosya sunucusunda uygulamanın uygun işaretçileri içeren `wsgi_app` işlev ve Python 3.4 uygulama hizmetine ait varsayılan yorumlayıcı.
- Projenin dosyaların işlenmesini kapatmak `static` klasörü (Bu kurallardır içinde `web.config`).
- Sanal ortam sunucuya yayımlayın.
- Ekleme bir `web.debug.config` dosya ve hata ayıklama araçları uzaktan hata ayıklamayı etkinleştirmek için ptvsd.

Daha önce belirtildiği gibi otomatik olarak bu adımları yayımlama işlemini basitleştirmek ancak Python ortamı denetlemek daha zor hale. Örneğin, `web.config` dosyası yalnızca sunucuda oluşturulan ancak projenize eklenmedi. Yayımlama işlemi de tüm sanal ortamı geliştirme bilgisayarınızdan kopyalama yerine çünkü sunucu yapılandırmasına bağlı olan daha uzun sürer.

Sonunda, kendi korumak isteyebilirsiniz `web.config` dosya ve kullanma `requirements.txt` sunucuda paketleri doğrudan korumak için. Kullanarak `requirements.txt`, özellikle, geliştirme ve sunucu ortamınızı her zaman aynı garantiler.

## <a name="remote-debugging-on-azure-app-service"></a>Azure uygulama hizmeti uzaktan hata ayıklama

Visual Studio 2015 hata ayıklama yapılandırmasından yayımladığınızda, işlem otomatik olarak oluşturur bir `web.debug.config` dosya ve ekleyen bir `ptvsd` gerekli hata ayıklama içeren klasörü araçları.

Visual Studio 2017 ile bunun yerine bu bileşenlerin doğrudan projeye ekleyin. ' Nde projeye sağ **Çözüm Gezgini**seçin **Ekle > Yeni öğe...** ve "Azure uzaktan hata ayıklama web.config" şablonunu seçin. Bir hata ayıklama `web.debug.config` dosya ve `ptvsd` aracı klasörüne projenizde görünür.

Bu dosyalar sunucuya dağıtıldığında (otomatik olarak Visual Studio 2015; sonraki Visual Studio 2017 ile yayımladığınızda), yönergeleri izleyin [Azure uzaktan hata ayıklama](debugging-azure-remote.md).
