---
title: VS hata ayıklayıcı olmadan bellek kullanımını çözümleme | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fc133ee89c61146ab5217e5b48f4c9cacff5aaf0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="analyze-memory-usage-without-the-visual-studio-debugger"></a>Visual Studio hata ayıklayıcısı olmadan bellek kullanımını çözümleme
Kullanabileceğiniz **bellek kullanımı** aşağıdakileri yapmak için hata ayıklama olmadan aracı  
  
-   Uygulamanızın izleme bellek kullanım hakkı Visual Studio'da bir senaryo geliştirirken.  
  
-   Uygulamanızın bellek durumu ayrıntılı anlık görüntülerini oluşturma.  
  
-   Bellek sorunları kök nedenini bulmak için anlık görüntü karşılaştırın.  
  
 Bu konuda açıklanmaktadır nasıl UWP XAML uygulama çözümlemek için bellek kullanımını Aracı'nı kullanın. UWP uygulamasında bellek kullanımını analiz etmek istiyorsanız, JavaScript ve HTML kullanıyorsa, bkz: [bellek kullanımı (JavaScript) analiz](../profiling/javascript-memory.md).  
  
##  <a name="BKMK_Start_a_Memory_Usage_diagnostic_session"></a> Bellek kullanımı Tanılama oturumu Başlat  
  
1.  Bir C# Evrensel Windows projesi Visual Studio'da açın.  
  
2.  Menü çubuğunda seçin **hata ayıklama / Performans Profil Oluşturucu...** .  
  
3.  Seçin **bellek kullanımı** ve ardından **Başlat** altındaki sayfasının düğmesini.  
  
     ![Bellek kullanımı Tanılama oturumu başlatmak](../profiling/media/memuse_start_diagnosticssession.png "MEMUSE_Start_DiagnosticsSession")  
  
##  <a name="BKMK_Monitor_memory_use"></a> Bellek kullanımını izleme  
 Kullanabilirsiniz ancak **bellek kullanımı** bulmak ve sorunları gidermek için kullanabileceğiniz ayrıntılı raporlar üretmek için aracı, onu etkin olarak geliştirmekte bir senaryo gerçek zamanlı bellek etkilerini araştırmak için de kullanabilirsiniz.  
  
 Tanılama oturumu başlattığınızda, uygulamanızı başlar ve **tanılama araçları** penceresi, uygulamanızın bellek kullanımı zaman çizelgesi grafiği görüntüler.  
  
 ![Bellek kullanımı genel bakış sayfasında](../profiling/media/memuse__reportoverview.png "MEMUSE__ReportOverview")  
  
 Çalışan zaman çizelgesi grafiği, uygulamanızın bellek dalgalanmalara gösterir. Grafikte ani genellikle biraz kod toplama veya veri oluşturma ve işlem bittiğinde atılıyor olduğunu gösterir. Büyük depoları en iyi duruma getirme olabilir alanları belirtin. Daha fazla yetersiz bellek kullanımı veya bellek sızıntısı gösterebilir çünkü döndürülmez bellek tüketimi artışa konusudur.  
  
###  <a name="BKMK_Close_a_monitoring_session"></a> Bir izleme oturumu kapat  
 ![Toplamayı Durdur](../profiling/media/memuse__stopcollection.png "MEMUSE__StopCollection")  
  
 Rapor oluşturma olmadan bir izleme oturumu durdurmak için yalnızca tanılama penceresini kapatın. Bellek anlık görüntüleri durumdayken bir rapor oluşturmak için tercih **durdurmak**.  
  
##  <a name="BKMK_Take_snapshots_to_analyze_the_memory_state_of_your_app"></a> Uygulamanızı bellek durumu anlık görüntülerini alın  
 İncelemek istediğiniz bir bellek sorun bulursanız, bellekte nesneleri belirli anlarda yakalamak için tanılama oturumu sırasında anlık görüntüsünü alabilirsiniz. Bir uygulama çok sayıda birçok türdeki nesneler kullandığından, üzerinde bir senaryo çözümleme yoğunlaşabilirsiniz isteyebilirsiniz. Senaryo yineleyebilirsiniz, uygulamanın taban çizgisi anlık bellek sorununu görünmesi sorunun ilk örneğini sonra başka bir anlık görüntü almak için iyi bir fikir ve bir veya daha fazla ek anlık görüntüleri de olabilir.  
  
 Anlık görüntüleri toplamak için yeni bir tanılama oturumu başlatın. Seçin **anlık görüntüsünü Al** bellek verileri yakalamak istediğinizde. Bir raporu oluşturmak için Seç **durdurmak**.  
  
##  <a name="BKMK_Memory_Usage_overview_page"></a> Bellek kullanımı genel bakış sayfası  
 Veri toplamayı durdurduktan sonra bellek kullanımı aracı uygulama durdurur ve genel bakış raporu görüntüler.  
  
 ![Bellek kullanımı genel bakış sayfasında](../profiling/media/memuse__reportoverview.png "MEMUSE__ReportOverview")  
  
###  <a name="BKMK_Memory_Usage_snapshot_views"></a> Bellek kullanımı anlık görüntü görünümleri  
 Yeni Visual Studio windows ayrıntılı raporlar açmak için anlık görüntü görünümlerini kullanın. Anlık görüntü görünümleri iki tür vardır:  
  
-   A [anlık görüntü ayrıntılı raporlar](../profiling/memory-usage-without-debugging2.md#BKMK_Snapshot_details_reports) türlerinin ve örneklerinin bir anlık görüntüde gösterir.  
  
-   A [fark (fark) raporları anlık görüntü](../profiling/memory-usage-without-debugging2.md#BKMK_Snapshot_difference__diff__reports) türleri ve iki anlık görüntüsü durumlarda karşılaştırır.  
  
 ![Anlık görüntü görünüm bağlantılar](../profiling/media/memuse__snapshotview_numbered.png "MEMUSE__SnapshotView_Numbered")  
  
 Anlık görüntü görünüm resimdeki numaralı öğeler bellek kullanımı rapor görünümlerini açmak bağlantılardır.  
  
|||  
|-|-|  
|![1. adım](../profiling/media/procguid_1.png "ProcGuid_1")|Anlık görüntü durumdayken bağlantı metnini bellekte toplam bayt sayısı gösterilir.<br /><br /> Türü örnekleri toplam boyutu tarafından sıralanmış bir anlık görüntü Ayrıntıları raporu görüntülemek için bu bağlantıyı seçin.|  
|![2. adım](../profiling/media/procguid_2.png "ProcGuid_2")|Anlık görüntü durumdayken bağlantı metnini bellekte nesneleri toplam sayısını gösterir.<br /><br /> Türlerin örnekleri sayısına göre sıralanmış bir anlık görüntü Ayrıntıları raporu görüntülemek için bu bağlantıyı seçin.|  
|![3. adım](../profiling/media/procguid_3.png "ProcGuid_3")|Bağlantı metni, bu anlık görüntü anda bellekte nesneleri toplam boyutu ve önceki anlık görüntüsünü toplam boyutu arasındaki farkı gösterir.<br /><br /> Boyutu daha küçük olduğunda bu anlık görüntü bellek boyutunu öncekinin ve negatif bir sayı büyük olduğunda, bağlantı metnini pozitif bir sayıdır. Bağlantı metni **temel** bu anlık görüntü tanılama oturumunda; ilk olduğunu gösterir **Hayır fark** fark sıfır olduğunu gösterir.<br /><br /> Türlerin örnekleri toplam boyutu fark göre sıralanmış bir anlık görüntü fark raporunu görüntülemek için bu bağlantıyı seçin.|  
|![Adım 4](../profiling/media/procguid_4.png "ProcGuid_4")|Bağlantı metni, önceki anlık görüntüsünü nesnelerin sayısı ve bu anlık görüntü bellek nesneleri toplam sayısı arasındaki farkı gösterir.<br /><br /> Türlerin örnekleri toplam hata sayısı fark göre sıralanmış bir anlık görüntü fark raporunu görüntülemek için bu bağlantıyı seçin.|  
  
##  <a name="BKMK_Snapshot_reports"></a> Anlık görüntü raporları  
 ![Bellek kullanımı anlık görüntü rapor](../profiling/media/memuse_snapshotreport_all.png "MEMUSE_SnapshotReport_All")  
  
###  <a name="BKMK_Snapshot_report_trees"></a> Anlık görüntü rapor ağaçları  
  
####  <a name="BKMK_Managed_Heap"></a> Yönetilen yığın  
 Yönetilen yığın ağaç [Yönetilen yığın ağaç (anlık görüntü ayrıntıları)](../profiling/memory-usage-without-debugging2.md#BKMK_Managed_Heap_tree__Snapshot_details_) ve [Yönetilen yığın ağaç (anlık görüntü fark)](../profiling/memory-usage-without-debugging2.md#BKMK_Managed_Heap_tree__Snapshot_diff_) türlerinin ve örneklerinin raporda göster. Türü veya örnek seçerek görüntüler **kök yollara** ve **başvurulan nesneler** ağaçları seçili öğe için.  
  
####  <a name="BKMK_Paths_to_Root"></a> Kök yolları  
 [Kök ağaç (anlık görüntü ayrıntıları) yollara](../profiling/memory-usage-without-debugging2.md#BKMK_Paths_to_Root_tree__Snapshot_details_) ve [kök ağaç (anlık görüntü fark) yollara](../profiling/memory-usage-without-debugging2.md#BKMK_Paths_to_Root_tree__Snapshot_diff_) türü veya örnek başvuru nesneleri zincirine göster. Yalnızca tüm başvurularını serbest bıraktığınızda .NET Framework Atık toplayıcısının bir nesne için bellek temizler.  
  
####  <a name="BKMK_Referenced_Objects"></a> Başvurulan nesneler  
 [Başvurulan nesneler ağaç (anlık görüntü ayrıntıları)](../profiling/memory-usage-without-debugging2.md#BKMK_Referenced_Objects_tree__Snapshot_details_) ve [başvurulan nesneler ağaç (anlık görüntü fark)](../profiling/memory-usage-without-debugging2.md#BKMK_Referenced_Objects_tree__Snapshot_diff_) seçili türü veya örnek başvuruda bulunan nesneleri göster.  
  
###  <a name="BKMK_Object_Type_and_Instance_fields"></a> Nesne türü ve örnek alanları  
 Zaman bir **nesne türü** giriş alt girişleri sahipse, bunları görüntülemek için ok simgesine seçebilirsiniz. Varsa rengini **nesne türü** metin mavi, kendi kaynak kodu dosyasının nesnesinde gitmek için seçebilirsiniz. Kaynak dosya ayrı bir pencerede açılır.  
  
 Örnek, bellek kullanımı aracı tarafından oluşturulan benzersiz kimlikler adlardır.  
  
 Kolayca belirleyemez türü fark ederseniz ya da kodunuzu nasıl dahil bilmiyorsanız, .NET Framework, işletim sistemi ya da sahipliği zincirde söz konusu olduğu için bellek kullanımı Aracı'nı görüntüleyen derleyici bir nesne olabilir nesnelerinizi.  
  
###  <a name="BKMK_Report_tree_filters_"></a> Rapor ağaç filtreleri  
 Çoğu uygulamalar, çoğu uygulama geliştiricisine çok ilginç olmayan türleri, şaşırtıcı çok sayıda içerir. **Bellek kullanımı** aracı tanımlar çoğu bu tür gizlemek için kullanabileceğiniz iki filtre **Yönetilen yığın** ve **kök yollara** ağaçları. Ayrıca bir ağaç türü adına göre filtre uygulayabilirsiniz.  
  
 ![Sıralama ve filtreleme seçenekleri](../profiling/media/memuse_sortandfilter.png "MEMUSE_SortAndFilter")  
  
####  <a name="BKMK_Filter"></a> Filtre  
 Bir dize girin **filtre** ağaç sınırlandırmak için kutusunu Belirtilen metni içeren türlerini görüntüler. Filtre büyük küçük harfe duyarlı değildir ve tür adları, herhangi bir parçası olarak belirtilen dizeyi tanır.  
  
####  <a name="BKMK_Collapse_Small_Objects"></a> Küçük nesneleri Daralt  
 Bu filtre uygulandığında özelliği türleri **boyutu (bayt)** anlık bellek toplam boyutunun yüzde 0,5'den az gizli **Yönetilen yığın** listesi.  
  
####  <a name="BKMK_Just_My_Code"></a> Yalnızca kendi kodum  
 **Sadece kendi kodumu** filtre dış kod tarafından oluşturulan çoğu örnekleri gizler. Dış türleri Framework bileşenlerini veya işletim sistemi tarafından sahip olunan veya derleyici tarafından üretilir.  
  
##  <a name="BKMK_Snapshot_details_reports"></a> Rapor anlık görüntüsü ayrıntıları  
 Bir anlık görüntü tanılama oturumundan odaklanmak için anlık görüntü ayrıntıları raporunu kullanın. Ayrıntıları raporu açmak için bağlantılardan birine bir anlık görüntü görünümünde aşağıdaki resimde gösterildiği gibi seçin. Her iki bağlantı aynı raporu açın; Başlangıç sıralama düzenini yalnızca farktır **Yönetilen yığın** rapor ağacında. Her iki durumda da, rapor açılır sonra sıralama düzenini değiştirebilirsiniz.  
  
 ![Anlık görüntü rapor bir anlık görüntü görünümünde bağlantılar](../profiling/media/memuse_snapshotview_snapshotdetailslinks.png "MEMUSE_SnapshotView_SnapshotDetailsLinks")  
  
-   **MB** bağlantı sıralar raporun **kapsayıcı boyutu (bayt)** sütun.  
  
-   **Nesneleri** bağlantı sıralar raporun **sayısı** sütun.  
  
###  <a name="BKMK_Managed_Heap_tree__Snapshot_details_"></a> Yönetilen yığın ağaç (anlık görüntü ayrıntıları)  
 **Yönetilen yığın** ağaç bellekte tutulan nesne türlerini listeler. Boyuta göre sıralanmış türü, on büyük örneklerini görüntülemek için bir tür adı genişletebilirsiniz. Türü veya örnek seçerek görüntüler **kök yollara** ve **başvurulan nesneler** ağaçları seçili öğe için.  
  
 ![Yönetilen yığın ağaç](../profiling/media/memuse__snapshotdetails_managedheaptree.png "MEMUSE__SnapshotDetails_ManagedHeapTree")  
  
|||  
|-|-|  
|**Nesne türü**|Tür ya da nesne örneğinin adı.|  
|**Sayısı**|Türünde nesne örneği sayısı. Sayı her zaman bir örneği için 1'dir.|  
|**Boyut (bayt)**|Bir türü nesnelerde yer alan nesneler boyutunu hariç türünün bellek anlık görüntüdeki tüm örneklerini boyutu.<br /><br /> Bir örneği, türü, örneğinde yer alan nesneler boyutunu hariç nesnenin boyutu için. örnekleri.|  
|**Kapsayıcı boyutu (bayt)**|Türünün örneklerini ya da kapsanan nesneleri boyutunu dahil olmak üzere tek bir örnek boyutunu boyutu.|  
  
###  <a name="BKMK_Paths_to_Root_tree__Snapshot_details_"></a> Kök ağaç (anlık görüntü ayrıntıları) yolları  
 **Kök ağaç yollara** türü veya örnek başvuru nesneleri zincirine gösterir. Yalnızca tüm başvurularını serbest bıraktığınızda .NET Framework Atık toplayıcısının bir nesne için bellek temizler.  
  
 ![Kök yolları ağaç türleri için](../profiling/media/memuse_snapshotdetails_type_pathstoroottree.png "MEMUSE_SnapshotDetails_Type_PathsToRootTree")  
  
 Bir tür görüntülediğinizde **kök yollara** ağacında, bu tür başvuruları tutmak türleri nesnelerin sayısı görüntülenir **başvuru sayısı** sütun. Bir örneği çözümlediğinizde sütun görünmez.  
  
###  <a name="BKMK_Referenced_Objects_tree__Snapshot_details_"></a> Başvurulan nesneler ağaç (anlık görüntü ayrıntıları)  
 **Başvurulan nesneler** ağaç, seçili türü veya örnek başvuruda bulunan nesneleri gösterir.  
  
 ![Başvurulan Objjects ağacı örnekleri](../profiling/media/memuse_snapshotdetails_referencedobjects_instance.png "MEMUSE_SnapshotDetails_ReferencedObjects_Instance")  
  
|||  
|-|-|  
|**Nesne türü / örnek**|Tür ya da nesne örneğinin adı.|  
|**Boyut (bayt)**|Bir türü türünde bulunan nesneler boyutunu hariç türünün tüm örneklerini boyutu.<br /><br /> Bir örneği nesnesinde yer alan nesneleri boyutunu hariç nesnenin boyutu.|  
|**Kapsayıcı boyutu (bayt)**|Türünün örneklerini ya da kapsanan nesneleri boyutunu dahil olmak üzere, örnek boyutunu toplam boyutu.|  
  
##  <a name="BKMK_Snapshot_difference__diff__reports"></a> Anlık görüntü fark (fark) raporları  
 Bir anlık görüntü fark (fark) raporu birincil bir anlık görüntü ve hemen daha önce alınan anlık arasında değişiklik gösterir. Diff raporu açmak için bağlantılardan birine bir anlık görüntü görünümünde aşağıdaki resimde gösterildiği gibi seçin. Her iki bağlantı aynı raporu açın; Başlangıç sıralama düzenini yalnızca farktır **Yönetilen yığın** rapor ağacında. Rapor açıldıktan sonra sıralama düzenini değiştirebilirsiniz.  
  
 ![Fark bağlantılar rapor bir anlık görüntü görünümünde](../profiling/media/memuse_snapshotview_snapshotdifflinks.png "MEMUSE_SnapshotView_SnapshotDiffLinks")  
  
-   **MB** bağlantı sıralar raporun **kapsayıcı boyutu (bayt)** sütun.  
  
-   **Nesneleri** bağlantı sıralar raporun **sayısı** sütun.  
  
###  <a name="BKMK_Managed_Heap_tree__Snapshot_diff_"></a> Yönetilen yığın ağaç (anlık görüntü fark)  
 **Yönetilen yığın** ağaç bellekte tutulan nesne türlerini listeler. Boyuta göre sıralanmış türü, on büyük örneklerini görüntülemek için bir tür adı genişletebilirsiniz. Türü veya örnek seçerek görüntüler **kök yollara** ve **başvurulan nesneler** ağaçları seçili öğe için.  
  
 ![Yönetilen yığın ağaç fark rapordaki bir tür için](../profiling/media/memuse_snapshotdiff_type_heap.png "MEMUSE_SnapshotDiff_Type_Heap")  
  
 Dikkat **sayısı**, **boyutu (bayt)**, ve **kapsayıcı boyutu (bayt)** sütunları, aşağıdaki resimde daraltılmış.  
  
|||  
|-|-|  
|**Nesne türü**|Tür ya da nesne örneğinin adı.|  
|**Sayısı**|Birincil anlık görüntüdeki bir türün örneklerinin sayısı. **Count** daima bir örneği için 1'dir.|  
|**Count fark**|Bir türü türdeki örneklerin sayısını birincil anlık görüntü ve önceki anlık görüntünün arasındaki farkı. Alan bir örnek için boştur.|  
|**Boyut (bayt)**|İçindeki nesneler yer alan nesneleri boyutunu hariç birincil anlık görüntü nesneleri boyutu. Bir tür için **boyutu (bayt)** ve **kapsayıcı boyutu (bayt)** türü örnekleri boyutlarını toplamlar.|  
|**Toplam boyutu fark (bayt)**|Nesnelerde yer alan nesneler boyutunu hariç türü için türdeki örneklerin toplam boyutu birincil anlık görüntü ve önceki bir anlık arasındaki fark. Alan bir örnek için boştur.|  
|**Kapsayıcı boyutu (bayt)**|İçindeki nesneler yer alan nesneleri boyutunu dahil olmak üzere birincil anlık görüntüyü nesneleri boyutu.|  
|**Kapsayıcı boyutu fark (bayt)**|Bir türü türünün tüm örneklerini boyutunu birincil anlık görüntü boyutu nesneleri bulunan nesneler de dahil olmak üzere önceki anlık görüntüyü arasındaki fark. Alan bir örnek için boştur.|  
  
###  <a name="BKMK_Paths_to_Root_tree__Snapshot_diff_"></a> Kök ağaç (anlık görüntü fark) yolları  
 **Kök ağaç yollara** türü veya örnek başvuru nesneleri zincirine gösterir. Yalnızca tüm başvurularını serbest bıraktığınızda .NET Framework Atık toplayıcısının bir nesne için bellek temizler.  
  
 ![İçin yollar için kök ağacı örnekleri bir fark görünümünde](../profiling/media/memuse_snapshotdiff_pathstoroot_instance_all.png "MEMUSE_SnapshotDiff_PathsToRoot_Instance_All")  
  
###  <a name="BKMK_Referenced_Objects_tree__Snapshot_diff_"></a> Başvurulan nesneler ağaç (anlık görüntü fark)  
 **Başvurulan nesneler** ağacı birincil türü veya örnek başvuruda bulunan nesneleri gösterir.  
  
 ![Başvurulan Objjects ağacı örnekleri](../profiling/media/memuse_snapshotdetails_referencedobjects_instance.png "MEMUSE_SnapshotDetails_ReferencedObjects_Instance")  
  
|||  
|-|-|  
|**Nesne türü / örnek**|Tür ya da nesne örneğinin adı.|  
|**Boyut (bayt)**|Bir örnek boyutu örneğinde yer alan nesneler hariç birincil anlık görüntüdeki nesnenin boyutu.<br /><br /> Bir türü örneğinde yer alan nesneler boyutunu hariç türünün birincil anlık görüntüdeki örneklerini toplam boyutu.|  
|**Kapsayıcı boyutu (bayt)**|İçindeki nesneler yer alan nesneleri boyutunu dahil olmak üzere birincil anlık görüntüyü nesneleri boyutu.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript belleği](../profiling/javascript-memory.md)  
 [Visual Studio'da profil oluşturma](../profiling/index.md)  
 [Özellik turu profil oluşturma](../profiling/profiling-feature-tour.md)  
 [C++, C# ve Visual Basic kullanarak UWP uygulamaları için performansı en iyi yöntemler](http://msdn.microsoft.com/library/windows/apps/hh750313.aspx)   
 [Visual Studio'da yeni bellek kullanımı aracıyla bellek sorunlarını tanılama](http://go.microsoft.com/fwlink/p/?LinkId=394706)