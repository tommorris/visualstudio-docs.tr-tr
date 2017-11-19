---
title: "UWP uygulamalarında JavaScript bellek kullanımını çözümleme | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- dominators, memory analyzer (JavaScript)
- memory leaks (JavaScript)
- heap memory, JavaScript
- leaks, memory (JavaScript)
- snapshots, memory analyzer (JavaScript)
- JavaScript Memory Analyzer
- analyzing memory, JavaScript
- memory analyzer, JavaScript
ms.assetid: 78f8532b-7b4e-4b50-b8b7-68ca0926dd4e
caps.latest.revision: "49"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e52bef93735efc1ec5e43230ba46c7aa90cb67bc
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="analyze-javascript-memory-usage-in-uwp-apps"></a>UWP uygulamalarında JavaScript bellek kullanımını çözümleme
JavaScript bellek Çözümleyicisi bellek kullanımını anlamak ve JavaScript kullanan Windows için oluşturulmuştur, UWP uygulamaları içinde bellek sızıntıları bulmanıza yardımcı olmak için Visual Studio'da kullanılabilir. Desteklenen uygulamaların uygulamaları Evrensel Windows uygulamaları için içerir.
  
 JavaScript bellek Çözümleyicisi bu için yapabilecekleriniz:  
  
-   Hızlı bellek kullanım sorunları uygulamanızda en ilgili veriler vurgulayarak bulmanıza yardımcı.  
  
     İki anlık görüntüsü arasındaki farkları gösteren ve daha ayrıntılı görünümler için bağlantılar sağlar anlık görüntü özetleri içinde bu verileri alın.  
  
-   Önde gelenler, türleri ve kökleri sorunlarını gidermeye yardımcı olmak için görünümleri sağlar.  
  
-   JavaScript yığını veri tıklatılabilir olmayan bilgisini azaltın.  
  
     Uygulama kodunuzda doğrudan oluşturulmayacak nesneleri otomatik olarak filtrelenir. Ayrıca veri nesne adına göre filtre uygulayabilirsiniz.  
  
 Çalışma uygulama bellek sızıntısına tanımlama işleminde size yol gösterir bir öğretici için bkz [izlenecek yol: Bellek sızıntısını (JavaScript) bulmak](../profiling/walkthrough-find-a-memory-leak-javascript.md).  
  
 Bu konuda:  
  
 [JavaScript bellek Çözümleyicisi çalıştırma](#Run)   
 [Bellek kullanımını denetleyin](#Check)   
 [Bellek sızıntısı yalıtma](#Isolate)   
 [Dinamik bellek kullanım özetini görüntüle](#LiveMemory)   
 [Bir anlık görüntü özeti görüntülemek](#SnapshotSummary)   
 [Anlık görüntü ayrıntıları görüntüle](#SnapshotDetails)   
 [Bir anlık görüntü fark görüntüleyin](#SnapshotDiff)   
 [DOMINATOR tarafından nesneleri görüntüle](#FoldObjects)   
 [Veri tanımlayıcısına göre filtrele](#Filter)   
 [Nesne ağacında bir nesne bulunamadı](#ShowInRootsView)   
 [Paylaşılan Görünüm nesne başvuruları](#References)   
 [Yerleşik nesneleri göster](#BuiltInValues)   
 [Tanılama oturumu dosyaları kaydetme](#Save)   
 [Kaynak kodu ile bellek kullanım verileri ilişkilendirme](#JSConsoleCommands)   
 [Bellek sorunları tanımlamak için ipuçları](#Tips)  
  
##  <a name="Run"></a>JavaScript bellek Çözümleyicisi çalıştırma  
 Visual Studio'da Aç veya yüklü çalışma UWP uygulaması çalıştıran bir bilgisayarda olduğunda bellek Çözümleyicisi'ni kullanabilirsiniz [!INCLUDE[win8](../debugger/includes/win8_md.md)] veya sonraki bir sürümü.  
  
#### <a name="to-run-the-memory-analyzer"></a>Bellek Çözümleyicisi'ni çalıştırmak için  
  
1.  Visual Studio'yu açın.  
  
2.  Uygulama Visual Studio'dan içinde çalıştırıyorsanız **hata ayıklamayı Başlat** listesini **standart** araç, projeniz için hata ayıklama hedefi seçin: bir ya da Windows Phone öykünücüsü veya bir UWP uygulaması  **Yerel makine**, **Simulator**, veya **uzak makine**.  
  
     Bu seçenekler hakkında daha fazla bilgi için bkz: [Visual Studio'dan uygulamaları çalıştırma](../debugger/run-store-apps-from-visual-studio.md).  
  
3.  Menü çubuğunda seçin **hata ayıklama**, **Performans Profil Oluşturucu...** .  
  
     Varsayılan olarak, geçerli başlangıç projesi analiz edilir. Çözümleme hedefi değiştirmek istiyorsanız seçin **değiştirmek hedef**.  
  
     ![Değişiklik çözümleme hedef](../profiling/media/js_tools_target.png "JS_Tools_Target")  
  
     Çözümleme hedefi için aşağıdaki seçenekler kullanılabilir:  
  
    -   **Başlangıç projesi**. Geçerli başlangıç projesi analiz eder. Uzak makinede uygulama çalıştırıyorsanız, bu seçenek varsayılandır seçmeniz gerekir.  
  
    -   **Uygulama çalışırken**. Çalışan uygulamalar listesinden bir UWP uygulaması seçmenizi sağlar. Uzak makinede uygulamanızı çalıştırırken bu seçeneği kullanamazsınız.  
  
         Kaynak kodu erişimi olmadığında, bilgisayarınızda çalışan uygulamalar bellek kullanımını analiz etmek için bu seçeneği kullanın.  
  
    -   **Uygulamanın yüklü**. Analiz etmek istediğiniz yüklü olan bir UWP uygulaması seçmenizi sağlar. Uzak makinede uygulamanızı çalıştırırken bu seçeneği kullanamazsınız.  
  
         Kaynak kodu erişiminiz yoksa, bilgisayarınızda yüklü uygulamalar bellek kullanımını analiz etmek için bu seçeneği kullanın. Yalnızca kendi uygulama geliştirme dışında herhangi bir uygulama bellek kullanımını çözümlemek istediğinizde bu seçeneği de yararlı olabilir.  
  
4.  Gelen **kullanılabilen Araçlar**seçin **JavaScript belleği** onay kutusunu işaretleyin ve ardından **Başlat**.  
  
5.  Bellek Çözümleyicisi'ni başlattığınızda, bir kullanıcı hesabı denetimi penceresi Visual Studio ETW Collector.exe çalıştırma izni isteyebilir. Seçin **Evet**.  
  
     Uygulamayla ilgili bellek kullanım senaryoları sınamak ve bellek grafik görüntülemek için aşağıdaki bölümlerde açıklandığı gibi etkileşimde bulunur.  
  
6.  Alt + Sekme tuşlarına basarak Visual Studio'ya geçin.  
  
7.  Bellek Çözümleyicisi toplama verileri görüntülemek için seçin **yığın anlık görüntüsünü Al**. Bkz: [bir anlık görüntü özeti görüntülemek](#SnapshotSummary) bu konuda daha sonra.  
  
##  <a name="Check"></a>Bellek kullanımını denetleyin  
 JavaScript bellek Çözümleyicisi'nde farklı görünümleri kullanarak bellek sızıntılarını tanımlamak deneyebilirsiniz. Uygulama bellek sızıntısına yol açıyor zaten şüpheleniyorsanız bakın [bellek sızıntısı yalıtmak](#Isolate) önerilen bir iş akışı için.  
  
 Bellek sızıntıları bir uygulamada belirlemenize yardımcı olması için aşağıdaki görünümleri kullanın:  
  
-   [Dinamik bellek kullanım özeti görüntülemek](#LiveMemory). Bellek kullanım grafiği, bellek kullanımı ani artışları veya sürekli olarak belirli eylemler sonuçları bellek kullanımı artırmayı aramak için kullanın. Yığın anlık görüntülerini almak için dinamik bellek kullanımı özet görünümünü kullanın. Anlık görüntüler, bellek kullanım grafiği bir koleksiyon olarak görünür.  
  
    > [!TIP]
    >  Bir anlık görüntüsünü bellek kullanımında ani görürsünüz. Anlık görüntü özetleri İyileştirilecek daha doğru bir göstergesi için kullanın.  
  
-   [Bir anlık görüntü özeti görüntülemek](#SnapshotSummary). Sırasında veya sonrasında profil oluşturma oturumu belleği, anlık görüntü özet bilgileri görüntüleyebilirsiniz. Anlık görüntü ayrıntıları ve anlık görüntü fark görünümlere bağlamak için anlık görüntü özetleri kullanın.  
  
    > [!TIP]
    >  Genellikle, anlık görüntü fark görünümleri bellek sızıntılarını en yararlı bilgiler sağlar.  
  
-   [Anlık görüntü ayrıntıları görüntüleyin](#SnapshotDetails). Tek bir anlık görüntü için ayrıntılı bellek kullanım verilerini gösterir.  
  
-   [Bir anlık görüntü fark görüntülemek](#SnapshotDiff). Anlık görüntüler arasındaki fark değerleri gösterir. Bu görünümler nesne farklılıkları boyutu ve nesne sayısını gösterir.  
  
##  <a name="Isolate"></a>Bellek sızıntısı yalıtma  
 Bu adımlar, JavaScript bellek Çözümleyicisi daha verimli şekilde kullanmanıza yardımcı olabilecek bir iş akışı sağlar. Bu adımları uygulamanız bellek sızıntısı olduğundan şüpheleniyorsanız yararlı olabilir. Çalışma uygulama bellek sızıntısına tanımlama işleminde size yol gösterir bir öğretici için bkz [izlenecek yol: Bellek sızıntısını (JavaScript) bulmak](../profiling/walkthrough-find-a-memory-leak-javascript.md).  
  
1.  Uygulamanızı Visual Studio'da açın.  
  
2.  JavaScript bellek Çözümleyicisi'ni çalıştırın. Daha fazla bilgi için bkz: [JavaScript bellek Çözümleyicisi'ni çalıştırmak](#Run).  
  
3.  Uygulamanızı test etmek istediğiniz senaryosuyla çalıştırın. Örneğin, senaryo belirli bir sayfa yüklendiğinde veya uygulama başlatıldığında büyük DOM mutation gerektirebilir.  
  
4.  Senaryo 1-4 ek kez yineler.  
  
    > [!TIP]
    >  Birkaç kez test senaryosu tekrarlayarak başlatma iş sonuçları dışında filtrelenebilir emin olunmasına yardımcı olabilirsiniz.  
  
5.  Visual Studio'ya (Alt + Sekme tuşuna basın) geçin.  
  
6.  Seçerek bir taban çizgisi yığın anlık görüntüsünü **yığın anlık görüntüsünü Al**.  
  
     Aşağıdaki çizimde, bir taban çizgisi anlık görüntüsü bir örneği gösterir.  
  
     ![Taban çizgisi anlık görüntü](../profiling/media/js_mem_leak_workflow_baseline.png "JS_Mem_Leak_Workflow_Baseline")  
  
    > [!TIP]
    >  Anlık görüntü zamanlama üzerinde daha kesin denetim için kullandığınız [kaynak kodu ile bellek kullanım verilerini ilişkilendirmek](#JSConsoleCommands) kodunuzda komutu.  
  
7.  Uygulamanıza geçin ve (yalnızca bir kez yineleyin) Test senaryosu yineleyin.  
  
8.  Visual Studio geçin ve ikinci bir anlık görüntü alın.  
  
9. Uygulamanıza geçin ve (yalnızca bir kez yineleyin) Test senaryosu yineleyin.  
  
10. Visual Studio geçin ve üçüncü bir anlık görüntü alın.  
  
     Aşağıdaki çizimde, ikinci ve üçüncü bir anlık görüntüsü bir örneği gösterir.  
  
     ![İkinci ve üçüncü anlık görüntü](../profiling/media/js_mem_leak_workflow.png "JS_Mem_Leak_Workflow")  
  
     Bu iş akışındaki temel, ikinci ve üçüncü anlık görüntü yararlanarak, daha kolay bellek sızıntıları ile ilişkili olmayan değişikliklere filtre uygulayabilirsiniz. Örneğin, üstbilgiler ve altbilgiler bazı değişiklikler bellek kullanımında oluşturur ama bellek sızıntıları ilgisiz olabilir bir sayfada güncelleştirme gibi beklenen değişiklikler olabilir.  
  
11. Üçüncü anlık görüntüden bağlantı fark görünümlerden birini seçin:  
  
    -   Fark öbek boyutu (öbek boyutunu altındaki sol bağlantı). Bağlantı metni geçerli anlık görüntünün yığın boyutu ve önceki anlık görüntüsünü yığın boyutu arasındaki farkı gösterir.  
  
    -   Fark nesne sayısı (sağ bağlantı nesne sayısını altında). Bağlantı metni iki değerleri gösterir (örneğin, +1858 /-1765): ilk değer önceki anlık itibaren eklenen yeni nesneler sayısıdır ve ikinci değer önceki bir anlık beri kaldırılan nesnelerinin sayısı.  
  
     Bu bağlantılar türleri fark anlık görüntü Ayrıntılar görünümünü elde tutulmuş boyutu veya nesne sayısı, bağlı olarak hangi bağlantı açtığınız sıralanmış yığında açın.  
  
12. Aşağıdakilerden birini seçin **kapsam** filtre bellek kullanım sorunları belirlemenize yardımcı olması için seçenekleri:  
  
    -   **Nesneleri kalan anlık görüntü # 2'den**.  
  
    -   **Anlık görüntü #2 ile #3 arasında eklenen nesneler**  
  
    > [!TIP]
    >  Bellek sızıntıları araştırmak için önceki anlık görüntüden kalan nesnelerin filtrelenmiş görünümünü kullanın. Örneğin, fark nesne sayısını +205 ise /-195, bu görünüm kalan 10 nesneleri gösterilir ve bu bellek sızıntıları olası adaylar.  
  
     Aşağıdaki çizimde anlık görüntü # 2'den kalan nesnelerin fark bir görünümünü gösterir.  
  
     ![Fark görünümü türleri gösteren anlık görüntü](../profiling/media/js_mem_snapshot_diff.png "JS_Mem_Snapshot_Diff")  
  
     Önceki çizimde, iki nesne önceki anlık görüntüden kalmış olduğunu bakın. Bu belirli uygulamanız için beklenen bir davranış olup olmadığını araştırın. Aksi durumda, bir bellek sızıntısı gösterebilir.  
  
13. Diff görünümlerdeki nesneleri bunları çöpünün toplanma engeller, bir genel nesne burada olsunlar görmek için bir nesne için kısayol menüsünü açın ve ardından **Göster kökleri görünümünde**. Tek bir nesne (veya bazı nesneler) tarafından başvurulduğundan çok sayıda nesneleri bellekte kalması genel nesne kökü.  
  
14. Daha fazla bellek sızıntısı gerçekleştiğini dönemi yalıtmak ve üç anlık görüntü yeniden yanıtlamak kalan nesnelerin görünümünü çok fazla nesne varsa deneyin. Daha fazla bellek sızıntısı ayırmak için kullanma [kaynak kodu ile bellek kullanım verilerini ilişkilendirmek](#JSConsoleCommands), [kaynak kodu ile bellek kullanım verilerini ilişkilendirmek](#JSConsoleCommands)ve diğer bellek Çözümleyicisi'nde kullanılabilir olan bellek kullanım verileri.  
  
##  <a name="LiveMemory"></a>Dinamik bellek kullanım özetini görüntüle  
 Dinamik bellek kullanımı Özet görünümü bellek kullanım grafiği çalışan uygulamanın ve tüm anlık görüntü Özet kutucukları koleksiyonu sağlar. Bu görünümde, Özet bilgileri analiz etme ve diğer görünümlere gezinme anlık görüntü alma gibi temel görevleri gerçekleştirebilir. Veri toplamayı durdurduğunuzda, bellek grafik kaybolduktan ve yalnızca gördüğünüz [bir anlık görüntü özeti görüntülemek](#SnapshotSummary) görünümü.  
  
 Bellek grafik özel bayt sayısı, yerel bellek ve JavaScript yığını içeren uygulamanın işlem bellek canlı bir görünümünü gösterir. Bellek grafik işlem bellek kaydırılabilir görülmektedir. İşte bu şekilde görünür:  
  
 ![JavaScript bellek Çözümleyicisi bellek grafik](../profiling/media/js_mem_memory_graph.png "JS_Mem_Memory_Graph")  
  
 Uygulama kodunuz eklediğiniz kullanıcı işaretlerini (bkz [kaynak kodu ile bellek kullanım verilerini ilişkilendirmek](#JSConsoleCommands)), bu bölüm kodunun ulaşıldığında göstermek için bellek kullanım grafiğinde bir ters üçgen.  
  
 Bazı bellek grafikte gösterildiği bellek JavaScript çalışma zamanı tarafından ayrılır. Bu bellek kullanımı uygulamanızda denetleyemezsiniz. Grafikte gösterildiği bellek kullanımı ilk anlık görüntünüz alırken ve ek her anlık görüntü için en düşük düzeyde çıkarır.  
  
##  <a name="SnapshotSummary"></a>Bir anlık görüntü özeti görüntülemek  
 Bir anlık görüntüsünü uygulamanızın bellek kullanımı geçerli durumunu almak için seçin **yığın anlık görüntüsünü Al** bellek grafikten. (Uygulama çalışırken) hem de dinamik bellek kullanımında Özet görünür bir anlık görüntü Özet kutucuğuna ve anlık görüntü özeti (uygulama durdurulduğunda), JavaScript yığını ve daha ayrıntılı bilgi için bağlantılar hakkında bilgi sağlar. İki veya daha fazla anlık görüntüsünü alırsanız, bir anlık görüntü verilerini, önceki anlık görüntünün karşılaştırma ek bilgi sağlar.  
  
> [!NOTE]
>  JavaScript bellek Çözümleyicisi her anlık görüntü önce çöp toplama zorlar. Bu, daha tutarlı sonuçlar çalıştırmaları arasında sağlamaya yardımcı olur.  
  
 Aşağıda, birden çok anlık görüntü alırken bir anlık görüntü Özet bir örnek verilmiştir.  
  
 ![Anlık görüntü Özet](../profiling/media/js_mem_snapshot_summary.png "JS_Mem_Snapshot_Summary")  
  
 Anlık görüntü özeti içerir:  
  
-   Anlık görüntü başlık ve zaman damgası.  
  
-   Olası sorunlar sayısı (mavi bilgisi simgesiyle belirtilir). DOM iliştirilmemiş düğümleri gibi olası bellek sorunları varsa, bu sayı tanımlar Olası sorunları vurgulamak için sorun türüne göre sıralanmış anlık görüntü türleri görünümünü sayısı bağlantılar. Bir araç ipucunu sorunun açıklamasını gösterir.  
  
-   Yığın boyutu. Bu sayı DOM öğeleri ve JavaScript yığını için JavaScript çalışma zamanı altyapısı ekler nesneleri içerir. Anlık Görüntü türleri görünümünü yığın boyutu bağlantılar.  
  
-   Fark yığın boyutu. Bu değer, geçerli anlık görüntünün yığın boyutu ve önceki anlık görüntüsünü yığın boyutu arasındaki farkı gösterir. Bellek azaltma ise değer kırmızı bir bellek artış ise ok yukarı veya aşağı ok bir yeşil tarafından izlenir. Yığın boyutu anlık görüntüler arasında değişmediğinden, metni görürsünüz **hiçbir değişiklik** yerine bir sayı. İlk anlık görüntü için metni görürsünüz **temel**. Anlık görüntü diff türleri görünümünü fark yığın boyutu bağlantılar  
  
-   Nesne sayısı. Bu sayaç yalnızca uygulama ve JavaScript çalışma zamanı tarafından oluşturulan yerleşik nesneler çıkış filtreleri oluşturulan nesneleri gösterir. Anlık görüntü ayrıntıları türleri görünümünü nesne sayısı bağlantılar.  
  
-   Fark nesne sayısı. Bu iki değer gösterir: ilk değer önceki anlık itibaren; eklenen yeni nesneler sayısıdır. ve ikinci değer önceki bir anlık beri kaldırılan nesne sayısı. Örneğin, çizimde 1,859 nesneleri eklendi ve 1,733 nesneleri anlık görüntü # 1'den beri kaldırılan gösterir. Bunu indirildi varsa bu bilgileri kırmızı toplam nesne sayısı arttıkça, OK veya yeşil aşağı ok tarafından izlenir. Nesne sayısını değişmediğinden, metni görürsünüz **hiçbir değişiklik** yerine bir sayı. İlk anlık görüntü için metni görürsünüz **temel**. Anlık görüntü diff türleri görünümünü fark nesne sayısı bağlantılar  
  
-   Anlık görüntü alınırken zaman ekranının ekran görüntüsü.  
  
##  <a name="SnapshotDetails"></a>Anlık görüntü ayrıntıları görüntüle  
 Anlık görüntü ayrıntıları görünümlerinde her anlık görüntü için bellek kullanımı hakkında ayrıntılı bilgileri görüntüleyebilirsiniz.  
  
 Anlık görüntü Özet görünümünden anlık görüntü ayrıntılarını görmek için bir bağlantıyı seçin. Örneğin, yığın boyutu bağlantı türleri görünüm ayrıntılarla varsayılan olarak açık anlık görüntü açar.  
  
 Bu örnekte türleri görünüm tutulan boyutuna göre sıralanmış bellek kullanım verileri ile bir anlık görüntü ayrıntılı olarak gösterilmiştir.  
  
 ![Anlık görüntü ayrıntılarına gösteren olası sorunları](../profiling/media/js_mem_snapshot_details.png "JS_Mem_Snapshot_Details")  
  
 Anlık görüntü Ayrıntıları görünümünde araç çubuğundaki bir seçeneği belirleyerek türü, kök veya DOMINATOR bellek kullanım verileri gözden geçirebilirsiniz:  
  
-   **Türleri**. Nesne türüne göre gruplandırılmış yığında nesneleri örnek sayısı ve toplam boyutunu gösterir. Varsayılan olarak, bu örnek sayısına göre sıralanır.  
  
    > [!TIP]
    >  Genellikle, fark görünümler türleri nesne yığında bellek sızıntısı tanımlamak için en kullanışlı görünümlerdir; Bu görünüm sağlayan bir **kapsam** nesneler üzerinde sol tanımlamaya yardımcı olmak için filtre.  
  
-   **Kökler**. Alt öğe başvurusu kök nesnelerde nesnelerden hiyerarşik bir görünümü gösterir. Varsayılan olarak, alt düğümler ile büyük üst tutulan boyutu sütuna göre sıralanır.  
  
-   **Önde gelenler**. Diğer nesneler özel başvuran yığında nesnelerin bir listesini gösterir. Önde gelenler tutulan boyutuna göre sıralanır.  
  
    > [!TIP]
    >  Bir DOMINATOR bellekten kaldırdığınızda, nesne korur tüm belleği geri. Tam nesne başvuru zinciri araştırmak için birkaç uygulama için tutulan bellek boyutları açıklamak önde gelenler görünüm yardımcı olabilir.  
  
 Tüm üç görünüm benzer değer türleri gösterilmektedir:  
  
-   **Tanımlayıcıları**. En iyi nesneyi tanımlayan adı. Örneğin, bir kullanılırsa, HTML öğeleri için anlık görüntü ayrıntılarını kimliği öznitelik değeri gösterir.  
  
-   **Türü**. Nesne türü (örneğin, HTML bağlantı öğesine veya div öğesinin).  
  
-   **Boyutu**. Nesnenin boyutu, başvurulan tüm nesnelerin boyutunu dahil edilmez.  
  
-   **Boyutu korunur**. Nesne boyutu ek olarak diğer üst sahip tüm alt nesneleri boyutu. Pratik amacıyla, bu nesne silerseniz belirli bellek miktarını geri kazanmak için nesne tarafından korunduğunu bellek miktarıdır.  
  
-   **Count**. Nesne örneği sayısı. Bu değer yalnızca türleri görünümünde görüntülenir.  
  
##  <a name="SnapshotDiff"></a>Bir anlık görüntü fark görüntüleyin  
 JavaScript bellek Çözümleyicisi'nde, önceki anlık anlık görüntü fark görünümlerinde karşı bir anlık görüntü karşılaştırabilirsiniz.  
  
 Anlık görüntü Özet görünümünde iki veya daha fazla anlık görüntüleri kazandıktan sonra fark yığın boyutu veya değişiklikleri nesne sayısı bağlantıları seçerek fark anlık görüntü ayrıntıları görüntüleyebilirsiniz.  
  
 Türleri, kökleri ve önde gelenler hakkında fark bilgilerini görüntüleyebilirsiniz. Anlık görüntü fark yığın iki anlık görüntülerin arasında eklenme nesneleri gibi bilgileri gösterir.  
  
 Bu çizimde türleri görünümü bir anlık görüntü diff gösterir.  
  
 ![Fark görünümü türleri gösteren anlık görüntü](../profiling/media/js_mem_snapshot_diff.png "JS_Mem_Snapshot_Diff")  
  
 Anlık görüntü fark penceresinde önde gelenler, türler ve kökleri de aynı görünümlerdir [anlık görüntü ayrıntıları görüntüleyin](#SnapshotDetails) penceresi. Anlık görüntü fark anlık görüntü ayrıntılarla bu ek değerler olarak aynı bilgileri gösterir:  
  
-   **Boyutu fark**. Geçerli anlık görüntüdeki nesnenin boyutu ve boyutuna arasındaki farkı boyutunu dahil değil önceki anlık görüntüdeki nesnelerine başvuru.  
  
-   **Boyutu fark korunur**. Önceki anlık görüntüsünü o anki anlık görüntüsü nesnesinin tutulan boyutu ile tutulan boyutu arasındaki fark. Elde tutulmuş boyutu nesne boyutu ek boyutu diğer üst sahip tüm alt nesneleri içerir. Pratik amaçlar için tutulan nesne silerseniz belirli bellek miktarını geri kazanmak için nesne tarafından korunduğunu bellek miktarını boyutudur.  
  
 Anlık görüntüler arasındaki fark bilgisi filtre uygulamak için aşağıdakilerden birini seçin **kapsam** fark görünümleri üstündeki filtreleri.  
  
-   **Gelen nesneleri kalan anlık görüntü #\<numarası >**. Bu filtre yığına eklenebilir ve temel anlık görüntü ve önceki anlık görüntüsünü karşılaştırıldığında yığın kaldırılmasını nesneler arasındaki fark gösterir. Örneğin, anlık görüntü Özet +205 gösteriyorsa /-195 nesne sayısı bu filtre gösterir, on nesneleri eklendi ancak kaldırılmaz.  
  
    > [!TIP]
    >  Bu filtre en yararlı bilgileri göstermek için açıklanan adımları izleyin [bellek sızıntısı yalıtmak](#Isolate).  
  
-   **Arasında eklenen nesneler anlık görüntü #\<numarası > ve #\<numarası >**. Bu filtre önceki anlık görüntüden yığına eklenen tüm nesneleri gösterir.  
  
-   **Anlık görüntü içindeki tüm nesneler #\<numarası >**. Bu filtre ayarı öbek nesneleri filtrelemenize değil.  
  
 Geçerli eşleşmeyen nesne başvuruları göstermek için **kapsam** filtresi, select **eşleşmeyen başvuruları göster** ayarlar listesinde ![ayarları açılan &#45; bellek Çözümleyicisi listesinde aşağı ] (../profiling/media/js_mem_settings.png "JS_Mem_Settings") bölmesi sağ üst köşesindeki. Bu ayarı etkinleştirirseniz, eşleşmeyen başvuruları gri metinle görüntülenir.  
  
> [!TIP]
>  ' Ndaki adımları izlemenizi öneririz [bellek sızıntısı yalıtmak](#Isolate) ve kalan nesneler kullanma **kapsam** bellek sızıntısına yol nesneleri tanımlamaya yardımcı olmak için filtre.  
  
##  <a name="FoldObjects"></a>DOMINATOR tarafından nesneleri görüntüle  
 Türleri ve önde gelenler görünümlerinde (önde gelenler sekmesindeki varsayılan görünüm budur) kendi önde gelenler içine Katlanmış nesneleri görüntülemek seçebilirsiniz. Bu görünüm seçili olduğunda, yalnızca önde gelenler nesneleri en üst düzey görünümünde gösterilir. (Genel olmayan nesneler alt öğeleri olan nesneler üst düzey görünümünden gizlenir.) Bazı uygulamalar için bu veri gürültü azaltarak bellek sızıntısı hangi nesnelerin neden olan açıklık getirebilir.  
  
 Nesnelerin görünümünü DOMINATOR tarafından geçiş için tercih **nesneleri tarafından DOMINATOR Katlama** düğmesi. ![Kendi önde gelenler nesneleri Katlama](../profiling/media/js_mem_fold_objects.png "JS_Mem_Fold_Objects")  
  
 Önde gelenler hakkında daha fazla bilgi için bkz: [anlık görüntü ayrıntıları görüntüleyin](#SnapshotDetails).  
  
##  <a name="Filter"></a>Veri tanımlayıcısına göre filtrele  
 Önde gelenler ve türleri görünümlerinde belirli kimlikleri için arama yaparak veri çıkış filtreleyebilirsiniz. Bir tanımlayıcı için arama yapmak için yalnızca adını yazın **tanımlayıcısı filtre** metin kutusunda sağ üst. Yazmaya başladığınızda, yazılan karakterleri içermeyen tanımlayıcıları filtrelenir.  
  
 Her görünüm kendi filtre sahiptir, bu nedenle başka bir görünüme geçiş yaptığınızda filtre korunur değil.  
  
##  <a name="ShowInRootsView"></a>Nesne ağacında bir nesne bulunamadı  
 Belirli bir nesnesi için ilişki türleri ve önde gelenler görünümlerinde görebilirsiniz `Global` nesnesi. Nesneleri kökü için `Global` nesne atık olarak toplanmış olmayacak. Aracılığıyla aramadan bilinen bir nesneyi kökleri görünümünde kolayca bulabilirsiniz `Global` nesne ağacı. Bunu yapmak için önde gelenler içinde bir nesne için kısayol menüsünü açın veya Görünüm yazın ve ardından **Göster kökleri görünümünde**.  
  
##  <a name="References"></a>Paylaşılan Görünüm nesne başvuruları  
 Türleri ve önde gelenler görünümlerde, alt bölmedeki paylaşılan başvuruları görüntüler bir nesne başvuruları listesi içerir. Üst bölmede bir nesne seçtiğinizde, bu nesneye işaret tüm nesneleri nesne başvuruları listesi görüntüler.  
  
> [!NOTE]
>  Döngüsel başvuru bir yıldız işareti (*) ve bilgi araç ipucu ile gösterilir ve genişletilemez. Aksi takdirde, bunlar başvuru ağaca taramasını ve bellek koruma nesneleri tanımlama sizden engeller.  
  
 Ek Yardım eşdeğer nesneleri tanımlamak istiyorsanız, tercih **görüntüleme nesne kimlikleri** ayarlar listesinde ![ayarları açılan &#45; bellek Çözümleyicisi listesinde aşağı](../profiling/media/js_mem_settings.png "JS_Mem_Settings ") üst bölmesi sağ üst köşesindeki. Bu seçenek nesne adları yanındaki nesne tanımlayıcıları görüntüler **tanımlayıcıları** (kimlikleri tüm görünümlerde yalnızca nesne başvuruları listesi gösterilir) listesi. Aynı Kimliğe sahip paylaşılan başvuruları nesneleridir.  
  
 Aşağıdaki çizimde gösterilen kimliklerle nesne başvuruları listesinde seçili öğe için gösterir.  
  
 ![Nesne başvuruları görüntülenen kimlikleri](../profiling/media/js_mem_shared_refs.png "JS_Mem_Shared_Refs")  
  
##  <a name="BuiltInValues"></a>Yerleşik nesneleri göster  
 Varsayılan olarak, uygulamanızı oluşturduğunuz nesneleri önde gelenler ve türleri görünümleri gösterir. Bu filtre gereksiz bilgileri inceleyin ve uygulama ile ilgili sorunlarını gidermeye yardımcı olur. Ancak, bazen uygulamanız için JavaScript çalışma zamanı oluşturduğu tüm nesneleri görüntülemek için yararlı olabilir.  
  
 Bu nesneleri görüntülemeyi seçebilir **Göster öğelerin** ayarlar listesinde ![ayarları açılan &#45; bellek Çözümleyicisi listesinde aşağı](../profiling/media/js_mem_settings.png "JS_Mem_Settings") sağ üst köşede içinde Köşe bölmesinin.  
  
##  <a name="Save"></a>Tanılama oturumu dosyaları kaydetme  
 Tanılama anlık görüntü özetler ve bunların ilişkili ayrıntıları görünümlerini .diagsession dosyaları olarak kaydedilir. **Çözüm Gezgini** tanılama oturumları klasöründe önceki tanılama oturumları görüntüler. İçinde **Çözüm Gezgini**, önceki oturum açın veya kaldırabilir veya dosyalarını yeniden adlandırın.  
  
##  <a name="JSConsoleCommands"></a>Kaynak kodu ile bellek kullanım verileri ilişkilendirme  
 Bellek sorun var. kod bölümünü yalıtmaya yardımcı olması için aşağıdaki yöntemleri kullanın:  
  
-   Sınıf adları ve kimlikleri için ayrıntıları ve değişiklik görünümleri DOM öğe arayın.  
  
-   Dize değerlerini ayrıntıları ve kaynak kodunuzu ile ilişkilendirilmiş olabilecek değişiklikleri görünümlerde arayın.  
  
-   Kullanım [nesne ağacında bir nesne bulunamadı](#ShowInRootsView) nesne ağacı yol için komutu. Bu, ilişkili kaynak kodu belirtmek için yardımcı olabilir.  
  
-   Bellek Çözümleyicisi komutları için kaynak kodu ekleyin.  
  
 Kaynak kodunuz aşağıdaki komutları kullanabilirsiniz:  
  
-   `console.takeHeapSnapshot`JavaScript bellek Çözümleyicisi'nde görünür bir yığın anlık görüntüsünü alır. Bu komut, biri [JavaScript Konsolu komutları](../debugger/javascript-console-commands.md).  
  
-   `performance.mark`Uygulama çalışırken bellek grafik Özet görünümünde Zaman Çizelgesi'nde görüntülenen kullanıcı işareti (ters üçgen) ayarlar. Bu komutu olay açıklar ve bellek grafikte bir araç ipucu olarak görüntülenen bir dize bağımsız değişkeni alır. Bu açıklama 100 karakteri aşmamalıdır.  
  
> [!TIP]
>  Kullanım `console.takeHeapSnapshot` bellek kullanım senaryoları yinelenen analiz hızlandırmak için.  
  
 Uygulamanıza ekleme ve uygulama JavaScript bellek Çözümleyicisi dışında çalıştırırsanız bu komutları bir özel durum. Bununla birlikte, komutları kullanmadan önce mevcut olup olmadığını sınayabilirsiniz. (Komutları erken oturum başlangıç aşamasında yok.) Güvenle çağırabilirsiniz olup olmadığını denetlemek için `takeHeapSnapshot`, bu kodu kullanın:  
  
```javascript  
if (console && console.takeHeapSnapshot) {  
    console.takeHeapSnapshot();  
}  
```  
  
 Güvenle çağırabilirsiniz olup olmadığını denetlemek için `performance.mark`, bu kodu kullanın:  
  
```javascript  
if (performance && performance.mark) {  
    performance.mark("message_string");  
}  
  
```  
  
 Birkaç kullanıcı işaretleri ve kendisi için şu anda seçili kullanıcı işareti için araç ipucu ile birlikte bellek grafik işte `performance.mark` dize bağımsız değişkeni "oluşturulan veri" ayarlayın:  
  
 ![Bir profil işareti kullanarak](../profiling/media/js_mem_performance_marks.png "JS_Mem_Performance_Marks")  
  
##  <a name="Tips"></a>Bellek sorunları tanımlamak için ipuçları  
  
-   Açıklanan iş akışı izleyin [bellek sızıntısı yalıtmak](#Isolate) ve **gelen nesneleri kalan anlık görüntü #\<numarası >** bellek sızıntıları için olası adaylar tanımlamak üzere bir fark görünümünde filtre.  
  
-   Kullanım [nesne ağacında bir nesne bulunamadı](#ShowInRootsView) nesneyi bellek hiyerarşi içinde nereye başvurulan görmek için. Çöp toplanan yüklenmesini önleyen genel nesne için bir nesne nasıl kökü kökleri görünümü gösterir.  
  
-   Bellek sorunun nedenini belirlemek zor olduğu durumlarda, özellikle bir nesneyi (ya da birkaç nesneleri) belirlemenize yardımcı olması için commonalities için aramak için (örneğin, önde gelenler ve türleri) çeşitli görünümleri kullanma görünen diğer nesnelerin çoğunu başvuru içerebilir Görünüm.  
  
-   Kullanıcının ortak bir nedeni bellek sorunları olan bir yeni sayfa gezinen sonra bellekte yanlışlıkla korunur nesneleri arayın. Örneğin:  
  
    -   Yanlış kullanımı [URL. CreateObjectUrl](http://msdn.microsoft.com/library/windows/apps/hh453196.aspx) işlevi bu soruna neden olabilir.  
  
    -   Bazı nesneler sağlayabilir bir `dispose` yöntemi ve öneriler için kullanın. Örneğin, çağırmalıdır `dispose` üzerinde bir [WinJS.Binding.List](http://msdn.microsoft.com/library/windows/apps/Hh700774.aspx) listenin çağırırsanız `createFiltered` yöntemi ve bir sayfadan sonra.  
  
    -   Bir veya daha fazla olay dinleyicileri kaldırmanız gerekebilir. Daha fazla bilgi için bkz: [görünüm DOM olayı dinleyicilerini](../debugger/view-dom-event-listeners.md).  
  
-   İkinci bölümü izleme [bu videoyu](http://channel9.msdn.com/Events/Build/2013/3-316) JavaScript bellek Çözümleyicisi hakkında yapı 2013 konferans gelen.  
  
-   Okuma [UWP uygulamaları bellekte yönetme](http://msdn.microsoft.com/magazine/jj651575.aspx).  
  
-   Geçici olarak sorunları yalıtmak için kod değiştirmeyi düşünebilirsiniz. Örneğin, aşağıdakileri yapabilirsiniz:  
  
    -   Bellek Çözümleyicisi için komutları kullanın `console.takeSnapshot` ve `performance.mark`. (Bkz [kaynak kodu ile bellek kullanım verilerini ilişkilendirmek](#JSConsoleCommands).)  
  
         Bu komutları el ile bir yığın anlık görüntüsü uygulayarak ayıramazsınız sorunlarını gidermeye yardımcı olmak için kullanabilirsiniz.  
  
    -   Sınama nesnesi oluşturun ve JavaScript bellek Çözümleyicisi görünümlerde türleri görünümü gibi izleme. Örneğin, belirli nesne veya öğenin çöpünün toplanma olup olmadığını görmek için başka bir nesneye çok büyük nesne ekleyebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: bir bellek sızıntısı (JavaScript) bulma](../profiling/walkthrough-find-a-memory-leak-javascript.md)