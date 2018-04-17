---
title: Visual Studio'da bellek kullanımını çözümleme | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 04/25/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2b1c7f9420c2e5a9d3225ae0e8ab0d9023afb275
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="profile-memory-usage-in-visual-studio"></a>Visual Studio profil bellek kullanımı
Bellek sızıntıları ve verimsiz bellek hata ayıklayıcısı ile tümleşik hatalarını ayıkladığınız sırada Bul **bellek kullanımı** tanı aracı. Uygulamanız bir veya daha fazla bellek kullanımı araç sağlar *anlık görüntüleri* nesne türlerini bellek kullanımı etkisini anlamanıza yardımcı olması için yönetilen ve yerel bellek heap öğesinin. .NET, yerel ya da karma mod (.NET ve yerel) uygulamaları anlık görüntüleri toplayabilirsiniz.  
  
 Aşağıdaki grafik gösterir **tanılama araçları** penceresi (Visual Studio 2015 güncelleştirme 1 ve sonraki sürümlerinde kullanılabilir):  
  
 ![DiagnosticTools&#45;Update1](../profiling/media/diagnostictools-update1.png "DiagnosticTools Update1")  
  
 İçinde herhangi bir zamanda bellek anlık görüntüleri toplamak rağmen **bellek kullanımı** aracı, performans sorunları incelemeye sırasında uygulamanızı nasıl yürütür denetlemek için Visual Studio hata ayıklayıcısı kullanabilirsiniz. Kesme noktalarını ayarlama, Adımlama, kesme tüm ve diğer hata ayıklayıcı eylemleri, performans araştırmalar en uygun olan kodu yazmalar odaklanmanıza yardımcı olabilir. Uygulamanızı çalışırken bu eylemleri gerçekleştirme sizi ilgilendirmeyen ve bir sorunu tanılamak için geçen süreyi önemli ölçüde düşürebilirsiniz kodundan gürültü ortadan kaldırabilirsiniz.  
  
 Hata ayıklayıcı dışında bellek Aracı'nı da kullanabilirsiniz. Bkz: [bellek kullanımını hata ayıklama olmadan](../profiling/memory-usage-without-debugging2.md).  
  
> [!NOTE]
>  **Özel ayırıcısı Destek** yerel bellek profil oluşturucu çalışır ayırma toplayarak [ETW](/windows-hardware/drivers/devtest/event-tracing-for-windows--etw-) göre çalışma zamanı sırasında gösterilen olay verileri.  Böylece ayırma verilerini yakalanabilir allocators CRT ve Windows SDK kaynak düzeyinde açıklama.  Kendi allocators yazma sonra yeni ayrılan yığın bellek için bir işaretçi döndüren tüm işlevler ile donatılmış [__declspec](/cpp/cpp/declspec)(myMalloc için bu örnekte görüldüğü gibi ayırıcısı):  
>   
>  `__declspec(allocator) void* myMalloc(size_t size)` 

Bu öğreticide şunları yapacaksınız:

> [!div class="checklist"]
> * Bellek anlık görüntülerini alın
> * Bellek kullanım verilerini çözümleme

## <a name="collect-memory-usage-data"></a>Bellek kullanım verilerini toplama

1.  Visual Studio'da hata ayıklama ve bellek kullanımı inceleniyor başlamasını istediğiniz yere noktada uygulamanızda bir kesme noktası ayarlamak istediğiniz projeyi açın.

    Burada bir bellek sorununu şüpheleniyorsanız bir alanı varsa, bellek sorun oluşmadan önce ilk kesme noktası ayarlayın.

    > [!TIP]
    >  Uygulamanızı sık ayırır ve belleği serbest bırakır olduğunda sizi ilgilendiren bir işlemin bellek profili yakalamak için bu zor olabilir çünkü başlangıç ve bitiş tam noktası bulmak için işlemi (veya adım işlemi aracılığıyla) kesme noktalarını ayarlayın bellek değiştirildi. 

2.  İşlev veya bölge analiz etmek istediğiniz kodu sonunda ikinci bir kesme noktası ayarlayın (veya bir şüpheli bellek sorununu gerçekleştikten sonra).
  
3.  **Tanılama araçları** penceresi görünür otomatik olarak, bunu devre dışı bırakmış sürece. Pencereyi yeniden getirmek için tıklatın **hata ayıklama / Windows / Tanılama Araçları Göster**.

4.  Seçin **bellek kullanımı** ile **seçtiğiniz Araçları** araç çubuğunda ayarlama.

     ![Tanılama araçlarını Göster](../profiling/media/DiagToolsSelectTool.png "DiagToolsSelectTool")

5.  Tıklatın **hata ayıklama / hata ayıklamayı Başlat** (veya **Başlat** araç çubuğunda veya **F5**).

     Uygulamanın yüklenmesi tamamlandığında, Tanılama Araçları'nın Özet görünümü görüntülenir.

     ![Tanılama araçları Özet sekmesi](../profiling/media/DiagToolsSummaryTab.png "DiagToolsSummaryTab")

     > [!NOTE]
     >  Bellek anlık görüntüleri, verileri, yerel ya da karma modda uygulamalarınızı hata ayıklama performansını etkileyebilir bellek toplama olduğundan, varsayılan olarak devre dışıdır. Yerel veya karışık mod uygulamaları anlık görüntüleri etkinleştirmek için bir hata ayıklama oturumu başlatın (kısayol tuşu: **F5**). Zaman **tanılama araçları** penceresi görüntülenir, bellek kullanımı sekmesini seçin ve ardından **yığın profil**.  
     >   
     >  ![Anlık görüntüler etkinleştiremezsiniz](../profiling/media/dbgdiag_mem_mixedtoolbar_enablesnapshot.png "DBGDIAG_MEM_MixedToolbar_EnableSnapshot")  
     >   
     >  Durdur (kısayol tuşu: **Shift + F5**) ve hata ayıklamayı yeniden başlatın.  

6.  Hata ayıklama oturumunun başlangıcında bir anlık görüntüsünü tercih **anlık görüntü Al** üzerinde **bellek kullanımı** Özet araç. (Bu bir kesme noktası burada da ayarlamak için yardımcı olabilir.)

    ![Anlık Görüntü Al](../profiling/media/dbgdiag_mem_mixedtoolbar_takesnapshot.png "DBGDIAG_MEM_MixedToolbar_TakeSnapshot") 
     
     > [!TIP]
     >  Bellek karşılaştırmaları için bir taban çizgisi oluşturmak için hata ayıklama oturumunun başlangıcında anlık göz önünde bulundurun.  

6.  İlk kesme noktası isabet neden olur senaryosu çalıştırabilirsiniz.

7.  Hata ayıklayıcı ilk kesme noktasında duraklatıldığında seçin **anlık görüntü Al** üzerinde **bellek kullanımı** Özet araç.  

8.  İkinci isabetini uygulamayı çalıştırmak için F5'e basın.

9.  Şimdi, başka bir anlık görüntü alın.

     Bu noktada, verileri çözümlemek başlayabilirsiniz.    
  
## <a name="analyze-memory-usage-data"></a>Bellek kullanım verilerini çözümleme
Bellek kullanımı Özet Tablo hata ayıklama oturumu sırasında yapılan anlık görüntüleri listeler ve daha ayrıntılı görünümler için bağlantılar sağlar.

![Bellek Özet Tablo](../profiling/media/dbgdiag_mem_summarytable.png "DBGDIAG_MEM_SummaryTable")

 Proje Özellikleri'nde seçtiğiniz hata ayıklama modunu sütun adını bağlıdır: .NET, yerel ya da karma (.NET ve yerel).  
  
-   **Nesneleri (fark)** ve **ayırmaları (fark)** sütunları görüntüleme nesne sayısı .NET ve yerel bellek anlık görüntü alındıktan olduğunda.  
  
-   **Yığın boyutu (fark)** sütunu .NET ve yerel yığın bayt sayısını gösterir 

Birden çok anlık görüntüler aldıysanız, Özet Tablo hücrelerinin değişiklik satır anlık görüntü ve önceki bir anlık arasında bir değer ekleyin.  

Bellek kullanımı çözümlemek için ayrıntılı bir rapor bellek kullanımı açılır bağlantılardan birini tıklatın:  

-   Geçerli anlık görüntünün ve önceki anlık görüntünün arasındaki farkı ayrıntılarını görüntülemek için sol ok değiştir bağlantısını seçin (![bellek kullanımını artırır](../profiling/media/prof-tour-mem-usage-up-arrow.png "bellek kullanımını artırır")). Kırmızı bir ok bellek kullanımı ve bir düşüşü gösterir için yeşil bir ok artış gösterir.

    > [!TIP]
    >  Bellek sorunları daha hızlı bir şekilde tanımlamak için fark raporları en genel numarasında artan nesne türlerine göre sıralanır (değişiklik bağlantıya tıklayın **nesneleri (fark)** sütun) veya en genel yığın boyutu (tıklatın artar Değiştir bağlantısını **yığın boyutu (fark)** sütun).

-   Yalnızca seçilen anlık görüntü ayrıntılarını görüntülemek için değişiklik olmayan bağlantıya tıklayın. 
  
 Raporun ayrı bir pencerede görüntülenir.   
  
### <a name="managed-types-reports"></a>Yönetilen türler raporları  
 Geçerli bağlantıyı seçin bir **nesneleri (fark)** veya **ayırmaları (fark)** bellek kullanımı Özet tablodaki hücre.  
  
 ![Yönetilen tür rapor hata ayıklayıcı &#45; kök yollara](../profiling/media/dbgdiag_mem_managedtypesreport_pathstoroot.png "DBGDIAG_MEM_ManagedTypesReport_PathsToRoot")  
  
 Üst bölme sayısı ve türleri boyutu türü tarafından başvurulan tüm nesnelerin boyutunu dahil olmak üzere anlık görüntüyü gösterir (**kapsayıcı boyutu**).  
  
 **Kök yollara** alt bölme ağacında üst bölmede seçili türü başvuru nesneleri görüntüler. Yalnızca başvurduğu son türü serbest bırakıldığında .NET Framework Atık toplayıcısının bir nesne için bellek temizler.  
  
 **Başvurulan türleri** ağacı üst bölmede seçilen türe göre tutulan başvuruları görüntüler.  
  
 ![Yönetilen eferenced türleri rapor görünümü](../profiling/media/dbgdiag_mem_managedtypesreport_referencedtypes.png "DBGDIAG_MEM_ManagedTypesReport_ReferencedTypes")  
  
 Üst bölmede seçili türünün örneklerini görüntülemek için seçin ![örneği simgesi](../profiling/media/dbgdiag_mem_instanceicon.png "DBGDIAG_MEM_InstanceIcon") simgesi.  
  
 ![Örnekler Görünüm](../profiling/media/dbgdiag_mem_managedtypesreport_instances.png "DBGDIAG_MEM_ManagedTypesReport_Instances")  
  
 **Örnekleri** görünüm anlık görüntüdeki üst bölmede seçili nesne örneklerini görüntüler. Kök ve başvuru türleri bölmesinde yollara seçilen örnek ve seçilen örnek başvuran türleri başvuru nesneleri görüntüler. Hata ayıklayıcı burada anlık görüntü alındıktan noktada durdurulduğunda, bir araç ipucunda nesnenin değerlerini görüntülemek için Değer hücresini üzerinden gelebilirsiniz.  
  
### <a name="native-type-reports"></a>Yerel tür raporları  
 Geçerli bağlantıyı seçin bir **ayırmaları (fark)** veya **yığın boyutu (fark)** bellek kullanımı özet tablosuna hücre **tanılama araçları** penceresi.  
  
 ![Yerel tür Görünüm](../profiling/media/dbgdiag_mem_native_typesview.png "DBGDIAG_MEM_Native_TypesView")  
  
 **Türleri Görünüm** sayısını ve boyutunu türleri anlık görüntüler.  
  
-   Örnekleri simgesini seçin (![örneği simgesi nesne türü sütununda](../profiling/media/dbg_mma_instancesicon.png "DBG_MMA_InstancesIcon")) anlık seçilen türündeki nesneler hakkındaki bilgileri görüntülemek için seçilen bir tür.  
  
     **Örnekleri** görünümü her örnek seçilen tür görüntüler. Bir örneği seçildiğinde örneğinde oluşturulmasını ile sonuçlandı çağrı yığını görüntülenir **ayırma çağrı yığını** bölmesi.  
  
     ![Örnekler Görünüm](../profiling/media/dbgdiag_mem_native_instances.png "DBGDIAG_MEM_Native_Instances")  
  
-   Seçin **yığınlar görünümü** içinde **görüntüleme modu** seçili türünün ayırma yığını görmek için liste.  
  
     ![Yığınlar Görünüm](../profiling/media/dbgdiag_mem_native_stacksview.png "DBGDIAG_MEM_Native_StacksView")  
  
### <a name="change-diff-reports"></a>(Fark) raporları değiştirme  
  
-   Özet tablosunu hücrede değiştir bağlantısını seçin **bellek kullanımı** sekmesi **tanılama araçları** penceresi.  
  
     ![Bir değişiklik seçin &#40;DIF&#41;f rapor](../profiling/media/dbgdiag_mem_choosediffreport.png "DBGDIAG_MEM_ChooseDiffReport")  
  
-   İçindeki bir anlık görüntüsünü seçin **karşılaştırmak için** yönetilen veya yerel rapor listesi.  
  
     ![Karşılaştırmak için listeden bir anlık görüntüsünü seçin](../profiling/media/dbgdiag_mem_choosecompareto.png "DBGDIAG_MEM_ChooseCompareTo")  
  
 Değişiklik raporu sütunları ekler (ile işaretli **(fark)**) temel anlık görüntü değer karşılaştırma anlık görüntü arasındaki fark Göster temel rapor. Yerel türü görünümü fark raporu nasıl görünebileceği aşağıda verilmiştir:  
  
 ![Yerel türler fark Veiw](../profiling/media/dbgdiag_mem_native_typesviewdiff.png "DBGDIAG_MEM_Native_TypesViewDiff")  
  
## <a name="blogs-and-videos"></a>Bloglar ve videolar  

|         |         |
|---------|---------|
|  ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin")  |    [Bir video izlemek](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Profiling-with-Diagnostics-Tools-in-Visual-Studio-2017-daHnzMD6D_9211787171) bellek kullanımı ve Visual Studio 2017 CPU kullanımı analiz etme gösterir tanılama araçlarını kullanma. |

 [Hata ayıklama sırasında CPU ve bellek çözümleme](https://blogs.msdn.microsoft.com/visualstudio/2016/02/15/analyze-cpu-memory-while-debugging/)  
  
 [Visual C++ Blog: Visual C++ 2015'te bellek profili oluşturma](https://blogs.msdn.microsoft.com/vcblog/2015/10/21/memory-profiling-in-visual-c-2015/)  

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, toplamak ve bellek kullanım verilerini analiz etme öğrendiniz. Zaten tamamladıysanız [profil oluşturucu Turu](../profiling/profiling-feature-tour.md), uygulamalarınızdaki CPU kullanımı analiz etme hızlı bir bakış almak isteyebilirsiniz.

> [!div class="nextstepaction"]
> [CPU kullanımını analiz etme](../profiling/beginners-guide-to-performance-profiling.md) 