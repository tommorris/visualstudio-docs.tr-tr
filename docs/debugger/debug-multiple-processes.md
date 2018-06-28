---
title: Birden çok işlem hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.programs
- vs.debug.processes.attaching
- vs.debug.activeprogram
- vs.debug.attaching
- vs.debug.attachedprocesses
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: bde37134-66af-4273-b02e-05b3370c31ab
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 498c865b1a904af28386e27fe58836cb0c0e2070
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057973"
---
# <a name="debug-multiple-processes"></a>Birden çok işlem hata ayıklama
İşlemler hata ayıklamayı başlatma, işlemler arasında geçiş, bölün ve yürütme devam, kaynağı aracılığıyla adım, hata ayıklamayı durdurun ve sonlandırmak veya işlemlerini ayırmak bırakılır.  
  
##  <a name="BKMK_Configure_the_execution_behavior_of_multiple_processes"></a> Birden çok işlem yürütme davranışını yapılandırın  
 Birden çok işlem hata ayıklayıcısı'ndaki çalıştırırken, varsayılan olarak, kesme, adımlama ve durdurma hata ayıklayıcı komutlarını genellikle tüm işlemler etkiler. Örneğin, bir işlem sırasında bir kesme noktası askıya alındığında, diğer tüm işlemlerin yürütülmesi de askıya alınmış durumda. Yürütme komutları hedefler üzerinde daha fazla denetim kazanmak için bu varsayılan davranışı değiştirebilirsiniz.  
  
1.  Tıklatın **hata ayıklama > Seçenekler ve ayarlar**.  
  
2.  Üzerinde **hata ayıklama**, **genel** sayfasında, Temizle **tüm işlemler bir işlem böldüğünde bölün** onay kutusu.  
  
##  <a name="BKMK_Find_the_source_and_symbol___pdb__files"></a> Kaynak ve simge (.pdb) dosyaları bulma  
 Kaynak kodu, bir işlemin gitmek için hata ayıklayıcı kaynak dosyaları ve simge dosyaları işleminin erişimi olmalıdır. Bkz: [simge (.pdb) belirtin ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
 Bir işlem için dosyalara erişemiyorsanız, Ayrıştırılmış kod penceresini kullanarak gidebilirsiniz. Bkz: [nasıl yapılır: Ayrıştırılmış kod penceresini kullanma](../debugger/how-to-use-the-disassembly-window.md)  
  
##  <a name="BKMK_Start_multiple_processes_in_a_VS_solution__attach_to_a_process__automatically_start_a_process_in_the_debugger"></a> VS çözüm birden çok işlem başlatmak için bir işlem ekleme, bir işlem hata ayıklayıcısı'ndaki otomatik olarak Başlat  
  
-   [Visual Studio çözümü birden çok işlemlerde hata ayıklamayı Başlat](#BKMK_Start_debugging_multiple_processes_in_a_Visual_Studio_solution)  
  
-   [Başlangıç projesi değiştirme](#BKMK_Change_the_startup_project)  
  
-   [Bir çözümde belirli bir proje başlatın](#BKMK_Start_a_specific_project_in_a_solution)  
  
-   [Bir çözümde birden çok proje Başlat](#BKMK_Start_multiple_projects_in_a_solution)  
  
-   [Bir işlem ekleme](#BKMK_Attach_to_a_process)  
  
-   [Bir işlem hata ayıklayıcısı'ndaki otomatik olarak Başlat](#BKMK_Automatically_start_an_process_in_the_debugger)  
  
> [!NOTE]
>  Alt proje aynı çözümde olsa bile hata ayıklayıcısı hata ayıklaması bir işlem tarafından başlatılan bir alt işlem otomatik olarak eklemez. Bir alt işlemde hata ayıklamak için:  
>   
>  -   Başlatıldıktan sonra alt işleme iliştirilemiyor.  
>   
>      veya  
> -   Windows hata ayıklayıcısı yeni bir örneğini alt işlem otomatik olarak başlayacak şekilde yapılandırın.  
  
###  <a name="BKMK_Start_debugging_multiple_processes_in_a_Visual_Studio_solution"></a> Visual Studio çözümü birden çok işlemlerde hata ayıklamayı Başlat  
 Birden çok proje bağımsız olarak çalıştırabilirsiniz bir Visual Studio çözümünde olduğunda (hangi hata ayıklayıcı başlatıldığında projeleri seçebilirsiniz ayrı işlemlerde çalıştırılan projeleri),.  
  
 ![Bir proje için başlangıç türünü değiştirme](../debugger/media/dbg_execution_startmultipleprojects.png "DBG_Execution_StartMultipleProjects")  
  
####  <a name="BKMK_Change_the_startup_project"></a> Başlangıç projesi değiştirme  
 Çözüm başlangıç projesi değiştirmek için Çözüm Gezgini'nde proje seçin ve ardından **başlangıç projesi olarak ayarla** ve bağlam menüsünden.  
  
####  <a name="BKMK_Start_a_specific_project_in_a_solution"></a> Bir çözümde belirli bir proje başlatın  
 Varsayılan başlangıç projesi değiştirmeden bir çözüm için bir proje başlatmak için Çözüm Gezgini'nde proje seçin ve ardından **hata ayıklama** ve bağlam menüsünden. Daha sonra seçebilirsiniz **başlangıç yeni örnek** veya **Step Into yeni örnek**.  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [VS çözümde birden çok işlem başlatmak için bir işlem ekleme, bir işlem hata ayıklayıcısı'ndaki otomatik olarak Başlat](../debugger/debug-multiple-processes.md#BKMK_Start_multiple_processes_in_a_VS_solution__attach_to_a_process__automatically_start_a_process_in_the_debugger)  
  
####  <a name="BKMK_Start_multiple_projects_in_a_solution"></a> Bir çözümde birden çok proje Başlat  
  
1.  Çözüm Gezgini'nde çözümü seçin ve ardından **özellikleri** bağlam menüsünde.  
  
2.  Seçin **ortak özellikleri**, **başlangıç projesi** üzerinde **özellikleri** iletişim kutusu.  
  
3.  Değiştirmek istediğiniz her proje için ya da seçin **Başlat**, **Başlat hata ayıklama olmadan**, veya **hiçbiri**.  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [VS çözümde birden çok işlem başlatmak için bir işlem ekleme, bir işlem hata ayıklayıcısı'ndaki otomatik olarak Başlat](../debugger/debug-multiple-processes.md#BKMK_Start_multiple_processes_in_a_VS_solution__attach_to_a_process__automatically_start_a_process_in_the_debugger)  
  
###  <a name="BKMK_Attach_to_a_process"></a> Bir işlem ekleme  
 Hata ayıklayıcı ayrıca yapabilirsiniz *attach* işlemlerde Visual Studio dışında çalışan programlar uzak aygıtta çalışan programlar da dahil. Bir programa ekledikten sonra hata ayıklayıcı yürütme komutlarını kullanın, programın durumunu inceleyin ve benzeri. Yeteneğinizi program incelemek için program ile hata ayıklama bilgileri olup oluşturuldu ve programın kaynak koduna erişim olup ve ortak dil çalışma zamanı JIT derleyicisi hata ayıklama bilgileri olup izleme bağlı olarak sınırlı olabilir.  
  
 Bkz: [Attach çalışan işlemler için](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md) daha fazla bilgi için.  
  
 **Yerel makine üzerinde çalışan bir işlem ekleme**  
  
 Tıklatın **hata ayıklama > işleme iliştirilemiyor**. Üzerinde **ekleme işlemi için** iletişim kutusunda, işleminden seçin **kullanılabilir işlemler** listeleyin ve ardından **Attach**.  
  
 ![Ekle işlem iletişim kutusu](../debugger/media/dbg_attachtoprocessdlg.png "DBG_AttachToProcessDlg")  
  
###  <a name="BKMK_Automatically_start_an_process_in_the_debugger"></a> Bir işlem hata ayıklayıcısı'ndaki otomatik olarak Başlat  
 Bazı durumlarda, başka bir işlem tarafından başlatılan bir programı Başlangıç kodda hata ayıklama gerekebilir. Örnekler, hizmetleri ve özel kurulum eylemleri içerir. Bu senaryolarda, hata ayıklayıcı başlatma sahip ve uygulamanız başladığında otomatik olarak ekleyin.  
  
1.  Kayıt Defteri Düzenleyicisi'ni başlatın (**regedit.exe**).  
  
2.  Gidin **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows nt\currentversion\ımage dosya yürütme seçeneklerini** klasör.  
  
3.  Hata ayıklayıcıda başlatmak istediğiniz uygulamanın klasörü seçin.  
  
     Uygulama adı bir alt klasör olarak listelenmemişse seçin **görüntü dosyası yürütme seçenekleri** ve ardından **yeni**, **anahtar** bağlam menüsünde. Yeni anahtarı seçin, **yeniden adlandırma** kısayol menüsünde ve uygulama adı girin.  
  
4.  Uygulama klasörünün bağlam menüsünde, **yeni**, **dize değeri**.  
  
5.  Yeni değerden adını değiştirmek **yeni değer** için `debugger`.  
  
6.  Hata Ayıklayıcı girdi bağlam menüsünde seçin **Değiştir**.  
  
7.  Dize Düzenle iletişim kutusu, yazın `vsjitdebugger.exe` içinde **değer verisi** kutusu.  
  
     ![Düzenle iletişim kutusu dize](../debugger/media/dbg_execution_automaticstart_editstringdlg.png "DBG_Execution_AutomaticStart_EditStringDlg")  
  
 ![Otomatik hata ayıklayıcısını başlatma girişi regedit.exe dosyasındaki](../debugger/media/dbg_execution_automaticstart_result.png "DBG_Execution_AutomaticStart_Result")  
  
##  <a name="BKMK_Switch_processes__break_and_continue_execution__step_through_source"></a> İşlemler geçiş, bölme ve yürütme, kaynak adıma devam edin  
  
-   [İşlemler arasında geçiş](#BKMK_Switch_between_processes)  
  
-   [Bölme, adım ve devam et komutlarını](#BKMK_Break__step__and_continue_commands)  
  
###  <a name="BKMK_Switch_between_processes"></a> İşlemler arasında geçiş  
 Hata ayıklama yaptığınız ancak herhangi bir anda yalnızca bir işlem hata ayıklayıcısı'ndaki etkin olduğu durumlarda, birden çok işlem ekleyebilirsiniz. Etkin ayarlayabilirsiniz veya *geçerli* veya'te hata ayıklama konumu araç işlem **işlemleri** penceresi. İşlemler arasında geçiş yapmak için her iki işlem kesme modunda olması gerekir.  
  
 **Geçerli işlem ayarlamak için**  
  
-   Hata ayıklama konumu araç çubuğunda seçin **işlem** görüntülemek için **işlem** liste kutusu. Geçerli işlem olarak atamak istediğiniz işlemi seçin.  
  
     ![İşlemler arasında geçiş yapma](../debugger/media/dbg_execution_switchbetweenmodules.png "DBG_Execution_SwitchBetweenModules")  
  
     Varsa **hata ayıklama konumu** araç çubuğu görünür durumda değilse, seçin **Araçları**, **Özelleştir**. Üzerinde **araç çubukları** sekmesinde, seçin **hata ayıklama konumu**.  
  
-   Açık **işlemleri** penceresi (kısayol **Ctrl + Alt + Z**), geçerli işlem olarak ayarlamak istediğiniz işlemi bulun ve çift tıklayın.  
  
     ![İşlemler penceresi](../debugger/media/dbg_processeswindow.png "DBG_ProcessesWindow")  
  
     Geçerli işlem sarı bir ok işaretlenir.  
  
 Bir projeye geçiş geçerli işlem için hata ayıklama amacıyla ayarlar. Yalnızca geçerli işlem tüm sürüm komutları etkileyen ve görüntülediğiniz tüm hata ayıklayıcı penceresini geçerli işlem için durumu gösterilir.  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [geçiş işlemleri, bölme ve yürütme, kaynak adıma devam edin](../debugger/debug-multiple-processes.md#BKMK_Switch_processes__break_and_continue_execution__step_through_source)  
  
###  <a name="BKMK_Break__step__and_continue_commands"></a> Bölme, adım ve devam et komutlarını  
  
> [!NOTE]
>  Varsayılan olarak, sonu devam edin ve adım hata ayıklayıcı komutlarını ayıklanacak tüm işlemler etkiler. Bu davranışı değiştirmek için bkz: [birden çok işlem yürütme davranışını yapılandırın](#BKMK_Configure_the_execution_behavior_of_multiple_processes)  
  
|**Komutu**|**Tüm işlemler bir işlem böldüğünde bölün**<br /><br /> Checked (varsayılan)|**Tüm işlemler bir işlem böldüğünde bölün**<br /><br /> Temizlenmiş|  
|-|-|-|  
|**Hata ayıklama** menüsü:<br /><br /> -   **Tüm bölün**|Tüm işlemler bölün.|Tüm işlemler bölün.|  
|**Hata ayıklama** menüsü:<br /><br /> -   **Devam etmek**|Tüm işlemler sürdürün.|Tüm bekleyen işlemleri devam edin.|  
|**Hata ayıklama** menüsü:<br /><br /> -   **Girme**<br />-   **Adımlama**<br />-   **Dışarı Adım**|Tüm işlemler geçerli işlem adımları sırasında çalıştırın.<br /><br /> Ardından tüm işlemler bölün.|Geçerli işlem adımları.<br /><br /> Askıya alınan işlemler sürdürün.<br /><br /> Çalışan işlemleri devam edin.|  
|**Hata ayıklama** menüsü:<br /><br /> -   **Geçerli işlem adımla**<br />-   **Geçerli işlem Adımlama**<br />-   **Geçerli işlem adım**|Yok|Geçerli işlem adımları.<br /><br /> Diğer işlemlerin (askıya alındı veya çalıştıran) mevcut durumlarına korur.|  
|Kaynağı penceresi<br /><br /> -   **Kesme noktası**|Tüm işlemler bölün.|Yalnızca kaynak penceresi işlem sonu.|  
|Kaynak penceresi bağlam menüsü:<br /><br /> -   **İmleci çalıştırın**<br /><br /> Kaynak penceresini geçerli işlemde olması gerekir.|Kaynak pencere işlemi için imleç çalıştırır ve ardından sonları yaparken tüm işlemleri çalıştırın.<br /><br /> Sonra diğer tüm işlemlerin bölün.|Kaynak pencere işlemi için imleç çalışır.<br /><br /> Diğer işlemlerin (askıya alındı veya çalıştıran) mevcut durumlarına korur.|  
|**İşlemler** penceresi bağlam menüsü:<br /><br /> -   **Kesme işlemi**|Yok|İşlem sonları seçili.<br /><br /> Diğer işlemlerin (askıya alındı veya çalıştıran) mevcut durumlarına korur.|  
|**İşlemler** penceresi bağlam menüsü:<br /><br /> -   **İşleme devam edin**|Yok|Seçili işlem sürdürür.<br /><br /> Diğer işlemlerin (askıya alındı veya çalıştıran) mevcut durumlarına korur.|  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [geçiş işlemleri, bölme ve yürütme, kaynak adıma devam edin](../debugger/debug-multiple-processes.md#BKMK_Switch_processes__break_and_continue_execution__step_through_source)  
  
##  <a name="BKMK_Stop_debugging__terminate_or_detach_from_processes"></a> Hata ayıklamayı durdurun, sonlandırma veya işlemlerini ayırma  
  
-   [Durdur, sonlandırmak ve komutları ayırma](#BKMK_Stop__terminate__and_detach_commands)  
  
 Varsayılan olarak, seçtiğinizde, **hata ayıklama**, **durdurma hata ayıklama** birden çok işlem hata ayıklayıcısı'ndaki açık olduğunda, hata ayıklayıcı sonlandırır veya işlemin nasıl açıldığı bağlı olarak tüm işlemlerden ayırır Hata Ayıklayıcı:  
  
-   Geçerli işlem hata ayıklayıcısı'ndaki başlatıldı, bu işlem sonlandırıldı.  
  
-   Geçerli işlem hata ayıklayıcısı ekli, hata ayıklayıcı işleminden ayırır ve çalışan işlemi bırakır.  
  
 Örneğin, bir Visual Studio çözümü işleminden hata ayıklama başlatırsanız, çalışmakta olan başka bir işleme ekleyin ve ardından **durdurma hata ayıklama**, hata ayıklama oturumu sona erer Visual Studio'da başlatıldığından işlemi iliştirdiğiniz işlem çalışır durumda kalır ancak, sonlandırılır. Hata ayıklamayı durdurun şeklini denetlemek için aşağıdaki yordamları kullanabilirsiniz.  
  
> [!NOTE]
>  **Tüm işlemler bir işlem böldüğünde bölün** seçeneği hata ayıklama veya sonlandırma ve işlemlerini ayırma durdurma etkilemez.  
  
 **Tek bir işlem durdurma hata ayıklama nasıl etkilediğini değiştirmek için**  
  
-   Açık **işlemleri** penceresi (kısayol **Ctrl + Alt + Z**). Bir işlem seçin ve ardından seçin veya temizleyin **Detach hata ayıklama durduğunda** onay kutusu.  
  
###  <a name="BKMK_Stop__terminate__and_detach_commands"></a> Durdur, sonlandırmak ve komutları ayırma  
  
|**Komutu**|**Açıklama**|  
|-|-| 
|**Hata ayıklama** menüsü:<br /><br /> -   **Hata ayıklamayı durdurun**|Davranış tarafından değiştirilmediği sürece **işlemleri** penceresi **Detach durakları hata ayıklama sırasında** seçeneği:<br /><br /> 1.  Hata ayıklayıcı tarafından başlatılan işlemleri sonlandırılır.<br />2.  Bağlı işlemler hata ayıklayıcı'dan ayrılır.|  
|**Hata ayıklama** menüsü:<br /><br /> -   **Tüm Sonlandır**|Tüm işlemleri sonlandırılır.|  
|**Hata ayıklama** menüsü:<br /><br /> -   **Tüm ayırma**|Hata ayıklayıcı tüm işlemlerini ayırır.|  
|**İşlemler** penceresi bağlam menüsü:<br /><br /> -   **İşlem ayırma**|Hata ayıklayıcı seçili işleminden ayırır.<br /><br /> Diğer işlemlerin (askıya alındı veya çalıştıran) mevcut durumlarına korur.|  
|**İşlemler** penceresi bağlam menüsü:<br /><br /> -   **İşlem sonlandırma**|Seçili işlem sonlandırıldı.<br /><br /> Diğer işlemlerin (askıya alındı veya çalıştıran) mevcut durumlarına korur.|  
|**İşlemler** penceresi bağlam menüsü:<br /><br /> -   **Durakları hata ayıklama sırasında ayırma**|Davranışını değiştirir **hata ayıklama**, **durdurma hata ayıklama** seçili işlem için:<br /><br /> -Checked: Hata ayıklayıcı işleminden ayırır.<br />-Temizlenmiş: İşlem sonlandırıldı.|  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [hata ayıklamayı durdurun, sonlandırma veya işlemlerini ayırma](../debugger/debug-multiple-processes.md#BKMK_Stop_debugging__terminate_or_detach_from_processes)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simge (.pdb) belirtin ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [Çalıştırma işlemine iliştirme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Hata ayıklayıcısı ile kodlarda gezinme](../debugger/navigating-through-code-with-the-debugger.md)   
 [Tam zamanında hata ayıklama](../debugger/just-in-time-debugging-in-visual-studio.md)   
 [Birden çok iş parçacıklı uygulamalarda hata ayıklama](../debugger/debug-multithreaded-applications-in-visual-studio.md)