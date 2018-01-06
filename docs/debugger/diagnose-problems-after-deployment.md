---
title: "Dağıtımdan sonra sorunları tanılama | Microsoft Docs"
ms.custom: 
ms.date: 06/20/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3463eab-a352-4d17-8551-adbaad526db0
caps.latest.revision: "60"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 562222296ca79a568a3b68aac55a879c8f2f51b1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="diagnose-problems-after-deployment"></a>Dağıtımdan sonra sorunları tanılama
IntelliTrace'i kullanarak dağıtımdan sonra ASP.NET web uygulamanızda sorunları tanılamak için Visual Studio IntelliTrace günlük hata ayıklamak için gereken simge dosyaları ve doğru kaynak dosyalarını otomatik olarak bulmak izin vermek için sürüm ile yapı bilgileri içerir.  

 Microsoft Monitoring Agent denetim IntelliTrace kullanıyorsanız, ayrıca uygulama, web sunucunuz üzerinde performansı izleme yukarı kümesi ayarlamanız gerekir. Uygulamanızı çalıştıran ve olayları bir IntelliTrace günlük dosyasına kaydeder çalışırken bu tanılama olayları kaydeder. Ardından Visual Studio Enterprise (ancak değil Professional veya topluluk sürümleri) olayları bakmak, bir olay yapıldığı koda gitme olanağı zamandaki o noktada kaydedilen değerlere göz ve İleri ya da geri çalışan kodda taşıma. Bulmak ve sorunu düzelttikten sonra derleme, sürüm ve önceki ve daha hızlı gelecekteki olası sorunları çözebilmek sürüm izlemek için döngü yineleyin.  

 ![Kod, derleme, sürüm, izleme, tanılama, düzeltme](../debugger/media/ffr_cycle.png "FFR_Cycle")  

 **İhtiyacınız vardır:**  
  
-   Visual Studio 2017, Visual Studio 2015 veya Team Foundation Server 2017, 2015, 2013, 2012 veya 2010'u, yapı ayarlayın  
  
-   Microsoft Monitoring Agent'ı uygulama ve kaydı tanılama verilerinizi izlemek için  

-   Tanılama verilerini gözden geçirin ve kodunuzu IntelliTrace ile hata ayıklamak için Visual Studio Enterprise'ı (ancak Professional veya topluluk sürümleri)  

##  <a name="SetUpBuild"></a>1. adım: Dahil sürüm bilgilerle derleme  
 Web projeniz için bir derleme bildirimi (BuildInfo.config dosyası) oluşturmak için derleme işleminizi ayarlayın ve sürüm ile bu bildirimini içerir. Bu bildirim, proje, kaynak denetimi ve belirli bir yapı oluşturmak için kullanılan yapılandırma sistemi hakkında bilgiler içerir. Bu bilgiler, kaydedilen olayları gözden geçirmek için IntelliTrace oturum açtıktan sonra eşleşen kaynak ve simgeleri Bul Visual Studio yardımcı olur.  

###  <a name="AutomatedBuild"></a>Team Foundation Server kullanarak otomatik bir yapı için derleme bildirimi oluşturma  

 Team Foundation sürüm denetimi veya Git kullanıp şu adımları izleyin.
  
 **2. adım:** [2. adım: uygulamanızı sürüm](#DeployRelease)  
  
 Team Foundation sürüm denetimi veya Git kullanıp şu adımları izleyin.  
 
 ####  <a name="TFS2017"></a>Team Foundation Server 2017

 Derleme bildirimi (BuildInfo.config dosyası) için kaynak, yapı ve simgeleri konumlarını eklemek için yapı tanımınızı ayarlayın. Team Foundation Build otomatik olarak bu dosyayı oluşturur ve projenizin çıkış klasörüne yerleştirir.
  
1.  ASP.NET Core (.NET Framework) şablonu kullanarak bir derleme tanımınız varsa, aşağıdakilerden birini yapabilirsiniz [yapı tanımınızı düzenleyin veya yeni bir derleme tanımı oluşturun.](http://msdn.microsoft.com/Library/1c2eca2d-9a65-477e-9b23-0678ff7882ee)
  
     ![Yapı TFS 2017 tanımında görüntüle](../debugger/media/ffr_tfs2017viewbuilddefinition.png "FFR_TFS2013ViewBuildDefinition")
  
2.  Yeni bir şablon oluşturursanız, ASP.NET Core (.NET Framework) şablonunu seçin. 
  
     ![Derleme işlem şablonu &#45;seçin; TFS 2017](../debugger/media/ffr_tfs2017buildprocesstemplate.png "FFR_TFS2013BuildProcessTemplate")  
  
3.  Böylece kaynağınız otomatik olarak dizine simgeleri (PDB) dosyasının kaydedileceği yeri belirtin.  
  
     Özel bir şablon kullanırsanız, şablonun kaynağınızı dizinleyecek bir aktivitesi olduğundan emin olun. MSBuild bağımsız değişken sembolleri dosyaları kaydetmek istediğiniz konumu belirtmek için daha sonra eklersiniz.
  
     ![Yapı tanımı TFS 2017 simgeleri yolunda ayarlama](../debugger/media/ffr_tfs2017builddefsymbolspath.png "FFR_TFS2013BuildDefSymbolsPath")  
  
     Simgeler hakkında daha fazla bilgi için bkz: [simge verilerini yayınlamak](http://msdn.microsoft.com/Library/bd6977ca-e30a-491a-a153-671d81222ce6).  
  
4.  TFS ve simgeleri konumlarınıza yapı bildirim dosyasında dahil etmek için bu MSBuild bağımsız değişkeni ekleyin:  
  
     **/p:IncludeServerNameInBuildInfo = true**  
  
     Web sunucunuzun erişebilen herkes bu konumları derleme bildiriminde görebilirsiniz. Kaynak Sunucunuzu güvenli olduğundan emin olun.
  
6.  Yeni bir yapı çalıştırın.  

####  <a name="TFS2013"></a>Team Foundation Server 2013  
 Derleme bildirimi (BuildInfo.config dosyası) için kaynak, yapı ve simgeleri konumlarını eklemek için yapı tanımınızı ayarlayın. Team Foundation Build otomatik olarak bu dosyayı oluşturur ve projenizin çıkış klasörüne yerleştirir.  

1.  [Yapı tanımı düzenleyin veya yeni bir derleme tanımı oluşturun.](http://msdn.microsoft.com/Library/1c2eca2d-9a65-477e-9b23-0678ff7882ee)  

     ![Yapı tanımı TFS 2013'te görüntüle](../debugger/media/ffr_tfs2013viewbuilddefinition.png "FFR_TFS2013ViewBuildDefinition")  

2.  Varsayılan şablon (TfvcTemplate.12.xaml) veya kendi özel şablonunuzu seçin.  

     ![Derleme işlem şablonu &#45;seçin; TFS 2013](../debugger/media/ffr_tfs2013buildprocesstemplate.png "FFR_TFS2013BuildProcessTemplate")  

3.  Böylece kaynağınız otomatik olarak dizine simgeleri (PDB) dosyasının kaydedileceği yeri belirtin.  

     Özel bir şablon kullanırsanız, şablonun kaynağınızı dizinleyecek bir aktivitesi olduğundan emin olun. MSBuild bağımsız değişken sembolleri dosyaları kaydetmek istediğiniz konumu belirtmek için daha sonra eklersiniz.  

     ![Yapı tanımı TFS 2013 simgeleri yolunda ayarlama](../debugger/media/ffr_tfs2013builddefsymbolspath.png "FFR_TFS2013BuildDefSymbolsPath")  

     Simgeler hakkında daha fazla bilgi için bkz: [simge verilerini yayınlamak](http://msdn.microsoft.com/Library/bd6977ca-e30a-491a-a153-671d81222ce6).  

4.  TFS ve simgeleri konumlarınıza yapı bildirim dosyasında dahil etmek için bu MSBuild bağımsız değişkeni ekleyin:  

     **/p:IncludeServerNameInBuildInfo = true**  
  
     Web sunucunuzun erişebilen herkes bu konumları derleme bildiriminde görebilirsiniz. Kaynak Sunucunuzu güvenli olduğundan emin olun.

5.  Özel bir şablon kullanıyorsanız, simgeleri dosyasının kaydedileceği yeri belirtmek için bu MSBuild bağımsız değişkeni ekleyin:  
  
     **/p:BuildSymbolStorePath =**\<*simge yolu*>  
  
     ![Yapı sunucu bilgisi derleme def TFS 2013 dahil](../debugger/media/ffr_tfs2013builddefincludeserverinfo.png "FFR_TFS2013BuildDefIncludeServerInfo")  
  
     Ve web proje dosyanıza (.csproj, .vbproj) bu satırları ekleyin:  
  
    ```  
    <!-- Import the targets file. Change the folder location as necessary. -->  
       <Import Project=""$(MSBuildExtensionsPath)\Microsoft\VisualStudio\v$(VisualStudioVersion)\BuildInfo\Microsoft.VisualStudio.ReleaseManagement.BuildInfo.targets" />  
  
    ```  

     Web sunucunuzun erişebilen herkes bu konumları derleme bildiriminde görebilirsiniz. Kaynak Sunucunuzu güvenli olduğundan emin olun.  

6.  Yeni bir yapı çalıştırın.  

 **2. adım:** [2. adım: uygulamanızı sürüm](#DeployRelease)  

####  <a name="TFS2012_2010"></a>Team Foundation Server 2012 veya 2010  
 Otomatik olarak projeniz için derleme bildirimi (BuildInfo.config dosyası) oluşturun ve dosyayı projenizin çıkış klasörüne koyun için aşağıdaki adımları izleyin. Dosya olarak görüntülenir "*ProjectName*. Çıkış klasöründe "BuildInfo.config ancak olduğu uygulamanızı yayımladıktan sonra dağıtım klasörü" BuildInfo.config"yeniden adlandırıldı.  

1.  Visual Studio 2013 (herhangi bir sürümünü) Team Foundation Yapı sunucunuza yükleyin.  

2.  Yapı tanımınızda, kaynağı otomatik olarak endeksleyen simgelerin kaydedileceği konumu belirtin.  

     Özel bir şablon kullanırsanız, şablonun kaynağınızı dizinleyecek bir aktivitesi olduğundan emin olun.  

3.  Yapı tanımınıza bu MSBuild bağımsız değişkenlerini ekleyin:  

    -   **/p:VisualStudioVersion 12.0 =**  

    -   **/p:MSBuildAssemblyVersion 12.0 =**  

    -   **/TV:12.0**  

    -   **/p:IncludeServerNameInBuildInfo = true**  

    -   **/p:BuildSymbolStorePath =**\<*simge yolu*>  

4.  Yeni bir yapı çalıştırın.  

 **2. adım:** [2. adım: uygulamanızı sürüm](#DeployRelease)  

###  <a name="ManualBuild"></a>Visual Studio kullanarak el ile bir yapı için derleme bildirimi oluşturma  
 Otomatik olarak projeniz için derleme bildirimi (BuildInfo.config dosyası) oluşturun ve dosyayı projenizin çıkış klasörüne koyun için aşağıdaki adımları izleyin. Dosya olarak görüntülenir "*ProjectName*. Çıkış klasöründe "BuildInfo.config ancak olduğu uygulamanızı yayımladıktan sonra dağıtım klasörü" BuildInfo.config"yeniden adlandırıldı.  

1.  İçinde **Çözüm Gezgini**, web projeniz kaldırın.  

2.  Proje dosyası (.csproj, .vbproj) açın. Şu satırları ekleyin:  

    ```xml  
    <!-- **************************************************** -->  
    <!-- Build info -->  
    <PropertyGroup>  
       <!-- Generate the BuildInfo.config file -->  
       <GenerateBuildInfoConfigFile>True</GenerateBuildInfoConfigFile>  
       <!-- Include server name in build info -->   
       <IncludeServerNameInBuildInfo>True</IncludeServerNameInBuildInfo>   
       <!-- Include the symbols path so Visual Studio can find the matching deployed code when you start debugging. -->  
       <BuildSymbolStorePath><path to symbols></BuildSymbolStorePath>  
    </PropertyGroup>  
    <!-- **************************************************** -->  
    ```  

3.  Güncelleştirilen proje dosyasında denetleyin.  

4.  Yeni bir yapı çalıştırın.  

 **2. adım:** [2. adım: uygulamanızı sürüm](#DeployRelease)  

###  <a name="MSBuild"></a>Derleme bildirimi MSBuild.exe kullanarak el ile bir yapı için oluşturma  
 Bir yapı çalıştırdığınızda bu bağımsız değişkenler derleme ekleyin:  

 **/p:GenerateBuildInfoConfigFile = true**  

 **/p:IncludeServerNameInBuildInfo = true**  

 **/p:BuildSymbolStorePath =**\<*simge yolu*>  

##  <a name="DeployRelease"></a>2. adım: uygulamanızı sürüm  
 Kullanırsanız [Web.Deploy paket](http://msdn.microsoft.com/library/dd394698.aspx) uygulamanızı dağıtmak için derleme süreci tarafından oluşturulduğu, yapı bildirim alanından otomatik olarak yeniden adlandırılır "*ProjectName*. "BuildInfo.config" için "BuildInfo.config ve web sunucunuzda, uygulamanızın Web.config dosyasında ile aynı klasöre yerleştirin.  

 Uygulamanızı dağıtmak için diğer yöntemleri kullanırsanız derleme bildirimi gelen adlandırılır emin olun "*ProjectName*. "BuildInfo.config" için "BuildInfo.config ve uygulamanızın Web.config dosyasında web sunucusu ile aynı klasöre yerleştirin.  

## <a name="step-3-monitor-your-app"></a>Adım 3: Uygulamanızı izleyin  
 Böylece uygulamanız sorunları için izleyebilir, tanılama olaylarını kaydetmek ve bu olayları bir IntelliTrace günlük dosyasına kaydedin uygulama performans web sunucunuzda izleme işlevini ayarlama. Bkz: [dağıtım sorunları için sürüm izlemek](../debugger/using-the-intellitrace-stand-alone-collector.md).  

##  <a name="InvestigateEvents"></a>4. adım: sorun Bul  
 Visual Studio Enterprise geliştirme bilgisayarınıza veya kaydedilmiş olayları gözden geçirmek ve IntelliTrace kullanarak kodunuzun hatalarını ayıklamak için başka bir bilgisayarda gerekir. CodeLens, hata ayıklayıcı eşlemeleri gibi araçları da kullanabilirsiniz ve sorunu tanılamak yardımcı olması için kod eşler.  

### <a name="open-the-intellitrace-log-and-matching-solution"></a>IntelliTrace günlüğünü ve eşleşen çözümü açın  

1.  Visual Studio kuruluş IntelliTrace günlüğü'nü (.iTrace dosyası) açın. Veya yalnızca Visual Studio Enterprise aynı bilgisayarda varsa, dosyayı çift tıklatın.  

2.  Seçin **açmak çözüm** eşleşen çözüm ya da proje, otomatik olarak açılmasını Visual Studio Proje çözümün bir parçası yerleşik değildi varsa için. [S: IntelliTrace günlük dağıtılan Uygulamam hakkında bilgiler eksik. Bunun nedeni? Ne yapmalıyım?](#InvalidConfigFile)  

     Eşleşen çözüm ya da proje açıldığında visual Studio bekleyen değişiklikleri otomatik olarak kaldırır. Bu shelveset hakkında daha fazla bilgi almak için konum **çıkış** penceresi veya **Takım Gezgini**.  

     Herhangi bir değişiklik yapmadan önce doğru kaynak sahip olduğunuzdan emin olun. Dal oluşturma kullanırsanız, Visual Studio sürüm dalı gibi eşleşen kaynak yeri bulur daha farklı bir dal çalışıyor olabilirsiniz.  

     ![IntelliTrace günlüğü'nden çözüm açmak](../debugger/media/ffr_itsummarypageopensolution.png "FFR_ITSummaryPageOpenSolution")  

     Bu çözüm ya da proje eşlenmiş varolan bir çalışma alanı varsa, Visual Studio bulunan kaynak koymak için bu çalışma alanı seçer.  

     ![Açık kaynak denetiminden eşlenen çalışma](../debugger/media/ffr_openprojectfromsourcecontrol_mapped.png "FFR_OpenProjectFromSourceControl_Mapped")  

     Aksi halde, zaten eşleşmiş başka bir çalışma alanı seçin veya yeni bir çalışma alanı oluşturun. Visual Studio tüm dalı bu çalışma alanına eşleyecektir.  

     ![Açık kaynak denetiminden &#45; Yeni çalışma alanı oluşturma](../debugger/media/ffr_openprojectfromsourcecontrol_createnewworkspace.png "FFR_OpenProjectFromSourceControl_CreateNewWorkspace")  

     Belirli eşlemeleri veya bilgisayarınızın adını değil bir ad ile bir çalışma alanı oluşturmak için seçtiğiniz **Yönet**.  

     [S: neden Visual Studio seçilen çalışma Alanım uygun değil dediği?](#IneligibleWorkspace)  

     [Neden bir takım veya farklı bir koleksiyon seçene kadar ı devam edemiyor?](#ChooseTeamProject)  

### <a name="diagnose-a-performance-problem"></a>Performans sorunu tanıla  

1.  Altında **performans ihlallerinin**, kaydedilen performans olayları, toplam yürütme zamanları ve diğer olay bilgileri gözden geçirin. Sonra belirli performans olayı sırasında çağrılan yöntemlerde fazla araştırma yapın.  

     ![Performans olay ayrıntıları görüntüleyin](../debugger/media/ffr_itsummarypageperformance.png "FFR_ITSummaryPagePerformance")  

     Ayrıca, olayı çift tıklatabilirsiniz.  

2.  Olay sayfasında, bu çağrılar için yürütme zamanını gözden geçirin. Yürütme ağacında yavaş bir çağrı bulun.  

     İç içe ya da başka şekilde birden fazla çağrınız varsa, en yavaş çağrılar kendi bölümünde görüntülenir.  

     Yuvalanmış çağrıları ve zamanın o anında kaydedilmiş değerleri gözden geçirmek için o çağrıyı genişletin. Sonra o çağrıdan hata ayıklamayı başlatın.  

     ![Yöntem çağrısının hata ayıklamayı Başlat](../debugger/media/ffr_itsummarypageperformancemethodscalled.png "FFR_ITSummaryPagePerformanceMethodsCalled")  

     Ayrıca, aramayı çift tıklatabilirsiniz.  

     Yöntem uygulama kodunuzda ise, Visual Studio bu yönteme gider.  

     ![Git uygulama kodu performans olaydan](../debugger/media/ffr_itsummarypageperformancegotocode.png "FFR_ITSummaryPagePerformanceGoToCode")  

     Çağrı yığını kaydedilmiş diğer değerleri gözden geçirebilirsiniz şimdi adım kodunuz veya kullanmak **IntelliTrace** penceresine [geriye doğru veya ileten "zamanı" diğer yöntemleri arasında taşıma](../debugger/intellitrace.md) sırasında adında Bu performans olayı. [Bu diğer tüm olayları ve IntelliTrace günlük bilgileri nedir? ](../debugger/using-saved-intellitrace-data.md) [Buradan başka ne yapabilirim?](#WhatElse) [Performans olayları hakkında daha fazla bilgi edinmek istiyorsanız?](http://blogs.msdn.com/b/visualstudioalm/archive/2013/09/20/performance-details-in-intellitrace.aspx)  

### <a name="diagnose-an-exception"></a>Bir özel durumu tanıla  

1.  Altında **özel durum verileri**, kaydedilen özel durum olayları, türleri, iletileri gözden geçirin ve ne zaman özel durum oluştu. Kodu daha ayrıntılı incelemek için özel durumlar grubu içindeki en son olaydan başlayın.  

     ![Özel durum olayı hata ayıklamayı Başlat](../debugger/media/ffr_itsummarypageexception.png "FFR_ITSummaryPageException")  

     Ayrıca, olayı çift tıklatabilirsiniz.  

     Uygulama kodunuzda bir özel durum oluştuysa, Visual Studio özel durumun olduğu yere gider.  

     ![Git uygulama kodu bir özel durum olaydan](../debugger/media/ffr_itsummarypageexceptiongotocode.png "FFR_ITSummaryPageExceptionGoToCode")  

     Çağrı yığını kaydedilmiş diğer değerleri gözden geçirin veya kullanın artık **IntelliTrace** penceresine [geriye doğru veya ileten "zamanı" diğer kaydedilen olaylar arasında taşıma](../debugger/intellitrace.md), ilgili kod ve adresindeki kaydedilen değerler Bu puanları zaman. [Bu diğer tüm olayları ve IntelliTrace günlük bilgileri nedir?](../debugger/using-saved-intellitrace-data.md)  

###  <a name="WhatElse"></a>Buradan başka ne yapabilirim?  

-   [Bu kodu hakkında daha fazla bilgi almak](../ide/find-code-changes-and-other-history-with-codelens.md). Bu kod başvurularını bulmak için Düzenleyicisi'nde CodeLens göstergeleri değişiklik geçmişini, ilgili hatalar, iş öğelerini, kod incelemeleri veya birim testleri - tümü düzenleyiciden ayrılmadan - kullanın.  

     ![CodeLens &#45; Bu kod başvurularını görüntülemek](../debugger/media/ffr_itsummarypageperformancecodelensreferences.png "FFR_ITSummaryPagePerformanceCodeLensReferences")  

     ![CodeLens &#45; Görünümü değiştirmek için bu kodu geçmişini](../debugger/media/ffr_itsummarypageperformancecodelensauthors.png "FFR_ITSummaryPagePerformanceCodeLensAuthors")  

-   [Hatalarını ayıkladığınız sırada, kod yerinde eşleyin.](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md) Hata ayıklama sırasında aranan yöntemleri görsel izlemek için çağrı yığınını eşleyin.  

     ![Hata ayıklarken çağrı yığınında eşleştirme](../debugger/media/ffr_itsummarypageperformancedebuggermap.png "FFR_ITSummaryPagePerformanceDebuggerMap")  

###  <a name="FAQ"></a>SORU- CEVAP  

####  <a name="WhyInclude"></a>S: neden proje, kaynak denetimi, yapı ve simgeleri my sürüm ile ilgili bilgileri içerir?  
 Visual Studio hata ayıklama çalıştığınız sürüm için eşleşen çözüm ve kaynak bulmak için bu bilgileri kullanır. IntelliTrace günlüğünü açın ve hata ayıklamayı başlatmak için bir olay seçin sonra Visual Studio simgeleri bulmak ve olay yapıldığı kodunu göstermek için kullanır. Sonra kaydedilen değerlere göz ve İleri ya da geri, kodun yürütme taşıyın.  

 TFS ve bu bilgileri kullanıyorsanız değil derleme bildirimi (BuildInfo.config dosyası), Visual Studio, şu anda bağlı TFS üzerindeki simgelerin ve eşleşen kaynak arar. Visual Studio doğru TFS veya eşleşen kaynak bulamazsanız, farklı bir TFS seçin istenir.  

####  <a name="InvalidConfigFile"></a>S: IntelliTrace günlük dağıtılan Uygulamam hakkında bilgiler eksik. Bunun nedeni? Ne yapmam gerekir?  
 Dağıtım sırasında TFS bağlı değilseniz veya geliştirme bilgisayarınızdan dağıttığınızda gerçekleşebilir.  

1.  Projenizin dağıtım klasörüne gidin.  

2.  Bul ve derleme bildirimi (BuildInfo.config dosyası) açın.  

3.  Gerekli bilgileri dosyası olduğundan emin olun:  

-   **ProjectName**  

     Visual Studio, projenizin adı. Örneğin:  

    ```  
    <ProjectName>FabrikamFiber.Extranet.Web</ProjectName>  
    ```  

-   **SourceControl**  

-   Kaynak Denetim sisteminiz ve bunlar hakkında bilgi özellikleri gerekli:  

    -   **TFS**  

        -   **ProjectCollectionUri**: Team Foundation Server ve project koleksiyonunuz için URI  

        -   **ProjectItemSpec**: uygulamanızın proje dosyası (.csproj veya .vbproj) yolu  

        -   **ProjectVersionSpec**: projeniz için yeni sürümü  

         Örneğin:  

        ```  
        <SourceControl type="TFS">  
           <TfsSourceControl>  
              <ProjectCollectionUri>http://fabrikamfiber:8080/tfs/FabrikamFiber</ProjectCollectionUri>  
              <ProjectItemSpec>$/WorkInProgress/FabrikamFiber/FabrikamFiber.CallCenter/FabrikamFiber.Web/FabrikamFiber.Web.csproj</ProjectItemSpec>  
              <ProjectVersionSpec>LFabrikamFiber_BuildAndPublish_20130813@$/WorkInProgress</ProjectVersionSpec>  
           </TfsSourceControl>  
        </SourceControl>  
        ```  

    -   **Git**  

        -   **GitSourceControl**: konumunu **GitSourceControl** şeması  

        -   **RepositoryUrl**: Team Foundation Server, projesi koleksiyonu ve Git deposu için URI  

        -   **ProjectPath**: uygulamanızın proje dosyası (.csproj veya .vbproj) yolu  

        -   **CommitId**:, yürütme kimliği  

         Örneğin:  

        ```  
        <SourceControl type="Git">   
           <GitSourceControl xmlns="http://schemas.microsoft.com/visualstudio/deploymentevent_git/2013/09">  
              <RepositoryUrl>http://gittf:8080/tfs/defaultcollection/_git/FabrikamFiber</RepositoryUrl>  
              <ProjectPath>/FabrikamFiber.CallCenter/FabrikamFiber.Web/FabrikamFiber.Web.csproj</ProjectPath>  
              <CommitId>50662c96502dddaae5cd5ced962d9f14ec5bc64d</CommitId>  
           </GitSourceControl>  
        </SourceControl>  
        ```  

-   **Derleme**  

     Derleme sisteminiz hakkında bilgi ya da `"TeamBuild"` veya `"MSBuild"`, ve bunlar gerekli özellikleri:  

    -   **BuildLabel** (için TeamBuild): derleme adı ve numarası. Bu etiket de dağıtım olay adı olarak kullanılır. Yapı numaraları hakkında daha fazla bilgi için bkz: [kullanılan yapı numaraları için tamamlanan yapıları anlamlı adlar verin](http://msdn.microsoft.com/Library/1f302e9d-4b0a-40b5-8009-b69ca6f988c3).  

    -   **SymbolPath** (önerilen): URI listesi simgeler (PDB dosyası) konumlarınıza için noktalı virgülle ayrılmış. Bu URI URL'leri veya UNC olabilir. Bu hata ayıklamaya yardımcı olmak için eşleşen simgeleri bulmak Visual Studio için kolaylaştırır.  

    -   **BuildReportUrl** (için TeamBuild): TFS yapı raporda konumu  

    -   **Buildıd** (için TeamBuild): derleme için URI TFS'de ayrıntıları. Bu URI dağıtım olay kimliği olarak da kullanılır. Bu kimliği TeamBuild kullanmıyorsanız benzersiz olmalıdır gerekir.  

    -   **BuiltSolution**: Bu Visual Studio çözümü dosyasının yolunu kullanır bulup eşleşen çözümü açın. Bu içeriği olan **SolutionPath** MsBuild özelliği.  

     Örneğin:  

    -   **TFS**  

        ```  
        <Build type="TeamBuild">  
           <MsBuild>  
              <BuildLabel kind="label">FabrikamFiber_BuildAndPublish_20130813.1</BuildLabel>  
              <SymbolPath>\\fabrikamfiber\FabrikamFiber.CallCenter\Symbols</SymbolPath>  
              <BuildReportUrl kind="informative, url" url="http://fabrikamfiber:8080/tfs/FabrikamFiber/_releasePipeline/FindRelease?buildUri=fabrikamfiber%3a%2f%2f%2fBuild%2fBuild%2f448">Build Report Url</BuildReportUrl>  
              <BuildId kind="id">1c4444d2-518d-4673-a590-dce2773c7744,fabrikamfiber:///Build/Build/448</BuildId>  
              <BuiltSolution>$/WorkInProgress/FabrikamFiber/FabrikamFiber.CallCenter/FabrikamFiber.CallCenter.sln</BuiltSolution>  
           </MsBuild>  
        </Build>  
        ```  

    -   **Git**  

        ```  
        <Build type="MSBuild">   
           <MSBuild>  
              <SymbolPath>\\gittf\FabrikamFiber.CallCenter\Symbols</SymbolPath>  
              <BuiltSolution>/FabrikamFiber.CallCenter/FabrikamFiber.CallCenter.sln</BuiltSolution>  
           </MSBuild>  
        </Build>  
        ```  

####  <a name="IneligibleWorkspace"></a>S: neden Visual Studio seçilen çalışma Alanım uygun değil dediği?  
 **Y:** kaynak denetimi klasörü ve bir yerel klasör arasındaki eşlemeleri seçilen çalışma alanı yok. Bu çalışma alanı için bir eşleme oluşturmak için seçtiğiniz **Yönet**. Aksi halde, zaten eşleşmiş bir çalışma alanı seçin veya yeni bir çalışma alanı oluşturun.  

 ![Eşlenen çalışma alanı ile kaynak denetiminden Aç](../debugger/media/ffr_openprojectfromsourcecontrol_notmapped.png "FFR_OpenProjectFromSourceControl_NotMapped")  

####  <a name="ChooseTeamProject"></a>Neden bir takım veya farklı bir koleksiyon seçene kadar ı devam edemiyor?  
 **Y:** şu nedenlerden biriyle gerçekleşebilir:  

-   Visual Studio TFS'ye bağlı değildir.  

     ![Açık kaynak denetiminden &#45; bağlı](../debugger/media/ffr_openprojectfromsourcecontrol_notconnected.png "FFR_OpenProjectFromSourceControl_NotConnected")  

-   Visual Studio geçerli takım koleksiyonunuzda çözüm ya da proje bulamadı.  

     Ne zaman yapı bildirim dosyası (\<*ProjectName*>. BuildInfo.config) değil belirtin Visual Studio eşleşen kaynak bulabileceğiniz Visual Studio eşleşen çözüm ya da proje bulmak için şu anda bağlı TFS kullanır. Geçerli takım koleksiyonunuzda eşleşen kaynak yoksa, Visual Studio farklı takım koleksiyonuna bağlanmanızı ister.  

-   Visual Studio kaydetmedi Bul çözüm ya da projeyi derleme bildirim dosyasında belirtilen koleksiyondaki (\<*ProjectName*>. BuildInfo.config).  

     Belirtilen TFS artık eşleşen kaynağa sahip olmayabilir, hatta yeni bir TFS'ye geçtiğiniz için hiç varolmayabilir. Belirtilen TFS mevcut değilse Visual Studio bir dakika ya da sonrasında zaman aşımına uğrayabilir ve bu durumda sizden farklı bir koleksiyona bağlanmanız istenebilir. Devam etmek için doğru TFS sunucusuna bağlanın.  

     ![Açık kaynak denetiminden &#45; geçirilen](../debugger/media/ffr_openprojectfromsourcecontrol_migrated.png "FFR_OpenProjectFromSourceControl_Migrated")  

####  <a name="WhatWorkspace"></a>S: bir çalışma alanı nedir?  
 **Y:** , [çalışma kaynak bir kopyasını depolar](http://msdn.microsoft.com/Library/1d7f6ed8-ec7c-48f8-86da-9aea55a90d5a) geliştirmek ve ayrı olarak önce onay çalışmanızı test. Bulunan çözümle veya projeyle özel olarak eşleşen bir çalışma alanı yoksa, Visual Studio varsayılan çalışma alanı adı olarak bilgisayar adınızla birlikte yeni bir çalışma alanı oluşturmanızı veya mevcut bir çalışma alanı seçmenizi ister.  

####  <a name="UntrustedSymbols"></a>S: Bu ileti güvenilmeyen simgeler hakkında neden alıyorum?  
 ![Güvenilmeyen simge yolu ile hata ayıklama? ] (../debugger/media/ffr_ituntrustedsymbolpaths.png "FFR_ITUntrustedSymbolPaths")  

 **Y:** ne zaman bu ileti görünür derleme bildirim dosyasında simge yolu (\<*ProjectName*>. BuildInfo.config) güvenilen simgesi yolları listesine dahil değil. Hata ayıklama seçeneklerindeki sembol yolu listesine yolu ekleyebilirsiniz.
