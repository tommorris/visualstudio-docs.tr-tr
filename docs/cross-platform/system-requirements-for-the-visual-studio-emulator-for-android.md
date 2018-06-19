---
title: Android için Visual Studio öykünücüsü sistem gereksinimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 35e766ad-269f-41e4-ba23-74a556c315f3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 42415e1a8814de8b7a9872bf619d0ae3a000fc69
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31068667"
---
# <a name="system-requirements-for-the-visual-studio-emulator-for-android"></a>Android için Visual Studio Öykünücüsü Sistem Gereksinimleri
Android için Visual Studio öykünücüsü Hyper-V, Windows 8 ve sonraki sürümler için sanallaştırma teknolojisi sanal makine olarak çalışır. Öykünücü çalıştırmak için bilgisayarınızı bu konu başlığı altında açıklandığı gibi Hyper-V çalıştırmak için gereksinimleri karşılaması gerekir.  
  
 Öykünücü yüklediğinizde, bu önkoşulları sessiz bir şekilde yapılandırmak Kurulum programı çalışır. Kurulum Önkoşulları başarıyla yapılandırdığında öykünücü yalnızca beklendiği gibi çalışır. Aksi takdirde bu Önkoşullar el ile etkinleştirmeniz gerekebilir. Önkoşullar el ile yapılandırmanız varsa, araçları ve adımları açıklanan aynı adımlardır [burada](/previous-versions/windows/apps/jj863509\(v=vs.105\)) Windows Phone öykünücüsü.  
  
> [!IMPORTANT]
>  Kurulum programı öykünücüsü Android için Visual Studio öykünücüsü çalıştıran önkoşulları denetler. Önkoşullar mevcut olmayan, ancak bunları gerektirmez uyarıları görüntüler.  
  
 Bu konu aşağıdaki bölümleri içerir.  
  
-   [Hızlı Denetim listesi](#Checklist)  
  
-   [Sistem gereksinimleri](#System)  
  
-   [Ağ gereksinimleri](#Network)  
  
-   [Hyper-V gereksinimleri](#HyperV)  
  
-   [Öykünücü önyüklenebilir bir VHD'den çalıştırılması desteklenmez](#BootableVHD)  
  
-   [Şifrelenmemiş ve sıkıştırılmamış dosyaları Hyper-V gerektirir](#Files)  
  
##  <a name="Checklist"></a> Hızlı Denetim listesi  
 Android için Visual Studio öykünücüsü çalıştırmak için gereksinimleri hızlı bir listesi aşağıda verilmiştir. Bu konunun sonraki bölümlerinde daha ayrıntılı bilgi için bkz.  
  
 Sistem gereksinimleri  
  
-   Hyper-V desteği (Hyper-V gereksinimleri aşağıya bakın)  
  
-   6 GB veya daha fazla RAM.  
  
-   Windows 8, Windows 8.1 Windows10 veya üzeri Pro sürümü 64-bit sürümü  
  
-   SSSE3 destekleyen bir işlemci veya üstü.  
  
 Ağ gereksinimleri  
  
-   DHCP  
  
-   Otomatik olarak yapılandırılan DNS ve ağ geçidi ayarları  
  
 Hyper-V gereksinimleri  
  
-   BIOS içinde desteklenen aşağıdaki özellikleri gerekir:  
  
    -   Donanım destekli sanallaştırma  
  
    -   İkinci düzey adres çevirisi (SLAT)  
  
    -   Donanım tabanlı Veri Yürütme Engellemesi (DEP)  
  
-   Windows, Hyper-V etkin ve çalışıyor olması gerekir.  
  
-   Yerel Hyper-V Yöneticileri grubunun bir üyesi olması gerekir.  
  
##  <a name="System"></a> Sistem gereksinimleri  
 Bilgisayarınız, aşağıdaki gereksinimleri karşılaması gerekir:  
  
-   Hyper-V desteği (bkz [Hyper-V gereksinimleri](#HyperV))  
  
-   6 GB veya daha fazla RAM.  
  
-   Windows 8, Windows 8.1 Windows10 veya üzeri Pro edition sürümü 64-bit.  
  
 RAM ve Denetim Masası ' nda Windows için koşulları denetlemek üzere sistem ve güvenlik seçin ve ardından sistemi seçin.  
  
 ![Sistem gereksinimlerini doğrulama](../cross-platform/media/android_emu_system_requirements.png "Android_Emu_System_Requirements")  
  
##  <a name="Network"></a> Ağ gereksinimleri  
 Ağınız, aşağıdaki gereksinimleri karşılaması gerekir:  
  
-   DHCP  
  
     Kendi IP adresini ağ üzerinde ayrı bir aygıta olarak kendisini yapılandırır çünkü öykünücü DHCP gerektirir.  
  
-   Otomatik olarak yapılandırılan DNS ve ağ geçidi ayarları  
  
     DNS ve ağ geçidi ayarlarını el ile öykünücü yapılandırmak olası değil.  
  
 Öykünücü ağ sorunları gidermek için aşağıdaki konulara bakın:  
  
-   [Android için Visual Studio Öykünücüsü’nde Sorun Giderme](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md)  
  
##  <a name="HyperV"></a> Hyper-V gereksinimleri  
 BIOS içinde Hyper-V gereksinimleri  
  
 Bilgisayarınızın BIOS aşağıdaki gereksinimleri desteklemesi ve etkinleştirilmiş olması gerekir:  
  
-   Donanım destekli sanallaştırma  
  
-   İkinci düzey adres çevirisi (SLAT)  
  
-   Donanım tabanlı Veri Yürütme Engellemesi (DEP)  
  
 Windows Hyper-V gereksinimleri  
  
 Bilgisayarınız ve BIOS ayarlarını zaten Hyper-V desteklemek üzere yapılandırıldığında, Kurulum programı sağlar ve Hyper-V başlatır. Aksi takdirde bu gereksinimleri el ile etkinleştirmeniz gerekebilir.  
  
|Gereksinim|Denetleyin ve bu gereksinim etkinleştirme|  
|-----------------|----------------------------------------------|  
|Hyper-V yüklü olmalıdır|İçin kullanılan aynı yönergeleri izleyerek [Hyper-V'yi etkinleştirmek için Windows Phone öykünücüsü](https://msdn.microsoft.com/en-us/library/windows/apps/jj863509\(v=vs.105\).aspx).<br /><br /> Durumunu denetleme **Hyper-V sanal makine Yönetimi** Hizmetler ek bileşeninde hizmet.|  
|Hyper-V çalıştıran gerekir.|Hizmetleri yönetme hakkında daha fazla bilgi için aşağıdaki konulara bakın:<br /><br /> -   [Başlat, Durdur, duraklatma, sürdürme veya bir hizmeti yeniden başlatın](https://technet.microsoft.com/library/cc736564\(v=WS.10\).aspx)<br />-   [Bir hizmetin nasıl başlatılacağını yapılandırma](https://technet.microsoft.com/%20library/cc739213\(v=ws.10\))|  
  
 Yerel Hyper-V Yöneticileri grubunun bir üyesi olması gerekir.  
  
 Android için Visual Studio öykünücüsü haklarınızı yükseltmek için yinelenen bir uyarı olmadan çalıştırmak için yerel Hyper-V Administrators grubunun bir üyesi olmanız gerekir. SDK'yı yüklediğinizde, bilgisayarda yerel bir yönetici zaten varsa, Kurulum programı SDK'sı Hyper-V Administrators grubuna ekler. Aksi takdirde bu gereksinim el ile etkinleştirmeniz gerekebilir.  
  
 Zaten Hyper-V Yöneticileri grubunun bir üyesi değilseniz öykünücüsü çalıştırdığınızda (iletişim kutusu, Windows Phone öykünücüsü atıfta bulunmaktadır) gruba katılması istenir. Gruba katılmak yönetici hakları gerekir.  
  
> [!IMPORTANT]
>  Gruba katıldıktan sonra oturumunu veya etkili değişiklik yapmak için yeniden başlatın.  
  
 ![Hyper birleştirme&#45;V Administrators güvenlik grubunun](../cross-platform/media/android_emu_hyperv_admin.png "Android_Emu_HyperV_Admin")  
  
 Kendiniz el ile bir gruba eklemek için yerel kullanıcılar ve Gruplar ek bileşenini açın. Daha fazla bilgi için bkz: [bir gruba bir kullanıcı hesabı eklemek](http://windows.microsoft.com/en-us/windows/add-user-account-to-group#1TC=windows-7). (Bu Windows 7 konu, aynı zamanda Windows 8 için geçerlidir.)  
  
##  <a name="BootableVHD"></a> Öykünücü önyüklenebilir bir VHD'den çalıştırılması desteklenmez  
 Bir uygulama Windows önyüklenebilir bir VHD'den çalışırken Android için Visual Studio öykünücüsünde çalıştırmak çalışırsanız, öykünücü genellikle başlatmak için birkaç dakika sürer veya başlatmak başarısız olur. Öykünücü başlatma başarısız olduğunda, aşağıdaki iletiyi görürsünüz: uygulama dağıtımı başarısız oldu. Lütfen yeniden deneyin.  
  
 Bu yapılandırma desteklenmez. İlgili sorunlar hakkında daha fazla bilgi için bkz: [Android için Visual Studio öykünücüsü sorun giderme](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md).  
  
##  <a name="Files"></a> Şifrelenmemiş ve sıkıştırılmamış dosyaları Hyper-V gerektirir  
 Bir sabit sürücüde NTFS dosya sistemi ile yapılandırılmış Hyper-V tarafından kullanılan sanal sabit disk dosyalarını sıkıştırılmamış şifrelenmemiş ve gerekir. Aşağıdaki dizinleri sıkıştırılmış veya şifrelenmiş değil, emin olun:  
  
-   %localappdata%\Microsoft\XDE  
  
-   C:\Program dosyaları (x86) \Microsoft öykünücüsü yöneticisi  
  
-   C:\Program Files (x86)\Microsoft Visual Studio Emulator for Android  
  
-   %localappdata%\Microsoft\VisualStudioEmulator  
  
 ReFS dosya sisteminde, sanal sabit disk dosyalarını bit bütünlüğü kümesi olmamalıdır.  
  
## <a name="hardware-graphics-forwarding-opengl-es-support-requirements"></a>Donanım gereksinimleri grafik iletme (OpenGL ES desteği)  
 OpenGL ES tarafından kullanılanlar gibi GPU çağrıları benzetmek öykünücüsü makinenizi DirectX uyumlu GPU'ya uygun DirectX sürücüleri yüklü olması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Android için Visual Studio Öykünücüsü’nde Sorun Giderme](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md)