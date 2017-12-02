---
title: "Python için Azure bulut hizmeti proje şablonu | Microsoft Docs"
ms.custom: 
ms.date: 07/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "11"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: b8ddcb234d43407c256145245b4cbdac308ed9ea
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2017
---
# <a name="azure-cloud-service-projects-for-python"></a>Python için Azure bulut hizmeti projeleri

Visual Studio şablonları yardımcı olması için Python kullanarak Azure Cloud Services oluşturmaya başlamak sağlar.

A [bulut hizmeti](http://go.microsoft.com/fwlink/?LinkId=306052) herhangi bir sayıda oluşur *çalışan rolleri* ve *web rolleri*, her biri kavramsal olarak ayrı bir görev gerçekleştiren ancak için ayrı olarak çoğaltılabilir arasında ölçeklendirme için görsel makineler gerektiği gibi. Web rolleri için ön uç web uygulamalarını barındırma sağlar. Bu tür bir uygulama yazmak için Python ilgilenen olduğu WSGI destekleyen herhangi bir web çerçevesidir kullanılabilir (tarafından desteklenen gibi [Web Proje şablonu](template-web.md)). Çalışan rollerini doğrudan kullanıcılarınız ile etkileşim değil uzun süre çalışan işlemler için tasarlanmıştır. Genellikle yaptıkları kullanımı [veri](http://go.microsoft.com/fwlink/?LinkId=401571) ve [uygulama hizmeti](http://go.microsoft.com/fwlink/?LinkId=401572) ile yüklenebilir kitaplıkları `pip install` &nbsp; [ `azure` ](http://pypi.org/project/azure).

Bu konu, proje şablonu ve diğer Visual Studio (önceki sürümlerinde benzer, ancak bazı farklılıklar) 2017 desteği hakkında ayrıntılar içerir. Python'dan Azure ile çalışma hakkında daha fazla bilgi için ziyaret [Azure Python Geliştirici Merkezi](http://go.microsoft.com/fwlink/?linkid=254360).

## <a name="create-a-project"></a>Proje oluşturma

1. Yükleme [Visual Studio için Azure .NET SDK'sı](https://www.visualstudio.com/vs/azure-tools/), bulut hizmet şablonu kullanmak için gereklidir.
1. Visual Studio'da seçin **Dosya > Yeni > Proje...** , "Azure Python" için arama yapın ve seçin **Azure bulut hizmeti** listeden:

    ![Python için Azure bulut proje şablonu](media/template-azure-cloud-project.png)

1. Eklenecek bir veya daha fazla rol seçin. Bulut projeleri en uygun dilde uygulamanızın her parçası kolayca yazabilirsiniz şekilde farklı dillerde yazılmış rollerini birleştirmeniz. Bu iletişim kutusunu tamamladıktan sonra projeye yeni rolleri eklemek için sağ tıklatın **rolleri** Çözüm Gezgini'nde ve altındaki öğelerin birini seçin **Ekle**.

    ![Azure bulut proje şablonu rol ekleme](media/template-azure-cloud-service-project-wizard.png)

1. Tek tek rolü projeleri oluşturuldukça bunlardan birini kullanan bir rolü seçtiyseniz, Django, Bottle veya Flask çerçeveleri gibi ek Python paketlerini yüklemek için istenebilir.

1. Projeniz için yeni bir rol ekledikten sonra yapılandırma yönergeleri görünür. Yapılandırma değişiklikleri genellikle gereksizdir, ancak gelecekte projelerinizi özelleştirme için yararlı olabilir. Aynı anda birden çok rol eklerken, yalnızca son rolü yönergelerini açık kalmasını unutmayın. Diğer roller için kendi ilgili yönergeler ve sorun giderme ipuçları ancak bulabilirsiniz `readme.mht` rolün kök veya bulunan dosyaları, `bin` klasörü.

1. Bir projenin `bin` klasörü, Python, her yükleme dahil olmak üzere uzaktan sanal makineyi yapılandırmak için kullanılan bir veya iki PowerShell komut dosyalarını da içerir [requirements.txt](#dependencies) dosya projenizde ve IIS ayarı gerekli. En yaygın seçenekler diğer yollarla yönetilebilir olsa dağıtımınız için bu dosyaları istediğiniz gibi düzenleyin (bakın [rol dağıtımı yapılandırma](#configuring-role-deployment) aşağıda). Dosyaları mevcut değilse eski yapılandırma komut dosyası yerine kullanılmak üzere bu dosyaları kaldırma öneririz değil.

    ![Çalışan rolü destek dosyaları](media/template-azure-cloud-service-worker-role-support-files.png)

    Bu yapılandırma komut dosyaları için yeni bir proje eklemek için projeye sağ tıklayın, seçin **Ekle > Yeni öğe...** seçin **Web rolü destek dosyalarını** veya **çalışan rolü destek dosyalarını**.
   

## <a name="configuring-role-deployment"></a>Rol dağıtımı yapılandırma

Bir rolü projesinin PowerShell komut `bin` klasör bu rol dağıtımını denetlemek ve yapılandırmasını özelleştirmek için düzenlenebilir:

- `ConfigureCloudService.ps1`Web ve çalışan rolleri için genellikle yüklemek ve bağımlılıkları yapılandırmak ve Python sürümü ayarlamak için kullanılır.
- `LaunchWorker.ps1`yalnızca çalışan rolleri için kullanılır ve başlangıç davranışını değiştirmek için komut satırı bağımsız değişkenleri ekleyip ortam değişkenleri eklemek için kullanılır.

Her iki dosya özelleştirme için yönergeleri içerir. Ana bulut hizmet projesinin için başka bir görev ekleyerek de kendi Python sürümü yükleyebilirsiniz `ServiceDefinition.csdef` dosyası ayarı `PYTHON` kendi yüklü için değişken `python.exe` (veya eşdeğer) yolu. Zaman `PYTHON` olan ayarlayın, Python Nuget'ten yüklü değil.

Ek yapılandırma gibi gerçekleştirilebilir:

1. Kullanarak paketleri yüklemek `pip` güncelleştirerek `requirements.txt` projenizin kök dizininde dosya. `ConfigureCloudService.ps1` Komut dosyası dağıtım bu dosyayı yükler.
1. Ortam değişkenlerini ayarlama değiştirerek, `web.config` dosya (web rolleri) veya `Runtime` bölümünü, `ServiceDefinition.csdef` dosya (çalışan rolleri).
1. Komut dosyası ve çalışan rolü için komut satırında değiştirerek kullanılacak değişkenleri belirtin `Runtime/EntryPoint` bölümü, `ServiceDefinitions.csdef` dosya.
1. Ana işleyicisi komut dosyası web rolü için `web.config` dosya.

## <a name="testing-role-deployment"></a>Rol dağıtımı test etme

Rollerinizi yazılırken, bulut projenizi bulut hizmeti öykünücüsü kullanarak yerel olarak test edebilirsiniz. Öykünücü Azure SDK Araçları ile birlikte gelir ve bulut hizmetiniz için Azure yayımlandığında kullanılan ortamı, sınırlı bir sürümüdür.

Öykünücü başlatmak için önce bulut projenize sağ tıklayıp seçerek çözümünüzdeki başlangıç projesi olduğundan emin olun **başlangıç projesi olarak ayarla**. Ardından **hata ayıklama > hata ayıklamayı Başlat** (F5) veya **hata ayıklama > hata ayıklama olmadan Başlat** (Ctrl + F5).

Öykünücü sınırlamaları nedeniyle, Python kodunuzu hata ayıklama mümkün olmadığını unutmayın. Bu nedenle önerilir rolleri bağımsız olarak çalıştırarak hata ayıklama ve yayımlanmadan önce test tümleştirme öykünücü kullanın.


## <a name="deploying-a-role"></a>Bir rolü dağıtma

Açmak için **Yayımla** rolü Çözüm Gezgini'nde proje ve seçin Sihirbazı, select **Yapı > Yayımla** ana menüden veya projesine sağ tıklatın ve **Yayımla**.

Yayımlama işlemi iki aşamaları içerir. İlk olarak, Visual Studio bulut hizmetiniz için tüm rolleri içeren tek bir paket oluşturur. Bu, her rol için bir veya daha fazla sanal makine başlatır ve kaynak dağıtma Azure'a dağıtılan bir pakettir.

Her sanal makineyi etkinleştirir olarak yürütülmeden `ConfigureCloudService.ps1` komut dosyası ve bağımlılıkları yükleyin. Varsayılan olarak bu komut dosyası Python yeni bir sürümünü yükler [NuGet](https://www.nuget.org/packages?q=Tags%3A%22python%22+Authors%3A%22Python+Software+Foundation%22) ve belirtilen herhangi bir paket bir `requirements.txt` dosyası. 

Son olarak, çalışan rolleri yürütme `LaunchWorker.ps1`, başladığı Python kodunuzu çalıştıran; rolleri Initialize IIS web ve web istekleri işleme başlamak.


## <a name="dependencies"></a>Bağımlılıklar

Bulut hizmeti için `ConfigureCloudService.ps1` komut dosyası kullanan `pip` Python bağımlılıkları kümesini yüklemek için. Bağımlılıklar adlı bir dosyaya belirtilmelidir `requirements.txt` (değiştirerek özelleştirilebilir `ConfigureCloudService.ps1`). Dosya ile yürütülür `pip install -r requirements.txt` başlatma bir parçası olarak.

C uzantılı tüm kitaplıkları önceden derlenmiş ikili dosyaları sağlamalısınız bulut hizmeti örnekleri C Derleyicileri içermez unutmayın.

PIP ve bağımlılıklarını yanı sıra paketler `requirements.txt`, otomatik olarak yüklenir ve ücrete tabi bant genişliği kullanımı sayılır. Bkz: [gerekli paketleri yönetme](python-environments.md#managing-required-packages) yönetme ile ilgili ayrıntılar için `requirements.txt` dosyaları.

## <a name="troubleshooting"></a>Sorun giderme

Web veya çalışan rolü düzgün bir şekilde dağıtıldıktan sonra davranıyor değil, aşağıdakileri denetleyin:

- Python projenizin (en az) sahip bir bin\ klasör içerir:
    - `ConfigureCloudService.ps1`
    - `LaunchWorker.ps1`(çalışan rolleri için)
    - `ps.cmd`

- Python projenizi içeren bir `requirements.txt` tüm bağımlılıkları (veya alternatif olarak, tekerlek dosyalarını koleksiyonu) listeleme dosya.
- Uzak Masaüstü'nü, bulut hizmeti etkinleştirmek ve günlük dosyalarını inceleyin.
- Günlükleri `ConfigureCloudService.ps1` ve `LaunchWorker.ps1` depolanmış `C:\Resources\Directory\%RoleId%.DiagnosticStore\LogFiles` uzak makinede klasör.
- Web rolleri yazma ek günlükleri yapılandırılan bir yola `web.config`, yani yolunda `WSGI_LOG` appSetting. Çoğu normal IIS veya Fastcgı günlüğünü de çalışır.
- Şu anda `LaunchWorker.ps1.log` çıkış veya Python çalışan rolü tarafından görüntülenen hataları görüntülemek için tek yolu bir dosyadır.