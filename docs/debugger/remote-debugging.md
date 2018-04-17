---
title: Visual Studio uzaktan hata ayıklama | Microsoft Docs
ms.custom: remotedebugging
ms.date: 08/14/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.remote.overview
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- remote debugging, setup
ms.assetid: 5a94ad64-100d-43ca-9779-16cb5af86f97
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 77726cb404cf764fa41d62dc6b4794cdb2f52d95
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="remote-debugging"></a>Uzaktan Hata Ayıklama
Başka bir bilgisayara dağıtılan bir Visual Studio uygulama ayıklayabilirsiniz. Bunu yapmak için Visual Studio uzaktan hata ayıklayıcı kullanın.

Uzaktan hata ayıklama hakkında ayrıntılı yönergeler için şu konulara bakın.

|Senaryo|Bağlantı|
|-|-|-|
|Azure uygulama hizmeti|[Hata ayıklayıcı anlık görüntü](../debugger/debug-live-azure-applications.md) veya [uzaktan Azure üzerinde ASP.NET hata ayıklama](../debugger/remote-debugging-azure.md)|
|Azure VM|[Azure’da ASP.NET hatalarını uzaktan ayıklama](../debugger/remote-debugging-azure.md)|
|Azure Service Fabric|[Azure Service Fabric uygulama hata ayıklama](/azure/service-fabric/service-fabric-debugging-your-application#debug-a-remote-service-fabric-application)|
|ASP.NET|[Uzaktan hata ayıklama ASP.NET Core](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md) veya [uzaktan hata ayıklama ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)|
|C# veya Visual Basic|[Uzaktan C# veya Visual Basic projesi hatası ayıklama](../debugger/remote-debugging-csharp.md)|
|C++|[C++ projesinin hatalarını uzaktan ayıklama](../debugger/remote-debugging-cpp.md)|
|Evrensel Windows uygulamaları (UWP)|[Bir uzak makinede UWP uygulamaları çalıştırma](../debugger/run-windows-store-apps-on-a-remote-machine.md) veya [yüklü uygulama paketi hata ayıklama](../debugger/debug-installed-app-package.md)|

Yalnızca uzaktan hata ayıklayıcı karşıdan yükleyip istiyorsanız ve senaryonuz için hiçbir ek yönergeler gerekmez, bu makaledeki adımları izleyin.
  
## <a name="download-and-install-the-remote-tools"></a>Uzak araçları yükleyip  

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

### <a name="fileshare_msvsmon"></a> (İsteğe bağlı) Uzaktan hata ayıklayıcı dosya paylaşımından çalıştırmak için

Uzaktan hata ayıklayıcı bulabilirsiniz (**msvsmon.exe**) Visual Studio Community, Professional veya Enterprise zaten yüklü olan bir bilgisayarda. Bazı senaryolarda, uzaktan hata ayıklama Kurulumu en kolay yolu uzaktan hata ayıklayıcı (msvsmon.exe) bir dosya paylaşımından çalıştırmaktır. Kullanım kısıtlamaları için uzaktan hata ayıklayıcı'nın yardım sayfasına bakın (**Yardım > kullanım** uzaktan hata ayıklayıcı).

1. Bul **msvsmon.exe** Visual Studio sürümünüzle eşleşen dizininde. Visual Studio Enterprise 2017 için:

      **Program dosyaları (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x86\msvsmon.exe**
      
      **Program dosyaları (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x64\msvsmon.exe**

2. Paylaşım **uzaktan hata ayıklayıcı** Visual Studio bilgisayardaki klasör.

3. Uzak bilgisayarda çalıştırmak **msvsmon.exe**. İzleyin [kurulum yönergeleri](#bkmk_setup).

> [!TIP] 
> Komut satırı yüklemesi ve komut satırı başvurusu için yönelik yardım sayfasına bakın **msvsmon.exe** yazarak ``msvsmon.exe /?`` Visual Studio'nun yüklü olan bilgisayarda bir komut satırında (veya gitmek **Yardım > kullanım**uzaktan hata ayıklayıcı).
  
## <a name="requirements_msvsmon"></a> Gereksinimleri

[!INCLUDE [remote-debugger-requirements](../debugger/includes/remote-debugger-requirements.md)]
  
## <a name="set-up-the-remote-debugger"></a>Uzaktan hata ayıklayıcı ayarlayın  

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

### <a name="configure_msvsmon"></a> Uzaktan hata ayıklayıcı yapılandırın  
İlk kez başlattıktan sonra bazı yönleri uzaktan hata ayıklayıcı yapılandırmasını değiştirebilirsiniz.
  
-   Uzaktan hata ayıklayıcıya bağlanmak için seçin diğer kullanıcılar için izinler eklemeniz gerekiyorsa, **Araçlar > izinleri**. İzinleri vermek veya reddetmek için yönetici ayrıcalıklarınızın olması gerekir.

     > [!IMPORTANT] 
     > Visual Studio bilgisayarda kullandığınız kullanıcı hesabından farklı bir kullanıcı hesabı altında uzaktan hata ayıklayıcı çalıştırabilirsiniz ancak Uzaktan Hata Ayıklayıcı'nın izni farklı bir kullanıcı hesabı eklemeniz gerekir. 

     Alternatif olarak, uzaktan hata ayıklayıcı komut satırıyla başlamak için kullanabileceğiniz **/ izin \<kullanıcı adı >** parametresi: **msvsmon / izin \< username@computer>**.
  
-   Kimlik doğrulama modu veya bağlantı noktası numarasını değiştirin ya da uzak araçları için zaman aşımı değeri belirtmek gerekirse: seçin **Araçlar > Seçenekler**.  
  
     Varsayılan olarak kullanılan bağlantı noktası numaraları listesi için bkz: [uzaktan hata ayıklayıcı bağlantı noktası atamaları](../debugger/remote-debugger-port-assignments.md).  
  
     > [!WARNING]
     >  Uzak araçları Kimlik Doğrulaması Yok modunda çalıştırmayı seçebilirsiniz, fakat bu mod kesinlikle önerilmez. Bu modda çalıştırdığınızda, ağ güvenliği yoktur. Yalnızca ağ kötü amaçlı veya saldırgan trafiğinden risk kullanılmadığından emin olduğunuzda Hayır kimlik doğrulama modu seçin.

##  <a name="bkmk_configureService"></a> (İsteğe bağlı) Uzaktan hata ayıklayıcı bir hizmet olarak yapılandırma
ASP.NET ve diğer sunucu ortamlara hata ayıklama için uzaktan hata ayıklayıcı yönetici olarak çalıştırın veya, her zaman çalışmasını istiyorsanız, uzaktan hata ayıklayıcı bir hizmet olarak çalıştırın.
  
 Uzaktan hata ayıklayıcı bir hizmet olarak yapılandırmak istiyorsanız, aşağıdaki adımları izleyin.  
  
1.  Bul **uzaktan hata ayıklayıcı Yapılandırma Sihirbazı'nı** (rdbgwiz.exe). (Uzaktan hata ayıklayıcı ayrı bir uygulamadan budur.) Yalnızca uzak araçları yüklediğinizde kullanılabilir. Visual Studio ile yüklenmedi.  
  
2.  Yapılandırma Sihirbazı'nı çalıştıran başlatın. İlk sayfasına geldiğinde tıklatın **sonraki**.  
  
3.  Denetleme **Visual Studio 2015 uzaktan hata ayıklayıcı bir hizmet olarak çalışması** onay kutusu.  
  
4.  Parola ve kullanıcı hesabı adını ekleyin.  
  
     Eklemeniz gerekebilir **hizmet oturum açma** bu hesap için doğru kullanıcı (Bul **yerel güvenlik ilkesi** (secpol.msc) içinde **Başlat** sayfa veya pencere (veya türü  **secpol** bir komut isteminde). Penceresi açıldığında, çift **kullanıcı hakları ataması**, ardından bulmak **hizmet oturum açma** sağ bölmede. Çift tıklatın. Kullanıcı hesabı eklemek **özellikleri** penceresini açın ve **Tamam**). **İleri**'ye tıklayın.  
  
5.  İle iletişim kurmak için Uzak araçları istediğiniz ağı seçin. En az bir ağ türü seçilmelidir. Bilgisayarlar üzerinden bir etki alanına bağlıysanız, ilk öğe seçmeniz gerekir. Bilgisayar bir çalışma grubu veya ev grubu aracılığıyla bağlıysanız, ikinci veya üçüncü öğe seçmeniz gerekir. **İleri**'ye tıklayın.  
  
6.  Hizmet başlatılabilirse göreceğiniz **Visual Studio uzaktan hata ayıklayıcı Yapılandırma Sihirbazı'nı başarıyla tamamladınız**. Hizmet başlatılamazsa göreceğiniz **Visual Studio uzaktan hata ayıklayıcı Yapılandırma Sihirbazı'nı tamamlamak için başarısız**. Sayfa aynı zamanda başlatmak için hizmet almak için izlemeniz gereken bazı ipuçları sağlar.  
  
7.  **Son**'a tıklayın.  
  
 Bu aşamada uzaktan hata ayıklayıcı bir hizmet olarak çalışıyor. Bunu giderek doğrulamak **Denetim Masası > Hizmetleri** ve aramakta **Visual Studio 2015 uzaktan hata ayıklayıcı**.  
  
 Durdurma ve uzaktan hata ayıklayıcı hizmetinden başlatma **Denetim Masası > Hizmetleri**.

## <a name="set-up-debugging-with-remote-symbols"></a>Uzak simgeleri ile hata ayıklama Kurulumu 

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)]
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı özelliği turu](../debugger/debugger-feature-tour.md)   
 [Uzaktan hata ayıklama için Windows Güvenlik duvarını yapılandırma](../debugger/configure-the-windows-firewall-for-remote-debugging.md)   
 [Uzaktan hata ayıklayıcı bağlantı noktası atamaları](../debugger/remote-debugger-port-assignments.md)   
 [Uzaktan bir uzak IIS bilgisayarda ASP.NET çekirdek hata ayıklama](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)
