---
title: "Visual Studio'da Uygulama performansı profil | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 02/27/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: get-started-article
f1_keywords:
- vs.performance.wizard.intropage
helpviewer_keywords:
- Profiling Tools, quick start
- Diagnostics Tools, CPU Usage
- CPU Usage
- Diagnostics Tools
ms.assetid: da2fbf8a-2d41-4654-a509-dd238532d25a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: bacc4e9ebb0b0125b22089ec53a97248e9e1f4e9
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2018
---
# <a name="profile-application-performance-in-visual-studio"></a>Visual Studio'da profili uygulama performansı
Profil Araçları Visual Studio, uygulamanızda performans sorunlarını çözümlemek için kullanabilirsiniz. Bu yordam nasıl kullanılacağını gösterir **CPU kullanımı** sekmesi, uygulamanız için performans verilerini almak için tanılama araçları. Tanılama araçları, yerel/C++ geliştirme ve ASP.NET, dahil olmak üzere Visual Studio .NET geliştirme için desteklenir.
  
Hata ayıklayıcıyı zaman duraklatır, **CPU kullanımı** aracı uygulamanızda yürütülen işlevler hakkında bilgi toplar. Aracı iş gerçekleştirdiğiniz işlevleri listeler ve örnekleme oturum belirli kesimlerinde odaklanmak için kullanabileceğiniz bir zaman çizelgesi grafik sağlar.

Tanılama hub'ı çok çalıştırın ve tanılama oturumunuz yönetmek için diğer seçenekleri sunar. Varsa **CPU kullanımı** ihtiyacınız veri vermez [diğer profil oluşturma araçları](../profiling/Profiling-Tools.md) değişik size yardımcı olabilecek bilgiler sağlar. Çoğu durumda, uygulamanızın performans düşüklüğü, CPU, bellek, işleme kullanıcı Arabirimi veya ağ istek süresi gibi dışında bir şey tarafından kaynaklanıyor olabilir. Tanılama hub'ı çok kaydetmek ve bu tür verilerin çözümlemek için diğer seçenekleri sunar.

|         |         |
|---------|---------|
|  ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin")  |    [Bir video izlemek](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Profiling-with-Diagnostics-Tools-in-Visual-Studio-2017-daHnzMD6D_9211787171) CPU kullanımı analiz etme ve bellek kullanımını analiz etme gösterir tanılama araçlarını kullanma. |

Bu konuda, biz hata ayıklama normal iş akışınızda çözümlenirken CPU kullanımı ele alacağız. CPU kullanımı - daha fazla bilgi için çalışan bir uygulamanın hedefleyerek veya bir hata ayıklayıcısı ekli olmadan çözümleyebilirsiniz [hata ayıklama olmadan profil oluşturma verilerini toplama](../profiling/running-profiling-tools-with-or-without-the-debugger.md#collect-profiling-data-without-debugging) içinde [Profil Araçları ile veya olmadanhataayıklayıcıÇalıştır](../profiling/running-profiling-tools-with-or-without-the-debugger.md).
  
##  <a name="BKMK_Quick_start__Collect_diagnostic_data"></a>1. adım: profil oluşturma verilerini topla 
  
1.  Visual Studio'da hata ayıklama ve CPU kullanımını incelemek istediğiniz bir noktada, uygulamanızda bir kesme noktası ayarlamak istediğiniz projeyi açın.

2.  İkinci bir kesme noktası işlevi veya bölge analiz etmek istediğiniz kodu sonunda ayarlayın.

    > [!TIP]
    > İki kesme noktası belirleyerek, çözümlemek istediğiniz kod parçalarını veri toplama sınırlayabilirsiniz.
  
3.  **Tanılama araçları** penceresi görünür otomatik olarak, bunu devre dışı bırakmış sürece. Pencereyi yeniden getirmek için tıklatın **hata ayıklama / Windows / Tanılama Araçları Göster**.

4.  Görmek isteyip istemediğinizi seçebilirsiniz **CPU kullanımı**, [bellek kullanımı](../profiling/Memory-Usage.md), ya da her ikisini birlikte **seçtiğiniz Araçları** araç çubuğunda ayarlama. Visual Studio Enterprise çalıştırıyorsanız, ayrıca etkinleştirebilir veya IntelliTrace içinde devre dışı **Araçlar / Seçenekler / IntelliTrace**.

     ![Tanılama araçlarını Göster](../profiling/media/DiagToolsSelectTool.png "DiagToolsSelectTool")

     Biz esas olarak CPU kullanımı arayan olması, bu nedenle olduğundan emin olun **CPU kullanımı** etkin (varsayılan olarak etkindir).

5.  Tıklatın **hata ayıklama / hata ayıklamayı Başlat** (veya **Başlat** araç çubuğunda veya **F5**).

     Uygulamanın yüklenmesi tamamlandığında, Tanılama Araçları'nın Özet görünümü görüntülenir.

     ![Tanılama araçları Özet sekmesi](../profiling/media/DiagToolsSummaryTab.png "DiagToolsSummaryTab")

     Olaylar hakkında daha fazla bilgi için bkz: [arama ve filtreleme tanılama araçları penceresindeki olaylar sekmesi](http://blogs.msdn.com/b/visualstudioalm/archive/2015/11/12/searching-and-filtering-the-events-tab-of-the-diagnostic-tools-window.aspx)

6.  İlk kesme noktası isabet neden olur senaryosu çalıştırabilirsiniz.

7.  Hata ayıklayıcı durdurulduğunda, CPU kullanım verilerini toplamayı etkinleştirmek ve ardından açın **CPU kullanımı** sekmesi.

     ![Tanılama araçlarını etkinleştirme CPU profil](../profiling/media/DiagToolsEnableCPUProfiling.png "DiagToolsEnableCPUProfiling")

     Seçtiğinizde **kayıt CPU profili**, Visual Studio işlevlerinizi kaydı başlayacak ve aldıkları yürütmek için ne kadar süre. Uygulamanızı bir kesme noktasında durdurulamaz olduğunda, yalnızca bu toplanan verileri görüntüleyebilirsiniz.

8.  İkinci isabetini uygulamayı çalıştırmak için F5'e basın.

     Şimdi, artık performans verilerini bölge için özellikle uygulamanıza iki kesme noktaları arasında çalışan kod sahipsiniz.

9.  CPU zaman çizelgesinde çözümlenmesinde ilgilenen bölgeyi seçin (gösteren bir bölge olmalıdır profil oluşturma verilerini).

     ![Tanılama araçları zaman diliminin seçme](../profiling/media/DiagToolsSelectTimeSegment.png "DiagToolsSelectTimeSegment")

     Profil Oluşturucu iş parçacığı verileri hazırlama başlar. Bitmesini bekleyin.

     ![Tanılama araçları hazırlama iş parçacığı](../profiling/media/DiagToolsPreparingThreads.png "DiagToolsPreparingThreads")
  
     Raporda CPU kullanımı araç görüntüler **CPU kullanımı** sekmesi.
  
     ![Tanılama araçları CPU kullanımı sekmesi](../profiling/media/DiagToolsCPUUsageTab.png "DiagToolsCPUUsageTab")

     Bu noktada, verileri çözümlemek başlayabilirsiniz.

## <a name="Step2"></a>2. adım: CPU kullanım verilerini çözümleme

CPU kullanımı altında işlevlerin listesi inceleyerek, en fazla çalışmayı yapan işlevleri tanımlama ve her biri daha ayrıntılı bir bakış alma verilerinizi incelemeye başlamak öneririz.

1. İşlev listesinde en fazla çalışmayı yapan işlevleri inceleyin.

    ![Tanılama araçları CPU kullanımı işlevi listesinde](../profiling/media/DiagToolsCPUUsageFunctionList.png "DiagToolsCPUUsageFunctionList")

    > [!TIP]
    > İşlevler en fazla çalışmayı yapan olanlar başlangıç sırayla listelenir (çağrı sırayla olmadıklarını). Bu en uzun çalışan işlevleri hızla tanımlamanıza yardımcı olur.

2. İşlev listesinde çok fazla iş yaptığını uygulama işlevlerinizi birini çift tıklatın.

    Bir işlev çift tıkladığınızda **arayan/Aranan** sol bölmede görünümünü açar. 

    ![Tanılama araçları çağıran Aranan görünümü](../profiling/media/DiagToolsCallerCallee.png "DiagToolsCallerCallee")

    Başlık hem de bu görünümde seçili işlevi görüntülenir **geçerli işlevi** kutusunu (Bu örnekte, GetNumber). Solda'nin altında gösterilen geçerli işlevini çağırdı işlevi **işlevi çağırma**, ve geçerli işlev tarafından çağrılan tüm işlevler gösterilir **çağrılan işlevler** sağdaki kutusu. (Geçerli işlevi değiştirmek için ya da kutusunu seçebilirsiniz.)

    Bu görünüm toplam süre (ms) ve genel uygulamayı işlevi tamamlamak için geçen zaman yüzdesini gösterir.
    **İşlev gövdesi** ayrıca toplam zamanı (ve zamanı yüzdesi) işlev gövdesine harcanan zaman hariç içinde arama harcanan ve işlevleri adlı gösterilmektedir. (Bu örnekte, 3713 dışı 3729 ms işlev gövdesine harcanan ve kalan 16 ms bu işlev tarafından çağrılan dış kodunda harcanan).

    > [!TIP]
    > Yüksek değerleri **işlev gövdesi** işlevi içinde performans sorunu gösteriyor olabilir.

3. Hangi işlevleri çağrılan, select sipariş gösteren üst düzey bir görünüm görmek istiyorsanız **çağrı ağacı** bölmesinin üst aşağı açılan listeden.
 
    Şekil numaralı her alanda bir yordamda adım ile ilgilidir.
  
    ![Tanılama araçları çağrı ağacı](../profiling/media/DiagToolsCallTree.png "DiagToolsCallTree")
  
|||
|-|-|
|![1. adım](../profiling/media/ProcGuid_1.png "ProcGuid_1")|CPU kullanımı çağrısı ağaçları en üst düzey düğümünde sahte bir düğümdür|  
|![2. adım](../profiling/media/ProcGuid_2.png "ProcGuid_2")|Çoğu uygulamalardaki zaman [Göster harici kod](#BKMK_External_Code) seçeneği devre dışıdır, ikinci düzey düğüm bir **[dış kodu]** başlayan ve uygulama durdurur sistem ve framework kodu içeren düğümü çizer kullanıcı Arabirimi iş parçacığı zamanlama denetler ve diğer alt düzey uygulama hizmetleri sağlar.|  
|![3. adım](../profiling/media/ProcGuid_3.png "ProcGuid_3")|Düğümün alt öğelerinin ikinci düzey adlı ya da framework kod ve ikinci düzey sistem oluşturduğunuz zaman uyumsuz yordamları ve kullanıcı kodu yöntemler ' dir.|
|![Adım 4](../profiling/media/ProcGuid_4.png "ProcGuid_4")|Bir yöntemin alt düğümleri yalnızca üst yöntemi çağrıları verilerini içerir. Zaman **Göster harici kod** olan devre dışı, uygulama yöntemlerini de içerebilir bir **[dış kodu]** düğümü.|

Sütun değerleri hakkında daha fazla bilgi aşağıdadır:

- **Toplam CPU** ne kadar iş işlevi ve tarafından çağrılan tüm işlevler tarafından yapılmadı gösterir. Toplam CPU üksek genel en pahalı İşlevler seçeneğine gidin.
  
- **Kendi kendine CPU** ne kadar iş tarafından adlı işlevler tarafından çalışmanın hariç işlev gövdesi kod tarafından yapılmadı gösterir. Yüksek **Self CPU** değerleri işlev içinde performans sorunu olduğunu gösteriyor olabilir.

- **Modülleri** işlevi veya işlevleri [dış kodu] düğümünde içeren modüllerin sayısını içeren modül adı.

## <a name="BKMK_External_Code"></a>Dış görünümü kodu

Harici kod olan sistem ve framework bileşenleri işlevlerde yazdığınız kodu tarafından yürütülür. Harici kod başlatın ve uygulamayı durdurun, UI çizin, iş parçacığı oluşturma denetleyen ve diğer alt düzey uygulama hizmetleri sağlamak işlevler içerir. Çoğu durumda, dış kodda ilgilenen olmayacaktır ve böylece CPU kullanımı Aracı'nı toplar kullanıcı yönteminin dış işlevler birine **[dış kodu]** düğümü.
  
Harici kod çağrısı yollarını görüntülemek istiyorsanız, tercih **Göster harici kod** gelen **filtre görünümü** listeleyin ve ardından **Uygula**.  
  
![Filtre görünümü seçin, ardından Göster harici kod](../profiling/media/DiagToolsShowExternalCode.png "DiagToolsShowExternalCode")  
  
İşlev adı sütunun genişliği tüm ancak bilgisayar monitörü en büyük görüntü genişliğini aşabilir böylece birçok harici kod çağrısı zincirleri derine yerleştirilir unutmayın. Bu gerçekleştiğinde, işlev adları olarak gösterilen **[...]** .
  
Aradığınız bir düğüm bulmak için arama kutusunu kullanın, sonra verileri görünüme getirmek için yatay kaydırma çubuğu kullanın.

> [!TIP]
> Windows işlevlerini çağıran harici kod profil, en güncel .pdb dosyaları sahip olduğunuzdan emin olun. Bu dosyalar olmadan rapor görünümlerini şifreli ve anlaşılması zor Windows işlev adlarını listeler. İhtiyacınız olan dosyalara sahip olduğunuzdan emin olmak nasıl hakkında daha fazla bilgi için bkz: [belirtin simge (.pdb) ve kaynak dosyaları hata ayıklayıcı](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek kullanımı](../profiling/memory-usage.md)  
 [CPU kullanımı](../profiling/cpu-usage.md)  
 [Visual Studio'da profil oluşturma](../profiling/index.md)  
 [Özellik turu profil oluşturma](../profiling/profiling-feature-tour.md)
