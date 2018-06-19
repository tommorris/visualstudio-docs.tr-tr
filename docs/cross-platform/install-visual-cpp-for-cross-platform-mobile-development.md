---
title: Platformlar arası Mobil Geliştirme için Visual C++ yüklemek | Microsoft Docs
ms.custom: ''
ms.date: 05/21/2018
ms.technology: vs-ide-mobile
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: aaea6b8d-55eb-4427-8185-c050f855c257
author: corob-msft
ms.author: corob
manager: douge
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: 5013f1ce5ed9c20ba51feef7dd73d80adc152103
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34454707"
---
# <a name="install-cross-platform-mobile-development-with-c"></a>C++ ile platformlar arası mobil geliştirme yükleyin

Visual Studio'da C++, Android ve iOS için Windows Masaüstü uygulamaları, Evrensel Windows Platformu (UWP) uygulamalarını, Linux uygulamaları ve şimdi, uygulamaları oluşturmak için kullanabilirsiniz. **C++ ile Mobil Geliştirme** iş yükü kümesidir yüklenebilir bileşenleri platformlar arası iOS, Android ve UWP Visual Studio içeren Visual Studio şablonları. Platformlar arası araç ve SDK bulun, indirin ve bunları kendiniz yapılandırmak zorunda kalmadan hızlıca başlamak için ihtiyacınız yükler. Visual Studio'da bu araçları kullanın kolayca oluşturma, düzenleme, hata ayıklama ve platformlar arası projelerinizi sınayın. Bu konuda, araçları ve Visual Studio kullanarak c++ platformlar arası uygulamalar geliştirmek için gereken üçüncü taraf yazılım nasıl yükleneceği açıklanmaktadır. Genel bir bakış için bkz: [Visual C++ platformlar arası mobil](https://go.microsoft.com/fwlink/p/?LinkId=536383)

## <a name="requirements"></a>Gereksinimler

- Yükleme gereksinimleri için bkz: [Visual Studio ürün ailesi sistem gereksinimleri](https://www.visualstudio.com/productinfo/vs2017-system-requirements-vs).

   > [!IMPORTANT]
   > Windows 7 veya Windows Server 2008 R2 kullanıyorsanız, Windows Masaüstü uygulamaları, Android yerel etkinlik uygulamalar ve kitaplıklarını ve uygulamalar için kod ve iOS ancak olmayan Windows Phone veya UWP uygulamaları için kod kitaplıkları geliştirebilirsiniz.

Belirli cihaz platformları için uygulamalar oluşturmak için bazı ek gereksinimleri vardır:

- Windows Phone Öykünücüler ve Android için Microsoft Visual Studio öykünücüsü Hyper-V çalıştıran bir bilgisayar gerektirir. Windows Hyper-V özelliği yükleyip Öykünücüler çalıştırmak önce etkinleştirilmesi gerekir. Öykünücü ait daha fazla bilgi için bkz: [sistem gereksinimleri](system-requirements-for-the-visual-studio-emulator-for-android.md).

- Android SDK ile birlikte gelen Android öykünücüsünü en iyi Intel HAXM sürücü çalışabilir bilgisayarlarda çalışmasını x86. Bu sürücü bir Intel x64 işlemci VT-x ve devre dışı bırakma Bit yürütme desteği gerektirir. Daha fazla bilgi için bkz: [Intel® donanım hızlandırılmış yürütme Yöneticisi'ni (Intel® HAXM)](https://go.microsoft.com/fwlink/p/?LinkId=536385).

- İOS için kod oluşturma gerektiren bir Apple kimliği, bir iOS Developer Program hesap ve çalıştırabilirsiniz bir Mac bilgisayara [Xcode](https://go.microsoft.com/fwlink/p/?LinkId=536387) sürüm 6 veya daha sonra OS X Mavericks (sürüm 10.9) veya sonraki sürümler. Yükleme adımlarını bağlantı için bkz: [yüklemek için iOS Araçları](#install-tools-for-ios).

## <a name="get-the-tools"></a>Araçları edinin

C++ ile mobil geliştirme Visual Studio Community, Professional ve Enterprise sürümlerinde kullanılabilir. Visual Studio almak için Git [Visual Studio indirmeleri](https://go.microsoft.com/fwlink/p/?linkid=517106) sayfası. Platformlar arası mobil geliştirme araçlarını Visual Studio 2015 güncelleştirme 2 veya sonraki sürümlerde başlayarak kullanılabilir.

## <a name="install-the-tools"></a>Araçları'nı yükleme

Visual Studio 2017 için Visual Studio yükleyicisi içeren bir **C++ ile Mobil Geliştirme** C++ dil araçları, şablonları ve Visual Studio Android ve iOS geliştirme için gerekli bileşenleri yükler iş yükü. İOS geliştirme için bir Mac ile iletişim kurmak için Android yapılar ve hata ayıklama ve bileşenleri için gerekli GCC ve Clang toolsets yükler. Tüm üçüncü taraf araçları ve iOS ve Android uygulaması geliştirme desteklemek için gereken yazılım geliştirme setleri de yükler. Bu üçüncü taraf araçları Android platformu desteği için gerekli açık kaynaklı yazılım durumdadır.

- Android yerel Geliştirme Seti (NDK) Android platformu hedefleyen C++ kodu oluşturmak için gereklidir.

- Android SDK'sı, Apache Ant ve Java SE Geliştirme Seti Android derleme işlemi için gereklidir.

- Google Android öykünücüsü ve Intel donanım hızlandırılmış yürütme Yöneticisi isteğe bağlıdır, ancak önerilen, bileşenleri. Geliştir ve doğrudan Android cihazında hata ayıklama, ancak genellikle hata ayıklama için masaüstünde bir öykünücü kullanmak daha kolay olur. Microsoft Visual Studio öykünücüsü ayrı olarak yüklenebilir Android için de sağlar.

#### <a name="to-install-the-mobile-development-with-c-workload-in-visual-studio-2017"></a>Visual Studio 2017 C++ yükündeki mobil geliştirme yüklemek için

1. Çalıştırma **Visual Studio yükleyicisi** gelen **Başlat** menüsü.

1. Visual Studio'nun zaten yüklediyseniz, seçin **Değiştir** düğmesi için Visual Studio değiştirmek istediğiniz yüklü sürümü. Aksi takdirde seçin **yükleme** Visual Studio'yu yüklemek için.

1. İle **iş yükleri** sekmesi seçili, seçin ve aşağı kaydırma **C++ ile Mobil Geliştirme** Visual Studio yükleyicisi iş yükü. Bu iş yükü seçildiğinde, C++ geliştirme için gereken diğer bileşenleri de seçilir. Ayrıca, diğer iş yükleri ve aynı anda yüklenecek bileşenleri tek tek seçebilirsiniz. Ayrıca UWP hedefleyen platformlar arası kod oluşturmak için seçin **Evrensel Windows platformu geliştirme** iş yükü.

1. İçinde **Yükleme ayrıntıları** bölmesini genişletin **C++ ile Mobil Geliştirme**. İçinde **isteğe bağlı** bölümünde, ek sürümlerini NDK, Google Android öykünücüsü, Intel donanım hızlandırılmış yürütme Yöneticisi'ni seçebilirsiniz ve IncrediBuild yapı hızlandırma aracı.

1. Varsayılan olarak, bir veya daha fazla Android SDK kurulum bileşenleri iş yükü dahil edilir. Android SDK'sı ek sürümlerinde kullanılabilir. Yüklemenizi birine eklemek için **bileşenleri tek tek** sekmesini ve sonra aşağı kaydırarak **SDK'ları, kitaplıklarını ve çerçevelerini** bölüm seçiminizi yapın.

1. Seçin **Değiştir** veya **yükleme** yüklemek için düğmeyi **C++ ile Mobil Geliştirme** iş yükü ve diğer seçili iş yükleri ve isteğe bağlı bileşenler.

   Yükleme tamamlandığında yükleyici kapatın ve bilgisayarınızı yeniden başlatın. Bazı kurulum eylemleri üçüncü taraf bileşenler için bilgisayar yeniden başlatılana kadar etkili olmaz.

   > [!IMPORTANT]
   > Her şeyin doğru şekilde yüklendiğinden emin olmak için yeniden başlatmanız gerekir.

1. Visual Studio'yu açın. Bu, Visual Studio çalıştırdığınız ilk kez ise, yapılandırma ve oturum açmak için biraz zaman alabilir. Visual Studio hazır olduğunda, tüm güncelleştirmeleri denetlemek ve onları yükleyin.

#### <a name="to-install-the-mobile-development-component-and-third-party-tools-in-visual-studio-2015"></a>Visual Studio 2015'te mobil geliştirme bileşeni ve üçüncü taraf araçları yüklemek için

Visual Studio 2015 kullanıyorsanız, yükleyicisi Visual Studio 2015'te gerekli C++ dil araçları, şablonları ve bileşenleri yükler platformlar arası Mobil Geliştirme için Visual C++ yüklemek için bir seçenek içerir.

1. Visual Studio 2015 yükleyiciyi çalıştırın. İsteğe bağlı bileşenleri yüklemek için tercih **özel** yükleme türü olarak. Seçin **sonraki** yüklemek için isteğe bağlı bileşenleri seçin.

1. İçinde **seçin özellikleri**, genişletin **platformlar arası mobil geliştirme** ve denetleme **Visual C++ mobil geliştirme**.

   ![Visual C seçin&#43; &#43; mobil geliştirme](../cross-platform/media/cppmdd_install_vcmdd.png "CPPMDD_Install_VCMDD")

   Varsayılan olarak seçtiğinizde, **Visual C++ mobil geliştirme**, **programlama dilleri** yüklemek için seçeneği ayarlanmış **Visual C++** ve **ortak araçları ve yazılım geliştirme setleri** seçenekleri gerekli üçüncü taraf bileşenleri yüklemek için ayarlanır. Eğer gerekiyorsa, ek bileşenleri seçebilirsiniz. Varsayılan olarak, **Android için Microsoft Visual Studio öykünücüsü** da seçilir. Zaten yüklü olan bileşenleri listesinde etkin olmayan görünür.

   Evrensel Windows uygulamaları oluşturma ve buna kod onlarla, Android ve iOS projeler arasında paylaşmak için **seçin özellikleri**, genişletin **Windows ve Web geliştirme** ve denetleme **Evrensel Windows uygulaması Geliştirme Araçları**. Evrensel Windows uygulamaları oluşturmak planlamıyorsanız, bu seçenek atlayabilirsiniz.

   Seçin **sonraki** devam etmek için.

1. Üçüncü taraf bileşenleri kendi lisans koşulları'nı sahiptir. Lisans Koşulları'nı seçerek görüntüleyebilirsiniz **Lisans Koşulları'nı** her bileşenin yanındaki bağlantı. Seçin **yükleme** bileşenleri ekleyin ve platformlar arası Mobil Geliştirme için Visual Studio ve Visual C++ yüklemek için.

1. Yükleme tamamlandığında yükleyici kapatın ve bilgisayarınızı yeniden başlatın. Bazı kurulum eylemleri üçüncü taraf bileşenler için bilgisayar yeniden başlatılana kadar etkili olmaz.

   > [!IMPORTANT]
   > Her şeyin doğru şekilde yüklendiğinden emin olmak için yeniden başlatmanız gerekir.

   Yüklemek Android bileşen için Microsoft Visual Studio öykünücüsü başarısız olursa, bilgisayarınızın Hyper-V etkin olmayabilir. Kullanım **kapatma Windows özelliklerini aç veya Kapat** Denetim Masası uygulaması Hyper-V etkinleştirip Visual Studio yükleyiciyi yeniden çalıştırın.

   > [!NOTE]
   > Bilgisayarınız veya Windows sürümünüz Hyper-V desteklemiyorsa, Android bileşen için Microsoft Visual Studio öykünücüsü kullanamazsınız. Home Edition, Windows Hyper-V desteği içermez.

1. Visual Studio'yu açın. Bu, Visual Studio çalıştırdığınız ilk kez ise, yapılandırma ve oturum açmak için biraz zaman alabilir. Visual Studio olduğunda hazır üzerinde **Araçları** menüsünde, select **Uzantılar ve güncelleştirmeler**, **güncelleştirmeleri**. Varsa Visual Studio kullanılabilir Visual C++ için Microsoft Visual Studio öykünücüsü veya platformlar arası Mobil Geliştirme için Android için güncelleştirmeler, bunları yükleyin.

## <a name="install-tools-for-ios"></a>İOS için araçlarını yükleme

Platformlar arası Mobil Geliştirme için Visual C++ düzenlemek, hata ayıklama ve iOS simülatörü'nü veya bir iOS aygıtı iOS kodu dağıtmak için kullanabilirsiniz, ancak lisans kısıtlamaları nedeniyle kodu uzaktan Mac'te oluşturulmalıdır Derleme ve Visual Studio kullanarak iOS uygulamaları çalıştırmak için ayarlama ve Mac üzerindeki uzak aracı yapılandırma Ayrıntılı yükleme yönergeleri, Önkoşullar ve yapılandırma seçenekleri için bkz: [yükleme ve yapılandırma araçları iOS kullanılarak derleme](install-and-configure-tools-to-build-using-ios.md). İOS için değil oluşturuyorsanız, bu adımı atlayabilirsiniz.

## <a name="install-or-update-dependencies-manually"></a>Yükleme veya bağımlılıkları el ile güncelleştirme

Bir yüklememeye karar verirseniz veya yüklediğinizde Visual Studio Yükleyicisi'ni kullanarak daha fazla üçüncü taraf bağımlılıkları **C++ ile Mobil Geliştirme** iş yükü (veya Visual Studio 2015, Visual C++ mobil geliştirme seçeneği), bunları daha sonra adımları kullanarak yükleyebilirsiniz. [Araçları'nı yükleme](#install-the-tools). Visual Studio yükleyicisi, en son üçüncü taraf bileşenleri yüklemek için düzenli olarak güncelleştirilir. Güncelleştirilmiş SDK'lar ve NDKs yüklemek için kullanabilirsiniz. Ayrıca, yükleme veya bağımsız olarak Visual Studio güncelleştirme.

> [!CAUTION]
> Java dışındaki herhangi bir sırada bağımlılıkları yükler. Yükleme ve Android SDK'yı yüklemeden önce JDK yapılandırmanız gerekir.

Aşağıdaki bilgileri okuyun ve bağımlılıkları el ile yüklemek için aşağıdaki bağlantıları kullanın.

- [Java SE Geliştirme Seti](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

   Varsayılan olarak, yükleyici Java Araçlar C:\Program Files (x86) \Java geçirir.

- [Android SDK'sı](https://developer.android.com/sdk/index.html#command-tools)

   Yükleme sırasında API önerildiği şekilde güncelleştirin. En az emin olmak için Android 5.0 Lolipop (API düzeyi 21) SDK'sı yüklü. Varsayılan olarak, yükleyici Android SDK C:\Program Files (x86) \Android\android-sdk geçirir.

   SDK Yöneticisi uygulamasının yeniden SDK'yi güncelleştirmek ve isteğe bağlı araçları ve ek API düzeylerini yüklemek için Android SDK'sı dizininde çalıştırabilirsiniz. Güncelleştirmeleri kullanmadığınız sürece yüklemek başarısız olabilir **yönetici olarak çalıştır** SDK Manager uygulamayı çalıştırmak için. Android uygulaması oluşturma sorunları varsa, güncelleştirmeler, yüklü SDK'ları için SDK Yöneticisi'ni denetleyin.

   Android SDK ile birlikte gelen Android öykünücüsünü bazıları kullanmak için isteğe bağlı Intel HAXM sürücüleri yüklemeniz gerekir. Intel HAXM sürücüleri başarıyla yüklemek için Windows Hyper-V özelliği kaldırmak zorunda kalabilirsiniz. Windows Phone Öykünücüler ve Microsoft Visual Studio öykünücüsü Android için kullanmak üzere Hyper-V özelliği geri yüklemeniz gerekir. Daha fazla bilgi için bkz: [Android öykünücüsü donanım hızlandırmasını](https://docs.microsoft.com/xamarin/android/get-started/installation/android-emulator/hardware-acceleration?tabs=vswin).

- [Android NDK](https://developer.android.com/tools/sdk/ndk/index.html)

   Varsayılan olarak, yükleyici Android NDK C:\ProgramData\Microsoft\AndroidNDK geçirir. İndirin ve Android NDK yükleme güncelleştirmeyi yeniden NDK yükleyin.

- [Apache Ant](https://ant.apache.org/bindownload.cgi)

   Varsayılan olarak, yükleyici Apache Ant C:\Program Files (x86) \Microsoft Visual Studio 14.0\Apps geçirir.

- [Android için Microsoft Visual Studio öykünücüsü](https://aka.ms/vscomemudownload)

   Android için Microsoft Visual Studio öykünücüsü bir isteğe bağlı öykünücü test ve kodunuzu hata ayıklama için yararlı olur. Sürümünden Visual Studio öykünücüsü sonra Android için Google, Android öykünücüsü güncelleştirilmiş donanım hızlandırmasını Intel aracılığıyla kullanmak için kullanıcının HAXM. Yapabilecekleriniz olduğunda en son Android işletim sistemi görüntüleri ve Google Play erişim hizmetleri sunar olarak Google hızlandırılmış öykünücüsü kullanmanızı öneririz.

Çoğu durumda, Visual Studio yüklediniz ve iç ortam değişkenleri içindeki yükleme yolları tutar üçüncü taraf yazılım yapılandırmalarını algılayabilir. Bu platformlar arası geliştirme araçları Visual Studio IDE'de varsayılan yollarını geçersiz kılabilirsiniz.

#### <a name="to-set-the-paths-for-third-party-tools"></a>Üçüncü taraf araçları için yollar ayarlamak için

1. Visual Studio menü çubuğunda seçin **Araçları** > **seçenekleri**.

1. İçinde **seçenekleri** iletişim kutusunda **Çapraz Platform** > **C++** > **Android**.

   ![Android aracı yolu seçenekleri](../cross-platform/media/cppmdd_options_android.PNG "CPPMDD_Options_Android")

1. Bir aracı tarafından kullanılan yolu değiştirmek için yolun yanındaki onay kutusunu işaretleyin ve klasör yolu metin kutusuna düzenleyin. Gözat düğmesini de kullanabilirsiniz (**...** ) açmak için bir **seçin konumu** iletişim klasörü seçin.

1. Seçin **Tamam** klasör konumlarını özel aracı kaydetmek için.

## <a name="see-also"></a>Ayrıca Bkz.

- [İOS Kullanarak Derlemeye Yönelik Araçları Yükleme ve Yapılandırma](install-and-configure-tools-to-build-using-ios.md)
- [Visual C++ platformlar arası mobil](https://go.microsoft.com/fwlink/p/?LinkId=536383)
