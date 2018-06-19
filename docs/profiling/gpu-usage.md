---
title: GPU kullanımı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9926846ceaba3591a3e89f2eba0fa2d3888e9302
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31575565"
---
# <a name="gpu-usage"></a>GPU Kullanımı
Visual Studio performans ve tanılama hub'ı GPU kullanım aracını daha iyi Direct3D uygulamanızı üst düzey donanım kullanımını anlayın. Uygulamanızın performansını CPU bağımlı veya platformun donanım daha etkili bir şekilde nasıl kullanabileceğinizi içine GPU bağlanmış ve kazanç Insight olup olmadığını belirlemek için kullanabilirsiniz. GPU kullanımı Direct3D 12, Direct3D 11 ve Direct3D 10 kullanan uygulamaları destekler; diğer grafik Direct2D veya OpenGL gibi API'leri desteklemez.  
  
 Bu **GPU kullanım raporu** penceresi:  
  
 ![GPU kullanımı raporla CPU ve GPU'ya zaman çizelgelerini](media/gfx_diag_gpu_usage_report.png "gfx_diag_gpu_usage_report")  
  
## <a name="requirements"></a>Gereksinimler  
 Grafik tanılama gereksinimlerine ek olarak olan GPU kullanım Aracı'nı kullanmak için gereksinimler şunlardır:  
  
-   Bir GPU ve sürücü gerekli zamanlama Araçları'nı destekler.  
  
    > [!NOTE]
    >  Desteklenen donanım ve sürücüler hakkında daha fazla bilgi için bkz: [donanım ve sürücü desteği](#hwsupport) bu belgenin sonundaki.  
  
 Grafik tanılama gereksinimleri hakkında daha fazla bilgi için bkz: [Başlarken](../debugger/graphics/getting-started-with-visual-studio-graphics-diagnostics.md).  
  
## <a name="using-the-gpu-usage-tool"></a>GPU kullanımı Aracı'nı kullanma  
 Uygulamanızı altında GPU kullanım Aracı'nı çalıştırdığınızda, Visual Studio, uygulamanızın işleme performansı ve gerçek zamanlı GPU kullanımı hakkında üst düzey bilgileri grafik tanılama bir oturum oluşturur.  
  
#### <a name="to-start-the-gpu-usage-tool"></a>GPU kullanımı Aracı'nı başlatmak için:  
  
1.  Ana menüde seçin **hata ayıklama**, ardından **performans ve tanılama** (klavye: Alt + F2 tuşuna basın).  
  
2.  Performans ve tanılama hub yanındaki kutuyu işaretleyin **GPU kullanım**. İsteğe bağlı olarak, ilgilendiğiniz diğer araçları yanındaki kutuları işaretleyin. Aynı anda daha eksiksiz bir resim, uygulamanızın performansını almak için birkaç performans ve tanılama araçları çalıştırabilirsiniz.  
  
     ![Kullanmak istediğiniz tanılama araçları seçin. ] (media/gfx_diag_diagsession_tools.png "gfx_diag_diagsession_tools")  
  
    > [!NOTE]
    >  Tüm performans ve tanılama araçları aynı anda kullanılabilir.  
  
3.  Mavi seçin **Başlat** uygulamanızı seçtiğiniz Araçları altında çalıştırmak için performans ve tanılama hub'ın altındaki düğmesini.  
  
 Gerçek zamanlı olarak gösterilen üst düzey bilgileri çerçeve zamanlama, kare hızı ve GPU kullanımı içerir. Bu bilgilerin her grafiği çizilecek bağımsız olarak, ancak ortak saat ölçekli kullanabilir, böylece bunlar arasında kolayca ilişkilendirebilirsiniz.  
  
 **Çerçeve süresi (ms)** ve **kare / saniye (FPS)** grafikleri içeren iki kırmızı, yatay satırları temsil performans hedefleyen 60 ve 30 kare / saniye. İçinde **çerçeve zaman** grafik, uygulamanızı grafiğin altına satır olduğunda performans hedef aşan ve grafik üstündeki satırın olduğunda eksik. İkinci grafik başına çerçeveler tersidir - uygulamanızı grafik üstündeki satırın olduğunda performans hedef aşan ve grafiğin altına satır olduğunda eksik. Öncelikle, bu grafikler, uygulamanızın performansı hakkında üst düzey bir fikir edinmek ve--örneğin araştırmak isteyebileceğiniz slow-downs, kare hızı ani bir düşüş ya da bir ani GPU kullanımı belirlemek için kullanılır.  
  
 Uygulamanızı GPU kullanım aracı altında çalışırken, Tanılama oturumu üzerinde GPU yürütüldü grafik olaylarla ilgili ayrıntılı bilgileri de toplar. Bu bilgi, donanım uygulamanızı nasıl kullanacağını daha ayrıntılı bir rapor oluşturmak için kullanılır. Bu rapor toplanan bilgileri oluşturmak için biraz zaman alır çünkü Tanılama oturumu toplama bilgi gerçekleştirdikten sonra yalnızca kullanılabilir.  
  
 Olduğunda, bir performans aramak istediğiniz veya kullanımı daha yakından vermek, böylece raporu oluşturan performans bilgilerini toplama durdurun.  
  
#### <a name="to-generate-and-view-the-gpu-usage-report"></a>Oluştur ve GPU kullanım raporunu görüntülemek için:  
  
1.  Tanılama oturumu pencerenin alt kısmındaki seçin **koleksiyonunu Durdur** tuşuna basın veya bağlantı **durdurmak** sol üst köşedeki.  
  
     ![GPU ve CPU zamanlama bilgi toplayın. ] (media/gfx_diag_gpu_usage_collect.png "gfx_diag_gpu_usage_collect")  
  
2.  Raporun üst kısmında bir bölüm araştırmak istediğiniz sorunu gösteren grafikleri birini seçin. Seçiminiz en fazla 3 saniye uzunluğunda olabilir; uzun bölümler doğrultusunda başına kesilir.  
  
     ![POST&#45;koleksiyonu, ayrıntıları görüntülemek için bir aralığı select](media/gfx_diag_gpu_usage_select1.png "gfx_diag_gpu_usage_select1")  
  
3.  Rapor alt kısmında seçin **ayrıntıları görüntüleyin** bağlamak **.. Bu aralık için GPU kullanım ayrıntılarını görüntülemek için burayı** seçiminizin ayrıntılı bir zaman çizelgesi görüntülenecek ileti.  
  
     ![POST&#45;koleksiyonuyla aralık seçili](media/gfx_diag_gpu_usage_select2.png "gfx_diag_gpu_usage_select2")  
  
 Bu raporda yeni bir sekmeli belge açar. GPU kullanım raporu, grafik olay CPU'da başlatıldığında, GPU ulaştığında ve çalıştırmak üzere GPU süreyi görmek için yardımcı olur. Bu bilgiler performans sorunlarını ve artan paralellik kodunuzda olanaklarını belirlemenize yardımcı olabilir.  

<!-- VERSIONLESS -->
## <a name="export-to-gpuview-or-windows-performance-analyzer"></a>GPUView veya Windows Performans Çözümleyicisi verme
Visual Studio 2017 ile başlayarak, bu verileri ile açılabilir [GPUView](/windows-hardware/drivers/display/using-gpuview) ve [Windows Performans Çözümleyicisi](/windows-hardware/test/wpt/windows-performance-analyzer) tıklayarak **GpuView Aç** veya **Aç WPA içinde** Tanılama oturumu alt sağ tarafta bulunan bağlantılar.

![Aç...](media/gfx_diag_open_in.png)
<!-- /VERSIONLESS -->

## <a name="using-the-gpu-usage-report"></a>GPU kullanım raporu kullanma  
 GPU kullanım raporu üst kısmını zaman çizelgeleri CPU işlem etkinlik, GPU işleme etkinliği ve GPU kopyalama etkinliği için görüntüler. Bu zaman çizelgelerini görüntünün vsync temsil açık gri, dikey çubuk tarafından ayrılır; aşağıdakilerden birini görüntüler yenileme hızı çubukları sıklığını eşleşen (kullanılarak seçilen **görüntü** açılan) bu GPU kullanım verileri toplandığı. Görüntü, uygulamanızın performansını hedef daha yüksek bir yenileme hızı olabileceğinden vsync ve elde etmek için uygulamanızın istediğiniz kare hızı 1-1 ilişkisi olmayabilir. Performans hedefine karşılamak için bir uygulama gerekir tüm işleminin tamamlanması, işleme gerçekleştirmek ve hedeflenen kare hızı Present() çağırmaya, ancak işlenmiş çerçeve kadar sonraki vsync Present() sonra görüntülenmez.  
  
 Alt bölümünde raporun dönem boyunca gerçekleşen grafik olaylar listesini görüntüler.  
  
 Burada **GPU kullanım raporu** penceresi:  
  
 ![GPU kullanımı raporla CPU ve GPU'ya zaman çizelgelerini](media/gfx_diag_gpu_usage_report.png "gfx_diag_gpu_usage_report")  
  
 Olaylardan biri raporu alt kısmı seçilmesi yerleştirir bir işaret ilgili zaman çizelgeleri, genellikle bir olay iş parçacığında API çağrısını temsil eden bir CPU ve ne zaman temsil eden GPU zaman çizelgelerini birinde başka bir olay karşılık gelen olayları adresindeki GPU Görev tamamlandı. Benzer şekilde, bir zaman çizelgesinde olayları birini seçerek raporu alt kısmında karşılık gelen olay vurgular. Raporun üst kısmındaki zaman çizelgelerini dışında uzaklaştırılacağını, yalnızca en uzun süren olayları görünür. Daha kısa bir süre olan olayları görmek için Ctrl + tekerleği işaretleme aygıtınızın ya da üst panelde sol alt köşesindeki ölçeklendirme denetimi kullanarak zaman çizelgelerini Yakınlaştır. Kaydedilen olayları taşımak için zaman çizelgesi bölmenin içeriği sürükleyebilirsiniz.  
  
 Aradığınızı bulmanıza yardımcı olmak için GPU kullanım raporu işlem adları, iş parçacığı kimlikleri ve olay adına göre filtre uygulayabilirsiniz; Ayrıca, hangi görüntünün yenileme hızı vysnc satırları belirler seçebilirsiniz ve uygulamanız için Grup işleme komutları ID3DUserDefinedAnnotation arabirimi kullanıyorsa hiyerarşik olarak olayları sıralayın.  
  
 Daha fazla ayrıntı aşağıdadır:  
  
|Filtre denetimi|Açıklama|  
|--------------------|-----------------|  
|**İşlem**|İlgilendiğiniz işlemin adı. GPU tanılama oturum sırasında kullanılan tüm işlemler, bu açılır menüde dahil edilir. Bu açılan işleminde ilişkili renk aşağıdaki zaman çizelgeleri iş parçacığının etkinliğinde rengini ' dir.|  
|**İş parçacığı**|İlgilendiğiniz iş parçacığı kimliği. Çok iş parçacıklı uygulamada, bu ilgilendiğiniz işlemine ait belirli iş parçacığı ayırmanıza yardımcı olabilir. Seçilen iş parçacığı ile ilişkili olaylar her zaman çizelgesinde vurgulanır.|  
|**Görüntüleme**|Yenileme hızı görüntülenir görüntü sayısı **Not:** bazı sürücüler birden çok fiziksel görüntüler büyük, tek bir sanal görüntü sunmak üzere yapılandırılabilir. Makineye bağlı birden çok görüntüler olsa bile, listelenen, yalnızca bir görüntü görebilirsiniz.|  
|**Filtre**|İlgilendiğiniz anahtar sözcükler. Olaylar raporu alt kısmında bir anahtar sözcük tamamen veya kısmen eşleşen olanlar dahil edilir. Noktalı virgül (;) ayırarak, birden çok anahtar sözcükler belirtebilirsiniz.|  
|**Hiyerarşi sıralama**|Kullanıcı işaretçileri--tanımlanan olay hiyerarşilerde--korunur göz ardı ya da olup olmadığını belirten bir onay kutusu.|  
  
 GPU kullanım raporu alt kısmında olayların listesini her olay ayrıntılarını görüntüler.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Olay adı**|Grafik olay adı. Bir olay, genellikle bir CPU iş parçacığı Zaman Çizelgesi'nde bir olay ve tek olay GPU zaman çizelgesinde karşılık gelir.<br /><br /> GPU kullanımı bir olayın adı belirleyemedi olay adları 'unattributed' olabilir. Daha fazla bilgi için bu tablonun altındaki nota bakın.|  
|**CPU başlangıç (ns)**|Olay CPU üzerinde Direct3D API'sini çağırarak başlatıldığı zaman. Uygulama başlatıldığında zamanı göreli nanosaniye cinsinden ölçülür.|  
|**GPU başlangıç (ns)**|Olay üzerinde GPU başlatıldığı zaman. Uygulama başlatıldığında zamanı göreli nanosaniye cinsinden ölçülür.|  
|**GPU süresi (ns)**|Olay nanosaniye GPU'yu tamamlamak için geçen süre.|  
|**İşlem adı**|Olay geldiği uygulamasının adı.|  
|**İş parçacığı kimliği**|Olay geldiği iş parçacığı kimliği.|  
  
> [!IMPORTANT]
>  GPU veya sürücü gereken İzleme özelliklerini desteklemeyen tüm olayları 'unattributed' gösterilmesi gerekir. GPU sürücünüzü güncelleştirin ve bu sorunu yaşarsanız yeniden denemek emin olun. Daha fazla bilgi için bkz: [donanım ve sürücü desteği](#hwsupport) aşağıda.  
  
## <a name="gpu-usage-settings"></a>GPU kullanım ayarları  
 GPU kullanım aracı uygulama başlar başlamaz bilgi toplamak başlangıç yerine bilgi profil oluşturma toplama ertelemek için yapılandırabilirsiniz. Profil bilgilerini boyutunu önemli olabileceğinden, uygulamanızın performansını yavaşlamalara sonraya görünmez bildiğiniz durumlarda kullanışlıdır.  
  
#### <a name="to-postpone-profiling-from-the-start-of-the-app"></a>Uygulama başından profil ertelemek için:  
  
1.  Ana menüde seçin **hata ayıklama**, ardından **performans ve tanılama** (klavye: Alt + F2 tuşuna basın).  
  
2.  Performans ve tanılama hub izleyin **ayarları** bağlantısına **GPU kullanım**.  
  
3.  Altında **GPU profil yapılandırma**, **genel** özellik sayfası, Temizle **uygulama başlangıcında profil başlamak** profil ertelemek için onay kutusunu.  
  
     ![GPU kullanım verisi toplama başladığında, yapılandırma](media/gfx_diag_gpu_usage_config.png "gfx_diag_gpu_usage_config")  
  
> [!IMPORTANT]
>  Profil oluşturma erteleme Direct3D 12 uygulamalar için şu anda desteklenmiyor.  
  
 Uygulamanızı altında GPU kullanım Aracı'nı çalıştırdığınızda, ek bir bağlantı bu ayarı kullanarak profil bilgilerini koleksiyonunu ertelediğinizde GPU kullanım aracı pencerenin alt kısmında kullanılabilir hale gelir. Profil bilgilerini toplamaya başlamak için tercih **Başlat** bağlamak **başlangıç ek toplama ayrıntılı GPU kullanım verilerini** ileti.  
  
##  <a name="hwsupport"></a> Donanım ve sürücü desteği  
 Aşağıdaki GPU donanım ve sürücüler desteklenir:  
  
|Satıcı|GPU açıklaması|Gerekli sürücü sürümü|  
|------------|---------------------|-----------------------------|  
|Intel®|4. nesil Intel® çekirdekli işlemciler ('Haswell')<br /><br /> -Intel® HD grafikleri (GT1)<br />-Intel® HD grafikleri 4200 (GT2)<br />-Intel® HD grafikleri 4400 (GT2)<br />-Intel® HD grafikleri 4600 (GT2)<br />-Intel® HD grafik P4600 (GT2)<br />-Intel® HD grafik P4700 (GT2)<br />-Intel® HD grafikleri 5000 (GT3)<br />-Intel® Iris™ grafik 5100 (GT3)<br />-Intel® Iris™ Pro grafik 5200 (GT3e)|--(en son sürücülere kullanın)|  
|AMD®|Çoğu AMD Radeon™ HD 7000-Serisi (AMD Radeon™ HD 7350 7670 hiç tutar) itibaren<br /><br /> AMD Radeon™ GPU, AMD FirePro™ GPU ve AMD FirePro GPU Hızlandırıcıları grafik çekirdek sonraki (GCN) mimarisi özelliklerine sahip.<br /><br /> AMD® E-serisi ve AMD A-series hızlandırılmış işleme grafik çekirdek sonraki (GCN) mimarisi ('Kaveri', 'Kabini', 'Temash', 'Beema', 'Mullins') özelliklerine sahip birimler (APUs)|14.7 RC3 veya üzeri|  
|NVIDIA®|Çoğu NVIDIA GeForce® 400-serisi itibaren.<br /><br /> NVIDIA® GeForce® GPU, NVIDIA Quadro® GPU ve NVIDIA® Tesla™ GPU Hızlandırıcıları Fermi™, Kepler™ veya Maxwell™ mimarisi özelliklerine sahip.|343.37 veya üzeri|  
  
 Çoklu GPU yapılandırmaları NVIDIA® SLI™ ve AMD Crossfire™ gibi şu anda desteklenmez. NVIDIA® Optimus™ ve AMD Enduro™ gibi karma grafik Kurulum desteklenir.  
  
## <a name="see-also"></a>Ayrıca bkz.  
  
-   [Oyun kullanarak DirectX araçlarınızı (video) ile zorlu grafik sorunları](http://channel9.msdn.com/Events/GDC/GDC-2015/Solve-the-Tough-Graphics-Problems-with-your-Game-Using-DirectX-Tools)  
-   [GPU kullanımı aracı Visual Studio (video)](http://channel9.msdn.com/Events/Visual-Studio/Connect-event-2014/715)  
-   [GPU kullanımı aracında Visual Studio 2013 güncelleştirme 4 CTP1 (blog)](http://blogs.msdn.com/b/vcblog/archive/2014/09/05/gpu-usage-tool-in-visual-studio-2013-update-4-ctp1.aspx)  
-   [GPU kullanımı DirectX Visual Studio (blog)](http://blogs.msdn.com/b/ianhu/archive/2014/12/16/gpu-usage-for-directx-in-visual-studio.aspx)
- [GPUView](/windows-hardware/drivers/display/using-gpuview) 
- [Windows Performans Çözümleyicisi](/windows-hardware/test/wpt/windows-performance-analyzer)