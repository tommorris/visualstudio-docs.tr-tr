---
title: Azure App Service'te bir Python uygulaması yayımlama
description: Web.config dosyası için gerekli içeriği de dahil olmak üzere Visual Studio'da Python web uygulaması Azure App Service'e doğrudan yayımlanacağını.
ms.date: 07/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: a1824b9ce04b8a45c011561b73654ac3ccd49f03
ms.sourcegitcommit: 95aedf723c6be5272c3c5a2911cb2bdec50e2148
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47228922"
---
# <a name="publish-to-azure-app-service"></a>Azure App Service’e yayımlama

> [!Important]
> Azure App Service'e Python uygulamaları dağıtımı Linux için Visual Studio şu anda desteklenmiyor. Microsoft, Windows üzerinde App Service'te Python kullanımdan kaldırmaya planlamaktadır. Güncelleştirmeler kullanılabilir olduğunda bu makalede yayımlanacak. Bu arada, kapsayıcıları kullanarak Linux üzerinde App Service'e dağıtabilirsiniz. Daha fazla bilgi için [Linux üzerinde Azure App Service'te bir Python web uygulaması oluşturma](/azure/app-service/containers/quickstart-python).

Visual Studio, doğrudan Azure App Service'e Python web uygulaması yayımlama olanağı sağlar. Azure App Service'e yayımlama anlamına gelir sunucuya gerekli dosyaları kopyalanıyor ve uygun bir ayar *web.config* uygulamanızı başlatmak nasıl web sunucusuna yönlendiren dosya.

Yayımlama işlemi, Visual Studio 2017 ve Visual Studio 2015 arasında farklılık gösterir. Özellikle, Visual Studio 2015 oluşturulmasını da dahil olmak üzere bu adımlardan bazıları otomatikleştirir *web.config*, ancak bu Otomasyon uzun vadeli esneklik ile denetim sınırlar. Visual Studio 2017, daha fazla el ile yapılacak adımlar gerekli ancak Python ortamınız üzerinde daha kesin denetim sağlar. Her iki seçenek aşağıda açıklanmıştır.

> [!Note]
> Blog gönderisi, Visual Studio 2015 ve Visual Studio 2017 arasındaki değişiklikleri üzerinde arka plan bilgileri için bkz. [Visual Studio 2017'de Azure'da Yayımla](https://blogs.msdn.microsoft.com/pythonengineering/2016/12/12/publish-to-azure-in-vs-2017/).

## <a name="prerequisites"></a>Önkoşullar

Bu kılavuz için Bottle, Flask ve Django çerçevelerini temel alan bir web uygulaması projesi gerekir. Henüz bir proje yok ve yayımlama işlemi deneyin istiyorsanız, bir basit bir test projesi şu şekilde oluşturun:

1. Visual Studio'da **dosya** > **yeni** > **proje**, "Bottle için" arayın, seçin **Bottle Web projesi**, bir ad ve proje için bir yol belirtin, tıklayın **Tamam**. (Bottle Python geliştirme iş yüküyle birlikte şablonudur; bkz [yükleme](installing-python-support-in-visual-studio.md).)

1. Seçerek dış paketleri yüklemek için istemleri izleyin **sanal bir ortama yükleme** ve sanal ortam için tercih edilen temel yorumlayıcı. Genellikle bu seçenek yüklü üzerinde App Service'e Python sürümü ile Bul.

1. Yerel olarak tuşuna basarak projeyi test **F5** veya seçerek **hata ayıklama** > **hata ayıklamayı Başlat**.

## <a name="create-an-azure-app-service"></a>Bir Azure App Service oluştur

Azure'da yayımlamak için bir hedef App Service gerektirir. Bu amaç için bir Azure aboneliğini kullanarak bir App Service oluşturabilir veya geçici bir site kullanabilirsiniz.

Bir abonelik daha önce yoksa başlayan bir [ücretsiz tam Azure hesap](https://azure.microsoft.com/free/), Azure Hizmetleri için Cömert krediler içerir. Ayrıca kaydolmak için gerekli göz önünde bulundurun [Visual Studio Dev Essentials](https://azure.microsoft.com/pricing/member-offers/vs-dev-essentials/), size sağlayan 25 ABD Doları değerinde kredi tam bir yıl boyunca her ay.

> [!Tip]
> Azure hesabınızı doğrulamak bir kredi kartı için soran olsa da, kart ücretlendirilmez. Ayrıca bir [harcama limiti](/azure/billing/billing-spending-limit) herhangi bir ek ücret gerçekleşmesini sağlamak için ücretsiz kredilerinizi eşittir. Ayrıca, Azure ücretsiz bir App Service sonraki bölümde açıklandığı gibi basit bir test uygulamaları için idealdir planı katmanı sağlar.

### <a name="use-a-subscription"></a>Bir abonelik kullanın

Bir etkin Azure aboneliği ile bir App Service ile bir boş Web uygulaması gibi oluşturun:

1. Oturum açmak [portal.azure.com](https://portal.azure.com).
1. Seçin **+ yeni**, ardından **Web + mobil** ardından **Web uygulaması**.
1. Web uygulaması için bir ad belirtin, bırakın **kaynak grubu** için **Yeni Oluştur**ve **Windows** işletim sistemi olarak.
1. Seçin **App service planı/konumu**seçin **Yeni Oluştur**ve bir ad ve konum belirtin. Ardından **fiyatlandırma katmanı**, aşağı kaydırın ve **F1 ücretsiz** planlayın, basın **seçin**çizgidir **Tamam** ve ardından **Oluşturma**.
1. (İsteğe bağlı) App Service oluşturulduktan sonra bu sayfaya gidin, seçin **yayımlama profili Al**ve yerel olarak kaydedin.

### <a name="use-a-temporary-app-service"></a>Geçici bir App Service kullanın

Geçici bir App Service gibi bir Azure aboneliğine gerek duymadan oluşturun:

1. Tarayıcınızda [try.azurewebsites.net](https://try.azurewebsites.net).
1. Seçin **Web uygulaması** için uygulama türü, ardından **sonraki**.
1. Seçin **boş Site**çizgidir **Oluştur**.
1. Tercih ettiğiniz sosyal olarak oturum açma bilgilerinizle oturum açın ve kısa bir süre sonra sitenizi görüntülenen URL'SİNDE hazırdır.
1. Seçin **yayımlama profilini indirin** kaydedip *.publishsettings* daha sonra kullanacağınız dosya.

## <a name="configure-python-on-azure-app-service"></a>Azure App Service'te Python'u yapılandırma

Sonra boş bir App Service Web çalışan uygulama (veya aboneliğinizdeki ücretsiz sitesinde), açıklandığı gibi seçilen bir Python sürümünü yükleyin [Azure App Service'te Python'u yönetme](managing-python-on-azure-app-service.md). Visual Studio 2017'den yayımlama için olan site uzantısı makalesinde açıklandığı gibi yüklü Python yorumlayıcısı tam yolunu kaydedin.

İsterseniz de yükleyebilirsiniz `bottle` işlemi bu yönergeleri kullanarak bu izlenecek yolda bölümü diğer adımlar gibi paketin yüklü olduğu paketi.

## <a name="publish-to-app-service---visual-studio-2017"></a>App Service - Visual Studio 2017 yayımlama

Visual Studio 2017 kopyalar, Azure App Service'e sunucuya projenizdeki yalnızca dosyalar yayımlanıyor. Bu nedenle, sunucu ortamı yapılandırmak için gerekli dosyaları oluşturmak için gereklidir.

1. Visual Studio'da **Çözüm Gezgini**, projeye sağ tıklayıp seçin **Ekle** > **yeni öğe**. Görüntülenen iletişim kutusunda, seçmek **web.config Pro Azure (Fast CGI)** şablonu seçip alt **Tamam**. Bu, oluşturur bir *web.config* proje kökünüze dosyasında.

1. Değiştirme `PythonHandler` girişi *web.config* sunucuya Python yükleme yolu eşleşmesi (bkz [IIS yapılandırma başvurusu](https://www.iis.net/configreference) (IIS.NET) hakkında tam Ayrıntılar için). Örneğin, Python 3.6.1 x64 giriş aşağıdaki gibi görünmelidir:

    ```xml
    <system.webServer>
      <handlers>
        <add name="PythonHandler" path="*" verb="*" modules="FastCgiModule"
            scriptProcessor="D:\home\Python361x64\python.exe|D:\home\Python361x64\wfastcgi.py"
            resourceType="Unspecified" requireAccess="Script"/>
      </handlers>
    </system.webServer>
    ```

1. Ayarlama `WSGI_HANDLER` girişi *web.config* framework için uygun şekilde kullanmakta olduğunuz:

    - **Bottle**: sonra parantez ekleyin `app.wsgi_app` aşağıda gösterildiği gibi. Bir işlev, nesne olduğu için bu gereklidir (bkz *app.py*) bir değişken yerine:

        ```xml
        <!-- Bottle apps only -->
        <add key="WSGI_HANDLER" value="app.wsgi_app()"/>
        ```

    - **Flask**: değişiklik `WSGI_HANDLER` değerini `<project_name>.app` burada `<project_name>` projenizin adıyla aynıdır. Bakarak tam tanımlayıcısını bulabilirsiniz `from <project_name> import app` deyiminde *runserver.py*. Örneğin, proje "FlaskAzurePublishExample" ise, giriş şu şekilde görünür:

        ```xml
        <!-- Flask apps only: change the project name to match your app -->
        <add key="WSGI_HANDLER" value="FlaskAzurePublishExample.app"/>
        ```

    - **Django**: iki değişiklik için gereken *web.config* Django projeler için. İlk olarak değiştirmek `WSGI_HANDLER` değerini `django.core.wsgi.get_wsgi_application()` (nesne *wsgi.py* dosyası):

        ```xml
        <!-- Django apps only -->
        <add key="WSGI_HANDLER" value="django.core.wsgi.get_wsgi_application()"/>
        ```

        İkinci olarak, için aşağıda şu girişi ekleyin `WSGI_HANDLER`, değiştirmeyi `DjangoAzurePublishExample` projenizin adı:

        ```xml
        <add key="DJANGO_SETTINGS_MODULE" value="DjangoAzurePublishExample.settings" />
        ```

1. **Yalnızca Django uygulamaları**: içinde Django projesinin *settings.py* site URL'si etki alanınızı ekleyin `ALLOWED_HOSTS` aşağıda gösterildiği gibi 'vspython test 02.azurewebsites .net' URL'niz ile doğal değiştirme:

    ```python
    # Change the URL to your specific site
    ALLOWED_HOSTS = ['vspython-test-02.azurewebsites.net']
    ```

    Hatalı dizi sonuçlarını URL'nizi ekleme hatası **DisallowedHost / geçersiz HTTP_HOST başlığı: '\<site URL'si\>'. Eklemeniz gerekebilir '\<site URL'si\>' ALLOWED_HOSTS için.**

    Boş bir dizidir, Django 'localhost' otomatik olarak tanır, ancak üretim URL'nizi ekleyerek bu yetenekleri kaldırır unutmayın. Bu nedenle ayrı geliştirme ve üretim korumak isteyebilirsiniz, kopyalar için *settings.py*, veya çalışma zamanı değerlerini denetlemek için ortam değişkenlerini kullanın.

1. İçinde **Çözüm Gezgini**, projenizi aynı adlı klasörü genişletin, sağ **statik** klasörüne **Ekle** > **yeni öğe** seçin **Azure statik dosyaları web.config** şablonu ve select **Tamam**. Bu eylem başka oluşturur *web.config* içinde *statik* bu klasör için işleme Python devre dışı bırakan bir klasör. Bu yapılandırma, varsayılan web sunucusu yerine kullanarak Python uygulama statik dosyaları için istekleri gönderir.

1. Visual Studio, projenizi kaydedin **Çözüm Gezgini**, projeye sağ tıklayıp seçin **Yayımla**.

    ![Bir projenin bağlam menüsünden komut yayımlama](media/template-web-publish-command.png)

1. İçinde **Yayımla** görüntülenen sekmesini yayımlama hedefi seçin:

    1. Azure aboneliğinizi: seçin **Microsoft Azure App Service**, ardından **var olanı Seç** ardından **Yayımla**. App service ve uygun aboneliği seçebilirsiniz bir iletişim kutusu görüntülenir. App Service görünmüyorsa, geçici bir App Service için aşağıda açıklandığı gibi indirilen yayımlama profilini kullanın.

       ![Azure 1. adım için Visual Studio 2017, mevcut aboneliklerinizi yayımlama](media/tutorials-common-publish-1a-2017.png)

    2. Geçici bir App Service üzerinde try.azurewebsites.net kullanıyorsanız veya aksi halde bir yayımlama profili kullanmanız gerekir, seçin **\>** bulmak için Denetim **profili içeri aktar**, bu seçenek, ardından seçin seçin **Yayımla**. Bu konumu için ister *.publishsettings* dosyasını daha önce indirdiğiniz.

    ![Azure 1. adım için Visual Studio 2017, geçici app Service'e yayımlama](media/tutorials-common-publish-1b-2017.png)

1. Visual Studio yayımlama durumu görüntüler bir **Web yayımlama etkinliği** penceresi ve **Yayımla** penceresi. Yayımlama tamamlandıktan sonra varsayılan tarayıcı site URL'sini açar. URL Ayrıca gösterilen **Yayımla** penceresi.

1. Tarayıcı açıldığında bir ileti görebilirsiniz **bir iç sunucu hatası oluştuğundan sayfası görüntülenemiyor.** Bu ileti, sunucu üzerinde Python ortamınızı tam olarak, bu durumda aşağıdaki adımları uygulayın yapılandırılmadığını gösterir:

    1. Yeniden başvuru [Azure App Service'te Python'u yönetme](managing-python-on-azure-app-service.md), uygun olmasını sağlamaktan Python uzantısı yüklü site.

    2. Python yorumlayıcısı içinde yolunu denetleyin, *web.config* dosya. Yolu, seçilen site uzantısı yükleme konumunu tam olarak eşleşmelidir.

    3. Uygulamanızın içinde listelenen herhangi bir paket yükseltmek için Kudu konsolu kullanmak *requirements.txt* dosya: kullanılan aynı Python klasöre gidin *web.config*, gibi  */home/python361x64*, ve açıklanan şekilde aşağıdaki komutu çalıştırarak [Kudu konsolunu](managing-python-on-azure-app-service.md#azure-app-service-kudu-console) bölümü:

    ```command
    python -m pip install --upgrade -r /home/site/wwwroot/requirements.txt
    ```

    Site uzantısı klasörünüzde komutunu çalıştırıyorsanız, bu komutu çalıştırırken izin hataları görüyorsanız denetleyin ve *değil* klasöründe bir App Service'nın varsayılan Python yüklemeleri. Bu varsayılan ortamlarda değiştiremediğiniz için paketleri yüklemeye çalışmadan kesinlikle başarısız olur.

    4. Ayrıntılı hata çıktısı, aşağıdaki satırı ekleyin *web.config* içinde `<system.webServer>` düğümü, daha ayrıntılı hata çıktısı sağlar:

    ```xml
    <httpErrors errorMode="Detailed"></httpErrors>
    ```

    5. App Service, yeni paketler yüklendikten sonra yeniden başlatmayı deneyin. Yeniden başlatma değiştirilirken gerekli değil *web.config*, App Service otomatik olarak herhangi bir zamanda yeniden *web.config* değişiklikler.

    > [!Tip]
    > Uygulamanızın herhangi bir değişiklik yaparsanız *requirements.txt* dosya, yeniden artık bu dosyada listelenen herhangi bir paket yüklemek için Kudu Konsolu kullandığınızdan emin olun.

1. Sunucu ortamı tam olarak yapılandırdıktan sonra tarayıcı içinde sayfayı yenileyin ve web uygulaması görünmelidir.

    ![Bottle, Flask ve Django uygulamaları App Service'te yayımlama sonuçları](media/azure-publish-results.png)

## <a name="publish-to-app-service---visual-studio-2015"></a>App Service - Visual Studio 2015 yayımlama

> [!Note]
> Bu işlemin kısa bir video bulunabilir [Visual Studio Python Öğreticisi: bir Web sitesi oluşturmanın](https://www.youtube.com/watch?v=FJx5mutt1uk&list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff&index=6) (youtube.com, 3m10s).

1. İçinde **Çözüm Gezgini**, projeye sağ tıklayıp seçin **Yayımla**.

1. İçinde **Yayımla** iletişim kutusunda **Microsoft Azure App Service**:

  ![Adım 1 Azure yayımlama](media/tutorials-common-publish-1.png)

1. Bir hedef seçin:

    - Azure aboneliğiniz varsa, seçin **Microsoft Azure App Service** yayımlama hedefi olarak sonra aşağıdaki iletişim kutusunda, var olan bir App Service seçin veya seçin **yeni** yeni bir tane de oluşturabilirsiniz.
    - Try.azurewebsites.net geçici bir siteden kullanıyorsanız seçin **alma** tarayabileceği ardından yayımlama hedefi olarak *.publishsettings* dosyasını indirdiğiniz site ve select **Tamam** .

1. App Service ayrıntıları görünür **Yayımla** iletişim kutusunun **bağlantı** sekmesini tıklatın.

  ![Adım 2 Azure yayımlama](media/tutorials-common-publish-2.png)

1. Seçin **sonraki** ek ayarlarını gözden geçirmek için gerektiği şekilde. Eğer [Python kodunuzu azure'da uzaktan hata ayıklama](debugging-remote-python-code-on-azure.md), ayarlamalısınız **yapılandırma** için **hata ayıklama**

1. Seçin **yayımlama**. Uygulamanızın Azure'a dağıtıldığında, o sitede varsayılan tarayıcınızı açar.

Bu işlemin bir parçası, Visual Studio ayrıca aşağıdakileri yapar:

- Oluşturma bir *web.config* dosya sunucusunda uygun uygulamanın işaretçileri içeren `wsgi_app` işlev ve Python 3.4 App Service'in için varsayılan yorumlayıcı.
- Projenin dosyaların işlenmesini Kapat *statik* klasörü (Bu kurallarının mevcut olduğunu *web.config*).
- Sanal ortam sunucuya yayımlayın.
- Ekleme bir *web.debug.config* dosya ve uzaktan hata ayıklamayı etkinleştirmek için Araçlar hata ayıklama ptvsd.

Daha önce belirtildiği gibi bu otomatik adımlar yayımlama işlemini basitleştirmek ancak Python ortamını denetlemek daha zor hale. Örneğin, *web.config* dosya yalnızca sunucuda oluşturulur, ancak projeye eklenmedi. Yayımlama işlemi ayrıca, tüm sanal ortam Geliştirme bilgisayarınızdan kopyalamak yerine çünkü sunucu yapılandırmasına bağlı olan daha uzun sürer.

Kendi korumak sonunda isteyebileceğiniz *web.config* kullanın ve dosya *requirements.txt* sunucuda paketleri doğrudan korumak için. Kullanarak *requirements.txt*, özellikle, geliştirme ve sunucu ortamınızı her zaman aynı garanti eder.

## <a name="remote-debugging-on-azure-app-service"></a>Azure App Service'te uzaktan hata ayıklama

Yayımladığınızda bir **hata ayıklama** Visual Studio 2015 yapılandırmasından işlemi otomatik olarak oluşturur bir *web.debug.config* ekler ve dosya bir *ptvsd* içeren klasör gerekli hata ayıklama araçları.

Visual Studio 2017 ile bunun yerine bu bileşenler doğrudan projeye ekleyin. Projeye sağ **Çözüm Gezgini**seçin **Ekle** > **yeni öğe**seçip **Azure uzaktan hata ayıklama web.config** şablonu. Bir hata ayıklama *web.debug.config* dosya ve *ptvsd* aracının klasörüne projenizde görünür.

Bu dosyalar sunucuya dağıtılan sonra (otomatik olarak Visual Studio 2015; sonraki Visual Studio 2017 ile yayımladığınızda), ilgili yönergeleri izleyebilirsiniz [Azure uzaktan hata ayıklama](debugging-remote-python-code-on-azure.md).
