---
title: Visual Studio uzaktan hata ayıklama | Microsoft Docs
ms.custom: remotedebugging
ms.date: 05/21/2018
ms.technology: vs-ide-debug
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
ms.openlocfilehash: 2ec5dd6979a46465f44583368251aea603ba02ff
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057797"
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

## <a name="unblock_msvsmon"></a> Windows Server'da uzak araçları yüklenmesini engellemesini kaldırma

Windows Server Internet Explorer'da varsayılan güvenlik ayarlarını uzak araçları gibi bileşenleri yüklemek zaman yapabilirsiniz.

* Açarak Web siteleri ve kaynak içeren etki alanını açıkça izin verilmediği sürece web kaynaklarına erişmesini önler Internet Explorer Artırılmış Güvenlik Yapılandırması etkin (diğer bir deyişle, güvenilir).

* Windows Server 2016, varsayılan ayar **Internet Seçenekleri** > **güvenlik** > **Internet**  >   **Özel düzey** > **indirmeleri** ayrıca yüklemeleri devre dışı bırakır dosya. Doğrudan Windows Server'da uzak araçları karşıdan yüklemeyi seçerseniz, dosya indirme etkinleştirmeniz gerekir.

Windows Server'da Araçları'nı indirmek için aşağıdakilerden birini öneririz:

* Bir çalışan Visual Studio gibi farklı bir bilgisayarda Uzak araçları indirin ve ardından kopyalama *.exe* Windows Server dosya.

* Uzaktan hata ayıklayıcı çalıştırmak [dosya paylaşımından](#fileshare_msvsmon) Visual Studio makinenizde.

* Doğrudan Windows Server'da uzak Araçları'nı indirmek ve Güvenilen siteler eklemek için komut istemlerini kabul edin. Bu komut istemlerini çok miktarda sonuçlanabilir şekilde Modern Web siteleri genellikle çok sayıda üçüncü taraf kaynakları içerir. Ayrıca, yeniden yönlendirilen bağlantıları el ile eklenmesi gerekebilir. Yükleme başlamadan önce Güvenilen siteler bazıları eklemeyi seçebilirsiniz. Git **Internet Seçenekleri > Güvenlik > Güvenilen siteler > siteleri** ve aşağıdaki siteleri ekleyin.

  * VisualStudio.microsoft.com
  * download.VisualStudio.microsoft.com
  * hakkında: boş

  Hata ayıklayıcıyı my.visualstudio.com daha eski sürümleri için bu oturum açma başarılı olduğundan emin olmak için bu ek siteleri ekleyin:

  * Microsoft.com
  * go.microsoft.com
  * download.microsoft.com
  * My.VisualStudio.com
  * login.microsoftonline.com
  * Login.live.com
  * secure.aadcdn.microsoftonline-p.com
  * MSFT.STS.microsoft.com
  * auth.Gfx.MS
  * app.vssps.visualstudio.com
  * vlscppe.microsoft.com
  * Query.prod.cms.RT.microsoft.com

    Uzak Araçlar indirilirken bu etki alanı eklemek seçin ve ardından, **Ekle** istendiğinde.

    ![Engellenen içerik iletişim kutusu](../debugger/media/remotedbg-blocked-content.png)

    Yazılım yüklediğinizde, çeşitli web sitesi komut dosyaları ve kaynakları yükleme izni vermek için bazı ek istekler alın. My.VisualStudio.com üzerinde bu oturum açma başarılı olduğundan emin olmak için ek etki alanları eklemenizi öneririz.

### <a name="fileshare_msvsmon"></a> (İsteğe bağlı) Uzaktan hata ayıklayıcı dosya paylaşımından çalıştırmak için

Uzaktan hata ayıklayıcı bulabilirsiniz (*msvsmon.exe*) Visual Studio Community, Professional veya Enterprise zaten yüklü olan bir bilgisayarda. Bazı senaryolarda, uzaktan hata ayıklama Kurulumu en kolay yolu uzaktan hata ayıklayıcı (msvsmon.exe) bir dosya paylaşımından çalıştırmaktır. Kullanım kısıtlamaları için uzaktan hata ayıklayıcı'nın yardım sayfasına bakın (**Yardım > kullanım** uzaktan hata ayıklayıcı).

1. Bul *msvsmon.exe* Visual Studio sürümünüzle eşleşen dizininde. Visual Studio Enterprise 2017 için:

      *Program dosyaları (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x86\msvsmon.exe*

      *Program dosyaları (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x64\msvsmon.exe*

2. Paylaşım **uzaktan hata ayıklayıcı** Visual Studio bilgisayardaki klasör.

3. Uzak bilgisayarda çalıştırmak *msvsmon.exe*. İzleyin [uzaktan hata ayıklayıcı ayarlamak](#Requirements).

> [!TIP]
> Komut satırı yüklemesi ve komut satırı başvurusu için yönelik yardım sayfasına bakın *msvsmon.exe* yazarak ``msvsmon.exe /?`` Visual Studio'nun yüklü olan bilgisayarda bir komut satırında (veya gitmek **Yardım > kullanım**uzaktan hata ayıklayıcı).

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

## <a name="see-also"></a>Ayrıca bkz.

- [Hata ayıklayıcı özelliği turu](../debugger/debugger-feature-tour.md)
- [Uzaktan hata ayıklama için Windows Güvenlik duvarını yapılandırma](../debugger/configure-the-windows-firewall-for-remote-debugging.md)
- [Uzaktan hata ayıklayıcı bağlantı noktası atamaları](../debugger/remote-debugger-port-assignments.md)
- [Uzaktan bir uzak IIS bilgisayarda ASP.NET çekirdek hata ayıklama](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)
- [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)