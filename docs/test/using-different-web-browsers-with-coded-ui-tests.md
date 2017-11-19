---
title: "Kodlanmış UI testleri ile farklı Web tarayıcıları kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a859595f-6517-43f2-9d61-c706cb55a388
caps.latest.revision: "23"
ms.author: douge
manager: douge
ms.openlocfilehash: 6c8e2cac9d6f2622bacae0b27cecc8f074ea3a15
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="using-different-web-browsers-with-coded-ui-tests"></a>Kodlanmış UI Testleriyle Farklı Web Tarayıcıları Kullanma
Kodlanmış UI testleri, web uygulamaları için Internet Explorer'ı kullanarak testlerinizi kaydederek sınamayı otomatikleştirebilirsiniz. Bu web uygulamaları için Internet Explorer veya başka tarayıcı türleri kullanarak testinizi özelleştirebilir ve geri oynatabilirsiniz.  
  
 **Gereksinimler**  
  
-   Visual Studio Enterprise  
  
-   İşletim sistemleri:  
  
    -   Microsoft Windows 7  
  
    -   Microsoft Windows 8  
  
    -   Microsoft Windows Server 2008 R2 SP1  
  
-   Web tarayıcı sürümleri:  
  
    -   Windows Internet Explorer 9  
  
    -   Windows Internet Explorer 10  
  
    -   Mozilla Firefox ve Google Chrome'nün desteklenen sürümleri için Git [burada](http://visualstudiogallery.msdn.microsoft.com/11cfc881-f8c9-4f96-b303-a2780156628d/)  
  
-   Yükleme [Selenium bileşenleri kodlanmış UI arası tarayıcı testi için](http://visualstudiogallery.msdn.microsoft.com/11cfc881-f8c9-4f96-b303-a2780156628d/).  
  
 **Tüm web tarayıcıları arasında ne destekleniyor mu?**  
  
-   [Özellikleri denetlemek için özel kod ekleme](http://blogs.msdn.com/b/visualstudioalm/archive/2012/12/10/coded-ui-test-configuring-search-properties-while-recording-on-internet-explorer.aspx) özellikleri, arama ve kayıttan yürütme waiters gibi.  
  
-   Açılır pencereler ve iletişim kutuları  
  
-   [Dönüş türü ile temel JavaScript yürütme](http://blogs.msdn.com/b/visualstudioalm/archive/2013/01/18/introducing-jscript-execution-on-internetexplorer-and-crossbrowser-in-coded-ui-test.aspx)  
  
-   Arama esnekliği (akıllı eşleşme kullanarak) ve [performans iyileştirmeleri](http://blogs.msdn.com/b/visualstudioalm/archive/2012/02/01/guidelines-on-improving-performance-of-coded-ui-test-playback.aspx)  
  
## <a name="why-should-i-use-coded-ui-tests-across-multiple-web-browser-types"></a>Birden çok web tarayıcı türleri arasında kodlanmış UI testleri neden kullanmalıyım?  
 Çeşitli web tarayıcı türleri kullanarak, web uygulamanızı test ederek, farklı tarayıcılar çalıştıran kullanıcıların kullanıcı arabirimi deneyimi daha iyi benzetirsiniz. Örneğin, uygulamanız diğer web tarayıcıları ile uyumlu olmayan Internet Explorer denetim veya kod içerebilir. Diğer tarayıcılar arasında kodlanmış UI testleri çalıştırarak, müşterilerinizi etkilemeden önce herhangi bir sorunu keşfedebilir ve düzeltebilirsiniz.  
  
## <a name="how-do-i-record-and-play-back-coded-ui-tests-on-web-applications-using-the-supported-web-browsers"></a>Kodlanmış UI testleri desteklenen web tarayıcısı kullanarak web uygulamaları üzerinde nasıl kaydederim ve kayıttan yürütürüm?  
 **Kaydı:** Internet Explorer kullanarak, web uygulaması sınaması kaydetmek için kodlanmış UI Test derleyicisini kullanmanız gerekir. İsteğe bağlı olarak, doğrulama ve kodlanmış UI testleri için normalde yaptığınız gibi önceden tanımlanmış bir özellik kümesi kullanarak sınanmış denetimler için özel kod ekleyebilirsiniz. Daha fazla bilgi için bkz: [kullanım UI Otomasyon için Test kodunuzu](../test/use-ui-automation-to-test-your-code.md).  
  
> [!NOTE]
>  Google Chrome veya Mozilla Firefox tarayıcısı kullanarak kodlanmış UI testleri kaydedemezsiniz.  
  
 **Internet Explorer ile kayıttan:** hiçbir tarayıcı açıkça belirtildiğinde, Internet Explorer, varsayılan olarak testleri çalıştırırsınız. Açıkça ayarlayarak kullanılacak tarayıcı durum **BrowserWindow.CurrentBrowser** test kodunuzu bir özellik. Internet Explorer için bu özelliği ayarlanmalıdır **IE** veya **Internet Explorer**.  
  
 **Internet Explorer web tarayıcılarıyla kayıttan:** üzerinde Internet Explorer web tarayıcıları çalmak için test kodunuzu BrowserWindow.CurrentBrowser özelliğinde ya da değiştirme **Firefox** veya **Chrome** .  
  
 Testleri üzerinde IE olmayan web tarayıcıları çalmak için yüklemelisiniz **Selenium bileşenleri kodlanmış UI arası tarayıcı testi için**.  
  
#### <a name="installing-selenium-components"></a>Selenium bileşenlerini yükleme  
  
1.  Üzerinde **Araçları** menüsünde seçin **Uzantılar ve güncelleştirmeler**.  
  
2.  İçin arama uzantısı ve güncelleştirmeleri iletişim kutusu `Selenium components for Cross Browser Testing`.  
  
3.  Uzantı vurgulayın ve seçin **karşıdan**.  
  
    > [!TIP]
    >  Kodlanmış UI arası tarayıcı testi için Selenium bileşenleri indirebilirsiniz [burada](http://visualstudiogallery.msdn.microsoft.com/11cfc881-f8c9-4f96-b303-a2780156628d/).  
  
 Daha fazla bilgi hakkında oluşturma ve kullanma kodlanmış UI testleri için bkz: [kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate).  
  
### <a name="enable-debugging"></a>Hata ayıklamayı etkinleştir  
 Web uygulamanızda hata ayıklamayı etkinleştirmek için aşağıdaki yapılandırma seçeneklerini tamamlamanız gerekir:  
  
1.  Yalnızca Kendi Kodumu Etkinleştir:  
  
    1.  Üzerinde **Araçları** menüsünde seçin **seçenekleri** ve ardından **hata ayıklama**.  
  
    2.  Seçin **yalnızca benim kodumu etkinleştir**.  
  
2.  CLR özel durumları devre dışı bırakın:  
  
    1.  Üzerinde **hata ayıklama** menüsünde seçin **özel durumları**.  
  
    2.  İçin **ortak dil çalışma zamanı özel durumları**, işaretini **kullanıcı işlenmemiş**.  
  
##  <a name="generate"></a>*BrowserWindow.CurrentBrowser kodlanmış UI testi değiştirme seçeneği görmüyorum.*  
 Bir sürümünü kullanıyor olabilirsiniz [!INCLUDE[vs2011_first](../test/includes/vs2011_first_md.md)] çeşitli web tarayıcısı kullanarak kodlanmış UI testlerini desteklemiyor. Bu tür kodlanmış UI testleri kullanmak için Visual Studio Enterprise kullanmanız gerekir.  
  
 *Başka ne bilebilirim?*  
 **Notlar**  
  
-   ![Prerequsite](../test/media/prereq.png "önkoşul") Apple Safari web tarayıcısı desteklenmiyor.  
  
-   ![Prerequsite](../test/media/prereq.png "önkoşul") web tarayıcısı başlangıç eylemi kodlanmış UI testi parçası olması gerekir.  
  
     Internet Explorer kullanmadığınız sürece açık bir web tarayıcısına sahip ve adımlar üzerinde çalıştırmak istiyorsanız, kayıttan yürütme başarısız olur. Bu nedenle, web tarayıcınızı başlatması kodlanmış UI testleriniz bir parçası olarak dahil en iyi uygulamadır.  
  
-   ![Prerequsite](../test/media/prereq.png "önkoşul") belirli otomatikleştirme tarayıcı tabanlı UI eylemlerini gibi en üst düzeye çıkarmak, en aza indirmek ve geri yükleme desteklenmez.  
  
 **İpuçları**  
  
-   ![İpucu](../test/media/tip.png "İpucu") çıkış ekran görüntüleri kodlanmış UI günlüklerde içerecek şekilde yapılandırabilirsiniz. Bunu yapmak için bazı yapılandırma ayarlarını QTAgent32.exe.config dosyasında ayarlamanız gerekir. Varsayılan olarak, bu dosya aşağıdaki konuma yüklenir:  
  
     **C:\Program dosyaları (x86) \Microsoft Visual Studio 11.0\Common7\IDE**  
  
     Aşağıdaki değerleri ayarlayın:  
  
    -   `EqtTraceLevel`içinde `system.diagnostics` bölümü.  
  
    -   `<add name="EqtTraceLevel" value="4" />`  
  
         3 veya daha yüksek bir değere ayarlayarak ekran görüntüleri her eylem için alınır. Değeri 1 veya 2'ye ayarlandığında, ekran görüntüleri yalnızca hata eylemleri alır.  
  
     Daha fazla bilgi için bkz: [çözümleme kodlanmış UI testleri kullanarak kodlanmış UI Test günlüklerini](../test/analyzing-coded-ui-tests-using-coded-ui-test-logs.md).  
  
## <a name="external-resources"></a>Dış Kaynaklar  
  
### <a name="videos"></a>Videolar  
 [IE ve kayıttan yürütme her yerde kaydedin](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!183&authkey=!ANqaLtCZbtJrImU)  
  
 [Kodlanmış UI Test derleyicisini tarayıcı testleriyle çapraz Yazar](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!184&authkey=!AKG8CSow_qmeTq8)  
  
 [UI eşlemesi düz el kodlama kullanarak tarayıcı testleri çapraz Yazar](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!186&authkey=!AJaEvxJnsefyAT4)  
  
 [Çapraz tarayıcı testleri birden çok tarayıcılarda sırayla çalışır.](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!187&authkey=!ADI8eCQkxHnpOR8)  
  
 [Tarayıcı test hatalarını giderme](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!182&authkey=!AEpS48i295B49FI)  
  
### <a name="guidance"></a>Kılavuz  
 [Visual Studio 2012 - bölüm 2 ile sürekli teslimat için test etme: birim testi: iç test etme](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
 [Visual Studio 2012 - bölüm 5 ile sürekli teslimat için test etme: Sistem testlerini otomatikleştirme](http://go.microsoft.com/fwlink/?LinkID=255196)  
  
### <a name="faq"></a>SSS  
 [SSS - 1 kodlanmış UI testleri](http://go.microsoft.com/fwlink/?LinkID=230576)  
  
 [Kodlanmış UI testleri ile ilgili SSS -2](http://go.microsoft.com/fwlink/?LinkID=230578)  
  
### <a name="forum"></a>Forum  
 [Visual Studio UI Otomasyon (kodlanmış UI içerir) test etme](http://go.microsoft.com/fwlink/?LinkID=224497)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kodunuzu test etmek için UI otomasyonunu kullanma](../test/use-ui-automation-to-test-your-code.md)   
 [Kodlanmış UI testleri ve eylem kayıtları için desteklenen yapılandırmalar ve platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)   
 [Kodlanmış UI Test günlüklerini kullanarak kodlanmış UI testlerini çözümleme](../test/analyzing-coded-ui-tests-using-coded-ui-test-logs.md)
