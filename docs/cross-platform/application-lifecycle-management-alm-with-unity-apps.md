---
title: "Unity uygulamaları ile uygulama yaşam döngüsü yönetimi (ALM) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dc61e63-9ba2-4c16-b1ad-f46249e576b6
caps.latest.revision: "12"
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload: unity
ms.openlocfilehash: 4e68024333084b6166305266dd061ef32bc0e14a
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="application-lifecycle-management-alm-with-unity-apps"></a>Unity Uygulamaları ile Uygulama Yaşam Döngüsü Yönetimi (ALM)
Modern platformlar için uygulama geliştirme yeni kod yazma daha pek çok daha fazla etkinlik içerir. Bu etkinlikler başvurulan için DevOps (geliştirme + işlemleri) uygulamanın tam yaşam döngüsü span ve planlama ve iş izleme, tasarlama ve kod, uygulama bir kaynak kod deposu yönetme derlemeleri, çalışan sürekli tümleştirmeler yönetme içerir dağıtımlar, test (dahil, birim testleri ve UI testleri) tanılama çeşitli biçimlerde hem geliştirme hem de üretim ortamlarında çalışan ve uygulama performansı ve kullanıcı davranışlarını telemetri ve analiz ile gerçek zamanlı izleme.  

 Visual Studio Team Services ve Team Foundation Server ile birlikte Visual Studio uygulama yaşam döngüsü yönetimi veya ALM da bilinir DevOps özellikleri, çeşitli sağlar. Bunların çoğu oyunları ve Unity ile oluşturulan derinlikli grafik uygulamalar dahil olmak üzere, platformlar arası projeleri için geçerli olan — özellikle kullanarak C# bir komut dosyası dili. Ancak, Unity kendi geliştirme ortamı ve çalışma zamanı altyapısı olduğundan, diğer türde Visual Studio'da oluşturulmuş projeler için yaptıkları gibi çok sayıda ALM özelliği uygulanmaz.  

 Aşağıdaki tablolarda, Visual Studio ALM özellikleri nasıl uygulamak veya Unity ile çalışırken, uygulama tanımlar. Özellikleri hakkında ayrıntılı bilgi için bağlantılı belgelerine bakın.  

## <a name="agile-tools"></a>Çevik Araçlar  
 Başvuru bağlantısı:  **[iş](http://msdn.microsoft.com/Library/52aa8bc9-fc7e-4fae-9946-2ab255ca7503)**  (Visual Studio Team Services veya TFS Takım Gezgini her yerde dahil olmak üzere, kullanarak)  

 Genel Açıklama: tüm planlama ve izleme özellikleri proje türüne ve dilleri kodlama bağımsızdır.  

|Özellik|Unity ile desteklenen|Ek Açıklamalar|  
|-------------|--------------------------|-------------------------|  
|Biriktirme listelerini ve sprint yönetme|Evet||  
|İş izleme|Evet||  
|Takım odası işbirliği|Evet||  
|Kanban Panosu|Evet||  
|Rapor ve ilerlemeyi Görselleştirme|Evet||  

## <a name="modeling"></a>Modelleme  
 Başvuru bağlantısı:  **[çözümleme ve modelleme mimarisi](../modeling/analyze-and-model-your-architecture.md)**  

 Genel Açıklama: Bu tasarım özellikleri dil kodlama ya da bağımsız olduğundan veya C# .NET dilleri ile çalışır, ancak bunlar geleneksel uygulama kip nesne hiyerarşileri ve sınıf ilişkileri çalışmayabilir. Unity içinde oyun tasarımında gerekir farklı bir standardı tamamen, yani ilişkilerini grafik nesneleri, ses, gölgelendiriciler, betikler ve benzeri. Bu nedenle, diyagram modelleme Visual Studio Araçları Unity projenin bütün özellikle ilgili değildir. C# betiklerini içindeki ilişkileri yönetmek için büyük olasılıkla kullanılabilir, ancak tüm yalnızca bir parçası olan.  

|Özellik|Unity ile desteklenen|Ek Açıklamalar|  
|-------------|--------------------------|-------------------------|  
|Sıralı diyagramlar|Hayır||  
|Bağımlılık grafikleri|Hayır||  
|Çağrı hiyerarşisi|Hayır||  
|Sınıf Tasarımcısı|Hayır||  
|Mimari Gezgini|Hayır||  
|UML diyagramları (çalışması, etkinlik, sınıf, bileşen, dizisi ve DSL kullanın)|Hayır||  
|Katman diyagramları|Hayır||  
|Katman doğrulaması|Hayır||  

## <a name="code"></a>Kod  

|Özellik|Unity ile desteklenen|Ek Açıklamalar|  
|-------------|--------------------------|-------------------------|  
|[Team Foundation sürüm denetimini kullanma](http://msdn.microsoft.com/Library/1d629052-c65d-4c5d-81eb-eaa4413fe285) veya Visual Studio Team Services|Evet|Unity projeleri yalnızca sürüm denetim sistemleri gibi başka bir projeye içine yerleştirilebilir dosyaları koleksiyonu olan, ancak sonra bu tabloda açıklandığı gibi bazı özel durumlar vardır.|  
|[Git Team Services ile çalışmaya başlama](http://msdn.microsoft.com/Library/32f46ecd-1b03-4ef0-a9c4-8a120da2b03f)|Evet|Tablodan sonra notlarına bakın.|  
|[Kod Kalitesini Geliştirme](/visualstudio/test/improve-code-quality)|Evet||  
|[Kod değişikliklerini ve diğer geçmişi bulma](../ide/find-code-changes-and-other-history-with-codelens.md)|Evet||  
|[Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma](../modeling/use-code-maps-to-debug-your-applications.md)|Evet||  

 Sürüm denetimi ile Unity için özel hususlar:  

1.  Varsayılan olarak gizlidir opak, tek bir Kitaplığı'nda Oyun varlıkları hakkında meta veri bütünlüğünü izler. Dosyaları ve meta verileri eşitlenmiş tutmak için bu meta veriler görünür hale getirmek için ve daha fazlasını yönetilebilir yığınlar halinde depolamak için gereklidir. Ayrıntılar için başvurmak [kullanarak dış sürüm denetim sistemleri Unity ile](http://docs.unity3d.com/Manual/ExternalVersionControlSystemSupport.html) (Unity belge).  

2.  Tüm dosya ve klasörleri Unity projesinde yukarıdaki bağlantıyı de açıklandığı gibi kaynak denetimi için uygundur. Varlıklar ve ProjectSettings klasörleri eklenmesi gerekir, ancak kitaplığı ve Temp klasörleri kullanmamalıdır. Tartışma kaynak denetimine geçmeyecek oluşturulan dosyaların ek bir listesi için bkz: [Unity3D kaynak denetimi için Git kullanmayı?](http://stackoverflow.com/questions/18225126/how-to-use-git-for-unity3d-source-control) StackOverflow üzerinde. Birçok geliştiriciler ayrıca blogged bu konuda bağımsız olarak vardır.  

3.  Unity projesinde ikili varlıklar — dokuları ya da ses dosyaları gibi — büyük miktarda depolama alabilir. Değişiklik dosyasının yalnızca küçük bir bölümünü etkiler olsa bile Git gibi çeşitli kaynak denetim sistemleri bir dosya yapılır, her değişiklik için benzersiz bir kopyasını saklar. Bu, Git deposu bloated hale gelmesine neden olabilir. Bu sorunu çözmek için Unity geliştiriciler genellikle yalnızca son varlıklar için kendi deposunu ekleyin ve OneDrive, DropBox veya git annex varlıklarına çalışma geçmişini tutmayı farklı bir yol kullanmak seçin. Bu tür varlıklar genellikle kaynak kod değişiklikleri birlikte sürümlü olması gerekmediği için bu yaklaşım çalışır. Geliştiriciler proje Düzenleyicisi'nin varlık serileştirme modunu zorla metne birleştirmeler kaynak denetiminde izin veren ikili biçimi yerine metin Sahne dosyaları depolamak için de genellikle ayarlayın. Ayrıntılar için bkz [Düzenleyici ayarları](http://docs.unity3d.com/Manual/class-EditorManager.html) (Unity belge).  

## <a name="build"></a>Derleme  
 Başvuru bağlantısı:  **[derleme ve sürüm](/vsts/build-release/index)**  

|Özellik|Unity ile desteklenen|Ek Açıklamalar|  
|-------------|--------------------------|-------------------------|  
|Şirket içi TFS sunucusu|Olası|Unity projeleri Unity ortamı üzerinden yerleşiktir ve aracılığıyla Visual Studio oluşturma sistemi (Visual Studio Araçları içinde Unity komut dosyalarını derlemek ancak yürütülebilir bir dosya üretmez oluşturma). İçin mümkündür [Unity projeleri komut satırından derleme](http://docs.unity3d.com/Manual/CommandLineArguments.html) (Unity belge), Unity kendisini yüklenmiş olması koşuluyla, bir MSBuild işlemi uygun Unity yürütmek için TFS sunucusunda yapılandırmak mümkün, komutları için Bu bilgisayar.<br /><br /> Unity sunduğu [Unity bulut yapı](https://build.cloud.unity3d.com/landing/), Git veya SVN deposu izler ve düzenli çalıştırır oluşturur. Şu anda, Team Foundation sürüm denetimi veya Visual Studio Team Services ile çalışmaz.|  
|Visual Studio Team Services bağlantılı sunucu şirket içi derleme|Olası|Aynı koşullarda, daha fazla Visual Studio Team bir şirket içi TFS bilgisayarını kullanmayı Services tetiklenen derlemeleri yönlendirmek mümkündür.  Bkz: [derleme ve sürüm aracıları](/vsts/build-release/concepts/agents/agents) yönergeler için.|  
|Visual Studio Team Services barındırılan denetleyicisi hizmeti|Hayır|Unity derlemeleri şu anda desteklenmiyor.|  
|Yapı tanımlarla öncesi ve sonrası betikleri|Evet|Unity komut satırı derleme çalıştırmak için kullandığı bir özel derleme tanımı öncesi ve sonrası betikler için de yapılandırılabilir.|  
|Sürekli tümleştirme de dahil olmak üzere iadeler geçişli|Evet|Yalnızca Git iadeler yerine bir çekme isteği modeli çalışırken iadeler TFVC'yi için geçişli.|  

## <a name="testing"></a>Sınama

|Özellik|Unity ile desteklenen|Ek Açıklamalar|  
|-------------|--------------------------|-------------------------|  
|Test paketleri testleri planlama, test çalışmaları oluşturma ve düzenleme|Evet||  
|El ile test etme|Evet||  
|Test Yöneticisi'ni (kaydı ve kayıttan yürütme testleri)|Windows cihazlar ve yalnızca Android öykünücüsünü||  
|Kod kapsamı|yok|Birim olarak uygulanamaz sınama Unity ve değil Visual Studio içinde gerçekleşir, aşağıya bakın.|  
|[Kodunuza Birim Testi Uygulama](../test/unit-test-your-code.md)|Unity ancak değil Visual Studio içinde|Unity sağlar, kendi birim testi çerçevesini parçası olarak [Unity Test Araçları](https://www.assetstore.unity3d.com/en/#!/content/13802) (Unity varlık deposu). Birim testi sonuçları Unity içinde bildirilen ve Visual Studio içinde ortaya değil.|  
|[Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](../test/use-ui-automation-to-test-your-code.md)|Hayır|Kodlanmış UI testleri uygulamanın kullanıcı arabiriminde okunabilir denetimleri kullanır; Unity uygulamaları doğası gereği grafik ve bu nedenle içeriği kodlanmış UI test araçları tarafından okunabilir değil.|  

## <a name="improve-code-quality"></a>Kod kalitesini geliştirme

Başvuru bağlantısı:  **[kod kalitesini geliştirmek](/visualstudio/test/improve-code-quality)**  

|Özellik|Unity ile desteklenen|Ek Açıklamalar|  
|-------------|--------------------------|-------------------------|  
|[Yönetilen kod kalitesini analiz etme](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)|Evet|Visual Studio içinde C# betik kodu analiz edebilirsiniz.|  
|[Kod kopyası algılamayı kullanarak yinelenen kodları bulma](http://msdn.microsoft.com/Library/a97cd5a6-5ffa-4104-9627-8e59e513654d)|Evet|Visual Studio içinde C# betik kodu analiz edebilirsiniz.|  
|[Yönetilen Kodun Ölçüm Karmaşıklığı ve Bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)|Evet|Visual Studio içinde C# betik kodu analiz edebilirsiniz.|  
|[Performans Gezgini](../profiling/performance-explorer.md)|Hayır|Kullanım [Unity profil oluşturucu](http://docs.unity3d.com/Manual/Profiler.html) (Unity Web sitesi).|  
|[.NET Framework bellek sorunlarını çözümleme](https://msdn.microsoft.com/en-us/library/dn342825.aspx)|Hayır|Visual Studio Araçları profil oluşturma için Mono framework (olarak Unity tarafından kullanılan) içine kancaları gerekmez. Kullanım [Unity profil oluşturucu](http://docs.unity3d.com/Manual/Profiler.html) (Unity belge).|  

## <a name="release-management"></a>Yayın yönetimi  
 Başvuru bağlantısı:  **[yayın yönetimi ile dağıtımları otomatikleştirme](https://msdn.microsoft.com/library/vs/alm/release/overview)**  

|Özellik|Unity ile desteklenen|Ek Açıklamalar|  
|-------------|--------------------------|-------------------------|  
|Yayın işlemlerini yönetme|Evet||  
|Dağıtım için dışarıdan yükleme komut dosyaları aracılığıyla sunucularına|Evet||  
|Uygulama deposuna karşıya yükleme|Kısmi|Uzantıları mevcut bazı uygulama depoları için bu işlemi otomatikleştirmek.  Bkz: [Visual Studio Team Services uzantıları](https://marketplace.visualstudio.com/VSTS); Örneğin, [Google Play için uzantı](https://marketplace.visualstudio.com/items?itemName=ms-vsclient.google-play).|  

## <a name="monitor-with-hockeyapp"></a>HockeyApp izleme  
 Başvuru bağlantısı:  **[HockeyApp izlemesi](https://www.hockeyapp.net/features/)**  

|Özellik|Unity ile desteklenen|Ek Açıklamalar|  
|-------------|--------------------------|-------------------------|  
|Kilitlenme analizi, telemetri ve beta dağılımı|Evet|HockeyApp beta dağılımı işleme ve kilitlenme raporları elde etmek için özellikle yararlıdır.<br /><br /> C# komut dosyalarından telemetri için koşuluyla Unity tarafından kullanılan .NET sürümünü çalıştıran tüm analytics framework kullanmak da mümkündür. Ancak, bu yalnızca oyun komut dosyaları içinde ve Unity altyapısı içinde değil daha kapsamlı analizi sağlar. Şu anda hiçbir eklentisi için Application Insights yoktur, ancak diğer analiz çözümleri için kullanılabilir gibi olan eklentileri [Unity Analytics](https://www.assetstore.unity3d.com/en/#!/content/28120) ve [Google Analytics](https://github.com/googleanalytics/google-analytics-plugin-for-unity). Unity proje yapısını anlamak Unity analiz eder, doğal olarak, gibi hizmetleri genel çerçeveleri daha çok daha anlamlı çözümleme sağlar.|
