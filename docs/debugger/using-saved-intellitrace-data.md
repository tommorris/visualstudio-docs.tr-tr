---
title: "Kullanılarak kaydedilen IntelliTrace verilerini | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.historicaldebug.norepro
helpviewer_keywords:
- iTrace files
- IntelliTrace, log files
- IntelliTrace log files
- .iTrace files
ms.assetid: 9f2cce86-345a-4e22-84ba-91542d81e67a
caps.latest.revision: "106"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 37c4c82dc3edb1abcad9dc212040864155deb1a6
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="using-saved-intellitrace-data"></a>Kaydedilen IntelliTrace verilerini kullanma
Uygulamanızın yürütme belirli noktalara bir IntelliTrace günlüğü (.iTrace) dosyasından hata ayıklamayı başlattığınızda gidin. Bu dosya, performans olaylarının, özel durumlar, iş parçacıkları, test adımları, modüller ve IntelliTrace kayıtları uygulama çalışmalarınız while diğer sistem bilgisi içerebilir.  
  
 Bilgisayarınızda yüklü olduğundan emin olun:  
  
-   Eşleşen kaynak dosyalar ve uygulama kodunuz için simge (.pdb) dosyaları. Aksi takdirde, Visual Studio kaynak konumları çözümlenemiyor ve "simgeleri bulunamadı." iletisi gösterir Bkz: [belirtin simge (.pdb) ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md) ve [dağıtımdan sonra sorunları tanılama](../debugger/diagnose-problems-after-deployment.md).  
  
-   Visual Studio .iTrace dosyaları açmaya Enterprise (ancak değil Professional veya topluluk sürümleri) geliştirme bilgisayarınızda veya başka bir bilgisayar  
  
-   Bu kaynaklardan birinden .iTrace dosyası:  
  
    |**Kaynak**|**Bkz:**|  
    |----------------|-------------|  
    |Bir IntelliTrace oturumda Visual Studio Enterprise (ancak değil Professional veya topluluk sürümleri)|[IntelliTrace özellikleri](../debugger/intellitrace-features.md)|  
    |Microsoft Test Yöneticisi'nde bir test oturumu. Bu, Team Foundation Server iş öğesine .iTrace dosyayı iletiye ekler.|[El ile testlerde daha fazla tanılama verisi toplama](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)|  
    |Microsoft Monitoring Agent, ya da tek başına veya System Center 2012 R2 Operations Manager ile için ASP.NET uygulamaları ve SharePoint uygulamaları dağıtımında çalışan web|-   [Dağıtımdan sonra sorunları tanılama](../debugger/diagnose-problems-after-deployment.md)<br />-   [System Center 2012 R2 Operations Manager için Yenilikler](http://technet.microsoft.com/library/dn249700.aspx)|  
  
##  <a name="GetStarted"></a>Ne yapmak istiyorsunuz?  
  
-   [Bir IntelliTrace günlüğü'nü açın](#Open)  
  
-   [IntelliTrace günlüğünü anlama](#Understand)  
  
-   [Bir IntelliTrace günlüğü'nden hata ayıklamayı Başlat](#StartDebugging)  
  
##  <a name="Open"></a>Bir IntelliTrace günlüğü'nü açın  
 Visual Studio Enterprise olan bir bilgisayarda .iTrace dosyasını açın.  
  
-   Visual Studio dışında .iTrace dosyasını çift tıklatın veya dosyayı açmak Visual Studio içinde.  
  
     \-veya -  
  
-   .İTrace dosyasının Team Foundation Server iş öğesine bağlı olduğundan, iş öğesi şu adımları izleyin:  
  
    -   Altında **tüm bağlantılar**, .iTrace dosyasını bulun. Açın.  
  
         \-veya -  
  
    -   Altında **yeniden oluşturma adımları**, seçin **IntelliTrace** bağlantı.  
  
> [!TIP]
>  Hata ayıklama sırasında IntelliTrace dosyası kapattıysanız, bunu kolayca yeniden açabilirsiniz. Git **hata ayıklama** menüsünde seçin **IntelliTrace**, **günlük Özet Göster**. Ayrıca seçebilirsiniz **günlük Özet Göster** içinde **IntelliTrace** penceresi. Yalnızca IntelliTrace ile hata ayıklama sırasında bu kullanılabilir.  
  
##  <a name="Understand"></a>IntelliTrace günlüğünü anlama  
 Yalnızca, belirli bir kaynaktan, örneğin, Test Yöneticisi'nden veya SharePoint uygulamalardan toplanan veriler .iTrace dosyasında aşağıdaki bölümlerde bazıları görünür.  
  
|**Bölüm**|**İçerir**|**Toplama kaynağı**|  
|-----------------|------------------|---------------------------|  
|[Performans ihlalleri](#Performance)|Yapılandırılan Eşiği aşan işlev çağrılarını sahip performans olayları|Microsoft Monitoring Agent, her iki bağımsız veri toplayıcı veya System Center 2012 R2 Operations Manager IIS üzerinde barındırılan ASP.NET web uygulamaları ile|  
|[Özel durum verileri](#ExceptionData)|Her özel durum için tam çağrı yığınına dahil olmak üzere özel durumlar|Tüm kaynakları|  
|[Çözümleme](#Analysis)|Yalnızca SharePoint 2010 ve SharePoint 2013 uygulamalar için. Hata ayıklayıcı olayları, ULS olayları, İşlenmeyen özel durumlar ve Microsoft Monitoring Agent kaydedilen diğer veriler gibi IntelliTrace ve SharePoint olayları tanılayın.|Microsoft Monitoring Agent, her iki bağımsız veri toplayıcı veya System Center 2012 R2 Operations Manager ile|  
|[Sistem bilgisi](#SystemInfo)|Ayarları ve ana bilgisayar sistemi belirtimleri|Tüm kaynakları|  
|[İş parçacığı listesi](#ThreadsList)|Toplama sırasında çalışan iş parçacıkları|Tüm kaynakları|  
|[Test verileri](#TestData)|Test adımları ve sonuçları bir test oturumundan|Test Yöneticisi|  
|[Modüller](#Modules)|Hedef işlemin yüklendikleri sıraya yüklenen modüller.|Tüm kaynakları| 
|[Web isteği](#Modules)|Üretim IIS için Web isteği verisi web uygulamaları ve SharePoint 2010 ve SharePoint 2013|Microsoft izleme aracısı ve bağımsız veri toplayıcı| 
  
 Her bölümde bilgileri bulmanıza yardımcı olacak bazı ipuçları şöyledir:  
  
-   Verileri sıralamak için sütun başlığını seçin.  
  
-   Filtre verileri için arama kutusunu kullanın. Düz metin arama saat sütunları dışındaki tüm sütunları boyunca çalışır. Sütun başına bir filtre ile de aramaları belirli bir sütun için filtre uygulayabilirsiniz. Boşluk, iki nokta ile sütun adını yazın (**:**) ve arama değeri. Noktalı virgül izleyin (**;**) başka bir sütun ve arama değer eklemek için.  
  
     Örneğin, bulmak için Word'ün performans olayları "içinde yavaş" **açıklama** sütun, türü:  
  
     `Description:slow`  
  
##  <a name="StartDebugging"></a>Bir IntelliTrace günlüğü'nden hata ayıklamayı Başlat  
  
###  <a name="Performance"></a>Performans ihlalleri  
 Uygulamanız için kaydedilmiş bir performans olayları gözden geçirin. Genellikle durum yok olayları gizleyebilirsiniz.  
  
##### <a name="to-start-debugging-from-a-performance-event"></a>Bir performans olayı hata ayıklamayı başlatmak için  
  
1.  Altında **performans ihlallerinin**, kaydedilen performans olayları, toplam yürütme zamanları ve diğer olay bilgileri gözden geçirin. Sonra belirli performans olayı sırasında çağrılan yöntemlerde fazla araştırma yapın.  
  
     ![Performans olay ayrıntıları görüntüleyin](../debugger/media/ffr_itsummarypageperformance.png "FFR_ITSummaryPagePerformance")  
  
     Ayrıca, olayı çift tıklatabilirsiniz.  
  
2.  Olay sayfasında, bu çağrılar için yürütme zamanını gözden geçirin. Yürütme ağacında yavaş bir çağrı bulun.  
  
     İç içe ya da başka şekilde birden fazla çağrınız varsa, en yavaş çağrılar kendi bölümünde görüntülenir.  
  
3.  Çağrı gözden çağrılarını ve zamandaki o noktada kaydedilmiş bir parametre değerlerini içe genişletin.  
  
     (Klavye: göstermek veya iç içe geçmiş bir çağrı gizlemek için basın **sağ ok** veya **sol ok** sırasıyla anahtar. Gösterme ve gizleme iç içe geçmiş bir çağrı için parametre değerleri için basın **alanı** anahtar.)  
  
     Çağrısından hata ayıklamayı Başlat.  
  
     ![Yöntem çağrısının hata ayıklamayı Başlat](../debugger/media/ffr_itsummarypageperformancemethodscalled.png "FFR_ITSummaryPagePerformanceMethodsCalled")  
  
     Çağrı yalnızca çift tıklayarak veya basın **Enter** anahtarı.  
  
     Yöntem uygulama kodunuzda ise, Visual Studio bu yönteme gider.  
  
     ![Git uygulama kodu performans olaydan](../debugger/media/ffr_itsummarypageperformancegotocode.png "FFR_ITSummaryPagePerformanceGoToCode")  
  
     Çağrı yığını kaydedilmiş diğer değerleri gözden geçirebilirsiniz şimdi adım kodunuz veya kullanmak **IntelliTrace** penceresine [geriye doğru veya ileten "zamanı" diğer yöntemleri arasında taşıma](../debugger/intellitrace.md) sırasında adında Bu performans olayı.  
  
###  <a name="ExceptionData"></a>Özel durum verileri  
 Durum ve uygulamanız için kaydedilen özel durumları gözden geçirin. Aynı türde ve yalnızca en son istisnası görebilmesi için çağrı yığını özel durumların gruplayabilirsiniz.  
  
##### <a name="to-start-debugging-from-an-exception"></a>Bir özel durum hata ayıklamayı başlatmak için  
  
1.  Altında **özel durum verileri**, kaydedilen özel durum olayları, türleri, iletileri gözden geçirin ve ne zaman özel durum oluştu. Kodu daha ayrıntılı incelemek için özel durumlar grubu içindeki en son olaydan başlayın.  
  
     ![Özel durum olayı hata ayıklamayı Başlat](../debugger/media/ffr_itsummarypageexception.png "FFR_ITSummaryPageException")  
  
     Ayrıca, olayı çift tıklatabilirsiniz. Olayları gruplandırılmış olmayan kaldığınızda **hata ayıklama bu olay**.  
  
     Uygulama kodunuzda bir özel durum oluştuysa, Visual Studio özel durumun olduğu yere gider.  
  
     ![Git uygulama kodu bir özel durum olaydan](../debugger/media/ffr_itsummarypageexceptiongotocode.png "FFR_ITSummaryPageExceptionGoToCode")  
  
     Çağrı yığını kaydedilmiş diğer değerleri gözden geçirin veya kullanın artık **IntelliTrace** penceresine [geriye doğru veya ileten "zamanı" diğer kaydedilen olaylar arasında taşıma](../debugger/intellitrace.md), ilgili kod ve adresindeki kaydedilen değerler Bu puanları zaman.  
  
    |**Sütun**|**Gösterir**|  
    |----------------|-------------------|  
    |**Türü**|Özel durumun .NET türü|  
    |**Yeni ileti** gruplandırılmış özel durumlar veya **ileti** gruplanmamış özel durumları|Özel durum tarafından sağlanan ileti|  
    |**Count** gruplandırılmış özel durumlar|Özel durum sayısı|  
    |**İş parçacığı kimliği** gruplanmamış özel durumları|Özel durum oluşturdu iş parçacığı kimliği|  
    |**Yeni olay süresi** veya **olay süresi**|Ne zaman özel durumu zaman damgası kaydedilmiş|  
    |**Çağrı yığını**|İçin bir özel durum çağrı yığını.<br /><br /> Çağrı yığını görmek için bir özel durum listesinden seçin. Çağrı yığını özel durum listenin altında görüntülenir.|  
  
###  <a name="Analysis"></a>Çözümleme  
 Bir SharePoint bağıntı kimliği'ni kullanarak SharePoint 2010 ve SharePoint 2013 uygulamalarla sorunları tanılamak veya Microsoft İzleme Aracısı bulunan işlenmeyen özel durumlar gözden geçirin.  
  
-   Bir SharePoint bağıntı kimliği eşleşen web isteği ve olayları bulmak için kullanın. Bir olay seçin ve bir noktada hata ayıklamayı Başlat nerede ve ne zaman olayı oluştu.  
  
-   Microsoft Monitoring Agent işlenmeyen özel durumlar bulunamadı, bir özel durum'yı seçerseniz ve noktasında hata ayıklamayı Başlat nerede ve ne zaman özel durum oluştu.  
  
##### <a name="start-debugging-with-a-sharepoint-correlation-id"></a>SharePoint bağıntı kimliği ile hata ayıklamayı başlat  
  
1.  SharePoint bağıntı kimliği kaynağından kopyalayın.  
  
     Örneğin:  
  
     ![IntelliTrace &#45; SharePoint hatası &#45; Bağıntı Kimliği](../debugger/media/sharepointerror_intellitrace.png "SharePointError_IntelliTrace")  
  
2.  .İTrace dosyasını açın ve gidin **analiz** eşleşen web isteğini gözden geçirmek için SharePoint bağıntı kimliği girin ve olayları kaydedilir.  
  
     ![IntelliTrace günlük &#45; SharePoint bağıntı kimliği girin](../debugger/media/entersharepointcorrelationid.png "EnterSharePointCorrelationID")  
  
3.  Altında **isteği olayları**, olayları inceleyin. En üstten başlayarak, olayları bunlar oldu sırada görünür.  
  
    1.  Ayrıntılarını görmek için bir olay seçin.  
  
    2.  Seçin **hata ayıklamayı Başlat** olay yapıldığı noktasında hata ayıklama başlatılamıyor.  
  
     ![IntelliTrace günlük dosyası &#45; Web isteği &#43;görüntüleyin; olayları](../debugger/media/entersharepointcorrelationid2.png "EnterSharePointCorrelationID2")  
  
 Bu tür SharePoint olaylarının IntelliTrace olayları birlikte görebilirsiniz:  
  
-   **Kullanıcı profili olayları**  
  
     Bu olaylar, SharePoint bir kullanıcı profili yüklendiğinde ve kullanıcı profili özellikleri okuma ya da değiştirilmiş gerçekleşir.  
  
-   **Birleşik Günlük sistem (ULS) olayları**  
  
     Microsoft Monitoring Agent SharePoint ULS olayları ve bu alanlar bir alt kümesini kaydeder:  
  
    |**IntelliTrace alan**|**SharePoint ULS alan**|  
    |----------------------------|------------------------------|  
    |**Kimliği**|**Olay Kimliği**|  
    |**Düzeyi**|**Düzeyi**|  
    |**Kategori Kimliği**|**Kategori Kimliği**|  
    |**Kategori**|**Kategori**|  
    |**Alan**|**Ürün**|  
    |**Output**|**İleti**|  
    |**Bağıntı Kimliği**|**Bağıntı Kimliği**|  
  
##### <a name="start-debugging-from-an-unhandled-exception"></a>İşlenmemiş bir özel durumdan hata ayıklamayı başlat  
  
1.  Bir özel durum için bir SharePoint bağıntı kimliği seçin. Özel durumlar türüne göre gruplandırılır ve çağrı yığını.  
  
2.  (İsteğe bağlı) Genişletme **çağrı yığını** bir grubu özel durumlar için çağrı yığını görmek için.  
  
3.  Seçin **hata ayıklama özel durum** noktasında hata ayıklamayı başlatmak için nerede ve ne zaman özel durum oluştu.  
  
     ![IntelliTrace günlük &#45; SharePoint işlenmeyen özel durumlar](../debugger/media/sharepointunhandledexceptions_intellitrace.png "SharePointUnhandledExceptions_IntelliTrace")  
  
 İçin bkz [izlenecek yol: bir SharePoint uygulaması kullanarak IntelliTrace ile hata ayıklama](../sharepoint/walkthrough-debugging-a-sharepoint-application-by-using-intellitrace.md). Aracı kayıtlarını bkz veri türleri için [IntelliTrace özellikleri](../debugger/intellitrace-features.md).  
  
###  <a name="ThreadsList"></a>İş parçacığı listesi  
 Hedef işlemde çalışan kayıtlı iş parçacıklarının inceleyin. Seçili bir iş parçacığı ilk geçerli IntelliTrace olayı gelen hata ayıklama başlatabilirsiniz.  
  
##### <a name="to-start-debugging-from-a-specific-thread"></a>Belirli bir iş parçacığından hata ayıklamayı başlatmak için  
  
1.  Altında **iş parçacıklarının listesi**, bir iş parçacığı seçin.  
  
2.  Ekranın alt kısmındaki **iş parçacıklarının listesi**, seçin **hata ayıklamayı Başlat**. Ayrıca, bir iş parçacığı çift tıklatabilirsiniz.  
  
     Uygulama başladığı hata ayıklamayı başlatmak için çift **ana iş parçacığı**. Bkz: [IntelliTrace özellikleri](../debugger/intellitrace-features.md).  
  
 Kullanıcının oluşturduğu iş parçacığı veri bir sunucu oluşturur ve IIS tarafından barındırılan Web uygulamaları için yöneten iş parçacıkları daha kullanışlı olabilir.  
  
|**Sütun**|**Gösterir**|  
|----------------|-------------------|  
|**KİMLİĞİ**|İş parçacığı kimliği numarasını|  
|**Ad**|İş parçacığı adı. Adlandırılmamış iş parçacığı görünür olarak "\<ad >".|  
|**Başlangıç zamanı**|İş parçacığı oluşturulduğu zaman|  
|**Bitiş saati**|İş parçacığı tamamlandığı zaman|  
  
###  <a name="TestData"></a>Test verileri  
 Test Yöneticisi'ni uygulamanızı test ederken kaydedilen IntelliTrace verilerini inceleyin.  
  
##### <a name="to-start-debugging-from-a-specific-test-step"></a>Belirli test adımından hata ayıklamayı başlatmak için  
  
1.  Genişletme **Test adımları kılavuz**. Bir test adımı seçin.  
  
2.  Ekranın alt kısmındaki **Test adımları kılavuz**, seçin **hata ayıklamayı Başlat**. Ayrıca, bir test adımı çift tıklatabilirsiniz.  
  
     Bu, seçilen test adımdan sonra ilk geçerli IntelliTrace etkinlikten hata ayıklama başlatır.  
  
     Test verileri mevcut olduğunda, IntelliTrace testi gerçekleştirmek için kullanılan ilişkili Team Foundation Server yapı çözümlemeye çalışır. Yapı bulunursa, ilişkili uygulama simgelerini otomatik olarak çözümlenir.  
  
|**Alan**|**Gösterir**|  
|---------------|-------------------|  
|**Sınama oturumu**|Kaydedilmiş oturumları sınayın. Genellikle, yalnızca bir olduğundan. Bu liste, test verileri el ile bir keşif testi kullanılarak oluşturulduysa boştur.|  
|**Test çalışması**|Test çalışmaları seçili test oturumundan. Bu liste, test verileri el ile bir keşif testi kullanılarak oluşturulduysa boştur.|  
|**Test adımları kılavuz**|Test geçişi test sonucu ile kaydedilmiş adımları veya başarısız|  
  
###  <a name="SystemInfo"></a>Sistem bilgisi  
 Bu bölümde, uygulama örneğin barındırılan sistem, donanım, işletim sistemi, ortam ve işleme özgü bilgileri ilgili ayrıntıları gösterir.  
  
###  <a name="Modules"></a>Modülleri  
 Bu bölümde, hedef işlem yüklenen modülleri gösterir. Modülleri yüklendikleri sıraya göre görünür.  
  
|**Sütun**|**Gösterir**|  
|----------------|-------------------|  
|**Modül adı**|Modül dosyası adı|  
|**Modül yolu**|Disk konumu modülü burada yüklendi|  
|**Modül kimliği**|Sürüme özgü ve eşleşen simge (PDB) dosyalarını katkı modülü benzersiz tanımlayıcısı. Bkz: [simge (.pdb) dosyaları ve kaynak dosyaları bulma](http://msdn.microsoft.com/en-us/05384c85-d264-4e18-abaa-aa482ab25470).|  
  
### <a name="where-can-i-get-more-information"></a>Daha fazla bilgiyi nereden bulabilirim?  
 [IntelliTrace tek başına toplayıcıyı kullanma](../debugger/using-the-intellitrace-stand-alone-collector.md)  
  
 [IntelliTrace özellikleri](../debugger/intellitrace-features.md)  
  
 [El ile testlerde daha fazla tanılama verisi toplama](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)  
  
 [IntelliTrace](../debugger/intellitrace.md)  
  
#### <a name="forums"></a>Forumlar  
 [Visual Studio hata ayıklayıcısı](http://go.microsoft.com/fwlink/?LinkId=262263)  
  
#### <a name="guidance"></a>Kılavuz  
 [Visual Studio 2012 - Bölüm 6 ile sürekli teslimat için test etme: Test araç kutusu](http://go.microsoft.com/fwlink/?LinkID=255203)