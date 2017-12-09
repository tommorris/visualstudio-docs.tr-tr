---
title: "Özellik turu profil oluşturma | Microsoft Docs"
ms.custom: H1HackMay2017
ms.date: 05/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugger
ms.assetid: d2ee0301-ea78-43d8-851a-71b7b2043d73
caps.latest.revision: "1"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4899f59362f623f6ecf92927e8a15ed4762fa367
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2017
---
# <a name="profiling-feature-tour"></a>Özellik turu profil oluşturma

Visual Studio Profil Araçları performans sorunları, uygulama türüne bağlı olarak farklı türde tanılamanıza yardımcı olan çeşitli sağlar.

Hata ayıklama oturumu sırasında erişebilmeniz için profil oluşturma araçları tanılama araçları penceresindeki kullanılabilir. Tanılama araçları penceresini, onu devre dışı bırakmış sürece otomatik olarak görünür. Penceresini getirmek için tıklatın **hata ayıklama / Windows / Tanılama Araçları Göster**. Penceresi açıkken veri toplamak istediğiniz araçları seçebilirsiniz.

![Tanılama araçları penceresindeki](../profiling/media/prof-tour-diagnostic-tools.png "tanılama araçları")

Hata ayıklarken, kullanabileceğiniz **tanılama araçları** penceresi CPU ve bellek kullanımı ve analiz etmek için performans ile ilgili bilgiler göster olayları görüntüleyebilir.

![Tanılama araçları özeti görünümü](../profiling/media/prof-tour-cpu-and-memory-graph.gif "tanılama araçları özeti")

**Tanılama araçları** penceredir genellikle tercih edilen yol profili uygulamalara, ancak bunun yerine, uygulamanızın bir Proje Sonrası Değerlendirme analizi yapabilirsiniz. Farklı yaklaşımlar hakkında daha fazla bilgi istiyorsanız, bkz: [çalıştıran profil oluşturma araçları ile veya olmadan Debugger](../profiling/running-profiling-tools-with-or-without-the-debugger.md).

## <a name="analyze-cpu-usage"></a>CPU kullanımı analiz

CPU kullanımı aracı, uygulamanızın performansını analiz etme başlatmak için uygun bir yerdir. Bu, uygulamanızın tüketen CPU kaynakları hakkında daha fazla size bildirir. CPU kullanımı aracı hakkında daha ayrıntılı bilgi için bkz: [performans profili oluşturma Başlangıç Kılavuzu](../profiling/beginners-guide-to-performance-profiling.md).

Gelen **Özet** tanılama araçlarını görüntülemek için seçin **etkinleştirmek CPU profil** (hata ayıklama oturumunda olması gerekir).

![CPU kullanımı Tanılama Araçları'nda Etkinleştir](../profiling/media/prof-tour-enable-cpu-profiling.png "tanılama araçları etkinleştirmek CPU kullanımı")

Aracı en verimli şekilde kullanmak için tek başına diğeri işlevi sonuna veya bölge kodu analiz etmek istiyorsanız, kodunuzu iki kesme noktalarını ayarlayın. İkinci kesme noktasında duraklama profil oluşturma verileri inceleyin.

**CPU kullanımı** görünüm üst uzun süre çalışan işlevi ile uzun çalışan göre sıralanmış işlevlerin bir listesini gösterir. Bu, performans sorunlarını nerede gerçekleştiği işlevler Kılavuzu yardımcı olabilir.

![Tanılama araçları CPU Kullanımı görünümü](../profiling/media/prof-tour-cpu-usage.png "tanılama araçları CPU kullanımı")

İlgilendiğiniz, ve bir ayrıntılı seçili üç bölmesi "bölümü" Görünümü penceresinde, soldaki çağıran işlevi ortasında seçili işlevi ile görürsünüz ve işlevleri sağ tarafta adlı bir işlev çift tıklayın. **İşlev gövdesi** süresi (ve zamanı yüzdesi) işlev gövdesine harcanan zaman hariç toplam miktarı içinde arama harcanan ve işlevleri adlı bölümü gösterir. Bu veri işlevi performans sorunu olup olmadığını değerlendirmeye yardımcı olabilir.

![Tanılama araçları çağıran seçili Aranan "bölümü" view](../profiling/media/prof-tour-cpu-usage-caller-callee.png "tanılama araçları çağıran Aranan görünümü")

## <a name="analyze-memory-usage"></a>Bellek kullanımını çözümleme

Tanılama araçları penceresini bellek kullanımı, uygulamanızda değerlendirmek sağlar. Örneğin, öbek üzerinde sayısını ve boyutunu nesnelerin bakabilirsiniz. Daha ayrıntılı bellek çözümlemek için yönergeler için bkz: [bellek kullanımını çözümleme](../profiling/memory-usage.md).

Bellek kullanımını analiz etmek için hata ayıklarken en az bir bellek anlık görüntüsünü gerekir. Genellikle, bellek analiz etmek için en iyi iki anlık görüntülerini almak için yoludur; ilk hemen şüpheli bellek sorununu önce ve şüpheli bellek sorununu gerçekleştikten sonra ikinci bir anlık görüntü sağ. Ardından iki anlık görüntüyü bir fark görüntüleyin ve tam olarak nelerin değiştiğini bakın.

![Tanılama araçları bir anlık görüntüsünü](../profiling/media/prof-tour-take-snapshots.gif "tanılama araçları ele anlık görüntüler")

Ok bağlantılardan birini seçtiğinizde, öbek fark görünümü verilir (kırmızı yukarı ok ![bellek kullanımını artırır](../profiling/media/prof-tour-mem-usage-up-arrow.png "bellek kullanımını artırır") artan nesne sayısı (soldaki) veya bir artırmayı gösterir yığın boyutu (sağdaki)). Sağ bağlantısına tıklarsanız, yığın boyutu en artan nesneleri göre sıralanmış bir fark yığın görünümü alın. Bu bellek sorunları belirlemenize yardımcı olabilir. Örneğin, aşağıdaki çizimde, bayt tarafından kullanılan `ClassHandlersStore` nesneleri ikinci anlık görüntüdeki 3,492 bayt olarak artar.

![Tanılama araçları yığın fark görünümü](../profiling/media/prof-tour-mem-usage-diff-heap.png "tanılama araçları yığın fark görünümü")

Sol taraftaki bağlantı bunun yerine, tıklatırsanız **bellek kullanımı** görünümü, yığın görünümü nesne sayısına göre düzenlenmiştir; en fazla artan belirli bir türdeki nesneler en üstünde gösterilir (göre sıralanmış **sayısı fark** sütun).

## <a name="examine-performance-events"></a>Performans olayları inceleyin

**Olayları** tanılama araçları görünümünde, bir kesme noktası veya bir kod sürüm işlemi ayarı gibi hata ayıklarken oluşan farklı olayları gösterir. (Hata ayıklayıcı en son ne zaman duraklatıldı veya uygulama başladığında ölçülür) olay süresi gibi bilgileri kontrol edebilirsiniz. Örneğin, kodda (F10, F11), adım **olayları** görünüm geçerli adım için önceki adımı işlemi uygulama çalışma zamanı süresini gösterir.

![Tanılama araçları olayları görüntülemek](../profiling/media/prof-tour-events.png "tanılama araçları olayları görüntüle")

 > [!NOTE]
 > Visual Studio Enterprise varsa da görebilirsiniz [IntelliTrace olayları](../debugger/intellitrace.md) bu sekmede.

Aynı olayları da PerfTips görüntüleyebilirsiniz Kod düzenleyicisinde gösterilir.

![Turu PerfTips profil](../profiling/media/prof-tour-perf-tips.png "turu PerfTips profil oluşturma")

## <a name="examine-ui-performance-and-accessibility-events-uwp"></a>UI performans ve erişilebilirlik olayları (UWP) inceleyin

UWP uygulamalarınızda etkinleştirmeniz **UI analiz** tanılama araçları penceresindeki. Aracı için genel performans veya erişilebilirlik sorunları arar ve bunları görüntüler **olayları** hata ayıklarken görüntüleyin. Olay açıklamaları sorunları gidermek yardımcı olabilecek bilgiler sağlar.

![Tanılama araçları UI çözümleme olayları görüntülemek](../profiling/media/prof-tour-ui-analysis.png "tanılama araçları UI analiz olaylarını görüntüle")

## <a name="profile-release-builds-without-the-debugger"></a>Hata Ayıklayıcı olmadan profili yayın derlemeleri

Profil CPU kullanımı ve bellek kullanımını hata ayıklayıcısını kullanmaya kullanılabilir gibi araçları (önceki bölümlerde bakın) veya profil oluşturma araçları için analiz sağlamaya yönelik performans Profiler kullanarak çalıştırabilirsiniz **sürüm** oluşturur. Performans Profil Oluşturucusu'nda Uygulama çalışırken tanılama bilgisi toplamak ve uygulama durdurulduktan sonra toplanan bilgileri inceleyin. Bu farklı yaklaşımlar hakkında daha fazla bilgi için bkz: [çalıştıran profil oluşturma araçları ile veya olmadan Debugger](../profiling/running-profiling-tools-with-or-without-the-debugger.md).

![Performans Profil Oluşturucu](../profiling/media/prof-tour-performance-profiler.png "Performans Profil Oluşturucu")

Performans Profil Oluşturucu seçerek açın **hata ayıklama / Performans Profil Oluşturucu**.

Pencerenin bazı senaryolarda birden çok profil oluşturma araçları seçmenize olanak sağlayacaktır. CPU kullanımı gibi araçlar, çözümlemede yardımcı olmak için kullanabileceğiniz tamamlayıcı veri sağlayabilir.

## <a name="analyze-resource-consumption-xaml"></a>Kaynak tüketimi (XAML) Çözümle

Windows Masaüstü WPF uygulamalar ve UWP uygulamalar gibi XAML uygulamalarda uygulama zaman çizelgesi aracıyla kaynak tüketimini analiz edebilirsiniz. Örneğin, UI çerçeveler (düzeni ve işleme) hazırlama, ağ ve disk isteklere hizmet, uygulamanız tarafından harcanan süre çözümlemek ve uygulama başlatma gibi senaryolarda sayfa yükü ve pencere boyutlandırma. Aracı'nı kullanmayı tercih **uygulama zaman çizelgesi** performans profil oluşturucu ve ardından **Başlat**. Uygulamanızda şüpheli kaynak tüketimi sorunu senaryoyla geçer ve ardından **durdurmak koleksiyonu** raporu oluşturmak için.

Düşük içinde framerates **Visual verimlilik** grafik uygulamanızı çalışırken görmek visual sorunları için karşılık gelen. Benzer şekilde, içinde yüksek sayılar **kullanıcı Arabirimi iş parçacığı kullanımı** grafik UI yanıtlama hızı sorunları da karşılık. Raporda, şüpheli performans sorunu zaman aralığını seçin ve zaman çizelgesi Ayrıntıları görünümünde (alt bölme) ayrıntılı kullanıcı Arabirimi iş parçacığı etkinliklerini inceleyin.

![Aracı profili oluşturma uygulama zaman çizelgesi](../profiling/media/prof-tour-application-timeline.gif "turu uygulama zaman çizelgesi profili oluşturma")

Zaman Çizelgesi Ayrıntıları görünümünde etkinlik süresi birlikte activitiy türünü (veya söz konusu kullanıcı Arabirimi öğesi) gibi bilgileri bulabilirsiniz. Örneğin, çizimdeki bir **düzeni** kılavuz denetimi için olay 57.53 ms alır.

Daha fazla bilgi için bkz: [uygulama zaman çizelgesi](../profiling/application-timeline.md).

## <a name="analyze-gpu-usage-direct3d"></a>GPU kullanımı (Direct3D) Çözümle

Direct3D uygulamaları (Direct3D bileşenleri c++'ta olmalıdır), GPU etkinliği inceleyin ve performans sorunlarını analiz edin. Daha fazla bilgi için bkz: [GPU kullanım](../debugger/gpu-usage.md). Aracı'nı kullanmayı tercih **GPU kullanım** performans profil oluşturucu ve ardından **Başlat**. Uygulamanızda profil ilgilendiğiniz senaryosu aracılığıyla gidin ve ardından **durdurmak koleksiyonu** rapor oluşturmak için.

Ne zaman, bir süre grafiklerde seçip **ayrıntıları görüntüleyin**, ayrıntılı bir görünüm alt bölmesinde görüntülenir. Ayrıntılı görünümde ne kadar etkinlik her CPU ve GPU'ya gerçekleştiği inceleyebilirsiniz. Açılan pencereler zaman çizelgesinde almak için en düşük bölmesinde olayları seçin. Örneğin, seçin **mevcut** görüntülemek için olay **mevcut** çağrısı açılır. (Belirli olup olmadığını anlamak için bir başvuru olarak açık gri dikey Vsync çizgiler kullanılabilir **mevcut** çağrıları Vsync eksik. Mutlaka bir tane **mevcut** çağrı süreleri 60 FPS isabet için her iki Vsyncs arasında sırada uygulama için.)

![GPU kullanımı aracı profili oluşturma](../profiling/media/prof-tour-gpu-usage.png "tanı GPU kullanımı")

Grafikler, CPU'ya vardır veya performans sorunları GPU bağlı olup olmadığını belirlemek için de kullanabilirsiniz.

## <a name="analyze-performance-javascript"></a>Analiz performans (JavaScript)

Windows Evrensel HTML uygulamaları için JavaScript belleği aracı ve HTML UI yanıtlama hızı aracı kullanabilirsiniz.

JavaScript bellek aracı diğer uygulama türleri için kullanılabilir bellek kullanımı aracı benzer. Bellek kullanımını anlamanıza ve uygulamanıza bellek sızıntıları bulmak için bu aracı kullanabilirsiniz. Aracı hakkında daha fazla ayrıntı için bkz: [JavaScript belleği](../profiling/javascript-memory.md).

![JavaScript bellek aracı profili oluşturma](../profiling/media/diagjsmemory.png "DiagJSMemory")

UI yanıtlama hızı, saat ve Windows Evrensel HTML uygulamalarında yavaş visual güncelleştirmeleri yükleme yavaş tanılamak için HTML UI yanıtlama hızı aracını kullanın. Kullanım, diğer uygulama türleri için uygulama zaman çizelgesi aracı benzerdir. Daha fazla bilgi için bkz: [HTML UI yanıtlama hızı](../profiling/html-ui-responsiveness.md).

![HTML UI yanıtlama hızı aracı profili oluşturma](../profiling/media/diaghtmlresp.png "DiagHTMLResp")

## <a name="analyze-network-usage-uwp"></a>Ağ kullanımı (UWP) Çözümle

UWP uygulamalarında kullanılarak gerçekleştirilen ağ işlemlerinin çözümleyebilirsiniz `Windows.Web.Http` API. Bu araç, erişim ve kimlik doğrulama sorunları, yanlış önbellek kullanımı ve görüntü gibi sorunları gidermek ve performans indirmek için yardımcı olabilir. Aracı'nı kullanmayı tercih **ağ** performans profil oluşturucu ve ardından **Başlat**. Uygulamanızda kullanan senaryosuyla Git `Windows.Web.Http`ve ardından **durdurmak koleksiyonu** raporu oluşturmak için.

![Ağ kullanımı aracı profili oluşturma](../profiling/media/prof-tour-network-usage.png "tanı ağ kullanımı")

Bir işlem Özet görünümünü için daha ayrıntılı olarak seçin.

![Ayrıntılı bilgi ağ kullanımını aracında](../profiling/media/prof-tour-network-usage-details.png "tanı ağ kullanım ayrıntıları")

Daha fazla bilgi için bkz: [ağ kullanımını](../profiling/network-usage.md).

## <a name="analyze-performance-legacy-tools"></a>Performans (eski araçları) Çözümle

CPU kullanımı veya bellek kullanımı araçları şu anda mevcut olmayan araçları gibi özellikleri gerekir ve Masaüstü veya ASP.NET uygulamaları çalıştırıyorsanız, profil oluşturma için performans Gezgini kullanabilirsiniz. (UWP uygulamalarında desteklenmez). Daha fazla bilgi için bkz: [performans Gezgini](../profiling/performance-explorer.md).

![Performans Gezgini aracı](../profiling/media/prof-tour-performance-explorer.png "performans Gezgini")

## <a name="which-tool-should-i-use"></a>Hangi aracı kullanmalıyım?  
Visual Studio sunar farklı araçlar listeleyen bir tablo işte ve farklı proje türleri ile kullanabilmek için:
  
|Performans aracı|Windows Masaüstü|Windows Evrensel/deposu|ASP.NET/ASP.NET çekirdek|  
|----------------------|---------------------|------------------------------|-------------|  
|[Bellek kullanımı](../profiling/memory-usage.md)|Evet|Evet|Evet|  
|[CPU kullanımı](../profiling/cpu-usage.md)|Evet|Evet|Evet (Hayır için .NET Core/ASP.NET çekirdek)|  
|[GPU kullanımı](../debugger/gpu-usage.md)|Evet|Evet|Yok|  
|[Uygulama zaman çizelgesi](../profiling/application-timeline.md)|Evet|Evet|Yok|  
|[PerfTips](../profiling/perftips.md)|Evet|HTML için Hayır XAML için Evet|Evet|  
|[Performans Gezgini](../profiling/performance-explorer.md)|Evet|Yok|Evet (Hayır için ASP.NET çekirdek)|  
|[IntelliTrace](../debugger/intellitrace.md)|Yalnızca .NET Enterprise|Yalnızca .NET Enterprise|Yalnızca .NET Enterprise|
|[Ağ kullanımı](../profiling/network-usage.md)|Yok|Evet|Yok| 
|[HTML UI yanıtlama hızı](../profiling/html-ui-responsiveness.md)|Yok|XAML için Hayır HTML için Evet|Yok|  
|[JavaScript belleği](../profiling/javascript-memory.md)|Yok|XAML için Hayır HTML için Evet|Yok|  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da hata ayıklama](../debugger/debugging-in-visual-studio.md)