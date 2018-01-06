---
title: Grafik bilgilerini yakalama | Microsoft Docs
ms.custom: 
ms.date: 02/09/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.graphics.frame
- vs.graphics.capturewindow
- VS.ToolsOptionsPages.Graphics_Diagnostics.Capture
ms.assetid: 187ce86e-e340-4f6c-8937-8e8f1027a17f
caps.latest.revision: "41"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 89488533ab8ba36b0344faa7f0b800d8c4ecc6ff
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="capturing-graphics-information"></a>Grafik Bilgilerini Yakalama
Böylece işleme sorunları ve performans sorunları tanılamak için Visual Studio grafik Çözümleyicisi kullanabilirsiniz Direct3D uygulamanızdan grafik bilgilerini yakalama.  
  
## <a name="capturing-graphics-information"></a>Graf bilgilerini yakalama  
 Graf bilgilerini yakalama iki adımlı bir işlemdir. Önce uygulamanızı Grafik Tanılama altında çalıştırın ve sonra ayrıntılı bilgilerini yakalamak üzere bir veya daha fazla kare belirtin.  
  
### <a name="to-run-your-app-under-graphics-diagnostics"></a>Uygulamanızı Grafik Tanılama altında çalıştırmak için  
  
-   Menü çubuğunda seçin **hata ayıklama**, **grafik**, **grafik hata ayıklamayı Başlat**. (Klavye: Alt+F5 tuşlarına basın)  
  
-   Üzerinde **grafik** araç seçin **grafik hata ayıklamayı Başlat** düğmesi.  
  
 Bir uygulama Grafik Tanılama altında çalışırken, belirli grafik bilgisi türleri sürekli olarak yakalanır; bunlar cihaz kurulumu, takas zincirinin oluşturulması, grafik nesnelerinin ve kaynakların oluşturulması ve birden fazla kareyi etkileyen diğer önemli olayları içerir. Aynı zamanda, belirli kareler hakkında ayrıntılı bilgiler yakalayabilirsiniz; Direct3D nesneleri ve bunları destekleyen kaynaklar ile birlikte çizim çağrıları ve hesaplayıcı-gölgelendirici sevkleri buna dahildir.  
  
### <a name="to-capture-a-frame"></a>Bir kareyi yakalamak için  
  
-   Visual Studio'da üzerinde **grafik** araç tıklatın **yakalama çerçeve** düğmesini ![grafik yakalama düğme simgesi](media/debuggingdirectxgraphics.png "DebuggingDirectXGraphics").  
  
-   Klavyede Print Screen tuşuna basın.
  
    > [!NOTE]
    >  Bir uygulama altında çalışırken **grafik tanılama**, Print Screen tuşuna yalnızca grafik bilgilerini çerçeve yakalamak için kullanılabilir; kendi normal işlevini gerçekleştirmez. Başka bir uygulama odakta olsa bile, grafik bilgilerini yakalamayı durduruncaya kadar (genellikle hata ayıklamayı durdurarak veya uygulamadan normal yolla çıkarak) bu durum devam eder.  
  
-   Visual Studio yakalama arabiriminde seçtiğiniz **yakalama çerçeve** düğmesinin bulunan aşağıda **Tanılama oturumu** zaman çizelgesi veya büyük seçin **yakalama çerçeve** düğmesi Aşağıda bulunan **saniyedeki kare** yüz lane ve tüm daha önce yakalanan çerçeve sağındaki. Aşağıdaki görüntü iki düğmeleri vurgulanır.  
  
     ![GPU kullanımı Aracı'nı kullanarak çerçevelerini yakalayın.](media/pix_gpu_usage_tool_capture_frame.png)  
  
     Çerçeve incelemek hazır olduğunuzda, yakalanan, başlangıç **Visual Studio grafik Çözümleyicisi** izleyerek **çerçeve...**  görüntü küçük resimleri yukarıda veya küçük resim çift tıklatarak bağlantıyı.  
  
 Bir yakalama başlatıldığında, gerçekten kaydedilen sonraki çerçeveden grafik bilgilerini olacak şekilde, yalnızca tüm çerçeveler yakalanır. Kayıt, yakalama işlemini başlattığınız kare sunulduktan hemen sonra başlar ve yakalanan kare sunulduğunda sona erer. Uygulama Grafik Tanılama altında çalışırken istediğiniz sayıda kare yakalayabilirsiniz. Hiçbir kare yakalamazsanız, grafik günlüğü atılır.  
  
 Çerçeve yakalarken, Visual Studio Tanılama oturumu (.diagsession) penceresi görüntüler. Bu pencereyi kapatın, hata ayıklamayı durdurun veya uygulamasını kapatın, bu oturum için daha fazla çerçeve yakalama yapılamaz. Daha fazla grafik bilgilerini yakalama için yeni bir tanılama oturumu yeniden başlatmak için grafik tanılamayı altında uygulamayı çalıştırmak sahip.  
  
### <a name="graphics-diagnostics-capture-options"></a>Grafik tanılama yakalama seçenekleri  
 Çağrı yığınları tüm grafik olayları veya sınırlı bir alt kümesinde toplamak, yakalama HUD, devre dışı bırakma ve etkinleştirme veya devre dışı yakalama uyumluluk modu yakalama yapılandırabilirsiniz.  
  
#### <a name="to-configure-graphics-diagnostics-capture-options"></a>Grafik tanılama yakalama seçeneklerini yapılandırmak için  
  
1.  Menü çubuğunda Araçlar, seçenekleri seçin. Seçenekler iletişim kutusu görüntülenir.  
  
2.  Soldaki seçenekleri kategori listesi, grafik Tanılama'yı seçin, ardından istediğiniz grafik tanılama seçenekleri yapılandırın.  
  
     **Çağrı yığınları yakalama sırasında TOPLA (yapar yakalamak daha yavaş)**  
     Çağrı yığınları toplamak için bu onay kutusunu işaretleyin. Varsayılan olarak, çağrı yığınları toplanmadı. Çağrı yığınları yakalamak için olduğundan emin olun **toplama çağrı yığınları yakalama sırasında (yapar yakalamak daha yavaş** onay kutusunu toplamayı etkinleştirmek ve ya da ayarlamak için ayarlanmış **çizim, gönderme, mevcut ve perf işaretlerin**yalnızca en önemli çağrı yığınları, toplanacak seçeneği (varsayılan) veya **her şeyi** tüm çağrı yığınları toplamak için seçeneği. Çağrı yığınları daha sonra toplamayı durdurmak için temizleyin **toplama çağrı yığınları yakalama sırasında (yapar yakalamak daha yavaş** onay kutusu.  
  
     **Oyun HUD yakalama sırasında devre dışı bırak**  
     Grafik altında tanılama genellikle görüntüler çalışan bir uygulama kaplama HUD devre dışı bırakmak için bu kutuyu denetleyin. HUD katmana görüntülemek için onay kutusunu temizleyin.  
  
     **Uyumluluk modunda yakalama**  
     Grafik bilgilerini uyumluluk modunda yakalamak için bu onay kutusunu işaretleyin. Uyumluluk modunda yakalama varsayılandır. Uyumluluk modunda GPU diğer ek özellikleri temel özellik düzeyinde tanımlanan ötesinde desteklediğini Direct3D rapor olmaz. Bu, yakalanan GPU donanım özgü uzantılarını kullanarak üzerinde yakalanan uygulama engeller ve grafik günlük geri aynı veya daha yüksek özellik düzeyini desteklemiyor GPU kullanılarak çalınabilir sağlar. Uyumluluk modu devre dışı bırakmak için bu kutunun işaretini kaldırın; Uyumluluk modu devre dışı yakalanan günlükleri, yakalama sırasında uygulama tarafından kullanılan aynı ek özellikleri desteklemiyor GPU üzerinde çalmak başarısız olur.  
  
     **SDK Katmanlar hataları bulunursa yakalama işlemini durdurun.**  
     Bir hatayla karşılaşılmazsa yakalama hemen durdurmak için bu onay kutusunu işaretleyin.  
  
## <a name="capturing-graphics-information-remotely"></a>Graf bilgilerini uzaktan yakalama  
 Grafik bilgileri, yerel makinede ya da uzak bir makine veya cihazda çalışan bir uygulamadan yakalanabilir. Uzak yakalama için desteklenen [!INCLUDE[winblue_client_2](../includes/winblue_client_2_md.md)] makineler ve [!INCLUDE[winblue_winrt_2](../includes/winblue_winrt_2_md.md)] aygıtlar. Uzakta çalışan bir uygulamadan grafik bilgilerini yakalamak için, projenizi uzaktan hata ayıklama için yapılandırın ve sonra uygulamanızı, daha önce açıklandığı gibi, Grafik Tanılama altında çalıştırın. Uygulama uzak makinede çalışır ve yakalanan grafik bilgileri geliştirme makinenizde kaydedilir.  
  
 Projenizi uzaktan hata ayıklama için yapılandırma şekliniz, geliştirmekte olduğunuz uygulamanın türüne ve kullandığınız programlama diline göre değişir. Uzaktan hata ayıklama bir UWP uygulaması için yapılandırma hakkında daha fazla bilgi için bkz: [uzaktaki bir makinede çalıştırın UWP uygulamaları](../run-windows-store-apps-on-a-remote-machine.md). Bir Windows masaüstü uygulaması için uzaktan hata ayıklama yapılandırma hakkında daha fazla bilgi için bkz: [uzaktan hata ayıklama](../remote-debugging.md).  
  
 Daha sonra, bilgilerin yakalandığı yerden bağımsız olarak, grafik bilgilerini kayıttan yürütmek için bir uzak makine veya cihaz kullanabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: grafik tanılama kayıttan yürütme makinesini değiştirme](how-to-change-the-graphics-diagnostics-playback-machine.md).  
  
## <a name="capturing-graphics-information-from-the-command-line"></a>Komut satırından grafik bilgilerini yakalama  
 Grafik bilgilerini komut satırı aracını kullanarak bir uygulamadan yakalanır. Bu araç, DXCap.exe, hızlı bir şekilde yakalamak ve Visual Studio veya programlı yakalama kullanmadan grafik bilgilerini çalmak. Özellikle, otomasyon için ya da bir test ortamında DXCap.exe kullanabilirsiniz. DXCap.exe hakkında daha fazla bilgi için bkz: [yakalama komut satırı aracı](command-line-capture-tool.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek Yol: Grafik Bilgilerini Yakalama](walkthrough-capturing-graphics-information.md)