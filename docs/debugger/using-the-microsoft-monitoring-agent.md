---
title: Microsoft Monitoring Agent kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: fd0a86b9-015d-408e-aa58-59a0a97826ac
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2cf84975f96ca2d1935da7f750f5c120d72eb112
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34454589"
---
# <a name="using-the-microsoft-monitoring-agent"></a>Microsoft İzleme Aracısı’nı kullanma
Kullanarak IIS tarafından barındırılan ASP.NET web uygulamaları ve SharePoint 2010 veya 2013 uygulamaları hataları, performans sorunlarını ya da diğer sorunlar için yerel olarak izleyebilirsiniz **Microsoft İzleme Aracısı**. Tanılama olaylarını aracıdan bir IntelliTrace günlük (.iTrace) dosyasına kaydedebilirsiniz. Ardından tüm Visual Studio tanılama araçları ile sorunları hata ayıklamak için Visual Studio Enterprise'ı (ancak Professional veya topluluk sürümleri) oturum açabilirsiniz. Aracısı'nı çalıştırarak IntelliTrace Tanılama verilerini ve yöntem verilerini de toplayabilirsiniz **izleme** modu. Microsoft Monitoring Agent ile tümleştirilebilir [Application Insights](/azure/application-insights/) ve [System Center Operation Manager](http://technet.microsoft.com/library/hh205987.aspx). Yüklendiğinde Microsoft Monitoring Agent hedef sistemin ortam değiştirmez.  
  
> [!NOTE]
>  Hedef ortam kullanarak değiştirmeden Uzak makinelerde web, SharePoint, WPF ve Windows Form uygulamaları için IntelliTrace Tanılama ve yöntemi verileri toplayabilir **IntelliTrace tek başına toplayıcıyı**. Tek başına toplayıcıyı Microsoft Monitoring Agent çalışır durumda daha büyük bir performans etkisi olur **İzleyici** modu. Bkz: [IntelliTrace tek başına toplayıcıyı kullanma](../debugger/using-the-intellitrace-stand-alone-collector.md).  
  
 System Center 2012 kullanıyorsanız, sorunlarla ilgili uyarı almak ve kayıtlı IntelliTrace günlük dosyalarının bağlantılarını içeren Team Foundation Server iş öğeleri oluşturmak için Microsoft İzleme Aracısı'nı İşlem Yöneticisi ile birlikte kullanın. Ardından, bu iş öğelerini daha ayrıntılı hata ayıklama için başkalarına atayabilirsiniz. Bkz: [Operations Manager'ı geliştirme süreçleri ile tümleştirme](http://technet.microsoft.com/library/jj614609.aspx) ve [Microsoft Monitoring Agent ile izleme](http://technet.microsoft.com/en-us/library/dn465153.aspx).  
  
 Başlamadan önce oluşturulan ve dağıtılan kod için eşleşen kaynağa ve sembollere sahip olup olmadığınızı kontrol edin. Bu, hata ayıklamaya ve IntelliTrace günlüğünde tanılama olaylarını taramaya başladığınızda doğrudan uygulama koduna gitmenizi sağlar. [Derlemeleriniz ayarlamak](../debugger/diagnose-problems-after-deployment.md) böylece Visual Studio, otomatik olarak bulmak ve dağıtılan kodunuz için eşleşen kaynak açın.  
  
1.  [1. adım: Microsoft İzleme Aracısı ayarlama](#SetUpMonitoring)  
  
2.  [2. adım: uygulamanızı İzlemeyi Başlat](#MonitorEvents)  
  
3.  [3. adım: Kaydet olayları kaydedilir.](#SaveEvents)  
  
##  <a name="SetUpMonitoring"></a> 1. adım: Microsoft İzleme Aracısı ayarlama  
 Uygulamanızı değiştirmeden yerel izleme yapmak için web sunucunuz üzerinde bağımsız aracıyı ayarlayın. System Center 2012 kullanıyorsanız bkz [Microsoft İzleme Aracısı yükleme](http://technet.microsoft.com/library/dn465156.aspx).  
  
###  <a name="SetUpStandaloneMMA"></a> Tek başına aracısını ayarlama  
  
1.  Olduğundan emin olun:  
  
    -   Web sunucunuzun çalıştırdığı [desteklenen sürümleri Internet Information Services (IIS)](http://technet.microsoft.com/en-us/library/dn465154.aspx).  
  
    -   Web sunucunuzda .NET Framework 3.5, 4 veya 4.5 sürümü var.  
  
    -   Web sunucunuzun Windows PowerShell 3.0 veya üstü çalışıyor. [S: ı Windows PowerShell 2.0 yoksa ne?](#PowerShell2)  
  
    -   Web sunucunuz üzerinde, PowerShell komutlarını çalıştırmak ve izleme başlattığınızda uygulama havuzunu geri dönüştürmek için yönetici izinlerine sahipsiniz.  
  
    -   Microsoft İzleme Aracısı'nın önceki sürümlerini kaldırdınız.  
  
2.  [Ücretsiz Microsoft İzleme Aracısı'nı indirme](http://go.microsoft.com/fwlink/?LinkId=320384), 32-bit sürümünü **MMASetup-i386.exe** veya 64 bit sürümü **MMASetup-AMD64.exe**, web için Microsoft Download Center gelen Sunucu.  
  
3.  İndirdiğiniz yürütebilen dosyayı çalıştırarak yükleme sihirbazını başlatın.  
  
4.  Örneğin, IntelliTrace günlüklerini depolamak için web sunucunuzda güvenli bir dizin oluşturma **C:\IntelliTraceLogs**.  
  
     Bu dizini izlemeye başlamadan önce oluşturduğunuzdan emin olun. Uygulamanızı yavaşlamasının önlemek için çok etkin olmayan bir yerel diskte yüksek hızlı bir konum seçin.  
  
    > [!IMPORTANT]
    >  IntelliTrace günlükleri kişisel ve hassas veriler içerebilir. Bu dizini yalnızca dosyalarla çalışması gereken kimliklerle sınırlayın. Şirketinizin gizlilik ilkeleri denetleyin.  
  
5.  İşlev düzeyinde ayrıntılı izleme yapmak veya SharePoint uygulamalarını izlemek için, web uygulamanızı veya SharePoint uygulamanızı barındıran uygulama havuzuna IntelliTrace günlük dizini için okuma ve yazma izni verin. [S: uygulama havuzu için izinleri nasıl ayarlarım?](#FullPermissionsITLog)  
  
### <a name="q--a"></a>Soru - Yanıt  
  
####  <a name="PowerShell2"></a> S: ı Windows PowerShell 2.0 yoksa ne?  
 **Y:** PowerShell 3.0 kullanmanız önerilir. Aksi halde, PowerShell'i her çalıştırdığınızda Microsoft İzleme Aracısı PowerShell cmdlet'lerini içeri aktarmanız gerekir. Ayrıca, indirilebilen Yardım içeriğine de erişiminiz olmayacaktır.  
  
1.  Açık bir **Windows PowerShell** veya **Windows PowerShell ISE** komut istemini yönetici olarak.  
  
2.  Varsayılan yükleme konumundan Microsoft İzleme Aracısı PowerShell modülünü içeri aktarın:  
  
     **PS C: > Import-Module "C:\Program Files\Microsoft Agent\Agent\PowerShell\Microsoft.MonitoringAgent.PowerShell\Microsoft.MonitoringAgent.PowerShell.dll izleme"**  
  
3.  [TechNet ziyaret](http://technet.microsoft.com/systemcenter/default) en son Yardım içeriği almak için.  
  
####  <a name="FullPermissionsITLog"></a> S: uygulama havuzu için izinleri nasıl ayarlarım?  
 **Y:** pencerelerini kullanma **icacls** komutunu veya Windows Explorer (veya dosya Gezgini'ni) kullanın. Örneğin:  
  
-   Windows izinleri ayarlamak için **icacls** komutu:  
  
    -   Bir web uygulaması için **DefaultAppPool** uygulama havuzu:  
  
         `icacls "C:\IntelliTraceLogs" /grant "IIS APPPOOL\DefaultAppPool":RX`  
  
    -   Bir SharePoint uygulaması için **SharePoint - 80** uygulama havuzu:  
  
         `icacls "C:\IntelliTraceLogs" /grant "IIS APPPOOL\SharePoint - 80":RX`  
  
     -veya-  
  
-   Windows Gezgini (veya dosya Gezgini'ni) izinleriyle ayarlamak için:  
  
    1.  Açık **özellikleri** IntelliTrace günlük dizini için.  
  
    2.  Üzerinde **güvenlik** sekmesinde, seçin **Düzenle**, **Ekle**.  
  
    3.  Olduğundan emin olun **yerleşik güvenlik sorumluları** görünür **bu nesne türünü seçin** kutusu. Bunu sahip değil, seçerseniz **nesne türlerini** ekleyin.  
  
    4.  Yerel bilgisayarınızda emin olun görünür **bu konumdan** kutusu. Bunu sahip değil, seçerseniz **konumları** değiştirmek için.  
  
    5.  İçinde **Seçilecek nesne adlarını girin** kutusunda, web uygulaması veya SharePoint uygulaması için uygulama havuzunu ekleyin.  
  
    6.  Seçin **Adları Denetle** adı çözümlenemedi. Seçin **Tamam**.  
  
    7.  Uygulama havuzu olduğundan emin olun **okuma & yürütme** izinleri.  
  
##  <a name="MonitorEvents"></a> 2. adım: uygulamanızı İzlemeyi Başlat  
 Windows PowerShell kullanmak [Start-WebApplicationMonitoring](http://go.microsoft.com/fwlink/?LinkID=313686) uygulamanızı izlemeye başlamak için komutu. System Center 2012 kullanıyorsanız bkz [Microsoft Monitoring Agent ile Web uygulamalarını izleme](http://technet.microsoft.com/library/dn465157.aspx).  
  
1.  Web sunucunuz üzerinde açık bir **Windows PowerShell** veya **Windows PowerShell ISE** komut istemini yönetici olarak.  
  
     ![Windows PowerShell'i yönetici olarak açın](../debugger/media/ffr_powershellrunadmin.png "FFR_PowerShellRunAdmin")  
  
2.  Çalıştırma [Start-WebApplicationMonitoring](http://go.microsoft.com/fwlink/?LinkID=313686) uygulamanızı izlemeye başlamak için komutu. Bu, web sunucunuzdaki tüm web uygulamalarını yeniden başlatır.  
  
     Kısa sözdizimi şu şekildedir:  
  
     **Start-WebApplicationMonitoring** *"\<uygulamaadı >"*  *\<monitoringMode >* *"\<outputPath >"*  *\<UInt32 >* *"\<collectionPlanPathAndFileName >"*  
  
     İşte yalnızca web uygulaması adı ve basit kullanan bir örnek **İzleyici** modu:  
  
     **PS C: > Start-WebApplicationMonitoring "FabrikamFabrikamFiber.Web" izleme "C:IntelliTraceLogs"**  
  
     Basit ve IIS yolunu kullanır örneği **İzleyici** modu:  
  
     **PS C: > Start-WebApplicationMonitoring "IIS:sitesFabrikamFabrikamFiber.Web" izleme "C:IntelliTraceLogs"**  
  
     İzlemeye başladıktan sonra, uygulamalarınız yeniden başlatılırken Microsoft İzleme Aracısı'nın durakladığını görebilirsiniz.  
  
     ![MMA onayı İzlemeyi Başlat](../debugger/media/ffr_powershellstartmonitoringconfirmation.png "FFR_PowerShellStartMonitoringConfirmation")  
  
    |||  
    |-|-|  
    |*"\<uygulamaadı >"*|IIS içinde web sitesinin yolunu ve web uygulamasının adını belirtin. İsterseniz IIS yolunu da ekleyebilirsiniz.<br /><br /> *"\<IISWebsiteName >\\< IISWebAppName\>"*<br /><br /> -veya-<br /><br /> **"IIS:\sites**  *\\< IISWebsiteName\>\\< IISWebAppName\>"*<br /><br /> Bu yolu IIS Yöneticisi'nde bulabilirsiniz. Örneğin:<br /><br /> ![IIS web sitesi ve web uygulaması yolu](../debugger/media/ffr_iismanager.png "FFR_IISManager")<br /><br /> Aynı zamanda [Get-WebSite](http://technet.microsoft.com/library/ee807832.aspx) ve [alma WebApplication](http://technet.microsoft.com/library/ee790554.aspx) komutları.|  
    |*\<monitoringMode >*|İzleme modunu belirtin:<br /><br /> <ul><li>**İzleyici**: özel durum olayları ve performans olaylarını en az ayrıntılarını kaydeder. Bu mod varsayılan toplama planını kullanır.</li><li>**İzleme**: kayıt işlev düzeyi ayrıntıları veya belirtilen koleksiyon planı kullanarak SharePoint 2010 ve SharePoint 2013 uygulamalarını izleyin. Bu mod, uygulamanızın daha yavaş çalışmasına neden olabilir.<br /><br /> <ul><li>[S: uygulama havuzu için izinleri nasıl ayarlarım?](#FullPermissionsITLog)</li><li>[S: en çok veri Uygulamam yavaşlamasının olmadan nasıl sağlarım?](#Minimizing)</li></ul><br />     Bu örnek, bir SharePoint sitesi üzerindeki SharePoint uygulaması için olayları kaydeder:<br /><br />     **Start-WebApplicationMonitoring "FabrikamSharePointSite\FabrikamSharePointApp" izleme "C:\Program Files\Microsoft Agent\Agent\IntelliTraceCollector\collection_plan.ASP.NET.default.xml izleme" "C:\IntelliTraceLogs"**</li><li>**Özel**: Belirtilen özel koleksiyon planı kullanarak özel ayrıntıları kaydedin. İzleme başladıktan sonra toplama planını değiştirirseniz izlemeyi yeniden başlatmanız gerekir.</li></ul>|  
    |*"\<outputPath >"*|IntelliTrace günlüklerinin depolanacağı tam dizin yolunu belirtin. Bu dizini izlemeye başlamadan önce oluşturduğunuzdan emin olun.|  
    |*\<UInt32 >*|IntelliTrace günlüğünün çıkabileceği en büyük boyutu belirtin. IntelliTrace günlüğü için varsayılan en büyük boyut 250 MB'tır.<br /><br /> Günlük bu sınıra ulaştığında, aracı yeni girişlere yer açmak için en eski girişlerin üzerine yazar. Bu sınırı değiştirmek için kullanın **- Maximumfilesizeınmegabytes** seçeneğini veya düzenleme `MaximumLogFileSize` koleksiyon planı özniteliği.|  
    |*"\<collectionPlanPathAndFileName >"*|Toplama planının tam yolunu veya göreli yolunu ve dosya adını belirtin. Bu plan, aracı için ayarları yapılandıran bir .xml dosyasıdır.<br /><br /> Bu planlar aracıyla birlikte gelir ve web uygulamaları ve SharePoint uygulamalarıyla çalışır:<br /><br /> -   **collection_plan.ASP.NET.default.XML**<br />     Yalnızca özel durumlar, performans olayları, veritabanı çağrıları ve Web sunucusu istekleri gibi olayları toplar.<br />-   **collection_plan.ASP.NET.Trace.XML**<br />     Varsayılan toplama planındaki verilere ek olarak işlev düzeyi çağrıları toplar. Bu plan ayrıntılı analiz için iyidir ancak uygulamanızı yavaşlatabilir.<br /><br /> Bu planların yerelleştirilmiş sürümlerini aracının alt klasörlerinde bulabilirsiniz. Ayrıca [kendi planları oluşturun ya da bu planlarını özelleştirin](http://go.microsoft.com/fwlink/?LinkId=227871) uygulamanızı yavaşlamasının önlemek için. Özel planları aracıyla aynı güvenli konuma yerleştirin.<br /><br /> [S: en çok veri Uygulamam yavaşlamasının olmadan nasıl sağlarım?](#Minimizing)|  
  
     Tam söz dizimi ve diğer örnekler hakkında daha fazla bilgi için Çalıştır **get-help Start-WebApplicationMonitoring-ayrıntılı** komutu veya **get-help Start-WebApplicationMonitoring-örnekler** komutu.  
  
3.  Web uygulamaları çalıştırmak, izlenen tüm durumunu denetlemek için [Webuygulamasıizlemedurumunu](http://go.microsoft.com/fwlink/?LinkID=313685) komutu.  
  
### <a name="q--a"></a>Soru - Yanıt  
  
####  <a name="Minimizing"></a> S: en çok veri Uygulamam yavaşlamasının olmadan nasıl sağlarım?  
 **Y:** Microsoft İzleme Aracısı çok fazla veri toplayabilir ve toplamak için seçtiğiniz veri ve topladığınız nasıl bağlı olarak, uygulamanızın performansı etkiler. Uygulamanızı yavaşlamasının olmadan çoğu veri almak için bazı yöntemler şunlardır:  
  
-   Web uygulamaları ve SharePoint uygulamaları için, aracı belirtilen uygulama havuzunu paylaşan her uygulama için veri kaydeder. Bu aynı uygulama havuzunu paylaşan herhangi bir uygulamayı, toplamayı tek bir uygulamanın modüllerine kısıtlamanıza rağmen yavaşlatabilir. Diğer uygulamaları yavaşlatmayı önlemek için, her uygulamayı kendi uygulama havuzunda barındırın.  
  
-   Toplama planında aracının veri topladığı olayları gözden geçirin. İlgili olmayan veya ilgilendirmeyen olayları devre dışı bırakmak için koleksiyon planı düzenleyin. Bu, başlangıç ve çalışma zamanı performansını artırabilir.  
  
     Bir olay devre dışı bırakmak için ayarlanmış `enabled` için öznitelik `<DiagnosticEventSpecification>` öğesine `false`:  
  
     `<DiagnosticEventSpecification enabled="false">`  
  
     Varsa `enabled` öznitelik yoksa, Olay etkinleştirildi.  
  
     Örneğin:  
  
    -   Windows Workflow kullanmayan uygulamalar için Windows Workflow olaylarını devre dışı bırakın.  
  
    -   Kayıt defterine erişen ancak kayıt defteri ayarlarında sorun göstermeyen uygulamalar için kayıt defteri olaylarını devre dışı bırakın.  
  
-   Toplama planında aracının veri topladığı modülleri gözden geçirin. Toplama planını yalnızca ilginizi çeken modülleri içerecek şekilde düzenleyin.  
  
     Bu uygulama başladığında ve çalıştığında aracının topladığı yöntem çağrı bilgisi ve diğer araç verisi miktarını azaltır. Bu veriler, hata ayıklarken kod içinde adım adım ilerlemenize ve işlev çağrılarına gönderilen ve bu çağrılardan alınan değerleri gözden geçirmenize yardımcı olur.  
  
    1.  Koleksiyon planı açın. Bul `<ModuleList>` öğesi.  
  
    2.  İçinde `<ModuleList>`ayarlayın `isExclusionList` özniteliğini `false`.  
  
    3.  Kullanım `<Name>` öğesi her modülü aşağıdakilerden birini belirtin: dosya adı, adında, dize veya ortak anahtar içeren herhangi bir modül eklenecek dize değeri.  
  
     Bu örnek, Fabrikam Fiber web uygulamasının yalnızca ana modülünden veri toplayan bir liste oluşturur:  
  
    ```xml  
    <ModuleList isExclusionList="false">  
       <Name>FabrikamFiber.Web.dll</Name>  
    </ModuleList>  
  
    ```  
  
     Adı "Fabrikam" içeren herhangi bir modül verileri toplamak için bunun gibi bir liste oluşturun:  
  
    ```xml  
    <ModuleList isExclusionList="false">  
       <Name>Fabrikam</Name>  
    </ModuleList>  
  
    ```  
  
     Kendi ortak anahtar belirteçlerinden belirterek modüllerden verileri toplamak için bunun gibi bir liste oluşturun:  
  
    ```xml  
    <ModuleList isExclusionList="false">  
       <Name>PublicKeyToken:B77A5C561934E089</Name>  
       <Name>PublicKeyToken:B03F5F7F11D50A3A</Name>  
       <Name>PublicKeyToken:31BF3856AD364E35</Name>  
       <Name>PublicKeyToken:89845DCD8080CC91</Name>  
       <Name>PublicKeyToken:71E9BCE111E9429C</Name>  
    </ModuleList>  
  
    ```  
  
     **S: neden değil yalnızca modüller yerine bırakılsın mı?**  
  
     **Y:** varsayılan olarak, koleksiyon planlarını modülleri ayarlayarak hariç `isExclusionList` özniteliğini `true`. Ancak bu, yine de üçüncü taraf veya açık kaynak modüller gibi listenin ölçütlerine uymayan veya ilgilenmediğiniz modüllerden veri toplayabilir.  
  
#### <a name="q-what-values-does-the-agent-collect"></a>S: Aracı hangi değerleri toplar?  
 **Y:** aracı performans üzerindeki etkisini azaltmak için yalnızca bu değerleri toplar:  
  
-   Yöntemlere geçirilen ve yöntemlerden döndürülen ilkel veri türleri  
  
-   Yöntemlere geçirilen veya yöntemlerden geri döndürülen en üst düzey nesnelerin alanlarındaki ilkel veri türleri  
  
 Örneğin, sahip olduğunuz varsayalım bir `AlterEmployee` tamsayı kabul yöntemi imza `id` ve bir `Employee` nesne `oldemployee`:  
  
 `public Employee AlterEmployee(int id, Employee oldemployee)`  
  
 `Employee` Türü şu öznitelikler bulunur: `Id`, `Name`, ve `HomeAddress`. Arasında bir ilişki ilişki var. `Employee` ve `Address` türü.  
  
 ![Çalışan ve adresi arasındaki ilişkiyi](../debugger/media/employeeaddressrelationship.png "EmployeeAddressRelationship")  
  
 Aracı `id`, `Employee.Id` ve `Employee.Name` değerlerini ve `Employee` yönteminden döndürülen `AlterEmployee` nesnesini kaydeder. Ancak aracı `Address` nesnesi hakkında, nesnenin null olup olmadığı dışında bilgi kaydetmez. Aracı, ayrıca, `AlterEmployee` yöntemindeki yerel değişkenlerle ilgili olarak, diğer yöntemler bu yerel değişkenleri parametre olarak kullanıp onların yöntem parametresi olarak kaydedilmesini sağlamadığı sürece, veri kaydetmez.  
  
##  <a name="SaveEvents"></a> 3. adım: Kaydet olayları kaydedilir.  
 Bir hata veya performans sorunu bulduğunuzda, kayıtlı olayları bir IntelliTrace günlüğüne kaydedin. Aracı günlüğü yalnızca olay kaydettiyse oluşturur. System Center 2012 kullanıyorsanız bkz [Microsoft Monitoring Agent ile Web uygulamalarını izleme](http://technet.microsoft.com/library/dn465157.aspx).  
  
### <a name="save-recorded-events-but-continue-monitoring"></a>Kayıtlı olayları kaydedip izlemeye devam etme  
 IntelliTrace günlüğünü oluşturmak istediğinizde ancak uygulamanızı yeniden başlatmak veya izlemeyi durdurmak istemediğinizde bu adımları izleyin. Aracı, sunucu veya uygulama yeniden başlasa bile izlemeye devam eder.  
  
1.  Web sunucunuzda yönetici olarak bir Windows PowerShell komut istemi penceresi açın.  
  
2.  Çalıştırma [Checkpoint-WebApplicationMonitoring](http://go.microsoft.com/fwlink/?LinkID=313684) komutu IntelliTrace günlüğü görüntüsünü kaydetmek için:  
  
     **Checkpoint-WebApplicationMonitoring** *"\<IISWebsiteName >\\< IISWebAppName\>"*  
  
     \- veya -  
  
     **Checkpoint-WebApplicationMonitoring "IIS:\sites**  *\\< IISWebsiteName\>\\< IISWebAppName\>"*  
  
     Örneğin:  
  
     **PS C:\\> Checkpoint-WebApplicationMonitoring "Fabrikam\FabrikamFiber.Web"**  
  
     -veya-  
  
     **PS C: > Checkpoint-WebApplicationMonitoring "IIS:sitesFabrikamFabrikamFiber.Web"**  
  
     Daha fazla bilgi için **get-help Checkpoint-WebApplicationMonitoring-ayrıntılı** komut veya **get-help Checkpoint-WebApplicationMonitoring-örnekler** komutu.  
  
3.  Günlük güvenli paylaşılan bir klasöre kopyalayın ve Visual Studio Enterprise (ancak Professional veya topluluk sürümleri) sahip bir bilgisayarda oturum açın.  
  
    > [!IMPORTANT]
    >  Kişisel ve hassas veriler içerebileceklerinden, IntelliTrace günlüklerini paylaşırken dikkatli olun. Bu günlüklere erişebilen kişilerin o verileri görme izni olduğundan emin olun. Şirketinizin gizlilik ilkeleri denetleyin.  
  
 **Sonraki:** [Tanıla kaydedilen olayları Visual Studio Enterprise](../debugger/diagnose-problems-after-deployment.md#InvestigateEvents)  
  
### <a name="save-recorded-events-and-stop-monitoring"></a>Kayıtlı olayları kaydedip izlemeyi durdurma  
 Belirli bir sorunu yeniden oluştururken yalnızca tanı bilgilerini almak istediğinizde bu adımları izleyin. Bu, web sunucunuzdaki tüm web uygulamalarını yeniden başlatır.  
  
1.  Web sunucunuzda yönetici olarak bir Windows PowerShell komut istemi penceresi açın.  
  
2.  Çalıştırma [Stop-WebApplicationMonitoring](http://go.microsoft.com/fwlink/?LinkID=313687) IntelliTrace günlüğü oluşturmak ve bir özel web uygulaması izlemeyi durdurmak için komutu:  
  
     **Stop-WebApplicationMonitoring** *"\<IISWebsiteName >\\< IISWebAppName\>"*  
  
     \- veya -  
  
     **Stop-WebApplicationMonitoring "IIS:\sites**  *\\< IISWebsiteName\>\\< IISWebAppName\>"*  
  
     Veya tüm web uygulamalarının izlenmesini durdurmak için:  
  
     **Stop-WebApplicationMonitoring - tüm**  
  
     Örneğin:  
  
     **PS C:\\> Stop-WebApplicationMonitoring "Fabrikam\iFabrikamFiber.Web"**  
  
     \- veya -  
  
     **PS C:\\> Stop-WebApplicationMonitoring "IIS:\sites\Fabrikam\FabrikamFiber.Web"**  
  
     Daha fazla bilgi için **get-help Stop-WebApplicationMonitoring-ayrıntılı** komut veya **get-help Stop-WebApplicationMonitoring-örnekler** komutu.  
  
3.  Günlük güvenli paylaşılan bir klasöre kopyalayın ve Visual Studio Enterprise sahip bir bilgisayarda oturum açın.  
  
 **Sonraki:** [Tanıla kaydedilen olayları Visual Studio Enterprise](../debugger/diagnose-problems-after-deployment.md#InvestigateEvents)  
  
## <a name="q--a"></a>Soru - Yanıt  
  
### <a name="q-where-can-i-get-more-information"></a>S: Nereden daha fazla bilgi edinebilirim?  
  
#### <a name="blogs"></a>Bloglar  
 [Microsoft Monitoring Agent Tanıtımı](http://blogs.msdn.com/b/visualstudioalm/archive/2013/09/20/introducing-microsoft-monitoring-agent.aspx)  
  
 [Üretim sunucularında IntelliTrace toplamasını en iyi duruma getirme](http://go.microsoft.com/fwlink/?LinkId=255233)  
  
#### <a name="forums"></a>Forumlar  
 [Visual Studio tanılama](http://go.microsoft.com/fwlink/?LinkId=262263)