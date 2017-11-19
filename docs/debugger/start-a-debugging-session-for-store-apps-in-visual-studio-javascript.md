---
title: "Visual Studio (JavaScript) UWP uygulamaları için hata ayıklama oturumu Başlat | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.installedapppackagelauncher
- vs.debug.error.wwahost_scriptdebuggingdisabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: fb91203f-2cf4-44d3-8ed9-93bc5aaa50b8
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 192000815a5d35056c88cf81de9956614c092284
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="start-a-debugging-session-for-uwp-apps-in-visual-studio-javascript"></a>Visual Studio (JavaScript) UWP uygulamaları için hata ayıklama oturumu Başlat
![Windows ve Windows Phone için geçerlidir](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 Bu konu, HTML5 ve JavaScript ile yazılmış UWP uygulamaları için hata ayıklama oturumu başlatmak açıklar. Tek bir tuş vuruşu ile hata ayıklama başlatabilirsiniz veya belirli senaryolar için hata ayıklama oturumu yapılandırmak ve uygulamayı başlatmak için yol seçin.  
  
> [!NOTE]
>  XAML ve Visual C#, Visual C++ veya Visual Basic içinde yazılmış uygulamalar için bkz: [(VB, C#, C++ ve XAML) bir hata ayıklama oturumu Başlat](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)  
  
##  <a name="BKMK_In_this_topic"></a>Bu konudaki  
 [Bu konudaki](#BKMK_In_this_topic)  
  
 [En kolay yolu hata ayıklamayı Başlat](#BKMK_The_easy_way_to_start_debugging)  
  
 [Hata ayıklama oturumu yapılandırın](#BKMK_Configure_the_debugging_session)  
  
-   [Proje için hata ayıklama özellik sayfasını açın](#BKMK_Open_the_debugging_property_page_for_the_project)  
  
-   [Yapı yapılandırma seçeneklerini seçin](#BKMK_Choose_the_build_configuration_options)  
  
-   [Dağıtım hedefi seçin](#BKMK_Choose_the_deployment_target)  
  
-   [Kullanmak için hata ayıklayıcı seçin](#BKMK_Choose_the_debugger_to_use)  
  
-   [(İsteğe bağlı) Hata ayıklama oturumunda uygulama başlatma gecikmesi](#BKMK__Optional__Delay_starting_app_in_the_debug_session)  
  
-   [(İsteğe bağlı) Ağ geri döngüler devre dışı bırak](#BKMK__Optional__Disable_network_loopbacks)  
  
 [Hata ayıklama oturumu Başlat](#BKMK_Start_the_debugging_session)  
  
-   [(F5) hata ayıklamayı Başlat](#BKMK_Start_debugging__F5_)  
  
-   [(F5) hata ayıklamayı Başlat ancak uygulama başlatma gecikmesi](#BKMK_Start_debugging__F5__but_delay_the_app_start)  
  
 [Hata Ayıklayıcısı'ndaki yüklü bir uygulamayı Başlat](#BKMK_Start_an_installed_app_in_the_debugger)  
  
 [Hata ayıklayıcıyı çalışan bir uygulama Ekle](#BKMK_Attach_the_debugger_to_a_running_app_)  
  
-   [Hata ayıklama modunda çalıştırmak için uygulamayı Ayarla](#BKMK_Set_the_app_to_run_in_debug_mode)  
  
-   [Hata ayıklayıcıyı Ekle](#BKMK_Attach_the_debugger)  
  
##  <a name="BKMK_The_easy_way_to_start_debugging"></a>En kolay yolu hata ayıklamayı Başlat  
 ![Windows için yalnızca geçerlidir](../debugger/media/windows_only_content.png "windows_only_content")  
  
1.  Uygulama çözümü Visual Studio'da açın.  
  
2.  Çözüm birden çok proje içeriyorsa, hata ayıklamak istediğiniz projesini başlangıç projesi olduğundan emin olun. Çözüm keşfetmek, projesini seçin ve ardından **başlangıç projesi olarak ayarla** ve bağlam menüsünden.  
  
3.  F5 tuşuna basın.  
  
 ![Windows Phone için yalnızca geçerli](../debugger/media/phone_only_content.png "phone_only_content")  
  
 Visual Studio oluşturur ve hata ayıklayıcısı ekli uygulamayı başlatır. Yürütme bir kesme noktası ulaşıldığında, el ile işlenmeyen bir özel durum oluşur, yürütme, askıya veya uygulama sona kadar devam eder. Daha fazla bilgi için bkz: [hızlı başlangıç: hata ayıklama HTML ve CSS](../debugger/quickstart-debug-html-and-css.md).  
  
##  <a name="BKMK_Configure_the_debugging_session"></a>Hata ayıklama oturumu yapılandırın  
 Komut dosyası derlenmemiş olduğundan yapı yapılandırma ve platform ayarları uygulanmaz. C++ ya da yönetilen bileşen ayıkladığınız, ayarlamak **yapılandırma** için **hata ayıklama** ve hedef platformunuzu seçin **yapılandırma** iletişim.  
  
###  <a name="BKMK_Open_the_debugging_property_page_for_the_project"></a>Proje için hata ayıklama özellik sayfasını açın  
  
1.  Çözüm Gezgini'nde proje seçin. Kısayol menüsünden seçin **özellikleri**.  
  
2.  Genişletme **yapılandırma özellikleri** düğümünü ve ardından **hata ayıklama**.  
  
###  <a name="BKMK_Choose_the_build_configuration_options"></a>Yapı yapılandırma seçeneklerini seçin  
  
1.  Gelen **yapılandırma** listesinde, seçin **hata ayıklama** veya **(etkin) hata ayıklama**.  
  
2.  Gelen **Platform** listesi oluşturmak için hedef platformu seçin. Çoğu durumda, **herhangi bir CPU** en iyi seçimdir.  
  
###  <a name="BKMK_Choose_the_deployment_target"></a>Dağıtım hedefi seçin  
 Dağıtma ve Visual Studio makinede yerel makinede ya da uzak makinede Visual Studio simulator uygulama hata ayıklama. Hedef seçtiğiniz **başlatmak için hata ayıklayıcı** listesini **hata ayıklama** projesi için özellik sayfası.  
  
 ![Windows için yalnızca geçerlidir](../debugger/media/windows_only_content.png "windows_only_content")  
  
 UWP uygulaması için bu seçeneklerden birini **hedef aygıt** listesi:  
  
|||  
|-|-|  
|**Yerel Makine**|Uygulama hata ayıklama yerel makinenizdeki geçerli oturumdaki. Bkz: [yerel makine üzerinde çalıştırmak UWP uygulamaları](../debugger/run-windows-store-apps-on-the-local-machine.md).|  
|**Simulator**|Visual Studio simülatörü uygulamada hata ayıklama [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulamalar. Simulator cihazın işlevselliğini ayıklamanızı sağlar masaüstü bir penceredir — dokunma hareketleri ve cihaz döndürme gibi — yerel makinede kullanılabilir değildir. Bkz: [simulator çalıştırmak UWP uygulamalarında](../debugger/run-windows-store-apps-in-the-simulator.md).|  
|**Uzak makine**|Yerel makineye intranet üzerinden bağlı veya Ethernet kablosu kullanarak doğrudan bağlı bir cihaza uygulamanın hata ayıklama. Uzaktan hata ayıklamak için Visual Studio uzak Araçlar yüklü ve uzak aygıt üzerinde çalışıyor olması gerekir. Bkz: [uzaktaki bir makinede çalıştırın UWP uygulamaları](../debugger/run-windows-store-apps-on-a-remote-machine.md).|  
  
 Seçerseniz **uzak makine**, adı veya IP adresi Uzak makinenin şu yöntemlerden birini belirtin:  
  
-   Adı veya IP adresi Uzak makinenin girin **makine adı** kutusu.  
  
-   Aşağı oka seçin **makine adı** kutusuna ve seçin  **\<bulun... >**. Uzak makineden seçin **seçin uzaktan hata ayıklayıcı bağlantı** iletişim kutusu.  
  
     ![Uzaktan hata ayıklayıcı bağlantıyı seçin](../debugger/media/vsrun_pro_selectremotedebuggerdlg.png "VSRUN_PRO_SelectRemoteDebuggerDlg")  
  
    > [!NOTE]
    >  Yerel alt ağ üzerinde olan makinelere ve Visual Studio makineye Ethernet kablosu tarafından doğrudan bağlı sanal makinelere uzaktan hata ayıklayıcı bağlantısı seçin iletişim kutusu görüntüler. Başka bir makine belirtmek için ad girin **makine adı** kutusu.  
  
 ![Windows Phone için yalnızca geçerli](../debugger/media/phone_only_content.png "phone_only_content")  
  
 Windows Phone uygulaması için seçin **aygıt** veya Öykünücüler **hedef aygıt** listesi.  
  
###  <a name="BKMK_Choose_the_debugger_to_use"></a>Kullanmak için hata ayıklayıcı seçin  
 Varsayılan olarak, hata ayıklayıcı JavaScript kodu, uygulamanızda ekler. Yönetilen kod JavaScript kodu yerine, uygulamanızın bileşenlerinin ve yerel C++ hata ayıklama seçebilirsiniz. İçinde hata ayıklamak için kod belirttiğiniz **hata ayıklayıcı türü** listesini **hata ayıklama** uygulama projesi özellik sayfasında.  
  
 Bu hata ayıklayıcıları birini **hata ayıklayıcı türü** listesi:  
  
|||  
|-|-|  
|**Yalnızca komut dosyası**|JavaScript kodu, uygulamanızda hata ayıklama. Yönetilen kod ve yerel kodu göz ardı edilir.|  
|**Yalnızca yerel**|Yerel C/C++ kodu, uygulamanızda hata ayıklama. Yönetilen kod ve JavaScript kodu göz ardı edilir.|  
|**Yerel kod**|Yerel C++ kodu ve JavaScript kodu, uygulamanızda hata ayıklama.|  
|**Yalnızca yönetilen**|Uygulamanızı yönetilen kodda hata ayıklama. JavaScript kodu ve yerel C/C++ kod göz ardı edilir.|  
|**Karma (yönetilen ve yerel)**|Yerel C/C++ kod ve uygulamanızı yönetilen kodda hata ayıklama. JavaScript kodu göz ardı edilir.|  
  
###  <a name="BKMK__Optional__Delay_starting_app_in_the_debug_session"></a>(İsteğe bağlı) Hata ayıklama oturumunda uygulama başlatma gecikmesi  
 Hata ayıklama başlattığınızda varsayılan olarak, Visual Studio uygulama hemen başlar. Ayrıca, bir hata ayıklama oturumu Başlat ancak uygulamanızı başlangıcı geciktirmek. Uygulama Hata Ayıklayıcısı'ndaki Başlat menüsünden veya bir etkinleştirme sözleşme başlatıldığında ya da başka bir işlem veya yöntemi tarafından başlatıldığında başlatılır. Gecikmeli Başlatma, uygulama çalışmıyorken gerçekleştirilmesini istediğiniz uygulamanızda hata ayıklama arka plan olayları için de kullanabilirsiniz.  
  
 Uygulamanızda başlatma gecikmesi belirtin **uygulama Başlat** listesini **hata ayıklama** uygulama projesi özellik sayfasında. Bu seçeneklerden birini seçin:  
  
-   Seçin **Hayır** gecikme uygulamanızı başlatın.  
  
-   Seçin **Evet** uygulamayı hemen başlatmak için.  
  
###  <a name="BKMK__Optional__Disable_network_loopbacks"></a>(İsteğe bağlı) Ağ geri döngüler devre dışı bırak  
 ![Windows için yalnızca geçerlidir](../debugger/media/windows_only_content.png "windows_only_content")  
  
 Güvenlik nedeniyle, standart bir biçimde yüklü bir UWP uygulaması, üzerinde yüklü olduğu cihaz ağ çağrı yapmak için izin verilmiyor. Varsayılan olarak, bu kural dağıtılan uygulama için bir muafiyet Visual Studio dağıtımı oluşturur. Bu istisna tek bir makinede iletişim yordamlarını test etmenizi sağlar. Microsoft Store uygulamanıza göndermeden önce muafiyet olmadan uygulamanızı test etmeniz gerekir.  
  
 Ağ geri döngü muafiyet kaldırmak için tercih **Hayır** gelen **izin ağ geri döngü** listesini **hata ayıklama** özellik sayfası.  
  
##  <a name="BKMK_Start_the_debugging_session"></a>Hata ayıklama oturumu Başlat  
  
###  <a name="BKMK_Start_debugging__F5_"></a>(F5) hata ayıklamayı Başlat  
 Seçtiğinizde **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: F5), Visual Studio hata ayıklayıcısı ekli uygulamayı başlatır. Yürütme bir kesme noktası ulaşıldığında, el ile işlenmeyen bir özel durum oluşur, yürütme, askıya veya uygulama sona kadar devam eder.  
  
###  <a name="BKMK_Start_debugging__F5__but_delay_the_app_start"></a>(F5) hata ayıklamayı Başlat ancak uygulama başlatma gecikmesi  
 Hata ayıklama modunda çalıştırmak, ancak hata ayıklayıcı dışında bir yöntem tarafından başlatıldığından izin uygulamanın ayarlayabilirsiniz. Örneğin, başlatma Başlat menüsünden, uygulamanızın hatalarını ayıklama veya uygulama başlatmadan bir arka plan işlemi uygulamasında hata ayıklama isteyebilirsiniz. Uygulama başlangıcı geciktirmek için şunu yapın:  
  
1.  Üzerinde **hata ayıklama** sayfa uygulaması proje özellikleri, seçin **Hayır** gelen **uygulama Başlat** listesi.  
  
2.  Seçin **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: F5).  
  
3.  Uygulamanızı bir yürütme sözleşme Başlat menüsünden veya başka bir yordam başlatın.  
  
 Uygulama hata ayıklama modunda başlatır. Yürütme bir kesme noktası ulaşıldığında, el ile işlenmeyen bir özel durum oluşur, yürütme, askıya veya uygulama sona kadar devam eder.  
  
 biçimindeki telefon numarasıdır. Arka plan görevleri hata ayıklama hakkında daha fazla bilgi için bkz: [tetikleyici askıya alma, sürdürme ve arka plan olaylarını UWP uygulamalar için)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).  
  
##  <a name="BKMK_Start_an_installed_app_in_the_debugger"></a>Hata Ayıklayıcısı'ndaki yüklü bir uygulamayı Başlat  
 F5 kullanarak hata ayıklama başlattığınızda, Visual Studio oluşturur ve uygulamayı dağıtır, hata ayıklama modunda çalıştırmak için uygulamayı ayarlar ve ardından başlatır. Bir cihazda zaten yüklü olan bir uygulamayı başlatmak için yüklenen uygulama paketi hata ayıklama iletişim kutusunu kullanın. Bu yordam, Windows Mağazası'ndan veya uygulama için kaynak dosyaları varsa, ancak uygulama için bir Visual Studio projesini yok yüklü olduğu bir uygulama hata ayıklama gerektiğinde kullanışlıdır. Örneğin, Visual Studio projeleri veya çözümleri kullanmayan bir özel yapı sistemi olabilir.  
  
 Uygulama yerel cihazda yüklenebilir veya bir uzak cihazda olabilir.  Uygulamanın hemen başlatmak için ya da onu Başlat menüsünden veya bir etkinleştirme sözleşme tarafından bir arka plan işlemi hata ayıklama istediğinizde hata ayıklama modunda çalıştırmak için uygulamayı de ayarlayabilirsiniz gibi başka bir işlem veya yöntemi tarafından başlatılırken hata ayıklayıcısı'ndaki çalıştırmak için ayarlayabilir. Uygulama başlatmadan. Daha fazla bilgi için bkz: [tetikleyici askıya alma, sürdürme ve arka plan olaylarını UWP uygulamalar için)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).  
  
 Hata ayıklama modunda çalıştırmak için yüklü bir uygulamayı ayarlamak için bunu yapın:  
  
> [!NOTE]
>  Bu yordamı başlattığınızda, uygulama çalışmıyor olması gerekir.  
  
1.  Üzerinde **hata ayıklama** menüsünde seçin **yüklü uygulama paketi Debug**.  
  
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
  
##  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a>Hata ayıklayıcıyı çalışan bir uygulama Ekle  
 Hata ayıklayıcısını için bir [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulama, hata ayıklama modunda çalıştırmak için uygulamayı ayarlamak için Debuggable Paket Yöneticisi kullanmalıdır. Debuggable Paket Yöneticisi ile Visual Studio uzak Araçlar yüklenir.  
  
 Hata ayıklayıcı için uygulama ekleme yararlıdır uygulama zaten yüklü hata ayıklamak gerektiğinde, Windows yüklü olduğu bir uygulama gibi depolamak. Uygulama için kaynak dosyaları varsa, ancak uygulama için bir Visual Studio projesini olmayan ekleme gereklidir. Örneğin, Visual Studio projeleri veya çözümleri kullanmayan bir özel yapı sistemi olabilir.  
  
 Bir uygulamaya eklemek için:  
  
1.  Hata ayıklama modunda çalıştırmak için uygulamayı ayarlayın. Uygulama çalışmıyorken Bunun yapılması gerekir.  
  
2.  Uygulamayı başlatın. Başlat menüsü, yürütme sözleşme ya da başka bir yöntem uygulama başlatabilirsiniz.  
  
3.  Hata ayıklayıcısını çalışan uygulamaya ekleyin.  
  
###  <a name="BKMK_Set_the_app_to_run_in_debug_mode"></a>Hata ayıklama modunda çalıştırmak için uygulamayı Ayarla  
  
1.  Visual Studio uzak Araçlar uygulamanın yüklendiği cihaza yükleyin. Bkz: [uzak araçları yükleme](http://msdn.microsoft.com/library/windows/apps/hh441469.aspx#BKMK_Installing_the_Remote_Tools).  
  
2.  Başlat menüsünde arama `Debuggable Package Manager` ve sonra başlatın.  
  
     AppxDebug cmdlet'i için doğru yapılandırılmış bir PowerShell penceresi görüntülenir.  
  
3.  Bir uygulama hata ayıklamayı etkinleştirmek için uygulama PackageFullName tanıtıcısı belirtmeniz gerekir. PackageFullName içeren tüm uygulamaların bir listesini görüntülemek için şunu yazın `Get-AppxPackage` PowerShell komut isteminde.  
  
4.  PowerShell komut isteminde, girin `Enable-AppxDebug` *PackageFullName* nerede *PackageFullName* uygulamanın PackageFullName tanımlayıcısıdır.  
  
###  <a name="BKMK_Attach_the_debugger"></a>Hata ayıklayıcıyı Ekle  
  
> [!TIP]
>  JavaScript uygulamaları wwahost.exe işlem örneğini çalıştırın. Uygulamaya taktığınızda diğer JavaScript uygulamaları çalıştırıyorsanız, uygulamayı çalıştıran wwahost.exe sayısal işlem kimliğini (PID) bilmeniz gerekir.  
>   
>  Bu durumu düzeltmek için kolay bir JavaScript uygulamaları kapatmaya yoludur. Aksi takdirde, uygulamayı başlatın ve wwahost.exe işlem kimlikleri not alın önce Windows Görev Yöneticisi'ni açın. Uygulamasındaki ekleme işlemi belirttiğinizde **kullanılabilir işlemler** iletişim kutusunda, uygulama wwahost.exe not ettiğiniz olanları farklı bir kimlik olacaktır.  
  
 Hata ayıklayıcı eklemek için:  
  
1.  Üzerinde **hata ayıklama** menüsünde seçin **ekleme işlemi için**.  
  
     **Ekleme işlemi için** iletişim kutusu görüntülenir.  
  
2.  Uzak cihazdaki bir uygulamaya eklemek için uzak aygıt belirtin **niteleyicisi** kutusu. Şunları yapabilirsiniz:  
  
    -   Bir ad girin **niteleyicisi** kutusu.  
  
    -   Aşağı yönlü oku seçin **niteleyicisi** kutusuna ve aygıtı önce eklediyseniz aygıtları listesinden seçin.  
  
    -   Seçin **bulmak** , yerel alt ağdaki aygıtları listesinden bir cihaz seçmek için.  
  
3.  İçinde hata ayıklamak istediğiniz kod türünü belirtin **ekleme** kutusu.  
  
     Seçin **seçin** ve ardından aşağıdakilerden birini yapın:  
  
    -   Seçin **otomatik olarak hata ayıklamak için kod türünü belirleme**.  
  
    -   Seçin **bu kodu türleri hata ayıklama** ve listeden bir veya daha fazla türleri'i seçin.  
  
4.  İçinde **kullanılabilir işlemler** listesinde, uygun seçin **wwahost.exe** işlemi. Kullanım **başlık** uygulamanızı tanımlamak için sütun.  
  
5.  Seçin **Attach**.  
  
 Visual Studio hata ayıklayıcı işleme ekler. Yürütme bir kesme noktası ulaşıldığında, el ile işlenmeyen bir özel durum oluşur, yürütme, askıya veya uygulama sona kadar devam eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim yürütme bir hata ayıklama oturumunda (JavaScript)](../debugger/control-execution-of-a-store-app-in-a-visual-studio-debug-session-for-windows-store-apps-javascript.md)   
 [Hızlı Başlangıç: HTML ve CSS hata ayıklama](../debugger/quickstart-debug-html-and-css.md)   
 [Tetiklemek askıya alma, sürdürme ve arka plan olaylarını UWP uygulamalar için)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md)   
 [Visual Studio uygulamalarında hata ayıklama](../debugger/debug-store-apps-in-visual-studio.md)