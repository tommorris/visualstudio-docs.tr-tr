---
title: "Platformlar arası Mobil Geliştirme için Visual C++ yüklemek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-mobile
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: aaea6b8d-55eb-4427-8185-c050f855c257
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: b9f87e95a2d4088bb72890ef3f9508d9c5e02abc
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="install-visual-c-for-cross-platform-mobile-development"></a>Platformlar arası Mobil Geliştirme için Visual C++ yüklemek
[Platformlar arası Mobil Geliştirme için Visual C++](http://go.microsoft.com/fwlink/p/?LinkId=536383) Visual Studio 2015 yüklenebilir bileşendir. Platformlar arası Visual Studio şablonları içerir ve bulun, indirin ve bunları kendiniz yapılandırmak zorunda kalmadan hızlıca başlamak için SDK'ları ve platformlar arası araçları yükler. Kolayca oluşturma, düzenleme, hata ayıklama ve test platformlar arası projeleri için Visual Studio'da bu araçları kullanabilirsiniz. Bu konuda, araçları ve Visual Studio kullanarak platformlar arası uygulamalar geliştirmek için gereken üçüncü taraf yazılım nasıl yükleneceği açıklanmaktadır. Bileşen genel bakış için bkz: [Visual C++ platformlar arası mobil](http://go.microsoft.com/fwlink/p/?LinkId=536387)  
  
 [Gereksinimleri](#Requirements)   
 [Araçları edinin](#GetTheTools)   
 [Araçları'nı yükleme](#InstallTheTools)   
 [İOS için araçlarını yükleme](#InstallForiOS)   
 [Yükleme veya bağımlılıkları el ile güncelleştirme](#ThirdParty)  
  
##  <a name="Requirements"></a>Gereksinimleri  
  
-   Yükleme gereksinimleri için bkz: [Visual Studio 2015 sistem gereksinimleri](https://www.visualstudio.com/visual-studio-2015-system-requirements-vs).  
  
    > [!IMPORTANT]
    >  Windows 7 veya Windows Server 2008 R2 kullanıyorsanız, Klasik Windows uygulamalarını, Android yerel etkinlik uygulamalar ve kitaplıklarını ve uygulamalar için kod ve iOS, ancak Windows mağazası veya evrensel Windows uygulamaları için kod kitaplıkları geliştirebilirsiniz.  
  
 Belirli cihaz platformları için uygulamalar oluşturmak için bazı ek gereksinimleri vardır:  
  
-   Windows Phone Öykünücüler ve Android için Microsoft Visual Studio öykünücüsü Hyper-V çalıştıran bir bilgisayar gerektirir. Windows Hyper-V özelliği yükleyip Öykünücüler çalıştırmak önce etkinleştirilmesi gerekir. Öykünücü ait daha fazla bilgi için bkz: [sistem gereksinimleri](http://msdn.microsoft.com/en-us/4d5bb438-231a-4cd2-84b7-e9660b0e3baf).  
  
-   Android SDK ile birlikte gelen Android öykünücüsünü en iyi Intel HAXM sürücü çalışabilir bilgisayarlarda çalışmasını x86. Bu sürücü bir Intel x64 işlemci VT-x ve devre dışı bırakma Bit yürütme desteği gerektirir. Daha fazla bilgi için bkz: [yükleme yönergeleri için Intel® donanım hızlandırılmış yürütme Yöneticisi - Microsoft Windows](http://go.microsoft.com/fwlink/p/?LinkId=536385).  
  
-   İOS için kod oluşturma gerektiren bir Apple kimliği, bir iOS Developer Program hesap ve çalıştırabilirsiniz bir Mac bilgisayara [Xcode 6](http://go.microsoft.com/fwlink/p/?LinkId=536387) veya daha sonra OS X Mavericks veya sonraki sürümler. Basit yükleme adımları için bkz: [yüklemek için iOS Araçları](#InstallForiOS).  
  
##  <a name="GetTheTools"></a>Araçları edinin  
 Platformlar arası Mobil Geliştirme için Visual C++, Visual Studio Community, Professional ve Enterprise sürümlerinde bulunan bir yüklenebilir bileşendir. Visual Studio almak için Git [Visual Studio 2015 indirmeleri](http://go.microsoft.com/fwlink/p/?linkid=517106) sayfasında ve Visual Studio 2015 güncelleştirme 2 veya sonraki sürümü indirin.  
  
##  <a name="InstallTheTools"></a>Araçları'nı yükleme  
 Visual Studio 2015 için yükleyiciyi platformlar arası Mobil Geliştirme için Visual C++ yüklemek için bir seçenek içerir. Bu, gerekli C++ dil araçları, şablonları ve Visual Studio, GCC ve Clang toolsets iOS geliştirme için bir Mac ile iletişim kurmak için Android yapılar ve hata ayıklama ve bileşenleri için gerekli bileşenleri yükler. Tüm üçüncü taraf araçları ve iOS ve Android uygulaması geliştirme desteklemek için gereken yazılım geliştirme setleri de yükler. Bu üçüncü taraf araçları Android platformu desteği için gerekli açık kaynaklı yazılım durumdadır.  
  
-   Android yerel Geliştirme Seti (NDK) Android platformu hedefleyen C++ kodu oluşturmak için gereklidir.  
  
-   Android SDK'sı, Apache Ant ve Java SE Geliştirme Seti Android derleme işlemi için gereklidir.  
  
-   Android için Microsoft Visual Studio öykünücüsü test ve kodunuzu hata ayıklama için yararlı bir isteğe bağlı yüksek performanslı öykünücüsü ' dir.  
  
#### <a name="to-install-visual-c-for-cross-platform-mobile-development-and-the-third-party-tools"></a>Platformlar arası mobil geliştirme ve üçüncü taraf araçları için Visual C++ yüklemek için  
  
1.  Aşağıdaki bağlantıyı indirdiğiniz Visual Studio 2015 yükleyiciyi çalıştırmak [araçları edinin](#GetTheTools). İsteğe bağlı bileşenleri yüklemek için tercih **özel** yükleme türü olarak. Seçin **sonraki** yüklemek için isteğe bağlı bileşenleri seçin.  
  
2.  Özellikleri Seç genişletin **platformlar arası mobil geliştirme** ve denetleme **Visual C++ mobil geliştirme**.  
  
     ![Visual C# 43; &#43;seçin; Mobil Geliştirme](../cross-platform/media/cppmdd_install_vcmdd.png "CPPMDD_Install_VCMDD")  
  
     Varsayılan olarak seçtiğinizde, **Visual C++ mobil geliştirme**, **programlama dilleri** yüklemek için seçeneği ayarlanmış **Visual C++**ve **ortak araçları ve yazılım geliştirme setleri** seçenekleri gerekli üçüncü taraf bileşenleri yüklemek için ayarlanır. Eğer gerekiyorsa, ek bileşenleri seçebilirsiniz. Varsayılan olarak, **Android için Microsoft Visual Studio öykünücüsü** da seçilir. Zaten yüklü olan bileşenleri listesinde etkin olmayan görünür.  
  
     Evrensel Windows uygulamaları oluşturma ve buna kod onlarla, Android ve iOS projeler arasında paylaşmak için **seçin özellikleri**, genişletin **Windows ve Web geliştirme** ve denetleme **Evrensel Windows uygulaması Geliştirme Araçları**. Evrensel Windows uygulamaları oluşturmak planlamıyorsanız, bu seçenek atlayabilirsiniz.  
  
     Seçin **sonraki** devam etmek için.  
  
3.  Üçüncü taraf bileşenleri kendi lisans koşulları'nı sahiptir. Lisans Koşulları'nı seçerek görüntüleyebilirsiniz **Lisans Koşulları'nı** her bileşenin yanındaki bağlantı. Seçin **yükleme** bileşenleri ekleyin ve platformlar arası Mobil Geliştirme için Visual Studio ve Visual C++ yüklemek için.  
  
4.  Yükleme tamamlandığında yükleyici kapatın ve bilgisayarınızı yeniden başlatın. Bazı kurulum eylemleri üçüncü taraf bileşenler için bilgisayar yeniden başlatılana kadar etkili olmaz.  
  
    > [!IMPORTANT]
    >  Her şeyin doğru şekilde yüklendiğinden emin olmak için yeniden başlatmanız gerekir.  
  
     Yüklemek Android bileşen için Microsoft Visual Studio öykünücüsü başarısız olursa, bilgisayarınızın Hyper-V etkin olmayabilir. Kullanım **kapatma Windows özelliklerini aç veya Kapat** Denetim Masası uygulaması Hyper-V etkinleştirip Visual Studio yükleyiciyi yeniden çalıştırın.  
  
    > [!NOTE]
    >  Bilgisayarınız veya Windows sürümünüz Hyper-V desteklemiyorsa, Android bileşen için Microsoft Visual Studio öykünücüsü kullanamazsınız. Home Edition, Windows Hyper-V desteği içermez.  
  
5.  Visual Studio'yu açın. Bu, Visual Studio çalıştırdığınız ilk kez ise, yapılandırma ve oturum açmak için biraz zaman alabilir. Visual Studio olduğunda hazır üzerinde **Araçları** menüsünde, select **Uzantılar ve güncelleştirmeler**, **güncelleştirmeleri**. Varsa Visual Studio kullanılabilir Visual C++ için Microsoft Visual Studio öykünücüsü veya platformlar arası Mobil Geliştirme için Android için güncelleştirmeler, bunları yükleyin.  
  
##  <a name="InstallForiOS"></a>İOS için araçlarını yükleme  
 Platformlar arası Mobil Geliştirme için Visual C++ düzenlemek, hata ayıklama ve iOS simülatörü'nü veya bir iOS aygıtı iOS kodu dağıtmak için kullanabilirsiniz, ancak lisans kısıtlamaları nedeniyle kodu uzaktan Mac'te oluşturulmalıdır Derleme ve Visual Studio kullanarak iOS uygulamaları çalıştırmak için ayarlama ve Mac üzerindeki uzak aracı yapılandırma Ayrıntılı yükleme yönergeleri, Önkoşullar ve yapılandırma seçenekleri için bkz: [yükleme ve yapılandırma araçları iOS kullanılarak derleme](../cross-platform/install-and-configure-tools-to-build-using-ios.md). İOS için değil oluşturuyorsanız, bu adımı atlayabilirsiniz.  
  
##  <a name="ThirdParty"></a>Yükleme veya bağımlılıkları el ile güncelleştirme  
 Bir yüklememeye karar veya Visual C++ mobil geliştirme seçeneği yüklediğinizde Visual Studio Yükleyicisi'ni kullanarak daha fazla üçüncü taraf bağımlılıkları, bunları daha sonra adımları kullanarak yükleyebilirsiniz [Araçları'nı yükleme](#InstallTheTools). Ayrıca, yükleme veya bağımsız olarak Visual Studio güncelleştirme.  
  
> [!CAUTION]
>  Java dışındaki herhangi bir sırada bağımlılıkları yükler. Yükleme ve Android SDK'yı yüklemeden önce JDK yapılandırmanız gerekir.  
  
 Aşağıdaki bilgileri okuyun ve bağımlılıkları el ile yüklemek için aşağıdaki bağlantıları kullanın.  
  
-   [Java SE Geliştirme Seti](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)  
  
     Varsayılan olarak, yükleyici Java Araçlar C:\Program Files (x86) \Java geçirir.  
  
-   [Android SDK'sı](https://developer.android.com/sdk/index.html#Other)  
  
     Yükleme sırasında API önerildiği şekilde güncelleştirin. En az emin olmak için Android 5.0 Lolipop (API düzeyi 21) SDK'sı yüklü. Varsayılan olarak, yükleyici Android SDK C:\Program Files (x86) \Android\android-sdk geçirir.  
  
     SDK Yöneticisi uygulamasının yeniden SDK'yi güncelleştirmek ve isteğe bağlı araçları ve ek API düzeylerini yüklemek için Android SDK'sı dizininde çalıştırabilirsiniz. Güncelleştirmeleri kullanmadığınız sürece yüklemek başarısız olabilir **yönetici olarak çalıştır** SDK Manager uygulamayı çalıştırmak için. Android uygulaması oluşturma sorunları varsa, güncelleştirmeler, yüklü SDK'ları için SDK Yöneticisi'ni denetleyin.  
  
     Android SDK ile birlikte gelen Android öykünücüsünü bazıları kullanmak için isteğe bağlı Intel HAXM sürücüleri yüklemeniz gerekir. Intel HAXM sürücüleri başarıyla yüklemek için Windows Hyper-V özelliği kaldırmak zorunda kalabilirsiniz. Windows Phone Öykünücüler ve Microsoft Visual Studio öykünücüsü Android için kullanmak üzere Hyper-V özelliği geri yüklemeniz gerekir.  
  
-   [Android NDK](https://developer.android.com/tools/sdk/ndk/index.html)  
  
     Varsayılan olarak, yükleyici Android NDK C:\ProgramData\Microsoft\AndroidNDK geçirir. İndirin ve Android NDK yükleme güncelleştirmeyi yeniden NDK yükleyin.  
  
-   [Apache Ant](http://ant.apache.org/bindownload.cgi)  
  
     Varsayılan olarak, yükleyici Apache Ant C:\Program Files (x86) \Microsoft Visual Studio 14.0\Apps geçirir.  
  
-   [Android için Microsoft Visual Studio öykünücüsü](http://go.microsoft.com/fwlink/p/?LinkId=536390)  
  
     Yükleyin ve Visual Studio Galerisi Android için Microsoft Visual Studio öykünücüsü güncelleştirin.  
  
 Çoğu durumda, Visual Studio yüklediniz ve iç ortam değişkenleri içindeki yükleme yolları tutar üçüncü taraf yazılım yapılandırmalarını algılayabilir. Bu platformlar arası geliştirme araçları Visual Studio IDE'de varsayılan yollarını geçersiz kılabilirsiniz.  
  
#### <a name="to-set-the-paths-for-third-party-tools"></a>Üçüncü taraf araçları için yollar ayarlamak için  
  
1.  Visual Studio menü çubuğunda seçin **Araçları**, **seçenekleri**.  
  
2.  İçinde **seçenekleri** iletişim kutusunda, genişletin **Çapraz Platform**, **C++**seçip **Android**.  
  
     ![Android aracı yolu seçenekleri](../cross-platform/media/cppmdd_options_android.PNG "CPPMDD_Options_Android")  
  
3.  Bir aracı tarafından kullanılan yolu değiştirmek için yolun yanındaki onay kutusunu işaretleyin ve klasör yolu metin kutusuna düzenleyin. Gözat düğmesini de kullanabilirsiniz (**...** ) açmak için bir **seçin konumu** iletişim klasörü seçin.  
  
4.  Seçin **Tamam** klasör konumlarını özel aracı kaydetmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İOS kullanılarak derleme ve Yapılandırma Araçları'nı yükleme](../cross-platform/install-and-configure-tools-to-build-using-ios.md)   
 [Visual C++ platformlar arası mobil](https://www.visualstudio.com/explore/cplusplus-mdd-vs.aspx)