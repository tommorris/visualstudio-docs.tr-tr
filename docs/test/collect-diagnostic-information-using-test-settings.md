---
title: Visual Studio'da Test ayarlarını kullanarak tanılama bilgileri Topla
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, configuring run settings
ms.assetid: 0c86918b-cd63-4468-8f49-6d547a1276dc
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 50a2462fc6b32d1f1375314a9799055acfab909b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31974890"
---
# <a name="collect-diagnostic-information-using-test-settings"></a>Test ayarlarını kullanarak tanılama bilgileri Topla

Kullanabileceğiniz *Test ayarlarını* testlerinizi çalıştırdığınızda, ek veriler toplamak için Visual Studio'da. Örneğin, bir video testinizi çalıştırırken kaydı yapmak isteyebilirsiniz. Tanılama veri bağdaştırıcıları vardır:

-   Metin biçimindeki her UI eylem adımı Topla

-   Tekrar oynatma her UI eylem kaydetme

-   Sistem bilgilerini toplama

-   Olay günlüğü verilerini topla

-   Hatalar üretme olmayan yalıtmaya yardımcı olması için IntelliTrace verilerini toplama

Tanılama veri bağdaştırıcıları test makinesi davranışını değiştirmek için de kullanılabilir. Örneğin, bir test ayarında ile Visual Studio, ekibinizin uygulamanın performansını değerlendirmek için ağ topolojisi performans sorunlarını çeşitli taklit edebilir.

## <a name="use-test-settings-with-visual-studio"></a>Visual Studio ile test ayarları kullan

Biriminiz çalıştırmak için kodlanmış UI, web performans ya da Visual Studio kullanarak yük testleri, Ekle, yapılandırabilir ve testlerinizi çalıştırdığınızda kullanmak için test ayarları seçin. Testleri çalıştırma, veri toplamak veya test makinesini uzaktan etkilemek için test ayarlarınızda kullanmak üzere bir test denetleyicisi belirtmeniz gerekir. Test denetleyicisi test ayarlarınızda her rol için kullanılan aracılara sahip olacaktır.

## <a name="diagnostic-data-adapter-details"></a>Tanılama veri bağdaştırıcısı ayrıntıları

Aşağıdaki tabloda tanılama veri bağdaştırıcıları yerel veya uzak makine rolleri ile kullanılmak üzere yapılandırılabilir çeşitli şekillerde genel bir bakış sağlar.

|Test ayarlarında kullanılan tanılama veri bağdaştırıcısı|Yerel makinede el ile testler|Otomatikleştirilmiş test|El ile testler: rolleri ve bir ortam kümesi kullanarak verileri toplama|Notlar|
|----------------------------------------------------------|-----------------------------------|---------------------|------------------------------------------------------------------------------|-----------|
|**IntelliTrace ve Test etkisi için ASP.NET İstemci Proxy:** bu proxy, IntelliTrace ve Test etkisi tanılama veri bağdaştırıcıları için bir Web sunucusu istemciden gelen http çağrıları hakkında bilgi toplamanıza olanak tanır.|Evet|Evet|Evet|-Bu IntelliTrace veya Test etkisi tanılama veri bağdaştırıcıları için bir istemci rolü yalnızca seçili olduğunda kullanın.|
|**ASP.NET Profil Oluşturucu:** ASP.NET Web uygulamaları üzerinde performans verilerini toplayan ASP.NET profil oluşturma, içeren bir test ayarı oluşturabilirsiniz.|Hayır|Evet (notlara bakın)|Hayır|-Visual Studio'dan yük testlerini çalıştırdığınızda bu tanılama veri bağdaştırıcısı desteklenir.|
|**Kod kapsamı:** kodunuzu ne kadarının testleri tarafından kapsanan araştırmak için kullanılan kod kapsam bilgisini içeren bir test ayarı oluşturabilirsiniz.|Hayır|Evet (notlara bakın)|Hayır|Yalnızca Visual Studio ya da mstest.exe bir otomatik test çalıştırdığınızda ve test çalışmaları yalnızca makineden-kod kapsamı kullanabilirsiniz. Uzaktan Toplama desteklenmiyor.<br />-IntelliTrace bilgilerini toplamak üzere yapılandırılmış test ayarı de varsa kod kapsamı verilerini toplama çalışmaz. **Not:** Bu tanılama veri bağdaştırıcısı yalnızca Visual Studio test ayarları için geçerlidir. Microsoft Test Yöneticisi'nde test ayarları için kullanılmaz. Ayrıca, bu Visual Studio 2010 test projeleri ile uyumluluk için bağdaştırıcısıdır. **Not:** otomatikleştirilmiş testleri Microsoft Test Yöneticisi'nden veya uzak bir Test aracısı Visual Studio'dan eski mstest'i Çalıştırıcısı kullanarak çalıştırıldığında kod kapsamı uyumluluk için geçerlidir.|
|**Olay günlüğü:** test sonuçlarında bulunan olay günlüğü toplama, dahil etmek için test ayarı yapılandırabilirsiniz.|Evet|Evet|Evet||
|**IntelliTrace:** için tanılama veri bağdaştırıcısı yapılandırabilirsiniz *IntelliTrace* yeniden oluşturması zor olan hatalarda gidermeye yardımcı olmak için özel Tanılama izleme bilgilerini toplamak için. Bu, bu bilgileri içeren bir IntelliTrace dosyası oluşturur. Bir IntelliTrace dosyası .iTrace uzantısına sahiptir. Bir test başarısız olduğunda, bir hata oluşturabilirsiniz. Test sonuçları birlikte kaydedilen IntelliTrace dosyası otomatik olarak bu hataya bağlanır. IntelliTrace dosyasında toplanan verileri yeniden oluşturun ve kodda bir hata tanımak için gerekli olan zamanı azaltarak hata ayıklama verimliliğini artırır. Bu IntelliTrace dosyasından dosya yerel oturumun başka bir bilgisayarda benzetimi yapılabilir. Bu hatanın oluşturulabilme riskini azaltır.|Evet|Evet|Evet|-IntelliTrace verilerini toplama etkinleştirirseniz, kod kapsamı veri koleksiyonu çalışmaz.<br />-Web istemci rolü için IntelliTrace kullanıyorsanız, IntelliTrace ve Test etkisi tanılama veri bağdaştırıcısı için ASP.NET İstemci Proxy seçmeniz gerekir.<br />-IIS yalnızca şu sürümleri desteklenir: IIS 7.0, IIS 7.5 ve IIS 8. 0.|
|**Ağ öykünmesi:** test ayarı kullanarak, test yapay bir ağ yükü yerleştirmek istediğinizi belirtebilirsiniz. Ağ öykünmesi çevirmeli gibi belirli bir ağ bağlantısı hızı öykünen tarafından iletişimi makine etkiler. **Not:**|Hayır|Evet (notlara bakın)|Hayır|Ağ öykünmesi tanılama veri bağdaştırıcısı için bir istemci veya sunucu rolü kullanabilirsiniz. Birbirleriyle iletişim hem bu rolleri bağdaştırıcısı kullanmanız gerekmez. **Not:** Bu tanılama veri bağdaştırıcısı yalnızca Visual Studio test ayarları için geçerlidir. Microsoft Test Yöneticisi'nde test ayarları için kullanılmaz. **Not:** ağ öykünmesi, ağ bağlantı hızını artırmak için kullanılamaz. **Uyarı:** ağ öykünmesi tanılama veri bağdaştırıcısı test ayarlarında içerir ve yerel makinenizde kullanmayı düşündüğünüz olduysa, ayrıca ağ öykünmesi sürücüsünü makinenizin ağ bağdaştırıcılarından birine bağlamanız gerekir. Ağ öykünmesi sürücüsü ağ öykünmesi tanılama veri bağdaştırıcısı çalışması için gereklidir. Ağ öykünmesi sürücüsü yüklenir ve bağdaştırıcınızı iki yolla bağlı: <ul><li>**Microsoft Visual Studio Test Aracısı ile yüklenmiş ağ öykünme sürücüsü:** Microsoft Visual Studio Test aracısı, hem uzak makineleri hem de yerel makinenize kullanılabilir. Visual Studio Test aracısı yüklediğinizde, yükleme işlemi ağ öykünmesi sürücüsü ağ kartınıza bağlayan bir yapılandırma adımı içerir. Daha fazla bilgi için bkz: [yüklemek ve test aracılarını yapılandırma](../test/lab-management/install-configure-test-agents.md).</li><li>**Microsoft Visual Studio Test Professional ile yüklenmiş ağ öykünme sürücüsü:** ağ öykünmesini ilk kez kullandığınızda, bir ağ kartı ağ öykünmesi sürücüsü bağlamanız istenir.</li></ul> Ayrıca ağ öykünmesi sürücüsü komut satırından yerel makinenizde aşağıdaki komutu kullanarak Visual Studio test aracısı yüklemeden yükleyebilirsiniz: **da VSTestConfig NETWORKEMULATION/install**  **Uyarı:** ağ öykünmesi bağdaştırıcısı yük testleri tarafından göz ardı edilir. Bunun yerine, yük testleri yük testi senaryosuna ağ karışımı belirtilen ayarları kullanın.|
|**Sistem bilgileri:** testi çalıştırıldığı makine hakkında sistem bilgileri dahil etmek için bir test ayarı ayarlanabilir.|Evet|Evet|Evet||
|**Test etkisi:** hakkında uygulama kodunuzun yöntemlerinin kullanıldığını bir test çalışması çalıştırdığınızda bilgi toplayabilirsiniz. Bu değişiklikleri ile hangi testlerin etkilendiğini belirlemek için geliştiriciler tarafından yapılan uygulama kodunda değişiklik yapılmasını birlikte kullanılabilir.|Evet|Evet|Evet|-Web istemci rolü için test etkisi verisi topluyorsanız, IntelliTrace ve Test etkisi tanılama veri bağdaştırıcısı için ASP.NET İstemci Proxy seçmeniz gerekir.<br />-IIS yalnızca şu sürümleri desteklenir: IIS 7.0, IIS 7.5 ve IIS 8. 0.|
|**Video Kaydedici:** bir testi çalıştırdığınızda masaüstü oturumunuzun bir video kaydı oluşturabilirsiniz. Video diğer takım üyeleri yeniden oluşturması zor olan uygulama sorunlarını gidermeye yardımcı olabilir.|Evet|Evet (notlara bakın)|Evet|-Bir hizmeti yerine bir işlem olarak çalıştırmak test aracısı yazılımı etkinleştirirseniz, bir video otomatikleştirilmiş testleri çalıştırdığınızda kaydı oluşturabilirsiniz.|