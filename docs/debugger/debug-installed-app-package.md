---
title: "Yüklü uygulama paketi (UWP) hata ayıklama | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 07/17/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.installedapppackagelauncher
- vs.debug.remote.connection
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- app package, debug
ms.assetid: 5a94ad64-100d-43ca-9779-16cb5af86f97
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- uwp
ms.openlocfilehash: 16f4b69fa25861d893471a161fdb7c1a6bba34e5
ms.sourcegitcommit: 5d43e9590e2246084670b79269cc9d99124bb3df
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="debug-an-installed-app-package-in-visual-studio-uwp"></a>Yüklü uygulama paketi, Visual Studio (UWP) hata ayıklama

Tüm yüklü uygulama paketlerini tıklayarak ayıklayabilirsiniz **hata ayıklama > diğer hata ayıklama hedeflerini > yüklü uygulama paketi Debug**. Hata ayıklama bu yöntem, bu aygıtlar üzerinde Evrensel Windows uygulamaları (UWP) için kullanılabilir:

* Windows 10 (telefonlarda desteklenmez)
* XBox
* HoloLens
* IoT

Bu özellikler hakkında daha fazla bilgi için blog için güncelleştirmelerini gönderisine bakın [hata ayıklama, uygulama paketleri yüklü](https://blogs.msdn.microsoft.com/visualstudioalm/2016/03/30/updates-for-debugging-installed-app-packages-in-visual-studio-2015-update-2/) ve üzerindeki posta [Evrensel Windows uygulamaları (UWP) oluşturma](https://blogs.msdn.microsoft.com/visualstudio/2016/08/02/universal-windows-apps-targeting-windows-10-anniversary-sdk/).

## <a name="debug-an-installed-app-package-or-running-app-on-a-local-machine-or-device"></a>Bir uygulama paketi yüklü veya yerel makine ya da cihaz üzerinde çalışan uygulama hata ayıklama

1. Visual Studio'da açıkken, UWP projesi ile tıklatın **hata ayıklama > diğer hata ayıklama hedeflerini > yüklü uygulama paketi Debug**.

2. Şunlardan birini seçin **yerel makine** veya **aygıt**.

     Seçerseniz **aygıt**, bilgisayarınızın Windows 10 cihaz için fiziksel olarak bağlı olması gerekir.

     ![DebugInstalledAppPackage](../debugger/media/debug-installed-app-pkg.png "DebugInstalledAppPackage")

     Şu anda çalışan yüklü altında uygulama paketleri gösteri **çalıştıran** düğümü. Göster altında çalışan olmayan uygulama paketlerinin yüklü **çalışmıyor**.

3. Altında hata ayıklamak istediğiniz uygulamanın adını seçin **çalıştıran** veya **çalışmıyor** ve **Başlat** veya uygulama zaten çalışıyorsa seçin **Attach**.

     Seçerseniz **değil başlatın, ancak başlatıldığında kodum hata ayıklama**, bu özel aynı anda başlattığında uygulamanıza eklemek Visual Studio hata ayıklayıcısı neden olur. Bu denetim yolları hata ayıklamak için etkili bir yoldur [farklı başlatma yöntemleri](/windows/uwp/xbox-apps/automate-launching-uwp-apps), özel parametrelerle Protokolü etkinleştirme gibi.

> [!NOTE]
> Visual Studio ayrıca iliştirebilirsiniz herhangi çalışan bir UWP uygulaması işlem seçerek **hata ayıklama**ve ardından **ekleme işlemi için**. Bir çalışan işlemine iliştirme özgün Visual Studio projesi gerektirmez, ancak işlemin simgeleri yüklenirken önemli ölçüde özgün kodunu sahip olmayan bir işlem hata ayıklama sırasında yardımcı olur.
  
## <a name="remote"></a>Uzak bir bilgisayarda yüklü olan veya çalışan uygulama hata ayıklama 

İlk olarak uzak bir bilgisayarda yüklü uygulama paketi hata ayıklamasını yaparken, Visual Studio hedef cihaz için Uzak araçları doğru sürümünü yükler. Hedef aygıt, bir Windows 10 bilgisayarı, XBox, HoloLens ve IOT cihazı olmalıdır.

1. Windows 10 Cihazınızda etkinleştirmek [geliştirici modunu](/windows/uwp/get-started/enable-your-device-for-development).

2. Pre-oluşturanın güncelleştirme sürümü Windows 10 çalıştıran ilk el ile bir uzak Bilgisayara bağlanıyorsanız [yükleyin ve uzaktan hata ayıklayıcı başlatın](../debugger/remote-debugging.md).

     XBox, HoloLens ve IOT cihaz Windows 10 oluşturanın güncelleştirme çalıştıran ve Windows cihazları için uzaktan hata ayıklayıcı el ile yüklemeniz gerekmez. Uygulamayı dağıttığınızda uzak araçları otomatik olarak yüklenir.

3. Tıklatın **hata ayıklama > diğer hata ayıklama hedeflerini > hata ayıklama yüklü uygulama paketi**.

4. İlk açılan listeden seçin **uzak makine**.

5. Adı veya eklemek istediğiniz bilgisayarın IP adresini yazın.

     ![ChooseRemoteComputer](../debugger/media/debug-remote-app-pkg.png "ChooseRemoteComputer")

     Bilgisayar adını kullanarak bağlanamıyorsa (seçtiğiniz sonra **Başlat**), IP adresi kullanın. IP adresi, XBox, HoloLens ve IOT cihazlar için kullanın.

5. Bir seçenek olarak seçerek kimlik doğrulaması yapmayı seçin **kimlik doğrulama modu**.

    Çoğu uygulamalar için varsayılan değeri tutmak **Evrensel (şifrelenmemiş Protokolü)**.

6. Altında hata ayıklamak istediğiniz uygulamayı seçin ve **çalıştıran** veya **çalışmıyor** ve **Başlat** veya (çalışan uygulamalar) **Attach**.

     Seçerseniz **değil başlatın, ancak başlatıldığında kodum hata ayıklama**, bu özel aynı anda başlattığınızda, uygulama paketi eklemek Visual Studio hata ayıklayıcısı neden olur. Bu denetim yolları hata ayıklamak için etkili bir yoldur [farklı başlatma yöntemleri](/windows/uwp/xbox-apps/automate-launching-uwp-apps), özel parametrelerle Protokolü etkinleştirme gibi.

     İlk kez bağlı bir XBox, HoloLens ve IOT cihazda yüklü uygulama paketi hata ayıklamasını yaparken, Visual Studio uzaktan hata ayıklayıcı hedef cihazınız için doğru sürümünü yükler. Bu işlem biraz zaman alabilir ve bir ileti görürsünüz ``Starting remote debugger`` bu sürerken.

     > [!NOTE]
> Sunmak, XBox veya HoloLens aygıt uygulama hata ayıklayıcısı ekli zaten çalışıyorsa, yeniden başlatılır.

UWP uygulamaları'nın uzaktan dağıtımı için Gelişmiş seçenekleri hakkında daha fazla bilgi için bkz: [dağıtma ve hata ayıklama UWP uygulamaları](/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps.md#advanced-remote-deployment-options). 
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio’da hata ayıklama](../debugger/index.md)  
 [Hata ayıklayıcı özelliği turu](../debugger/debugger-feature-tour.md)  
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)  
 [Uzaktan hata ayıklama için Windows Güvenlik duvarını yapılandırma](../debugger/configure-the-windows-firewall-for-remote-debugging.md)  
 [Uzaktan hata ayıklayıcı bağlantı noktası atamaları](../debugger/remote-debugger-port-assignments.md)  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)