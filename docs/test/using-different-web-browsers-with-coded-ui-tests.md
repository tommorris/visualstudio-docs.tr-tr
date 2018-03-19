---
title: "Kodlanmış UI testleri Visual Studio'da farklı Web tarayıcıları ile kullanma | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 69f2f186b8462b5630970bdc93e358ffc61ad0f5
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="use-different-web-browsers-with-coded-ui-tests"></a>Kodlanmış UI testleriyle farklı Web tarayıcıları kullanma

Kodlanmış UI testleri, web uygulamaları için Internet Explorer'ı kullanarak testlerinizi kaydederek sınamayı otomatikleştirebilirsiniz. Bu web uygulamaları için Internet Explorer veya başka tarayıcı türleri kullanarak testinizi özelleştirebilir ve geri oynatabilirsiniz.

İlk olarak, yükleme [Selenium bileşenleri kodlanmış UI arası tarayıcı testi için](https://marketplace.visualstudio.com/items?itemName=AtinBansal.SeleniumcomponentsforCodedUICrossBrowserTesting).

## <a name="whats-supported-across-all-web-browsers"></a>Tüm web tarayıcıları arasında ne destekleniyor mu?

-   [Özellikleri denetlemek için özel kod ekleme](http://blogs.msdn.com/b/visualstudioalm/archive/2012/12/10/coded-ui-test-configuring-search-properties-while-recording-on-internet-explorer.aspx) özellikleri, arama ve kayıttan yürütme waiters gibi.

-   Açılır pencereler ve iletişim kutuları

-   [Dönüş türü ile temel JavaScript yürütme](http://blogs.msdn.com/b/visualstudioalm/archive/2013/01/18/introducing-jscript-execution-on-internetexplorer-and-crossbrowser-in-coded-ui-test.aspx)

-   Arama esnekliği (akıllı eşleşme kullanarak) ve [performans iyileştirmeleri](http://blogs.msdn.com/b/visualstudioalm/archive/2012/02/01/guidelines-on-improving-performance-of-coded-ui-test-playback.aspx)

## <a name="why-should-i-use-coded-ui-tests-across-multiple-web-browser-types"></a>Birden çok web tarayıcı türleri arasında kodlanmış UI testleri neden kullanmalıyım?

Çeşitli web tarayıcı türleri kullanarak, web uygulamanızı test ederek, farklı tarayıcılar çalıştıran kullanıcıların kullanıcı arabirimi deneyimi daha iyi benzetirsiniz. Örneğin, uygulamanız diğer web tarayıcıları ile uyumlu olmayan Internet Explorer denetim veya kod içerebilir. Diğer tarayıcılar arasında kodlanmış UI testleri çalıştırarak, müşterilerinizi etkilemeden önce herhangi bir sorunu keşfedebilir ve düzeltebilirsiniz.

## <a name="how-do-i-record-and-play-back-coded-ui-tests-on-web-applications-using-the-supported-web-browsers"></a>Kodlanmış UI testleri desteklenen web tarayıcısı kullanarak web uygulamaları üzerinde nasıl kaydederim ve kayıttan yürütürüm?

**Kaydı:** Internet Explorer kullanarak, web uygulaması sınaması kaydetmek için kodlanmış UI Test derleyicisini kullanmanız gerekir. İsteğe bağlı olarak, doğrulama ve kodlanmış UI testleri için normalde yaptığınız gibi önceden tanımlanmış bir özellik kümesi kullanarak sınanmış denetimler için özel kod ekleyebilirsiniz. Daha fazla bilgi için bkz: [kullanım UI Otomasyon için Test kodunuzu](../test/use-ui-automation-to-test-your-code.md).

> [!NOTE]
> Google Chrome veya Mozilla Firefox tarayıcısı kullanarak kodlanmış UI testleri kaydedemezsiniz.

 **Internet Explorer ile kayıttan:** hiçbir tarayıcı açıkça belirtildiğinde, Internet Explorer, varsayılan olarak testleri çalıştırırsınız. Açıkça ayarlayarak kullanılacak tarayıcı durum **BrowserWindow.CurrentBrowser** test kodunuzu bir özellik. Internet Explorer için bu özelliği ayarlanmalıdır **IE** veya **Internet Explorer**.

 **Internet Explorer web tarayıcılarıyla kayıttan:** üzerinde Internet Explorer web tarayıcıları çalmak için test kodunuzu BrowserWindow.CurrentBrowser özelliğinde ya da değiştirme **Firefox** veya **Chrome** .

 Testleri üzerinde IE olmayan web tarayıcıları çalmak için yüklemelisiniz **Selenium bileşenleri kodlanmış UI arası tarayıcı testi için**.

### <a name="install-selenium-components"></a>Selenium bileşenlerini yükle

1.  Üzerinde **Araçları** menüsünde seçin **Uzantılar ve güncelleştirmeler**.

2.  İçin arama uzantısı ve güncelleştirmeleri iletişim kutusu `Selenium components for Cross Browser Testing`.

3.  Uzantı vurgulayın ve seçin **karşıdan**.

    > [!TIP]
    > Kodlanmış UI arası tarayıcı testi için Selenium bileşenleri indirebilirsiniz [burada](https://marketplace.visualstudio.com/items?itemName=AtinBansal.SeleniumcomponentsforCodedUICrossBrowserTesting).

Daha fazla bilgi hakkında oluşturma ve kullanma kodlanmış UI testleri için bkz: [kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md).

### <a name="enable-debugging"></a>Hata ayıklamayı etkinleştir

Web uygulamanızda hata ayıklamayı etkinleştirmek için aşağıdaki yapılandırma seçeneklerini tamamlamanız gerekir:

1.  Yalnızca Kendi Kodumu Etkinleştir:

    1.  Üzerinde **Araçları** menüsünde seçin **seçenekleri** ve ardından **hata ayıklama**.

    2.  Seçin **yalnızca benim kodumu etkinleştir**.

2.  CLR özel durumları devre dışı bırakın:

    1.  Üzerinde **hata ayıklama** menüsünde seçin **özel durumları**.

    2.  İçin **ortak dil çalışma zamanı özel durumları**, işaretini **kullanıcı işlenmemiş**.

Varsa değiştirme seçeneğini görmüyorsanız `BrowserWindow.CurrentBrowser` kodlanmış UI testi, çeşitli web tarayıcısı kullanarak kodlanmış UI testlerini desteklemiyor Visual Studio sürümünü kullanıyor olabilirsiniz. Bu tür kodlanmış UI testleri kullanmak için Visual Studio Enterprise edition kullanmanız gerekir.

Bilmeniz gereken bazı şeyler şunlardır:

- Apple Safari web tarayıcısı desteklenmiyor.

- Web tarayıcısını başlatma eylemini, kodlanmış UI testi parçası olmalıdır.

   Internet Explorer kullanmadığınız sürece açık bir web tarayıcısına sahip ve adımlar üzerinde çalıştırmak istiyorsanız, kayıttan yürütme başarısız olur. Bu nedenle, web tarayıcınızı başlatması kodlanmış UI testleriniz bir parçası olarak dahil en iyi uygulamadır.

- Ekranı kapla, simge durumuna küçült, geri yükle gibi belirli tarayıcı tabanlı UI eylemlerini böyle otomatikleştirme desteklenmiyor.

## <a name="tips"></a>İpuçları

Çıktı kodlanmış UI günlüklerinde ekran görüntüleri dahil etmek için yapılandırabilirsiniz. Bunu yapmak için bazı yapılandırma ayarları kümesinde gereksinim *QTAgent32.exe.config* dosya. Varsayılan olarak, bu dosya aşağıdaki konuma yüklenir:

     *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE*

Aşağıdaki değerleri ayarlayın:

- `EqtTraceLevel` içinde `system.diagnostics` bölümü.

- `<add name="EqtTraceLevel" value="4" />`

   Ekran görüntüleri değeri 3 veya daha yüksek olarak ayarlayarak, her eylem için alınır. Değeri 1 veya 2'ye ayarlandığında, ekran görüntüleri yalnızca hata eylemleri alır.

Daha fazla bilgi için bkz: [çözümleme kodlanmış UI testleri kullanarak kodlanmış UI Test günlüklerini](../test/analyzing-coded-ui-tests-using-coded-ui-test-logs.md).

## <a name="video-resources"></a>Video Kaynakları

 [IE ve kayıttan yürütme her yerde kaydedin](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!183&authkey=!ANqaLtCZbtJrImU)

 [Kodlanmış UI Test derleyicisini tarayıcı testleriyle çapraz Yazar](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!184&authkey=!AKG8CSow_qmeTq8)

 [UI eşlemesi düz el kodlama kullanarak tarayıcı testleri çapraz Yazar](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!186&authkey=!AJaEvxJnsefyAT4)

 [Çapraz tarayıcı testleri birden çok tarayıcılarda sırayla çalışır.](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!187&authkey=!ADI8eCQkxHnpOR8)

 [Tarayıcı test hatalarını giderme](https://skydrive.live.com/redir?resid=AE5CD7309CCCC43C!182&authkey=!AEpS48i295B49FI)

## <a name="see-also"></a>Ayrıca bkz.

- [Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](../test/use-ui-automation-to-test-your-code.md)
- [Kodlanmış UI Testleri ve Eylem Kayıtları için Desteklenen Yapılandırmalar ve Platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
- [Kodlanmış UI Test Günlüklerini Kullanarak Kodlanmış UI Testlerini Çözümleme](../test/analyzing-coded-ui-tests-using-coded-ui-test-logs.md)
