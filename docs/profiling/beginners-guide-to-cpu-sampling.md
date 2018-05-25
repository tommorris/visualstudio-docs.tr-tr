---
title: CPU örnekleme Visual Studio için Başlangıç Kılavuzu | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 02/27/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.wizard.intropage
helpviewer_keywords:
- Profiling Tools, quick start
- performance tools, wizard
- Performance Wizard
ms.assetid: 85161cc4-18ee-49b3-9487-33680e687597
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c3a3e7786b56f33bec4d742b1ebd6c450ea14e09
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2018
---
# <a name="beginners-guide-to-cpu-sampling"></a>CPU örnekleme için Başlangıç Kılavuzu
Profil Araçları Visual Studio, uygulamanızda performans sorunlarını çözümlemek için kullanabilirsiniz. Bu yordam nasıl kullanılacağını gösterir **örnekleme** veri.

> [!NOTE]
>  Şunu kullanmanızı öneririz [CPU kullanımı](../profiling/beginners-guide-to-performance-profiling.md) aracı eski CPU örnekleme aracı yerine tanılama araçları penceresindeki araçları desteği gibi yeni özellikler gerekmedikçe.
  
 **Örnekleme** uygulamada kullanıcı modu çoğunu yapmakta olduğunuz işlevleri çalışır gösteren bir istatistiksel profil oluşturma yöntemidir. Örnekleme uygulamanızı hızlandırmak alanları aramaya başlamak için uygun bir yerdir.  
  
 Belirtilen aralıklarda **örnekleme** yöntemi uygulamanızda yürütülen işlevler hakkında bilgi toplar. Bir çalıştırmak, profil oluşturma işlemini tamamladıktan sonra **özeti** profil, görünüm verileri en etkin işlevi çağrısı ağacında gösterir adlı **etkin yolunuzda**, burada uygulamadaki işlerin çoğunu gerçekleştirilmedi. Görünümü de ayrı ayrı çoğu iş gerçekleştirdiğiniz işlevleri listeler ve örnekleme oturum belirli kesimlerinde odaklanmak için kullanabileceğiniz bir zaman çizelgesi grafik sağlar.  
  
 Varsa **örnekleme** ihtiyacınız veri vermez size yardımcı olabilecek bilgiler farklı türde diğer profil oluşturma araçları koleksiyon yöntemleri sağlar. Bu diğer yöntemler hakkında daha fazla bilgi için bkz: [nasıl yapılır: Koleksiyon yöntemleri seçme](../profiling/how-to-choose-collection-methods.md).  
  
> [!TIP]
>  Windows işlevlerini çağıran kodu profil, en güncel .pdb dosyaları sahip olduğunuzdan emin olun. Bu dosyalar olmadan rapor görünümlerini şifreli ve anlaşılması zor Windows işlev adlarını listeler. İhtiyacınız olan dosyalara sahip olduğunuzdan emin olmak nasıl hakkında daha fazla bilgi için bkz: [nasıl yapılır: başvuru Windows sembol bilgileri](../profiling/how-to-reference-windows-symbol-information.md).  
  
## <a name="create-and-run-a-performance-session"></a>Oluşturma ve Performans oturumunu çalıştırma  
 Analiz etmek için gereken verileri almak için öncelikle bir performans oturumu oluşturmanız ve oturum çalıştırın. **Performans Sihirbazı** her ikisini de yapmanızı sağlar.  
  
 Bir Windows masaüstü uygulaması veya ASP.NET uygulama profil değil, bir profil oluşturma araçları birini kullanmanız gerekir. Bkz: [Profil Araçları](../profiling/profiling-tools.md).  
  
#### <a name="to-create-and-run-a-performance-session"></a>Oluşturmak ve Performans oturumunu çalıştırmak için  
  
1.  Çözümü Visual Studio'da açın. Yapılandırması yayın olarak ayarlanmış. (Bul **çözüm yapılandırmaları** ayarlamak için araç çubuğundaki **hata ayıklama** varsayılan olarak. Şekilde değiştirin **sürüm**.)  
  
    > [!IMPORTANT]
    >  Profil Oluşturucu kullanırken, kullanmakta olduğunuz bilgisayarda yönetici değilseniz, Visual Studio Yönetici olarak çalıştırmanız gerekir. (Visual Studio uygulama simgesine sağ tıklayın ve ardından **yönetici olarak çalıştır**.  
  
2.  Üzerinde **hata ayıklama** menüsünde, select **profil oluşturucu**ve ardından **Performans Profil Oluşturucu**.  
  
3.  Denetleme **performans Sihirbazı** seçeneğini ve tıklayın **Başlat**.  
  
4.  Denetleme **CPU örnekleme (önerilir)** seçeneğini ve tıklayın **son**.  
  
5.  Uygulamanızı başlatır ve verileri toplamak profil oluşturucu başlatır.  
  
6.  Performans sorunlarını içerebilir işlevselliği uygular.  
  
7.  Genellikle yaptığınız gibi uygulamayı kapatın.  
  
     Uygulama çalıştıran tamamladıktan sonra **Özet** profil oluşturma verileri görünümünü ana Visual Studio penceresinde görüntülenir ve yeni oturum için bir simge görüntülenir **performans Gezgini** penceresi.  
  
## <a name="step-2-analyze-sampling-data"></a>2. adım: Örnekleme verileri analiz etme  
 Bir performans oturumu çalışması tamamlandığında **Özet** profil oluşturma raporu görünümünü Visual Studio ana penceresinde görünür.  
  
 Verilerinizi inceleyerek incelemeye başlamak öneririz **etkin yolunuzda** sonra en fazla çalışmayı yapan ve son olarak göre odaklanan diğer işlevleri kullanarak işlevlerin listesi **Özet zaman çizelgesi** . Profil oluşturma önerileri ve Uyarılar ile de görüntüleyebilirsiniz **hata listesi** penceresi.  
  
 Örnekleme yöntemi, gereksinim duyduğunuz bilgileri sağlamayabilir olduğunu unutmayın. Örneğin, yalnızca uygulamanın kullanıcı modunda kod çalıştırırken örnekleri toplanır. Bu nedenle, girdi ve çıktı işlemleri gibi bazı işlevleri örnekleme tarafından sayılmaz. Profil oluşturma araçları, önemli verilerin odaklanmaya etkinleştirebilirsiniz birkaç koleksiyon yöntemleri sağlar. Diğer yöntemler hakkında daha fazla bilgi için bkz: [nasıl yapılır: Koleksiyon yöntemleri seçme](../profiling/how-to-choose-collection-methods.md).  
  
 Şekil numaralı her alanda bir yordamda adım ile ilgilidir.  
  
 ![Örnekleme için Özet rapor görünümü](../profiling/media/summary_sampling.png "Summary_Sampling")  
  
#### <a name="to-analyze-sampling-data"></a>Örnekleme verileri çözümlemek için  
  
1.  İçinde **Özet** görünümü **etkin yolunuzda** yüksek dahil örnekleri ile uygulamanızın çağrı ağacı dalı gösterir. Toplanan veriler, en etkin yürütme yolu budur. Çağrı ağacı üreten algoritma iyileştirilebilir yüksek dahil değerler belirtebilirsiniz. Kodunuzdaki yolu en düşük işlevi bulun. Yolun ayrıca sistem işlevleri veya İşlevler dış modülleri ekleyebilirsiniz dikkat edin.  
  
     ![Profil Oluşturucu etkin yolunuzda](../profiling/media/profiler_hotpath.png "Profiler_HotPath")  
  
    1.  **Kapsayıcı örnekleri** ne kadar iş işlevi ve tarafından çağrılan tüm işlevler tarafından yapılmadı gösterir. Yüksek dahil sayıları genel en pahalı İşlevler seçeneğine gidin.  
  
    2.  **Özel örnekleri** ne kadar iş tarafından adlı işlevler tarafından çalışmanın hariç işlev gövdesi kod tarafından yapılmadı gösterir. Yüksek özel sayıları işlev içinde performans sorunu gösteriyor olabilir.  
  
2.  Görüntülenecek işlevi adına tıklayın **işlev ayrıntıları** profil oluşturma verileri görünümü. **İşlev ayrıntıları** görünüm bu işlevi çağrıldığında tüm işlevleri ve seçili işlev tarafından çağrılan tüm işlevleri gösteren seçili işlevi için profil oluşturma verileri grafik bir görünümünü sunar.  
  
    -   Çağıran ve çağrılan işlevleri bloklarının boyutunu işlevleri adlı veya adı veriliyordu göreli sıklığı temsil eder.  
  
    -   Bir arama adını tıklatın veya işlev Ayrıntıları görünümü seçili işlevinin yapmak için işlevini çağırdı.  
  
    -   Alt bölmesindeki **işlev ayrıntıları** windows, işlev kodunu görüntüler. Kodu inceleyin ve performansı iyileştirmek için bir fırsat bulmak, Visual Studio düzenleyicisinde dosyayı açmak için kaynak dosya adını tıklatın.  
  
3.  Çözümleme devam etmek için dönmek **Özet** seçerek Görünüm **Özet** Görünüm açılan listesinden. İşlevlerde inceleyin **en tek tek iş yapan işlevlerin**. Bu liste, en yüksek özel örnekleri işlevleriyle görüntüler. Bu işlevlerin işlev gövdesi kodunda önemli iş gerçekleştirilen ve onu en iyi duruma getirme olabilir. Daha fazla belirli bir işlev çözümlemek için görüntülenecek işlevi adına tıklayın **işlev ayrıntıları** görünümü.  
  
     ![En fazla çalışmayı yapan işlevlerin listesi](../profiling/media/functions_mostwork.png "Functions_MostWork")  
  
     Araştırmanızı çalıştırmak profil oluşturma devam etmek için profil oluşturma verileri bir parçasını zaman çizelgesinde kullanarak yeniden Çözümle **Özet** size göstermek için Görünüm **etkin yolunuzda** ve **işlevleri En fazla tek tek çalışmayı yapan** Seçili segmentin dışında. Örneğin, daha küçük bir en yüksek çizelgesinde odaklanan pahalı çağrısı ağaçları ve analiz çalıştırmak tüm profil, gösterilmeyen işlevleri ortaya çıkarabilir.  
  
     Bir segment yeniden Çözümle için Özet zaman çizelgesi kutu içinde bir segmenti seçin ve ardından **seçime göre filtre**.  
  
     ![Performans Özeti Görünümü zaman çizelgesi](../profiling/media/performancesummary.png "PerformanceSummary")  
  
4.  Profil Oluşturucu ayrıca profil Çalıştır artırmak yöntemler önerir ve olası performans sorunlarını tanımlamak için bir kural kümesi kullanır. Bir sorun bulunursa, bir uyarı görüntülenir **hata listesi** penceresi. Açmak için **hata listesi** penceresi, **Görünüm** menüsünü tıklatın **hata listesi**.  
  
    -   Bir uyarı oluşturuldu işlevi görmek için **işlev ayrıntıları** görüntülemek için uyarıyı çift tıklatın.  
  
    -   Uyarı hakkında ayrıntılı bilgi görüntülemek için hata sağ tıklayın ve ardından **hata yardımını göster**  
  
## <a name="step-3-revise-code-and-rerun-a-session"></a>3. adım: kod gözden geçirme ve bir oturumu yeniden çalıştırın  
 Bul ve bir veya daha fazla işlevler en iyi duruma getirme sonra profil Çalıştır yineleyin ve değişikliklerinizi uygulamanızın performansını yapmış olduğunuz farkı görmek için veri karşılaştırın.  
  
#### <a name="to-revise-code-and-rerun-the-profiler"></a>Kod gözden geçirme ve profil oluşturucu yeniden çalıştırın  
  
1.  Kodunuzu değiştirin.  
  
2.  Açmak için **performans Gezgini**, **hata ayıklama** menüsünü tıklatın **profil oluşturucu**, ardından **performans Gezgini** ve ardından**Göster performans Gezgini**.  
  
3.  İçinde **performans Gezgini**, yeniden çalıştırın ve ardından istediğiniz oturumu sağ tıklatın **profil oluşturma ile başlatın.**  
  
4.  Oturumu yeniden sonra başka bir veri dosyası eklenen **raporları** oturumu için klasör **performans Gezgini**. Her iki özgün seçin ve yeni profil oluşturma verilerini, seçime sağ tıklayın ve ardından **karşılaştırmak performans raporları**.  
  
     Karşılaştırma sonuçlarını görüntüleyen yeni bir rapor penceresi açılır. Karşılaştırma Görünümü kullanma hakkında daha fazla bilgi için bkz: [nasıl yapılır: performans veri dosyalarını karşılaştırma](../profiling/how-to-compare-performance-data-files.md).
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Performans Gezgini](../profiling/performance-explorer.md)   
 [Başlarken](../profiling/getting-started-with-performance-tools.md)   
 [Genel Bakışlar](../profiling/overviews-performance-tools.md)  
 [Visual Studio'da profil oluşturma](../profiling/index.md)  
 [Profil oluşturma özelliği turu](../profiling/profiling-feature-tour.md)
