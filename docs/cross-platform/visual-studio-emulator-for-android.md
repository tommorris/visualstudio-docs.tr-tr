---
title: Android için Visual Studio öykünücüsü | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.reviewer: ''
ms.suite: ''
ms.technology: vs-ide-mobile
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80f0104f-a4db-44dd-bd55-37bb67776c62
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4caa011bb0c7cdea3f9a1eed9e2eeb4adb089eb4
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="visual-studio-emulator-for-android"></a>Android için Visual Studio Öykünücüsü
Android için Visual Studio öykünücüsü bir Android cihaz öykünen bir masaüstü uygulamasıdır. Hata ayıklama ve bir fiziksel aygıt olmadan Android uygulamalarını test sanallaştırılmış bir ortam sağlar. Ayrıca, uygulama prototipleri için yalıtılmış bir ortam sağlar.  

> [!IMPORTANT]
> Çoğu senaryoda, Google Android öykünücüsü Android için Visual Studio öykünücüsü yerine kullanılması önerilir:
> - Android 7.0 veya üzeri, Android yayımlamak için herhangi bir plan olduğundan içeren öykünücü görüntülerinin ihtiyaç olduğunda sürüm 6.0 Android için Visual Studio öykünücüsü kullanmak için geçmiş görüntüler.
> - Apache Cordova için Visual Studio Araçları'nı kullanarak olduğunda. Daha fazla bilgi için bkz: [Apache Cordova uygulamanızı Android'de çalıştırma](/visualstudio/cross-platform/tools-for-cordova/run-your-app/run-app-android#a-idgoogle-android-emulatora-run-on-the-google-android-emulator).
  
 Android için Visual Studio öykünücüsü gerçek bir aygıt için karşılaştırılabilir performans sağlamak için tasarlanmıştır. Ancak, uygulamanızı yayınlamadan önce bir fiziksel cihaz üzerindeki uygulamanızı test etme öneririz.  
  
 Android platformları, ekran çözünürlükleri ve Android için Visual Studio öykünücüsü tarafından desteklenen diğer donanım özellikleri her bir benzersiz cihaz profili uygulamanıza test edebilirsiniz.
  
##  <a name="Installing"></a> Yükleme ve kaldırma  
 Yükleme  
  
 Android için Visual Studio öykünücüsü platformlar arası araçları Visual Studio'da kullanılabilir bir bileşenidir ve platformlar arası mobil geliştirme sonra ortak araçları ve yazılım geliştirme setleri seçtiğinizde özel bir Visual Studio Kurulumu sırasında yüklenecek ve ardından Visual Studio öykünücüsü Android için.  
  
 Kaldırma  
  
 Denetim Masası'ndaki Program Ekle/Kaldır kullanılarak Android için Visual Studio öykünücüsü kaldırabilirsiniz.  
  
> [!NOTE]
>  Visual Studio kaldırma öykünücü kaldırmaz. Öykünücü ayrı olarak kaldırmanız gerekir.  
  
 Android için Visual Studio öykünücüsü kaldırdığınızda, Hyper-V sanal Ethernet öykünücüsü kullanmak oluşturulan bağdaştırıcılarını otomatik olarak kaldırılmaz. Bu sanal bağdaştırıcılar (IF kullanılmadığı) Hyper-V Yöneticisi'ni açarak, öykünücüsü VHD görüntülerden birini seçerek, ağ sekmesini seçerek ve seçme el ile kaldırabilirsiniz **kaldırmak** bu sekmede görünür anahtarlardan her birinin için.  
  
##  <a name="Requirements"></a> Sistem gereksinimleri ve geriye dönük uyumluluk  
 Donanım, yazılım ve Android için Visual Studio öykünücüsü yapılandırma gereksinimleri hakkında önemli bilgiler için aşağıdaki konuya bakın.  
  
-   [Android için Visual Studio Öykünücüsü Sistem Gereksinimleri](../cross-platform/system-requirements-for-the-visual-studio-emulator-for-android.md)  
  
 Android için Visual Studio öykünücüsü, Visual Studio 2015 gerektirir; Visual Studio'nun önceki sürümleriyle geriye dönük olarak uyumlu değil.  
  
 Öykünücü yeni sürümlerini üstünde eski sürümlerinin yüklü olduğunu (ve bazı durumlarda, ayarları, uygulamalar ve dosyalar üzerinde bu görüntüleri yüklü atılıyor eski görüntülerini değiştirebilir).  
  
##  <a name="Networking"></a> Android için Visual Studio öykünücüsü'de ağ iletişimi  
 Android için Visual Studio öykünücüsü ' ağ bağlantısı bu özelliklere sahip bir masaüstü bilgisayar bağlantı gibi davranır:  
  
-   Öykünücü ağda ayrı bir aygıta kendi IP adresiyle olarak görünür.  
  
-   Öykünücü ile yüklü olmayan herhangi bir ek ağ yazılım gerektirmez.  
  
-   Bir Windows etki alanına katılmamış.  
  
 Öykünücü'nın ağ bağlantısı özellikleri anlamak için bunu Android telefonunuzu aynı ağa kullanarak Wi-Fi bağlantısı için benzer olarak düşünün. Telefonunuzda çalışan bir uygulama, bir ağ kaynağı kendi Wi-Fi bağlantısı üzerinden erişebiliyorsa öykünücüsünde çalışan bir uygulama da aynı ağ kaynağa erişebilir.  
  
 Ağ gereksinimleri hakkında daha fazla bilgi için bkz: [Android için Visual Studio öykünücüsü sistem gereksinimleri](../cross-platform/system-requirements-for-the-visual-studio-emulator-for-android.md)  
  
 Ağ sorunlarını giderme hakkında daha fazla bilgi için bkz [Android için Visual Studio öykünücüsü sorun giderme](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md).  
  
##  <a name="Configuring"></a> Android için Visual Studio öykünücüsü yapılandırın  
 Android donanım şaşırtıcı çeşitli arasında Android uygulamanızı uyumluluk için test zor olabilir. Android telefonlar ve tabletler pazardaki çok çeşitli sürümleri ve ekran boyutlarına span ve birçok farklı donanım yapılandırmalarında (RAM, CPU'lar, mimarisi, vb.) gelir. Android için Visual Studio öykünücüsü bu cihaz profillerini kullanarak basitleştirir. Cihaz profili bizim kümesini aygıtlar Samsung, Motorola, Sony LG ve daha fazlası dahil olmak üzere, piyasadaki en popüler donanım temsil eder.  
  
 Visual Studio 2015'te yüklemek, kaldırmak ve Öykünücüsü Yöneticisi'ni kullanarak cihaz profillerini başlatın. Öykünücü yöneticisini seçerek erişim **Araçları**, ardından **Android için Visual Studio öykünücüsü**.  
  
 ![Android Manager için Visual Studio öykünücüsü](../cross-platform/media/android_emu_manager.png "Android_Emu_Manager")  
  
 Varsayılan olarak, dört önceden yüklenmiş aygıt profilleri vardır (KitKat ve Lolipop telefon/5 "ve tablet/7" yapılandırmaları), simgeler ve beyaz metin tarafından belirtildiği şekilde. Seçtiğiniz kadar diğer profiller listede gri renkte görüntülenir **yükleme profili** düğmesi ve yüklemeyi tamamlar. API düzeyine göre listesini filtrelemek ve tam yapılandırma ayrıntılarını görüntülemek için bir profil alt sağ tarafındaki ayrıntıları oka tıklayın.  
  
 Hedeflemek istediğiniz profilleri kümesine yükledikten sonra bu yeni profiller doğrudan Manager'dan yeşil tuşlarına basarak başlatabilirsiniz **Yürüt** düğmesi. Hata ayıklama hedefi açılır menüde herhangi bir Visual Studio platformlar arası mobil proje türü de görüntülenir.  
  
##  <a name="FeaturesTest"></a> Öykünücüde test edebilirsiniz özellikleri  
 Bu öykünücüde test edebilirsiniz özellikleri hakkında ayrıntılı bilgi için bkz [blog gönderisi](http://blogs.msdn.com/b/visualstudioalm/archive/2014/11/12/introducing-visual-studio-s-emulator-for-android.aspx).  
  
##  <a name="FeaturesNonTest"></a> Öykünücüde test edilemez özellikleri  
 Aşağıdaki listede Android platformu özelliklerini açıklar, **olamaz** öykünücüde test edin. Bu özellikler bir fiziksel cihaz üzerindeki test gerekir.  
  
-   Pusula  
  
-   Jiroskop  
  
-   Titreşim denetleyicisi  
  
-   Parlaklığını. Öykünücü parlaklığını düzeyini değiştirme görsel olarak cihaz ekranınızda görüntülenme şeklini etkilemez.  
  
##  <a name="Support"></a> Destek kaynakları  
 Ana bilgisayarınız sistem gereksinimlerini karşıladığından ve bu sorun giderme Kılavuzu'nda kapsamında olmayan bir sorunla karşılaşırsanız ise:  
  
-   StackOverflow kullanarak bir soru sorun [android öykünücüsü](http://stackoverflow.com/questions/tagged/android-emulator) ve visual studio etiketi.  
  
-   Visual Studio'da veya Öykünücüsü Yöneticisi'nde gönderme gülümseme gönderme aracını kullanarak bir sorunu bildirin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Android için Visual Studio öykünücüsü sistem gereksinimleri](../cross-platform/system-requirements-for-the-visual-studio-emulator-for-android.md)   
 [Android için Visual Studio Öykünücüsü’nde Sorun Giderme](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md)
