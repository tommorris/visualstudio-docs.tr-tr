---
title: Visual Studio'da bir UWP uygulaması için hata ayıklama oturumu Başlat | Microsoft Docs
ms.custom: ''
ms.date: 01/04/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
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
- vs.debug.installedapppackagelauncher
- vs.debug.error.wwahost_scriptdebuggingdisabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: b298e2b17f1aa8805e0ab896c6978744c6c3bd53
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31481115"
---
# <a name="start-a-debugging-session-for-a-uwp-app-in-visual-studio"></a>Visual Studio'da bir UWP uygulaması için hata ayıklama oturumu Başlat
  
 Bu konu, HTML ve JavaScript UWP uygulamaları ve XAML ve Visual C++, Visual C# veya Visual Basic yazılmış UWP uygulamaları için hata ayıklama oturumu başlatmak açıklar. Bir uygulama hata ayıklama hem hata ayıklama oturumu yapılandırma ve uygulamayı başlatmak için yöntem seçme içerir.  
  
##  <a name="BKMK_The_easy_way_to_start_debugging"></a> En kolay yolu hata ayıklamayı Başlat  
  
1.  Uygulama çözümü Visual Studio'da açın.  
  
2.  F5'i seçin.  
  
 Visual Studio oluşturur ve hata ayıklayıcısı ekli uygulamayı başlatır. Yürütme bir kesme noktası ulaşıldığında, el ile işlenmeyen bir özel durum oluşur, yürütme, askıya veya uygulama sona kadar devam eder.  
  
##  <a name="BKMK_Choose_the_build_configuration_options"></a> Yapı yapılandırma seçeneklerini seçin  
  
1.   Açılır listeden sonraki **hata ayıklamayı Başlat** hata ayıklayıcı düğmesinde **standart** araç seçin **hata ayıklama**.  
  
2.  Gelen **Platform** listesi oluşturmak için hedef platformu seçin.  
  
##  <a name="BKMK_Choose_the_deployment_target"></a> Dağıtım hedefi seçin  
  
Dağıtma ve Visual Studio makine, bağlı bir aygıt, yerel makine, bir uzak aygıt ya da bir öykünücü Visual Studio simulator'da bir UWP uygulamasında hata ayıklama. Dağıtım hedef sağındaki açılan listeden seçin **Platform** hata ayıklayıcı hedefte **standart** araç.
  
![Bir dağıtım hedef seçin](../debugger/media/vsrun_select_target_device.png)  
  
Bu seçeneklerden birini seçin:  
  
|||  
|-|-|  
|**Yerel Makine**|Uygulama hata ayıklama yerel makinenizdeki geçerli oturumdaki.|  
|**Simulator**|UWP uygulamalar için Visual Studio simulator uygulamada hata ayıklama. Simulator cihazın işlevselliğini ayıklamanızı sağlar masaüstü bir penceredir — dokunma hareketleri ve cihaz döndürme gibi —, yerel makinede kullanılabilir olmayabilir. Bu seçenek yalnızca kullanılabilir değilse, uygulamanızın **hedef Platform Min. Sürüm** geliştirme makinenizdeki işletim sistemi küçük veya eşit. Bkz: [simulator çalıştırmak UWP uygulamalarında](../debugger/run-windows-store-apps-in-the-simulator.md).|  
|**Uzak makine**|Yerel makineye intranet üzerinden bağlı veya Ethernet kablosu kullanarak doğrudan bağlı bir cihaza uygulamanın hata ayıklama. Uzaktan hata ayıklamak için Visual Studio için Uzak araçları yüklü ve uzak cihazda çalışıyor olması gerekir. Bkz: [uzaktaki bir makinede çalıştırın UWP uygulamaları](../debugger/run-windows-store-apps-on-a-remote-machine.md).|  
|**Cihazı**|USB bağlantılı cihazda uygulama hata ayıklama. Cihaz kilidi Geliştirici ve kilidi ekran olmalıdır.|  
|**Mobil öykünücüsü**|Bir öykünücü öykünücüsü adında belirtilen yapılandırmayla önyükleme, uygulamayı dağıtmak ve hata ayıklamayı Başlat. Öykünücüler yalnızca Hyper-V etkin makinelerde kullanılabilir.|  

##  <a name="BKMK_Open_the_debugging_property_page_for_the_project"></a> Ek hata ayıklama seçeneklerini belirleyin  

Ek hata ayıklama seçeneklerini yapılandırmak gerekirse, proje için özellik sayfasını açın.
  
1.  Çözüm Gezgini'nde proje seçin. Kısayol menüsünden seçin **özellikleri**.  
  
2.  Bu proje için hata ayıklama özellik sayfası açmak için yapın:  
  
    -   Uygulamalar, Visual C# ve Visual Basic için **hata ayıklama**.  
  
         ![C&#35; &#47; VB proje hata ayıklama özellik sayfası](../debugger/media/dbg_csvb_debugpropertypage.png)  
  
    -   Visual C++ ve JavaScript uygulamaları için Genişlet **yapılandırma özellikleri** düğümünü ve ardından **hata ayıklama**.  
  
         ![C&#43; &#43; UWP uygulamasında hata ayıklama özellik sayfası](../debugger/media/dbg_cpp_debugpropertypage.png)  

###  <a name="BKMK_Choose_the_debugger_to_use"></a> Kullanmak için hata ayıklayıcı seçin  
Varsayılan olarak, Visual Studio C# ve Visual Basic uygulamalarında yönetilen kodu debugs. C# ve Visual Basic uygulamaları için hem yönetilen ve yerel C/C++ kodu, uygulamanızda hata ayıklama seçebilirsiniz. C++ uygulamalarında Visual Studio varsayılan olarak yerel kod debugs. JavaScript uygulamalarında Visual Studio komut dosyası varsayılan olarak debugs. 
  
C++ uygulamaları ve JavaScript için uygulamanızın yerine ya da ek olarak, yerel kod bileşenlerindeki kodu belirli türlerdeki hata ayıklamak seçebilirsiniz. İçinde hata ayıklamak için kod belirttiğiniz **hata ayıklayıcı türü** listesini **hata ayıklama** uygulama projesi özellik sayfasında.  
  
Bu hata ayıklayıcıları birini **uygulama işlemi** listesi:  
  
|||  
|-|-|  
|**Yalnızca yönetilen**|Uygulamanızı yönetilen kodda hata ayıklama. JavaScript kodu ve yerel C/C++ kod göz ardı edilir.|  
|**Yalnızca yerel**|Yerel C/C++ kodu, uygulamanızda hata ayıklama. Yönetilen kod ve JavaScript kodu göz ardı edilir.|  
|**Karma (yönetilen ve yerel)**|Yerel C/C++ kod ve uygulamanızı yönetilen kodda hata ayıklama. JavaScript kodu göz ardı edilir. C++ projelerinde, bu seçenek adlandırılır **(yönetilen ve yerel)**.|  
|**Yalnızca komut dosyası**|JavaScript kodu, uygulamanızda hata ayıklama. Yönetilen kod ve yerel kodu göz ardı edilir.|  
|**Komut dosyası ve yerel**|Yerel C/C++ kod ve JavaScript kodu, uygulamanızda hata ayıklama. Yönetilen kod yok sayılır. C++ projeleri yalnızca'nde kullanılabilir.|  
|**Yalnızca GPU (C++ AMP)**|Bir grafik işlemci birimi (GPU) çalıştıran yerel C++ kod hatalarını ayıklama. C++ projeleri yalnızca'nde kullanılabilir.|  

C# ve Visual Basic uygulamalarında da aynı ayarlayabilirsiniz **hata ayıklayıcı türü** projenin bir parçası olan herhangi bir arka plan görevi için değerler.
  
###  <a name="BKMK__Optional__Delay_starting_the_debug_session"></a> (İsteğe bağlı) Hata ayıklama oturumu başlatma gecikmesi  
 Hata ayıklama başlattığınızda varsayılan olarak, Visual Studio uygulama hemen başlar. Ayrıca, bir hata ayıklama oturumu Başlat ancak uygulamanızı başlangıcı geciktirmek. Bu seçeneği seçtiğinizde, uygulama başlangıç ekranından veya bir etkinleştirme sözleşme başlatıldığında veya başka bir işlem veya yöntemi tarafından başlatılırken hata ayıklayıcısı'ndaki başlatılır. Uygulama çalışmıyorken bir arka plan görevi hata ayıklama istediğinizde de, uygulamanızın başlangıç gecikme.  
  
 Uygulamanızı başlatma gecikmesi için şunları yapabilirsiniz:  
  
-   Visual C# ve Visual Basic uygulamaları için **değil başlatın, ancak başlatıldığında kodum hata ayıklama** üzerinde **hata ayıklama** özellik sayfası.  
  
-   Uygulamalar, Visual C++ ve JavaScript için **Hayır** gelen **uygulama Başlat** listesini **hata ayıklama** özellik sayfası.  
  
###  <a name="BKMK__Optional__Disable_network_loopbacks"></a> (İsteğe bağlı) Ağ geri döngüler devre dışı bırak  
  
 Güvenlik nedeniyle, standart bir biçimde yüklü bir UWP uygulaması, üzerinde yüklü olduğu cihaz ağ çağrı yapmak için izin verilmiyor. Varsayılan olarak, bu kural dağıtılan uygulama için bir muafiyet Visual Studio dağıtımı oluşturur. Bu istisna tek bir makinede iletişim yordamlarını test etmenizi sağlar. Microsoft Store uygulamanıza göndermeden önce muafiyet olmadan uygulamanızı test etmeniz gerekir.  
  
 Ağ geri döngü muafiyet kaldırmak için:  
  
-   Visual C# ve Visual Basic uygulamaları için temizleyin **yerel ağ geri döngü izin** onay kutusunu **hata ayıklama** özellik sayfası.  
  
-   Uygulamalar, Visual C++ ve JavaScript için **Hayır** gelen **izin yerel ağ geri döngü** listesini **hata ayıklama** özellik sayfası.  
  
###  <a name="BKMK__Optional__Reinstall_the_app_when_you_start_debugging"></a> (İsteğe bağlı) Hata ayıklama başlattığınızda uygulamayı yeniden yükleyin.  
 Yükleme ve Visual C# veya Visual Basic uygulamanızın ilk yapılandırma ile ilgili sorunları tanılamak için tercih **kaldırma ve my paketi yeniden** üzerinde **hata ayıklama** yeniden oluşturmak için özellik sayfası bir hata ayıklama başlattığınızda, özgün yükleme. Visual C++ ve JavaScript projeleri için bu seçenek kullanılamaz.  
  
###  <a name="BKMK__Optional__Disable_authentication_requirement_to_start_the_remote_debugger"></a> (İsteğe bağlı) Uzaktan hata ayıklayıcı başlatmak için kimlik doğrulama gereksinimini devre dışı bırak  
  
 Varsayılan olarak, uzaktan hata ayıklayıcı seçtiğinizde çalıştırmak için kimlik bilgilerini sağlamanız gerektiğini **uzak makine** dağıtım hedefi olarak.
  
> [!IMPORTANT]
>  Uzaktan hata ayıklayıcı hiçbir kimlik doğrulama ile çalıştıran seçebilirsiniz, ancak bu modu kesinlikle önerilmez. Bu modda çalıştırdığınızda, ağ güvenliği yoktur. Yalnızca ağ kötü amaçlı kod veya saldırgan trafik risk kullanılmadığından emin olduğunuzda hiçbir kimlik doğrulamasını seçin.  
  
 Kimlik doğrulama gereksinimini kaldırmak için:  
  
1.  Visual C# ve Visual Basic uygulamaları için **uzak makine** olarak **hedef aygıt** üzerinde **hata ayıklama** özellik sayfası olarak ayarlayın ve ardından **kimlik doğrulama modu**  için **hiçbiri** veya **Evrensel (şifrelenmemiş Protokolü)**.
  
2.  Visual C++ ve JavaScript uygulamaları için **uzak makine** olarak **hedef aygıt** üzerinde **hata ayıklama** özellik sayfası olarak ayarlayın ve ardından **gerektirir Kimlik doğrulama** için **hiçbiri** veya **Evrensel (şifrelenmemiş Protokolü)**.  

    **Evrensel (şifrelenmemiş Protokolü)** uzak bir aygıta dağıtırken kullanımı içindir. Şu anda bu IOT cihazları, Xbox aygıtları ve HoloLens aygıtları yanı sıra oluşturucuları güncelleştirme veya daha yeni bilgisayarlar içindir. Evrensel (şifrelenmemiş Protokolü) yalnızca güvenilen ağlarda kullanılmalıdır. Hata ayıklama bağlantıyı kesecek ve geliştirme ile uzak makine arasında aktarılan veriler değiştirmek kötü amaçlı kullanıcılar savunmasızdır.  
  
##  <a name="BKMK_Start_the_debugging_session"></a> Hata ayıklama oturumu Başlat  
  
###  <a name="BKMK_Start_debugging__F5_"></a> (F5) hata ayıklamayı Başlat  
 Seçtiğinizde **hata ayıklamayı Başlat** (klavye: F5) üzerinde **hata ayıklama** menüsünde, Visual Studio başlatır uygulama hata ayıklayıcısı ekli. Yürütme bir kesme noktası ulaşıldığında, el ile bir özel durum oluştu, yürütme, askıya veya uygulama sona kadar devam eder.  
  
###  <a name="BKMK_Start_debugging__F5__but_delay_the_app_start"></a> (F5) hata ayıklamayı Başlat ancak uygulama başlatma gecikmesi  
 Hata ayıklama modunda çalıştırın, ancak başlatılsın hata ayıklayıcı dışında bir yöntem tarafından uygulamanın ayarlayabilirsiniz. Örneğin, başlatma Başlat menüsünden, uygulamanızın hatalarını ayıklama veya uygulama başlatmadan bir arka plan işlemi uygulamasında hata ayıklama isteyebilirsiniz. Uygulama başlangıcı geciktirmek için şunu yapın:  
  
-   Üzerinde **hata ayıklama** uygulamanın özellik sayfası (**hata ayıklama** Visual C++ ve JavaScript)  
  
    -   Uygulamalar, Visual C# ve Visual Basic için **değil başlatın, ancak başlatıldığında kodum hata ayıklama**.  
  
    -   Uygulamalar, Visual C++ ve JavaScript için **Evet** gelen **uygulama Başlat** listesi.  
  
-   Seçin **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: F5).  
  
-   Uygulamanızı bir yürütme sözleşme Başlat menüsünden veya başka bir yordam başlatın.  
  
 Uygulama hata ayıklama modunda başlatır. Yürütme bir kesme noktası ulaşıldığında, el ile işlenmeyen bir özel durum oluşur, yürütme, askıya veya uygulama sona kadar devam eder.  
  
 Arka plan görevleri hata ayıklama hakkında daha fazla bilgi için bkz: [tetikleyici askıya alma, sürdürme ve arka plan olaylarını UWP uygulamalar için)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).  
  
###  <a name="BKMK_Start_an_installed_app_in_the_debugger"></a> Hata Ayıklayıcısı'ndaki yüklü bir uygulamayı Başlat  
F5 kullanarak hata ayıklama başlattığınızda, Visual Studio oluşturur ve uygulamayı dağıtır, hata ayıklama modunda çalıştırmak için uygulamayı ayarlar ve ardından başlatır. Bir cihazda zaten yüklü olan bir uygulamayı başlatmak için kullanmak **yüklü uygulama paketi Debug** iletişim kutusu. Bu yordam, Microsoft Store yüklü olduğu bir uygulama hata ayıklama gerektiğinde veya uygulama için kaynak dosyaları varsa, ancak uygulama için bir Visual Studio projesini yok kullanışlıdır. Örneğin, Visual Studio projeleri veya çözümleri kullanmayan bir özel yapı sistemi olabilir.  
  
Uygulama yerel cihazda yüklenebilir veya bir uzak cihazda olabilir.  Uygulamanın hemen başlatmak için ya da onu Başlat menüsünden veya bir etkinleştirme sözleşme tarafından bir arka plan işlemi hata ayıklama istediğinizde hata ayıklama modunda çalıştırmak için uygulamayı de ayarlayabilirsiniz gibi başka bir işlem veya yöntemi tarafından başlatılırken hata ayıklayıcısı'ndaki çalıştırmak için ayarlayabilir. Uygulama başlatmadan. Daha fazla bilgi için bkz: [tetikleyici askıya alma, sürdürme ve arka plan olaylarını UWP uygulamalar için)](../debugger/how-to-trigger-suspend-resume-and-background-events-for-windows-store-apps-in-visual-studio.md).  
  
Hata Ayıklayıcısı'ndaki yüklü bir uygulamayı başlatmak için tercih **hata ayıklama**, ardından **diğer hata ayıklama hedeflerini**ve ardından **yüklü uygulama paketi Debug**. Ek yönergeler için bkz: [yüklü uygulama paketi Debug](../debugger/debug-installed-app-package.md).

###  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a> Hata ayıklayıcıyı çalışan bir UWP uygulaması Ekle  

Çalışan bir UWP uygulamasında hata ayıklama tercih **hata ayıklama**, ardından **diğer hata ayıklama hedeflerini**ve ardından **yüklü uygulama paketi hata ayıklama**. Ek yönergeler için bkz: [yüklü uygulama paketi Debug](../debugger/debug-installed-app-package.md).
  
###  <a name="BKMK_Attach_the_debugger_to_a_running_app_"></a> Hata ayıklayıcıyı çalışan Windows 8.x uygulamasına Bağla
 Hata ayıklayıcısını için bir [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulama, hata ayıklama modunda çalıştırmak için uygulamayı ayarlamak için Debuggable Paket Yöneticisi kullanmalıdır. Debuggable Paket Yöneticisi ile uzak araçlar Visual Studio için yüklenir.  
  
 Hata ayıklayıcı için uygulama ekleme yararlıdır yüklendiği bir uygulama gibi bir zaten yüklü uygulama hata ayıklama gerektiğinde [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)]. Uygulama için kaynak dosyaları varsa, ancak uygulama için bir Visual Studio projesini olmayan ekleme gereklidir. Örneğin, Visual Studio projeleri veya çözümleri kullanmayan bir özel yapı sistemi olabilir.  
  
 Hata ayıklayıcı bir uygulamaya eklemek için aşağıdaki adımları gerekir:  
  
1.  Hata ayıklama modunda çalıştırmak için uygulamayı ayarlayın. Uygulama çalışmıyorken Bunun yapılması gerekir.  
  
2.  Uygulamayı başlatın. Uygulama başlangıç ekranında, yürütme sözleşme ya da başka bir yöntem başlatabilirsiniz.  
  
3.  Hata ayıklayıcısını çalışan uygulamaya ekleyin.  
  
####  <a name="BKMK_Set_the_app_to_run_in_debug_mode"></a> Hata ayıklama modunda çalıştırmak için uygulamayı Ayarla  
  
1.  Uzak araçlar Visual Studio için uygulamanın yüklendiği cihaza yükleyin. Bkz: [uzak araçları yükleme](../debugger/remote-debugging.md).  
  
2.  Başlangıç ekranında aramak `Debuggable Package Manager` ve sonra başlatın.  
  
     AppxDebug cmdlet'i için doğru yapılandırılmış bir PowerShell penceresi görüntülenir.  
  
3.  Bir uygulama hata ayıklamayı etkinleştirmek için uygulama PackageFullName tanıtıcısı belirtmeniz gerekir. PackageFullName içeren tüm uygulamaların bir listesini görüntülemek için şunu yazın `Get-AppxPackage` PowerShell komut isteminde.  
  
4.  PowerShell komut isteminde, girin `Enable-AppxDebug` *PackageFullName* nerede *PackageFullName* uygulamanın PackageFullName tanımlayıcısıdır.  
  
####  <a name="BKMK_Attach_the_debugger"></a> Hata ayıklayıcıyı Ekle  
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

    > [!NOTE]
    >  Diğer uygulama türlerinin aksine, JavaScript uygulamaları wwahost.exe işlem örneğini çalıştırın. Uygulamaya taktığınızda diğer JavaScript uygulamaları çalıştırıyorsanız, uygulamayı çalıştıran wwahost.exe sayısal işlem kimliğini (PID) bilmeniz gerekir.  
    >   
    >  Bu durumu düzeltmek için kolay bir JavaScript uygulamaları kapatmaya yoludur. Aksi takdirde, uygulamayı başlatın ve wwahost.exe işlem kimlikleri not alın önce Windows Görev Yöneticisi'ni açın. Uygulamasındaki ekleme işlemi belirttiğinizde **kullanılabilir işlemler** iletişim kutusunda, uygulama wwahost.exe not ettiğiniz olanları farklı bir kimlik olacaktır.  
  
5.  Seçin **Attach**.  
  
 Visual Studio hata ayıklayıcı işleme ekler. Yürütme bir kesme noktası ulaşıldığında, el ile işlenmeyen bir özel durum oluşur, yürütme, askıya veya uygulama sona kadar devam eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio uygulamalarında hata ayıklama](../debugger/debug-store-apps-in-visual-studio.md)   