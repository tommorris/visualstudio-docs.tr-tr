---
title: Visual Studio grafik tanılama genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 02/09/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 08a942830893bc7a195c64765f5915df32b5ecfb
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31478271"
---
# <a name="overview-of-visual-studio-graphics-diagnostics"></a>Visual Studio Grafik Tanılama’ya Genel Bakış
Visual Studio *grafik tanılama* kaydı ve Direct3D uygulamalar oluşturma ve performans sorunları çözümlemek için araç kümesidir. Grafik tanılama Windows bilgisayarınızda veya bir uzak bilgisayar veya cihaz üzerinde yerel olarak çalışan uygulamalar üzerinde kullanılabilir.  
  
## <a name="using-graphics-diagnostics-to-debug-rendering-problems"></a>İşleme sorunlarında hata ayıklamak için Grafik Tanılama'yı kullanma  
 Grafik açısından zengin bir uygulamada işleme sorunları hatalarının ayıklanması, hata ayıklayıcıyı başlatıp herhangi bir kodda adım adım ilerlemek kadar basit işlem değildir. Her kare içinde, her biri karmaşık bir durum, veri, parametre ve kod kümesine göre olmak üzere yüz binlerce benzersiz piksel üretilirken, tanılamaya çalıştığınız sorunu bunlar arasında belki de yalnızca birkaç piksel sergileyecektir. He bir pikseli üreten kodun, yüzlerce pikseli paralel olarak işlemden geçiren özel amaçlı donanımlarda yürütülmesi meseleyi daha da karmaşık bir hale getirir. Çok fazla veriyle karşı karşıya kalındığında, iş parçacıklarının yoğun olmadığı kodlarda bile yarar sağlanması zor olan geleneksel hata ayıklama araçları ve teknikleri etkisiz kalmaktadır.  
  
 Grafik tanılama araçları [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sorun ve sonra yeniden sorun kaynağına yalnızca ilgili gölgelendirici kod odaklanan izleme potansiyel satış gösteren visual yapıtlarıyla başlatarak işleme sorunlarını bulmanıza yardımcı olmak üzere tasarlanmıştır aşamaları çizin çağrıları, kaynakları ve cihaz durumu — uygulamanın kaynak kodunda.  
  
## <a name="directx-version-compatibility"></a>DirectX sürümü uyumluluğu  
 Grafik tanılama Direct3D 10 veya daha fazla kullanan uygulamaları destekler ve Direct2D kullanan uygulamalar için sınırlı destek sağlar. Direct3D, DirectDraw veya diğer grafik API'lerinin önceki sürümlerini kullanan uygulamaları desteklemez.  
  
### <a name="windows-10-and-direct3d-12"></a>Windows 10 ve Direct3D 12  
 Windows 10 sunulan *Direct3D 12*, Direct3D 10 ve Direct3D 11 önemli ölçüde farklı. Bu farklılıklar DirectX modern grafik donanım ve tüm olası unleashing hizalama sağlamak, ancak ayrıca büyük API değişiklikleri yapın ve kaynak yaşam süresi ve çakışma yönetmek için programcı büyük sorumluluk yerleştirin. Farkları rağmen grafik tanılama Direct3D 12 Direct3D 11.2 ile grafik Tanılama ile özelliği eşlik tutar.
  
 Windows 10 Direct3D oyun ve bunlar üzerinde kullanan uygulamalar önceki sürümleri için destek de korur. Visual Studio grafik tanılama Direct3D 10 ve Direct3D 11 üzerinde Windows 10 desteklemeye devam eder.
  
### <a name="limited-direct2d-support"></a>Sınırlı Direct2D desteği  
 Direct2D üzerinde Direct3D yerleşik bir kullanıcı modu API olduğundan, işleme sorunları Direct2D kullanan uygulamalarda hata ayıklama yardımcı olması için grafik tanılamayı kullanabilirsiniz. Bununla birlikte, üst düzey Direct2D olayları yerine yalnızca temeli oluşturan Direct3D olayları kaydedildiğinden, Direct2D olayları Grafik Olay Listesi'nde görünmez. Ayrıca, Direct2D olayları ve sonuç Direct3D olayları arasındaki ilişki her zaman net olmadığından, Direct2D kullanan uygulamalarda işleme sorunları hatalarını ayıklamak için Grafik Tanılama kullanılması her zaman basit değildir. Yine de, Direct2D kullanan uygulamalarda düşük düzeyli işleme sorunları hakkında bilgi almak için Grafik Tanılama'yı kullanabilirsiniz.  
  
## <a name="graphics-diagnostics-features-in-visual-studio"></a>Visual Studio grafik tanılama özellikleri  
 Grafik tanılama ayrılmış arabirimi - grafik çözümleyicisi penceresini - işleme sorunları tanılamak için olsa da, aynı zamanda Visual Studio arabirimine bazı araçları ekler.  
  
### <a name="the-graphics-toolbar-visual-studio"></a>Grafik araç çubuğu (Visual Studio)  
 Grafik araç çubuğu grafik tanılama komutlara hızlı erişim sağlar.  
  
 **Başlat tanılama** düğmesi grafik tanılama altında uygulamayı çalıştırır. Bir uygulama grafik tanılama altında çalışırken, **sonraki işlenmiş çerçeve yakalama** düğmesi etkindir.  
  
### <a name="diagnostics-capture-interface"></a>Tanılama yakalama arabirimi  
 Grafik tanılama altında uygulamanızı çalıştırdığınızda, Visual Studio çerçeveleri yakalamak için kullanabilir ve ayrıca geçerli CPU ve GPU'ya yük görüntüleyen bir tanılama oturumu arabirimini görüntüler. CPU ve GPU'ya yük, kendi performans özellikleri yerine nedeniyle işleme hataları yakalamak isteyebileceğiniz çerçeveler tanımlamanıza yardımcı olması için görüntülenir.  
  
 Bu çerçeveleri ancak yakalamak için tek yolu değildir. Çerçeve programlı yakalama arabirimini kullanarak veya komut satırı yakalama programını kullanarak yakalayabilirsiniz dxcap.exe.  
  
 Bkz: [grafik bilgilerini yakalama](capturing-graphics-information.md) daha fazla bilgi için.  
  
### <a name="gpu-usage"></a>GPU Kullanımı  
 Grafik tanılama Direct3D uygulamanızın performansını da profil. Profil oluşturma verilerini göre kaydı ayrıntıları grafik olayların eğri çünkü bu kullanılacak çerçeveleri yakalama ayrı grafik Çözümleyicisi ile inceledi.  
  
 Bkz: [GPU kullanım](gpu-usage.md) daha fazla bilgi için.  
  
### <a name="directx-control-panel"></a>DirectX denetim masası  
 DirectX denetim masası, DirectX'in davranış şeklini değiştirmek için kullanabileceğiniz bir DirectX bileşenidir; örneğin, DirectX çalışma zamanı bileşenlerinin hata ayıklama sürümünü etkinleştirebilir, raporlanan hata ayıklama iletilerinin türünü seçebilir ve daha düşük kapasiteli donanımlara öykünmek için belirli grafik donanımı yeteneklerinin kullanılmasına izin vermeyebilirsiniz. DirectX üzerinde bu düzeyde bir denetim DirectX uygulamanızda hata ayıklamanıza ve uygulamayı test etmenize yardımcı olabilir. DirectX denetim masasına Visual Studio'dan erişebilirsiniz.  
  
#### <a name="to-open-the-directx-control-panel"></a>DirectX denetim masasını açmak için  
  
-   Menü çubuğunda seçin **hata ayıklama**, **grafik**, **DirectX Denetim Masası**.  
  
## <a name="graphics-analyzer"></a>Grafik Çözümleyicisi  
 Visual Studio grafik Çözümleyicisi zaten yakalanan çerçeve işleme ve performans sorunları incelemek için adanmış bir arabirimdir. Grafik Çözümleyicisi içinde keşfedin ve uygulamanızı işleme davranışını anlamanıza yardımcı olacak birkaç araç bulabilirsiniz. Her aracı farklı türde bir Denetlenmekte olan çerçeve hakkında bilgi gösterir ve araçları sezgisel dar başlayarak bir işleme sorunun kaynağı için birlikte kullanılmak üzere tasarlanmış görünümünü framebuffer içinde.  
  
 Bu Çizim Araçları'nın tipik bir düzen grafik Çözümleyicisi'nde gösterir.  
  
 ![Tüm grafik windows hata ayıklayıcı](media/graphicsdebuggerwindows.png "GraphicsDebuggerWindows")  
  
### <a name="the-graphics-toolbar-graphics-analyzer"></a>Grafik araç çubuğu (grafik Çözümleyicisi)  
 Grafik araç çubuğu grafik Çözümleyicisi aracını windows hızlı erişim sağlar.  
  
 ![Grafik araç çubuğu grafik tanılama modunda](media/vsg_toolbar.png "vsg_toolbar")  
  
### <a name="graphics-log-document"></a>Grafik günlük belgesi  
 Grafik Çözümleyicisi içinde grafik günlük belgesi en belirgin aracı penceredir. Bu pencere tüm uygulamanızı grafik tanılama altında çalıştırarak yakalanan çerçeve temsil eder. Buradan inceleyin veya piksel geçmişi aracıyla incelemek istediğiniz belirli bir piksel seçmek için başka bir çerçeve seçebilirsiniz. Bu belge değişiklikleri framebuffer zaman içinde nasıl etkilendiğini görebilmeniz için şu anda seçili olay yansıtacak şekilde görüntülenen framebuffer resim.  
  
 [Grafik günlük belgesi](graphics-log-document.md) da yardımcı olur çerçeve analizi aracını giriş noktasını anlamak bir çerçeve performansını işleme belirli yönlerini yapılandırılır şekilde değiştirip Kıyaslama sonuçlar için sağlama özgün ile karşılaştırın.  
  
### <a name="event-list"></a>Olay listesi  
 Grafik olayları her Direct3D API çağrısı ve kullanıcı tanımlı olay işaretleyin.  
  
 [Olay listesi](graphics-event-list.md) tüm inceleniyor çerçevesinde kaydedilmiş bir grafik olayları gösterir. Önemli olan bulmanıza yardımcı olmak için olay listesi hiyerarşik olarak görüntülenebilir — son değişikliklerle durumu-sonraki altında çağrısı çizin — veya bir zaman çizelgesi olarak. Ayrıca, ait oldukları sıraya göre olaylar kodludur ve yalnızca ilgilendiğiniz olayları içermek üzere listesini filtreleyebilirsiniz.  
  
 Listede bir olay seçtiğinizde, grafik çözümleme araçları kalan olay aynı anda çerçeve durumunu yansıtır. Bu şekilde, GPU üzerinde herhangi bir olay etkisini görebilirsiniz. Örneğin, sonraki çizim çağrıları tarafından getirilmemeli hale olsa bile, tüm çizim hemen etkisini framebuffer üzerinde çağırmak görebilirsiniz. Bazı olaylar Ayrıca kendi parametreleri veya ilgili kaynak nesneleri hakkında daha fazla ayrıntı için izleyebileceğiniz köprüler sahiptir.  
  
### <a name="pipeline-stages"></a>Ardışık Düzen aşamaları  
 Uygulamanızı her çizim çağrısında Direct3D tarafından sağlanan grafik ardışık düzen geçer. Ardışık düzende her aşamada önceki aşamaya çıktısını küçük bir program tarafından dönüştürülen, gölgelendirici adlı ve ekrana son işlenen kadar sonraki aşamaya geçirildi. Çıktı biçimi sonraki aşamaya beklediğinden daha ya da herhangi bir aşamada yalnızca hatalı sonuçlar üretir farklı olduğunda ardışık düzen aşamaları arasında sınır en çok sayıda işleme hataları oluşur. Normalde, yalnızca son sonuçları ekranda görür ve ardışık düzeninde hatanın oluştuğu kolayca bildiremez alırsınız.  
  
 [Ardışık düzen aşamaları](graphics-pipeline-stages.md) penceresi visualizes her aşamanın sonucunu bağımsız olarak, hangi aşamada daha kolay belirleyebilmesi işleme sorun ilk olarak görünür. Diğer bir deyişle, aşama saptadıktan sonra ardışık düzen aşamaları penceresinden sağ kendi gölgelendirici hata ayıklama başlatabilirsiniz.  
  
### <a name="graphics-state"></a>Grafik Durumu  
 Oluşturma işlemleri genellikle birden çok nesneye yayılır durumu çok bağlıdır. Çok çeşitli işleme sorunları yanlış yapılandırılmış durumuna göre neden olur.  
  
 [Durumu](graphics-state.md) penceresi; böylece daha kolay bulmak için ve ayrıca vurgular önceki bu yana gerçekleşen durum değişiklikleri çizin çağrısı çağrısına her çizim birlikte tek bir yerde ilgili durum bilgilerini toplar.  
  
### <a name="pixel-history"></a>Piksel geçmişi  
 Karmaşık görünümlerde birden çok kez tek bir çerçevede gölgeli bir piksel için seyrek değil. Bazen önceki renk renkleri birleştirilir yalnızca üzerine, ancak diğer katıdır birlikte saydamlık gibi efektler elde etmek için. Bunları birlikte birleştirme sonucunu doğru görünüm sahip olmadığında renkleri biri hatalı olduğu veya yolu ile ilgili bir sorun varsa bunlar birleştirilen olup olmadığını kolayca bildiremez. Diğer durumlarda, bir nesne piksel kendi katkısı herhangi bir nedenden dolayı reddedildiği için eksik gibi görünebilir.  
  
 [Piksel geçmişi](graphics-pixel-history.md) penceresi visualizes çerçevesinde, reddedilen Katkıları dahil olmak üzere her piksel tam gölgelendirici geçmişini. Reddedilen doğru Katkıları ham gölgelendirici sonuçları ve her yeni bir renk öncekiyle nasıl birleştirilmiş görüntüler. Bu bilgiyle gölgelendirici sonuçları blend ya da kendi piksel katkısı yanlış reddedildiği için oluşturulan bir nesne eksik olduğunda piksel cinsinden hatalarının kaynağını bulmak daha kolay olur.  
  
### <a name="event-call-stack"></a>Olay Çağırma yığını  
 Yalnızca kaynak Direct3D uygulama işleme sorunları gölgelendirici kod değilse, bazen, uygulamanızın kaynak kodu yanlış parametre geçirmeden veya Direct3D oldukça sağ yapılandırmaz. Tüm pikselleri reddettiği için oluşturulan bir nesne eksik olduğunda daha önce ele alındığı özelliğini piksel geçmişi bulmanıza yardımcı olabilecek hata için bir türüdür. Bir ayarı yanlış bu tür bir hatayı genellikle olur, gibi bir derinliği test nasıl gerçekleştirildiğini denetleyen ve herhangi bir yerde, hata eksik nesnenin çağrı yığınında genellikle bulabilirsiniz çağrısı çizin.  
  
 [Olay çağrı yığını](graphics-event-call-stack.md) penceresi olay listesinde her grafik olay tam çağrı yığınını görüntüler ve hata ayıklama bilgileri kullanılabilir olsa bile sağlar, uygulamanızın atlama kaynak kodu. Bu, ilk olarak, uygulamanızın kaynak kodunda başlatıldığı için geri GPU üzerinde göründüğü gelen bir hatadan sonra için güçlü bir araçtır.  
  
### <a name="object-table"></a>Nesne tablosu  
 Uygulama işler yüzlerce veya binlerce kaynak nesnelerin bile tarafından büyük olasılıkla yedeklenen her çerçevesi. Bu geri arabellekleri içerir ve işleme hedefleri, doku, köşe arabellekleri, dizin arabellekleri, genel arabellekleri — hemen Direct3D hatırlıyor her şeyi bir nesnedir.  
  
 [Nesnesi tablosu](graphics-object-table.md) tüm seçili grafik olay sırada mevcut nesneleri olay listesi görüntüler. Tipik bir uygulamada çoğu nesneyi dokuları olduğundan, olay listesine bir bakışta görüntülerine ilgili ayrıntıları göstermek için optimize edilmiştir. Tür sütunu, her satırda ne tür bir nesneyi olduğunu bildirir ve biçimi sütunu daha fazla alt türü ya da nesne sürümünü gösterir. Diğer ayrıntıları da gösterilir. Bazı nesneler de köprüleri dokuları (bir görüntü olarak doku görüntüleyebilirsiniz) veya (nasıl arabellek Görüntüleyicisi'ni ayrıştırır ve arabellek tanımlayarak ham arabellek bayt görüntüler seçebileceğiniz arabellekleri gibi daha özelleştirilmiş bir Görüntüleyici nesnesiyle görüntülemeyi izleyin biçimi).  
  
### <a name="frame-analysis"></a>Çerçeve analizi  
 Uygulamanızın grafik yalnızca doğru olması gerekmez - çok hızlı, olması gerekir. Daha az güçlü cihazlarda tümleşik grafik veya cep telefonları dizüstü bilgisayarlar gibi. Ve çok büyük aramak hala gerekir.  
  
 [Çerçeve analizi](graphics-frame-analysis.md) aracı otomatik olarak uygulamanın kullandığı Direct3D biçimini değiştirme ve karşılaştırma için kıyaslama sonuçları sağlayarak olası performans iyileştirmelerini araştırır. Örneğin, çerçeve analizi MIP eşlemesinden yararlanabilirsiniz, ancak şu anda etkin sahip dokuları ortaya çıkarabilir her doku üzerinde MIP eşlemesi etkinleştirebilirsiniz. Onu destekleyen donanım üzerinde çerçeve analizi GPU'ın performans sayaçlarından toplanan bilgiler de sunar — bu düzeyde bilgi doku fetch takılması yüksek sayıda gibi donanım düzeyinde performans sorunlarını tanımlamak veya önbellek isabetsizliği.  
  
 Ancak çerçeve analizi neredeyse hızlı giderek değil - en az miktarda görsel kalite vermiş while çoğu performans sağlamasını ilgili değildir. Bazen büyük ekranda harika görünen pahalı efekt burada daha basit bir etkisi pil boşaltma olmadan yalnızca kadar iyi görünebilir bir telefon küçük ekranında görüntülendiğinde aynı etki yapmaz. Otomatik değişiklikleri ve grafik analizini sağlar kriterlere bir dizi cihazı uygulamanız için uygun olan Bakiye bulmanıza yardımcı olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komut satırı Yakalama aracı](command-line-capture-tool.md)   
 [HLSL hata ayıklayıcısı](hlsl-shader-debugger.md)