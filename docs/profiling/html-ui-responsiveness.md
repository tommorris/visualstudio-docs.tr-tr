---
title: UWP uygulamalarında HTML UI yanıtlama hızını çözümleme | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- JavaScript
helpviewer_keywords:
- performance, JavaScript [UWP apps]
- performance tools, JavaScript [UWP apps]
- UI Responsiveness Profiler [JavaScript]
- profiler, UI responsiveness [JavaScript]
- profiler, JavaScript [UWP apps]
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 7dd31d94552895d42c803df81e1e66cd9a3947f0
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="analyze-html-ui-responsiveness-in-universal-windows-apps"></a>Evrensel Windows uygulamaları, HTML UI yanıtlama hızını çözümleme
Bu konu, UI yanıtlama hızı Profil Oluşturucusu, Evrensel Windows uygulamaları için kullanılabilir bir performans aracını kullanarak uygulamalarınızı performans sorunlarını yalıtma açıklar.  
  
 UI yanıtlama hızı Profil Oluşturucusu UI yanıtlama hızı sorunları veya bu belirtiler ile genellikle oluşan platform yan etkileri gibi sorunları yalıtmak yardımcı olabilir:  
  
-   UI yanıtlama eksiği. Uygulama kullanıcı Arabirimi iş parçacığı engellendi yanıt yavaş olabilir. Kullanıcı Arabirimi iş parçacığı engelleyebilecek bazı şeyleri aşırı zaman uyumlu JavaScript kodu, aşırı CSS düzeni veya CSS hesaplama iş, zaman uyumlu XHR isteklerini, atık toplama, aşırı boyama kez veya işlemci kullanımı yoğun JavaScript kodu içerir.  
  
-   Yavaş yükleme süresi uygulama veya bir sayfa için. Bunun nedeni genellikle kaynakları aşırı zamanın yükleme.  
  
-   Beklenenden daha az sıklıkta visual güncelleştirmeler. Kullanıcı Arabirimi iş parçacığı kesintisiz kare hızı korumak için çok meşgul olduğundan bu oluşur. Örneğin, kullanıcı Arabirimi iş parçacığı meşgul ise, çerçeve bırakılabilir. Bazı kullanıcı Arabirimi iş parçacığı resim çözme, ağ istekleri ve paints de visual güncelleştirmelerinin sıklığını sınırlayabilirsiniz gibi çalışır. (Tüm boyama kullanıcı Arabirimi iş parçacığı üzerinde gerçekleştirilir.)  
  
##  <a name="RunningProfiler"></a> HTML UI yanıtlama hızı aracını çalıştırın  
 Visual Studio'da açın bir çalışma UWP uygulaması varsa, HTML UI yanıtlama hızı aracını kullanabilirsiniz.  
  
1.  Uygulama Visual Studio'dan üzerinde çalıştırıyorsanız, **standart** araç, **hata ayıklamayı Başlat** listesinde, bir dağıtım hedef gibi seçin **yerel makine** veya **Aygıt**.  
  
2.  Üzerinde **hata ayıklama** menüsünde seçin **Performans Profil Oluşturucu...** .  
  
     Çözümleme hedefi için profil oluşturucu değiştirmek istiyorsanız seçin**değiştirmek hedef**.  
  
     ![Değişiklik çözümleme hedef](../profiling/media/js_tools_target.png "JS_Tools_Target")  
  
     Çözümleme hedefi için aşağıdaki seçenekler kullanılabilir:  
  
    -   **Başlangıç projesi**. Geçerli başlangıç projesi analiz etmek için bu seçeneği belirleyin. Bir uzak makinenin veya cihazın uygulama çalıştırıyorsanız, bu ayarı varsayılan değer olan kullanmanız gerekir.  
  
    -   **Uygulama çalışırken**. UWP uygulamasında çalışan uygulamalar bir listeden seçmek için bu seçeneği belirleyin. Bir uzak makinenin veya cihazın uygulama çalıştırırken bu seçeneği kullanamazsınız.  
  
         Kaynak kodu erişimi olmadığında, bilgisayarınızda çalışan uygulamaların performansını çözümlemek için bu seçeneği kullanın.  
  
    -   **Uygulamanın yüklü**. Analiz etmek istediğiniz yüklü bir uygulama seçmek için bu seçeneği belirleyin. Bir uzak makinenin veya cihazın uygulama çalıştırırken bu seçeneği kullanamazsınız.  
  
         Kaynak kodu erişiminiz yoksa, bilgisayarınızda yüklü uygulamaların performansını çözümlemek için bu seçeneği kullanın. Yalnızca kendi uygulama geliştirme dışında herhangi bir uygulama performansını çözümlemek istediğinizde bu seçeneği de yararlı olabilir.  
  
3.  Gelen **kullanılabilen Araçlar**seçin **HTML UI yanıtlama hızı**ve ardından **Başlat**.  
  
4.  UI yanıtlama hızı Profil Oluşturucusu başlattığınızda, bir kullanıcı hesabı denetimi penceresi Visual Studio ETW Collector.exe çalıştırma izni isteyebilir. Seçin **Evet**.  
  
     İlgili performans senaryoyu test etmek için uygulama ile etkileşim. Ayrıntılı bir iş akışı için bkz: [UI yanıtlama hızı yalıtmak](#Workflow) ve [visual verimlilik yalıtmak](#IsolateVisualThroughput).  
  
5.  Alt + Sekme tuşlarına basarak Visual Studio'ya geçin.  
  
6.  Profil Oluşturucu toplanan uygulama ve görünüm veri profil oluşturmayı durdurmak için tercih **durdurmak koleksiyonu**.  
  
##  <a name="IsolateAnIssue"></a> Bir sorun yalıtma  
 Aşağıdaki bölümde, performans sorunlarını ayırmanıza yardımcı olmak için öneriler sağlar. Tanımlamak ve bir örnek performans uygulama testi kullanarak performans sorunlarını gidermek nasıl hakkında adım adım açıklama için bkz: [izlenecek yol: iyileştirme UI yanıtlama hızı (HTML)](../profiling/walkthrough-improving-ui-responsiveness-html.md).  
  
###  <a name="Workflow"></a> UI yanıtlama hızı yalıtmak  
 Bu adımları UI yanıtlama hızı Profil Oluşturucusu daha verimli şekilde kullanmanıza yardımcı olabilecek önerilen bir iş akışı sağlar:  
  
1.  Uygulamanızı Visual Studio'da açın.  
  
2.  UI yanıtlama hızı sorunlar için uygulamanızı test edin. (Hata ayıklama olmadan uygulamanızı başlatmak için Ctrl + F5 tuşuna basın.)  
  
     Bir sorun bulursanız, sorunun oluştuğu zaman çerçevesi daraltmak deneyin veya davranışa neden Tetikleyicileri belirlemeye çalışın test devam edin.  
  
3.  Visual Studio'ya (Alt + Sekme tuşuna basın) geçin ve uygulamanızı (Shift + F5) durdurun.  
  
4.  İsteğe bağlı olarak, kullanıcı işaretleri kullanarak kod ekleme [işaretlemek kod çözümleme için](#ProfileMark).  
  
    > [!TIP]
    >  Kullanıcı işaretleri yanıtlama hızı profil oluşturucu verileri görüntülerken tanımlamaya yardımcı olabilir. Örneğin, bir yanıt hızını soruna neden olan kod bir bölümünü başında ve sonunda bir kullanıcı işareti ekleyebilirsiniz.  
  
5.  UI yanıtlama hızı Profil Oluşturucusu önceki bölümünde yer alan yönergeleri izleyerek çalıştırın.  
  
6.  Uygulama bir UI yanıtlama hızı sorunu sonuçları durumu yerleştirin.  
  
7.  Visual Studio'ya (Alt + Sekme tuşuna basın) geçiş yapın ve seçin **durdurmak koleksiyonu** UI yanıtlama hızı Profil Oluşturucusu'nun profil oluşturucu sekmesinde.  
  
8.  Kullanıcı işaretleri eklediyseniz bunlar görünür [Tanılama oturumu zaman çizelgesi görüntülemek](#Ruler) , profil oluşturucu. Aşağıdaki çizimde, kodunuzda belirli bir işlemi belirtmek için kullanılan bir tek kullanıcı işareti gösterir.  
  
     ![Bir kullanıcı işareti gösteren tanılama cetvel](../profiling/media/js_htmlvizprofiler_usermark.png "JS_HTMLVizProfiler_UserMark")  
  
9. Zaman Çizelgesi ve profil oluşturucu grafikleri bir ilgi kullanıcı işaretleri, uygulama yaşam döngüsü olayları ya da veri grafiklerde görünür kullanarak belirleyin. Analiz etmek ve veri grafiklerde kullanmanıza yardımcı olması için bazı yönergeler şunlardır:  
  
    -   Kullanım [Tanılama oturumu zaman çizelgesi görüntülemek](#Ruler) görüntülemek için [işaretlemek kod çözümleme için](#ProfileMark), uygulama yaşam döngüsü olayları ve bu olayların ilişkili zaman çizelgesi ve diğer grafiklerde veriler için zaman çizelgesi.  
  
    -   Kullanım [CPU kullanım grafiği](#CPUutilization) CPU etkinliği ve belirli bir dönem boyunca işliyor iş türü hakkındaki genel bilgileri görüntülemek için. Aşırı CPU etkinlik dönemlerini yanıtlama sorunlara neden olasılığı daha yüksektir ve iptal edilen çerçeveler.  
  
    -   Oyun ya da zengin medya uygulaması geliştiriyorsanız kullanmak [görünüm visual üretilen işi (FPS)](#VisualThroughput) süreler içinde kare hızı bırakılan tanımlamak için.  
  
10. Grafikleri birinde ilgi alanı grafiğin parçası tıklatarak ve sürükleyerek işaretçiyi seçim yapmak için (veya SEKME tuşuna ve ok tuşlarını kullanarak) seçin. Bir süre seçim yaparak seçtiğinizde, yalnızca seçilen zaman aralığı göstermek için zaman çizelgesi ayrıntıları grafiğin Profil Oluşturucu'nın alt bölmesinde değiştirir.  
  
     Aşağıdaki çizimde vurgulanan ilgi alanı ile CPU kullanım grafiği gösterir.  
  
     ![CPU kullanım grafiği](../profiling/media/js_htmlvizprof_cpu_util.png "JS_HTMLVizProf_CPU_Util")  
  
11. Kullanım [zaman çizelgesi ayrıntıları görüntüleyin](#TimelineDetails) çok sık çalışıyor ya da tamamlamak için çok fazla zaman ayırdığınız olaylar hakkında ayrıntılı bilgi almak için. Örneğin, aşağıdakiler için bakın:  
  
    -   Olay dinleyicileri, zamanlayıcılar ve animasyon çerçeve geri aramalar. Belirli olay bağlı olarak, değiştirilmiş DOM öğeleri, değiştirilmiş CSS özelliklerini adı, kaynak konumu için bir bağlantı kimliği ve ilişkili olay ya da geri çağırma işlevinin adı sağlanan verileri bulunabilir.  
  
    -   Düzeni veya gibi işleme öğelerinde sonuçlandı olayları scripting çağrılar `window.getComputedStyles`. Olayı için ilişkili DOM öğesi sağlanır.  
  
    -   Sayfaları veya HTML olayları Ayrıştırmada betik değerlendirmeleri gibi uygulama tarafından yüklenen URL kaynaklarına. Dosya adı veya kaynak sağlanır.  
  
    -   Belirtilen diğer olayları [profil oluşturucu olay başvuru](#ProfilerEvents).  
  
    > [!TIP]
    >  Profil Oluşturucu kullanılabilir bilgilerin çoğu zaman çizelgesi ayrıntıları grafikte görüntülenir.  
  
12. CPU kullanımı veya visual işleme (FPS) grafik seçili sahip bir alan seçin **yakınlaştırmak** (daha ayrıntılı bilgi almak için düğmesini veya bağlam menüsü). Yalnızca seçilen zaman aralığı göstermek grafiği değişiklikleri için zaman çizelgesi.  
  
13. Yakınlaştırma açık olduğunda, CPU kullanımı veya visual geçiş grafiği bir bölümünü seçin. Ne zaman yalnızca seçilen zaman aralığı göstermek için Profil Oluşturucu'nın alt bölmesinde değişiklikleri zaman çizelgesi ayrıntıları grafiğinde bir seçimi yapın.  
  
###  <a name="IsolateVisualThroughput"></a> Görsel verimlilik yalıtmak  
 Aşırı CPU kullanımı dönemlerini düşük veya tutarsız çerçeve hızları neden olabilir. Zengin medya uygulamaları ve oyunları ortaya çıkarsa, visual geçiş grafiği CPU kullanım grafiği daha fazla önemli veri sağlayabilir.  
  
 Visual verimlilik sorunu ayırt etmek için önceki bölümde açıklanan adımları izleyin, ancak visual geçiş grafiği anahtar veri noktalarını biri olarak kullanın.  
  
###  <a name="ProfileMark"></a> Kod çözümleme için işaretler  
 Grafiklerde Görüntülenen verilerle ilişkili uygulama kodu bir bölümünü yalıtmaya yardımcı olması için kullanıcı işareti eklemek için profil oluşturucu yönlendiren uygulamanızı bir işlev çağrısı ekleyebilirsiniz. — bir ters üçgen — zaman çizelgesi anda işlevi yürütülme. CPU kullanım grafiği, visual geçiş grafiği ve zaman çizelgesi ayrıntıları grafiği için zaman çizelgesi eklediğiniz tüm kullanıcı işareti görünür.  
  
 Bir kullanıcı işareti eklemek için uygulamanız için aşağıdaki kodu ekleyin. Bu örnek olay açıklaması "verileri alınırken" kullanır.  
  
```javascript  
if (performance && performance.mark) {  
    performance.mark("getting data");  
}  
  
```  
  
 Fare işaretçisini kullanıcı işareti getirdiğinizde Olay açıklaması araç ipucu olarak görüntülenir. Gereksinim duyduğunuz kadar çok kullanıcı işaretleri ekleyebilirsiniz.  
  
> [!NOTE]
>  `console.timeStamp`, bir Chrome komut ayrıca kullanıcı işareti görünür.  
  
 Aşağıdaki çizimde bir tek kullanıcı işareti ve araç ipucu ile tanılama cetvel gösterir.  
  
 ![Bir kullanıcı işareti gösteren tanılama cetvel](../profiling/media/js_htmlvizprofiler_usermark.png "JS_HTMLVizProfiler_UserMark")  
  
 Aracı tarafından oluşturulan olaylar, iki kullanıcı işaretleri arasında geçen süreyi göstermek için zaman çizelgesi Ayrıntıları görünümünde de oluşturabilirsiniz. Aşağıdaki kod, ikinci kullanıcı işareti ve (Yukarıdaki kod ilk kullanıcı işareti gösterir) iki kullanıcı işaretleri yürütme arasında geçen süre ölçümü ekler.  
  
```javascript  
if (performance.mark && performance.measure) {  
    performance.mark("data retrieved");  
    performance.measure("data measure", "getting data", "data retrieved");  
}  
```  
  
 İkinci kullanıcı işareti belirtilmezse, `performance.measure` bir zaman damgası ikinci kullanıcı işareti kullanır. İlk kullanıcı işareti gereklidir.  
  
 Süre ölçümü olarak görünür bir **kullanıcı ölçü** Zaman Çizelgesi'nde olay ayrıntıları görünümü ve seçildiğinde ayrıntılı bilgileri gösterir.  
  
 ![Zaman Çizelgesi'nde kullanıcı ölçü Olay Ayrıntıları görünümü](../profiling/media/js_htmlvizprofiler_user_measure.png "JS_HTMLVizProfiler_User_Measure")  
  
##  <a name="AnalyzeData"></a> Verileri analiz etme  
 Aşağıdaki bölümlerde Profil Oluşturucusu'nda görüntülenen verileri yorumlamaya yardımcı olacak bilgiler sağlamaktadır.  
  
###  <a name="Ruler"></a> Görünüm Tanılama oturumu zaman çizelgesi  
 Profil Oluşturucu üstündeki cetvel profili bilgileri için zaman çizelgesi gösterir. Bu zaman çizelgesi, CPU kullanım grafiği ve görsel geçiş grafiği için geçerlidir.  
  
 İlgili tanılama oturumu zaman çizelgesi nasıl birkaç uygulama yaşam döngüsü olayları için görüntülenen bir araç ipucu ile göründüğünü aşağıda verilmiştir:  
  
 ![Tanılama oturumu cetvel](../profiling/media/js_htmlvizprof_ruler.png "JS_HTMLVizProf_Ruler")  
  
 Etkinleştirme olayı gibi uygulama yaşam döngüsü olayları oluşur ve kullanıcı işaretlerini (kullanıcı işareti üçgenler), gösterir zaman çizelgesi gösterir kodunuzu ekleyebilirsiniz. Daha fazla bilgi içeren araç ipuçlarını göster olayları seçebilirsiniz. Kullanıcı işaretleri hakkında daha fazla bilgi için bkz: [işaretlemek kod çözümleme için](#ProfileMark) bu konuda.  
  
 Uygulama yaşam döngüsü olayları elmas simgeler olarak görünür. Bunlar aşağıdakileri içerir DOM olayları şunlardır:  
  
-   `DOMContentLoaded` ve `Load` genellikle kodunuzda etkinleştirilmiş olay işleyicisi oluşan olaylar. Olayı için bir araç ipucu belirli olay ve URL'sini gösterir.  
  
-   Farklı bir sayfaya gittiğinizde oluşan bir gezinti olay. Olayı için bir araç ipucu hedef sayfa URL'si gösterilir.  
  
###  <a name="CPUUtilization"></a> Görünüm CPU kullanımı  
 CPU kullanım grafiği aşırı CPU etkinlik olduğu süre tanımlamanızı sağlar. Uygulamanın ortalama CPU tüketimi bir süre boyunca hakkında bilgi sağlar. Bilgi aşağıdaki belirli kategorileri temsil etmek için ren kodlu: **yüklenirken**, **komut dosyası**, atık toplama (**GC**), **stil**, **İşleme**, ve **görüntü çözülmesi**. Bu kategorileri hakkında daha fazla bilgi için bkz: [profil oluşturucu olay başvuru](#ProfilerEvents) bu konuda daha sonra.  
  
 CPU kullanım grafiği CPU kullanımı değerleri için bir veya daha fazla CPU tek yüzde değeri birleştirerek tüm uygulama iş parçacığı üzerinde harcanan süreyi gösterir. Birden fazla CPU kullanımda olduğunda CPU kullanımı değeri yüzde 100 aşabilir.  
  
> [!NOTE]
>  GPU kullanımı grafikte görünmez.  
  
 Bu örnek, CPU kullanım grafiği nasıl göründüğünü gösterir:  
  
 ![CPU kullanım grafiği](../profiling/media/js_htmlvizprof_cpu_util.png "JS_HTMLVizProf_CPU_Util")  
  
 Bu grafiğe kullanın:  
  
-   Genel sorun alanlarını tanımlayın.  
  
-   Zaman Çizelgesi ayrıntıları grafikte görüntülenecek belirli bir süre seçin. Bir süre seçmek için grafiğin parçası seçin ve seçim yapmak için işaretçiyi sürükleyin.  
  
-   Seçilen zaman aralığı daha ayrıntılı bir görünümünü seçerek elde **yakınlaştırmak** düğmesi.  
  
 Grafik kullanma hakkında daha fazla bilgi için bkz: [UI yanıtlama hızı yalıtmak](#Workflow) bu konuda.  
  
###  <a name="VisualThroughput"></a> Görünüm visual üretilen işi (FPS)  
 Visual geçiş grafiği süreler içinde kare hızı bırakılan belirlemenize olanak sağlar. Uygulama için (FPS) saniyedeki kare gösterilmektedir. Bu grafik, oyun ve zengin medya uygulamaları geliştirme için kullanışlıdır.  
  
 Görüntülenen FPS değeri gerçek kare hızı farklı olabilir. Bu bilgiler, bu grafikte verileri incelerken göz önünde bulundurun:  
  
-   Grafik FPS uygulamayı herhangi belirli bir zamanda elde kapasitesine sahip olduğunu gösterir. Uygulama boştayken FPS İzleyici yenileme hızı ile aynı değil.  
  
-   Grafik gerçek FPS uygulama bir görsel güncelleştirmeleri gerektiren iş yaptığını gösterir.  
  
-   Çerçeve bırakılma, grafik sıfır değeri gösterir.  
  
 Bu örnek visual geçiş grafiği nasıl göründüğünü gösterir:  
  
 ![Görsel geçiş grafiği](../profiling/media/js_htmlvizprof_vizthru.png "JS_HTMLVizProf_VizThru")  
  
 Görsel verimlilik grafiğe kullanın:  
  
-   Genel sorun alanlarını tanımlayın.  
  
-   Zaman Çizelgesi ayrıntıları grafikte görüntülenecek belirli bir süre seçin. Bir süre seçmek için grafiğin parçası seçin ve seçim yapmak için işaretçiyi sürükleyin.  
  
-   Seçilen zaman aralığı daha ayrıntılı bir görünümünü seçerek elde **yakınlaştırmak** düğmesi.  
  
###  <a name="TimelineDetails"></a> Zaman Çizelgesi ayrıntıları görüntüle  
 Zaman Çizelgesi ayrıntıları grafik UI yanıtlama hızı Profil Oluşturucusu alt bölmesinde görüntülenir. Sıralı ve hiyerarşik en fazla CPU süresi Seçilen süreler sırasında tüketilen olaylar hakkında bilgi sağlar. Bu grafik belirli bir olay ne tetiklenen belirlemenize yardımcı olabilir ve bazı olaylar için olay kaynak koduna nasıl eşlendiğini. Bu grafik, ayrıca ekranında visual güncelleştirmeleri boyamak için gereken süreyi belirlemenize yardımcı olur.  
  
 Grafik kullanıcı Arabirimi iş parçacığı çalışma ve çalışma visual güncelleştirmeleri yavaş katkıda bulunabilirsiniz arka plan iş parçacığı üzerinde gösterir. Grafik JavaScript JIT iş, zaman uyumsuz GPU iş, ana bilgisayar işlemi (örneğin, RuntimeBroker.exe ve dwm.exe çalışma) dışında gerçekleşen çalışma veya iş için Windows çalışma zamanı henüz (disk g/ç gibi) profil oluşturma için izleme henüz alanlarını göstermez.  
  
> [!TIP]
>  Arka plan iş parçacığında bir olay ortaya çıktığında, olay adının yanındaki köşeli iş parçacığı kimliği görüntülenir.  
  
 Bu örnek, bir DOM olay dinleyicisi tıklattığınızda olay seçilir ayrıntıları grafik görülüyor ne zaman çizelgesi gösterir:  
  
 ![Zaman Çizelgesi ayrıntıları grafik](../profiling/media/js_htmlvizprof_timelinedet.png "JS_HTMLVizProf_TimelineDet")  
  
 Bu çizimde, **spinAction** olay işleyicisini **olay adı** sütundur bir bağlantı, seçili olduğunda, kaynak kodundaki olay işleyicisi için yönlendirir. Sağ bölmede **geri çağırma işlevi** özelliği, kaynak kodu aynı bağlantısını sağlar. Diğer özellikleri de ilişkili DOM öğesi gibi olaya ilişkin bilgiler sağlar.  
  
 Görsel geçiş (FPS) grafiği ve CPU kullanımı için zaman çizelgesi bir kısmı seçerseniz, zaman çizelgesi ayrıntıları grafik seçilen zaman aralığı için ayrıntılı bilgileri gösterir.  
  
 İş CPU kullanımı grafikte görüntülenen aynı kategorilerini temsil etmek için zaman çizelgesi ayrıntıları grafik olayları kodludur. Olay kategoriler ve belirli olaylar hakkında daha fazla bilgi için bkz: [profil oluşturucu olay başvuru](#ProfilerEvents) bu konuda.  
  
 Zaman Çizelgesi ayrıntıları grafiğe kullanın:  
  
-   Yaklaşık başlangıç zamanlarını, süre ve bitiş zamanları bir olay için bir zaman çizelgesi ve ızgara görünümü görüntüleyin. Zaman Çizelgesi ayrıntıları grafik 30 milisaniye ızgara görünümünde yakınlaştırma durumuna bağlı olarak 30 saniye arasında değişen nokta gösterebilir. Duration değerleri için:  
  
    -   Kapsayıcı kez olay alt öğeler de dahil olmak üzere Olay süresini temsil eder. Izgara Görünümü'nde bu değer ilk olarak görünür.  
  
    -   Özel kez olay alt dahil değil, olay süresini temsil eder. Izgara Görünümü'nde bu değerin parantez içinde görüntülenir.  
  
-   Olay alt öğelerini görüntülemek için hiyerarşideki bir olay genişletin. Olay alt öğe üst olayı tarafından oluşturulan diğer olaylardır. Örneğin, bir DOM olayı alt öğesi olarak görünür olay dinleyicileri olabilir. Olay dinleyicisi, bu sınıftan bir düzen olayı gibi neden diğer olaylar olabilir.  
  
-   Başlangıç sıralama olayların süresi (varsayılan) veya süre. Kullanım **sıralama ölçütü** bir sıralama yöntemi seçin.  
  
-   Ayrıntılar bölmesinde (sağ bölme) her olay için ayrıntıları görüntüleyin. Bu örneklerde görüldüğü gibi özellikleri belirli olay bağlı olarak farklılık gösterir:  
  
    -   Zamanlayıcılar, olay dinleyicileri (DOM olayları) ve animasyon çerçeve geri çağırmalar **geri çağırma işlevi** özelliği, olay işleyicisi veya geri çağırma işlevinin kaynak kodu konuma adı ile birlikte bir bağlantı sağlar.  
  
    -   Seçili olay ve tüm alt öğelerini ren kodlu özetini zamanlayıcılarını, olay dinleyicileri (DOM olayları), Düzen olayları ve animasyon çerçeve geri aramalar için görünür **dahil süre Özet** bölümüne (ren kodlu halka). Görüntünün her ren kodlu dilim bir olay türünü temsil eder. Araç ipuçları olay türü adını sağlayın.  
  
    > [!TIP]
    >  Zaman Çizelgesi ayrıntıları grafik ve **dahil süre Özet** en iyi duruma getirme için alanlar belirlemenize yardımcı olabilir. Bu görünüm ya da çok sayıda küçük görevleri gösteriyorsa, olay iyileştirme aday olabilir. Örneğin, bir uygulama düzeni ve HTML olayları ayrıştırma çok sayıda içinde kaynaklanan yenileme DOM öğeleri sık de olabilir. Bu iş toplu işleme performansını iyileştirmek mümkün olabilir.  
  
###  <a name="FilterTimelineDetails"></a> Filtre zaman çizelgesi ayrıntıları  
 Belirli bir olay için zaman çizelgesi Ayrıntıları görünümünde seçerek filtreleyebilirsiniz **olay filtre** belirli bir olaya ilişkin bağlam menüsünden. Bu seçeneği seçtiğinizde, seçilen olaya zaman çizelgesi ve ızgara görünümü kapsamı olan. CPU kullanım grafiği seçim ayrıca belirli olay kapsamları.  
  
 ![Bir olay zaman çizelgesine filtre](../profiling/media/js_htmlvizprofiler_filtertoevent.png "JS_HTMLVizProfiler_FilterToEvent")  
  
###  <a name="FilterEvents"></a> Olaylar filtresi  
 Bazı olaylar veri gürültü azaltın ya da performans senaryonuz için ilginç olmayan veriler ortadan kaldırmak için zaman çizelgesi ayrıntıları grafikten çıkışı filtre uygulayabilirsiniz. Olay adı ya da olay süresi veya burada açıklanan belirli filtreler tarafından filtre uygulayabilirsiniz.  
  
 Görüntü kod çözme olmadığını, bunun kurgusal indiriliyor ve GC olayları filtrelemek için temizleyin **arka plan etkinliği** alt bölmesinde filtre simgesinden seçeneği. Bu olaylar çok işlem yapılabilir olmadığından, bunlar varsayılan olarak gizlidir.  
  
 ![Zaman Çizelgesi olayları filtreleme](../profiling/media/js_htmlvizprofiler_event_filter.png "JS_HTMLVizProfiler_Event_Filter")  
  
 HTTP istek olayları filtrelemek için temizleyin **ağ trafiğini** alt bölmesinde filtre simgesinden seçeneği. Varsayılan olarak, bu olayları zaman çizelgesi ayrıntıları grafiğinde gösterilir.  
  
 Kullanıcı Arabirimi iş parçacığı etkinliği filtrelemek için temizleyin **UI etkinlik** seçeneği.  
  
> [!TIP]
>  Bu seçeneği temizleyin ve ağ gecikmesini ilgili sorunları araştırmak için ağ trafiğini seçeneğini belirleyin.  
  
 Kullanıcı ölçüleri filtrelemek için temizleyin **kullanıcı ölçüleri** seçeneği. Kullanıcı, hiç alt öğe üst düzey olaylarla yöntemleridir.  
  
###  <a name="GroupFrames"></a> Çerçeve Grup olayları  
 Tek tek çerçeveler için zaman çizelgesi Ayrıntıları görünümünde görüntülenen olayları gruplandırabilirsiniz. Bu çerçeve olayları aracı tarafından oluşturulan olaylar ve boyama olayları arasında gerçekleşen tüm kullanıcı Arabirimi iş parçacığı iş için en üst düzey olay kapsayıcıları temsil eder. Bu görünümü etkinleştirmek için seçin **üst düzey olayları çerçeveleri tarafından grup**.  
  
 ![Üst düzey olayları çerçevesi tarafından grup](../profiling/media/js_htmlvizprofiler_frame_grouping_button.png "JS_HTMLVizProfiler_Frame_Grouping_Button")  
  
 Olayları çerçeve göre gruplandırdığınızda, üst düzey olayları zaman çizelgesi ayrıntıları her temsil bir çerçeve görüntüleyin.  
  
 ![Çerçeve göre gruplandırılmış zaman çizelgesi olayları](../profiling/media/js_htmlvizprofiler_frame_grouping.png "JS_HTMLVizProfiler_Frame_Grouping")  
  
##  <a name="SaveSession"></a> Tanılama oturumu Kaydet  
 Visual Studio'da oturum ile ilişkili sekme kapattığınızda Tanılama oturumu kaydedebilirsiniz. Daha sonra kaydedilmiş oturumları açılabilir.  
  
##  <a name="ProfilerEvents"></a> Profil Oluşturucu Olay Başvurusu  
 Profil Oluşturucu olayları kategorilere ve UI yanıtlama hızı Profil Oluşturucusu'nda renkli kodlu. Bu olay kategorileri şunlardır:  
  
-   **Yükleniyor.** Uygulamayı ilk kez yüklediğinde alınırken uygulama kaynakları ve ayrıştırma HTML ve CSS harcanan zamanı gösterir. Bu ağ isteklerini içerebilir.  
  
-   **Komut dosyası.** Zamanın ayrıştırma ve JavaScript çalıştıran gösterir. Bu DOM olayları, zamanlayıcılar, komut dosyası değerlendirme ve animasyon çerçeve iş içerir. Kullanıcı kodu ve kitaplık kodu içerir.  
  
-   **GC.** Çöp toplama harcadığı zamanı gösterir.  
  
-   **Stil.** Ayrıştırma CSS ve hesaplama öğesi sunu ve düzeni harcanan zamanı gösterir.  
  
-   **İşleme.** Saati gösteren ekran boyama harcanan.  
  
-   **Kod çözme görüntü.** Boyutunda ve görüntüleri kod çözme harcanan zamanı gösterir.  
  
 UI yanıtlama hızı profil oluşturucu komut dosyası ve stil kategorileri için zaman çizelgesi ayrıntıları grafikte üzerinde davranamaz veri sağlayabilir. Bir sorun olarak betik sorunları belirlemek, CPU örnekleme profil oluşturucu UI yanıtlama hızı Profil Oluşturucu ile çalıştırabilirsiniz. Alternatif olarak, daha ayrıntılı verileri elde etmek için Visual Studio işlevi profil oluşturucu kullanabilirsiniz. Daha fazla bilgi için bkz: [JavaScript belleği](../profiling/javascript-memory.md).  
  
 Diğer olay kategorileri için uygulamanıza özellik ekleme neden platform yan etkileri tanımlamak olabilir, ancak bu durumlarda, UI yanıtlama hızı Profil Oluşturucusu kullanarak belirli performans sorunlarını gidermeniz mümkün olmayabilir.  
  
 Bu tabloda, olayları ve açıklamaları gösterilmektedir:  
  
|Olay|Olay kategorisi|Oluşur olduğunda|  
|-----------|--------------------|-----------------|  
|CSS ayrıştırma|Yükleme|Yeni CSS içerik karşılaşıldı ve CSS içeriğini ayrıştırmak için bir girişimde bulunuldu.|  
|HTML Ayrıştırma|Yükleme|Yeni HTML içeriğini karşılaşıldı ve içeriği düğümlerin içine ayrıştırma ve içeriği DOM ağacına eklemek için girişimde bulunuldu.|  
|HTTP isteği|Yükleme|Bir XMLHttpRequest bir HTTP isteği sonuçlanan oluşturuldu veya uzak bir kaynak DOM'da bulunamadı.|  
|İndirme kurgusal|Yükleme|Sayfanın HTML içeriğini, böylece sonraki HTTP istekleri kaynaklara ilişkin hızlı bir şekilde zamanlanabilir için gerekli kaynakları arama.|  
|Animasyon çerçeve geri çağırma işlevi|Betik Oluşturma|Tarayıcı başka bir çerçeve işlemeye devam ve bu bir uygulama tarafından sağlanan geri çağırma işlevi tetiklenir.|  
|DOM olayı|Betik Oluşturma|DOM olayı oluştu ve yürütüldü.<br /><br /> `context` DOM olay özelliği gibi `DOMContentLoaded` veya `click`, parantez içinde görüntülenir.|  
|Olay dinleyicisi|Betik Oluşturma|Olay dinleyicisi adı ve yürütülür.|  
|Medya sorgu dinleyicisi|Betik Oluşturma|Kayıtlı medya sorguda, ilişkili listener(s) yürütme sonuçlandı geçersiz kılındı.|  
|Mutasyon gözlemci|Betik Oluşturma|Bir veya daha fazla olan bir MutationObserver'ın ilişkili geri çağırma yürütme sonuçlandı DOM öğeleri değiştirildi gözlenen.|  
|Komut dosyası değerlendirme|Betik Oluşturma|Yeni bir komut dosyası öğesi DOM'da bulundu ve ayrıştıracak ve komut dosyası için bir girişimde bulunuldu.|  
|Zamanlayıcı|Betik Oluşturma|Zamanlanmış bir süreölçer geçen ve bu onun ilişkili geri çağırma işlevini yürütme sonuçlandı.|  
|Windows çalışma zamanı zaman uyumsuz geri çağırma işlevi|Betik Oluşturma|Tetiklenen bir zaman uyumsuz işlemi bir `Promise` geri çağırma işlevi, bir Windows çalışma zamanı nesnesi tarafından tamamlandı.|  
|Windows çalışma zamanı olay|Betik Oluşturma|Kayıtlı bir dinleyici Windows çalışma zamanı nesne üzerinde gerçekleşen bir olay tetiklenir.|  
|Atık toplama|GC|Artık kullanımda olan nesneler için bellek toplamak için harcanan süre.|  
|CSS hesaplama|Stil oluşturma|Hesaplanacak tüm etkilenen öğeler stil özelliklerini gerekli DOM değişiklikler yapıldı.|  
|Düzen|Stil oluşturma|Boyutu ve/veya yeniden hesaplanması gerektiği için tüm etkilenen öğeler konumunu gerekli DOM değişiklikler yapıldı.|  
|Boyama|İşleme|DOM Visual değişiklikler yapıldı ve sayfa bölümünü yeniden işlemek için girişimde bulunuldu.|  
|Katman işleme|İşleme|(Bir katman olarak adlandırılır) DOM bağımsız olarak işlenen bir parçasını Visual değişiklikler yapıldı ve değişiklikleri işlenmek üzere sayfasının bir kısmı gerekli.|  
|Görüntü kod çözme|Görüntü kod çözme|Bir görüntü DOM'da eklenmiştir ve sıkıştırmasını açın ve özgün biçiminde görüntüden bir bit eşlem kod çözme için girişimde bulunuldu.|  
|Çerçeve|Yok|Etkilenen tüm bölümleri çizilmesi için sayfanın gerekli DOM Visual değişiklikler yapıldı. Bu gruplandırma için kullanılan aracı tarafından oluşturulan bir olaydır.|  
|Kullanıcı ölçü|Yok|Bir uygulamaya özgü senaryosunu kullanarak ölçülen `performance.measure` yöntemi. Bu kod çözümlemek için kullanılan aracı tarafından oluşturulan bir olaydır.|  
  
##  <a name="Tips"></a> Ek bilgi  
  
-   Gözcü [bu videoyu](http://channel9.msdn.com/Events/Build/2013/3-316) UI yanıtlama hızı Profil Oluşturucusu hakkında yapı 2013 konferans gelen.  
  
-   JavaScript kullanan Windows için oluşturulmuştur UWP uygulamaları için performans ipuçları okuyun. Daha fazla bilgi için bkz: [JavaScript kullanarak UWP uygulamaları için performans en iyi uygulamaları](http://msdn.microsoft.com/library/windows/apps/hh465194.aspx).  
  
-   Tek iş parçacıklı kod yürütme modeli ve performans ile ilgili daha fazla bilgi için bkz: [kod yürütmek](http://msdn.microsoft.com/library/windows/apps/hh781217.aspx).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Profil Araçları](../profiling/profiling-tools.md)