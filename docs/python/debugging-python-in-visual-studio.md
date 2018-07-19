---
title: Python kodunda hata ayıklama
description: Visual Studio'da hata ayıklama özellikleri özellikle kesme noktaları ayarlama, Adımlama, değerler geçirerek, özel durumlar arama ve etkileşimli pencerede hata ayıklama da dahil olmak üzere Python kodu için bir kılavuz.
ms.date: 07/13/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 14716aa85245dcbd7c1ba0bc85824f5a53bece2d
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39079829"
---
# <a name="debug-your-python-code"></a>Python kodunuzun hatalarını ayıklama

Yerel değişkenler, kesme noktaları, inceleme pencereler'deki içinde/out/üzerinden deyimleri, ayarlamak sonraki adım ve Visual Studio, Python, çalışan işlemlere, ekleme dahil olmak üzere izleme ifadelerinde değerlendirmek için kapsamlı bir hata ayıklama deneyimi sunar. Deyimi ve daha fazlası.

Ayrıca aşağıdaki senaryoya özgü hata ayıklama makalelere bakın:

- [Linux uzaktan hata ayıklama](debugging-python-code-on-remote-linux-machines.md)
- [Azure uzaktan hata ayıklama](debugging-remote-python-code-on-azure.md)
- [Python/C++ karışık mod hata ayıklaması](debugging-mixed-mode-c-cpp-python-in-visual-studio.md)
- [Karışık mod hata ayıklaması için semboller](debugging-symbols-for-mixed-mode-c-cpp-python.md)

|   |   |
|---|---|
| ![video kamera simgesini film](../install/media/video-icon.png "bir video izleyin") | [(Microsoft Virtual Academy) videoyu](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Debugging-Python-Ep5dp5LWE_3805918567) (3 m 32s) hata ayıklama Python tanıtımı için.|

<a name="debugging-without-a-project"></a>

> [!Tip]
> Visual Studio'da Python, bir proje hata ayıklamayı destekler. Tek başına Python dosyası ile açık Düzenleyicisi'nde sağ seçin **ile hata ayıklama Başlat**, ve Visual Studio genel varsayılan ortam komut dosyasını başlatır (bkz [Python ortamları](managing-python-environments-in-visual-studio.md)) ve bağımsız değişkenler. Ancak daha sonra tam hata ayıklama desteği gerekir.
>
> Ortamı ve bağımsız değişkenleri denetlemek için kolayca yapılır kod projesi oluşturma [mevcut Python'dan kod](managing-python-projects-in-visual-studio.md#creating-a-project-from-existing-files) proje şablonu.

<a name="debugging-with-a-project"></a>

## <a name="basic-debugging"></a>Temel hata ayıklama

Temel hata ayıklama iş akışından kod içerisinde ilerlemeye değerlerini inceleme ve aşağıdaki bölümlerde açıklandığı gibi özel durumları işleme ayarlarını kesme noktaları içerir.

İle hata ayıklama oturumu başlatır **hata ayıklama > hata ayıklamayı Başlat** komutu **Başlat** araç veya F5 tuşuna düğmesi. Bu Eylemler, projenizin başlangıç dosyasını başlatın (gösterilen Çözüm Gezgini'nde kalın) projenin etkin ortam ve komut satırı bağımsız değişkenleri veya proje özelliklerinde belirtilen arama yolları (bkz [proje hata ayıklama Seçenekleri](#project-debugging-options). **Visual Studio 2017 sürüm 15.6** ve daha sonra ayarlanmış bir başlangıç dosyası yoksa, sizi uyarır; önceki sürümlerinde çalışan Python yorumlayıcısı ile bir çıktı penceresini açın veya çıkış penceresine kısaca görüntülenir ve kaldırılır. Herhangi bir durumda, uygun dosya sağ tıklayıp **başlangıç dosyası olarak ayarla**.

> [!Note]
> Hata ayıklayıcı her zaman etkin Python ortamı proje için başlar. Ortamı değiştirmek için farklı bir tane aktif üzerinde açıklandığı gibi olun [seçerek bir proje için bir Python ortamı](selecting-a-python-environment-for-a-project.md).

### <a name="breakpoints"></a>Kesme noktaları

Program durumunu inceleyebilirsiniz. Bu nedenle işaretli bir noktada kod yürütme kesme noktaları durdurun. Sol kenar boşluğunu Kod Düzenleyicisi'ni veya bir kod satırı sağ tıklatıp seçerek tıklayarak kesme noktası ayarlama **kesme noktası > Kesme Noktası Ekle**. Her satırda bir kesme noktası ile kırmızı bir nokta belirir.

![Visual Studio'daki kesme noktaları](media/debugging-breakpoints.png)

Kırmızı nokta veya kod satırına sağ tıklayıp seçerek **kesme noktası > Sil kesme noktası** kesme noktası kaldırır. Ayrıca bunu kullanarak kaldırmadan devre dışı **kesme noktası > devre dışı kesme noktası** komutu.

> [!Note]
> Bazı kesme noktaları python'da şaşırtıcı diğer programlama dilleriyle hakkında deneyimli olduğunuzu geliştiriciler için olabilir. Herhangi bir üst düzey bir sınıf veya işlev tanımları işlenecek yüklendiğinde Python dosyası çalıştığında, Python tüm yürütülebilir kod dosyasıdır. Bir kesme noktası ayarlarsanız, hata ayıklayıcı kesme bölümü-şekilde bir sınıf bildirimine bulabilirsiniz. Doğru Bu davranışı bazen şaşırtıcı olmasına rağmen.

Koşullar altında bir kesme noktası, yalnızca bir değişken belirli bir değer veya değer aralığı için ayarlandığında bozucu gibi tetiklenir özelleştirebilirsiniz. Koşulları ayarlama, Kesme noktasının kırmızı nokta sağ tıklayın, seçin **koşul**, ardından ifadeleri Python kodu kullanarak oluşturun. Visual Studio'da bu özellik hakkında tam Ayrıntılar için bkz [kesme noktası koşulları](../debugger/using-breakpoints.md#breakpoint-conditions)

Koşullar ayarlarken de ayarlayabilirsiniz **eylem** ve çıkış penceresi için yürütmeyi isteğe bağlı olarak otomatik olarak devam günlüğe kaydedilecek iletinin oluşturun. Bir iletiyi günlüğe kaydetmeyi oluşturur ne adlı bir *İzleme noktası* günlüğe kaydetme koduna doğrudan uygulamanıza ekleme olmadan:

![İzleme noktası ile bir kesme noktası oluşturma](media/debugging-tracepoint.png)

### <a name="stepping-through-code"></a>Kod boyunca ilerleme

Bir kesme noktasında durduruldu sonra kodunuz içinde adım adım veya yeniden kesmeden önce kod bloklarını çalıştırmak için çeşitli yollar vardır. Bu komutlar yerler üst hata ayıklama araç çubuğu dahil olmak üzere, bir süre içinde kullanılabilir **hata ayıklama** menüsünde klavye kısayolları ve Kod Düzenleyicisi'nde sağ bağlam menüsünü (tüm komutları olan tüm konumları):

| Özellik | Tuş vuruşu | Açıklama |
| --- | --- | --- |
| Devam et | F5 | Kod, sonraki kesme noktasına ulaşılıncaya kadar çalışır. |
| Adımla | F11 | Sonraki deyimi çalıştırır ve durdurur. Sonraki ifade bir işlev çağrısı ise, hata ayıklayıcı çağrılan işlevin ilk satırına durdurur. |
| Üzerinden adımla | F10 | (Çalışan tüm kodun) bir işlev çağrısını yapmadan dahil olmak üzere, sonraki deyimi çalıştırır ve herhangi bir dönüş değeri uygulanıyor. Üzerinden Adımlama kolayca hata ayıklama gerekmez işlevleri atlamanızı sağlar. |
| Dışına adımla | Shift+F11 | Kod için çağırma deyimine adımları sonra geçerli işlevin sonuna kadar çalışır.  Bu komut, geçerli işlevin geri kalanında hata ayıklamak ihtiyacınız kalmadığında yararlıdır. |
| İmlece kadar Çalıştır | Ctrl+F10 | Kod Düzenleyicisi'nde şapka konumuna çalıştırır. Bu komut bir parçası olduğundan, hata ayıklamak için ihtiyacınız olmayan kod üzerinde kolayca atlamanızı sağlar. |
| Sonraki Deyimi Belirle | Ctrl+Shift+F10 | Giriş işareti konumuna kod noktası çalıştırma geçerli değiştirir. Bu komut tüm çalıştırılan kodun bir parçasını atlamak sağlar, bildiğinizde gibi kod bozuk veya üretir ve istenmeyen yan etkisi. |
| Sonraki bildirimi Göster | Alt+Num * | Sonraki deyimi çalıştırmak için döndürür. Bu komut, kodunuzda arıyorsunuz geçici bir çözüm ve hata ayıklayıcı durduğu hatırlamıyorum yararlıdır. |

### <a name="inspecting-and-modifying-values"></a>İnceleme ve değerleri değiştirme

Hata ayıklayıcıda durdurulduklarında inceleyin ve değişkenlerin değerlerini değiştirin. Bağımsız değişkenleri yanı sıra özel ifadeler izlemek için izleme penceresinde de kullanabilirsiniz. (Bkz [değişkenleri İnceleme](../debugger/getting-started-with-the-debugger.md#inspect-variables-with-the-autos-and-locals-windows) genel ayrıntılar için.)

Veri ipuçlarını kullanarak bir değeri görüntülemek için basitçe düzenleyicisinde herhangi bir değişken üzerinde fare gelin. Değeri değiştirmek için tıklayabilirsiniz:

![DataTips, hata ayıklayıcı](media/debugging-quick-tips.png)

Otomatik değişkenler penceresi (**hata ayıklama > Windows > Otolar**) değişkenleri ve yakın geçerli deyim ifadeleri içerir. Değer sütununu çift tıklatın veya seçin ve değeri düzenlemek için F2 tuşuna basın:

![Hata ayıklayıcı otomatik değişkenler penceresi](media/debugging-autos-window.png)

Yerel öğeler penceresinde (**hata ayıklama > Windows > Yereller**) yeniden düzenlenebilir geçerli kapsamda olan tüm değişkenlere görüntüler:

![Hata ayıklayıcı yerel öğeler penceresinde](media/debugging-locals-window.png)

Otolar ve yerel öğeler kullanma hakkında daha fazla bilgi için bkz. [Otolar ve yerel öğeler Windows değişkenler inceleyerek](../debugger/autos-and-locals-windows.md).

İzleme pencereleri (**hata ayıklama > Windows > İzleme > 1-4 izleyin**) rastgele Python ifadelerini girin ve sonuçları görüntülemek izin. İfadeler her adım için değerlendirilerek:

![İzleme penceresi hata ayıklayıcısı](media/debugging-watch-window.png)

Watch kullanma hakkında daha fazla bilgi için bkz. [bir izleme izleme ve QuickWatch Windows kullanarak değişkenlerde ayarlama](../debugger/watch-and-quickwatch-windows.md).

Bir dize değeri inceledi olduğunda (`str`, `unicode`, `bytes`, ve `bytearray` tüm dizeleri bu amaca yönelik olarak kabul edilir), değeri sağ tarafında bir Büyüteç simgesi görünür. Simgeye tıklayarak uzun dizeler için yararlı olan tırnak işareti olmayan bir dize değeri sarmalama ve kaydırmayı, açılan iletişim kutusunda görüntüler. Ayrıca, açılan ok simgesini seçerek, düz metin seçmenizi sağlar HTML, XML ve JSON görselleştirmeler:

![Dize görselleştiriciler](media/debugging-string-visualizers.png)

HTML, XML ve JSON görselleştirmeler ayrı açılır pencereleri söz dizimi vurgulama ve ağaç görünümleri ile görünür.

### <a name="exceptions"></a>Özel Durumlar

Hata ayıklama sırasında programınızdaki bir hata meydana gelir, ancak bunun için bir özel durum işleyicisi yok, hata ayıklayıcı özel durum noktasında keser:

![Özel durum açılan menüsü](media/debugging-exception-popup.png)

Bu noktada çağrı yığını da dahil olmak üzere program durumunu inceleyebilirsiniz. Ancak, kodunuz içinde adım adım denerseniz, özel durum ya da işlenir veya programınızın çıkar kadar oluşturulan devam eder.

**Hata ayıklama > Windows > özel durum ayarları** menü komutu genişletin bir penceresi getirir **Python özel durumları**:

![Özel durumlar penceresi](media/debugging-exception-settings.png)

Her özel durum denetimleri için onay kutusunu olmadığını hata ayıklayıcı *her zaman* keser olduğunda ortaya çıkar. Daha sık için belirli bir özel durumun kesmek istediğinizde bu kutuyu işaretleyin.

Kaynak kodunda özel durum işleyicisi bulunamadığında varsayılan olarak, çoğu özel durumların bölün. Bu davranışı değiştirmek için herhangi bir özel durum sağ tıklayın ve değiştirmek **devam yaparken işlenmemiş kullanıcı kodunda** seçeneği. Daha az sıklıkta için bir özel durum kesmek istediğinizde bu kutusunun işaretini kaldırın.

Bu listede görünmeyen bir özel durum yapılandırmak için tıklayın **Ekle** düğmesi ekleyin. Özel durumun tam adı eşleşmelidir.

## <a name="project-debugging-options"></a>Proje hata ayıklama seçenekleri

Varsayılan olarak, hata ayıklayıcı, programınızın standart Python başlatıcısı, hiçbir komut satırı bağımsız değişkenleri ve başka hiçbir özel yollar veya koşullar ile başlatır. Başlatma seçeneklerini, Çözüm Gezgini'nde projenize sağ tıklayarak erişilen projenin hata ayıklama özellikleri aracılığıyla değiştirilirse seçerek **özellikleri**, seçerek **hata ayıklama** sekmesi.

![Proje hata ayıklama özellikleri](media/debugging-project-properties.png)

### <a name="launch-mode-options"></a>Modu seçeneklerini başlatma

| Seçenek | Açıklama |
| --- | --- |
| Standart Python Başlatıcısı | CPython, IronPython ve Stackless Python gibi çeşitler uyumludur taşınabilir python'da yazılan kod hata ayıklamayı kullanır. Bu, saf Python kodunda hata ayıklama için en iyi deneyimi sağlar. Çalışan bir eklediğiniz zaman `python.exe` işlem, bu Başlatıcısı kullanılır. Bu Başlatıcı ayrıca sağlar [karışık mod hata ayıklama](debugging-mixed-mode-c-cpp-python-in-visual-studio.md) CPython için C/C++ kodu ve Python kodu arasında sorunsuz bir şekilde adım etmenize imkan sağlar. |
| Web Başlatıcısı | Varsayılan tarayıcınız başlatma sırasında başlatılır ve şablonları hata ayıklamasını etkinleştirir. Bkz: [Web şablonuna ilişkin hata ayıklama](python-web-application-project-templates.md#debugging) bölümünde daha fazla bilgi için. |
| Django Web Başlatıcısı | Aynı Web Başlatıcısı'nı ve yalnızca geriye dönük uyumluluk gösterilir. |
| IronPython (.NET) Başlatıcısı | .NET hata ayıklayıcı, IronPython yalnızca hangi çalışır kullanır ancak C# ve VB'nin dahil olmak üzere herhangi bir .NET dil projesine arasında atlamak için izin verir IronPython barındıran çalışan bir .NET işleme eklerseniz bu Başlatıcısı kullanılır. |

### <a name="run-options-search-paths-startup-arguments-and-environment-variables"></a>Çalıştırma Seçenekleri (arama yolları, başlangıç bağımsız değişkenleri ve ortam değişkenlerini)

| Seçenek | Açıklama |
| --- | --- |
| Arama yolları | Çözüm Gezgini'nde, projenin arama yollarını düğümünde gösterilen bu değerlerin eşleşmesi. Burada bu değeri değiştirebilirsiniz, ancak çözüm klasörleri göz atmanıza olanak sağlar ve otomatik olarak yolları göreli biçimine dönüştürür Gezgini kullanmak daha kolaydır. |
| Betik bağımsız değişkenleri | Bu bağımsız değişkenler komut dosyanızın filename sonra görünen betiğinizi başlatmak için kullanılan komut eklenir. İlk öğe İşte betiğinizi kullanılabilir `sys.argv[1]`olarak ikinci `sys.argv[2]`ve benzeri. |
| Yorumlayıcı bağımsız değişkenleri | Bu bağımsız komut dosyanız adının önünde Başlatıcısı komut satırına eklenir. Genel bağımsız değişkenler burada `-W ...` denetimi uyarılar için `-O` biraz programınızı iyileştirmek için ve `-u` arabellekten çıkarılan g/ç kullanılacak. IronPython kullanıcıları geçirmek için bu alan kullanması muhtemel `-X` gibi seçenekleri `-X:Frames` veya `-X:MTA`. |
| Cesta k İnterpretu | Geçerli ortam ile ilişkili yolu geçersiz kılar.  değer bir standart yorumlayıcı komut dosyanızı başlatmak için yararlı olabilir. |
| Ortam Değişkenleri | Bu çok satırlı metin kutusuna form girişlerini ekleme `NAME=VALUE`. Bu ayar son olarak, var olan tüm genel ortam değişkenlerini ve sonra üstte uygulandığından `PYTHONPATH` ayarlanır arama yollarını ayarına göre bunu el ile bu bulunanlardan herhangi biri diğer değişkenlerini geçersiz kılmak için kullanılabilir. |

<a name="the-debug-interactive-window"></a>

## <a name="immediate-and-interactive-windows"></a>Hemen ve etkileşimli windows

Hata ayıklama oturumu sırasında kullanabileceğiniz iki etkileşimli pencere vardır: standart Visual Studio komut penceresi ve hata ayıklama Python etkileşimli penceresinde.

Komut penceresi (**hata ayıklama > Windows > hemen**) Python ifadelerin ve İnceleme hızlı değerlendirme veya değişkenlerin çalışan bir program içerisinde atama için kullanılır. Bkz: Genel [komut penceresi](../ide/reference/immediate-window.md) makale Ayrıntılar için.

Hata ayıklama Python etkileşimli penceresinde (**hata ayıklama > Windows > hata ayıklama Python etkileşimli**) tam kolaylaştırır gibi daha zengin olmasının [etkileşimli REPL](python-interactive-repl-in-visual-studio.md) hata ayıklama sırasında yazma dahil olmak üzere kullanılabilir deneyimi ve Çalışan kodu. Standart Python Başlatıcısı'nı kullanarak hata ayıklayıcıda çalışmaya herhangi bir işlem otomatik olarak bağlanır (işlemler de dahil olmak üzere bağlı aracılığıyla **hata ayıklama > iliştirme**). Ancak, C/C++ karışık mod hata ayıklaması kullanırken kullanılabilir değilse.

![Python hata ayıklama etkileşimli penceresi](media/debugging-interactive.png)

Hata ayıklama etkileşimli pencereye ek olarak, özel meta-komutları destekler [standart REPL komutları](python-interactive-repl-in-visual-studio.md#meta-commands):

| Komut | Arguments | Açıklama |
| --- | --- | --- |
| `$continue`, `$cont`, `$c` | Geçerli deyimden programı çalıştırmaya başlar. |
| `$down`, `$d` | Geçerli çerçeve bir düzey aşağıya yığın izlemesi taşıyın. |
| `$frame` | | Geçerli çerçeve kimliğini görüntüler.
| `$frame` | Çerçeve kimliği | Geçerli çerçevenin belirtilen çerçeve kimliğe geçer.
| `$load` | Komut dosyasını yükler ve tamamlanana kadar yürütür |
| `$proc` |  | Geçerli işlem kimliğini görüntüler. |
| `$proc` | işlem kimliği | Geçerli işlem için belirtilen işlem kimliği geçer. |
| `$procs` | | Şu anda hataları ayıklanan işlemlerin listeler. |
| `$stepin`, `$step`, `$s` | Sonraki işlev çağrısı, eğer mümkünse adımlamayla girin. |
| `$stepout`, `$return`, `$r` | Geçerli işlev dışında adımları. |
| `$stepover`, `$until`, `$unt` | Sonraki işlev deyime çağırın. |
| `$thread` | | Geçerli iş parçacığı kimliğini görüntüler. |
| `$thread` | iş parçacığı kimliği | Geçerli iş parçacığı için belirtilen iş parçacığı kimliği geçer. |
| `$threads` | | Şu anda hataları ayıklanmakta olan iş parçacıkları listeler. |
| `$up`, `$u` | | Yığın izlemeyle uygulamanızda geçerli çerçeve bir düzey yukarı. |
| `$where`, `$w`, `$bt` | Geçerli iş parçacığı çerçevelerini listeler. |

Standart hata ayıklayıcı pencereleri işlemler, iş parçacıkları ve çağrı yığını gibi hata ayıklama etkileşimli pencere ile eşitlenmez unutmayın. Etkin işlem, iş parçacığı veya hata ayıklama etkileşimli pencerede çerçeve değiştirilmesi, diğer hata ayıklayıcı pencereleri etkilemez. Benzer şekilde, etkin işlem, iş parçacığı veya bir hata ayıklayıcı pencerelerinde çerçeve değiştirilmesi hata ayıklama etkileşimli pencereye etkilemez.

Hata ayıklama etkileşimli pencere, kendi aracılığıyla erişebileceğiniz seçenekleri ayarlanmış **Araçlar > Seçenekler > Python araçları > Etkileşimli penceresi hata ayıklama**. Her bir Python ortamı için ayrı bir örneği olan normal Python etkileşimli penceresinde, aksine yalnızca bir hata ayıklama etkileşimli pencerede ve her zaman ayıklanan işlemin Python yorumlayıcısı kullanır. Bkz: [seçenekleri - hata ayıklama seçenekleri](python-support-options-and-settings-in-visual-studio.md#debugging-options).

![Hata ayıklama etkileşimli penceresi seçenekleri](media/debugging-interactive-options.png)

## <a name="use-the-experimental-debugger"></a>Deneysel hata ayıklayıcısını kullan

Visual Studio 2017 Preview 4.0 ile başlayarak, "4.1 + ptvsd sürümü temel Deneysel hata ayıklayıcısını" kullanarak tercih edebilirsiniz. Katılım için seçin **Araçları** > **seçenekleri** menü komutunu ve ardından gitmek **Python** > **Deneysel**Seçenekler iletişim kutusu seçip **Deneysel hata ayıklayıcısını kullanın.**

Deneysel hata ayıklayıcı, aşağıdaki tabloda açıklandığı gibi yalnızca sınırlı Python ortamları ile uyumludur:

| Python sürümü | Deneysel hata ayıklayıcısı ile uyumlu |
| --- | --- |
| 2.6 | Hayır |
| 2.7 | Evet |
| 3.1 için 3.4 | Hayır |
| 3.5 ve sonraki sürümler | Evet |
| IronPython | Hayır |

Deneysel hata ayıklayıcısı ile uyumlu bir ortam kullanmayı denerseniz, Visual Studio hatayı gösterir, "Hata ayıklayıcı bu ortamı ile uyumlu değil":

![Deneysel hata ayıklayıcısını kullanarak hata ayıklayıcı bu ortam hatası ile uyumlu değil](media/debugging-experimental-incompatible-error.png)

Seçin **Deneysel hata ayıklayıcısını devre dışı** komutu, hangi temizler **Deneysel hata ayıklayıcısını** seçeneği.

> [!Note]
> Uyarı şu anda Python 3.3 ve 3.4 gösterilmez.

Geçerli ortama (örneğin, bir önceki 4.0.x sürümü sürümü uzaktan hata ayıklama için gereken bir 3.x) ptvsd daha eski bir sürümünü yüklediyseniz Visual Studio hatası "hata ayıklayıcısı paket yüklenemedi" ya da uyarı "hata ayıklayıcısı paket gösterir. güncel değil":

![Hata ayıklayıcısı paket Deneysel hata ayıklayıcısını kullanarak yüklenen hata bulunamadı](media/debugging-experimental-version-error.png)

![Hata ayıklayıcısı paket Deneysel hata ayıklayıcısını kullanarak uyarı güncel değil](media/debugging-experimental-version-warning.png)

Ptvsd yüklemenizi yönetmek için kullandığınız **paketleri** sekmesinde **Python ortamları** penceresi ya da komut satırından aşağıdaki komutları kullanın:

```ps
# Uninstalling ptvsd causes VS to default to its bundled 4.1.x version.
pip uninstall ptvsd

# Upgrading ptvsd gives you the latest version, which may be newer than the bundled version.
# -pre is required to allow pre-release versions as currently required by the experimental debugger.
pip install --upgrade ptvsd -pre
```

> [!Important]
> Ptvsd'ün bazı sürümleri için bir uyarıyı yoksaymak seçebilirsiniz ancak Visual Studio doğru şekilde çalışmayabilir.

## <a name="see-also"></a>Ayrıca bkz.

Visual Studio hata ayıklayıcı tüm ayrıntılar için bkz. [Visual Studio'da hata ayıklama](../debugger/debugger-feature-tour.md).
