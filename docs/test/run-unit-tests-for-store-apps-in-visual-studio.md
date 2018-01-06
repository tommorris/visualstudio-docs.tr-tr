---
title: "Visual Studio'da UWP uygulamaları için birim testleri çalıştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a6f5b32-bfce-4a63-81e9-02d54c592539
caps.latest.revision: "12"
ms.author: douge
manager: douge
ms.workload: uwp
ms.openlocfilehash: ad5a81a8b80ffb5a25a04d3aa83811e90c2785e9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="run-unit-tests-for-uwp-apps-in-visual-studio"></a>Visual Studio'da UWP uygulamaları için birim testleri çalıştırma
Bu konuda Microsoft Visual Studio Test Gezgini ile birim testleri çalıştırırken açıklar  
  
> [!NOTE]
>  Bu bölümdeki konular, Visual Studio Express için Windows 8 işlevselliğini açıklar. Visual Studio Community, Enterprise ve Professional birim testi için ek özellikler sağlar.  
>   
>  -   Bir eklenti bağdaştırıcı için Microsoft Test Gezgini oluşturduğu tüm üçüncü taraf veya açık kaynak birim testi çerçevesi kullanın. Ayrıca, çözümlemek ve testleriniz için kod kapsamı bilgilerini görüntüler.  
> -   Testlerinizi her yapıdan sonra çalıştırın. Microsoft Fakes, bir yalıtım framework sistemi ve üçüncü taraf işlevselliği için test kodu getirilmesiyle testlerinizi kendi kodlarına odaklanmasını yönetilen kod için de kullanabilirsiniz.  
>   
>  Daha fazla bilgi için bkz: [Birim Test kodunuzu](../test/unit-test-your-code.md) MSDN Kitaplığı'nda.  
  
##  <a name="BKMK_In_this_topic"></a>Bu konudaki  
 [Birim testi çerçevelerini ve test projeleri](#BKMK_Unit_test_frameworks_and_test_projects)  
  
 [Test Gezgini testlerini çalıştırma](#BKMK_Running_tests_in_Test_Explorer)  
  
-   [Testleri çalıştırma](#BKMK_Running_tests)  
  
 [Test sonuçlarını görüntüleme](#BKMK_Viewing_test_results)  
  
-   [Görüntüleme test ayrıntıları](#BKMK_Viewing_test_details)  
  
-   [Bir test yönteminin kaynak kodu görüntüleme](#BKMK_Viewing_the_source_code_of_a_test_method)  
  
 [Test listesini düzenleme](#BKMK_Organizing_the_test_list)  
  
-   [Testleri gruplandırma](#BKMK_Grouping_tests)  
  
-   [Arama ve test listesini filtreleme](#BKMK_Searching_and_filtering_the_test_list)  
  
 [Hata ayıklama birim testleri](#BKMK_Debugging_unit_tests)  
  
##  <a name="BKMK_Unit_test_frameworks_and_test_projects"></a>Birim testi çerçevelerini ve test projeleri  
 UWP uygulamalar için Visual Studio Express, yönetilen ve yerel C++ kodu için Microsoft birim test çerçevelerini içerir. Test Gezgini, bir çözümde birden çok test projelerden ve üretim kodu projeleri parçası olan test sınıflardan testleri çalıştırabilirsiniz. Visual C# ve Visual Basic birim test çerçevelerini veya testi projelerini Visual C++ herhangi bir bileşimini olabilir. .NET Framework için test altındaki kodun yazıldığında test projesinin hedef kod dilinin bağımsız olarak herhangi bir .NET Framework dil yazılabilir. Yerel C/C++ kod projeleri, C++ birim test çerçevesi kullanılarak test edilebilir.  
  
##  <a name="BKMK_Running_tests_in_Test_Explorer"></a>Test Gezgini testlerini çalıştırma  
 Test projesi derlerken, testleri Test Gezgini'nde görünür. Test Gezgini görünür durumda değilse, seçin **Test** Visual Studio menüsünde, **Windows**ve ardından **Test Gezgini**.  
  
 ![Birim Test Gezgini](../ide/media/ute_failedpassednotrunsummary.png "UTE_FailedPassedNotRunSummary")  
  
 Test Gezgini çalıştırmak, yazma ve testleri yeniden çalıştırmak gibi sonuçları varsayılan gruplar halinde görüntülenir. **başarısız testler**, **testleri geçti**, **atlandı testleri** ve  **Testler değil**. Test Gezgini testlerinizi grupları şekilde değiştirebilirsiniz.  
  
 Bulma, düzenleme ve testleri Test Gezgini araç çubuğundan çalışan işin çoğunu gerçekleştirebilirsiniz.  
  
 ![Test Gezgini araç çubuğundan testler](../test/media/ute_toolbar.png "UTE_ToolBar")  
  
###  <a name="BKMK_Running_tests"></a>Testleri çalıştırma  
 Bir grup veya seçtiğiniz testleri kümesi tüm testleri Çözümdeki tüm testleri çalıştırın. Aşağıdakilerden birini yapın:  
  
-   Bir çözümde tüm testleri çalıştırmak için tercih **tümünü Çalıştır**.  
  
-   Bir varsayılan grubundaki tüm testleri çalıştırmak için tercih **Çalıştır...**  ve grubun menüsünde'i seçin.  
  
-   Seçilen testi için kısayol menüsünü açın ve ardından çalıştırmak istediğiniz tek tek testlerin seçin **seçili Testleri Çalıştır**.  
  
 Test Gezgini penceresinin üst geçişi/hata çubuğu Testleri Çalıştır animasyon eklenir. Tüm testleri geçirilen ya da herhangi bir test başarısız olursa kırmızı kapatır testi sonuç geçişi/hata çubuğu yeşil olur.  
  
##  <a name="BKMK_Viewing_test_results"></a>Test sonuçlarını görüntüleme  
 Test Gezgini çalıştırmak, yazma ve testleri yeniden çalıştırmak gibi sonuçları gruplar halinde görüntülenir. **başarısız testler**, **testleri geçti**, **atlandı testleri** ve **çalışmıyor Testleri**. Test Gezgini görüntüler altındaki ayrıntılar bölmesini test özetini çalıştırın.  
  
###  <a name="BKMK_Viewing_test_details"></a>Görüntüleme test ayrıntıları  
 Bir test ayrıntılarını görüntülemek için test'i seçin.  
  
 Test Ayrıntılar bölmesinde aşağıdaki bilgileri görüntüler:  
  
-   Kaynak dosya adı ve test yöntemi satır sayısı.  
  
-   Test durumu.  
  
-   Test yöntemi sürdüğü geçen süre.  
  
 Sınama başarısız olursa, Ayrıntılar bölmesinde de görüntüler:  
  
-   Test için birim test çerçevesi tarafından döndürülen ileti.  
  
-   Yığın izleme testi başarısız zaman.  
  
###  <a name="BKMK_Viewing_the_source_code_of_a_test_method"></a>Bir test yönteminin kaynak kodu görüntüleme  
 Visual Studio Düzenleyicisinde test yöntemi için kaynak kodunu görüntülemek için test seçin ve ardından **açık Test** kısayol menüsünde (klavye: F12).  
  
##  <a name="BKMK_Organizing_the_test_list"></a>Test listesini düzenleme  
  
###  <a name="BKMK_Grouping_tests"></a>Testleri gruplandırma  
 Varsayılan olarak, Test Gezgini testlerinizi alt düğümleri olarak görüntüler **başarısız testler**, **testleri geçti**, **atlandı testleri** ve **testleri değil Çalıştır**.  
  
|||  
|-|-|  
|![Test Gezgini grubu düğmesini](../test/media/ute_groupby_btn.png "UTE_GroupBy_btn")|Bunları yürütme süresini tarafından testlerinizi gruplamak için açık **Group By** listesinde ve seçin **süresi**. Seçin **Test sonucu** özgün gruplandırmasına geçiş yapmak için.|  
  
###  <a name="BKMK_Searching_and_filtering_the_test_list"></a>Arama ve test listesini filtreleme  
 Çok sayıda testleri olduğunda tarafından belirtilen dize listesini filtrelemek için Test Gezgini arama kutusuna yazabilirsiniz. Arama dizesini girin önce Filtre listeden seçerek belirli dizeleri türleri için filtre kısıtlayabilirsiniz.  
  
 ![Arama filtresi kategorileri](../test/media/ute_searchfilter.png "UTE_SearchFilter")  
  
##  <a name="BKMK_Debugging_unit_tests"></a>Hata ayıklama birim testleri  
 Test Gezgini, testleriniz için hata ayıklama oturumu başlatmak için kullanabilirsiniz. Kodunuz Visual Studio hata ayıklayıcısı ile sorunsuz bir şekilde Adımlama, İleri ve geri birim testleri ve test altındaki proje arasında alır. Hata ayıklama başlatmak için:  
  
1.  Visual Studio Düzenleyicisi'nde hata ayıklamak istediğiniz bir veya daha fazla test yöntemler bir kesme noktası ayarlayın.  
  
    > [!NOTE]
    >  Test yöntemleri herhangi bir sırada çalıştığından hata ayıklamak istediğiniz tüm test yöntemler kesme noktalarını ayarlayın.  
  
2.  Test Gezgini test yöntemleri seçin ve ardından **seçili Testlerde Hata Ayıkla** kısayol menüsünde.  
  
 Hata ayıklayıcı hakkında daha fazla bilgi için bkz: [Visual Studio'da hata ayıklamayı](../debugger/debugging-in-visual-studio.md).
