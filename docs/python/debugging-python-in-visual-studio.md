---
title: Python kodda hata ayıklama
description: Visual Studio'da hata ayıklama özelliği özellikle kesme noktalarını ayarlama, Adımlama, değerleri inceleyerek, özel durumları görmek ve etkileşimli penceresinde hata ayıklama dahil olmak üzere Python kodu için bir kılavuz.
ms.date: 03/05/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: b521c85bd2a4fb8c29674a51e5e13ded2aba3fec
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2018
ms.locfileid: "32032261"
---
# <a name="debugging-your-python-code"></a>Python kodunuzun hatalarını ayıklama

Visual Studio, Python, çalışan işlemlere, ekleme de dahil olmak üzere izleme ifadelerinde değerlendirmek için kapsamlı bir hata ayıklama deneyimini sağlar ve hemen windows, yerel değişkenleri, kesme noktaları, inceleniyor içinde/çıkış/üzerinden deyimleri, ayarlamak sonraki adım İfade ve daha fazlası.

Ayrıca aşağıdaki senaryoya özgü hata ayıklama makalelerine bakın:

- [Linux uzaktan hata ayıklama](debugging-python-code-on-remote-linux-machines.md)
- [Azure uzaktan hata ayıklama](debugging-remote-python-code-on-azure.md)
- [Karışık mod Python/C++ hata ayıklama](debugging-mixed-mode-c-cpp-python-in-visual-studio.md)
- [Karışık mod hata ayıklaması için semboller](debugging-symbols-for-mixed-mode-c-cpp-python.md)

|   |   |
|---|---|
| ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin") | [(Microsoft Virtual Academy) bir video izlemek](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Debugging-Python-Ep5dp5LWE_3805918567) (3 m 32s) hata ayıklama Python tanıtımı için.|

<a name="debugging-without-a-project"></a>

> [!Tip]
> Visual Studio'da Python olmayan bir proje hata ayıklamayı destekler. Tek başına Python dosyası ile açık Düzenleyicisi'ni sağ tıklatın seçin **Başlat ile hata ayıklama**, ve Visual Studio komut dosyası genel varsayılan ortamı başlatır (bkz [Python ortamları](managing-python-environments-in-visual-studio.md)) ve bağımsız değişkenler. Ancak daha sonra tam hata ayıklama desteğine sahip.
>
> Bağımsız değişkenler ve ortamı denetlemek için kolayca gerçekleştirilir kodu için bir proje oluşturun [varolan Python kodu](managing-python-projects-in-visual-studio.md#creating-a-project-from-existing-files) proje şablonu.

<a name="debugging-with-a-project"></a>

## <a name="basic-debugging"></a>Temel hata ayıklama

Temel hata ayıklama iş akışı aracılığıyla koda atlama, değerlerini inceleme ve aşağıdaki bölümlerde açıklandığı gibi özel durumları işleme ayarları kesme noktaları içerir.

Hata ayıklama oturumu ile başlayan **hata ayıklama > hata ayıklamayı Başlat** komutu, **Başlat** araç veya F5 tuşuna düğmesine. Bu Eylemler, projenizin başlangıç dosyasını çalıştırın (gösterilen Çözüm Gezgini'nde kalın) projenin etkin ortam ve komut satırı bağımsız değişkenleri ya da proje özellikleri'nde belirtilen arama yolları (bkz [proje hata ayıklama Seçenekler](#project-debugging-options). **Visual Studio 2017 sürüm 15,6** ve daha sonra ayarlanmış bir başlatma dosyası yoksa sizi uyarır; önceki sürümlerinde çalıştıran Python yorumlayıcı ile bir çıktı penceresi açık veya çıktı penceresini kısaca görünür ve kaybolur. Herhangi bir durumda, uygun dosyasını sağ tıklatın ve seçin **başlangıç dosyası olarak ayarlamak**.

> [!Note]
> Hata ayıklayıcı her zaman etkin Python ortamı projesi için başlar. Ortam değiştirmek için farklı bir etkin açıklandığı gibi olun [bir proje için bir Python ortamı seçme](selecting-a-python-environment-for-a-project.md).

### <a name="breakpoints"></a>Kesme noktaları

Program durumu incelemek için kesme noktaları işaretlenen bir noktada kod yürütmeyi durdurun. Kesme sol kenar Kod düzenleyicisinde veya bir kod satırı sağ tıklayıp seçerek tıklayarak **kesme noktası > Kesme Noktası Ekle**. Her satırda bir kesme noktası ile kırmızı bir nokta görünür.

![Visual Studio'da kesme noktaları](media/debugging-breakpoints.png)

Kırmızı nokta veya kod satırı sağ tıklatıp seçerek **kesme noktası > silme kesme noktası** kesme kaldırır. Ayrıca, kullanarak kaldırmadan devre dışı bırakabilirsiniz **kesme noktası > devre dışı kesme noktası** komutu.

> [!Note]
> Bazı kesme noktaları python'da diğer programlama dilleriyle çalıştıktan geliştiriciler için şaşırtıcı olabilir. Herhangi bir üst düzey sınıfı veya işlev tanımları işlemek için yüklendiğinde Python dosyası çalıştığında Python, dosyanın tamamı yürütülebilir koddur. Bir kesme noktası ayarlarsanız, hata ayıklayıcı kesme bölümü yönlü sınıfı bildirimine bulabilirsiniz. Bu davranış doğru bazen şaşırtıcı olmasına rağmen.

Altında bir kesme noktası, yalnızca bir değişken belirli bir değer veya değer aralığı için ayarlandığında sonu gibi tetiklenir koşullar özelleştirebilirsiniz. Koşulları ayarlayın, kesme noktası'nın kırmızı nokta sağ tıklayın, seçin **koşulu**, Python kodu kullanarak ifadeler oluşturun. Visual Studio'da bu özellik hakkında tam bilgi için bkz: [kesme noktası koşullar](../debugger/using-breakpoints.md#breakpoint-conditions)

Koşullar ayarlarken de ayarlayabilirsiniz **eylem** ve isteğe bağlı olarak otomatik olarak yürütmeye çıkış penceresine oturum için bir ileti oluşturun. Bir ileti günlüğe kaydetme oluşturur ne adlı bir *tracepoint* eklemeden günlük kodu uygulamanıza doğrudan:

![Bir tracepoint bir kesme noktası ile oluşturma](media/debugging-tracepoint.png)

### <a name="stepping-through-code"></a>Kod atlama

Kesme noktasında durdurulduğunda aracılığıyla koda adım veya kod bloklarını kesmeden önce yeniden çalıştırmak için çeşitli yolu vardır. Bu komutlar üst debug araç dahil olmak üzere bir yerde sayısında kullanılabilir **hata ayıklama** menüsünde sağ tıklatma bağlam menüsünde klavye kısayolları ile kod düzenleyicisini (tüm komutları olan tüm konumları):

| Özellik | Tuş vuruşu | Açıklama |
| --- | --- | --- |
| Devam et | F5 | Sonraki kesme ulaşılana kadar kodu çalıştırır. |
| Girme | F11 | Sonraki deyim çalıştırır ve durdurur. Sonraki deyim bir işlevi çağrısı ise, hata ayıklayıcı çağrılan işlev ilk satırında durdurur. |
| Adımlama | F10 | (Tüm kodları çalıştıran) bir işlevi çağrısı yapmak dahil sonraki deyimini çalıştırır ve tüm dönüş değeri uygulanıyor. Üzerinden atlama hata ayıklama gerekmez işlevleri kolayca atlamanızı sağlar. |
| Dışarı Adım | Shift+F11 | Kod arama deyimi geçerli işlevi sonra adımları sonuna kadar çalışır.  Bu komut, geçerli işlevi geri kalanı hata ayıklama gerekmez yararlıdır. |
| İmleci çalıştırın | Ctrl+F10 | Düzenleyicideki düzeltme işareti konumunu kadar kodu çalıştırır. Bu komutu bir hata ayıklama gerekmez kod kesimi kolayca atlamanızı sağlar. |
| Sonraki Deyimi Belirle | Ctrl+Shift+F10 | Noktası şapka konuma kodda çalıştırma geçerli değiştirir. Bu komut tüm Çalıştır kod kesimi iptal etmenize izin verir, bildiğinizde gibi kodu hatalı veya üretir ve yan etkisi istenmeyen. |
| Sonraki deyim göster | Alt+Num * | Çalıştırmak için next deyimi döndürür. Bu komut, kodunuzda arayan edilmiş ve hata ayıklayıcı durduğu hatırlama yararlı olur. |

### <a name="inspecting-and-modifying-values"></a>İnceleme ve değerlerini değiştirme

Hata ayıklayıcıda durduğunda inceleyin ve değişkenlerin değerleri değiştirin. Gözcü penceresi, bağımsız değişkenleri ve bunun yanı sıra özel ifadeler izlemek için de kullanabilirsiniz. (Bkz [incelemek değişkenleri](../debugger/getting-started-with-the-debugger.md#inspect-variables-with-the-autos-and-locals-windows) genel ayrıntıları için.)

DataTips kullanarak bir değeri görüntülemek için yalnızca fare Düzenleyicisi'nde herhangi bir değişken üzerine gelerek. Değeri değiştirmek için tıklatın:

![DataTips hata ayıklayıcı](media/debugging-quick-tips.png)

Otomatik değişkenler penceresi (**hata ayıklama > Windows > otomobiller**) değişkenleri ve geçerli deyim yakın olan bir ifade içeriyor. Değer sütununda çift tıklatın veya seçin ve değeri düzenlemek için F2 tuşuna basın:

![Hata ayıklayıcı otomatik değişkenler penceresi](media/debugging-autos-window.png)

Yerel öğeler penceresi (**hata ayıklama > Windows > Yereller**) yeniden düzenlenebilir geçerli kapsamdaki tüm değişkenler görüntüler:

![Yerel öğeler penceresi hata ayıklayıcı](media/debugging-locals-window.png)

Otomatik değişkenler ve Yereller kullanma hakkında daha fazla bilgi için bkz: [otomobiller ve yerel Windows inceleniyor değişkenler](../debugger/autos-and-locals-windows.md).

Gözcü pencerelerini (**hata ayıklama > Windows > İzleme > 1-4 İzleme**) rasgele Python ifadeler girin ve sonuçları görüntüleme imkan tanır. İfadeler her adımı için değerlendirilerek:

![Hata ayıklayıcı Gözcü penceresi](media/debugging-watch-window.png)

Gözcü kullanma hakkında daha fazla bilgi için bkz: [bir izleme izleme ve QuickWatch Windows kullanarak değişkenlerde ayarı](../debugger/watch-and-quickwatch-windows.md).

Bir dize değeri Denetlenmekte olduğunda (`str`, `unicode`, `bytes`, ve `bytearray` tüm dizeleri bu amaca yönelik olarak kabul edilir), Büyüteç simgesini değeri sağ tarafında görünür. Simgeye tıklayarak uzun dizeleri için yararlı olan tırnak işareti olmayan dize değeri sarmalama ve kaydırmayı, açılan iletişim kutusunda görüntüler. Ayrıca, aşağı açılan ok simgesini seçerek düz metin seçmenizi sağlayan HTML, XML ve JSON görselleştirmeleri:

![Dize görselleştiriciler](media/debugging-string-visualizers.png)

HTML, XML ve JSON görselleştirmeleri ayrı açılır pencereleri söz dizimi vurgulama ve ağaç görünümlerle görünür.

### <a name="exceptions"></a>Özel Durumlar

Hata ayıklama sırasında bir hata programınıza oluşur, ancak bunun için bir özel durum işleyici yok, hata ayıklayıcı özel durum noktasında keser:

![Özel durum açılan](media/debugging-exception-popup.png)

Bu noktada çağrı yığınına dahil olmak üzere program durumunu inceleyebilirsiniz. Bununla birlikte, kod üzerinden adım çalışırsanız, özel durum ya da ele veya programınız çıktığında kadar oluşturulan devam eder.

**Hata ayıklama > Windows > özel ayarları** menü komutu getirir genişletin bir penceresini **Python özel durumları**:

![Özel durumlar penceresi](media/debugging-exception-settings.png)

Her özel durum denetimleri için onay kutusunu olup olmadığını hata ayıklayıcı *her zaman* bu oluştuğunda keser. Daha sık için belirli bir durum bölün istediğinizde bu onay kutusunu işaretleyin.

Varsayılan olarak, çoğu özel durumlar çıkarken bir özel durum işleyici kaynak kodunda bulunamıyor. Bu davranışı değiştirmek için bir özel durumla sağ tıklayın ve değiştirme **devam zaman işlenmemiş kullanıcı kodu** seçeneği. Daha az sıklıkta için bir özel durum bölün istediğinizde bu kutusunu temizleyin.

Bu listede görünmeyen bir özel durum yapılandırmak için tıklatın **Ekle** düğmesi ekleyin. Adı, özel durumun tam adıyla eşleşmelidir.

## <a name="project-debugging-options"></a>Hata ayıklama seçeneklerini proje

Varsayılan olarak, hata ayıklayıcı programınızı standart Python başlatıcısı, hiçbir komut satırı bağımsız değişkenleri ve diğer özel yollar veya koşullar ile başlatır. Başlangıç seçenekleri, Çözüm Gezgini'nde, projenize sağ tarafından erişilen projenin hata ayıklama özellikleri aracılığıyla değiştirilir seçme **özellikleri**, seçerek **hata ayıklama** sekmesi.

![Proje hata ayıklama özellikleri](media/debugging-project-properties.png)

### <a name="launch-mode-options"></a>Başlatma modu seçenekleri

| Seçenek | Açıklama |
| --- | --- |
| Standart Python Başlatıcısı | Hata ayıklama CPython, IronPython ve Stackless Python gibi değişkenleri ile uyumlu taşınabilir Python yazılmış kodu kullanır. Bu, saf Python kodda hata ayıklama için en iyi deneyimi sağlar. Çalışan bir eklediğiniz zaman `python.exe` işlem, bu Başlatıcısı kullanılır. Bu Başlatıcı de sağlar [karışık mod hata ayıklaması](debugging-mixed-mode-c-cpp-python-in-visual-studio.md) CPython için C/C++ kod ve Python kodu arasında sorunsuz bir şekilde adım olanak sağlar. |
| Web Başlatıcısı | Varsayılan tarayıcınız başlatılırken başlatılır ve şablonları hata ayıklamasını etkinleştirir. Bkz: [Web şablonu hata ayıklama](python-web-application-project-templates.md#debugging) daha fazla bilgi için bölüm. |
| Django Web Başlatıcısı | Web Başlatıcısı aynı ve yalnızca geriye doğru uyumluluk için gösterilen. |
| IronPython (.NET) Başlatıcısı | .NET hata ayıklayıcı IronPython yalnızca hangi çalışır kullanır ancak C# ve vb dahil olmak üzere tüm .NET dil proje arasında atlama için izin verir Bu Başlatıcı IronPython barındıran çalışan bir .NET işleme iliştirilemiyor kullanılır. |

### <a name="run-options-search-paths-startup-arguments-and-environment-variables"></a>Çalıştırma Seçenekleri (arama yolları, başlangıç bağımsız değişkenler ve ortam değişkenleri)

| Seçenek | Açıklama |
| --- | --- |
| Arama yolları | Çözüm Gezgini'nde proje arama yolları düğümünde görüntülenen bu değerlerin eşleşmesi. Burada bu değeri değiştirebilirsiniz, ancak klasörlere göz atmanıza izin verir ve otomatik olarak yolları göreli biçimine dönüştürür Çözüm Gezgini kullanmak daha kolaydır. |
| Betik bağımsız değişkenleri | Bu bağımsız değişkenler komut dosyanızın filename sonra görünen kodunuzu başlatmak için kullanılan komutu eklenir. İlk öğe İşte, komut dosyası olarak kullanılabilir `sys.argv[1]`, saniye olarak `sys.argv[2]`ve benzeri. |
| Yorumlayıcı bağımsız değişkenler | Bu bağımsız değişkenler komut dosyanızın adı önce Başlatıcısı komut satırına eklenir. Burada ortak bağımsız değişkenler `-W ...` denetimi uyarılar için `-O` biraz programınızı, en iyi duruma getirme ve `-u` arabellekten çıkarılan g/ç kullanmak için. IronPython kullanıcılar geçirmek için bu alanı kullanmak büyük olasılıkla `-X` gibi seçenekleri `-X:Frames` veya `-X:MTA`. |
| Yorumlayıcı yolu | Geçerli ortamı ile ilişkili yolu geçersiz kılar.  değer bir standart yorumlayıcı komut dosyanızı başlatmak için yararlı olabilir. |
| Ortam Değişkenleri | Bu çok satırlı metin kutusunda, form girişlerini ekleyin `NAME=VALUE`. Bu ayar son olarak, var olan tüm genel ortam değişkenlerini ve sonra üstte uygulandığından `PYTHONPATH` ayarlanmış arama yolları ayarına göre bu el ile bu bunlardan herhangi diğer değişkenler geçersiz kılmak için kullanılabilir. |

<a name="the-debug-interactive-window"></a>

## <a name="immediate-and-interactive-windows"></a>Anında ve etkileşimli windows

Hata ayıklama oturumu sırasında kullanabileceğiniz iki etkileşimli windows vardır: standart Visual Studio komut penceresi ve Python hata ayıklama etkileşimli penceresi.

Komut penceresi (**hata ayıklama > Windows > hemen**) hızlı değerlendirme Python ifadeleri ve denetleme veya çalışan program değişkenler ataması için kullanılır. Genel bkz [komut penceresi](../ide/reference/immediate-window.md) Ayrıntılar için makale.

Python hata ayıklama etkileşimli pencere (**hata ayıklama > Windows > Python hata ayıklama etkileşimli**) tam getirir daha zengin olan [etkileşimli REPL](python-interactive-repl-in-visual-studio.md) hata ayıklama sırasında yazma dahil olmak üzere kullanılabilir deneyimi ve kod çalıştırıyor. Standart Python Başlatıcısı'nı kullanarak hata ayıklayıcıda başlayan tüm işlem otomatik olarak bağlanır (işlemler de dahil olmak üzere bağlı aracılığıyla **hata ayıklama > ekleme işlemi için**). Ancak, C/C++ karışık mod hata ayıklaması kullanırken kullanılabilir değilse.

![Python hata ayıklama etkileşimli penceresi](media/debugging-interactive.png)

Hata ayıklama etkileşimli pencere ek olarak özel meta komutları destekleyen [standart REPL komutları](python-interactive-repl-in-visual-studio.md#meta-commands):

| Komut | Arguments | Açıklama |
| --- | --- | --- |
| `$continue`, `$cont`, `$c` | Program geçerli deyiminden çalışmaya başlar. |
| `$down`, `$d` | Geçerli çerçeve bir düzey aşağı yığın izlemesi taşıyın. |
| `$frame` | | Geçerli çerçeve kimliğini görüntüler.
| `$frame` | Çerçeve kimliği | Geçerli çerçeve belirtilen çerçeve kimliğine geçer.
| `$load` | Komutları dosyasından yükler ve tamamlanıncaya kadar yürütür |
| `$proc` |  | Geçerli işlem kimliğini görüntüler. |
| `$proc` | İşlem kimliği | Geçerli işlem için belirtilen işlem kimliği geçer. |
| `$procs` | | Şu anda ayıklanacak işlemleri listeler. |
| `$stepin`, `$step`, `$s` | Sonraki işlev çağrısı, mümkünse adımları. |
| `$stepout`, `$return`, `$r` | Adımlar geçerli işlevi dışında. |
| `$stepover`, `$until`, `$unt` | Sonraki işlev çağrısı üzerinden adımlar. |
| `$thread` | | Geçerli iş parçacığı kimliği görüntüler. |
| `$thread` | İş parçacığı kimliği | Geçerli iş parçacığının belirtilen iş parçacığı kimliğine geçer. |
| `$threads` | | Şu anda ayıklanacak iş parçacığı listeler. |
| `$up`, `$u` | | Yığın izlemesinde geçerli çerçeve bir düzey yukarı. |
| `$where`, `$w`, `$bt` | Geçerli iş parçacığının çerçevelerini listeler. |

İşlemler, iş parçacıkları ve çağrı yığını gibi standart hata ayıklayıcı windows hata ayıklama etkileşimli penceresiyle eşitlenmez unutmayın. Etkin işlem, iş parçacığı veya hata ayıklama etkileşimli pencere çerçevede değiştirme diğer hata ayıklayıcı windows etkilemez. Benzer şekilde, etkin işlem, iş parçacığı veya diğer hata ayıklayıcı windows çerçevede değiştirme hata ayıklama etkileşimli pencere etkilemez.

Hata ayıklama etkileşimli pencere kendi üzerinden erişebilirsiniz seçenekleri ayarlanmış **Araçlar > Seçenekler > Python araçları > hata ayıklama etkileşimli pencere**. Her bir Python ortamı için ayrı bir örneği olan normal Python etkileşimli pencere farklı olarak yalnızca bir hata ayıklama etkileşimli penceresi yok ve her zaman ayıklanacak işlemi için Python yorumlayıcı kullanır. Bkz: [seçenekleri - hata ayıklama seçeneklerini](python-support-options-and-settings-in-visual-studio.md#debugging-options).

![Hata ayıklama etkileşimli pencere seçenekleri](media/debugging-interactive-options.png)

## <a name="see-also"></a>Ayrıca bkz.

Visual Studio hata ayıklayıcısı hakkında tam bilgi için bkz: [Visual Studio'da hata ayıklamayı](../debugger/debugger-feature-tour.md).