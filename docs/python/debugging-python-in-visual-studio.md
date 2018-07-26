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
ms.openlocfilehash: de11159e513468a543229df5aab640142b006736
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39251939"
---
# <a name="debug-your-python-code"></a>Python kodunuzun hatalarını ayıklama

Visual Studio, Python, çalışan işlemlere, ekleme dahil olmak üzere, ifadeleri değerlendirme için kapsamlı bir hata ayıklama deneyimi sunar **Watch** ve **hemen** windows, yerel inceleniyor değişkenleri, kesme noktaları, / out/üzerinden deyimleri adım **sonraki deyimi Ayarla**ve daha fazlası.

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
> Ortamı ve bağımsız değişkenleri denetlemek için kolayca yapılır kod projesi oluşturma [mevcut Python'dan kod](managing-python-projects-in-visual-studio.md#create-a-project-from-existing-files) proje şablonu.

<a name="debugging-with-a-project"></a>

## <a name="basic-debugging"></a>Temel hata ayıklama

Temel hata ayıklama iş akışından kod içerisinde ilerlemeye değerlerini inceleme ve aşağıdaki bölümlerde açıklandığı gibi özel durumları işleme ayarlarını kesme noktaları içerir.

İle hata ayıklama oturumu başlatır **hata ayıklama** > **hata ayıklamayı Başlat** komutu **Başlat** araç çubuğundan veya **F5**anahtarı. Bu Eylemler, projenizin başlangıç dosyasını başlatın (gösterilen kalın **Çözüm Gezgini**) projenin etkin ortam ve komut satırı bağımsız değişkenleri veya içinde belirtilen arama yollarını **proje Özellikleri** (bkz [proje hata ayıklama seçenekleri](#project-debugging-options)). **Visual Studio 2017 sürüm 15.6** ve daha sonra ayarlanmış bir başlangıç dosyası yoksa, sizi uyarır; önceki sürümlerinde çalışan Python yorumlayıcısı ile bir çıktı penceresini açın veya çıkış penceresine kısaca görüntülenir ve kaldırılır. Herhangi bir durumda, uygun dosya sağ tıklayıp **başlangıç dosyası olarak ayarla**.

> [!Note]
> Hata ayıklayıcı her zaman etkin Python ortamı proje için başlar. Ortamı değiştirmek için farklı bir tane aktif üzerinde açıklandığı gibi olun [bir proje için bir Python ortamını seçin](selecting-a-python-environment-for-a-project.md).

### <a name="breakpoints"></a>Kesme noktaları

Program durumunu inceleyebilirsiniz. Bu nedenle işaretli bir noktada kod yürütme kesme noktaları durdurun. Sol kenar boşluğunu Kod Düzenleyicisi'ni veya bir kod satırı sağ tıklatıp seçerek tıklayarak kesme noktası ayarlama **kesme noktası** > **kesme noktası Ekle**. Her satırda bir kesme noktası ile kırmızı bir nokta belirir.

![Visual Studio'daki kesme noktaları](media/debugging-breakpoints.png)

Kırmızı nokta veya kod satırına sağ tıklayıp seçerek **kesme noktası** > **Sil kesme noktası** kesme noktası kaldırır. Ayrıca bunu kullanarak kaldırmadan devre dışı **kesme noktası** > **devre dışı kesme noktası** komutu.

> [!Note]
> Bazı kesme noktaları python'da şaşırtıcı diğer programlama dilleriyle hakkında deneyimli olduğunuzu geliştiriciler için olabilir. Herhangi bir üst düzey bir sınıf veya işlev tanımları işlenecek yüklendiğinde Python dosyası çalıştığında, Python tüm yürütülebilir kod dosyasıdır. Bir kesme noktası ayarlarsanız, hata ayıklayıcı kesme bölümü-şekilde bir sınıf bildirimine bulabilirsiniz. Bazen şaşırtıcı olmasına rağmen bu davranışı doğrudur.

Koşullar altında bir kesme noktası, yalnızca bir değişken belirli bir değer veya değer aralığı için ayarlandığında bozucu gibi tetiklenir özelleştirebilirsiniz. Koşulları ayarlama, Kesme noktasının kırmızı nokta sağ tıklayın, seçin **koşul**, ardından ifadeleri Python kodu kullanarak oluşturun. Visual Studio'da bu özellik hakkında tam Ayrıntılar için bkz [kesme noktası durumlarını](../debugger/using-breakpoints.md#breakpoint-conditions).

Koşullar ayarlarken de ayarlayabilirsiniz **eylem** ve çıkış penceresi için yürütmeyi isteğe bağlı olarak otomatik olarak devam günlüğe kaydedilecek iletinin oluşturun. Bir iletiyi günlüğe kaydetmeyi oluşturur ne adlı bir *İzleme noktası* günlüğe kaydetme koduna doğrudan uygulamanıza ekleme olmadan:

![İzleme noktası ile bir kesme noktası oluşturma](media/debugging-tracepoint.png)

### <a name="step-through-code"></a>Kodunuz içinde adım adım

Bir kesme noktasında durduruldu sonra kodunuz içinde adım adım veya yeniden kesmeden önce kod bloklarını çalıştırmak için çeşitli yollar vardır. Bu komutlar yerler üst hata ayıklama araç çubuğu dahil olmak üzere, bir süre içinde kullanılabilir **hata ayıklama** menüsünde klavye kısayolları ve Kod Düzenleyicisi'nde sağ bağlam menüsünü (tüm komutları tüm konumları değildir):

| Özellik | Tuş vuruşu | Açıklama |
| --- | --- | --- |
| **Devam et** | **F5** | Kod, sonraki kesme noktasına ulaşılıncaya kadar çalışır. |
| **Adımla** | **F11** | Sonraki deyimi çalıştırır ve durdurur. Sonraki ifade bir işlev çağrısı ise, hata ayıklayıcı çağrılan işlevin ilk satırına durdurur. |
| **Üzerinden adımla** | **F10** | (Çalışan tüm kodun) bir işlev çağrısını yapmadan dahil olmak üzere, sonraki deyimi çalıştırır ve herhangi bir dönüş değeri uygulanıyor. Üzerinden Adımlama kolayca hata ayıklama gerekmez işlevleri atlamanızı sağlar. |
| **Dışına adımla** | **Shift**+**F11** | Kod için çağırma deyimine adımları sonra geçerli işlevin sonuna kadar çalışır.  Bu komut, geçerli işlevin geri kalanında hata ayıklamak ihtiyacınız kalmadığında yararlıdır. |
| **İmlece kadar Çalıştır** | **CTRL**+**F10** | Kod Düzenleyicisi'nde şapka konumuna çalıştırır. Bu komut bir parçası olduğundan, hata ayıklamak için ihtiyacınız olmayan kod üzerinde kolayca atlamanızı sağlar. |
| **Sonraki deyimi belirle** | **CTRL**+**Shift**+**F10** | Giriş işareti konumuna kod noktası çalıştırma geçerli değiştirir. Bu komut, gibi bildiğiniz kodu bozuk veya istenmeyen bir yan etkisi üretir, çalıştırılan kodun bir parçasını atlamak sağlar. |
| **Sonraki bildirimi Göster** | **Alt**+**Num**+**&#42;**| Sonraki deyimi çalıştırmak için döndürür. Bu komut, kodunuzda arıyorsunuz geçici bir çözüm ve hata ayıklayıcı durduğu hatırlamıyorum yararlıdır. |

### <a name="inspect-and-modify-values"></a>Denetleme ve değerleri değiştirme

Hata ayıklayıcıda durdurulduklarında inceleyin ve değişkenlerin değerlerini değiştirin. Ayrıca **Watch** bağımsız değişkenleri yanı sıra özel ifadeleri İzleme penceresinde. (Bkz [değişkenleri denetleyin](../debugger/getting-started-with-the-debugger.md#inspect-variables-with-the-autos-and-locals-windows) genel ayrıntılar için.)

Kullanarak bir değeri görüntülemek için **DataTips**, fare düzenleyicisinde herhangi bir değişken yalnızca üzerine gelin. Değeri değiştirmek için tıklayabilirsiniz:

![DataTips, hata ayıklayıcı](media/debugging-quick-tips.png)

**Otolar** penceresi (**hata ayıklama** > **Windows** > **Otolar**) değişkenleri ve ifadeleri içeriyor, Geçerli deyimi yakın olan. Değer sütunu veya seçin ve ENTER tuşuna çift tıklayabilirsiniz **F2** değerini düzenlemek için:

![Hata ayıklayıcı otomatik değişkenler penceresi](media/debugging-autos-window.png)

**Yereller** penceresi (**hata ayıklama** > **Windows** > **Yereller**) bulunan tüm değişkenleri görüntüler Geçerli kapsam, yeniden düzenlenebilir:

![Hata ayıklayıcı yerel öğeler penceresinde](media/debugging-locals-window.png)

Daha fazla üzerinde kullanma **Otolar** ve **Yereller**, bkz: [Otolar ve yerel öğeler pencerelerinde değişkenleri denetleyin](../debugger/autos-and-locals-windows.md).

**Watch** windows (**hata ayıklama** > **Windows** > **Watch**  >   **1-4 izleyin**) rastgele Python ifadelerini girin ve sonuçları görüntülemeniz olanak sağlar. İfadeler her adım için değerlendirilerek:

![İzleme penceresi hata ayıklayıcısı](media/debugging-watch-window.png)

Daha fazla üzerinde kullanma **izleme**, bkz: [izleme ve QuickWatch pencerelerini kullanarak değişkenler üzerinde bir izleme ayarlama](../debugger/watch-and-quickwatch-windows.md).

Bir dize değeri incelerken (`str`, `unicode`, `bytes`, ve `bytearray` tüm dizeleri bu amaca yönelik olarak kabul edilir), değeri sağ tarafında bir Büyüteç simgesi görünür. Simgeye tıklayarak uzun dizeler için yararlı olan tırnak işareti olmayan bir dize değeri sarmalama ve kaydırmayı, açılan iletişim kutusunda görüntüler. Ayrıca, açılan ok simgesini seçerek, düz metin seçmenizi sağlar HTML, XML ve JSON görselleştirmeler:

![Dize görselleştiriciler](media/debugging-string-visualizers.png)

HTML, XML ve JSON görselleştirmeler ayrı açılır pencereleri söz dizimi vurgulama ve ağaç görünümleri ile görünür.

### <a name="exceptions"></a>Özel Durumlar

Hata ayıklama sırasında programınızdaki bir hata meydana gelir, ancak bunun için bir özel durum işleyicisi yok, hata ayıklayıcı özel durum noktasında keser:

![Özel durum açılan menüsü](media/debugging-exception-popup.png)

Bu noktada çağrı yığını da dahil olmak üzere program durumunu inceleyebilirsiniz. Ancak, kodunuz içinde adım adım denerseniz, özel durum ya da işlenir veya programınızın çıkar kadar oluşturulan devam eder.

**Hata ayıklama** > **Windows** > **özel durum ayarları** menü komutu genişletin bir penceresi getirir **Python Özel durumlar**:

![Özel durumlar penceresi](media/debugging-exception-settings.png)

Her özel durum denetimleri için onay kutusunu olmadığını hata ayıklayıcı *her zaman* keser olduğunda ortaya çıkar. Daha sık için belirli bir özel durumun kesmek istediğinizde bu kutuyu işaretleyin.

Kaynak kodunda özel durum işleyicisi bulunamadığında varsayılan olarak, çoğu özel durumların bölün. Bu davranışı değiştirmek için herhangi bir özel durum sağ tıklayın ve değiştirmek **devam yaparken işlenmemiş kullanıcı kodunda** seçeneği. Daha az sıklıkta için bir özel durum kesmek istediğinizde bu kutusunun işaretini kaldırın.

Bu listede görünmeyen bir özel durum yapılandırmak için tıklayın **Ekle** düğmesi ekleyin. Özel durumun tam adı eşleşmelidir.

## <a name="project-debugging-options"></a>Proje hata ayıklama seçenekleri

Varsayılan olarak, hata ayıklayıcı, programınızın standart Python başlatıcısı, hiçbir komut satırı bağımsız değişkenleri ve başka hiçbir özel yollar veya koşullar ile başlatır. Başlangıç seçenekleri, projenize sağ tıklayarak erişilen projenin hata ayıklama özellikleri aracılığıyla değiştirilirse **Çözüm Gezgini**u seçerek **özellikleri**, seçerek **hata ayıklama**  sekmesi.

![Proje hata ayıklama özellikleri](media/debugging-project-properties.png)

### <a name="launch-mode-options"></a>Modu seçeneklerini başlatma

| Seçenek | Açıklama |
| --- | --- |
| **Standart Python Başlatıcısı** | CPython, IronPython ve Stackless Python gibi çeşitler uyumludur taşınabilir python'da yazılan kod hata ayıklamayı kullanır. Bu, saf Python kodunda hata ayıklama için en iyi deneyimi sağlar. Çalışan bir eklediğiniz zaman *python.exe* işlem, bu Başlatıcısı kullanılır. Bu Başlatıcı ayrıca sağlar [karışık mod hata ayıklama](debugging-mixed-mode-c-cpp-python-in-visual-studio.md) CPython için C/C++ kodu ve Python kodu arasında sorunsuz bir şekilde adım etmenize imkan sağlar. |
| **Web Başlatıcısı** | Varsayılan tarayıcınız başlatma sırasında başlatılır ve şablonları hata ayıklamasını etkinleştirir. Bkz: [Web şablonuna ilişkin hata ayıklama](python-web-application-project-templates.md#debugging) bölümünde daha fazla bilgi için. |
| **Django Web Başlatıcısı** | Aynı Web Başlatıcısı'nı ve yalnızca geriye dönük uyumluluk gösterilir. |
| **IronPython (.NET) Başlatıcısı** | .NET hata ayıklayıcı, IronPython yalnızca hangi çalışır kullanır ancak C# ve VB'nin dahil olmak üzere herhangi bir .NET dil projesine arasında atlamak için izin verir IronPython barındıran çalışan bir .NET işleme eklerseniz bu Başlatıcısı kullanılır. |

### <a name="run-options-search-paths-startup-arguments-and-environment-variables"></a>Çalıştırma Seçenekleri (arama yolları, başlangıç bağımsız değişkenleri ve ortam değişkenlerini)

| Seçenek | Açıklama |
| --- | --- |
| **Arama yolları** | ' Nde projenin arama yollarını düğümünde gösterilen bu değerlerin eşleşmesi **Çözüm Gezgini**. Burada bu değeri değiştirebilirsiniz, ancak bunu daha kolay olan kullanın **Çözüm Gezgini** klasörlere göz atmanıza olanak tanır ve yolları göreli forma otomatik olarak dönüştürür. |
| **Betik bağımsız değişkenleri** | Bu bağımsız değişkenler komut dosyanızın filename sonra görünen betiğinizi başlatmak için kullanılan komut eklenir. İlk öğe İşte betiğinizi kullanılabilir `sys.argv[1]`olarak ikinci `sys.argv[2]`ve benzeri. |
| **Yorumlayıcı bağımsız değişkenleri** | Bu bağımsız komut dosyanız adının önünde Başlatıcısı komut satırına eklenir. Genel bağımsız değişkenler burada `-W ...` denetimi uyarılar için `-O` biraz programınızı iyileştirmek için ve `-u` arabellekten çıkarılan g/ç kullanılacak. IronPython kullanıcıları geçirmek için bu alan kullanması muhtemel `-X` gibi seçenekleri `-X:Frames` veya `-X:MTA`. |
| **Cesta k İnterpretu** | Geçerli ortam ile ilişkili yolu geçersiz kılar. Değer bir standart yorumlayıcı komut dosyanızı başlatmak için yararlı olabilir. |
| **Ortam Değişkenleri** | Bu çok satırlı metin kutusuna form girişlerini ekleme \<adı > =\<değer >. Bu ayar son olarak, var olan tüm genel ortam değişkenlerini ve sonra üstte uygulandığından `PYTHONPATH` ayarlanır arama yollarını ayarına göre bunu el ile bu bulunanlardan herhangi biri diğer değişkenlerini geçersiz kılmak için kullanılabilir. |

<a name="the-debug-interactive-window"></a>

## <a name="immediate-and-interactive-windows"></a>Hemen ve etkileşimli windows

Hata ayıklama oturumu sırasında kullanabileceğiniz iki etkileşimli pencere vardır: standart Visual Studio **hemen** penceresinde ve **Python etkileşimli hata ayıklama** penceresi.

**Hemen** penceresi (**hata ayıklama** > **Windows** > **hemen**) hızlı değerlendirmesi için kullanılır Python ifadeleri ve inceleme veya değişkenlerin çalışan bir program içerisinde atama. Bkz: Genel [komut penceresi](../ide/reference/immediate-window.md) makale Ayrıntılar için.

**Python etkileşimli hata ayıklama** penceresi (**hata ayıklama** > **Windows** > **Python etkileşimli hata ayıklama**) olan tam kolaylaştırır gibi daha zengin [etkileşimli REPL](python-interactive-repl-in-visual-studio.md) hata ayıklarken, yazma ve çalıştırma kod dahil olmak üzere kullanılabilir karşılaşırsınız. Standart Python Başlatıcısı'nı kullanarak hata ayıklayıcıda çalışmaya herhangi bir işlem otomatik olarak bağlanır (işlemler de dahil olmak üzere bağlı aracılığıyla **hata ayıklama** > **iliştirme**). Ancak, C/C++ karışık mod hata ayıklaması kullanırken kullanılabilir değilse.

![Python hata ayıklama etkileşimli penceresi](media/debugging-interactive.png)

**Hata ayıklama etkileşimli** penceresi destekleyen ek olarak, özel meta-komutları [standart REPL komutları](python-interactive-repl-in-visual-studio.md#meta-commands):

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

Standart windows gibi hata ayıklayıcı, Not **işlemleri**, **iş parçacıkları**, ve **çağrı yığını** ile eşitlenmemiş **etkileşimli hata ayıklama** penceresi. Etkin işlemi, iş parçacığı veya çerçevede değiştirme **hata ayıklama etkileşimli** penceresi bir hata ayıklayıcı pencereleri etkilemez. Benzer şekilde, etkin işlem, iş parçacığı veya bir hata ayıklayıcı pencerelerinde çerçeve değiştirme etkilemez **hata ayıklama etkileşimli** penceresi.

**Hata ayıklama etkileşimli** penceresine sahip kendi aracılığıyla erişebileceğiniz seçenekleri kümesi **Araçları** > **seçenekleri**  >   **Python Araçları** > **hata ayıklama, etkileşimli Pencere'ye**. Normal aksine **Python etkileşimli** yalnızca biri, her bir Python ortam için ayrı bir örneği var olan bir pencere **hata ayıklama etkileşimli** penceresi ve her zaman için Python yorumlayıcısı kullanır hataları ayıklanan işlem. Bkz: [seçenekleri - hata ayıklama seçenekleri](python-support-options-and-settings-in-visual-studio.md#debugging-options).

![Hata ayıklama etkileşimli penceresi seçenekleri](media/debugging-interactive-options.png)

## <a name="use-the-experimental-debugger"></a>Deneysel hata ayıklayıcısını kullan

Visual Studio 2017 Preview 4.0 ile başlayarak, "4.1 + ptvsd sürümü temel Deneysel hata ayıklayıcısını" kullanarak tercih edebilirsiniz. Katılım için seçin **Araçları** > **seçenekleri** menü komutunu ve ardından gitmek **Python** > **Deneysel**Seçenekler iletişim kutusu seçip **Deneysel hata ayıklayıcısını**.

Deneysel hata ayıklayıcı, aşağıdaki tabloda açıklandığı gibi yalnızca sınırlı Python ortamları ile uyumludur:

| Python sürümü | Deneysel hata ayıklayıcısı ile uyumlu |
| --- | --- |
| 2.6 | Hayır |
| 2.7 | Evet |
| 3.1 için 3.4 | Hayır |
| 3.5 ve sonraki sürümler | Evet |
| IronPython | Hayır |

Deneysel hata ayıklayıcısı ile uyumlu bir ortam kullanmayı denerseniz, Visual Studio hatayı gösterir **hata ayıklayıcı bu ortamı ile uyumsuz**:

![Deneysel hata ayıklayıcısını kullanarak hata ayıklayıcı bu ortam hatası ile uyumlu değil](media/debugging-experimental-incompatible-error.png)

Seçin **Deneysel hata ayıklayıcısını devre dışı** komutu, hangi temizler **Deneysel hata ayıklayıcısını** seçeneği.

> [!Note]
> Uyarı şu anda Python 3.3 ve 3.4 gösterilmez.

Geçerli ortama (örneğin, bir önceki 4.0.x sürümü sürümü uzaktan hata ayıklama için gereken bir 3.x) ptvsd daha eski bir sürümünü yüklediyseniz Visual Studio ya da bir hatayı gösterir. **hata ayıklayıcısı paket yüklenemedi**, veya Uyarı **hata ayıklayıcı paketi güncel değil**:

![Hata ayıklayıcısı paket Deneysel hata ayıklayıcısını kullanarak yüklenen hata bulunamadı](media/debugging-experimental-version-error.png)

![Hata ayıklayıcısı paket Deneysel hata ayıklayıcısını kullanarak uyarı güncel değil](media/debugging-experimental-version-warning.png)

Ptvsd yüklemenizi yönetmek için kullandığınız **paketleri** sekmesinde **Python ortamları** penceresi ya da komut satırından aşağıdaki komutları kullanın:

```powershell
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
