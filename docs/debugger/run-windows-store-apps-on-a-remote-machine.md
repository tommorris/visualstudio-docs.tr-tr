---
title: "Bir uzak makinede UWP ve Windows 8.1 uygulamalarını çalıştırma | Microsoft Docs"
ms.custom: 
ms.date: 01/05/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 0f6814d6-cd0d-49f3-b501-dea8c094b8ef
caps.latest.revision: "43"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 3e27aae0b9a8e57575015d1d8d5baee3803959a9
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="run-uwp-and-windows-81-apps-on-a-remote-machine"></a>Bir uzak makinede UWP ve Windows 8.1 uygulamaları çalıştırma  
  
Uzak makinede bir UWP veya Windows 8.1 uygulamasını çalıştırmak için Visual Studio için Uzak araçları kullanarak ilişkilendirmeniz gerekir. Uzak araçları çalıştırmak için profil, hata ayıklama ve Visual Studio çalıştıran ikinci bir bilgisayardan bir cihazda çalışan bir UWP uygulaması test etkinleştirin. Visual Studio bilgisayar UWP uygulamaları dokunma, coğrafi konum ve fiziksel yönü gibi belirli işlevleri desteklemediğinde uzak cihazda çalışan özellikle yararlı olabilir. Bu konuda, yapılandırma ve uzak bir oturum başlatmak için yordamlar açıklanmaktadır.

Uzak bir cihaza dağıttığınızda, bazı senaryolarda, uzak Araçlar otomatik olarak yüklenir.

- Windows 10 oluşturucuları güncelleştirme ve sonraki sürümlerini çalıştıran bilgisayarlar için Uzak Araçlar otomatik olarak yüklenir.
- Windows 10 Xbox, IOT ve HoloLens cihazlar için Uzak araçları otomatik olarak yüklenir.
- Windows Phone için telefon fiziksel olarak bağlı olmalıdır, ya da yüklemeli bir [Geliştirici lisansı](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh974578.aspx) (Windows Phone 8 ve 8.1) etkinleştirmek veya [geliştirici modunu](/windows/uwp/get-started/enable-your-device-for-development) (Windows Mobile 10), ve gerekir seçin **aygıt** hata ayıklama hedefi olarak. Uzak Araçlar gerekli veya desteklenen güncelleştirilmez.

Hata ayıklama önce Windows 8.1 bilgisayarları ve Windows 10 bir pre-oluşturanın güncelleştirme Windows sürümünü çalıştıran bilgisayarları için Uzak Araçlar uzak makinede el ile yüklemeniz gerekir. Bu konudaki yönergeleri izleyin. 
  
##  <a name="BKMK_Prerequisites"></a> Önkoşullar  
 Uzak bir cihazda hata ayıklamak için:  
  
-   Uzak aygıt ve Visual Studio bilgisayar ağ üzerinden bağlı veya gerekir doğrudan USB veya Ethernet kablo bağlı. Internet üzerinden hata ayıklama desteklenmez.  

- Uzak aygıt geliştirme için etkinleştirilmesi gerekir.

    - Windows 8 ve Windows 8.1 cihazları için bir [Geliştirici lisansı](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh974578.aspx) uzak cihazda yüklü olmalıdır.
    - Windows 10 cihazlar için etkinleştirmeniz gerekir [geliştirici modunu](/windows/uwp/get-started/enable-your-device-for-development). 
  
-   Windows 10 oluşturanın Güncelleştirme'den önceki bir sürüm olarak Windows 10 çalıştıran Windows 10 bilgisayarları için yapmanız gerekenler [yükleyin ve uzaktan hata ayıklama bileşenleri Çalıştır](#BKMK_download).
  
##  <a name="BKMK_Security"></a>Güvenlik  
Varsayılan olarak, **Evrensel (şifrelenmemiş Protokolü)** üzerinde Windows 10 kullanılır. Bu protokol, yalnızca güvenilen ağlarda kullanılmalıdır. Hata ayıklama bağlantıyı kesecek ve geliştirme ile uzak makine arasında aktarılan veriler değiştirmek kötü amaçlı kullanıcılar savunmasızdır.
  
> [!WARNING]
>  Ağ güvenlik yoktur, kimlik doğrulama modu ayarladığınızda **Evrensel (şifrelenmemiş Protokolü)** veya **hiçbiri**. Yalnızca ağ etkilenir kötü amaçlı veya saldırgan trafiği kullanılmadığından emin olduğunuzda bu modları seçin.  
  
##  <a name="BKMK_DirectConnect"></a>Bir USB kablosu kullanarak doğrudan bağlanma 

Windows 10'seçerek USB bağlantılı bir aygıta dağıtabilirsiniz **aygıt** yerine **uzak makine** dağıtım hedefi olarak (Bunu yapmak için **standart** araç çubuğu veya hata ayıklama özellikleri sayfasında). Doğrudan bağlanmadan önce Windows 8.1 için Uzak araçları cihazda yüklenmesi gerekir.

##  <a name="BKMK_ConnectVS"></a>Uzaktan hata ayıklama için Visual Studio projesi yapılandırın  
 Proje özelliklerinde bağlanmak için uzak aygıt belirtin. Yordam programlama dili bağlı olarak farklılık gösterir. Uzak aygıt ağ adı yazın veya dosyayı seçin **uzak bağlantı** iletişim kutusu.  
  
 ![Select uzaktan hata ayıklayıcı bağlantı iletişim kutusu](../debugger/media/vsrun_selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")  
  
 İletişim kutusu yalnızca Visual Studio bilgisayarın yerel alt ağda olmayan ve uzaktan hata ayıklayıcı çalıştıran aygıtlarını listeler.  
  
> [!TIP]
>  Uzak bir cihaza bağlanma konusunda sorun yaşıyorsanız, aygıtın IP adresi girmeyi deneyin. Bir aygıtın IP adresi belirlemek için bir komut penceresi açın ve ardından yazın **ipconfig**. IP adresi olarak listelenen **IPv4 adresi**.  
  
###  <a name="BKMK_Choosing_the_remote_device_for_C__and_Visual_Basic_projects"></a>C# ve Visual Basic projeleri için uzak aygıt seçin  
  
1.  Çözüm Gezgini'nde proje adını seçin ve ardından **özellikleri** kısayol menüsünden.  
  
2.  Seçin **hata ayıklama**.  
  
3.  Seçin **uzak makine** gelen **hedef aygıt** listesi.  
  
4.  Uzak aygıt ağ adı girin **uzak makine** kutusunda veya seçin **Bul** aygıttan seçmek için **seçin uzaktan hata ayıklayıcı bağlantı** iletişim kutusu. 

    ![Uzaktan hata ayıklama için proje özellikleri yönetilen](../debugger/media/vsrun_managed_projprop_remote.png "VSRUN_Managed_ProjProp_Remote")  
  
###  <a name="BKMK_Choosing_the_remote_device_for_JavaScript_and_C___projects"></a>JavaScript ve C++ projeleri için uzak aygıt seçin  
  
1.  Çözüm Gezgini'nde proje adını seçin ve ardından **özellikleri** kısayol menüsünden.  
  
2.  Genişletme **yapılandırma özellikleri** düğümünü ve ardından **hata ayıklama**.  
  
3.  Seçin **uzaktan hata ayıklayıcı** gelen **başlatmak için hata ayıklayıcı** listesi.  
  
4.  Uzak aygıt ağ adı girin **makine adı** kutusu veya aygıttan seçmek için kutusunda aşağı oku seçin **seçin uzaktan hata ayıklayıcı bağlantı** iletişim kutusu.  

    ![C# 43; &#43; Proje özellikleri uzaktan hata ayıklama için](../debugger/media/vsrun_cpp_projprop_remote.png "VSRUN_CPP_ProjProp_Remote")
  
## <a name="BKMK_download"></a>Uzak araçları yükleyip (ön oluşturucuları güncelleştirmesi)

Windows 8.1 veya Windows 10 'un bir pre-oluşturanın güncelleştirme sürümleri kullanıyorsanız, bu yönergeleri izleyin. Aksi takdirde, bu bölümü atlayabilirsiniz.

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
### <a name="BKMK_setup"></a>Uzaktan hata ayıklayıcı ayarlayın

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]  
  
##  <a name="BKMK_RunRemoteDebug"></a>Uzaktan hata ayıklama oturumu Başlat  
 Başlatmak, durdurmak ve bir yerel oturum yaptığınız gibi bir uzaktan hata ayıklama oturumunda gezinme. Pre-oluşturanın güncelleştirme sürümlerinde Windows 10, uzaktan hata ayıklama İzleyicisi uzak cihazda çalışır durumda olduğundan emin olun.  
  
 Ardından **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: F5). Projeyi yeniden derlenebileceğini gösterir, ardından dağıtılan ve uzak cihazda başlatıldı. Hata ayıklayıcı kesme noktalarında durduran ve, üzerinden, kodun içine ve dışına, geçebilirsiniz. Seçin **durdurma hata ayıklama** hata ayıklama oturumunuzu sonlandırmak ve uzak uygulamasını kapatın. Daha fazla bilgi için bkz: [Visual Studio uygulamalarında hata ayıklama](../debugger/debug-store-apps-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio ile UWP uygulamaları test etme](../test/testing-store-apps-with-visual-studio.md)   
 [Visual Studio uygulamalarında hata ayıklama](../debugger/debug-store-apps-in-visual-studio.md)