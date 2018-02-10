---
title: "Android için Visual Studio öykünücüsü sorunlarını giderme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-mobile
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f3fb5df4-3aae-40e4-9450-bbe15b0c5af5
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 6d99892d42190e64c54213c2b6b9e52fdd22dfd8
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="troubleshooting-the-visual-studio-emulator-for-android"></a>Android için Visual Studio Öykünücüsü’nde Sorun Giderme
Bu konu, Android için Visual Studio öykünücüsü kullanırken karşılaşabileceğiniz sorunları gidermenize yardımcı olabilecek bilgiler içerir.  
  
> [!WARNING]
>  Öykünücü yüklendikten sonra Kurulum programı yazılımı çalıştıran önkoşulları denetler. Önkoşullar mevcut olmayan, ancak bunları yükleme için gerekli olmadığı uyarıları görüntüler.  
  
 Bu konu aşağıdaki bölümleri içerir.  
  
-   [Başlamadan önce](#BeforeYouStart)  
  
-   [Öykünücü yüklenmesi başarısız](#NoInstall)  
  
-   [Bir etki alanı veya kurumsal bir ağda ağ hedeflere bağlanamıyor](#DomainNetwork)  
  
-   [Ağ ayarlarını el ile yapılandırma gerektirdiğinde ağ hedeflere bağlanamıyor](#ManualNetworkConfig)  
  
-   [Öykünücü yavaş bir zaman aşımı nedeniyle başlatmak için başarısız başlatır veya uygulama dağıtımı başarısız oluyor](#SlowStart)  
  
-   [Öykünücü başlatılamıyor](#NoStart2)  
  
-   [Öykünücü (ilk kullanın) başlatılamıyor](#NoStart)  
  
-   [Bilgisayar öykünücüsü yüklendikten sonra önyükleme başarısız olur.](#NoBoot)  
  
-   [Visual Studio öykünücüsü uygulama dağıtılmaya çalışılırken takılmış veya öykünücü diğer IDE hata ayıklama hedefi olarak görünmez](#ADB)  
  
-   [UDP bağlantı noktası ayarlanamadı çünkü öykünücüsü askıda kalır](#XamarinPlayer)  
  
-   [Hata ayıklayıcı Xamarin projesine eklenemiyor](#Skylake)  
  
-   [Google Play hizmetleri kullanan uygulamalarda öykünücüsü çalışmaz](#GooglePlay)  
  
-   [Sürükle ve bırak dosya, APK veya yazılımına anlık olarak erişilebilen zip dosyası çalışmıyor](#DragAndDrop)  
  
-   [Ekran çözünürlüğü yanlış](#Resolution)  
  
-   [OpenGL içeriğini işlemek öykünücüsü başarısız](#OpenGL)  
  
-   [Öykünücü çok dokunma hareketleri yanıt vermiyor](#Multitouch)  
  
-   [Destek kaynakları](#Support)  
  
##  <a name="BeforeYouStart"></a>Başlamadan önce  
 Sorun gidermeye başlamadan önce aşağıdaki konuları gözden geçirmek yararlı olabilir:  
  
-   [Android için Visual Studio Öykünücüsü Sistem Gereksinimleri](../cross-platform/system-requirements-for-the-visual-studio-emulator-for-android.md)  
  
##  <a name="NoInstall"></a>Öykünücü yüklenmesi başarısız  
 Hyper-V'nin yüklü yoksa, öykünücü yüklemeye çalıştığınızda şu iletiyi görürsünüz. HyperV destekleyen bir makine olmalıdır ve etkinleştirilmesi gerekir.  
  
 ![Android &#95; AB &#95;Yükleme &#95; sorun](../cross-platform/media/android_emu_install_issue.png "Android_Emu_Install_Issue")  
  
> [!NOTE]
>  Bu ileti, hem Android için Visual Studio öykünücüsü ve Windows Phone öykünücüsü için geçerlidir. Windows 8.1 ve Windows 10 öykünücü destekler.  
  
 Bu iletiyi görürseniz, denetleme [Android için Visual Studio öykünücüsü sistem gereksinimleri](../cross-platform/system-requirements-for-the-visual-studio-emulator-for-android.md) öykünücü çalıştırılıp çalıştırılmayacağını görmek için.  
  
##  <a name="DomainNetwork"></a>Bir etki alanı veya kurumsal bir ağda ağ hedeflere bağlanamıyor  
 Android için Visual Studio öykünücüsü ağda ayrı bir aygıta kendi IP adresiyle olarak görünür. Bir Windows etki alanına katılmamışsa ve ana bilgisayar ile etki alanı veya çalışma grubu kimlik bilgileri paylaşmaz.  
  
 Ağınızın temel ağ ve Internet bağlantısı için etki alanı veya çalışma yetkilendirme gerektiriyorsa, bir özel durum için BT yöneticinize başvurun. Bu özel durumun geliştirme bilgisayarınıza bir sınır makine olarak hizmet verecek ve etki alanına birleştirilmemiş ağ aygıtlarını öykünücü gibi gelen bağlantıları kabul edecek sağlar.  
  
 Android için Visual Studio öykünücüsü de kendi MAC adresleri kümesini kullanır. Ağ veya Internet kaynakların öykünücüsünden erişemiyorsanız, ağınızda öykünücüsü'nın MAC adresleri yetkili olduğundan emin olmak için BT yöneticinize danışın.  
  
#### <a name="to-view-the-emulators-mac-addresses"></a>Adresleri öykünücüsü'nın MAC görüntülemek için  
  
1.  Öykünücüyü başlatın.  
  
2.  Öykünücü araç çubuğunda Köşeli Çift Ayraca düğmesini tıklatın (>>) ek araçları penceresini açın.  
  
3.  Ek araçlar penceresinde ağ sekmesini tıklatın.  
  
4.  Ağ sayfasında fiziksel adres girdilerini bulun.  
  
##  <a name="ManualNetworkConfig"></a>Ağ ayarlarını el ile yapılandırma gerektirdiğinde ağ hedeflere bağlanamıyor  
 Ağ hedeflere öykünücüsünden bağlanmak için ağınıza aşağıdaki gereksinimleri karşılaması gerekir:  
  
-   DHCP. Kendi IP adresini ağ üzerinde ayrı bir aygıta olarak kendisini yapılandırır çünkü öykünücü DHCP gerektirir.  
  
-   Otomatik olarak yapılandırılan DNS ve ağ geçidi ayarları. DNS ve ağ geçidi ayarlarını el ile öykünücü yapılandırmak olası değil.  
  
 Ağınız el ile yapılandırılan ayarları gerektiriyorsa, ağ bağlantısı için öykünücüsü nasıl etkinleştirebilirsiniz belirlemek için BT yöneticinize danışın.  
  
##  <a name="SlowStart"></a>Öykünücü yavaş bir zaman aşımı nedeniyle başlatmak için başarısız başlatır veya uygulama dağıtımı başarısız oluyor  
 Belirli koşullar altında öykünücü başlatmak için birkaç dakika sürer veya bir zaman aşımı nedeniyle başlatılamıyor. Öykünücü başlatma başarısız olduğunda, aşağıdaki iletiyi görürsünüz: `App deployment failed. Please try again`. Aşağıdaki koşullar, bu hatayı neden olabilir.  
  
-   Android için Visual Studio öykünücüsü önyüklenebilir bir VHD'den çalışıyor. Bu yapılandırma desteklenmez.  
  
-   Hatalı bir sabit sürücü. Chkdsk programı çalıştırmayı deneyin.  
  
-   Birleştirilmesi gereken bir sabit sürücü. Sürücü birleştirmelisiniz.  
  
-   Bir sabit sürücü dolmak üzere. Sürücüde kullanılabilir alanı denetleyin.  
  
-   Yetersiz bellek nedeniyle çalışan diğer uygulamaları yok. Bellek tükettikten veya bellek miktarını artırın uygulamalarının sayısını azaltın.  
  
-   Genellikle, düşük performans sistem üzerindeki katkıda bulunan tüm faktörü. En düşük alt Denetim Masası'nın performans bilgileri ve araçları sayfasında bulabilirsiniz Windows Deneyimi Dizini olan bileşeni ile sorun giderme başlar.  
  
##  <a name="NoStart2"></a>Öykünücü başlatılamıyor  
 Öykünücü daha önce çalışan, ancak artık çalışmaz, aşağıdaki görevleri gidin. Öykünücü ilk kez kullanıyorsanız bkz [öykünücüsü başarısız (ilk kullanımda) başlatmak](#NoStart) önce aşağıdaki adımları deneyin.  
  
-   Öykünücü diğer Hyper-V örneklerini kaldırın.  
  
    1.  Visual Studio’yu kapatın.  
  
    2.  Hyper-V Yöneticisi'ni açın ve tüm Hyper-V örnekleri zaten çalışan öykünücüsünü (sanal makineler) ve büyük olasılıkla bozuk durumda durdurun.  
  
    3.  Hyper-V Yöneticisi'nde herhangi diğer öykünücüsü sanal makineleri silin.  
  
    4.  Makinenizi yeniden başlatın.  
  
-   En az 4 GB sistem belleği ve bunu diğer yoğun bir kaynak programlar ve işlemler (örneğin, tüm tarayıcı pencerelerini kapatmayı deneyin) tarafından tüketilmesi değil olduğundan emin olun.  
  
-   Hyper-V Yöneticisi'nde, iki ağ anahtarları olduğunu görmek için sanal Anahtar Yöneticisi'ni ve onay açın; ilk iç anahtar ve ikinci dış olduğunu doğrulayın.  
  
     ![Android &#95; AB &#95; V &#95; Geçiş &#95; ADAM](../cross-platform/media/android_emu_v_switch_man.png "Android_Emu_V_Switch_Man")  
  
     Kurulum yanlış ise ve Windows 10 kullanıyorsanız, için deneyebilirsiniz [netcfg -d komutu kullanarak ağ aygıtlarını yeniden](http://windows.microsoft.com/en-us/windows-10/fix-network-connection-issues) (Bölüm 6).  
  
-   Bu adımlar sorunu çözmezse, bkz: [öykünücüsü başarısız (ilk kullanımda) başlatmak](#NoStart) öykünücü ile çakışabilecek 3 taraf yazılımlar hakkında bilgi için.  
  
##  <a name="NoStart"></a>Öykünücü (ilk kullanın) başlatılamıyor  
 Öykünücü başlamazsa belirlemek ve sorunu düzeltmek için aşağıdaki görevleri gidin.  
  
-   En düşük donanım gereksinimleri karşılandıktan ve BIOS ayarlarının doğru olduğundan emin olun.  
  
     Windows 8 Hyper-V ve öykünücüsü ikinci düzey adres çevirisi (SLAT) ile bir 64-bit işlemci gerektirir. Intel için temelde çekirdek i3 i5 veya i7 işlemci (veya biri birçok Xeon) gerekir. AMD yongaları listesi kullanılabilir [burada](http://support.amd.com/en-us).  
  
    1.  Bilgisayar karşılıyor emin olun [sistem gereksinimleri](../cross-platform/system-requirements-for-the-visual-studio-emulator-for-android.md).  
  
    2.  Doğrulayın [SLAT aracı](https://slatstatuscheck.codeplex.com/) bilgisayarınızı SLAT özellikli olduğunu bildirir.  
  
    3.  Bilgisayarınızın BIOS ayarları tüm sanallaştırma teknolojisi etkin olduğundan emin olun. Tam BIOS açıklamaları için her donanım üreticisinin farklılık gösterebilir. Genel olarak, ilgili özellikleri etkinleştirin:  
  
        -   SLAT (ikinci düzey adres çevirisi)  
  
        -   Kabul et (sayfası tabloları genişletilmiş) (Intel)  
  
        -   NPT (iç içe geçmiş sayfası tabloları) (AMD)  
  
        -   (Hızlı sanallaştırma dizin) RVI (AMD)  
  
        -   VMX (donanım Yardımlı sanallaştırma desteği belirten bir Intel kısaltma)  
  
        -   SVM (donanım Yardımlı sanallaştırma desteği belirten bir AMD kısaltma)  
  
        -   XD (yürütmeyi devre dışı bırak) (Intel); Bu etkinleştirilmelidir  
  
        -   NX (Execute)(AMD) yok; Bu etkinleştirilmesi gerekir.  
  
    4.  Aşağıdaki seçenekler BIOS'ta varsa, bunları devre dışı bırakın.  
  
        -   Disable Intel VT-d  
  
        -   Güvenilir yürütme devre dışı bırak  
  
         Bu makalede daha fazla bilgi için bkz: Technet: Hyper-V: nasıl için düzeltme BIOS hataları etkinleştirme Hyper-V  
  
    5.  En az 4 GB sistem belleği ve bunu diğer yoğun bir kaynak programlar ve işlemler tarafından tüketilmesi değil olduğundan emin olun.  
  
    6.  Daha iyi veya Windows 8 Professional çalıştırdığınızdan emin olun (Windows Server 2008 desteklenmez). Windows Server 2012 desteklenir, ancak masaüstü deneyimi etkinleştirmeniz gerekir.  
  
     Hiper yönetici hataları olup olmadığını görmek için Olay Görüntüleyicisi'ni inceleyebilirsiniz. Bunu yapmak için Olay Görüntüleyicisi'ni açın (Başlangıç tuşu + R yazın, `eventvwr`) ve ardından **Windows Günlükleri**, **sistem**. Kaynak ayarını günlüğü olay kaynağı tarafından filtre **Hyper-V-hiper yönetici**. Kök nedenini belirlemenize yardımcı olması hatalara karşı denetleyin.  
  
     En düşük gereksinimleri ancak hiper yönetici yine başarısız, işlemci karşıladığını düşünüyorsanız olmadığını anlamak bulma BIOS yükseltme bilgisayarınız için mevcut değil. Varsa, ve seçtiğiniz yükseltmek için üreticinin tüm önlemleri (örneğin, BIOS üretici yazılımı yükseltme kalıcı olarak BIOS bozulmasına neden olabilir ve güç kaybı tarafından engellenmez emin) BIOS yükseltirken izlemek emin olun.  
  
-   En az 4 GB sistem belleği ve bunu diğer yoğun bir kaynak programlar ve işlemler tarafından tüketilmesi değil olduğundan emin olun.  
  
-   Kaldırma/devre dışı bırak üçüncü taraf sürücüler veya sanal ağ ile çakışabilecek yazılım.  
  
     Ağ sürücüleri/Hyper-V ağ yığınını ile tamamen uyumlu olmayan protokolleri gibi Windows 8 altında yüklü 3 bazı taraf ürünleri ile ilgili bazı bilinen sorunlar vardır.  
  
     Genel olarak, Windows 8 ve Hyper-V ile uyumlu olacak şekilde yazılımlarını güncelleştirmek için bu ürünlerden birinin geliştiricilere kadar olacaktır.  
  
     Aşağıdaki ürünler için Windows 8 Uyumluluk yükseltme gerektirebilir: VirtualBox, Virtual PC 7, VMWare, bazı VPN istemcileri yazılım güvenlik duvarları, Cisco VPN istemcilerinin ve diğer sanallaştırma sistemlerinin bazı sürümlerinde. Windows 8 ve Hyper-V ile uyumlu hale getirmek için yazılım yükseltmelerini teşvik eden Geliştirici şüpheli sanallaştırma yazılımı ile çalışır.  
  
     Farklı bir **geçici çözüm**, tüm üçüncü taraf sürücüler ve Visual Studio ile iletişim kurmak için öykünücüsü tarafından kullanılan sanal ağ ile engel olabilen uygulamaları devre dışı bırakabilirsiniz. Bu uygulamalar içerebilir:  
  
    -   (Ağ yığına kanca) virüsten koruma uygulamaları  
  
    -   Ağ izleme araçları  
  
    -   Ağ günlük araçları  
  
    -   Diğer sistem izleme yazılım  
  
     Ürünleri kaldırdıktan sahip başka bir olası çözüm soru (ve güncelleştirilmiş bir sürümünü yayımlamayı ürün Geliştirici isteyen), aşağıdaki adımları almaktır.  
  
    1.  Ağ bağlantıları Yöneticisi'ni başlatın (başlangıç ekranından yazın `View Network Connections` ve ağ bağlantılarını görüntülemek için bu seçeneği belirleyin.)  
  
    2.  VEthernet (iç Ethernet bağlantı noktası Windows Phone öykünücüsü iç anahtar) bağdaştırıcısı için **özellikleri** ve bağlam menüsünden.  
  
         ![Hyper &#45;tarafından kullanılan sanal bağdaştırıcı; V](../cross-platform/media/android_emu_virtual_adapter.png "Android_Emu_Virtual_Adapter")  
  
         Bağdaştırıcı özelliklerini burada gösterilir.  
  
         ![Sanal bağdaştırıcı özellikleri](../cross-platform/media/android_emu_virtual_adapter_properties.png "Android_Emu_Virtual_Adapter_Properties")  
  
    3.  Bu bağdaştırıcı, altında seçilmelidir yalnızca öğeler için **Bu bağlantı aşağıdaki öğeleri kullanır** aşağıdaki gibi olmalıdır:  
  
        -   Microsoft Ağları için istemci  
  
        -   QoS Paket Zamanlayıcısı  
  
        -   Dosya ve yazıcı paylaşımı Microsoft Ağları için  
  
        -   Microsoft LLDP Protokolü Sürücüsü  
  
        -   Bağlantı Katmanı Topolojisi Bulma Eşleyicisi g/ç sürücüsü  
  
        -   Bağlantı Katmanı Topoloji Bulma Yanıtlayıcı  
  
        -   Internet Protokolü sürüm 6 (TCP/IPv6)  
  
        -   Internet Protokolü sürüm 4 (TCP/IPv4)  
  
    4.  Diğer öğeleri seçimini kaldırın.  
  
     Bu teknik kullanmanın olumsuz yanı dilediğiniz zaman yeni bir 3 taraf desteklenmeyen sürücüleri yükler veya öykünücü yüklendikten, dilediğiniz zaman adımları yinelenmesi gerekir ' dir.  
  
     Üçüncü taraf ürünleri kaldırıldıktan sonra Windows Phone öykünücüsü iç anahtarı geri yüklemeniz gerekebilir. Bunu yapmak için:  
  
    -   Hyper V açın ve sanal Anahtar Yöneticisi'ne gidin. "Windows Phone öykünücüsü iç geçiş" adlı bir sanal anahtar oluşturmak ve bağlantı türünü ayarlamak **iç ağ**.  
  
         ![Sanal Anahtar Yöneticisi'ni](../cross-platform/media/android_emu_virtual_switch_manager.png "Android_Emu_Virtual_Switch_Manager")  
  
     Şimdi öykünücüsünde başlatın. Çalışmalıdır.  
  
##  <a name="NoBoot"></a>Bilgisayar öykünücüsü yüklendikten sonra önyükleme başarısız olur.  
 Aşağıdaki koşullar doğru olduğunda bu sorun oluşabilir:  
  
-   Bilgisayarınızda bir gigabayt ana kart vardır.  
  
-   USB3 ana kartına etkinleştirilir.  
  
 Bu sorunu çözmek için USB3 ana kart BIOS ayarlarını devre dışı bırakın ve bilgisayarı yeniden başlatın. Ardından gigabayt ana bilgisayarın BIOS için bir güncelleştirme yayımladı olup olmadığını denetleyin.  
  
 Daha fazla bilgi için aşağıdaki Bilgi Bankası makalesine bakın: [gigabayt sistemlerinde Hyper-V rolü yüklendikten sonra önyükleme hatası](https://support.microsoft.com/en-us/kb/2693144).  
  
##  <a name="ADB"></a>Visual Studio öykünücüsü uygulama dağıtılmaya çalışılırken takılmış veya öykünücü diğer IDE hata ayıklama hedefi olarak görünmez  
 Öykünücü çalışıyor, ancak ADB (Android hata ayıklama köprüsü) bağlanması gerekir görünmüyor ya da (örneğin, Android Studio veya Eclipse) ADB kullanan Android araçlarında görünmez, öykünücü ADB için burada görünür ayarlamanız gerekebilir. Öykünücü, Android SDK'sı temel konumunu tanımlamak için bir kayıt defteri anahtarı kullanır ve bu dizin altında \platform-tools\adb.exe dosyasını arar. Öykünücü tarafından kullanılan Android SDK yolunu değiştirmek için:  
  
-   Kayıt Defteri Düzenleyicisi'ni seçerek açın **çalıştırmak** başlangıç düğmeleri bağlam menüsünden yazarak `regedit` iletişim kutusunda ve seçme **Tamam**.  
  
-   Sol taraftaki klasör ağacında HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Android SDK Araçları'nın üzerine gidin.  
  
-   Değiştirme **yolu** Android SDK yolunu eşleştirmek için kayıt defteri değişkeni.  
  
 Öykünücü yeniden başlatın ve şimdi öykünücü ADB için bağlı ve Android araçları ilişkili görüyor olmanız gerekir.  
  
##  <a name="XamarinPlayer"></a>UDP bağlantı noktası ayarlanamadı çünkü öykünücüsü askıda kalır  
 Xamarin Player uyumsuzluk nedeniyle bu sorunla karşılaşabilirsiniz. Öykünücü askıda görünüyorsa veya bu hata iletisini görüyorsanız "öykünücü cihaz işletim sistemine bağlanamıyor: UDP bağlantı noktası ayarlanamadı.  Bazı işlevler devre dışı bırakılabilir", bu sorunu yaşıyor olabilir. Aşağıdaki adımları uygulayın.  
  
1.  Xamarin Player kaldırın.  
  
2.  Sanal kutunun kaldırılan (Xamarin Player çalışır sanal kutusunun üstünde) bırakıldı doğrulayın.  
  
3.  Aygıt Yöneticisi'ni gidin, gizli aygıtları göstermek için bu seçeneği belirleyin ve ardından fiziksel ağ kartları dışında her şeyi silin.  
  
4.  Kaldırma/Hyper-V olmayan fiziksel ağ bağdaştırıcısı kaldırdıktan sonra yeniden yüklemeyi deneyebilirsiniz.  
  
##  <a name="Skylake"></a>Hata ayıklayıcı Xamarin projesine eklenemiyor  
 Intel Skylake işlemcilere sahip Windows 10 çalıştırıyorsanız, Xamarin uygulamaları öykünücüsünde çalıştırmak başarısız olabilir veya Visual Studio hata ayıklayıcısı iliştirdiğiniz değil. Hyper-V ve Skylake işlemciler ile ilgili bir sorun nedeniyle budur. Geçici bir çözüm olarak aşağıdaki adımları uygulayın.  
  
1.  Hyper-V Yöneticisi'ni açın ve öykünücü profil için VM seçin olduğunuz kullanma.  
  
2.  Seçin **Delete kaydedilmiş durumu** (sağ alt köşesinde).  
  
3.  Seçin **ayarları...**  
  
4.  İşlemci düğümünü genişletin ve seçin **Uyumluluk**.  
  
5.  Etkinleştirme **farklı bir işlemci sürümü olan fiziksel bir bilgisayara geçirme**.  
  
6.  Hizmeti yeniden başlatın (altında **Eylemler**) ve yeniden deneyin.  
  
##  <a name="GooglePlay"></a>Google Play hizmetleri kullanan uygulamalarda öykünücüsü çalışmaz  
 Öykünücü kitaplıklarıyla Google Play Hizmetleri'ni gelmez. Ancak, öykünücü sürükle ve bırak yazılımına anlık olarak erişilebilen ZIP dosyaları yüklenmesini desteklemez.  
  
##  <a name="DragAndDrop"></a>Sürükle ve bırak dosya, APK veya yazılımına anlık olarak erişilebilen zip dosyası çalışmıyor  
 Öykünücü ADB.exe bir dosya ekran üzerine sürükleyip zaman dosya aktarımı kolaylaştırmak için kullanır. Bir dosya sürükleyip denediğinizde bir hatayla karşılaşırsanız, bu büyük olasılıkla öykünücü ADB.exe için bağlanmamış gösterir. Gidermek için adımları [Visual Studio öykünücüsü uygulama dağıtılmaya çalışılırken takılmış veya öykünücü diğer IDE hata ayıklama hedefi olarak görünmez](#ADB).  
  
##  <a name="Resolution"></a>Ekran çözünürlüğü yanlış  
 Ekran sekmesindeki kullanarak bir ekran görüntüsü alın, **ek araçlar** penceresi ve elde edilen görüntü beklenmeyen bir boyutu, ekran yakınlaştırma düzeyi seçmeden önce ayarlamanız gerekebilir **Yakalama**. Öykünücü ekran görüntüleri, ana bilgisayar monitör ekranda çözünürlükte alır.  
  
##  <a name="OpenGL"></a>OpenGL içeriğini işlemek öykünücüsü başarısız  
 Öykünücü konak makinenizin GPU kullanarak OpenGL içerik işler ve bu çağrıları DirectX gelen ve giden dönüştürmek için AÇI proje kullanır. Uygulamanız doğru bir aygıtı ancak yanlış öykünücü işliyorsa, cihaz bir OpenGL çağrısı yanlış (örneğin, eşleşmiyor gölgelendirici değişkenler kullanarak) için Azaltıcı olasıdır.  
  
##  <a name="Multitouch"></a>Öykünücü çok dokunma hareketleri yanıt vermiyor  
 Bazı durumlarda, öykünücü başlatın ve çok ya da ile doğrudan etkileşim Dokunmatik özellikli ekranınıza veya öykünücü araç çubuğunda çok dokunma aracını kullanarak yanıt değil. Bu durumda, seçin **Döndür** öykünücüsü araç çubuğunda düğmesini ve çok dokunma yeniden kullanmayı dener. Sorun devam ederse, okuma [öykünücüsü başarısız OpenGL içeriğini işlemek](#OpenGL) sorun.  
  
##  <a name="Support"></a>Destek kaynakları  
 Ana bilgisayarınız sistem gereksinimlerini karşıladığından ve bu sorun giderme Kılavuzu'nda kapsamında olmayan bir sorunla karşılaşırsanız ise:  
  
-   StackOverflow kullanarak bir soru sorun [android öykünücüsü](http://stackoverflow.com/questions/tagged/android-emulator) ve visual studio etiketler.  
  
-   Visual Studio'da veya Öykünücüsü Yöneticisi'nde gönderme gülümseme gönderme aracını kullanarak bir sorunu bildirin.