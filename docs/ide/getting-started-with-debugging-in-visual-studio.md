---
title: "Visual Studio'da hata ayıklamaya başlama | Microsoft Docs"
ms.custom: 
ms.date: 12/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3a14d28-d811-4ff3-bd09-21dce14025ca
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c75b5508cd23a2131bcdd64cf52aacc1486d2713
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="get-started-with-debugging-in-visual-studio"></a>Visual Studio'da hata ayıklamaya başlama
Visual Studio Proje derleme ve hata ayıklama araçları güçlü tümleşik kümesi sağlar. Bu konuda, kullanıcı Arabirimi özelliklerini hata ayıklama en temel kümesi'ni kullanmaya başlamak öğrenin.  

## <a name="my-code-doesnt-work-help-me-visual-studio"></a>Kodumu işe yaramaz. Bana, Visual Studio Yardım!  
 Out Düzenleyicisi dahil edilir böylece ve bazı kodlar oluşturduysanız. Şimdi, bu kod hata ayıklamayı başlatmak istiyor. Visual Studio'da çoğu IDE gibi ile hata ayıklama için iki aşama vardır: yakalamak ve proje ve derleyici hataları; çözümlemek için kod oluşturma Bu kodu yakalamak ve çalışma zamanı ve dinamik hatalarını gidermek için ortamında ve çalıştırma.  

### <a name="build-your-code"></a>Kodunuzu oluşturma  
 Yapı yapılandırması iki temel tür vardır: **hata ayıklama** ve **sürüm**. İlk yapılandırmayı daha zengin etkileşimli çalışma zamanı hata ayıklama için bir deneyim sağlar, ancak hiçbir zaman sevk gereken daha yavaş ve daha büyük bir yürütülebilir üretir. İkinci sevk etmek uygun olan bir daha hızlı ve daha iyileştirilmiş yürütülebilir dosyası oluşturur (en az derleyici perspektifinden). Varsayılan derleme yapılandırma **hata ayıklama**.

Projenizi derleme için en kolay yolu basmaktır **F7**, ancak derleme seçerek de başlatabilirsiniz **Yapı > Yapı çözümü** ana menüden.  

 ![Visual Studio Proje menüsü Seçimi Yapı](../ide/media/vs_ide_gs_debug_build_menu_item.png "Vs_ide_gs_debug_build_menu_item")  

 Yapı işleminde gözleyebilirsiniz **çıkış** Visual Studio kullanıcı arabirimini ekranın alt kısmındaki durum penceresi. Hataları, uyarıları ve yapı işlemleri burada görüntülenir. Hataları (veya yapılandırılmış bir düzeyin üzerinde bir uyarı varsa) varsa, derleme başarısız olur. Hataları ve Uyarıları nerede oluştuğunu satıra gitme tıklatabilirsiniz. Projenizi yeniden oluşturun ya da tuşlarına basarak **F7** yeniden (yalnızca hatalar dosyalarıyla yeniden derleyin için) veya **Ctrl + Alt + F7** (için temiz ve eksiksiz rebuild).  

 Düzenleyici aşağıda Sonuçları penceresinde sekmeli windows iki yapı vardır: **çıkış** (hata iletileri de dahil olmak üzere) çıkış; ham derleyici içeren pencere ve **hata listesi** penceresinde hangi tüm hataların ve uyarıların sıralanabilir ve filtrelenebilir listesini sağlar.  

 Başarılı olduğunda, bu şekilde sonuçları görürsünüz **çıkış** penceresi.  

 ![Visual Studio başarılı yapı çıktısını](../ide/media/vs_ide_gs_debug_success_build.PNG "vs_ide_gs_debug_success_build")  

### <a name="review-the-error-list"></a>Hata listesini gözden geçirin  
 Daha önce ve başarılı bir şekilde derledik kod değişiklik yapmış olduğunuz sürece, muhtemelen bir hata vardır. Kodlama için yeniyseniz, bunları çok sayıda'de vardır. Bazen hatalar basit söz dizimi hatası veya hatalı değişken adı gibi belirgin ve bazı durumlarda, size yol göstermesi için yalnızca bir şifreli koduyla anlaşılması güç. Sorunları temizleyici görünümü için derleme alt kısmına gidin **çıkış** penceresi ve tıklatın **hata listesi** sekmesi. Bu hataları ve Uyarıları projeniz için daha düzenli bir görünümünü sürer ve bazı ek seçenekler de sunar.  

 ![Visual Studio çıkış ve hata listesi](../ide/media/vs_ide_gs_debug_bad_build_error_list.PNG "Vs_ide_gs_debug_bad_build_error_list")  

 Tıklatın hata satırında **hata listesi** penceresini açın ve hata oluşuyor satır atlanır. (Veya satır numaralarını tıklayarak açmak **hızlı başlatma** "numaraları içine satır" yazın ve Enter tuşuna basarak sağ üst, çubuğunda. Bu almak için en hızlı yoludur **seçenekleri** Burada, açmanız satır numaralarını penceresi girişi. Kullanmayı öğrenin **hızlı başlatma** çubuğunu ve kendiniz çok UI tıklama kaydedin!)  

 ![Satır numaraları ile Visual Studio düzenleyicisinde](../ide/media/vs_ide_gs_debug_line_numbers.png "Vs_ide_gs_debug_line_numbers")  

 ![Visual Studio satır numaraları seçeneği](../ide/media/vs_ide_gs_debug_options_line_numbers.png "Vs_ide_gs_debug_options_line_numbers")  

 Kullanım **Ctrl + G** hatanın oluştuğu satır numarası hızla atlamak için.  

 Hata bir kırmızı "dalgalı çizgi" alt çizgi tarafından tanımlanır. Daha fazla ayrıntı için üzerine gelin. Düzeltme yapın ve düzeltmeler ile yeni bir hata neden olabilir ancak bu, kaybolur. (Bu bir "gerileme" olarak adlandırılır.)  

 ![Visual Studio hata vurgulu](../ide/media/vs_ide_gs_debug_error_hover1.png "Vs_ide_gs_debug_error_hover1")  

 Hata listesi yol ve kodunuzdaki tüm hataları çözün.  

 ![Visual Studio hata ayıklama hataları penceresi](../ide/media/vs_ide_gs_debug_error_list.PNG "Vs_ide_gs_debug_error_list")  

### <a name="review-errors-in-detail"></a>Ayrıntılı hataları gözden geçirin  
 Birçok hata hiçbir derleyici şartlarında oldukları gibi tümcecik oluşturulmuş sizin için anlamlı olabilir. Bu durumda, ek bilgilere ihtiyacınız olacaktır. Gelen **hata listesi** penceresi, hata (veya uyarı) ile ilgili giriş satırına sağ tıklayıp seçerek hakkında daha fazla bilgi için otomatik bir Bing arama yapabilir **hata yardımını göster** gelen bağlam menüsü.  

 ![Visual Studio hata listesi Bing arama](../ide/media/vs_ide_gs_debug_error_list_error_help.png "Vs_ide_gs_debug_error_list_error_help")  

 Bu sekme Visual Studio içinde barındıran bir Bing sonuçlarını hata kodu ve metin arama başlatır. Internet üzerindeki birçok farklı kaynaktan sonuçlar olur ve tüm yararlı olabilir.  

 Alternatif olarak, köprülü hata kodu değeri tıklatabilirsiniz **kod** sütunu **hata listesi**. Bu yalnızca hata kodu için Bing arama başlatır.  

### <a name="use-light-bulbs-to-fix-or-refactor-code"></a>Kodu yeniden düzenleyin veya için ampuller kullanın  
 Ampuller sağlayan Visual Studio için yeni bir özellik olan kodu satır içi yeniden düzenleyin. Sık kullanılan uyarılar düzeltmek için kolay bir yol oldukları hızlı ve etkili şekilde. Bunları erişmek için bir uyarı dalgalı sağ tıklayın (veya basın **Ctrl +**. Dalgalı bekleyerek), çalışırken ve ardından **hızlı Eylemler**.  

 ![Visual Studio ampul hızlı seçenekleri](../ide/media/vs_ide_gs_debug_light_bulb1.png "Vs_ide_gs_debug_light_bulb1")  

 Olası düzeltmeler veya bu kod satırına uygulayabilirsiniz refactors listesini görürsünüz.  

 ![Visual Studio ampul Önizleme](../ide/media/vs_ide_gs_debug_light_bulb_preview_changes.PNG "Vs_ide_gs_debug_light_bulb_preview_changes")  

 Ampuller, düzenleme, düzeltmek veya kodunuzu iyileştirmek için bir fırsat kodu çözümleyiciler belirlemek her yerde kullanılabilir. Herhangi bir kod satırında, bağlam menüsünü açmak için sağ tıklayıp **hızlı Eylemler** (veya yeniden, verimliliği tercih ederseniz, basın **Ctrl +**.). Yeniden düzenleme veya geliştirme seçenekleri yoksa bunlar görüntülenir; Aksi takdirde, ileti `No quick options available here` IDE sol alt köşesinde çerçeve içinde görüntülenir.  

 ![Visual Studio ampul 'seçeneği' metin](../ide/media/vs_ide_gs_debug_light_bulb_no_options.PNG "Vs_ide_gs_debug_light_bulb_no_options")  

 Deneyim, hızlı bir şekilde ok tuşlarını kullanabilirsiniz ve **Ctrl +**. Hızlı fırsatları yeniden düzenleme seçeneği işaretleyin ve kodunuzu temizlemek amacıyla!  

 Ampuller hakkında daha fazla bilgi için okuma [ampullerle hızlı eylemler gerçekleştirme](../ide/perform-quick-actions-with-light-bulbs.md).  

### <a name="debug-your-running-code"></a>Çalışan kodda hata ayıklama  
 Başarıyla kodunuzu yerleşik artık ve biraz temizleme gerçekleştirilen göre çalıştırın tuşlarına basarak **F5** veya seçerek **hata ayıklama > hata ayıklamayı Başlat**. Ayrıntılı kendi davranış gözlenir şekilde bu bir hata ayıklama ortamında uygulamanızı başlatacak. Visual Studio IDE değişiklikleri uygulamanızı çalışırken: **çıkış** penceresi (varsayılan yapılandırmasında penceresi), iki yenilerini almıştır **Yereller/otomobiller/izleme** sekmeli pencere ve **Çağrı yığını/kesme noktaları/özel durum ayarları/çıkış** sekmeli penceresi. Bu windows inceleyebilir ve çalışırken, uygulamanızın değişkenleri, iş parçacıkları, çağrı yığınları ve çeşitli diğer davranışlarını değerlendirmek olanak tanıyan birden fazla sekme sahip.  

 ![Visual Studio otomobiller ve çağrı yığınını Windows](../ide/media/vs_ide_gs_debug_autos_and_call_stack.PNG "Vs_ide_gs_debug_autos_and_call_stack")  

 Tuşlarına basarak uygulamanızı durdurabilirsiniz **Shift + F5** veya tıklatarak **durdurmak** düğmesi. Veya, yalnızca uygulamanın ana penceresinde (veya komut satırı iletişim) kapatabilirsiniz.  

 Kodunuzu mükemmel çalıştırdıysanız ve tam olarak beklenen, Tebrikler! Ancak, askıda, veya kilitlendi veya bazı garip sonuçları vermiş, bu sorunların kaynağı bulmak ve hataları düzeltmek gerekir.  

### <a name="set-simple-breakpoints"></a>Set basit kesme noktaları  
 Kesme noktaları güvenilir hata ayıklama en temel ve temel özelliğidir. Bir kesme noktası değişkenlerin değerleri veya bellek davranışını göz olabilmesi için Visual Studio çalışan kodunuzu nereye askıya almanız veya kod dalı çalıştırmak destekleyip desteklemediğini belirtir. Ayarlama ve kesme noktaları kaldırma sonrasında bir projeyi yeniden gerekmez.  

 Tuşuna basın veya oluşabilir sonu istediğiniz kadar boşlukta satırının tıklatarak bir kesme noktası ayarlayın **F9** geçerli kod satırında bir kesme noktası ayarlamak için. Kodunuzu çalıştırdığınızda, duraklatmak (veya *sonu*) Bu kod satırı yönergelerini yürütülmeden önce.  

 ![Visual Studio kesme noktası](../ide/media/vs_ide_gs_debug_breakpoint1.png "Vs_ide_gs_debug_breakpoint1")   

 Kesme noktaları için yaygın kullanımları şunlardır:  

1.  Kilitlenme veya askı kaynağı daraltmak için bunları boyunca ve hataya neden olduğunu düşündüğünüz yöntem çağrısı kodunu çözmek dağılım. Hata ayıklayıcıda kod çalıştırmadan olarak kaldırın ve soruna neden olan kod satırı ile bulana kadar yakın kesme noktaları birlikte sıfırlayın.  Hata ayıklayıcıda kod çalıştırmayı öğrenmek için sonraki bölüme bakın.

2.  Yeni kod katılırsa, bunu başında bir kesme noktası ayarlayın ve beklendiği şekilde davrandığından emin olmak için kodu çalıştırın.

3.  Karmaşık bir davranış uyguladıysanız, program böldüğünde değişkenleri ve veri değerlerini inceleyebilirsiniz şekilde algoritmik kodu için kesme noktaları ayarlayın.  

4.  C veya C++ kodu, kod durdurmak için kullanım kesme noktaları bunu yazıyorsanız, bellekle ilgili hataları için hata ayıklama sırasında adres değerleri (NULL bakın) ve başvuru sayıları inceleyebilirsiniz.  

 Kesme noktaları kullanma hakkında daha fazla bilgi için okuma [kullanarak kesme noktaları](../debugger/using-breakpoints.md).  

### <a name="inspect-your-code-at-run-time"></a>Çalışma zamanında kodunuzu inceleyin.  
 Çalışan kodunuzu bir kesme noktası ve duraklatır geldiğinde, sarı (geçerli deyimi) olarak işaretlenmiş kod satırı henüz yürüttü değil. Bu noktada, geçerli deyimini yürütün ve sonra değiştirilmiş değerleri incelemek isteyebilirsiniz. Birkaç kullanabilirsiniz *adım* Hata Ayıklayıcısı'ndaki kod yürütmek için komutları. İşaretli kodu yöntem çağrısı ise, içine tuşlarına basarak adım **F11**. Ayrıca *üzerinden adım* basarak kod satırı **F10**. Ek komutlar ve aracılığıyla koda adım hakkında ayrıntılar için okuma [kod hata ayıklayıcısını kullanmaya gidin](../debugger/navigating-through-code-with-the-debugger.md).

 ![Visual Studio çalışma &#45; saat değeri denetleme](../ide/media/vs_ide_gs_debug_hit_breakpoint.PNG "vs_ide_gs_debug_inspect_value") 

 Önceki çizimde, hata ayıklayıcı bir deyim ya basarak ilerletebilirsiniz **F10** veya **F11** (hiçbir yöntem çağrısı olduğundan, her iki komut aynı sonucu vardır).

 Hata ayıklayıcı duraklatıldığında değişkenlerinizi inceleyebilir ve çağrı yığınları neler olduğunu belirlemek için. Değerleri görmeyi beklediğiniz aralıklardaki misiniz? Çağrılar doğru sırayla yapılır?  

 ![Visual Studio çalışma &#45; saat değeri denetleme](../ide/media/vs_ide_gs_debug_inspect_value.PNG "vs_ide_gs_debug_inspect_value")  

 Şu anda içeren alanlara ve değerleri görmek için bir değişken gelin. Beklemediğiniz bir değer görürseniz, önceki veya arama kod satırıyla, büyük olasılıkla bir hata bulunmaktadır.  Daha ayrıntılı bilgi için [daha fazla bilgi edinin](../debugger/getting-started-with-the-debugger.md) hata ayıklayıcıyı kullanma hakkında. 

 Ayrıca, Visual Studio Burada, uygulamanızın CPU ve bellek kullanımı zamanla inceleyebileceğiniz tanılama araçları penceresini görüntüler. Daha sonra uygulama geliştirme, beklenmeyen yoğun CPU kullanımı veya bellek ayırma için aramak için bu araçları kullanabilirsiniz. İle birlikte kullanmak **izleme** penceresini açın ve ne beklenmeyen ağır kullanımı veya yayımlanmamış kaynakları neden olduğunu belirlemek için kesme noktaları.  Daha fazla bilgi için bkz: [özelliği turu profil](../profiling/profiling-feature-tour.md).

### <a name="run-unit-tests"></a>Birim testleri çalıştırma  
 Birim testleri çünkü doğru yapıldığında, bunlar tek bir kod, tek bir işlev genellikle, "Birim" test, ilk karşı savunma hattı kod hataları ve tam programınızı hata ayıklama daha hata ayıklamak genellikle çok daha kolay. Visual Studio hem yönetilen hem de yerel kod için Microsoft birim test çerçevelerini yükler. Birim testleri oluşturmak, bunları çalıştırmak ve sonuçları bu testler, rapor için bir birim testi çerçevesi kullanın. Kodunuzun doğru şekilde çalışıp çalışmadığını sınamak için değişiklik yaptığınız zaman yeniden çalıştır birim testleri. Visual Studio Enterprise edition kullandığınızda, her yapıdan sonra otomatik olarak testleri çalıştırabilirsiniz.  

 Başlamak için okuma [Intellitest ile kodunuz için birim testleri oluşturmak](../test/generate-unit-tests-for-your-code-with-intellitest.md).  

 Visual Studio ve nasıl bunlar daha iyi kalite kod oluşturmanıza yardımcı olabilir birim testleri hakkında daha fazla bilgi için okuma [birim testi Temelleri](../test/unit-test-basics.md).  

### <a name="perform-static-code-analysis"></a>Statik kod çözümlemesi  
 "Statik kod analizi", "kodumu çalışma zamanı hataları neden olabilecek yaygın sorunlar veya kod yönetimi sorunları için otomatik olarak denetle" etkisine süslü bir yoludur. Yapı önleme belirgin hataları temizledikten sonra onu çalıştıran biri alýþkanlýk almak ve bunu üretebilir uyarıları gidermek için biraz zaman alabilir. Kendiniz bazı zorlukların yol aşağı Kaydet yanı birkaç kod stili teknikleri öğrenin.  

 Tuşuna **Alt + F11** (veya seçin **Çözümle > çalıştırmak Kod Analizi çözüm üzerinde** üstteki menüden) statik kod analizi başlatmak için. Çok fazla kod varsa, bu biraz zaman alabilir.  

 ![Visual Studio Kod Analizi menü öğesi](../ide/media/vs_ide_gs_debug_run_code_analysis.png "Vs_ide_gs_debug_run_code_analysis")  

 Tüm yeni veya güncelleştirilmiş uyarılar görünür **hata listesi** IDE ekranın alt kısmındaki sekme. Bunları atlamak için Uyarılar'ı tıklatın.  

 ![Visual Studio hata listesi uyarılarla](../ide/media/vs_ide_gs_debug_code_analysis_warning_error_list.PNG "vs_ide_gs_debug_code_analysis_warning_error_list")  

 Uyarılar yerine kırmızı bir açık sarı yeşil dalgalı ile tanımlanır. Daha fazla ayrıntı için üzerlerine getirin ve bunları düzeltmeleri veya yeniden düzenleme seçenekleri yardımcı olmak için bir bağlam menüsü almak için sağ tıklayın.  

 ![Visual Studio kod çözümleme uyarısı vurgulu](../ide/media/vs_ide_gs_debug_code_analysis_warning_hover.png "vs_ide_gs_debug_code_analysis_warning_hover")  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı özelliği turu](../debugger/debugger-feature-tour.md)  
 [Hata ayıklayıcıyı kullanma hakkında daha fazla bilgi edinin](../debugger/getting-started-with-the-debugger.md)
