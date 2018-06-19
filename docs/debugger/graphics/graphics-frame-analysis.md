---
title: Grafik Çerçeve analizi | Microsoft Docs
ms.custom: ''
ms.date: 02/09/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.graphics.frameanalysis
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9fe34c421d06fea1e4eefc064d344727382ca1d8
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31479659"
---
# <a name="graphics-frame-analysis"></a>Grafik Çerçeve Çözümlemesi
Grafik Çerçeve Çözümlemesi Visual Studio grafik Çözümleyicisi çözümlemek ve Direct3D oyun veya uygulama işleme performansını iyileştirmek için kullanın.  

## <a name="frame-analysis"></a>Çerçeve analizi  
 Çerçeve analizi tanılama grafik günlük dosyasında yakalanır, ancak işleme performans yerine özetlemek için kullandığı aynı bilgileri kullanır. Performans bilgileri, yakalama sırasında günlüğe kaydedilmez; Çerçeve çalınma gibi yerine performans bilgilerini daha sonra çerçeve çözümlemesi sırasında zamanlama olayları ve toplama istatistikleri tarafından oluşturulur. Bu yaklaşım, yakalama sırasında performans bilgilerini kaydetme birkaç avantajı vardır:  
  
-   Çerçeve analizi Özet performans istatistiksel olarak ses olduğundan emin olmak için aynı çerçevenin birden çok her oynatma sonuçlarından ortalama.  
  
-   Çerçeve analizi, donanım yapılandırmaları ve bilgilerin olduğu yakalandığında farklı aygıtlar için performans bilgilerini oluşturabilir.  
  
-   Çerçeve analizi, daha önce yakalanan bilgilerinden yeni performans özetleri üretebilir — Örneğin, ne zaman GPU sürücüleri en iyi duruma getirilir veya ek hata ayıklama özellikleri kullanıma sunar.  
  
 Bu avantajlara ek olarak, çerçeve analizi de bu değişiklikleri bir uygulamayı işleme performansını nasıl etkileyebileceği hakkında bilgi sunabilir böylece çerçeve kayıttan yürütme sırasında işlenme için değişiklik yapabilirsiniz. Bunları tüm uygulama ve ardından yakalayın ve tüm sonuçları karşılaştırma yapmak zorunda kalmadan olası en iyi duruma getirme stratejileri arasında karar vermek için bu bilgileri kullanın.  
  
 Çerçeve analizi öncelikle işleme daha hızlı performans elde yardımcı olmak için tasarlanmıştır ancak bunu eşit olarak belirli performans hedefi için daha iyi görsel kalite elde etmek veya GPU güç tüketimini azaltır yardımcı olabilir.  
  
 Çerçeve analizi uygulamanız için ne yapabileceğinizi bir örnek görmek için izleyebilir [Visual Studio Grafik Çerçeve Çözümlemesi](http://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool) Channel 9 video.  
  
## <a name="using-frame-analysis"></a>Çerçeve analizi kullanma  
 Çerçeve analizi kullanmadan önce çalışırken, bir grafik Çözümleyicisi araçlardan birini kullanırken yaptığınız gibi uygulamanızdan grafik bilgilerini yakalama sahip. Grafik günlük belgesi (.vsglog) penceresinde seçin **çerçeve analizi** sekmesi.  
  
 ![Çerçeve Çözümlemesi sekmesini](media/pix_frame_analysis_select_tab.png "pix_frame_analysis_select_tab")  
  
 Analiz tamamlandığında, sonuçları görüntülenir. Zaman Çizelgesi ve Özet Tablosu üst kısmında, çerçeve çözümlemesi sekmesini görüntüler. Alt bölümünde ayrıntıları tabloları görüntüler. Kayıttan yürütme sırasında oluşturulan hatalar veya uyarılar, bunlar zaman çizelgesi özetlenen; Buradan, hataları ve Uyarıları hakkında daha fazla bilgi için bağlantılar izleyebilirsiniz.  
  
### <a name="interpreting-results"></a>Sonuçları yorumlama  
 Her değişken sonuçlarını yorumlama tarafından uygulamanız hakkında yararlı bilgiler performans ve davranış işleme çıkarımını. İşleme türevleri hakkında daha fazla bilgi için bkz: [çeşitleri](#Variants) bu makalenin ilerisinde yer.  
  
 Bazı sonuçları doğrudan değişken oluşturma performansını nasıl etkilediğini gösterir:  
  
-   Çift doğrusal doku filtreleme değişken performans artışı gösterdi varsa, uygulamanızda filtreleme çift doğrusal doku kullanarak benzer performans artışları gösterir.  
  
-   1 x 1 görünüm penceresinin değişken performans artışı ise, uygulamanızda işleme hedefleri boyutunu azaltma işleme performansını artırır.  
  
-   Performans artışı BC doku sıkıştırma değişken gösterdi varsa, sonra uygulamanızda BC doku sıkıştırma kullanılarak benzer performans artışı gösterir.  
  
-   2xMSAA değişken neredeyse aynı performans 0xMSAA değişken varsa, performans maliyeti olmadan işleme kalitesini artırmak için uygulamanızda 2xMSAA etkinleştirebilirsiniz.  
  
 Diğer sonuçları, uygulamanızın performansını daha derin, daha hafif etkilerini önerebilir:  
  
-   1 x 1 görünüm penceresinin değişken çok yüksek performans artışları gösteriyorsa, uygulamanızı büyük olasılıkla bulunandan daha fazla fillrate tüketilmesine neden olabilir. Bu değişken performans artışı gösteriyorsa, uygulama büyük olasılıkla çok fazla köşeleri işliyor.  
  
-   16bpp işleme hedef biçimi değişken önemli performans artışları gösteriyorsa, uygulamanızı büyük olasılıkla çok fazla bellek bant genişliği tüketilmesine neden olabilir.  
  
-   Half/Quarter doku boyutları değişken önemli performans artışları gösteriyorsa, doku büyük olasılıkla çok fazla bellek kaplar, çok fazla bant genişliği veya doku önbellek kullanamayabilir. Bu değişken performans hiçbir değişiklik gösteriyorsa, büyük olasılıkla bir performans maliyeti ödeme olmadan daha büyük ve daha ayrıntılı dokuları kullanabilirsiniz.  
  
 Donanım sayaçları kullanılabilir olduğunda, uygulamanızın işleme performans neden sorunu hakkında çok ayrıntılı bilgi toplamak için kullanabilirsiniz. Tüm özellik düzeyinde 9.2 ve üzeri cihazlar derinliği kapanması sorgularını destekler (**occluded piksel** sayaç) ve zaman damgası. Diğer donanım sayaçları GPU üreticisine ve donanım sayaçları uygulanan kendi sürücü kullanıma bağlı olarak mevcut olabilir. Özet tabloda gösterilen sonuçları kesin nedenini onaylamak için bu sayaçları kullanabilirsiniz — örneğin, belirleyebilirsiniz olup overdraw derinliği test tarafından occluded piksel yüzdesi inceleyerek bir faktördür.  
  
### <a name="timeline-and-summary-table"></a>Zaman Çizelgesi ve Özet Tablosu  
 Varsayılan olarak, zaman çizelgenizi ve Özet tablosu görüntülenir ve diğer bölümleri daraltılır.  
  
#### <a name="timeline"></a>Zaman Çizelgesi  
 Zaman Çizelgesi çizim çağrısı zamanlamaları birbirine göre özetini gösterir. Daha büyük çubukları uzun çizim kez karşılık geldiğinden en pahalı çizim çağrıları çerçevede hızla bulmak için kullanabilirsiniz. Yakalanan çerçeve çizim çağrıları çok fazla sayıda içeriyorsa, tek uzunluğunu çubuk bu toplamıdır birden çok çizim çağrıları birleştirilir çağrıları çizin.  
  
 ![Zaman Çizelgesi çizim gösterir&#45;maliyetleri çağırın. ] (media/pix_frame_analysis_timeline.png "pix_frame_analysis_timeline")  
  
 Çubuğu karşılık gelen hangi çizim çağırma olayı görmeye çubuğundaki işaretçiyi tutun. Çubuğu belirlenmesi olayı eşitlemek olay listesi neden olur.  
  
#### <a name="table"></a>Tablo  
 Zaman Çizelgesi altındaki sayılar tablosu her işleme değişken her çizim çağrı uygulamanızın varsayılan işleme göre performanslarını gösterir. Her sütunun farklı işleme değişken görüntüler ve her satırın en sol sütunda tanımlanan bir farklı çizim çağrısını temsil eder; Buradan grafik olay Listesi penceresinde olay için bir bağlantı izleyebilirsiniz.  
  
 ![Özet tablosunu farklı varients gösterir. ] (media/pix_frame_analysis_summary.png "pix_frame_analysis_summary")  
  
 Özet Tablosu ikinci en sol sütunda, uygulamanızın temel işleme süresini görüntüler — diğer bir deyişle, bu uygulamanızın varsayılan işleme için çizim aramayı tamamlamak geçen süre. Böylece performansı geliştirildi olup olmadığını görmek daha kolay kalan sütunlar her işleme değişken göreli performans taban çizgisi yüzdesi olarak gösterir. % 100'den büyük yüzdeleri taban uzun sürdü — diğer bir deyişle, performans kapandı — ve daha az sürdü yüzde 100'den küçük yüzdeleri — performans oluştu.  
  
 Birden çok çalıştırılan gerçekte ortalama ortalamalar değerlerdir taban mutlak zamanlamasını ve işleme çeşitleri göreli zamanlamasını — varsayılan olarak 5. Bu ortalama zamanlama verileri güvenilir ve tutarlı olmasını sağlar. En düşük incelemek için tablodaki her hücre işaretçinin tuttuğunuzda, en fazla, ortalama ve sonuçlar için arama ve işleme değişken çizerken gözlenen Medyan zamanlama değerleri oluşturulan. Taban çizgisi zamanlama de görüntülenir.  
  
#### <a name="hot-draw-calls"></a>"Etkin" çağrıları çizme  
 Büyük bir kısmının kullanabilir aramaları çizmek için dikkat getirmek için genel işleme süresini ya da kaçınılması, nedenlerden dolayı bu içeren satırı olağandışı yavaş olabilir "etkin" Çizim çağrıdır gölgeli kırmızı kendi temel zamanlama birden fazla olduğunda Standart sapma çerçevesindeki tüm çizim çağrılarının ortalama temel zamanlama daha uzun.  
  
 ![Bu DrawIndexed çağrı sıcak ve soğuk varients sahiptir. ] (media/pix_frame_analysis_hot_calls.png "pix_frame_analysis_hot_calls")  
  
#### <a name="statistical-significance"></a>İstatistiksel önem  
 En yakın olan Çeşitlemeler işleme için dikkat getirmek için çerçeve analizi her işleme değişken istatistiksel önemini belirler ve önemli olanları kalın olarak görüntüler. Yeşil olarak performansı olanları ve kırmızı olarak performansı düşürebilir iletileri görüntüler. Normal türü olarak istatistiksel olarak önemli olmayan sonuçlar görüntüler.  
  
 ![Draw çağrısı değişkeni istatistiksel relevence](media/pix_frame_analysis_summary_stats.png "pix_frame_analysis_summary_stats")  
  
 Çerçeve analizi istatistiksel uygunluğu belirlemek için kullandığı [öğrencinin t-test](http://www.wikipedia.org/wiki/Student%27s_t-test).  
  
### <a name="details-table"></a>Ayrıntıları tablosu  
 Aşağıdaki tabloda varsayılan olarak daraltılmış Ayrıntıları tablosu özetidir. Ayrıntılar tablo içeriğini kayıttan yürütme makinesini donanım platformuna bağlıdır. Desteklenen donanım platformlar hakkında daha fazla bilgi için bkz: [donanım desteği](#HardwareSupport).  
  
#### <a name="platforms-that-do-not-support-hardware-counters"></a>Donanım sayaçları desteklemeyen platformları  
 Çoğu platformda donanım GPU sayaçları tam olarak desteklemeyen — bunlar şu anda Intel, AMD ve NVIDIA tarafından sunulan tüm GPU içerir. Toplamak için donanım sayaç olduğunda, yalnızca bir Ayrıntıları tablosu görüntülenir ve tüm çeşitleri ortalama mutlak zamanlamasını içerir.  
  
 ![Ayrıntıları tablosu ve bazı kayıttan yürütme varients. ] (media/pix_frame_analysis_details.png "pix_frame_analysis_details")  
  
#### <a name="platforms-that-support-hardware-counters"></a>Donanım sayaçları destekleyen platformlar  
 Donanım GPU sayaçları destekleyen platformlar için — örneğin, NVIDIA T40 SOC ve tüm Qualcomm SOCs — birkaç ayrıntıları tabloları görüntülenir, her değişken için bir tane. Her kullanılabilir donanım sayaç her işleme değişken için toplanır ve kendi ayrıntıları tabloda görüntülenir.  
  
 ![Donanım sayaçları desteklendiği durumlarda görüntülenir. ] (media/pix_frame.png "pix_frame")  
  
 Donanım sayaç bilgileri çok hassas bir şekilde performans sorunları nedenini belirlemenize yardımcı olabilir her çizim çağrısı için belirli donanım platformu davranışı çok ayrıntılı bir görünümünü sağlar.  
  
> [!NOTE]
>  Farklı donanım platformları farklı sayaçları destekler; Standart yoktur. Sayaçları ve neyi temsil ettiği yalnızca her GPU üreticisi tarafından belirlenir.  
  
### <a name="marker-regions-and-events"></a>İşaretçi bölgeler ve olaylar  
 Çerçeve analizi, kullanıcı tanımlı olay işaretçileri ve olay grupları destekler. Bunlar Özet tablosunu ve ayrıntı tabloları görüntülenir.  
  
 İşaretçileri ve grupları oluşturmak için ID3DUserDefinedAnnotation API'ları veya eski API D3DPERF_ ailesinin kullanabilirsiniz. D3DPERF_ API ailesi kullandığınızda, her bir işaret ve Grup çerçeve analizi Renkli Bant Olay işaret veya olay Grup başlamak son işaretçileri ve içeriklerini içeren satırı olarak görüntüler bir renk atayabilirsiniz. Bu özellik, önemli işleme olayları veya grupları olayların hızla tanımlamanıza yardımcı olabilir.  
  
### <a name="warnings-and-errors"></a>Uyarıları ve hataları  
 Çerçeve analizi bazen uyarıları veya zaman çizelgesi özetlenen ve çerçeve çözümlemesi sekmesi altındaki ayrıntılı hataları ile tamamlar.  
  
 Genellikle, uyarıları ve hataları yalnızca bilgilendirme amaçlıdır ve herhangi bir müdahalesi gerektirmez.  
  
 Uyarıları genellikle belirtmek donanım desteği bulunmaması ancak geçici çalışılan, donanım sayaçları olamaz toplanmasını veya belirli performans verileri güvenilir olmayabilir, — örneğin, ne zaman geçici bir çözüm olumsuz etkiler.  
  
 Hatalar genellikle çerçeve analiz uygulama hataları olan, bir sürücü hataları vardır, donanım desteği bulunmaması ve geçici çalışılan olamaz veya uygulama kayıttan yürütme tarafından desteklenmeyen bir şey çalışır olduğunu gösterir.  
  
### <a name="retries"></a>Yeniden deneme sayısı  
 GPU güç durumu geçişi çerçeve çözümlemesi sırasında uğradığında, çünkü GPU clockspeed değişti ve böylece göreli zamanlama sonuçları geçersiz kılınan etkilenen analiz geçişi denenmeli.  
  
 Çerçeve analizi 10 deneme sayısını sınırlar. Platformunuz agresif güç yönetimi veya saat geçişi varsa, başarısız ve yeniden deneme sınırını aştığından bir hata raporu çerçeve analizi neden olabilir. Platformunuza ait güç yönetimi sıfırlayarak bu sorunu azaltmak ve platform etkinleştirirse daha az agresif olmasını hızı azaltma saat mümkün olabilir.  
  
##  <a name="HardwareSupport"></a> Donanım desteği  
  
### <a name="timestamps-and-occlusion-queries"></a>Zaman damgaları ve kapanması sorguları  
 Zaman damgaları çerçeve analizi destekleyen tüm platformlarda desteklenir. Derinlik kapanması sorguları — piksel Occluded sayaç için gerekli — 9.2 veya üzeri özellik düzeyinde destek platformlarında desteklenir.  
  
> [!NOTE]
>  Zaman damgaları çerçeve analizi destekleyen tüm platformlarda desteklenir, ancak zaman damgaları tutarlılık ve doğruluğunu platformdan platforma değişir.  
  
### <a name="gpu-counters"></a>GPU sayaçları  
 GPU donanım sayaçları desteği donanım bağımlıdır.  
  
 Hiçbir bilgisayar şu anda Intel, AMD veya NVIDIA tarafından sunulan GPU GPU donanım sayaçları güvenilir bir şekilde desteklediğinden, çerçeve analizi sayaçları onlardan toplamak değil. Ancak, çerçeve analizi donanım sayaçları güvenilir bir şekilde bunları destekleyen aşağıdaki GPU Topla:  
  
-   NVIDIA T40 (Tegra4)
  
 Çerçeve analizi destekleyen herhangi bir platform GPU donanım sayaçlarını toplar.  
  
> [!NOTE]
>  GPU donanım sayaçları donanım kaynakları olduğundan, her işleme değişken için donanım sayaçları tamamını toplamak için birden çok geçiş alabilir. Sonuç olarak, hangi GPU sayaçları toplanır belirtilmeyen sırasıdır.  
  
## <a name="unsupported-scenarios"></a>Desteklenmeyen senaryolar  
 Çerçeve analizi kullanarak belirli yöntemler desteklenmeyen veya yalnızca kötü bir fikir değil.  
  
### <a name="playback-of-high-feature-level-captures-on-down-level-devices"></a>Alt düzey cihazlarda yüksek düzeyli özellik çalınmasını yakalar  
 Kayıttan yürütme makinesini desteklediğinden daha yüksek bir özellik düzeyini kullanan bir grafik günlük dosyası kayıttan yürütürken grafik Çözümleyicisi'nde, otomatik olarak geri için TÜNELİ döner. Çerçeve analizi, açıkça TÜNELİ için geri dönüş değil ve bir hata oluşturur — TÜNELİ yararlıdır Direct3D uygulamanızı doğruluğunu inceleyerek, ancak kendi performansını inceleme değil.  
  
> [!NOTE]
>  Özellik düzeyinde konuları göz önünde bulundurmanız önemli olsa da, yakalama ve grafik günlük dosyalarını farklı donanım yapılandırmaları ve aygıtları kayıttan. Grafik günlük günlük dosyası değil veya API'leri içeren kayıttan yürütme makinede desteklenmeyen özellik düzeylerini kullanın geri sürece çalınabilir.  
  
### <a name="direct3d-10-and-lower"></a>Direct3D 10 ve daha düşük  
 Uygulamanızı Direct3D 10 API çağrıları, çerçeve analizi tanımak veya tanınan ve diğer grafik Çözümleyicisi araçları tarafından kullanılan olsa bile bunları profil olmaz.
  
> [!NOTE]
>  Bu, kullanmakta olduğunuz yalnızca Direct3D API çağrıları olmayan özellik düzeylerini geçerlidir.

### <a name="warp"></a>TÜNELİ  
 Çerçeve analizi profil ve gerçek donanım üzerinde işleme performansı artırmak için kullanılmak üzere tasarlanmıştır. Çerçeve analizi TÜNELİ cihazlarda çalıştırılan engelledi değil, ancak genellikle faydalı takip TÜNELİ birinci sınıf bir CPU üzerinde çalışan bile en az özellikli modern GPU yavaş olduğundan ve TÜNELİ performans belirli CPU bağlı olarak büyük ölçüde farklılık gösterebileceğinden değil üzerinde çalıştırıldığı.  
  
##  <a name="Variants"></a> Çeşitleri  
 Bir çerçeve kayıttan yürütme sırasında işlenen şekilde çerçeve analizi yaptığı her değişiklik olarak bilinen bir *değişken*. Çerçeve analizi inceler çeşitleri işleme performansı veya uygulamanızı görsel kalitesini artırmak için yapabilir ortak, görece kolay değişiklikleri için karşılık gelen — örneğin, doku boyutunun azaltılması, doku sıkıştırma kullanılarak veya etkinleştirme yumuşatma farklı türde. Çeşitleri normal işleme bağlamını ve uygulamanızın parametreleri geçersiz. Bir özeti aşağıda verilmiştir:  
  
|Değişken|Açıklama|  
|-------------|-----------------|  
|**1 x 1 Görünüm penceresi boyutu**|Tüm işleme hedefleri görünüm penceresinin boyutlarında 1 x 1 piksel azaltır.<br /><br /> Daha fazla bilgi için bkz: [1 x 1 Görünüm penceresi boyutu değişken](1x1-viewport-size-variant.md)|  
|**0x MSAA**|Birden çok örnek yumuşatma (MSAA) tüm işleme hedeflerde devre dışı bırakır.<br /><br /> Daha fazla bilgi için bkz: [0 x / 2 x / 4 x MSAA çeşitleri](0x-2x-4x-msaa-variants.md)|  
|**2 x MSAA**|Birden çok örnek yumuşatma (MSAA) tüm işleme hedeflerde x 2 sağlar.<br /><br /> Daha fazla bilgi için bkz: [0 x / 2 x / 4 x MSAA çeşitleri](0x-2x-4x-msaa-variants.md)|  
|**4 x MSAA**|Birden çok örnek yumuşatma (MSAA) tüm işleme hedeflerde x 4 sağlar.<br /><br /> Daha fazla bilgi için bkz: [0 x / 2 x / 4 x MSAA çeşitleri](0x-2x-4x-msaa-variants.md)|  
|**Noktası doku filtreleme**|Filtreleme modunu ayarlar `DXD11_FILTER_MIN_MAG_MIP_POINT` (doku filtreleme noktası) için tüm uygun doku örnekleri.<br /><br /> Daha fazla bilgi için bkz: [noktası, ikili, Trilinear ve Eşyönsüz doku filtreleme çeşitleri](point-bilinear-trilinear-and-anisotropic-texture-filtering-variants.md).|  
|**Çift doğrusal doku filtreleme**|Filtreleme modunu ayarlar `DXD11_FILTER_MIN_MAG_LINEAR_MIP_POINT` (çift doğrusal doku filtreleme) tüm uygun doku örnekleri için.<br /><br /> Daha fazla bilgi için bkz: [noktası, ikili, Trilinear ve Eşyönsüz doku filtreleme çeşitleri](point-bilinear-trilinear-and-anisotropic-texture-filtering-variants.md).|  
|**Trilinear doku filtreleme**|Filtreleme modunu ayarlar `DXD11_FILTER_MIN_MAG_MIP_LINEAR` (trilinear doku filtreleme) tüm uygun doku örnekleri için.<br /><br /> Daha fazla bilgi için bkz: [noktası, ikili, Trilinear ve Eşyönsüz doku filtreleme çeşitleri](point-bilinear-trilinear-and-anisotropic-texture-filtering-variants.md).|  
|**Eşyönsüz doku filtreleme**|Filtreleme modunu ayarlar `DXD11_FILTER_ANISOTROPIC` ve `MaxAnisotropy` için `16` (Eşyönsüz doku filtreleme x 16) tüm uygun doku örnekleri için.<br /><br /> Daha fazla bilgi için bkz: [noktası, ikili, Trilinear ve Eşyönsüz doku filtreleme çeşitleri](point-bilinear-trilinear-and-anisotropic-texture-filtering-variants.md).|  
|**16bpp işleme hedef biçimi**|Piksel biçimini ayarlar `DXGI_FORMAT_B5G6R5_UNORM` (16bpp, 565 biçimi) tüm hedefleri ve backbuffers işlemek için.<br /><br /> Daha fazla bilgi için bkz: [16bpp işleme hedef biçimi değişken](16bpp-render-target-format-variant.md)|  
|**MIP harita oluşturma**|Hedefleri işlenmeyebilir tüm dokuları MIP-eşlemeleri sağlar.<br /><br /> Daha fazla bilgi için bkz: [MIP eşleme oluşturma değişken](mip-map-generation-variant.md).|  
|**Yarı doku boyutları**|Orijinal her boyut boyutlarında yarısı işleme hedeflerini olmayan tüm dokuları doku boyutlarında azaltır. Örneğin, 256 x 128 doku 128 x 64 texels azalır.<br /><br /> Daha fazla bilgi için bkz: [Half/Quarter doku boyutları değişken](half-quarter-texture-dimensions-variant.md).|  
|**Çeyrek doku boyutları**|Orijinal her boyut boyutlarında çeyreği hedeflerini işlenmeyebilir tüm dokuları doku boyutlarında azaltır. Örneğin, 256 x 128 doku 64 x 32 texels azalır.<br /><br /> Daha fazla bilgi için bkz: [Half/Quarter doku boyutları değişken](half-quarter-texture-dimensions-variant.md).|  
|**BC doku sıkıştırma**|Bir B8G8R8X8, B8G8R8A8 veya R8G8B8A8 piksel biçimi değişken sahip tüm dokuları sıkıştırmayı etkinleştirir engelleyin. B8G8R8X8 biçimi çeşitleri BC1 kullanarak sıkıştırılmış; B8G8R8A8 ve R8G8B8A8 biçimi çeşitleri BC3 kullanarak sıkıştırılır.<br /><br /> Daha fazla bilgi için bkz: [BC doku sıkıştırma değişken](bc-texture-compression-variant.md).|  
  
 Çoğu çeşitler için sonuç Düzenleyici olur: "azalan doku boyutuna yarısı göre daha hızlı yüzde 25" veya "2 x etkinleştirme MSAA yalnızca 2 yüzde daha yavaş olduğu". Daha fazla yorumlama diğer çeşitleri gerektirebilir — görünüm penceresinin boyutları değişiklikleri 1 x 1 için değişken bir büyük performans kazancı gösteriyorsa, örneğin, bu işleme düşük dolgu hızı tarafından; nedeniyle düşük performansa sahiptir olduğunu gösterebilir performansı önemli ölçüde değişiklik yoksa, alternatif olarak, bu işleme köşe işlemesi nedeniyle düşük performansa sahiptir olduğunu gösteriyor olabilir.