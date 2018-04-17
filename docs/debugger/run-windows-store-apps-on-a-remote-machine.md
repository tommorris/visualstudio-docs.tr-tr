---
title: Bir uzak makinede UWP uygulamaları çalıştırma | Microsoft Docs
ms.custom: ''
ms.date: 01/05/2018
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: 6ba0edc3c94ae3586615086d668df2c3bf9eaddf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="run-uwp-apps-on-a-remote-machine-in-visual-studio"></a>Visual Studio'da uzaktaki bir makinede UWP uygulamaları çalıştırma
  
Uzak makinede bir UWP uygulaması çalıştırmak için Visual Studio için Uzak araçları kullanarak ilişkilendirmeniz gerekir. Uzak araçları çalıştırmak için profil, hata ayıklama ve Visual Studio çalıştıran ikinci bir bilgisayardan bir cihazda çalışan bir UWP uygulaması test etkinleştirin. Visual Studio bilgisayar UWP uygulamaları dokunma, coğrafi konum ve fiziksel yönü gibi belirli işlevleri desteklemediğinde uzak cihazda çalışan özellikle yararlı olabilir. Bu konuda, yapılandırma ve uzak bir oturum başlatmak için yordamlar açıklanmaktadır.

Uzak bir cihaza dağıttığınızda, bazı senaryolarda, uzak Araçlar otomatik olarak yüklenir.

- Windows 10 oluşturucuları güncelleştirme ve sonraki sürümlerini çalıştıran bilgisayarlar için Uzak Araçlar otomatik olarak yüklenir.
- Windows 10 Xbox, IOT ve HoloLens cihazlar için Uzak araçları otomatik olarak yüklenir.
- Windows Mobile 10, telefon için fiziksel olarak bağlı gerekir, etkinleştirmelisiniz [geliştirici modunu](/windows/uwp/get-started/enable-your-device-for-development) ve seçmeniz gerekir **aygıt** hata ayıklama hedefi olarak. Uzak Araçlar gerekli veya desteklenen güncelleştirilmez.

Hata ayıklama önce bir pre-oluşturanın güncelleştirme Windows sürümü çalıştıran Windows 10 bilgisayarları için Uzak araçları uzak makinede el ile yüklemeniz gerekir. Bu konudaki yönergeleri izleyin. 
  
##  <a name="BKMK_Prerequisites"></a> Önkoşullar  
 Uzak bir cihazda hata ayıklamak için:  
  
- Uzak aygıt ve Visual Studio bilgisayar ağ üzerinden bağlı veya gerekir doğrudan USB veya Ethernet kablo bağlı. Internet üzerinden hata ayıklama desteklenmez.  

- Etkinleştirmelisiniz [geliştirici modunu](/windows/uwp/get-started/enable-your-device-for-development). 
  
- Windows 10 oluşturanın Güncelleştirme'den önceki bir sürüm olarak Windows 10 çalıştıran Windows 10 bilgisayarları için yapmanız gerekenler [yükleyin ve uzaktan hata ayıklama bileşenleri Çalıştır](#BKMK_download).
  
##  <a name="BKMK_Security"></a> Güvenlik  
Varsayılan olarak, **Evrensel (şifrelenmemiş Protokolü)** üzerinde Windows 10 kullanılır. Bu protokol, yalnızca güvenilen ağlarda kullanılmalıdır. Hata ayıklama bağlantıyı kesecek ve geliştirme ile uzak makine arasında aktarılan veriler değiştirmek kötü amaçlı kullanıcılar savunmasızdır.
  
> [!WARNING]
>  Ağ güvenlik yoktur, kimlik doğrulama modu ayarladığınızda **Evrensel (şifrelenmemiş Protokolü)** veya **hiçbiri**. Yalnızca ağ etkilenir kötü amaçlı veya saldırgan trafiği kullanılmadığından emin olduğunuzda bu modları seçin.  
  
##  <a name="BKMK_DirectConnect"></a> Bir USB kablosu kullanarak doğrudan bağlanma 

Windows 10'seçerek USB bağlantılı bir aygıta dağıtabilirsiniz **aygıt** yerine **uzak makine** dağıtım hedefi olarak (Bunu yapmak için **standart** araç çubuğu veya hata ayıklama özellikleri sayfasında).

##  <a name="BKMK_ConnectVS"></a> Uzaktan hata ayıklama için Visual Studio projesi yapılandırın  
 Proje özelliklerinde bağlanmak için uzak aygıt belirtin. Yordam programlama dili bağlı olarak farklılık gösterir. Uzak aygıt ağ adı yazın veya dosyayı seçin **uzak bağlantı** iletişim kutusu.  
  
 ![Select uzaktan hata ayıklayıcı bağlantı iletişim kutusu](../debugger/media/vsrun_selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")  
  
 İletişim kutusu yalnızca Visual Studio bilgisayarın yerel alt ağda olmayan ve uzaktan hata ayıklayıcı çalıştıran aygıtlarını listeler.  
  
> [!TIP]
>  Uzak bir cihaza bağlanma konusunda sorun yaşıyorsanız, aygıtın IP adresi girmeyi deneyin. Bir aygıtın IP adresi belirlemek için bir komut penceresi açın ve ardından yazın **ipconfig**. IP adresi olarak listelenen **IPv4 adresi**.  
  
###  <a name="BKMK_Choosing_the_remote_device_for_C__and_Visual_Basic_projects"></a> C# ve Visual Basic projeleri için uzak aygıt seçin  
  
1.  Çözüm Gezgini'nde proje adını seçin ve ardından **özellikleri** kısayol menüsünden.  
  
2.  Seçin **hata ayıklama**.  
  
3.  Seçin **uzak makine** gelen **hedef aygıt** listesi.  
  
4.  Uzak aygıt ağ adı girin **uzak makine** kutusunda veya seçin **Bul** aygıttan seçmek için **seçin uzaktan hata ayıklayıcı bağlantı** iletişim kutusu. 

    ![Uzaktan hata ayıklama için proje özellikleri yönetilen](../debugger/media/vsrun_managed_projprop_remote.png "VSRUN_Managed_ProjProp_Remote")  
  
###  <a name="BKMK_Choosing_the_remote_device_for_JavaScript_and_C___projects"></a> JavaScript ve C++ projeleri için uzak aygıt seçin  
  
1.  Çözüm Gezgini'nde proje adını seçin ve ardından **özellikleri** kısayol menüsünden.  
  
2.  Genişletme **yapılandırma özellikleri** düğümünü ve ardından **hata ayıklama**.  
  
3.  Seçin **uzaktan hata ayıklayıcı** gelen **başlatmak için hata ayıklayıcı** listesi.  
  
4.  Uzak aygıt ağ adı girin **makine adı** kutusu veya aygıttan seçmek için kutusunda aşağı oku seçin **seçin uzaktan hata ayıklayıcı bağlantı** iletişim kutusu.  

    ![C&#43; &#43; proje uzaktan hata ayıklama için özellikleri](../debugger/media/vsrun_cpp_projprop_remote.png "VSRUN_CPP_ProjProp_Remote")
  
## <a name="BKMK_download"></a> Uzak araçları yükleyip (ön oluşturucuları güncelleştirmesi)

Windows 10 'un bir pre-oluşturanın güncelleştirme sürümleri kullanıyorsanız, bu yönergeleri izleyin. Aksi takdirde, bu bölümü atlayabilirsiniz.

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
### <a name="BKMK_setup"></a> Uzaktan hata ayıklayıcı ayarlayın

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]  
  
##  <a name="BKMK_RunRemoteDebug"></a> Uzaktan hata ayıklama oturumu Başlat  
 Başlatmak, durdurmak ve bir yerel oturum yaptığınız gibi bir uzaktan hata ayıklama oturumunda gezinme. Pre-oluşturanın güncelleştirme sürümlerinde Windows 10, uzaktan hata ayıklama İzleyicisi uzak cihazda çalışır durumda olduğundan emin olun.  
  
 Ardından **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menü (klavye: F5). Projeyi yeniden derlenebileceğini gösterir, ardından dağıtılan ve uzak cihazda başlatıldı. Hata ayıklayıcı kesme noktalarında durduran ve, üzerinden, kodun içine ve dışına, geçebilirsiniz. Seçin **durdurma hata ayıklama** hata ayıklama oturumunuzu sonlandırmak ve uzak uygulamasını kapatın.
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş uzaktan dağıtım seçenekleri](/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps#advanced-remote-deployment-options)  
 [Visual Studio ile UWP uygulamaları test etme](../test/testing-store-apps-with-visual-studio.md)   
 [Visual Studio uygulamalarında hata ayıklama](../debugger/debug-store-apps-in-visual-studio.md)