---
title: "Uzaktan hata ayıklama Visual C++ projesinde | Microsoft Docs"
ms.custom: remotedebugging
ms.date: 08/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords: remote debugging, setup
ms.assetid: 8b8eca0d-122f-4eda-848a-cf0945f207d0
caps.latest.revision: "65"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9fb8230c2a70cf98a20993db930ddc1d494e989d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="remote-debugging-a-visual-c-project-in-visual-studio"></a>Uzaktan Visual C++ projesinde Visual Studio'da hata ayıklama
Farklı bir bilgisayara Visual Studio uygulama hata ayıklama, yükleme ve uygulamanızı dağıtacağı bilgisayarda Uzak araçları çalıştırmak için projenizi Visual Studio'dan uzak bilgisayara bağlanın ve ardından dağıtmak ve uygulamanızı çalıştırmak için yapılandırın.

![Uzaktan hata ayıklayıcı bileşenleri](../debugger/media/remote-debugger-client-apps.png "Remote_debugger_components")

Uzaktan hata ayıklama Evrensel Windows uygulamaları (UWP) hakkında daha fazla bilgi için bkz: [yüklü uygulama paketi Debug](debug-installed-app-package.md).

## <a name="requirements"></a>Gereksinimler

Windows 7 ve daha yeni uzaktan hata ayıklayıcı desteklenir (telefon değil) ve Windows Server 2008 Service Pack 2 ile başlayarak Windows Server sürümleri. Gereksinimlerinin tam listesi için bkz: [gereksinimleri](../debugger/remote-debugging.md#requirements_msvsmon).

> [!NOTE]
> Bir proxy üzerinden bağlı iki bilgisayar arasında hata ayıklama desteklenmiyor. Bir yüksek gecikme veya çevirmeli Internet gibi düşük bant genişliği bağlantısı veya Internet üzerinden ülkelerde arasında hata ayıklama önerilmez ve başarısız olabilir veya edilemeyecek yavaş.
  
## <a name="download-and-install-the-remote-tools"></a>Uzak araçları yükleyip

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
> [!TIP]
> Bazı senaryolarda, bir dosya paylaşımından uzaktan hata ayıklayıcı çalıştırmak için etkili olabilir. Daha fazla bilgi için bkz: [dosya paylaşımından uzaktan hata ayıklayıcı çalıştırmak](../debugger/remote-debugging.md#fileshare_msvsmon).
  
## <a name="BKMK_setup"></a>Uzaktan hata ayıklayıcı ayarlayın

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> Gerektiğinde ek kullanıcılar için izinler eklemek için kimlik doğrulaması modunu değiştirme veya bağlantı noktası numarası uzaktan hata ayıklayıcı için bkz: [uzaktan hata ayıklayıcı yapılandırma](../debugger/remote-debugging.md#configure_msvsmon).

## <a name="remote_cplusplus"></a>Uzaktan hata ayıklama Visual C++ projesi  
 Aşağıdaki yordamda adı ve yolu projenin C:\remotetemp\MyMfc ve uzak bilgisayarın adını **MJO DL**.  
  
1.  Adlı bir MFC uygulaması oluşturma **mymfc.**  
  
2.  Bir kesme noktası kolayca, örneğin içinde ulaşıldığında uygulama herhangi bir yerde kümesindeki **MainFrm.cpp**, başlangıcında `CMainFrame::OnCreate`.  
  
3.  Çözüm Gezgini'nde sağ tıklatın ve proje **özellikleri**. Açık **hata ayıklama** sekmesi.  
  
4.  Ayarlama **başlatmak için hata ayıklayıcı** için **uzak Windows hata ayıklayıcı**.  
  
     ![RemoteDebuggingCPlus](../debugger/media/remotedebuggingcplus.png "RemoteDebuggingCPlus")  
  
5.  Özellikler aşağıdaki değişiklikleri yapın:  
  
    |Ayar|Değer|
    |-|-|  
    |Uzak komutu|C:\remotetemp\mymfc.exe|  
    |Çalışma dizini|C:\remotetemp|  
    |Uzak sunucu adı|MJO-DL:*BağlantıNoktasıNumarası*|  
    |Bağlantı|Windows kimlik doğrulaması ile uzaktan|  
    |Hata ayıklayıcı türü|Yalnızca yerel|  
    |Dağıtım dizini|C:\remotetemp.|  
    |Dağıtmak için ek dosyalar|C:\data\mymfcdata.txt.|  
  
     Ek dosyalar (isteğe bağlı) dağıtırsanız, klasörü hem makinelerde bulunması gerekir.  
  
6.  Çözüm Gezgini'nde çözüme sağ tıklayın ve seçin **Configuration Manager**.  
  
7.  İçin **hata ayıklama** yapılandırma, select **dağıtma** onay kutusu.  
  
     ![RemoteDebugCplusDeploy](../debugger/media/remotedebugcplusdeploy.png "RemoteDebugCplusDeploy")  
  
8.  Hata Ayıklamayı Başlat (**hata ayıklama > hata ayıklamayı Başlat**, veya **F5**).  
  
9. Yürütülebilir dosya uzak bilgisayara otomatik olarak dağıtılır.  
  
10. İstenirse, uzak makineye bağlanmak için ağ kimlik bilgilerini girin.  
  
     Ağınızın güvenlik yapılandırması için gerekli kimlik bilgilerini özgüdür. Örneğin, bir etki alanı bilgisayarında bir güvenlik sertifikası seçin veya etki alanı adınızı ve parolanızı girin. Bir etki alanı dışı makinede, makine adı ve geçerli kullanıcı hesabı adı gibi girebilir  **MJO-DL\name@something.com** , doğru parolayı yanı sıra.  
  
11. Visual Studio bilgisayarda yürütme kesme noktasında durdurulur görmeniz gerekir.  
  
    > [!TIP]
    >  Alternatif olarak, dosyaları ayrı bir adım olarak dağıtabilirsiniz. İçinde **Çözüm Gezgini** sağ **mymfc** düğümünü ve ardından **dağıtma**.  
  
 Uygulama tarafından kullanılması gereken kod olmayan dosyalar varsa, Visual Studio projesinde eklemeniz gerekir. Ek dosyalar için bir proje klasör oluşturun (içinde **Çözüm Gezgini**, tıklatın **Ekle > Yeni bir klasör**.) Klasöre dosya ekleme (içinde **Çözüm Gezgini**, tıklatın **Ekle > varolan öğeyi**, dosyaları seçin). Üzerinde **özellikleri** sayfasında her dosya için **çıktı dizinine Kopyala** için **her zaman Kopyala**.
  
## <a name="set-up-debugging-with-remote-symbols"></a>Uzak simgeleri ile hata ayıklama Kurulumu 

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)] 
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio’da hata ayıklama](../debugger/index.md)  
 [Hata ayıklayıcı özelliği turu](../debugger/debugger-feature-tour.md)   
 [Uzaktan hata ayıklama için Windows Güvenlik duvarını yapılandırma](../debugger/configure-the-windows-firewall-for-remote-debugging.md)   
 [Uzaktan hata ayıklayıcı bağlantı noktası atamaları](../debugger/remote-debugger-port-assignments.md)   
 [Uzaktan bir uzak IIS bilgisayarda ASP.NET hata ayıklama](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)