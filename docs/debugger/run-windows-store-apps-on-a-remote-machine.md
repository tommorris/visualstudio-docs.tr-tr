---
title: Uzak makinede UWP uygulamaları çalıştırma | Microsoft Docs
ms.custom: ''
ms.date: 01/05/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 0f6814d6-cd0d-49f3-b501-dea8c094b8ef
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 2845057fe970299d249d580d97b557a5ed311fc0
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38795978"
---
# <a name="run-uwp-apps-on-a-remote-machine-in-visual-studio"></a>Visual Studio'da uzak makinede UWP uygulamaları çalıştırma
  
Uzak makinede UWP uygulaması çalıştırmak için Visual Studio için Uzak Araçlar'ı kullanarak kendisine eklemeniz gerekir. Uzak Araçlar, hata ayıklama, profil ve Visual Studio çalıştıran ikinci bir bilgisayardan bir cihazda çalışan bir UWP uygulaması test çalıştırmak etkinleştirin. Visual Studio bilgisayarı UWP uygulamaları dokunmatik, coğrafi konum ve fiziksel yön gibi belirli işlevleri desteklemiyorsa, uzak bir cihazda çalıştırma özellikle etkili olabilir. Bu konu başlığı altında yapılandırmak ve bir uzak oturumu başlatmak için gereken yordamları açıklar.

Uzak cihaza dağıttığınızda, bazı senaryolarda, uzak Araçlar otomatik olarak yüklenir.

- Windows 10 Creators Update ve üzeri sürümleri çalıştıran bilgisayarlar için Uzak Araçlar otomatik olarak yüklenir.
- Windows 10 Xbox, IOT ve HoloLens cihazlar için Uzak Araçlar otomatik olarak yüklenir.
- Windows 10 Mobile, telefon için fiziksel olarak bağlı gerekir, etkinleştirmelisiniz [Geliştirici modu](/windows/uwp/get-started/enable-your-device-for-development) ve seçmelisiniz **cihaz** hata ayıklama hedefi olarak. Uzak araçları gerekli veya desteklenmiyor.

Hata ayıklama yapılabilmesi öncesi oluşturan kişinin güncelleştirme Windows sürümünü çalıştıran Windows 10 bilgisayarları için Uzak Araçlar uzak makinede el ile yüklemeniz gerekir. Bu konu başlığı altındaki yönergeleri izleyin. 
  
##  <a name="BKMK_Prerequisites"></a> Önkoşullar  
 Uzak bir cihazda hata ayıklamak için:  
  
- Uzak cihaz ve Visual Studio bilgisayarı gereken bir ağ üzerinden bağlı veya doğrudan USB veya Ethernet kablosu ile bağlı. Internet üzerinden hata ayıklama desteklenmez.  

- Etkinleştirmelisiniz [Geliştirici modu](/windows/uwp/get-started/enable-your-device-for-development). 
  
- Windows 10 Creator'ın güncelleştirme öncesi bir Windows 10 sürümünü çalıştıran Windows 10 bilgisayarları için yapmanız gerekenler [yükleyin ve uzaktan hata ayıklama bileşenleri çalıştırın](#BKMK_download).
  
##  <a name="BKMK_Security"></a> Güvenlik  
Varsayılan olarak, **Evrensel (şifrelenmemiş Protokolü)** Windows 10'da kullanılır. Bu protokol, yalnızca güvenilen ağlarda kullanılmalıdır. Hata ayıklama bağlantıyı kesebilir ve değiştirmek geliştirme ve uzak makine arasında aktarılan veriler kötü amaçlı kullanıcılara savunmasızdır.
  
> [!WARNING]
>  Kimlik doğrulama modu ayarlamak, ağ güvenliği olan **Evrensel (şifrelenmemiş Protokolü)** veya **hiçbiri**. Ağ riskinden kötü amaçlı veya tehlikeli trafik olmadığından emin olması durumunda bu modları seçin.  
  
##  <a name="BKMK_DirectConnect"></a> USB kablosu kullanarak doğrudan bağlanma 

Windows 10'da seçerek USB bağlantılı bir aygıta dağıtabilirsiniz **cihaz** yerine **uzak makine** dağıtım hedefi olarak (Bunu yapmak için **standart** araç çubuğu veya hata ayıklama özellikleri sayfasında).

##  <a name="BKMK_ConnectVS"></a> Uzaktan hata ayıklama için Visual Studio projesini yapılandırma  
 Proje özelliklerinde Bağlanılacak uzak cihazı belirtin. Yordam programlama diline bağlı olarak farklılık gösterir. Uzak cihaz ağ adını yazabilir veya dosyayı seçin **uzak bağlantı** iletişim kutusu.  
  
 ![Select uzaktan hata ayıklayıcı bağlantısı iletişim kutusu](../debugger/media/vsrun_selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")  
  
 İletişim kutusu yalnızca Visual Studio bilgisayarının yerel alt ağda olan ve uzaktan hata ayıklayıcıyı çalıştıran cihazları listeler.  
  
> [!TIP]
>  Bir uzak cihaza bağlanırken sorun yaşıyorsanız, cihazın IP adresini girmeyi deneyin. Bir cihazın IP adresini belirlemek için bir komut penceresi açın ve ardından yazın **ipconfig**. IP adresi olarak listelenip listelenmediğini **IPv4 adresi**.  
  
###  <a name="BKMK_Choosing_the_remote_device_for_C__and_Visual_Basic_projects"></a> C# ve Visual Basic projeleri için Uzak cihaz seçin  
  
1.  Çözüm Gezgini'nde proje adını seçin ve ardından **özellikleri** kısayol menüsünden.  
  
2.  Seçin **hata ayıklama**.  
  
3.  Seçin **uzak makine** gelen **hedef cihaz** listesi.  
  
4.  Uzak cihaz ağ adını **uzak makine** kutusuna veya seçin **Bul** cihazı seçin **uzaktan hata ayıklayıcı bağlantısı Seç** iletişim kutusu. 

    ![Uzaktan hata ayıklama için proje özellikleri yönetilen](../debugger/media/vsrun_managed_projprop_remote.png "VSRUN_Managed_ProjProp_Remote")  
  
###  <a name="BKMK_Choosing_the_remote_device_for_JavaScript_and_C___projects"></a> JavaScript ve C++ projeleri için Uzak cihaz seçin  
  
1.  Çözüm Gezgini'nde proje adını seçin ve ardından **özellikleri** kısayol menüsünden.  
  
2.  Genişletin **yapılandırma özellikleri** düğümünü ve ardından **hata ayıklama**.  
  
3.  Seçin **uzaktan hata ayıklayıcı** gelen **başlatmak için hata ayıklayıcı** listesi.  
  
4.  Uzak cihaz ağ adını **makine adı** kutusuna veya kutusuna cihazı seçin aşağı oku seçin **uzaktan hata ayıklayıcı bağlantısı Seç** iletişim kutusu.  

    ![C&#43; &#43; proje uzaktan hata ayıklama özellikleri](../debugger/media/vsrun_cpp_projprop_remote.png "VSRUN_CPP_ProjProp_Remote")
  
## <a name="BKMK_download"></a> Uzak araçları indirme ve yükleme (ön Creators Update)

Windows 10 güncelleştirme sürümleri öncesi oluşturan kişinin kullanıyorsanız, ardından bu yönergeleri izleyin. Aksi takdirde, bu bölümü atlayabilirsiniz.

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
### <a name="BKMK_setup"></a> Uzaktan hata ayıklayıcı ayarlayın

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]  
  
##  <a name="BKMK_RunRemoteDebug"></a> Bir uzak hata ayıklama oturumu başlatma  
 Başlatın, durdurun ve uzaktan hata ayıklama oturumu, bir yerel oturumda olduğu gibi gidin. Pre-oluşturanın güncelleştirme sürümlerinde Windows 10, uzaktan hata ayıklama İzleyicisi, uzak cihazda çalıştığından emin olun.  
  
 Ardından **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: F5). Proje yeniden derlenen, ardından dağıtılan ve uzak cihaz üzerinde başlatıldı. Hata ayıklayıcı kesme noktalarında yürütmeyi askıya alır ve içine, üzerine ve dışına kodunuzu geçebilirsiniz. Seçin **hata ayıklamayı Durdur** hata ayıklama oturumunuzu bitirmek ve uzak uygulamayı kapatmak için.
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş uzak dağıtım seçenekleri](/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps#advanced-remote-deployment-options)  
 [Visual Studio ile UWP uygulamalarını test etme](../test/testing-store-apps-with-visual-studio.md)   
 [Visual Studio'da uygulamalarının hatalarını ayıklama](../debugger/debug-store-apps-in-visual-studio.md)
