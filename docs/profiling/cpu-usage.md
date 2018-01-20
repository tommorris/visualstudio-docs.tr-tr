---
title: "Visual Studio'da CPU kullanımı analiz | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7501a20d-04a1-480f-a69c-201524aa709d
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cfe16da805ec8a43af8bed0c7e112e589d060bc4
ms.sourcegitcommit: 5d43e9590e2246084670b79269cc9d99124bb3df
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="analyze-cpu-usage"></a>CPU kullanımı analiz
Uygulamanızda performans sorunları araştırmak gerektiğinde başlatmak için uygun bir yerdir nasıl CPU kullandığı anlamaktır. **CPU kullanımı** aracı gösterir, CPU Visual C++, Visual C# yürütme süresi yeri harcıyorsa / Visual Basic ve JavaScript kodu. Visual Studio 2015 güncelleştirme 1'de başlayarak, hata ayıklayıcı ayrılmadan CPU kullanımı işlevi başına dökümünü görebilirsiniz. Hata ayıklama sırasında CPU açma ve kapatma profil açın ve yürütme, örneğin bir kesme noktasında durdurulduğunda sonuçları görüntüleyin.  
  
Çalıştıran ve tanılama oturumunuz yönetmek için birkaç seçeneğiniz vardır. Örneğin, çalıştırabilirsiniz **CPU kullanımı** aracı yerel veya uzak makinelerde veya üzerinde bir simulator veya öykünücü. Visual Studio'da çalışan bir uygulama için bağlı, açık bir projesi performansını analiz ya da Microsoft Store yüklü bir uygulamayı başlatın. Daha fazla bilgi için bkz: [çalıştırmak profil oluşturma araçları ile veya olmadan hata ayıklayıcı](../profiling/running-profiling-tools-with-or-without-the-debugger.md).

Burada, toplamak ve yayın derlemeleri ile CPU kullanımını analiz etme gösteriyoruz. Hata ayıklama sırasında CPU kullanımını analiz etmek için bkz: [performans profili oluşturma Başlangıç Kılavuzu](../profiling/beginners-guide-to-performance-profiling.md). 
  
##  <a name="BKMK_Collect_CPU_usage_data"></a>CPU kullanım verilerini toplama  
  
1.  Visual Studio'da çözüm yapılandırma kümesi **sürüm** ve dağıtım hedefini seçin.  
  
     ![Yayın seçip yerel makine](../profiling/media/cpuuse_selectreleaselocalmachine.png "CPUUSE_SelectReleaseLocalMachine")  
  
    -   Uygulama çalışırken **sürüm** modu gerçek uygulamanızın performansı ile daha iyi bir görünümünü sağlar.  
  
    -   En iyi uygulama yerel makine üzerinde çalışırken, yüklü uygulamayı yürütülmesi çoğaltır.  
  
    -   Uzak bir aygıttan veri topluyorsanız, uygulamayı doğrudan cihazda ve Uzak Masaüstü bağlantısı kullanarak değil çalıştırın.  
  
    -   Windows Phone uygulamaları için doğrudan veri toplamayı **aygıt** en doğru verileri sağlar.  
  
2.  Üzerinde **hata ayıklama** menüsünde seçin **Performans Profil Oluşturucu...** .  
  
3.  Seçin **CPU kullanımı** ve ardından **Başlat**.  
  
     ![CPU kullanımı seçin](../profiling/media/cpuuse_lib_choosecpuusage.png "CPUUSE_LIB_ChooseCpuUsage")  
  
4.  Uygulama başlatıldığında tıklatın **almak en çok sayı**. Çıktı görüntülendikten sonra ikinci bir hakkında bekleyin ve ardından **en büyük sayı zaman uyumsuz Al**. Düğme tıklamaları yapar bekleyen düğmesi yalıtmak daha kolay tıklatın Tanılama raporu yordamları.  
  
5.  İkinci çıkış satır göründükten sonra seçin **koleksiyonunu Durdur** performans ve tanılama hub'ında.  
  
 ![CpuUsage veri toplamayı durdurmayı](../profiling/media/cpu_use_wt_stopcollection.png "CPU_USE_WT_StopCollection")  
  
 CPU kullanımı aracı verileri analiz eder ve rapor görüntüler.  
  
 ![CpuUsage rapor](../profiling/media/cpu_use_wt_report.png "CPU_USE_WT_Report")  
  
## <a name="analyze-the-cpu-usage-report"></a>CPU kullanım raporu Çözümle  
  
###  <a name="BKMK_The_CPU_Usage_call_tree"></a>CPU kullanımı çağrı ağacı  
 Çağrı ağacı bilgileri anlama başlamak için yeniden `GetMaxNumberButton_Click` segmentlere ayırmak ve çağrı ağacı ayrıntılarını inceleyin.  
  
####  <a name="BKMK_Call_tree_structure"></a>Çağrı ağaç yapısı  
 ![GetMaxNumberButton &#95; Çağrı ağacı tıklatın](../profiling/media/cpu_use_wt_getmaxnumbercalltree_annotated.png "CPU_USE_WT_GetMaxNumberCallTree_annotated")  
  
|||  
|-|-|  
|![1. adım](../profiling/media/procguid_1.png "ProcGuid_1")|CPU kullanımı çağrısı ağaçları en üst düzey düğümünde sahte bir düğümdür|  
|![2. adım](../profiling/media/procguid_2.png "ProcGuid_2")|Çoğu uygulamalardaki zaman **Göster harici kod** seçeneği devre dışıdır, ikinci düzey düğüm bir **[dış kodu]** başlayan ve uygulama durdurur sistem ve framework kodu içeren düğümü çizer kullanıcı Arabirimi iş parçacığı zamanlama denetler ve diğer alt düzey uygulama hizmetleri sağlar.|  
|![3. adım](../profiling/media/procguid_3.png "ProcGuid_3")|Düğümün alt öğelerinin ikinci düzey adlı ya da framework kod ve ikinci düzey sistem oluşturduğunuz zaman uyumsuz yordamları ve kullanıcı kodu yöntemler ' dir.|  
|![Adım 4](../profiling/media/procguid_4.png "ProcGuid_4")|Bir yöntemin alt düğümleri yalnızca üst yöntemi çağrıları verilerini içerir. Zaman **Göster harici kod** olan devre dışı, uygulama yöntemlerini de içerebilir bir **[dış kodu]** düğümü.|  
  
####  <a name="BKMK_External_Code"></a>Harici kod  
 Harici kod olan sistem ve framework bileşenleri işlevlerde yazdığınız kodu tarafından yürütülür. Harici kod başlatın ve uygulamayı durdurun, UI çizin, iş parçacığı oluşturma denetleyen ve diğer alt düzey uygulama hizmetleri sağlamak işlevler içerir. Çoğu durumda, dış kodda ilgilenen olmayacak ve bu nedenle CPU kullanımı çağırın ağaç toplar kullanıcı yönteminin dış işlevler birine **[dış kodu]** düğümü.  
  
 Harici kod çağrısı yollarını görüntülemek istediğinizde, belirleyin **Göster harici kod** gelen **filtre görünümü** listeleyin ve ardından **Uygula**.  
  
 ![Filtre görünümü seçin, ardından Göster harici kod](../profiling/media/cpu_use_wt_filterview.png "CPU_USE_WT_FilterView")  
  
 İşlev adı sütunun genişliği tüm ancak bilgisayar monitörü en büyük görüntü genişliğini aşabilir böylece birçok harici kod çağrısı zincirleri derine yerleştirilir unutmayın. Bu gerçekleştiğinde, işlev adları olarak gösterilen **[...]** :  
  
 ![Çağrı ağacı dış kodda iç içe geçmiş](../profiling/media/cpu_use_wt_showexternalcodetoowide.png "CPU_USE_WT_ShowExternalCodeTooWide")  
  
 Aradığınız bir düğüm bulmak için arama kutusunu kullanın, sonra verileri görünüme getirmek için yatay kaydırma çubuğu kullanın:  
  
 ![İç içe geçmiş harici kod arama](../profiling/media/cpu_use_wt_showexternalcodetoowide_found.png "CPU_USE_WT_ShowExternalCodeTooWide_Found")  
  
###  <a name="BKMK_Call_tree_data_columns"></a>Çağrı ağacı veri sütunları  
  
|||  
|-|-|  
|**Toplam CPU (%)**|![Toplam % veri eşitlik](../profiling/media/cpu_use_wt_totalpercentequation.png "CPU_USE_WT_TotalPercentEquation")<br /><br /> Uygulamanın CPU etkinlik işlev ve işlev tarafından çağrılan işlev çağrıları tarafından kullanılan seçili zaman aralığı içinde yüzdesi. Bu farklı olduğuna dikkat edin **CPU kullanımı** bir zaman aralığı için toplam kullanılabilir CPU kapasitesini uygulamada yapılan toplam etkinliği karşılaştırır zaman çizelgesi grafik.|  
|**Kendi kendini CPU (%)**|![Kendi kendine % eşitlik](../profiling/media/cpu_use_wt_selflpercentequation.png "CPU_USE_WT_SelflPercentEquation")<br /><br /> İşlev çağrıları tarafından kullanılan seçili zaman aralığı uygulamanın CPU etkinliğinde yüzdesi, işlevleri etkinliğini hariç işlev tarafından çağrılır.|  
|**Toplam CPU (ms)**|Seçili zaman aralığı içinde işlev ve işlev tarafından adı veriliyordu işlev çağrılarında milisaniye sayısını harcanan.|  
|**Kendi kendini CPU (ms)**|Seçili zaman aralığı içinde işlev ve işlev tarafından adı veriliyordu işlev çağrılarında milisaniye sayısını harcanan.|  
|**Modülü**|İşlev veya işlevleri [dış kodu] düğümünde içeren modüllerin sayısını içeren modülü adı.|  
  
###  <a name="BKMK_Asynchronous_functions_in_the_CPU_Usage_call_tree"></a>CPU kullanımı zaman uyumsuz işlevlerde çağrı ağacı  
 Derleyici zaman uyumsuz bir yöntem karşılaştığında yöntemin yürütme denetlemek için gizli bir sınıf oluşturur. Kavramsal olarak, özgün metodun işlemlerini zaman uyumsuz olarak çağırma derleyicinin ürettiği işlevleri ve geri aramalar, Zamanlayıcı ve yineleyiciler doğru yürütmek için gerekli olan bir listesini içeren bir durum makinesinin sınıftır. Özgün yöntemi üst yöntemi tarafından çağrıldığında, çalışma zamanı üst yürütme bağlamından yöntemi kaldırır ve gizli sınıfı yöntemlerinin uygulamanın yürütme denetlemek sistem ve framework kodu bağlamında çalıştırılır. Zaman uyumsuz yöntemleri genellikle, ancak her zaman, bir veya daha fazla farklı iş parçacıklarında yürütülür. Bu kod CPU kullanımı çağrısı ağacında alt olarak gösterilen **[dış kodu]** hemen üst Ağaç düğümünün altında düğüm.  
  
 Bu örneğimizde görmek için yeniden seçin `GetMaxNumberAsyncButton_Click` zaman çizelgesi segmenti.  
  
 ![GetMaxNumberAsyncButton &#95; Rapor seçimi tıklatın](../profiling/media/cpu_use_wt_getmaxnumberasync_selected.png "CPU_USE_WT_GetMaxNumberAsync_Selected")  
  
 İlk iki düğüm altında **[dış kodu]** durumu makine sınıfının derleyicinin ürettiği yöntemleridir. Üçüncü özgün yöntem çağrısı var. Oluşturulan yöntemleri genişletme neler olduğunu gösterir.  
  
 ![Genişletilmiş GetMaxNumberAsyncButton &#95; Çağrı ağacı tıklatın](../profiling/media/cpu_use_wt_getmaxnumberasync_expandedcalltree.png "CPU_USE_WT_GetMaxNumberAsync_ExpandedCallTree")  
  
-   `MainPage::GetMaxNumberAsyncButton_Click`çok az yapar; görev değerlerinin bir listesini yönetir, sonuçları maksimum hesaplar ve çıktısını görüntüler.  
  
-   `MainPage+<GetMaxNumberAsyncButton_Click>d__3::MoveNext`zamanlama ve çağrısı sarmalamak 48 görevleri başlatmak için gerekli etkinliğini gösterir `GetNumberAsync`.  
  
-   `MainPage::<GetNumberAsync>b__b`Çağrı görevleri etkinliğini gösterir `GetNumber`.
