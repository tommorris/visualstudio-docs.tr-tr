---
title: "Visual Studio'da (VB, C#, C++ ve XAML) bir UWP uygulaması için hata ayıklama oturumu Başlat | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.IVCAppHostRemoteDebugPageObject.MachineName
- VC.Project.IVCAppHostRemoteDebugPageObject.BreakpointBehavior
- VC.Project.IVCAppHostLocalDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostTetheredDebugPageObject.DebuggerType
- VC.Project.IVCAppHostLocalDebugPageObject.BreakpointBehavior
- VC.Project.IVCAppHostRemoteDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostRemoteDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostLocalDebugPageObject.DebuggerType
- VC.Project.IVCAppHostSimulatorDebugPageObject.DebuggerType
- ImmersiveProjects.Properties.Debug
- VC.Project.IVCAppHostTetheredDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostSimulatorDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostSimulatorDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCAppHostLocalDebugPageObject.LaunchApplication
- VC.Project.IVCAppHostLocalDebugPageObject.AllowLocalNetworkLoopback
- AppPackage.Properties.Debug
- VC.Project.IVCAppHostRemoteDebugPageObject.Authentication
- VC.Project.IVCAppHostRemoteDebugPageObject.DebuggerType
- VC.Project.IVCAppHostSimulatorDebugPageObject.BreakpointBehavior
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 66ec0e79-8261-4c19-a618-3fd1b3f71bbd
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: d99458d8afd6d4789d7827404f38d6dcfea76012
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="start-a-debugging-session-for-a-uwp-app-in-visual-studio-vb-c-c-and-xaml"></a>Visual Studio'da (VB, C#, C++ ve XAML) bir UWP uygulaması için hata ayıklama oturumu Başlat
![Windows ve Windows Phone için geçerlidir](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 Bu konu, XAML ve Visual C++, Visual C# veya Visual Basic yazılmış UWP uygulamaları için hata ayıklama oturumu başlatmak açıklar. Bir uygulama hata ayıklama hem hata ayıklama oturumu yapılandırma ve uygulamayı başlatmak için yöntem seçme içerir.  
  
> [!NOTE]
>  JavaScript ve HTML içinde yazılmış uygulamalar için bkz [bir hata ayıklama oturumu (JavaScript) Başlangıç](../debugger/start-a-debugging-session-for-store-apps-in-visual-studio-javascript.md).  
  
##  <a name="BKMK_In_this_topic"></a>Bu konudaki  
 [En kolay yolu hata ayıklamayı Başlat](#BKMK_The_easy_way_to_start_debugging)  
  
 [Hata ayıklama oturumu yapılandırın](#BKMK_Configure_the_debugging_session)  
  
-   [Proje için hata ayıklama özellik sayfasını açın](#BKMK_Open_the_debugging_property_page_for_the_project)  
  
-   [Yapı yapılandırma seçeneklerini seçin](#BKMK_Choose_the_build_configuration_options)  
  
-   [Dağıtım hedefi seçin](#BKMK_Choose_the_deployment_target)  
  
-   [Kullanmak için hata ayıklayıcı seçin](#BKMK_Choose_the_debugger_to_use)  
  
-   [(İsteğe bağlı) Hata ayıklama oturumu başlatma gecikmesi](#BKMK__Optional__Delay_starting_the_debug_session)  
  
-   [(İsteğe bağlı) Ağ geri döngüler devre dışı bırak](#BKMK__Optional__Disable_network_loopbacks)  
  
-   [(İsteğe bağlı) Hata ayıklama başlattığınızda uygulamayı yeniden yükleyin.](#BKMK__Optional__Reinstall_the_app_when_you_start_debugging)  
  
-   [(İsteğe bağlı) Uzaktan hata ayıklayıcı başlatmak için kimlik doğrulama gereksinimini devre dışı bırak](#BKMK__Optional__Disable_authentication_requirement_to_start_the_remote_debugger)  
  
 [Hata ayıklama oturumu Başlat](#BKMK_Start_the_debugging_session)  
  
-   [(F5) hata ayıklamayı Başlat](#BKMK_Start_debugging__F5_)  
  
-   [(F5) hata ayıklamayı Başlat ancak uygulama başlatma gecikmesi](#BKMK_Start_debugging__F5__but_delay_the_app_start)  
  
-   [Hata Ayıklayıcısı'ndaki yüklü bir uygulamayı Başlat](#BKMK_Start_an_installed_app_in_the_debugger)  
  
-   [Hata ayıklayıcıyı çalışan bir uygulama Ekle](#BKMK_Attach_the_debugger_to_a_running_app_)  
  
    -   [Hata ayıklama modunda çalıştırmak için uygulamayı Ayarla](#BKMK_Set_the_app_to_run_in_debug_mode)  
  
    -   [Hata ayıklayıcıyı Ekle](#BKMK_Attach_the_debugger)  
  
##  <a name="BKMK_The_easy_way_to_start_debugging"></a>En kolay yolu hata ayıklamayı Başlat  
  
1.  Uygulama çözümü Visual Studio'da açın.  
  
2.  F5'i seçin.  
  
 Visual Studio oluşturur ve hata ayıklayıcısı ekli uygulamayı başlatır. Yürütme bir kesme noktası ulaşıldığında, el ile bir işlenen kaydını özel durum oluştu, yürütme, askıya veya uygulama sona kadar devam eder. Daha fazla bilgi için bkz: [(Xaml ve C#) bir hata ayıklama oturumunda gezinme](../debugger/navigate-a-debugging-session-in-visual-studio-xaml-and-csharp.md) .  
  
##  <a name="BKMK_Configure_the_debugging_session"></a>Hata ayıklama oturumu yapılandırın  
  
###  <a name="BKMK_Open_the_debugging_property_page_for_the_project"></a>Proje için hata ayıklama özellik sayfasını açın  
  
1.  Çözüm Gezgini'nde proje seçin. Kısayol menüsünden seçin **özellikleri**.  
  
2.  Bu proje için hata ayıklama özellik sayfası açmak için yapın:  
  
    -   Uygulamalar, Visual C# ve Visual Basic için **hata ayıklama**.  
  
         ![C &#35; &#47; VB proje hata ayıklama özellik sayfası](../debugger/media/dbg_csvb_debugpropertypage.png "DBG_CsVb_DebugPropertyPage")  
  
    -   Visual C++ uygulamaları için Genişlet **yapılandırma özellikleri** düğümünü ve ardından **hata ayıklama**.  
  
         ![C# 43; &#43; UWP uygulamasında hata ayıklama özellik sayfası](../debugger/media/dbg_cpp_debugpropertypage.png "DBG_CPP_DebugPropertyPage")  
  
###  <a name="BKMK_Choose_the_build_configuration_options"></a>Yapı yapılandırma seçeneklerini seçin  
  
1.  Gelen **yapılandırma** listesinde, seçin **hata ayıklama** veya **(etkin) hata ayıklama**.  
  
2.  Gelen **Platform** listesi oluşturmak için hedef platformu seçin. Çoğu durumda, **herhangi bir CPU** (**tüm platformlar** Visual C++'ta) en iyi seçimdir.  
  
###  <a name="BKMK_Choose_the_deployment_target"></a>Dağıtım hedefi seçin  
 ![Windows için yalnızca geçerlidir](../debugger/media/windows_only_content.png "windows_only_content")  
  
 Dağıtma ve Visual Studio makinede Visual Studio simulator yerel makinede ya da uzak cihazda UWP uygulamasında hata ayıklama.  
  
-   C# ve Visual Basic uygulamaları için hedef seçin **hedef aygıt** listesini **hata ayıklama** projesi için özellik sayfası.  
  
-   C++ uygulamaları için hedef seçin **başlatmak için hata ayıklayıcı** listesini **hata ayıklama** özellik sayfası:  
  
 Bu seçeneklerden birini seçin:  
  
|||  
|-|-|  
|**Yerel Makine**|Uygulama hata ayıklama yerel makinenizdeki geçerli oturumdaki. Bkz: [yerel makine üzerinde çalıştırmak UWP uygulamaları](../debugger/run-windows-store-apps-on-the-local-machine.md).|  
|**Simulator**|Visual Studio simülatörü uygulamada hata ayıklama [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulamalar. Simulator cihazın işlevselliğini ayıklamanızı sağlar masaüstü bir penceredir — dokunma hareketleri ve cihaz döndürme gibi — yerel makinede kullanılabilir değildir. Bkz: [simulator çalıştırmak UWP uygulamalarında](../debugger/run-windows-store-apps-in-the-simulator.md).|  
|**Uzak makine**|Yerel makineye intranet üzerinden bağlı veya Ethernet kablosu kullanarak doğrudan bağlı bir cihaza uygulamanın hata ayıklama. Uzaktan hata ayıklamak için Visual Studio uzak Araçlar yüklü ve uzak aygıt üzerinde çalışıyor olması gerekir. Bkz: [uzaktaki bir makinede çalıştırın UWP uygulamaları](../debugger/run-windows-store-apps-on-a-remote-machine.md).|  
  
 Seçerseniz **uzak makine**, adı veya IP adresi Uzak makinenin şu yöntemlerden birini belirtin:  
  
-   Adı veya uzak makinenin IP adresini girin.  
  
    -   C# ve Visual Basic uygulamaları için ad veya IP adresini girin **uzak makine** kutusu.  
  
    -   C++ uygulamaları için ad veya IP adresini girin **makine adı** kutusu.  
  
-   Uzak makineden seçin **seçin uzaktan hata ayıklayıcı bağlantı** iletişim kutusu.  
  
     İletişim kutusunu açmak için:  
  
    -   Uygulamalar, C# ve Visual Basic için **Bul**.  
  
    -   C++ uygulamaları için aşağı oka seçin **makine adı** kutusuna ve seçin  **\<bulun... >**.  
  
     ![Select uzaktan hata ayıklayıcı bağlantı iletişim kutusu](../debugger/media/vsrun_selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")  
  
    > [!NOTE]
    >  **Seçin uzaktan hata ayıklayıcı bağlantı** yerel alt ağ üzerinde olan makinelere ve Visual Studio makineye Ethernet kablosu tarafından doğrudan bağlı sanal makinelere iletişim kutusu görüntüler. Başka bir makine belirtmek için ad girin **makine adı** kutusu.  
  
 ![Windows Phone için yalnızca geçerli](../debugger/media/phone_only_content.png "phone_only_content")  
  
 Dağıtma ve Windows Phone Uygulama bir aygıt veya Visual Studio telefon Öykünücüler birinde hata ayıklama. Cihaz veya öykünücüsünden seçin **hedef aygıt** listesi.  
  
###  <a name="BKMK_Choose_the_debugger_to_use"></a>Kullanmak için hata ayıklayıcı seçin  
 Varsayılan olarak, Visual Studio C# ve Visual Basic uygulamalarında yönetilen kodu debugs.  
  
 C# ve Visual Basic uygulamaları için hem yönetilen ve yerel C/C++ kodu, uygulamanızda hata ayıklama seçebilirsiniz. Seçin **yönetilmeyen kod hata ayıklamayı etkinleştir** yerel kod hata ayıklama oturumunda eklemek için onay kutusunu.  
  
 Varsayılan olarak, Visual Studio, C++ uygulamanızda yerel kod debugs.  
  
 C++ uygulamaları için uygulamanızın yerine ya da ek olarak, yerel kod bileşenlerindeki kodu belirli türlerdeki hata ayıklama seçebilirsiniz. İçinde hata ayıklamak için kod belirttiğiniz **hata ayıklayıcı türü** listesini **hata ayıklama** uygulama projesi özellik sayfasında.  
  
 Bu hata ayıklayıcıları birini **uygulama işlemi** listesi:  
  
|||  
|-|-|  
|**Yalnızca komut dosyası**|JavaScript kodu, uygulamanızda hata ayıklama. Yönetilen kod ve yerel kodu göz ardı edilir.|  
|**Yalnızca yerel**|Yerel C/C++ kodu, uygulamanızda hata ayıklama. Yönetilen kod ve JavaScript kodu göz ardı edilir.|  
|**Yalnızca yönetilen**|Uygulamanızı yönetilen kodda hata ayıklama. JavaScript kodu ve yerel C/C++ kod göz ardı edilir.|  
|**Karma (yönetilen ve yerel)**|Yerel C/C++ kod ve uygulamanızı yönetilen kodda hata ayıklama. JavaScript kodu göz ardı edilir.|  
|**GPU yalnızca**|Bir grafik işlemci birimi (GPU) çalıştıran yerel C++ kod hatalarını ayıklama.|  
  
 ![Windows Phone için yalnızca geçerli](../debugger/media/phone_only_content.png "phone_only_content")  
  
 Windows Phone uygulamaları için arka plan işlemleri için kullanılacak hata ayıklayıcı de seçebilirsiniz **arka plan görev işlemi**.  
  
###  <a name="BKMK__Optional__Delay_starting_the_debug_session"></a>(İsteğe bağlı) Hata ayıklama oturumu başlatma gecikmesi  
 Hata ayıklama başlattığınızda varsayılan olarak, Visual Studio uygulama hemen başlar. Ayrıca, bir hata ayıklama oturumu Başlat ancak uygulamanızı başlangıcı geciktirmek. Bu seçeneği seçtiğinizde, uygulama başlangıç ekranından veya bir etkinleştirme sözleşme başlatıldığında veya başka bir işlem veya yöntemi tarafından başlatılırken hata ayıklayıcısı'ndaki başlatılır. Uygulama çalışmıyorken bir arka plan görevi hata ayıklama istediğinizde de, uygulamanızın başlangıç gecikme.  
  
 Uygulamanızı başlatma gecikmesi için şunları yapabilirsiniz:  
  
-   Visual C# ve Visual Basic uygulamaları için **değil başlatın, ancak başlatıldığında kodum hata ayıklama** üzerinde **hata ayıklama** özellik sayfası.  
  
-   Visual C++ uygulamaları için seçin **Evet** gelen **uygulama Başlat** listesini **hata ayıklama** özellik sayfası.  
  
###  <a name="BKMK__Optional__Disable_network_loopbacks"></a>(İsteğe bağlı) Ağ geri döngüler devre dışı bırak  
 ![Windows için yalnızca geçerlidir](../debugger/media/windows_only_content.png "windows_only_content")  
  
 Güvenlik nedeniyle, standart bir biçimde yüklü bir UWP uygulaması, üzerinde yüklü olduğu cihaz ağ çağrı yapmak için izin verilmiyor. Varsayılan olarak, bu kural dağıtılan uygulama için bir muafiyet Visual Studio dağıtımı oluşturur. Bu istisna tek bir makinede iletişim yordamlarını test etmenizi sağlar. Microsoft Store uygulamanıza göndermeden önce muafiyet olmadan uygulamanızı test etmeniz gerekir.  
  
 Ağ geri döngü muafiyet kaldırmak için:  
  
-   Visual C# ve Visual Basic uygulamaları için temizleyin **izin ağ geri döngü** onay kutusunu **hata ayıklama** özellik sayfası.  
  
-   Visual C++ uygulamaları için seçin **Hayır** gelen **izin ağ geri döngü** listesini **hata ayıklama** özellik sayfası.  
  
###  <a name="BKMK__Optional__Reinstall_the_app_when_you_start_debugging"></a>(İsteğe bağlı) Hata ayıklama başlattığınızda uygulamayı yeniden yükleyin.  
 Yükleme ve Visual C# veya Visual Basic uygulamanızın ilk yapılandırma ile ilgili sorunları tanılamak için tercih **kaldırma ve my paketi yeniden** üzerinde **hata ayıklama** yeniden oluşturmak için özellik sayfası bir hata ayıklama başlattığınızda, özgün yükleme. Visual C++ projeleri için bu seçenek kullanılamaz.  
  
###  <a name="BKMK__Optional__Disable_authentication_requirement_to_start_the_remote_debugger"></a>(İsteğe bağlı) Uzaktan hata ayıklayıcı başlatmak için kimlik doğrulama gereksinimini devre dışı bırak  
 ![Windows için yalnızca geçerlidir](../debugger/media/windows_only_content.png "windows_only_content")  
  
 Varsayılan olarak, uzaktan hata ayıklayıcı çalıştırmak için kimlik bilgilerini sağlamanız gerekir.  
  
> [!IMPORTANT]
>  Uzaktan hata ayıklayıcı Hayır kimlik doğrulama modunda çalışacak şekilde seçebilirsiniz, ancak bu modu kesinlikle önerilmez. Bu modda çalıştırdığınızda, ağ güvenliği yoktur. Ağın, kötü amaçlı veya tehlikeli trafik riskinden uzak olduğundan eminseniz Kimlik Doğrulaması Yok modunu seçin.  
  
 Kimlik doğrulama gereksinimini kaldırmak için:  
  
1.  Visual C# ve Visual Basic uygulamaları için temizleyin **kimlik doğrulamasını kullan** onay kutusunu **hata ayıklama** özellik sayfası.  
  
2.  Visual C++ uygulamaları için seçin **Hayır** gelen **kimlik doğrulaması iste** listesini **hata ayıklama** özellik sayfası.  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Start_the_debugging_session"></a>Hata ayıklama oturumu Başlat  
  
###  <a name="BKMK_Start_debugging__F5_"></a>(F5) hata ayıklamayı Başlat  
 Seçtiğinizde **hata ayıklamayı Başlat** (klavye: F5) üzerinde **hata ayıklama** menüsünde, Visual Studio başlatır uygulama hata ayıklayıcısı ekli. Yürütme bir kesme noktası ulaşıldığında, el ile bir özel durum oluştu, yürütme, askıya veya uygulama sona kadar devam eder.  
  
###  <a name="BKMK_Start_debugging__F5__but_delay_the_app_start"></a>(F5) hata ayıklamayı Başlat ancak uygulama başlatma gecikmesi  
 Hata ayıklama modunda çalıştırın, ancak başlatılsın hata ayıklayıcı dışında bir yöntem tarafından uygulamanın ayarlayabilirsiniz. Örneğin, başlatma Başlat menüsünden, uygulamanızın hatalarını ayıklama veya uygulama başlatmadan bir arka plan işlemi uygulamasında hata ayıklama isteyebilirsiniz. Uygulama başlangıcı geciktirmek için şunu yapın:  
  
-   Üzerinde **hata ayıklama** uygulamanın özellik sayfası (**hata ayıklama** Visual c++)  
  
    -   Uygulamalar, Visual C# ve Visual Basic için **değil başlatın, ancak başlatıldığında kodum hata ayıklama**.  
  
    -   Visual C++ uygulamaları için seçin **Evet** gelen **uygulama Başlat** listesi.  
  
-   Seçin **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: F5).  
  
-   Uygulamanızı bir yürütme sözleşme Başlat menüsünden veya başka bir yordam başlatın.  
  
 Uygulama hata ayıklama modunda başlatır. Yürütme bir kesme noktası ulaşıldığında, el ile işlenmeyen bir özel durum oluşur, yürütme, askıya veya uygulama sona kadar devam eder.  
  
 biçimindeki telefon numarasıdır. Arka plan görevleri hata ayıklama hakkında daha fazla bilgi için bkz: [tetikleyici askıya alma, sürdürme ve arka plan olaylarını UWP uygulamalar için)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).  
  
###  <a name="BKMK_Start_an_installed_app_in_the_debugger"></a>Hata Ayıklayıcısı'ndaki yüklü bir uygulamayı Başlat  
 F5 kullanarak hata ayıklama başlattığınızda, Visual Studio oluşturur ve uygulamayı dağıtır, hata ayıklama modunda çalıştırmak için uygulamayı ayarlar ve ardından başlatır. Bir cihazda zaten yüklü olan bir uygulamayı başlatmak için yüklenen uygulama paketi hata ayıklama iletişim kutusunu kullanın. Bu yordam, Windows Mağazası'ndan veya uygulama için kaynak dosyaları varsa, ancak uygulama için bir Visual Studio projesini yok yüklü olduğu bir uygulama hata ayıklama gerektiğinde kullanışlıdır. Örneğin, Visual Studio projeleri veya çözümleri kullanmayan bir özel yapı sistemi olabilir.  
  
 Uygulama yerel cihazda yüklenebilir veya bir uzak cihazda olabilir.  Uygulamanın hemen başlatmak için ya da onu Başlat menüsünden veya bir etkinleştirme sözleşme tarafından bir arka plan işlemi hata ayıklama istediğinizde hata ayıklama modunda çalıştırmak için uygulamayı de ayarlayabilirsiniz gibi başka bir işlem veya yöntemi tarafından başlatılırken hata ayıklayıcısı'ndaki çalıştırmak için ayarlayabilir. Uygulama başlatmadan. Daha fazla bilgi için bkz: [tetikleyici askıya alma, sürdürme ve arka plan olaylarını UWP uygulamalar için)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).  
  
 Hata ayıklama modunda çalıştırmak için yüklü bir uygulamayı ayarlamak için bunu yapın:  
  
> [!NOTE]
>  Bu yordamı başlattığınızda, uygulama çalışmıyor olması gerekir.  
  
1.  Üzerinde **hata ayıklama** menüsünde seçin **yüklü uygulama paketi hata ayıklama**  
  
2.  Listeden aşağıdaki seçeneklerden birini seçin:  
  
    |||  
    |-|-|  
    |**Yerel Makine**|Uygulama hata ayıklama yerel makinenizdeki geçerli oturumdaki. Bkz: [yerel makine üzerinde çalıştırmak UWP uygulamaları](../debugger/run-windows-store-apps-on-the-local-machine.md).|  
    |**Simulator**|Visual Studio simülatörü uygulamada hata ayıklama [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulamalar. Simulator cihazın işlevselliğini ayıklamanızı sağlar masaüstü bir penceredir — dokunma hareketleri ve cihaz döndürme gibi — yerel makinede kullanılabilir değildir. Bkz: [simulator çalıştırmak UWP uygulamalarında](../debugger/run-windows-store-apps-in-the-simulator.md).|  
    |**Uzak makine**|Yerel makineye intranet üzerinden bağlı veya Ethernet kablosu kullanarak doğrudan bağlı bir cihaza uygulamanın hata ayıklama. Uzaktan hata ayıklamak için Visual Studio uzak Araçlar yüklü ve uzak aygıt üzerinde çalışıyor olması gerekir. Bkz: [uzaktaki bir makinede çalıştırın UWP uygulamaları](../debugger/run-windows-store-apps-on-a-remote-machine.md).|  
  
3.  Uygulamadan seçin **uygulama paketleri yüklü** listesi.  
  
4.  Kullanmak için hata ayıklama altyapısı seçin **Bu kod türü hata ayıklama** listesi.  
  
5.  (İsteğe bağlı). Seçin **değil başlatın, ancak başlatıldığında kodum hata ayıklama** başka bir yöntem tarafından başlatıldığında uygulama hata ayıklama veya bir arka plan işlemi hata ayıklamak için.  
  
 Tıkladığınızda **Başlat**, uygulama başlatıldığında veya hata ayıklama modunda çalışacak şekilde ayarlanmış.  
  
###  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a>Hata ayıklayıcıyı çalışan bir uygulama Ekle  
 Hata ayıklayıcısını için bir [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulama, hata ayıklama modunda çalıştırmak için uygulamayı ayarlamak için Debuggable Paket Yöneticisi kullanmalıdır. Debuggable Paket Yöneticisi ile Visual Studio uzak Araçlar yüklenir.  
  
 Hata ayıklayıcı için uygulama ekleme yararlıdır yüklendiği bir uygulama gibi bir zaten yüklü uygulama hata ayıklama gerektiğinde [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)]. Uygulama için kaynak dosyaları varsa, ancak uygulama için bir Visual Studio projesini olmayan ekleme gereklidir. Örneğin, Visual Studio projeleri veya çözümleri kullanmayan bir özel yapı sistemi olabilir.  
  
 Hata ayıklayıcı bir uygulamaya eklemek için aşağıdaki adımları gerekir:  
  
1.  Hata ayıklama modunda çalıştırmak için uygulamayı ayarlayın. Uygulama çalışmıyorken Bunun yapılması gerekir.  
  
2.  Uygulamayı başlatın. Uygulama başlangıç ekranında, yürütme sözleşme ya da başka bir yöntem başlatabilirsiniz.  
  
3.  Hata ayıklayıcısını çalışan uygulamaya ekleyin.  
  
####  <a name="BKMK_Set_the_app_to_run_in_debug_mode"></a>Hata ayıklama modunda çalıştırmak için uygulamayı Ayarla  
  
1.  Visual Studio uzak Araçlar uygulamanın yüklendiği cihaza yükleyin. Bkz: [uzak araçları yükleme](http://msdn.microsoft.com/library/windows/apps/hh441469.aspx#BKMK_Installing_the_Remote_Tools).  
  
2.  Başlangıç ekranında aramak `Debuggable Package Manager` ve sonra başlatın.  
  
     AppxDebug cmdlet'i için doğru yapılandırılmış bir PowerShell penceresi görüntülenir.  
  
3.  Bir uygulama hata ayıklamayı etkinleştirmek için uygulama PackageFullName tanıtıcısı belirtmeniz gerekir. PackageFullName içeren tüm uygulamaların bir listesini görüntülemek için şunu yazın `Get-AppxPackage` PowerShell komut isteminde.  
  
4.  PowerShell komut isteminde, girin `Enable-AppxDebug` *PackageFullName* nerede *PackageFullName* uygulamanın PackageFullName tanımlayıcısıdır.  
  
####  <a name="BKMK_Attach_the_debugger"></a>Hata ayıklayıcıyı Ekle  
 Hata ayıklayıcı eklemek için:  
  
1.  Üzerinde **hata ayıklama** menüsünde seçin **ekleme işlemi için**.  
  
     **Ekleme işlemi için** iletişim kutusu görüntülenir.  
  
2.  Uzak cihazdaki bir uygulamaya eklemek için uzak aygıt belirtin **niteleyicisi** kutusu. Şunları yapabilirsiniz:  
  
    -   Bir ad girin **niteleyicisi** kutusu.  
  
    -   Aşağı yönlü oku seçin **niteleyicisi** kutusuna ve ardından önce eklediyseniz aygıtlar listesinden bir cihaz seçin.  
  
    -   Seçin **bulmak** , yerel alt ağdaki aygıtları listesinden bir cihaz seçin.  
  
3.  İçinde hata ayıklamak istediğiniz kod türünü belirtin **ekleme** kutusu.  
  
     Seçin **seçin** ve ardından aşağıdakilerden birini yapın:  
  
    -   Seçin **otomatik olarak hata ayıklamak için kod türünü belirleme**  
  
    -   Seçin **bu kodu türleri hata ayıklama** ve listeden bir veya daha fazla türleri'i seçin.  
  
4.  İçinde **kullanılabilir işlemler** listesinde, uygulama işlemini seçin.  
  
5.  Seçin **Attach**.  
  
 Visual Studio hata ayıklayıcı işleme ekler. Yürütme bir kesme noktası ulaşıldığında, el ile işlenmeyen bir özel durum oluşur, yürütme, askıya veya uygulama sona kadar devam eder.  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio uygulamalarında hata ayıklama](../debugger/debug-store-apps-in-visual-studio.md)   
 [(Xaml ve C#) bir hata ayıklama oturumunda gezinme](../debugger/navigate-a-debugging-session-in-visual-studio-xaml-and-csharp.md)