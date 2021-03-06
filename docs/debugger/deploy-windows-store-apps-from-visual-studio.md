---
title: Visual Studio'dan UWP uygulamaları dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 01/16/2018
ms.technology: vs-ide-debug
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
- uwp
ms.openlocfilehash: fda8e9b09fadfb57145331b1fc09acc1687e58e7
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31477287"
---
# <a name="deploy-uwp-apps-from-visual-studio"></a>Visual Studio'dan UWP uygulamaları dağıtma
  
 Visual Studio dağıtım işlevselliği oluşturur ve Visual Studio ile hedef cihazda oluşturulan UWP uygulamaları kaydeder. Tam olarak nasıl uygulama kayıtlı hedef aygıt yerel veya uzak olduğuna bağlıdır:  
  
-   Hedef yerel Visual Studio makine olduğunda, Visual Studio derleme klasörü uygulamadan kaydeder.  
  
-   Hedef bir uzak aygıt olduğunda, Visual Studio uzak makineye gerekli dosyaları kopyalar ve bu cihaza uygulamanın kaydeder.  
  
 Kullanarak uygulamanızı Visual Studio'da hata ayıklarken dağıtım otomatik **hata ayıklamayı Başlat** seçeneği (klavye: F5) veya **hata ayıklama olmadan Başlat** seçeneği (klavye: CTRL + F5). Ayrıca, uygulamanızı el ile dağıtabilirsiniz. El ile dağıtımı, aşağıdaki senaryolarda kullanışlıdır:  
  
-   Bir yerel veya uzak makinede test geçici.  
  
-   Hata ayıklamak istediğiniz başka bir uygulama başlatacak bir uygulamayı dağıtma.  
  
-   Başlatıldığında hata ayıklaması bir uygulama başka bir uygulama veya yöntemi tarafından dağıtma.
  
##  <a name="BKMK_How_to_deploy_a_Windows_Store_app"></a> Bir UWP uygulaması dağıtma  
 El ile bir uygulama dağıtımı basit bir işlemdir:  
  
1.  Uzak bir aygıta dağıtıyorsanız, uygulamanın başlangıç projesi özellik Proje sayfasında adını veya aygıtın IP adresi belirtin. (Bu öğeler yapmak için bu konudaki daha aşağı listelenen adımları.).  
  
2.  Hata ayıklayıcı Visual Studio araç çubuğunda, dağıtım hedef aşağı açılan listeden seçin **hata ayıklamayı Başlat** düğmesi.  
  
     ![Yerel makine üzerinde çalışan](../debugger/media/vsrun_f5_local.png "VSRUN_F5_Local")  
  
3.  Üzerinde **yapı** menüsünde seçin **Dağıt**  
  
##  <a name="BKMK_How_to_specify_a_remote_device"></a> Uzak aygıt belirtme  

**Önkoşullar**  
  
Bir Windows 10 uzak cihazda etkinleştirmeniz gerekir [geliştirici modunu](/windows/uwp/get-started/enable-your-device-for-development). Oluşturanın güncelleştirme çalıştıran Windows 10 cihazlarda ya da uygulamanızı dağıtma daha sonra uzak Araçlar otomatik olarak yüklenir. Daha fazla bilgi için bkz: [yüklü uygulama paketi Debug](../debugger/debug-installed-app-package.md).

> [!NOTE]
> Pre-oluşturanın güncelleştirme sürümleri, Windows 10 için Visual Studio uzak Araçlar uzak cihazda yüklü olmalıdır ve uzaktan hata ayıklayıcı çalıştırıyor olması gerekir.
  
Dağıtım uzaktan hata ayıklayıcı ağ kanalının uzak aygıta uygulama dosyaları göndermek için kullanır.  
  
#### <a name="to-specify-a-remote-device"></a>Uzak aygıt belirtmek için  
  
1.  Başlangıç projesi olarak hata ayıklama özellik sayfasında, ad veya bir uzak dağıtım hedef IP adresini belirtin.  
  
2.  Hata ayıklama özellik sayfası açmak için Çözüm Gezgini'nde proje seçin ve ardından **özellikleri** kısayol menüsünden.  
  
3.  Ardından **hata ayıklama** özellik sayfaları penceresi düğümde.

4. İçin **hedef aygıt**seçin **uzak makine**.

5. Altında **uzak makine**, tıklatın **Bul**.
  
4.  Adı veya IP adresini uzak aygıt yazabilir veya aygıttan seçebilirsiniz **uzak bağlantı** iletişim kutusu.  
  
     ![Select uzaktan hata ayıklayıcı bağlantı iletişim kutusu](../debugger/media/vsrun_selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")  
  
     **Uzak bağlantı** iletişim kutusunda, yerel ağ alt ağı ve Visual Studio makineye Ethernet kablosu tarafından doğrudan bağlı herhangi bir aygıt aygıtları görüntüler.  
  
 **Uzak aygıt bir JavaScript veya Visual C++ proje sayfasında belirtme**  
  
 ![C&#43; &#43; proje uzaktan hata ayıklama için özellikleri](../debugger/media/vsrun_cpp_projprop_remote.png "VSRUN_CPP_ProjProp_Remote")  
  
1.  Seçin **uzaktan hata ayıklayıcı** gelen **başlatmak için hata ayıklayıcı** listesi.  
  
2.  Uzak aygıt ağ adı girin **makine adı** kutusu. Veya, aygıt uzaktan hata ayıklayıcı bağlantı seçin iletişim kutusundan seçmek için kutusunda aşağı oku seçebilirsiniz.  
  
 **Uzak aygıt bir Visual C# ve Visual Basic proje sayfasında belirtme**  
  
 ![Uzaktan hata ayıklama için proje özellikleri yönetilen](../debugger/media/vsrun_managed_projprop_remote.png "VSRUN_Managed_ProjProp_Remote")  
  
1.  Seçin **uzak makine** gelen **hedef aygıt** listesi.  
  
2.  Uzak aygıt ağ adını girin **uzak makine** kutusu veya tıklatın **bulmak** aygıttan seçmek için **seçin uzaktan hata ayıklayıcı bağlantı** iletişim kutusu.  
  
##  <a name="BKMK_Deployment_options"></a> Dağıtım seçenekleri  
 Başlangıç projesi hata ayıklama özellik sayfasında aşağıdaki dağıtım seçeneklerini ayarlayabilirsiniz.  
  
 **Ağ geri döngü izin ver**  
 Güvenlik nedeniyle, bir UWP veya [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] üzerinde yüklü olduğu cihaz ağ çağrı yapmak için standart bir biçimde yüklü app verilmez. Varsayılan olarak, bu kural dağıtılan uygulama için bir muafiyet Visual Studio dağıtımı oluşturur. Bu istisna tek bir makinede iletişim yordamlarını test etmenizi sağlar. Uygulamanıza göndermeden önce [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)], uygulamanızı muafiyet olmadan test etmeniz gerekir.  
  
 Uygulama ağ geri döngü muafiyet kaldırmak için:  
  
-   C# ve VB hata ayıklama özellik sayfası temizleyin **izin ağ geri döngü** onay kutusu.  
  
-   JavaScript ve hata ayıklama özellik sayfası **izin ağ geri döngü** değeri **Hayır**.  
  
 **Başlatma değil, ancak (C# ve VB) başlatıldığında kodum hata ayıklama / başlatma uygulama (JavaScript ve C++)**  
 Uygulama zaman başlatılan bir hata ayıklama oturumu otomatik olarak başlayacak şekilde dağıtımını yapılandırmak için:  
  
-   C# ve VB hata ayıklama özellik sayfası denetleyin **değil başlatın, ancak başlatıldığında kodum hata ayıklama** onay kutusu.  
  
-   JavaScript ve hata ayıklama özellik sayfası **uygulama Başlat** değeri **Evet**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş uzaktan dağıtım seçenekleri](/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps#advanced-remote-deployment-options)  
 [Yüklü uygulama paketi hata ayıklama](../debugger/debug-installed-app-package.md)   
 [Visual Studio'dan uygulamaları çalıştırma](../debugger/run-store-apps-from-visual-studio.md)