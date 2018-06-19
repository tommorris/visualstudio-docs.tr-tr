---
title: Profil Araçları ile veya hata ayıklayıcı olmadan çalışan | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 3fcdccad-c1bd-4c67-bcec-bf33a8fb5d63
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 64ea0d4d51a7dfbd9a7e1fb58e6297d0842d83b3
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34268275"
---
# <a name="run-profiling-tools-with-or-without-the-debugger"></a>Profil Araçları ile veya olmadan hata ayıklayıcı çalıştırın
Visual Studio şimdi sunar performans seçimine araçları, bazıları (örneğin, **CPU kullanımı** ve **bellek kullanımı**) ile veya hata ayıklayıcı olmadan çalıştırılabilir. Hata ayıklayıcı olmayan performans araçları araçları hata ayıklayıcı tümleşik hata ayıklama yapılandırmaları üzerinde çalıştırmak için tasarlanmış olsa da yayın yapılandırmalarında çalıştırmak üzere tasarlanmıştır.  
  
## <a name="should-i-run-the-tool-with-or-without-the-debugger"></a>Aracı ile veya olmadan hata ayıklayıcısı çalıştırabilir?  
 Hata ayıklayıcı tümleşik performans araçları, çok sayıda hata ayıklayıcı olmayan araçları olamaz şeyler yapın, örneğin kesme noktalarını ayarlayın ve değişken değerleri inceleyin sağlar. Olmayan hata ayıklayıcı araçlar için kullanıcıların yayımlanan uygulamanın görecekleri daha yakın olan bir deneyim sağlar.  
  
 Aşağıda, ne tür bir aracı amaçlarınız için uygun olduğuna karar vermenize yardımcı olabilecek bazı sorular verilmiştir:  
  
1.  Uygulama geliştirilmekte veya bu beklerken bulunan sorunu yayımlanmış bir sürüm bulundu?  
  
     İlgilendiğiniz sorunu geliştirme sırasında bulunursa, bir yayın derleme performans araçları çalıştırmak gerekmez. Bir sürümde bulunduysa yayın yapılandırmasıyla sorunu yeniden oluşturun ve daha fazla araştırma için hata ayıklayıcı yardımcı olacak olup olmadığına karar gerekir.  
  
2.  CPU-yoğun tarafından neden olduğu sorunu işliyor?  
  
     Performans araçları ile veya olmadan hata ayıklayıcı çalıştırmak isteyip kadar fark olun döndürmemelidir için çok sayıda dosya g/ç veya ağ yanıtlama hızı, gibi dış performans sorunları nedeniyle sorunlardır. CPU-yoğun çağrıları nedeniyle sorunu olduğunu, sürüm ve hata ayıklama yapılandırmaları arasındaki farkı önemli olabilir ve büyük olasılıkla gerektiğini sorunu hata ayıklayıcı tümleşik araçları kullanmadan önce yayın derlemede olup olmadığını kontrol edin  
  
3.  Tam olarak performansını ölçmek gerekiyor mu, yoksa yaklaşık bir sayı kabul edilebilir mı?  
  
     Yayın derlemeleri sağlayan bazı en iyi duruma getirme derlemeleri olmaması hata ayıklama, örneğin satır içi kullanım işlev çağrılarını ve sabitleri, ayıklama kullanılmayan kod yolları ve hata ayıklayıcı tarafından kullanılan şekilde depolanmasını değişkenleri. (Örneğin özel durumu ve modülü yük olaylarını kesintiye uğratan) hata ayıklama için gereken belirli işlemler gerçekleştirdiğinden debugger performansı kez değiştirir. Hata ayıklayıcı iyileştirmeler için hesap değil ancak hala hata ayıklama sırasında alınan diğer göreli ölçümlere ile karşılaştırıldığında yararlı olabilir hata ayıklayıcı tümleşik araçları performans numaraları daha düşüktür. Hata ayıklayıcı olmayan araçlarla yayın yapılandırmaları için performans numaraları çok daha kesin.
  
##  <a name="BKMK_Quick_start__Collect_diagnostic_data"></a> Hata ayıklama sırasında profil oluşturma verileri toplama  
 Aşağıdaki bölümde, yerel olarak hata ayıklama ile ilgilidir. Bir aygıt veya uzaktan, sonraki bölümlerde hata ayıklama hata ayıklama hakkında öğrenebilirsiniz.  
  
1.  Açık hata ayıklamak için istediğiniz projeyi ardından **hata ayıklama** > **hata ayıklamayı Başlat** (veya **Başlat** araç çubuğunda veya **F5**).  
  
2.  **Tanılama araçları** penceresi görünür otomatik olarak, bunu devre dışı bırakmış sürece. Pencereyi yeniden getirmek için tıklatın **hata ayıklama** > **Windows** > **tanılama araçları Göster**.  
  
3.  Verileri toplamak istediğiniz senaryolar çalıştırın.  
  
     Oturum çalışırken, olaylar, işlem bellek ve CPU kullanımı hakkındaki bilgileri görebilirsiniz.  
  
     Aşağıdaki grafik gösterir **tanılama araçları** Visual Studio 2015 güncelleştirme 1 penceresinde:  
  
     ![DiagnosticTools&#45;Update1](../profiling/media/diagnostictools-update1.png "DiagnosticTools Update1")  
  
4.  Görmek isteyip istemediğinizi seçebilirsiniz **bellek kullanımı** veya **CPU kullanımı** (veya her ikisi de) ile **seçtiğiniz Araçları** araç çubuğunda ayarlama. Visual Studio Enterprise çalıştırıyorsanız, etkinleştirme veya IntelliTrace içinde devre dışı **Araçları** > **seçenekleri** > **IntelliTrace**.  
  
5.  Hata ayıklamayı durdurun Tanılama oturumu sona erer.  
  
 Visual Studio 2015 güncelleştirme 1, **tanılama araçları** penceresi kolaylaştırır ilgilendiğiniz olayları odaklanmak için.   Olay adları artık kategori öneklerle gösterilir (**hareketi**, **Program çıktısı**, **kesme noktası**, **dosya**, vs.) hızlı şekilde Belirtilen kategori listesi tarama veya hakkında önemli değil kategorileri atlayabilirsiniz.  
  
 Her yerden olay listesi belirli bir dizeyi bulabilmesi için pencereyi bir arama kutusu artık sahiptir. Örneğin, aşağıdaki grafikte dize için bir arama sonuçlarını "dört olayları eşleşen Yükle" gösterir:  
  
 ![DiagnosticsEventSearch](../profiling/media/diagnosticseventsearch.png "DiagnosticsEventSearch")  
  
 Olaylar Görünümü penceresi içinde ve dışındaki de filtre uygulayabilirsiniz. İçinde **filtre** açılan listesinde, denetleyin veya belirli kategorilerden olayların seçeneğinin işaretini kaldırın:. Kategori adları önek adları ile aynıdır.  
  
 ![DiagnosticEventFilter](../profiling/media/diagnosticeventfilter.png "DiagnosticEventFilter")  
  
 Daha fazla bilgi için bkz: [arama ve tanılama araçları penceresindeki olaylar sekmesi filtreleme](http://blogs.msdn.com/b/visualstudioalm/archive/2015/11/12/searching-and-filtering-the-events-tab-of-the-diagnostic-tools-window.aspx).  
  
## <a name="collect-profiling-data-without-debugging"></a>Hata ayıklama olmadan profil oluşturma verilerini topla  
 Bazı profil oluşturma araçları çalıştırmak için yönetici ayrıcalıkları gerektirir. Visual Studio'yu yönetici olarak başlatın veya Tanılama oturumu başlattığınızda araçları yönetici olarak çalıştırmak seçebilirsiniz.  
  
1.  Projesini Visual Studio'da açın.  
  
2.  Üzerinde **hata ayıklama** menüsünde seçin **Performans Profil Oluşturucu** (kısayol tuşu: **Alt**+**F2**).  
  
3.  Tanılama başlatma sayfasında oturumunda çalıştırmak için bir veya daha fazla Araçlar'ı seçin. Proje türü, işletim sistemi ve programlama dili için geçerli olan araçları görüntülenir. Bir tanılama aracı seçtiğinizde, aynı tanılama oturumunda çalıştırılamaz araçları seçimlerini devre dışı bırakılır. Bir C# UWP uygulaması için yaptığınız seçimlere nasıl görünebileceği aşağıda verilmiştir:  
  
     ![Tanılama araçları seçin](../profiling/media/diag_selecttool.png "DIAG_SelectTool")  
  
4.  Tanılama oturumu başlatmak için tıklatın **Başlat**.  
  
5.  Veri toplamak istediğiniz senaryolar çalıştırın.  
  
     Oturum çalışırken bazı araçlar tanılama araçlarını Başlat sayfasında gerçek zamanlı veri grafikleri görüntüleyin.  
  
     ![Performans ve tanı sayfa üzerinde veri toplamak](../profiling/media/pdhub_collectdata.png "PDHUB_CollectData")  
  
6.  Tanılama oturumu sona erdirmek için tıklatın **durdurmak koleksiyonu**.  
  
 Tanılama bir oturumda veri toplamayı durdurduğunuzda, verileri analiz ve rapor tanılama sayfası görüntülenir.  
  
 Ayrıca, tanılama araçları son açılan listeden dosyalarda sayfasını başlatmak kaydedilmiş .diagnostic oturum açabilirsiniz.  
  
 ![Kaydedilen tanılama oturum açmanızı](../profiling/media/pdhub_openexistingdiagsession.png "PDHUB_OpenExistingDiagSession")  
  
## <a name="the-profiling-report"></a>Profil oluşturma raporu  
 ![Tanılama araçları rapor](../profiling/media/diag_report.png "DIAG_Report")  
  
|||  
|-|-|  
|![1. adım](../profiling/media/procguid_1.png "ProcGuid_1")|Zaman çizelgesi profil oluşturma oturumunun uzunluğunu, uygulama yaşam döngüsü etkinleştirme olaylarını ve kullanıcı işaretlerini gösterir.|  
|![2. adım](../profiling/media/procguid_2.png "ProcGuid_2")|Mavi çubukları sürükleyip zaman çizelgesinde bir bölgeyi seçerek, raporu zaman çizelgesinin bir bölümüyle sınırlandırabilirsiniz.|  
|![3. adım](../profiling/media/procguid_3.png "ProcGuid_3")|Bir aracı bir veya daha fazla ana grafikleri görüntüler. Tanılama oturumunuz ile birden çok araç oluşturduysanız, tüm ana grafikleri görüntülenir.|  
|![Adım 4](../profiling/media/procguid_4.png "ProcGuid_4")|Daraltma ve tek tek grafikleri genişletin.|  
|![5. adım](../profiling/media/procguid_6.png "ProcGuid_6")|Verilerinizin birden çok araç bilgileri içerdiğinde, aracı ayrıntıları sekme altında toplanır.|  
|![Adım 6](../profiling/media/procguid_6a.png "ProcGuid_6a")|Bir aracı bir veya daha fazla ayrıntı görünümleri olabilir. Görünümü zaman çizelgesi seçili bölgeye göre filtrelenir.|  
  
## <a name="set-the-analysis-target-to-another-device"></a>Başka bir cihaza çözümleme hedef ayarlayın  
 Visual Studio projeden uygulamanızı başlayarak yanı sıra tanılama oturumları alternatif hedeflerde de çalıştırabilirsiniz. Örneğin, uygulamanızın Windows uygulama Mağazası'ndan yüklenmiş sürümünü performans sorunlarını tanılamanıza isteyebilirsiniz.  
  
 ![Tanılama araçları çözümleme hedef seçin](../profiling/media/pdhub_chooseanalysistarget.png "PDHUB_ChooseAnalysisTarget")  
  
 Bir cihazda zaten yüklü olan uygulamaları başlatabilirsiniz veya çalışmakta olan bazı uygulamalar için tanılama araçları ekleyebilirsiniz. Seçtiğinizde **çalışan uygulama** veya **yüklü App**, belirtilen dağıtım hedefteki uygulamaları bulur bir listeden uygulamayı seçin.  
  
 ![Tanılama için çalışan ya da yüklü bir uygulama seçin](../profiling/media/pdhub_selectrunningapp.png "PDHUB_SelectRunningApp")  
  
 Seçtiğinizde **Internet Explorer**, URL'yi belirtin ve telefon dağıtım hedefini değiştirebilirsiniz.  
  
 ![Internet Explorer'da görüntülemek için URL'yi belirtin](../profiling/media/pdhub_choosephoneanalysistarget.png "PDHUB_ChoosePhoneAnalysisTarget")  
  
## <a name="remote-debugging"></a>Uzaktan Hata Ayıklama  
 Tanılama oturumu uzak PC veya tablet üzerinde çalışan Visual Studio uzak Araçlar yüklendiğinden ve çalıştığından hedefte uzak olmasını gerektirir. Masaüstü uygulamaları için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md).  UWP uygulamalar için bkz: [uzaktaki bir makinede çalıştırın UWP uygulamaları](../debugger/run-windows-store-apps-on-a-remote-machine.md).  
  
## <a name="blog-posts-and-msdn-articles-from-the-diagnostics-development-team"></a>Blog gönderileri ve tanılama geliştirme ekibi MSDN makaleleri  
 [MSDN dergisi: Visual Studio 2015'te hata ayıklama sırasında performansını çözümleme](https://msdn.microsoft.com/en-us/magazine/dn973013.aspx)  
  
 [MSDN dergisi: IntelliTrace daha hızlı sorunları tanılamak için kullanın.](https://msdn.microsoft.com/en-us/magazine/dn973014.aspx)  
  
 [Blog postası: olay işleyicisi sızıntıları Visual Studio 2015'te bellek kullanımı aracıyla tanılama](http://blogs.msdn.com/b/visualstudioalm/archive/2015/04/29/diagnosing-event-handler-leaks-with-the-memory-usage-tool-in-visual-studio-2015.aspx)  
  
 [Video: Geçmiş Microsoft Visual Studio IntelliTrace ile hata ayıklama Ultimate 2015](https://channel9.msdn.com/Events/Ignite/2015/BRK3716)  
  
 [Video: Visual Studio 2015 kullanarak performans sorunlarını hata ayıklama](https://channel9.msdn.com/Events/Build/2015/3-731)  
  
 [PerfTips: Performans bilgileri bir bakışta Visual Studio ile hata ayıklama sırasında](http://blogs.msdn.com/b/visualstudioalm/archive/2014/08/18/perftips-performance-information-at-a-glance-while-debugging-with-visual-studio.aspx)  
  
 [Visual Studio 2015'te tanılama araçlarını hata ayıklayıcı penceresi](http://blogs.msdn.com/b/visualstudioalm/archive/2015/01/16/diagnostic-tools-debugger-window-in-visual-studio-2015.aspx)  
  
 [Visual Studio Enterprise 2015 IntelliTrace](http://blogs.msdn.com/b/visualstudioalm/archive/2015/01/16/intellitrace-in-visual-studio-ultimate-2015.aspx)
