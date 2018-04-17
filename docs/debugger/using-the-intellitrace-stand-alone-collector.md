---
title: IntelliTrace tek başına toplayıcıyı kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.historicaldebug.collectdataoutsideVS
helpviewer_keywords:
- IntelliTrace, debugging applications in production
ms.assetid: 1bde9807-8219-4a2a-a440-ac5ee5178159
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9533c2a79a8fb692e970cf2f59d4be6feaaefc5f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="using-the-intellitrace-stand-alone-collector"></a>IntelliTrace tek başına toplayıcıyı kullanma
**IntelliTrace tek başına toplayıcıyı** IntelliTrace Tanılama verilerini uygulamalarınız için üretim sunucuları veya diğer ortamlara hedef makinede Visual Studio yükleme ve değiştirme olmadan toplamanıza olanak tanır sistemin ortam hedefleyin. IntelliTrace tek başına toplayıcıyı web, SharePoint, WPF ve Windows Forms uygulamalarında çalışır. Veri toplama bittiğinde, yalnızca kaldırmak için toplayıcı silin.  
  
 IntelliTrace eylemde izleyin: [toplama ve üretim (Channel 9 video) hata ayıklama için IntelliTrace verilerini analiz etme](http://go.microsoft.com/fwlink/?LinkID=251851)  
  
> [!NOTE]
>  Web ve kullanarak uzak makinelerde çalışan SharePoint uygulamaları için aynı IntelliTrace verilerini de toplayabilirsiniz **Microsoft İzleme Aracısı** içinde **izleme** modu.  
>   
>  Aracısı'nı çalıştırarak IntelliTrace veri performansı ile ilgili olayları toplayabilir **İzleyici** modu. **İzleyici** moduna sahip bir performans etkisi az **izleme** modu veya **IntelliTrace tek başına toplayıcıyı**. Yüklendiğinde Microsoft Monitoring Agent hedef sistemin ortam değiştirmez. Bkz: [Microsoft Monitoring Agent kullanarak](../debugger/using-the-microsoft-monitoring-agent.md).  
  
 **Gereksinimler**  
  
-   .NET framework 3.5, 4 veya 4.5  
  
-   Visual Studio .iTrace dosyaları açmaya Enterprise (ancak değil Professional veya topluluk sürümleri için) bir geliştirme veya diğer bilgisayarda  
  
    > [!NOTE]
    >  Simge (.pdb) dosyaları kaydettiğinizden emin olun. IntelliTrace ile hata ayıklama ve kod üzerinden adım için eşleşen kaynak dosyaları ve dosyaları simge olması gerekir. Bkz: [dağıtımdan sonra sorunları tanılama](../debugger/diagnose-problems-after-deployment.md).  
  
 **SSS**  
  
-   [Hangi uygulamaların toplayıcısı çalışıyor?](#WhatApps)  
  
-   [Nasıl başlayabilirim?](#GetStarted)  
  
-   [En çok veri Uygulamam yavaşlamasının olmadan nasıl alabilirim?](#Minimizing)  
  
-   [IntelliTrace verilerini başka nereden alabilirim?](#WhereElse)  
  
##  <a name="WhatApps"></a> Hangi uygulamaların toplayıcısı çalışıyor?  
  
-   Internet Information Services (IIS) sürüm 7.0, 7.5 ve 8.0 üzerinde barındırılan ASP.NET Web uygulamaları  
  
-   SharePoint 2010 ve SharePoint 2013 uygulamaları  
  
-   Windows Presentation Foundation (WPF) ve Windows uygulamaları oluşturur.  
  
##  <a name="GetStarted"></a> Nasıl başlayabilirim?  
  
1.  [Toplayıcı yükleme](#BKMK_Install_the_IntelliTrace_Stand_Alone_Collector)  
  
2.  [Toplayıcı directory izinlerini ayarlama](#ConfigurePermissionsRunningCollector)  
  
3.  [Web uygulamaları veya SharePoint uygulamaları için veri toplamak için IntelliTrace PowerShell cmdlet'lerini yükleyin](#BKMK_Set_up_the_IntelliTrace_PowerShell_commandlets)  
  
4.  [.İTrace dosya directory izinlerini ayarlama](#BKMK_Create_and_Configure_a_Log_File_Directory)  
  
5.  [Bir Web uygulaması veya SharePoint uygulaması veri toplayın](#BKMK_Collect_Data_from_IIS_Application_Pools)  
  
     -veya-  
  
     [Yönetilen bir uygulamadan veri toplama](#BKMK_Collect_Data_from_Executables)  
  
6.  [Visual Studio kuruluşta .iTrace dosyasını açın](#BKMK_View_IntelliTrace_Log_Files)  
  
##  <a name="BKMK_Install_the_IntelliTrace_Stand_Alone_Collector"></a> Toplayıcı yükleme  
  
1.  Uygulamanızın sunucuda Toplayıcı dizin örneğin oluşturun: **C:\IntelliTraceCollector**  
  
2.  Toplayıcı Microsoft Download Center veya Visual Studio 2013 güncelleştirme 3'ü yükleme klasöründen almak. [Visual Studio 2013 güncelleştirme 4 için IntelliTrace Toplayıcı](https://www.microsoft.com/en-us/download/details.aspx?id=44909)::  
  
    -   **Microsoft İndirme Merkezi**:  
  
        1.  Yanına **IntelliTraceCollector.exe**, seçin **karşıdan**.  
  
        2.  Örneğin IntelliTraceCollector.exe Toplayıcı dizinine kaydedin: **C:\IntelliTraceCollector**  
  
        3.  IntelliTraceCollector.exe çalıştırın. Bu IntelliTraceCollection.cab dosyasını ayıklar.  
  
         \- veya -  
  
    -   **Visual Studio yükleme klasörü**:  
  
        1.  IntelliTraceCollection.cab aşağıdaki klasörüne kopyalayın:  
  
             **..\Microsoft Visual Studio 12.0\Common7\IDE\CommonExtensions\Microsoft\IntelliTrace\12.0.0**  
  
        2.  IntelliTraceCollection.cab Toplayıcı dizininde örneğin koyun: **C:\IntelliTraceCollector**  
  
3.  IntelliTraceCollection.cab genişletin:  
  
    1.  Uygulamanızın sunucuda yönetici olarak bir komut istemi penceresi açın.  
  
    2.  Örneğin Toplayıcı dizinine göz atın: **C:\IntelliTraceCollector**  
  
    3.  Kullanım **genişletin** komutu, nokta ile birlikte (**.**) IntelliTraceCollection.cab genişletmek için bu sonunda:  
  
         `expand  /f:* IntelliTraceCollection.cab .`  
  
        > [!NOTE]
        >  Süre (**.**) yerelleştirilmiş koleksiyon planlarını içeren klasörleri korur.  
  
##  <a name="ConfigurePermissionsRunningCollector"></a> Toplayıcı directory izinlerini ayarlama  
  
1.  Uygulamanızın sunucuda yönetici olarak bir komut istemi penceresi açın.  
  
2.  Windows kullanan **icacls** sunucu Toplayıcı directory yönetici tam izin vermek için komutu. Örneğin:  
  
     `icacls "C:\IntelliTraceCollector" /grant "` *\<Domain\AdministratorID>* `":F`  
  
3.  Bir Web uygulaması veya SharePoint uygulaması için veri toplamak için:  
  
    1.  IntelliTrace PowerShell cmdlet'leri Toplayıcı dizinine tam izinleri çalışacak kişiye verin.  
  
         Örneğin:  
  
         `icacls "C:\IntelliTraceCollector" /grant "` *\<Domain\UserID>* `":F`  
  
    2.  Web uygulaması için uygulama havuzu verin veya SharePoint uygulaması okuma ve Yürütme izinleri Toplayıcı dizinine.  
  
         Örneğin:  
  
        -   Bir Web uygulaması için **DefaultAppPool** uygulama havuzu:  
  
             `icacls "C:\IntelliTraceCollector" /grant "IIS APPPOOL\DefaultAppPool":RX`  
  
        -   Bir SharePoint uygulaması için **SharePoint - 80** uygulama havuzu:  
  
             `icacls "C:\IntelliTraceCollector" /grant "IIS APPPOOL\SharePoint - 80":RX`  
  
##  <a name="BKMK_Set_up_the_IntelliTrace_PowerShell_commandlets"></a> Web uygulamaları veya SharePoint uygulamaları için veri toplamak için IntelliTrace PowerShell cmdlet'lerini yükleyin  
  
1.  Uygulamanızın sunucusunda PowerShell etkin olduğundan emin olun. Çoğu Windows Server sürümlerinde, bu özelliği ekleyebilirsiniz **Sunucu Yöneticisi'ni** yönetim aracı.  
  
     ![Sunucu Yöneticisi'ni kullanarak PowerShell ekleme](../debugger/media/intellitrace_servermanager_addpowershell.png "INTELLITRACE_ServerManager_AddPowerShell")  
  
2.  IntelliTrace PowerShell cmdlet'lerini yükleyin.  
  
    1.  Yönetici olarak bir PowerShell komut penceresi açın.  
  
        1.  Seçin **Başlat**, **tüm programlar**, **Donatılar**, **Windows PowerShell**.  
  
        2.  Aşağıdaki adımlardan birini seçin:  
  
            -   64-bit işletim sistemlerinde için kısayol menüsünü açın **Windows PowerShell**. Seçin **yönetici olarak çalıştır**.  
  
            -   32-bit işletim sistemlerinde için kısayol menüsünü açın **Windows PowerShell (x86)**. Seçin **yönetici olarak çalıştır**.  
  
    2.  PowerShell komut penceresini kullanma **Import-Module** içeri aktarmak için komutu **Microsoft.VisualStudio.IntelliTrace.PowerShell.dll**.  
  
         Örneğin:  
  
         `Import-Module "C:\IntelliTraceCollector\Microsoft.VisualStudio.IntelliTrace.PowerShell.dll"`  
  
##  <a name="BKMK_Create_and_Configure_a_Log_File_Directory"></a> .İTrace dosya directory izinlerini ayarlama  
  
1.  Örneğin, uygulamanızın sunucu üzerinde .iTrace dosyası dizini oluşturun: **C:\IntelliTraceLogFiles**  
  
    > [!NOTE]
    >  -   Uygulamanızı yavaşlamasının önlemek için çok etkin olmayan bir yerel diskte yüksek hızlı bir konum seçin.  
    > -   .İTrace dosyaları ve Toplayıcı dosyaları aynı yerde koyabilirsiniz. Ancak, bir Web uygulaması veya SharePoint uygulaması varsa, uygulamayı barındıran dizininin dışında Burası olduğundan emin olun.  
  
    > [!IMPORTANT]
    >  -   .İTrace dosyası dizini, Toplayıcı ile çalışması gereken kimlikleri kısıtlayın. Yöntem parametreleri veya dönüş değeri olarak geçirir herhangi bir veri IntelliTrace kaydedebileceği .iTrace dosya kullanıcılar, veritabanları, diğer kaynak konumları ve bağlantı dizeleri verileri gibi hassas bilgiler içerebilir.  
    > -   .İTrace dosyaları açabilir bu hassas verileri görüntülemek için yetkili olduğundan emin olun. .İTrace dosyaları paylaşırken dikkatli olun. Diğer kişilerin erişimi olması gerekir, dosyaları güvenli bir paylaşılan konuma kopyalayın.  
  
2.  Bir Web uygulaması veya SharePoint uygulaması için uygulama havuzunu .iTrace dosyası dizini tam izinleri verebilirsiniz. Windows kullanabilirsiniz **icacls** komutunu veya Windows Explorer (veya dosya Gezgini'ni) kullanın.  
  
     Örneğin:  
  
    -   Windows izinleri ayarlamak için **icacls** komutu:  
  
        -   Bir Web uygulaması için **DefaultAppPool** uygulama havuzu:  
  
             `icacls "C:\IntelliTraceLogFiles" /grant "IIS APPPOOL\DefaultAppPool":F`  
  
        -   Bir SharePoint uygulaması için **SharePoint - 80** uygulama havuzu:  
  
             `icacls "C:\IntelliTraceLogFiles" /grant "IIS APPPOOL\SharePoint - 80":F`  
  
         -veya-  
  
    -   Windows Gezgini (veya dosya Gezgini'ni) izinleriyle ayarlamak için:  
  
        1.  Açık **özellikleri** .iTrace dosyası dizini için.  
  
        2.  Üzerinde **güvenlik** sekmesinde, seçin **Düzenle**, **Ekle**.  
  
        3.  Emin olun **yerleşik güvenlik sorumluları** görünür **bu nesne türünü seçin** kutusu. Bunu sahip değil, seçerseniz **nesne türlerini** ekleyin.  
  
        4.  Yerel bilgisayarınızda emin olun görünür **bu konumdan** kutusu. Bunu sahip değil, seçerseniz **konumları** değiştirmek için.  
  
        5.  İçinde **Seçilecek nesne adlarını girin** kutusunda, Web uygulaması veya SharePoint uygulaması için uygulama havuzunu ekleyin.  
  
        6.  Seçin **Adları Denetle** adı çözümlenemedi. Seçin **Tamam**.  
  
        7.  Uygulama havuzu olduğundan emin olun **tam denetim**.  
  
##  <a name="BKMK_Collect_Data_from_IIS_Application_Pools"></a> Bir Web uygulaması veya SharePoint uygulaması veri toplayın  
  
1.  Veri toplama başlatmak için yönetici olarak bir PowerShell komut penceresi açın ve şu komutu çalıştırın:  
  
     `Start-IntelliTraceCollection` `"` *\<ApplicationPool >* `"`  *\<PathToCollectionPlan >*  *\<FullPathToITraceFileDirectory >*  
  
    > [!IMPORTANT]
    >  Bu komutu çalıştırdıktan sonra yazın **Y** veri toplama başlatmak istediğinizi onaylamak için.  
  
     Örneğin, bir SharePoint uygulamasında veri toplamak için **SharePoint - 80** uygulama havuzu:  
  
     `Start-IntelliTraceCollection "SharePoint - 80" "C:\IntelliTraceCollector\collection_plan.ASP.NET.default.xml" "C:\IntelliTraceLogFiles"`  
  
    |||  
    |-|-|  
    |*ApplicationPool*|Uygulamanızın çalıştığı uygulama havuzu adı|  
    |*PathToCollectionPlan*|Koleksiyon planı, Toplayıcı için ayarları yapılandırır bir .xml dosyası yolu.<br /><br /> Toplayıcı ile birlikte gelen bir plan belirtebilirsiniz. Aşağıdaki planları, Web uygulamaları ve SharePoint uygulamaları için çalışır:<br /><br /> -   collection_plan.ASP.NET.default.xml<br />     Yalnızca IntelliTrace olayları ve özel durumlar, veritabanı çağrılarını ve Web sunucusu isteklerinin dahil olmak üzere SharePoint olayları toplar.<br />-collection_plan.ASP.NET.trace.xml<br />     Toplar işlev çağrılarını ve collection_plan.ASP.NET.default.xml tüm veriler. Bu plan için ayrıntılı bir analiz iyi olduğu, ancak uygulamanızı collection_plan.ASP.NET.default.xml'den fazla aşağı yavaşlatabilir.<br /><br /> Uygulamanızı yavaşlamasının önlemek için bu planlarını özelleştirebilir veya kendi planınızı oluşturabilirsiniz. Güvenlik için özel planların Toplayıcı dosyalarıyla aynı güvenli bir konuma yerleştirin. Bkz: [oluşturma ve özelleştirme IntelliTrace koleksiyonu planları](http://go.microsoft.com/fwlink/?LinkId=227871) ve [nasıl alabilirim en veri Uygulamam yavaşlamasının olmadan?](#Minimizing) **Not:** varsayılan olarak, .iTrace dosyasının en büyük boyutu 100 MB'dir. .İTrace dosya bu sınıra ulaştığında, Toplayıcı yeni girişler için yer açmak üzere dosyanın en erken girişleri siler. Bu sınırı değiştirmek için koleksiyon planın Düzenle `MaximumLogFileSize` özniteliği. <br /><br /> *Bu koleksiyon planlarını yerelleştirilmiş sürümleri nereden bulabilirim?*<br /><br /> Yerelleştirilmiş planları toplayıcının klasörlerdeki bulabilirsiniz.|  
    |*FullPathToITraceFileDirectory*|.İTrace dosyası dizini tam yolu. **Güvenlik Notu:** göreli bir yol değil tam yolunu girin.|  
  
     Toplayıcı uygulama havuzuna ekler ve veri toplamayı başlatır.  
  
     *Şu anda .iTrace dosya açabilir miyim?* Hayır, dosya veri toplama sırasında kilitlendi.  
  
2.  Sorunu yeniden oluşturun.  
  
3.  .İTrace dosyasının anlık almak için şu sözdizimini kullanın:  
  
     `Checkpoint-IntelliTraceCollection` `"` *\<ApplicationPool >* `"`  
  
4.  Koleksiyon durumunu denetlemek için şu sözdizimini kullanın:  
  
     `Get-IntelliTraceCollectionStatus`  
  
5.  Veri toplamayı durdurmak için şu sözdizimini kullanın:  
  
     `Stop-IntelliTraceCollection` `"` *\<ApplicationPool >* `"`  
  
    > [!IMPORTANT]
    >  Bu komutu çalıştırdıktan sonra yazın **Y** veri toplamayı durdurmak istediğinizi onaylamak için. Aksi takdirde, Toplayıcı, verileri, işlem iTrace toplama dosya kilitli kalacak ya da dosya faydalı bilgiler içermeyebilir devam edebilir.  
  
6.  [Visual Studio kuruluşta .iTrace dosyasını açın](#BKMK_View_IntelliTrace_Log_Files)  
  
##  <a name="BKMK_Collect_Data_from_Executables"></a> Yönetilen bir uygulamadan veri toplama  
  
1.  Uygulamanızı başlatmak ve aynı anda veri toplamak için aşağıdaki sözdizimini kullanın:  
  
     *\<FullPathToIntelliTraceCollectorExecutable>* `\IntelliTraceSC.exe launch /cp:` *\<PathToCollectionPlan>* `/f:` *\<FullPathToITraceFileDirectoryAndFileName>* *\<PathToAppExecutableFileAndFileName>*  
  
     Örneğin, bir uygulamadan veri toplamak üzere adlı **Uygulamam**:  
  
     `C:IntelliTraceCollectorIntelliTraceSC.exe launch /cp:"C:IntelliTraceCollectorcollection_plan.ASP.NET.default.xml" /f:"C:IntelliTraceLogFilesMyApp.itrace" "C:MyAppMyApp.exe"`  
  
    |||  
    |-|-|  
    |*FullPathToIntelliTraceCollectorExecutable*|Toplayıcı yürütülebilir, IntelliTraceSC.exe tam yolu|  
    |*PathToCollectionPlan*|Koleksiyon planı, Toplayıcı için ayarları yapılandırır bir .xml dosyası yolu.<br /><br /> Toplayıcı ile birlikte gelen bir plan belirtebilirsiniz. Aşağıdaki planlar yönetilen uygulamalar için çalışır:<br /><br /> -   collection_plan.ASP.NET.default.xml<br />     Yalnızca IntelliTrace olayları özel durumlar, veritabanı çağrılarını ve Web sunucusu isteklerinin dahil toplar.<br />-collection_plan.ASP.NET.trace.xml<br />     Toplar işlev çağrılarını ve collection_plan.ASP.NET.default.xml tüm veriler. Bu plan için ayrıntılı bir analiz iyi olduğu, ancak uygulamanızı collection_plan.ASP.NET.default.xml'den fazla aşağı yavaşlatabilir.<br /><br /> Uygulamanızı yavaşlamasının önlemek için bu planlarını özelleştirebilir veya kendi planınızı oluşturabilirsiniz. Güvenlik için özel planların Toplayıcı dosyalarıyla aynı güvenli bir konuma yerleştirin. Bkz: [oluşturma ve özelleştirme IntelliTrace koleksiyonu planları](http://go.microsoft.com/fwlink/?LinkId=227871) ve [nasıl alabilirim en veri Uygulamam yavaşlamasının olmadan?](#Minimizing) **Not:** varsayılan olarak, .iTrace dosyasının en büyük boyutu 100 MB'dir. .İTrace dosya bu sınıra ulaştığında, Toplayıcı yeni girişler için yer açmak üzere dosyanın en erken girişleri siler. Bu sınırı değiştirmek için koleksiyon planın Düzenle `MaximumLogFileSize` özniteliği. <br /><br /> *Bu koleksiyon planlarını yerelleştirilmiş sürümleri nereden bulabilirim?*<br /><br /> Yerelleştirilmiş planları toplayıcının klasörlerdeki bulabilirsiniz.|  
    |*FullPathToITraceFileDirectoryAndFileName*|.İTrace dosya dizinini ve .iTrace dosya adıyla tam yolunu **.itrace** uzantısı. **Güvenlik Notu:** göreli bir yol değil tam yolunu girin.|  
    |*PathToAppExecutableFileAndFileName*|Yönetilen uygulama yolu ve dosya adı|  
  
2.  Uygulamadan çıkma veri toplamayı durdurun.  
  
3.  [Visual Studio kuruluşta .iTrace dosyasını açın](#BKMK_View_IntelliTrace_Log_Files)  
  
##  <a name="BKMK_View_IntelliTrace_Log_Files"></a> Visual Studio kuruluşta .iTrace dosyasını açın  
  
> [!NOTE]
>  IntelliTrace ile hata ayıklama ve kod üzerinden adım için eşleşen kaynak dosyaları ve dosyaları simge olması gerekir. Bkz: [dağıtımdan sonra sorunları tanılama](../debugger/diagnose-problems-after-deployment.md).  
  
1.  .İTrace dosyayı taşımak veya Visual Studio Enterprise (ancak değil Professional veya topluluk sürümleri) olan bir bilgisayara kopyalayın.  
  
2.  Visual Studio dışında .iTrace dosyasını çift tıklatın veya dosyayı açmak Visual Studio içinde.  
  
     Visual Studio gösterir **IntelliTrace Özet** sayfası. Çoğu bölümlerde, olayları veya diğer öğeleri gözden geçirebilir, bir öğe seçin ve bir noktada IntelliTrace ile hata ayıklamayı Başlat nerede ve ne zaman bir olay oluştu. Bkz: [IntelliTrace verilerini kaydedilmiş kullanma](../debugger/using-saved-intellitrace-data.md).  
  
    > [!NOTE]
    >  IntelliTrace ile hata ayıklama ve kod üzerinden adım için eşleşen kaynak dosyalarını ve geliştirme makinenizde dosyaları simge olması gerekir. Bkz: [dağıtımdan sonra sorunları tanılama](../debugger/diagnose-problems-after-deployment.md).  
  
##  <a name="Minimizing"></a> En çok veri Uygulamam yavaşlamasının olmadan nasıl sağlarım?  
 Dolayısıyla, uygulamanızın performansı IntelliTrace topladığı veriler ve bunları analiz kod türünü IntelliTrace çok fazla veri, toplayabilirsiniz. Bkz: [IntelliTrace toplamasını üretim sunucularında en iyi duruma getirme](http://go.microsoft.com/fwlink/?LinkId=255233).  
  
 Uygulamanızı yavaşlamasının olmadan çoğu veri almak için bazı yöntemler şunlardır:  
  
-   Toplayıcı bir sorun var. düşünürken ya da sorunu yeniden çalıştırın.  
  
     Toplama başlatmak, sorunu yeniden oluşturmak ve toplamayı durdur. Visual Studio kuruluşta .iTrace dosyasını açın ve verileri inceleyin. Bkz: [Visual Studio Enterprise .iTrace dosyasını açın](#BKMK_View_IntelliTrace_Log_Files).  
  
-   Web uygulamaları ve SharePoint uygulamaları için belirtilen uygulama havuzu paylaşır her uygulama için veri toplayıcı kaydeder. Bir koleksiyon planı yalnızca tek bir uygulama için modülleri belirtebilirsiniz olsa da bu uygulama havuzunu paylaşan herhangi bir uygulama yavaşlatabilir.  
  
     Diğer uygulamalar yavaşlamasının Toplayıcı önlemek için kendi uygulama havuzundaki her uygulama ana bilgisayar.  
  
-   Olaylar için IntelliTrace verilerini toplar koleksiyon planında gözden geçirin. İlgili olmayan veya ilgilendirmeyen olayları devre dışı bırakmak için koleksiyon planı düzenleyin.  
  
     Bir olay devre dışı bırakmak için ayarlanmış `enabled` için öznitelik `<DiagnosticEventSpecification>` öğesine `false`:  
  
     `<DiagnosticEventSpecification enabled="false">`  
  
     Varsa `enabled` öznitelik yoksa, Olay etkinleştirildi.  
  
     *Nasıl bu performansını?*  
  
    -   Uygulama için ilgili olmayan olaylar devre dışı bırakarak başlangıç zamanı azaltabilirsiniz. Örneğin, Windows iş akışı olayları Windows iş akışı kullanmayan uygulamalar için devre dışı bırakın.  
  
    -   Kayıt defterine erişim ancak kayıt defteri ayarları sorunları gösterme uygulamalar için kayıt defteri olaylarını devre dışı bırakarak hem Başlangıç hem de çalışma zamanı performansını iyileştirebilir.  
  
-   Modüller için IntelliTrace verilerini toplar koleksiyon planında gözden geçirin. Koleksiyon planı yalnızca ilgilendiğiniz modülleri içerecek şekilde düzenleyin:  
  
    1.  Koleksiyon planı açın. Bul `<ModuleList>` öğesi.  
  
    2.  İçinde `<ModuleList>`ayarlayın `isExclusionList` özniteliğini `false`.  
  
    3.  Kullanım `<Name>` öğesi her modülü aşağıdakilerden birini belirtin: dosya adı, adında, dize veya ortak anahtar içeren herhangi bir modül eklenecek dize değeri.  
  
     Örneğin, yalnızca ana Web modülünden Fabrikam Fiber Web uygulaması verileri toplamak için bunun gibi bir liste oluşturur:  
  
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
  
     *Nasıl bu performansını?*  
  
     Bu yöntem çağrısı bilgileri ve uygulama başlatılıp çalışır, IntelliTrace toplar diğer araçları veri miktarını azaltır. Bu veriler, sağlar:  
  
    -   Kod üzerinden veri topladıktan sonra adım.  
  
    -   Geçirilen ve işlevi çağrılarının döndürülen değerlerini inceleyin.  
  
     *Neden modülleri yerine bırakılsın mı?*  
  
     Varsayılan olarak, koleksiyon planlarını modülleri ayarlayarak hariç `isExclusionList` özniteliğini `true`. Ancak, modüller hariç hala listenin ölçütlere uyan yok ve, üçüncü taraf veya açık kaynak modülleri gibi ilginizi çekebilir değil modüllerden veri toplamayı neden olabilir.  
  
-   *IntelliTrace Topla olmayan herhangi bir veri var mı?*  
  
     Evet, performans etkisini azaltmak için geçirilen ve geçirilen ve yöntemleri döndürülen en üst düzey nesneler üzerinde yöntemleri ve temel veri türlerini alanlarındaki değerlere döndürülen temel veri türlerinin veri toplama değerlere IntelliTrace kısıtlar.  
  
     Örneğin, sahip olduğunuz varsayalım bir `AlterEmployee` tamsayı kabul yöntemi imza `id` ve bir `Employee` nesne `oldemployee`:  
  
     `public Employee AlterEmployee(int id, Employee oldemployee)`  
  
     `Employee` Türü şu öznitelikler bulunur: `Id`, `Name`, ve `HomeAddress`. Arasında bir ilişki ilişki var. `Employee` ve `Address` türü.  
  
     ![Çalışan ve adresi arasındaki ilişkiyi](../debugger/media/employeeaddressrelationship.png "EmployeeAddressRelationship")  
  
     Toplayıcı değerlerini kaydeder `id`, `Employee.Id`, `Employee.Name` ve `Employee` döndürülen nesne `AlterEmployee` yöntemi. Toplayıcı hakkında bilgi ancak kaydetmez `Address` olup olmadığını veya null olduğu dışında nesnesi. Toplayıcı ayrıca yerel değişkenler hakkındaki verileri kaydetmez `AlterEmployee` yöntemi diğer yöntemleri, bu noktada, yöntem parametreleri olarak kaydedilir parametre olarak yerel değişkenlere kullanmadığınız sürece.  
  
##  <a name="WhereElse"></a> IntelliTrace verilerini başka nereden alabilirim?  
  
-   Visual Studio Enterprise oturumunda hata ayıklama bir IntelliTrace dosyasından bkz [IntelliTrace özellikleri](../debugger/intellitrace-features.md).  
  
-   Microsoft Test Yöneticisi'nde bir test oturumundan bkz [nasıl yapılır: hata ayıklama zorluklarını çözmeye yardımcı olması için IntelliTrace verilerini toplama](http://msdn.microsoft.com/Library/02b6716f-569e-4961-938a-e790a0c74b5c).  
  
## <a name="where-can-i-get-more-information"></a>Daha fazla bilgiyi nereden bulabilirim?  
 [Kayıtlı IntelliTrace verilerini kullanma](../debugger/using-saved-intellitrace-data.md)  
  
 [IntelliTrace](../debugger/intellitrace.md)  
  
### <a name="blogs"></a>Bloglar  
 [IntelliTrace Standalone Collector kullanarak uzaktan](http://go.microsoft.com/fwlink/?LinkId=262277)  
  
 [Oluşturma ve IntelliTrace koleksiyon planlarını özelleştirme](http://go.microsoft.com/fwlink/?LinkId=227871)  
  
 [Üretim sunucularında IntelliTrace toplamasını en iyi duruma getirme](http://go.microsoft.com/fwlink/?LinkId=255233)  
  
 [Visual Studio ALM + TFS blogu](http://go.microsoft.com/fwlink/?LinkID=201340)  
  
### <a name="forums"></a>Forumlar  
 [Visual Studio Debugger](http://go.microsoft.com/fwlink/?LinkId=262263)  
  
### <a name="videos"></a>Videolar  
 [Kanal 9 video: toplama ve IntelliTrace verilerini analiz etme](http://go.microsoft.com/fwlink/?LinkID=251851)
