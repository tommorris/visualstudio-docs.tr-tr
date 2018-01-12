---
title: "Tetiklemek nasıl askıya alma, sürdürme ve UWP uygulamaları hata ayıklama sırasında arka plan olaylarını | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.background_task_activate_failure
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 824ff3ca-fedf-4cf5-b3e2-ac8dc82d40ac
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 4a62f02d98ed06df4a3eea1b3f253f5e91ff7115
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-trigger-suspend-resume-and-background-events-while-debugging-uwp-apps-in-visual-studio"></a>Tetiklemek nasıl askıya alma, sürdürme ve Visual Studio UWP uygulamalarında hata ayıklama sırasında arka plan olayları
Ne zaman değil ayıkladığınız, Windows **işlem yaşam süresi Management** (PLM) denetimleri, uygulamanızın yürütme durumu — başlatma, askıya alma, sürdürme ve uygulama yanıt kullanıcı eylemleri ve aygıtın durumu olarak sonlandırılıyor. Hata ayıklama yaptığınız Windows bu etkinleştirme olayları devre dışı bırakır. Bu konu, bu olayları hata ayıklayıcısında yangın açıklar.  
  
 Bu konu ayrıca hata ayıklama açıklar **arka plan görevleri**. Arka plan görevleri bile, uygulama çalışmıyorken belirli işlemlerin bir arka plan işlemi gerçekleştirmenize olanak sağlar. Hata ayıklama modunda uygulamanızı koymak için hata ayıklayıcı kullanabilirsiniz ve ardından — kullanıcı arabirimini başlatmadan — başlatın ve hata ayıklama arka plan görevi.  
  
 İşlem ömrü yönetimi ve arka plan görevleri hakkında daha fazla bilgi için bkz: [devam ettirme, başlatma ve çoklu](/windows/uwp/launch-resume/index).  
  
##  <a name="BKMK_In_this_topic"></a>Bu konudaki  
 [Tetikleyici işlem yaşam süresi Management olayları](#BKMK_Trigger_Process_Lifecycle_Management_events)  
  
 [Tetikleyici arka plan görevleri](#BKMK_Trigger_background_tasks)  
  
-   [Tetikleyici bir standart hata ayıklama oturumu bir arka plan görev olayı](#BKMK_Trigger_a_background_task_event_from_a_standard_debug_session)  
  
-   [Uygulama çalışmıyorken tetikleyicinin arka plan görevi](#BKMK_Trigger_a_background_task_when_the_app_is_not_running)  
  
 [İşlem yaşam süresi Management olaylarını tetiklemek ve yüklü bir uygulamadan görevleri arka plan](#BKMK_Trigger_Process_Lifetime_Management_events_and_background_tasks_from_an_installed_app)  
  
 [Arka plan görevi etkinleştirmesi hatalarını tanılama](#BKMK_Diagnosing_background_task_activation_errors)  
  
##  <a name="BKMK_Trigger_Process_Lifecycle_Management_events"></a>Tetikleyici işlem yaşam süresi Management olayları  
 Kullanıcı veya Windows düşük güç durumu girdiğinde çıktığınızda geçtiğinde Windows uygulamanızı askıya alabilirsiniz. Yanıt verebilirsiniz `Suspending` olay ilgili uygulama ve kullanıcı verilerini kalıcı depolama alanına kaydetmek ve kaynakları serbest bırakmak için. Ne zaman bir uygulama sürdürüldü gelen **askıya** durumunda, geçirilmeden **çalıştıran** durum ve onu askıya alındığında, bulunduğu gelen devam eder. Yanıt verebilirsiniz `Resuming` geri yüklemek veya uygulama durumu ve kaynakları geri kazanmak için olay.  
  
 Mümkün olduğunca bellekte kadar askıya alınmış uygulamaları korumak Windows çalışır ancak bellekte tutmak için yeterli kaynak yoksa Windows uygulamanızı sonlandırabilir. Bir kullanıcı aynı zamanda açıkça uygulamanızı kapatabilirsiniz. Kullanıcı bir uygulama kapattı belirtmek için özel olay yok.  
  
 Visual Studio Hata Ayıklayıcısı'ndaki, el ile askıya alma, sürdürme ve uygulamalarınızı hata ayıklama işlemi yaşam döngüsü olayları sonlandırılacak. Bir işlem yaşam döngüsü olayı hata ayıklamak için:  
  
1.  Bir breakpooint hata ayıklamak istediğiniz olay işleyici ayarlayın.  
  
2.  Tuşuna **F5** hata ayıklama başlatılamıyor.  
  
3.  Üzerinde **hata ayıklama konumu** araç yangın istediğiniz olayı seçin:  
  
     ![Askıya alma, sürdürme, sonlandırmak ve arka plan görevleri](../debugger/media/dbg_suspendresumebackground.png "DBG_SuspendResumeBackground")  
  
     Unutmayın **askıya alma ve sonlandırmak** uygulama kapatır ve hata ayıklama oturumu sona erer.  
  
##  <a name="BKMK_Trigger_background_tasks"></a>Tetikleyici arka plan görevleri  
 Herhangi bir uygulama bile uygulama çalışmıyorken bazı sistem olaylarına, yanıt için bir arka plan görevi kaydedebilirsiniz. Arka plan görevlerini doğrudan kullanıcı arabirimini güncelleştirir kod çalıştıramaz; Bunun yerine, bunlar bölme güncelleştirmeleri, rozet güncelleştirmeleri ve bildirimleri kullanıcı bilgilerini gösterir. Daha fazla bilgi için bkz: [arka plan görevleri ile uygulamanızı destekleme](http://msdn.microsoft.com/en-us/4c7bb148-eb1f-4640-865e-41f627a46e8e)  
  
 Hata Ayıklayıcı'dan uygulamanız için arka plan görevleri Başlat olayları tetikleyebilir.  
  
> [!NOTE]
>  Hata ayıklayıcı aygıt durum değişikliği belirten olayları gibi veri içermeyen olayları tetikleyebilir. El ile kullanıcı girişi veya diğer veri gerektiren arka plan görevlerini tetikleyin gerekir.  
  
 Uygulamanızı çalışır durumda değilken bir arka plan görev olayı tetiklemek için en gerçekçi yoludur. Ancak, standart hata ayıklama oturumunda olay tetikleme de desteklenir.  
  
###  <a name="BKMK_Trigger_a_background_task_event_from_a_standard_debug_session"></a>Tetikleyici bir standart hata ayıklama oturumu bir arka plan görev olayı  
  
1.  Arka plan görevi kodda hata ayıklamak istediğiniz bir kesme noktası ayarlayın.  
  
2.  Tuşuna **F5** hata ayıklama başlatılamıyor.  
  
3.  Üzerinde olaylar listesinden **hata ayıklama konumu** araç, başlatmak istediğiniz arka plan görevi seçin.  
  
     ![Askıya alma, sürdürme, sonlandırmak ve arka plan görevleri](../debugger/media/dbg_suspendresumebackground.png "DBG_SuspendResumeBackground")  
  
###  <a name="BKMK_Trigger_a_background_task_when_the_app_is_not_running"></a>Uygulama çalışmıyorken tetikleyicinin arka plan görevi  
  
1.  Arka plan görevi kodda hata ayıklamak istediğiniz bir kesme noktası ayarlayın.  
  
2.  Başlangıç projesi için hata ayıklama özellik sayfası açın. Çözüm Gezgini'nde proje seçin. Üzerinde **hata ayıklama** menüsünde seçin **özellikleri**.  
  
     C++ projeleri için genişletmeniz gerekebilir **yapılandırma özellikleri** ve ardından **hata ayıklama**.  
  
3.  Aşağıdakilerden birini yapın:  
  
    -   Visual C# ve Visual Basic projeleri seçin **değil başlatın, ancak başlatıldığında kodum hata ayıklama**  
  
         ![C &#35; &#47; VB hata ayıklama başlatma uygulama özelliği](../debugger/media/dbg_csvb_dontlaunchapp.png "DBG_CsVb_DontLaunchApp")  
  
    -   JavaScript ve Visual C++ projeleri için Seç **Hayır** gelen **uygulamayı Başlat** listesi.  
  
         ![C &#43; &#43; &#47; Uygulama hata ayıklama özelliği VB başlatma](../debugger/media/dbg_cppjs_dontlaunchapp.png "DBG_CppJs_DontLaunchApp")  
  
4.  Tuşuna **F5** uygulama hata ayıklama modunda yerleştirilecek. Not **işlem** listesini **hata ayıklama konumu** araç hata ayıklama modunda olduğunu belirtmek için uygulama paketi adını görüntüler.  
  
     ![Arka plan görevi işlem listesi](../debugger/media/dbg_backgroundtask_processlist.png "DBG_BackgroundTask_ProcessList")  
  
5.  Üzerinde olaylar listesinden **hata ayıklama konumu** araç, başlatmak istediğiniz arka plan görevi seçin.  
  
     ![Askıya alma, sürdürme, sonlandırmak ve arka plan görevleri](../debugger/media/dbg_suspendresumebackground.png "DBG_SuspendResumeBackground")  
  
##  <a name="BKMK_Trigger_Process_Lifetime_Management_events_and_background_tasks_from_an_installed_app"></a>İşlem yaşam süresi Management olaylarını tetiklemek ve yüklü bir uygulamadan görevleri arka plan  
 Ayıklayıcıya yüklü olan bir uygulama yüklemek için yüklü uygulama hata ayıklama iletişim kutusunu kullanın. Örneğin, Microsoft Store yüklü olduğu bir uygulama hatalarını ayıklama veya uygulama için kaynak dosyaları, ancak uygulama için bir Visual Studio projesini değil varsa, bir uygulama hata ayıklama. Hata ayıklama modunda Visual Studio makinede veya uzak cihazda ya da hata ayıklama modunda çalıştırılması ancak değil başlatmak için uygulama ayarlamak için bir uygulama Başlat yüklü uygulama hata ayıklama iletişim kutusu sağlar. Bkz: **Hata Ayıklayıcısı'ndaki yüklü bir uygulamayı Başlat** bölümünü [UWP uygulamasında hata ayıklama oturumu Başlat](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md#BKMK_Start_an_installed_app_in_the_debugger).
  
 Uygulama ayıklayıcıya yüklendikten sonra yukarıda açıklanan yordamlardan herhangi birini kullanabilirsiniz.  
  
##  <a name="BKMK_Diagnosing_background_task_activation_errors"></a>Arka plan görevi etkinleştirmesi hatalarını tanılama  
 Windows Olay Görüntüleyicisi'nde tanılama günlükleri arka plan altyapısı tanılamak ve arka plan görev hataları gidermek için kullanabileceğiniz ayrıntılı bilgiler içeriyor. Günlüğünü görüntülemek için:  
  
1.  Olay Görüntüleyicisi'ni uygulamasını açın.  
  
2.  İçinde **Eylemler** bölmesinde seçin **Görünüm** ve emin olun **Analitik ve hata ayıklama günlüklerini göster** denetlenir.  
  
3.  Üzerinde **Olay Görüntüleyicisi'ni (yerel)** ağaç, düğümleri genişletin **uygulama ve hizmet günlükleri** > **Microsoft** > **Windows**   >  **BackgroundTasksInfrastructure**.  
  
4.  Seçin **tanılama** günlük.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio ile UWP uygulamaları test etme](../test/testing-store-apps-with-visual-studio.md)   
 [Visual Studio uygulamalarında hata ayıklama](../debugger/debug-store-apps-in-visual-studio.md)   
 [Uygulama yaşam döngüsü](http://msdn.microsoft.com/en-us/53cdc987-c547-49d1-a5a4-fd3f96b2259d)   
 [Başlatma, sürdürme ve çoklu](http://msdn.microsoft.com/en-us/04307b1b-05af-46a6-b639-3f35e297f71b)