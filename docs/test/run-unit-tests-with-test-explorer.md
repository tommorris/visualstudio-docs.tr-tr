---
title: "Test Gezgini ile birim testleri çalıştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.unittesting.testexplorer.overview
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: bf466db15c30a9763c6d7be363041ee3bfa14f7d
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="run-unit-tests-with-test-explorer"></a>Test Gezgini ile birim testleri çalıştırma
Visual Studio ya da üçüncü taraf birim testi projelerini birim testleri çalıştırma, testleri kategoriler halinde gruplandırabilirsiniz, test listesini filtrelemek ve oluşturmak, kaydetme ve çalma testleri çalıştırmak için test Gezgini'ni kullanın. Ayrıca testleri hata ayıklama ve test performans ve kod kapsamını çözümleme.  
  
##  <a name="BKMK_Contents"></a>İçeriği  
 [Birim testi çerçevelerini ve test projeleri](#BKMK_Unit_test_frameworks_and_test_projects)  
  
 [Test Gezgini testleri çalıştırma](#BKMK_Run_tests_in_Test_Explorer)  
  
 [Test sonuçlarını görüntüleme](#BKMK_View_test_results)  
  
 [Grup ve test listesini filtreleme](#BKMK_Group_and_filter_the_test_list)  
  
 [Özel çalma listeleri oluşturma](#BKMK_Create_custom_playlists)  
  
 [Hata ayıklama ve birim testleri çözümleme](#BKMK_Debug_and_analyze_unit_tests)  
  
 [Dış Kaynaklar](#BKMK_External_resources)  
  
##  <a name="BKMK_Unit_test_frameworks_and_test_projects"></a>Birim testi çerçevelerini ve test projeleri  
 Visual Studio hem yönetilen hem de yerel kod için Microsoft birim test çerçevelerini içerir. Ancak, Test Gezgini herhangi bir birimi da bir Test Gezgini bağdaştırıcısı uyguladı test çerçevesi çalıştırabilirsiniz. Üçüncü şahıs birim test çerçevelerini yükleme hakkında daha fazla bilgi için bkz: [üçüncü taraf birim test çerçevelerini yükleme](../test/install-third-party-unit-test-frameworks.md)  
  
 Test Gezgini, bir çözümde birden çok test projelerden ve üretim kodu projeleri parçası olan test sınıflardan testleri çalıştırabilirsiniz. Test projeleri farklı birim test çerçevelerini kullanabilirsiniz. .NET Framework için test altındaki kodun yazıldığında test projesinin Ayrıca, hedef kod dilini bağımsız olarak .NET Framework hedefler herhangi bir dilde yazılabilir. Yerel C/C++ kod projeleri, C++ birim test çerçevesi kullanılarak test edilebilir. Daha fazla bilgi için bkz: [C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md).
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
##  <a name="BKMK_Run_tests_in_Test_Explorer"></a>Test Gezgini testleri çalıştırma  
 [Testler](#BKMK_Run_tests) **&#124;** [Her yapıdan sonra testleri çalıştırma](#BKMK_Run_tests_after_every_build)  
  
 Test projesi derlerken, testleri Test Gezgini'nde görünür. Test Gezgini görünür durumda değilse, seçin **Test** Visual Studio menüsünde, **Windows**ve ardından **Test Gezgini**.  
  
 ![Birim Test Gezgini](../test/media/ute_failedpassednotrunsummary.png "UTE_FailedPassedNotRunSummary")  
  
 Test Gezgini çalıştırmak, yazma ve testleri yeniden çalıştırmak gibi sonuçları varsayılan gruplar halinde görüntülenir. **başarısız testler**, **testleri geçti**, **atlandı testleri** ve  **Testler değil**. Test Gezgini testlerinizi grupları şekilde değiştirebilirsiniz.  
  
 Bulma, düzenleme ve testleri Test Gezgini araç çubuğundan çalışan işin çoğunu gerçekleştirebilirsiniz.  
  
 ![Test Gezgini araç çubuğundan testler](../test/media/ute_toolbar.png "UTE_ToolBar")  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
###  <a name="BKMK_Run_tests"></a>Testleri çalıştırma  
 Bir grup veya seçtiğiniz testleri kümesi tüm testleri Çözümdeki tüm testleri çalıştırın. Aşağıdakilerden birini yapın:  
  
-   Bir çözümde tüm testleri çalıştırmak için tercih **tümünü Çalıştır**.  
  
-   Bir varsayılan grubundaki tüm testleri çalıştırmak için tercih **Çalıştır...**  ve grubun menüsünde'i seçin.  
  
-   Seçilen test bağlam menüsünü açın ve ardından çalıştırmak istediğiniz tek tek testlerin seçin **seçili Testleri Çalıştır**.  
  
-   Tek tek testlerin herhangi bir sırayla çalıştırmak engelleyen bağımlılık varsa, paralel test yürütmesi ile Aç ![UTE &#95;parallelicon &#45; küçük](../test/media/ute_parallelicon-small.png "UTE_parallelicon küçük") iki durumlu düğme araç çubuğunda. Bu, tüm testleri çalıştırmak için geçen süre önemli ölçüde azaltabilir.  
  
 Test Gezgini penceresinin üst geçişi/hata çubuğu Testleri Çalıştır animasyon eklenir. Tüm testleri geçirilen ya da herhangi bir test başarısız olursa kırmızı kapatır testi sonuç geçişi/hata çubuğu yeşil olur.  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
###  <a name="BKMK_Run_tests_after_every_build"></a>Her yapıdan sonra testleri çalıştırma  
  
> [!WARNING]
>  Visual Studio kuruluştaki her yapı desteklenen sonra çalışan birim testleri.  
  
|||  
|-|-|  
|![Derleme sonrası çalıştırmak](../test/media/ute_runafterbuild_btn.png "UTE_RunAfterBuild_btn")|Her yerel yapıdan sonra birim testleri çalıştırmak için tercih **Test** standart menüsünde ve ardından **çalıştırmak sonra yapı testleri** Test Gezgini araç çubuğunda.|  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
##  <a name="BKMK_View_test_results"></a>Test sonuçlarını görüntüleme  
 [Test ayrıntıları görüntüleyin](#BKMK_View_test_details) **&#124;** [, Bir test yönteminin kaynak kodu görüntüleme](#BKMK_View_the_source_code_of_a_test_method)  
  
 Test Gezgini çalıştırmak, yazma ve testleri yeniden çalıştırmak gibi sonuçları gruplar halinde görüntülenir. **başarısız testler**, **testleri geçti**, **atlandı testleri** ve **çalışmıyor Testleri**. Test Gezgini görüntüler altındaki ayrıntılar bölmesini test özetini çalıştırın.  
  
###  <a name="BKMK_View_test_details"></a>Test ayrıntıları görüntüle  
 Bir test ayrıntılarını görüntülemek için test'i seçin.  
  
 ![Test yürütme ayrıntıları](../test/media/ute_testdetails.png "UTE_TestDetails")  
  
 Test Ayrıntılar bölmesinde aşağıdaki bilgileri görüntüler:  
  
-   Kaynak dosya adı ve test yöntemi satır sayısı.  
  
-   Test durumu.  
  
-   Test yöntemi sürdüğü geçen süre.  
  
 Sınama başarısız olursa, Ayrıntılar bölmesinde de görüntüler:  
  
-   Test için birim test çerçevesi tarafından döndürülen ileti.  
  
-   Yığın izleme testi başarısız zaman.  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
###  <a name="BKMK_View_the_source_code_of_a_test_method"></a>Bir test yönteminin kaynak kodu görüntüleme  
 Visual Studio Düzenleyicisinde test yöntemi için kaynak kodunu görüntülemek için test seçin ve ardından **açık Test** bağlam menüsünde (klavye: F12).  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
##  <a name="BKMK_Group_and_filter_the_test_list"></a>Grup ve test listesini filtreleme  
 [Test listesi gruplandırma](#BKMK_Grouping_the_test_list) **&#124;** [Nitelikler grupla](#BKMK_Group_by_traits) **&#124;** [Arama ve filtreleme test listesi](#BKMK_Search_and_filter_the_test_list)  
  
 Test Gezgini testlerinizi önceden tanımlanmış kategoriler halinde gruplandırabilirsiniz olanak sağlar. Test Gezgini let çalıştırdığınız çoğu birim test çerçevelerini kendi kategorileri ve testlerinizi gruplamak için kategori/değer çiftleri tanımlayın. Eşleşen dizeler karşı test özellikleri tarafından testleri listesi filtre uygulayabilirsiniz.  
  
###  <a name="BKMK_Grouping_the_test_list"></a>Test listesi gruplandırma  
 Seçin yanındaki aşağı oka testleri düzenlenir yöntemini değiştirmek için **Group By** düğmesini ![Test Gezgini grubu düğmesini](../test/media/ute_groupby_btn.png "UTE_GroupBy_btn") ve yeni bir grup seçin ölçütleri.  
  
 ![Test Gezgini'nda kategoriye göre testleri grup](../test/media/ute_groupbycategory.png "UTE_GroupByCategory")  
  
### <a name="test-explorer-groups"></a>Test Gezgini grupları  
  
|Grup|Açıklama|  
|-----------|-----------------|  
|**Süre**|Test grupları göre yürütme süresini: **hızlı**, **orta**, ve **yavaş**.|  
|**Sonucu**|Testleri yürütme sonuçları göre gruplandırır: **başarısız testler**, **atlandı testleri**, **testleri geçti**.|  
|**Özellikleri**|Belirlediğiniz kategori/değer çiftleri test grubu. Ayırdedici nitelik kategorileri ve değerleri belirtmek için sözdizimi birim test çerçevesi tarafından tanımlanır.|  
|**Proje**|Projeleri adıyla test grubu.|  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
###  <a name="BKMK_Group_by_traits"></a>Nitelikler göre gruplandırmak  
 Bir ayırdedici nitelik genellikle bir kategori ad/değer çifti adıdır, ancak tek bir kategori olabilir. Test yöntemi olarak birim testi çerçevesi tarafından tanımlanan yöntemler nitelikler atanabilir. Birim testi çerçevesi ayırdedici nitelik kategorileri tanımlayabilir. Kendi kategori ad/değer çiftleri tanımlamak için ayırdedici nitelik kategoriler değerleri ekleyebilirsiniz. Ayırdedici nitelik kategorileri ve değerleri belirtmek için sözdizimi birim test çerçevesi tarafından tanımlanır.  
  
 **Yönetilen kod için Framework sınama Microsoft biriminde özellikleri**  
  
 Microsoft birim test çerçevesi yönetilen uygulamalar için de ayırdedici nitelik adı tanımla / değer çiftini bir <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestPropertyAttribute> özniteliği. Test çerçevesi aynı zamanda bu önceden tanımlanmış özellikleri içerir:  
  
|Ayırdedici nitelik|Açıklama|  
|-----------|-----------------|  
|<xref:Microsoft.VisualStudio.TestTools.UnitTesting.OwnerAttribute>|Sahiplik kategorisi birim test çerçevesi tarafından tanımlanır ve bir dize değeri sahibinin sağlamanızı gerektirir.|  
|<xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute>|Öncelik kategori birim test çerçevesi tarafından tanımlanır ve öncelik tamsayı değerini sağlamanızı gerektirir.|  
|<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute>|TestCategory öznitelik, bir değer içermeyen bir kategori sağlamanıza izin verir. TestCategory özniteliği tarafından tanımlanan bir kategori TestProperty özniteliği kategorisini de olabilir.|  
|<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestPropertyAttribute>|TestProperty özniteliği ayırdedici nitelik kategori/değer çifti tanımlamanızı sağlar.|  
  
 **C++ için Framework sınama Microsoft biriminde özellikleri**  
  Bkz: [C++ için Microsoft birim testi çerçevesi kullanmayı](how-to-use-microsoft-test-framework-for-cpp.md).
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
###  <a name="BKMK_Search_and_filter_the_test_list"></a>Arama ve filtre test listesi  
 Test Gezgini filtreleri test yöntemleri, görüntüleme ve çalıştırma projelerinizde sınırlamak için kullanabilirsiniz.  
  
 Bir dizede Test Gezgini arama kutusuna yazın ve ENTER seçin, yalnızca tam adları dizeyi içeren testleri görüntülemek için test listesi filtrelenir.  
  
 Farklı bir ölçüte göre filtre uygulamak için:  
  
1.  Arama kutusunun sağındaki açılan listesini açın.  
  
2.  Yeni bir ölçütü seçin.  
  
3.  Filtre değeri tırnak işaretleri arasında girin.  
  
 ![Test Gezgini testlerinde filtre](../test/media/ute_filtertestlist.png "UTE_FilterTestList")  
  
> [!NOTE]
>  Aramalar büyük küçük harfe duyarlı ve herhangi bir kısmını ölçütleri değeri için belirtilen dize eşleşmesi.  
  
|Niteleyici|Açıklama|  
|---------------|-----------------|  
|**Ayırdedici nitelik**|Ayırdedici nitelik kategori ve değeri için eşleşme arar. Ayırdedici nitelik kategorileri ve değerleri belirlemek için söz dizimi birim test çerçevesi tarafından tanımlanır.|  
|**Proje**|Eşleşme için test proje adları arar.|  
|**Hata iletisi**|Kullanıcı tanımlı hata iletilerinin tarafından geri döndürülen başarısız aramaları için eşleşen onaylar.|  
|**Dosya yolu**|Test kaynak dosyaların tam dosya adı için eşleşen arar.|  
|**Tam adı**|Test ad alanları, sınıflar ve yöntemler tam dosya adı için eşleşen arar.|  
|**Output**|Standart çıkış (stdout) veya standart hata (stderr) için yazılmış kullanıcı tanımlı hata iletilerinin arar. Çıktı iletileri belirlemek için söz dizimi birim test çerçevesi tarafından tanımlanır.|  
|**Sonucu**|Test Gezgini kategori adları eşleştirmeleri arar: **başarısız testler**, **atlandı testleri**, **testleri geçti**.|  
  
 Bir filtre sonuçlarını kümesini dışarıda bırakmak için aşağıdaki sözdizimini kullanın:  
  
```  
FilterName:"Criteria" -FilterName:"SubsetCriteria"  
```  
  
 Örneğin,  
  
```  
FullName:"MyClass" - FullName:"PerfTest"  
```  
  
 "PerfTest" adında de dahil bu testler dışındaki kullanıcıların adı "MyClass" dahil tüm testleri döndürür.  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
##  <a name="BKMK_Create_custom_playlists"></a>Özel çalma listeleri oluşturma  
 Oluşturun ve çalıştırın veya bir grup olarak görüntülemek istediğiniz testleri listesini kaydedin. Bir çalma listesi seçtiğinizde, listedeki testler görüntülenir Test Gezgini. Bir test birden fazla çalma listesine ekleyin ve varsayılan seçtiğinizde projenizdeki tüm testleri kullanılabilir **tüm testleri** çalma listesi.  
  
 ![Bir çalma listesi seçin](../test/media/ute_playlist.png "UTE_Playlist")  
  
 **Bir çalma listesi oluşturmak için**, bir veya daha fazla testleri Test Explorer'da seçin. Bağlam menüsünde seçin **eklemek için çalma**, **NewPlaylist**. Ad ve belirttiğiniz konuma sahip dosyayı kaydedin **yeni çalma listesi oluştur** iletişim kutusu.  
  
 **Testleri çalma listesine eklemek için**, bir veya daha fazla testleri Test Explorer'da seçin. Bağlam menüsünde seçin **eklemek için çalma**ve ardından sınamaları eklemek istediğiniz çalma listesi seçin.  
  
 **Bir çalma listesi açmak için**, Test, Visual Studio menüsünde çalma listesi seçin ve son kullanılan çalma listesinden seçin veya çalma çalma konumunu ve adını belirtmek için Aç'ı seçin.  
  
 Tek tek testlerin herhangi bir sırayla çalıştırmak engelleyen bağımlılık varsa, paralel test yürütmesi ile Aç ![UTE &#95;parallelicon &#45; küçük](../test/media/ute_parallelicon-small.png "UTE_parallelicon küçük") iki durumlu düğme araç çubuğunda. Bu, tüm testleri çalıştırmak için geçen süre önemli ölçüde azaltabilir.  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
##  <a name="BKMK_Debug_and_analyze_unit_tests"></a>Hata ayıklama ve birim testleri çözümleme  
 [Birim testleri hata ayıklama](#BKMK_Debug_unit_tests) **&#124;** [Tanıla test yöntemi performans sorunlarını](#BKMK_Diagnose_test_method_performance_issues) **&#124;** [Birim testi kod kapsamını çözümleme](#BKMK_Analyzeunit_test_code_coverage)  
  
###  <a name="BKMK_Debug_unit_tests"></a>Birim testleri hata ayıklama  
 Test Gezgini, testleriniz için hata ayıklama oturumu başlatmak için kullanabilirsiniz. Kodunuz Visual Studio hata ayıklayıcısı ile sorunsuz bir şekilde Adımlama, İleri ve geri birim testleri ve test altındaki proje arasında alır. Hata ayıklama başlatmak için:  
  
1.  Visual Studio Düzenleyicisi'nde hata ayıklamak istediğiniz bir veya daha fazla test yöntemler bir kesme noktası ayarlayın.  
  
    > [!NOTE]
    >  Test yöntemleri herhangi bir sırada çalıştığından hata ayıklamak istediğiniz tüm test yöntemler kesme noktalarını ayarlayın.  
  
2.  Test Gezgini test yöntemleri seçin ve ardından **seçili Testlerde Hata Ayıkla** bağlam menüsünde.  
  
 Hata ayıklayıcı hakkında daha fazla bilgi için bkz: [Visual Studio'da hata ayıklamayı](../debugger/debugging-in-visual-studio.md).  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
###  <a name="BKMK_Diagnose_test_method_performance_issues"></a>Test yöntemi performans sorunlarını tanılamanıza  
 Test yöntemi çok fazla zaman ayırdığınız neden tanılamak için Test Gezgini'nde yöntemi seçin ve ardından bağlam menüsünden profilini seçin. Bkz: [performans Gezgini](../profiling/performance-explorer.md).  
  
###  <a name="BKMK_Analyzeunit_test_code_coverage"></a>Birim testi kod kapsamını çözümleme  
  
> [!NOTE]
>  Birim testi kod kapsamı, yalnızca Visual Studio Enterprise'da kullanılabilir.  
  
 Visual Studio kod kapsamı aracını kullanarak, birim testleri tarafından gerçekten sınanan ürün kodunuzu miktarını belirleyebilir. Kod kapsamı seçili testleri ya da bir çözümde tüm testleri çalıştırabilirsiniz.  
  
 Bir çözümde test yöntemleri için kod kapsamı çalıştırmak için:  
  
1.  Seçin **testleri** Visual Studio menüsünde ve ardından **kod kapsamını çözümleme**.  
  
2.  Alt menüsünden aşağıdaki komutlardan birini seçin:  
  
    -   **Seçili testleri** Test Gezgini'nde seçtiğiniz test yöntemleri çalıştırır.  
  
    -   **Tüm testler** Çözümdeki tüm test yöntemlerini çalıştırır.  
  
 Kod Kapsamı Sonuçları penceresi satır, işlev, sınıf, ad alanı ve modülü tarafından kullanılabilecek ürün kod bloklarını yüzdesini görüntüler.  
  
 Daha fazla bilgi için bkz: [kullanarak kod kapsamı belirleme ne kadar kodun için test](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
##  <a name="BKMK_External_resources"></a>Dış Kaynaklar  
  
###  <a name="BKMK_Guidance"></a>Kılavuzu  
 [Visual Studio 2012 - bölüm 2 ile sürekli teslimat için test etme: birim testi: iç test etme](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kodunuza birim testi](../test/unit-test-your-code.md)   
 [64 bitlik bir işlem olarak birim testi çalıştırma](../test/run-a-unit-test-as-a-64-bit-process.md)
