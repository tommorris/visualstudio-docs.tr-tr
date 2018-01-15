---
title: "Azure uygulama Hizmeti'nde Python yönetme | Microsoft Docs"
ms.custom: 
ms.date: 09/13/2017
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
ms.openlocfilehash: 50b306a3332678a4ab648e0e79730b0ef3ac996e
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2018
---
# <a name="managing-python-on-azure-app-service"></a>Azure uygulama Hizmeti'nde Python yönetme

[Azure uygulama hizmeti](https://azure.microsoft.com/services/app-service/) siteleri REST API'ları, kendi istemcileri veya olayı tarafından tetiklenen işlem tarafından kullanılan bir tarayıcı aracılığıyla erişilen oldukları olup, bir hizmet olarak platform sunumu web uygulamaları için. Uygulama hizmeti uygulamalarını uygulamak için Python kullanarak tam olarak destekler.

Özelleştirilebilir Python desteği Azure App Service'te bir uygulama hizmeti kümesi olarak sağlanan *site uzantıları* her Python çalışma zamanı belirli bir sürümünü içerir. Bu konu başlığı altında açıklandığı gibi sonra bu ortama doğrudan istenen herhangi bir paket yükleyebilirsiniz. Uygulama hizmeti ortamında özelleştirerek, paketler, web uygulaması projelerinde korumak veya uygulama koduyla yüklemek gerekmez.

> [!Tip]
> Uygulama hizmeti varsayılan olarak Python 2.7 ve Python 3.4 kök klasörlerdeki sunucuda yüklü olsa da, özelleştirebilir veya bu ortamlarda paketleri yüklemek veya kendi varlığına bağımlı olmalıdır. Bunun yerine, bu konu başlığı altında açıklandığı gibi denetleyen bir site uzantısı yararlanmalıdır.

> [!Important]
> Burada açıklanan değiştirilebilir ve özellikle geliştirme işlemlerdir. Değişiklikleri duyurdu üzerinde [Python mühendislik Microsoft blogu](https://blogs.msdn.microsoft.com/pythonengineering/).

## <a name="choosing-a-python-version-through-the-azure-portal"></a>Azure portalı üzerinden Python sürümünü seçme

1. Web uygulamanız için bir uygulama hizmeti Azure portalda oluşturun.
1. Uygulama hizmetin sayfasında kaydırın **geliştirme araçları** bölümünde, select **uzantıları**seçeneğini belirleyip **+ Ekle**.
1. İstediğiniz Python sürümünü içeren uzantısına listesinde ilerleyin:

    ![Azure portal gösteren Python uzantıları](media/python-on-azure-extensions.png)

    > [!Tip]
    > Python daha eski bir sürümü gerekir ve site uzantılarında listelendiği görmüyorsanız, yine, Azure Resource Manager aracılığıyla sonraki bölümde açıklandığı gibi yükleyebilirsiniz.

1. Uzantıyı seçin, yasal koşulları kabul edin ve sonra seçin **Tamam**.
1. Yükleme tamamlandığında, bir bildirim portalda görüntülenir.

## <a name="choosing-a-python-version-through-the-azure-resource-manager"></a>Python sürümü aracılığıyla Azure Kaynak Yöneticisi'ni seçme

Bir uygulama hizmeti bir Azure Resource Manager şablonu ile dağıtıyorsanız, site uzantısı bir kaynak olarak ekleyin. Uzantı türü olan iç içe geçmiş bir kaynak olarak görünür `siteextensions` ve adından [siteextensions.net](https://www.siteextensions.net/packages?q=Tags%3A%22python%22).

Örneğin, bir başvuru ekledikten sonra `python361x64` (şablonunuzu aşağıdaki gibi görünecektir Python 3.6.1 x 64), (atlanmış bazı özellikleri):

```json
"resources": [
  {
    "apiVersion": "2015-08-01",
    "name": "[parameters('siteName')]",
    "type": "Microsoft.Web/sites",

    // ...

    "resources": [
      {
        "apiVersion": "2015-08-01",
        "name": "python361x64",
        "type": "siteextensions",
        "properties": { },
        "dependsOn": [
          "[resourceId('Microsoft.Web/sites', parameters('siteName'))]"
        ]
      },
      // ...
    ]
  }
```

## <a name="setting-webconfig-to-point-to-the-python-interpreter"></a>Python yorumlayıcı işaret edecek şekilde web.config ayarlama

Site uzantısı (aracılığıyla, portal veya bir Azure Resource Manager şablonu) yükledikten sonra sonraki uygulamanızın noktası `web.config` Python yorumlayıcı dosya. `web.config` Dosya nasıl, Fastcgı veya HttpPlatform Python isteklerini yöneteceğini hakkında uygulama hizmeti üzerinde çalışan IIS (7 +) web sunucusuna bildirir.

Begin site uzantının tam yolunu bularak `python.exe`, ardından oluşturmak ve uygun değiştirme `web.config` dosya.

### <a name="finding-the-path-to-pythonexe"></a>Python.exe'yi yoluna bulma

Python site uzantısı altında sunucusunda yüklü olduğundan `d:\home` mimarisi ve Python sürümü için uygun bir klasörde (söz konusu olduğunda birkaç eski sürümleri hariç). Örneğin, Python 3.6.1 x64 yüklü `d:\home\python361x64`. Python yorumlayıcı tam yolunu ise `d:\home\python361x64\python.exe`.

Uygulama Hizmetiniz belirli yolu görmek için seçin **uzantıları** uygulama hizmeti sayfasında listede sonra uzantıyı seçin.

![Azure uygulama hizmeti uzantı listesinde](media/python-on-azure-extension-list.png)

Bu eylem yolunu içeren bir uzantının açıklama sayfası açılır:

![Azure uygulama hizmeti uzantı ayrıntıları](media/python-on-azure-extension-detail.png)

Yol uzantısı görme konusunda sorun yaşıyorsanız, konsolunu kullanarak el ile bulabilirsiniz:

1. Uygulama hizmeti sayfanızda seçin **geliştirme araçları > konsol**.
1. Aşağıdaki komutu girin `ls ../home` veya `dir ..\home` en üst düzey uzantıları klasörleri gibi görmek için `Python361x64`.
1. Gibi bir komut girin `ls ../home/python361x64` veya `dir ..\home\python361x64` onu içerdiğini doğrulamak için `python.exe` ve diğer yorumlayıcı dosyaları.

### <a name="configuring-the-fastcgi-handler"></a>Fastcgı işleyici yapılandırma

Fastcgı isteği düzeyinde çalışan bir arabirimdir. IIS gelen bağlantıları alır ve her birinde çalışan bir WSGI uygulama isteği iletir veya daha fazla kalıcı Python işler. [Wfastcgı paket](https://pypi.io/project/wfastcgi) önceden yüklenmiş ve her bir Python site uzantı ile kolayca kodda ekleyerek etkinleştirebileceğiniz şekilde yapılandırılmış `web.config` ister Bottle framework temel alınarak bir web uygulaması için ne aşağıda gösterilmiştir. Unutmayın tam yolları `python.exe` ve `wfastcgi.py` yerleştirilir `PythonHandler` anahtarı:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <appSettings>
    <add key="PYTHONPATH" value="D:\home\site\wwwroot"/>
    <!-- The handler here is specific to Bottle; other frameworks vary. -->
    <add key="WSGI_HANDLER" value="app.wsgi_app()"/>
    <add key="WSGI_LOG" value="D:\home\LogFiles\wfastcgi.log"/>
  </appSettings>
  <system.webServer>
    <handlers>
      <add name="PythonHandler" path="*" verb="*" modules="FastCgiModule"
           scriptProcessor="D:\home\Python361x64\python.exe|D:\home\Python361x64\wfastcgi.py"
           resourceType="Unspecified" requireAccess="Script"/>
    </handlers>
  </system.webServer>
</configuration>
```

`<appSettings>` Tanımlanmış buraya kullanılabilir uygulamanıza ortam değişkenleri olarak:

- Değeri `PYTHONPATH` genişletilmiş serbestçe ancak, uygulamanızın kök içermelidir.
- `WSGI_HANDLER`bir WSGI uygulaması alınabilir, uygulamanızdan işaret etmelidir.
- `WSGI_LOG`İsteğe bağlı ancak önerilen uygulamanızı hata ayıklama için değildir. 

Bkz: [Azure'a yayımlama](publishing-to-azure.md) hakkında daha fazla ayrıntı için `web.config` içeriği Bottle, Flask ve Django web uygulamaları.

### <a name="configuring-the-httpplatform-handler"></a>HttpPlatform işleyici yapılandırma

HttpPlatform modülü yuva bağlantısının doğrudan tek başına Python işlem geçirir. Bu geçiş gibi çalışır, ancak bir yerel web sunucusu çalıştıran bir başlangıç betiği gerektiren herhangi bir web sunucusuna çalıştırmanıza olanak sağlar. Komut dosyasında belirttiğiniz `<httpPlatform>` öğesinin `web.config`, burada `processPath` site uzantının Python yorumlayıcısı özniteliği ve `arguments` komut dosyanızı ve sağlamak istediğinizde herhangi bir bağımsız değişken özniteliği:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.webServer>
    <handlers>
      <add name="PythonHandler" path="*" verb="*" modules="httpPlatformHandler" resourceType="Unspecified"/>
    </handlers>
    <httpPlatform processPath="D:\home\Python361x64\python.exe"
                  arguments="D:\home\site\wwwroot\runserver.py --port %HTTP_PLATFORM_PORT%"
                  stdoutLogEnabled="true"
                  stdoutLogFile="D:\home\LogFiles\python.log"
                  startupTimeLimit="60"
                  processesPerApplication="16">
      <environmentVariables>
        <environmentVariable name="SERVER_PORT" value="%HTTP_PLATFORM_PORT%" />
      </environmentVariables>
    </httpPlatform>
  </system.webServer>
</configuration>
```

`HTTP_PLATFORM_PORT` Ortam değişkeni burada gösterilen yerel sunucunuz, localhost bağlantılarından dinleyecek bağlantı noktasını içerir. Bu örnek ayrıca, bu durumda isterseniz başka bir ortam değişkeni oluşturulacağını gösterir `SERVER_PORT`.

## <a name="installing-packages"></a>Paket yükleme

Bir site uzantısı aracılığıyla yüklü Python yorumlayıcı Python ortamı yalnızca bir parçasıdır. Muhtemelen farklı paketler, ortamda yüklemeniz gerekir.

Doğrudan sunucu ortamında paketleri yüklemek için aşağıdaki yöntemlerden birini kullanın:

| Yöntemler | Kullanım |
| --- | --- |
| [Azure App Service Kudu konsol](#azure-app-service-kudu-console) | Paketleri etkileşimli olarak yükler. Paket saf Python olmalıdır veya tekerlek yayımlamanız gerekir. |
| [Kudu REST API'si](#kudu-rest-api) | Paket yükleme otomatik hale getirmek için kullanılabilir.  Paket saf Python olmalıdır veya tekerlek yayımlamanız gerekir. |
| Uygulamayla paketini | Paketleri doğrudan projenize yükleyin ve ardından bunları App Service'e dağıtma uygulamanızı parçası değilmiş gibi. Bağlı olarak kaç bağımlılıkları vardır ve ne sıklıkta bunları güncelleştirin, bu yöntem olmaya çalışma dağıtım almak için en kolay yolu olabilir. Dikkat edin kitaplıkları Python sürümü sunucusunda aynı olmalıdır, aksi takdirde dağıtımdan sonra belirsiz hataları görürsünüz. Python site uzantılarını tam olarak üzerinde python.org yayımlanan bu sürümler ile aynı olan App Service'te sürümleri, uyumlu bir sürüm yerel geliştirme için kolayca edinebileceği olduğundan, bununla. |
| Sanal ortamlar | Desteklenmez. Bunun yerine, paketleme kullanın ve ayarlayın `PYTHONPATH` paketleri konumuna işaret etmek için ortam değişkeni. |

### <a name="azure-app-service-kudu-console"></a>Azure App Service Kudu konsol

[Kudu konsol](https://github.com/projectkudu/kudu/wiki/Kudu-console) uygulama hizmeti sunucusu ve dosya sistemi doğrudan, yükseltilmiş komut satırı erişimi sağlar. Bu, hem bir değerli hata ayıklama aracıdır ve paketlerin yüklenmesi gibi CLI işlemleri için sağlar.

1. Açık Kudu, uygulama hizmeti sayfasında Azure Portalı'nı seçerek **geliştirme araçları > Gelişmiş Araçlar**, ardından seçerek **Git**. Bu eylem, temel uygulama hizmeti URL'sini dışında ile aynı URL gider `.scm` eklenir. Örneğin, temel URL'niz ise `https://vspython-test.azurewebsites.net/` Kudu açıktır sonra `https://vspython-test.scm.azurewebsites.net/` (hangi yer işareti oluşturabileceğiniz):

    ![Azure App Service için Kudu Konsolu](media/python-on-azure-console01.png)

1. Seçin **hata ayıklama konsoluna > CMD** Python yüklemenizi gidin ve ne kitaplıkları zaten olup olmadığını tıklayarak konsolu açın.

1. Tek bir paket yüklemek için:

    a. Paketi gibi yüklemek istediğiniz klasöre Python yüklemesinin gidin `d:\home\python361x64`.

    b. Kullanım `python.exe -m pip install <package_name>` bir paketi yüklemek için.

    ![Azure App Service için bottle Kudu Konsolu aracılığıyla yükleme örneği](media/python-on-azure-console02.png)

1. Dağıttıktan sonra bir `requirements.txt` sunucuya uygulamanız için zaten bu gereksinimleri aşağıdaki gibi yükleyin:

    a. Paketi gibi yüklemek istediğiniz klasöre Python yüklemesinin gidin `d:\home\python361x64`.

    b. Komutu çalıştırın `python.exe -m pip install --upgrade -r d:\home\site\wwwroot\requirements.txt`.

    Kullanarak `requirements.txt` yeniden oluşturmak kolay olduğundan, tam paketinizi ayarlamak, her ikisi de, yerel olarak hem de sunucu tavsiye edilir. Herhangi bir değişiklik dağıttıktan sonra konsol ziyaret hatırlamak `requirements.txt` ve komutu yeniden çalıştırın.

> [!Note]
> Olmadığından C Derleyici uygulama hizmeti, yerel uzantısı modüllerle herhangi bir paket için tekerlek yüklemeniz gerekir. Birçok popüler paketleri kendi Tekerlek sağlar. Verme paketlerini kullanma `pip wheel <package_name>` yerel geliştirme bilgisayarınıza ve Tekerlek sitenize karşıya yükleme. Bir örnek için bkz: [gerekli paketleri yönetme](python-environments.md#managing-required-packages-requirementstxt).

### <a name="kudu-rest-api"></a>Kudu REST API'si

Azure portalı üzerinden Kudu konsol kullanmak yerine, komutları uzaktan Kudu REST API aracılığıyla komutu göndererek çalıştırabilirsiniz `https://yoursite.scm.azurewebsites.net/api/command`. Örneğin, yüklemek için `bottle` paket, aşağıdaki JSON sonrası `/api/command`:

```json
{
    "command": 'python.exe -m pip install bottle',
    "dir": '\home\python361x64'
}
```

Komutlar ve kimlik doğrulama hakkında daha fazla bilgi için bkz: [Kudu belgelerine](https://github.com/projectkudu/kudu/wiki/REST-API).

Kullanarak kimlik bilgileri de görebilirsiniz `az webapp deployment list-publishing-profiles` Azure CLI aracılığıyla komutu (bkz [az webapp dağıtım](/cli/azure/webapp/deployment?view=azure-cli-latest#az_webapp_deployment_list_publishing_profiles)). Kudu komutları nakil için bir yardımcı kitaplık kullanılabilir [GitHub](https://github.com/lmazuel/azure-webapp-publish/blob/master/azure_webapp_publish/kudu.py#L42).
