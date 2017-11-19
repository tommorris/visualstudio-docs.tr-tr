---
title: "Android ve iOS üzerinde bir OpenGL ES uygulaması oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 76a67886-df57-4a81-accb-2e3c2eaf607b
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 80463925da89165a569b1e6317ef8b1b22c77514
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="build-an-opengl-es-application-on-android-and-ios"></a>Android ve iOS üzerinde bir OpenGL ES uygulaması oluşturma
Platformlar arası mobil geliştirme seçeneği için Visual C++ yüklediğinizde Visual Studio çözümler ve projeler iOS uygulamaları ve ortak kod paylaşmak Android uygulamaları için oluşturabilirsiniz. Bu konuda, basit iOS uygulaması hem yerel Android etkinlik uygulama oluşturan bir çözüm şablonu aracılığıyla size yol gösterir. C++ kodu, uygulamaların aynı animasyonlu döndürme küp her platformda görüntülemek için OpenGL ES kullanan ortak vardır. OpenGL ES (OpenGL Embedded Systems veya GLES) bir 2B ve 3B grafik birçok mobil cihazlarda desteklenen API uygundur.  
  
 [Gereksinimleri](#req)   
 [Yeni bir OpenGLES uygulama projesi oluşturma](#Create)   
 [Derleme ve Android uygulamanızı çalıştırma](#BuildAndroid)   
 [Derleme ve iOS uygulamasını çalıştırma](#BuildIOS)   
 [Uygulamalarınızı özelleştirme](#Customize)  
  
##  <a name="req"></a>Gereksinimleri  
 İOS ve Android için OpenGL ES uygulamayı oluşturmadan önce tüm sistem gereksinimlerini karşılamanızın emin olmanız gerekir. Visual Studio 2015'te Visual C++ platformlar arası mobil geliştirme seçeneği için yüklemeniz gerekir. SDK'ları ve gerekli üçüncü taraf araçları yüklemeye dahil edilir ve Android için Visual Studio öykünücüsü yüklü olduğundan emin olun. Daha fazla bilgi ve ayrıntılı yönergeler için bkz: [platformlar arası Mobil Geliştirme için Visual C++ yüklemek](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md). Derleme ve test iOS uygulaması için bir Mac gerekir bilgisayar, yükleme yönergelerine göre ayarlayın. İOS geliştirme için ayarlama hakkında daha fazla bilgi için bkz: [yükleme ve yapılandırma araçları iOS kullanarak derleme](../cross-platform/install-and-configure-tools-to-build-using-ios.md)  
  
##  <a name="Create"></a>Yeni bir OpenGLES uygulama projesi oluşturma  
 Bu öğreticide, önce yeni bir OpenGL ES uygulama projesi oluşturun ve ardından oluşturup varsayılan uygulama Visual Studio öykünücüsü Android için çalıştırın. Sonraki iOS için uygulama oluşturun ve uygulamayı iOS Simulator'da çalıştırın.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Visual Studio'yu açın. Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **şablonları**, seçin **Visual C++**, **Çapraz Platform**ve ardından  **OpenGLES uygulama (Android, iOS)** şablonu.  
  
3.  Uygulama gibi bir ad verin `MyOpenGLESApp`ve ardından **Tamam**.  
  
     ![Yeni OpenGLES uygulama projesi](../cross-platform/media/cppmdd_opengles_newproj.PNG "CPPMDD_OpenGLES_NewProj")  
  
     Visual Studio yeni çözüm oluşturur ve Çözüm Gezgini açar.  
  
     ![Çözüm Gezgini'nde MyOpenGLESApp](../cross-platform/media/cppmdd_opengles_solexpl.PNG "CPPMDD_OpenGLES_SolExpl")  
  
 Yeni bir OpenGL ES uygulaması çözümü üç kitaplık projeleri ve iki uygulama projeleri içerir. Paylaşılan kod projesi ve paylaşılan kod başvurmak iki platforma özgü projeleri kitaplıkları klasör içerir:  
  
-   **MyOpenGLESApp.Android.NativeActivity** başvuruları ve uygulamanızı android'de yerel bir etkinlik olarak uygulayan Birleştirici kodunu içerir. Giriş noktaları Birleştirici kodundan uyarlamasını MyOpenGLESApp.Shared içinde ortak paylaşılan kodu içerir main.cpp olan. Önceden derlenmiş üst bilgiler pch.h içinde ' dir. Bu yerel etkinlik uygulama projesi MyOpenGLESApp.Android.Packaging projenin toplanma bir paylaşılan kitaplık (.so) dosyası derlenir.  
  
-   **MyOpenGLESApp.iOS.StaticLibrary** MyOpenGLESApp.Shared paylaşılan kodu içeren bir iOS statik kitaplık (bir) dosyası oluşturur. MyOpenGLESApp.iOS.Application projesi tarafından oluşturulan uygulama bağlandı.  
  
-   **MyOpenGLESApp.Shared** platformlarında çalışır paylaşılan kodunu içerir. Önişlemci makroları platforma özgü kodu koşullu derleme için kullanır. Paylaşılan kod MyOpenGLESApp.Android.NativeActivity ve MyOpenGLESApp.iOS.StaticLibrary proje başvurusu tarafından toplanma.  
  
 Çözüm, Android ve iOS platformlarında uygulamalar oluşturmak için iki proje içerir:  
  
-   **MyOpenGLESApp.Android.Packaging** bir Android cihaz veya öykünücü üzerinde dağıtım için .apk dosyası oluşturur. Bu, kaynakları ve bildirim özellikleri ayarladığınız AndroidManifest.xml dosyasında içerir. Ayrıca, Ant oluşturma işlemi denetimleri build.xml dosyası içerir. Böylece dağıtılan ve doğrudan Visual Studio'dan çalıştırma başlangıç projesi olarak varsayılan olarak ayarlanır.  
  
-   **MyOpenGLESApp.iOS.Application** kaynakları ve içinde MyOpenGLESApp.iOS.StaticLibrary C++ statik kitaplık kodu bağlanan bir iOS uygulaması oluşturmak için Objective-C Birleştirici kodunu içerir. Bu proje için Mac Visual Studio ve uzak aracı tarafından aktarılan bir yapı paketi oluşturur. Bu proje oluşturma sırasında dosya ve komutları oluşturmak ve Mac üzerinde uygulamanızı dağıtmak için Visual Studio gönderir  
  
##  <a name="BuildAndroid"></a>Derleme ve Android uygulamanızı çalıştırma  
 Şablon tarafından oluşturulan çözüm Android uygulamasını varsayılan proje olarak ayarlar.  Derleme ve yükleme ve Kurulum doğrulamak için bu uygulamayı çalıştırın. İlk test için Android için Visual Studio öykünücüsü tarafından yüklenen aygıt profillerinden birini uygulamayı çalıştırın. Başka bir hedef uygulamanızı test etmek isterseniz, hedef öykünücüsü yükünü ya da cihaz bilgisayarınıza bağlayın.  
  
#### <a name="to-build-and-run-the-android-native-activity-app"></a>Derleme ve Android yerel etkinlik uygulamayı çalıştırmak için  
  
1.  Zaten seçili değilse seçin **x86** gelen **çözüm platformları** aşağı açılan liste.  
  
     ![Çözüm platformu için x86 ayarlamak](../cross-platform/media/cppmdd_opengles_solutionplat.png "CPPMDD_OpenGLES_SolutionPlat")  
  
     X86 için Android öykünücüsü Windows hedeflemek için kullanın. Bir aygıt hedefliyorsanız, cihaz işlemcisini esas alan çözüm platformu seçin. Varsa **çözüm platformları** listesi görüntülenmiyorsa, seçin **çözüm platformları** gelen **Ekle/Kaldır düğmelerini** listesinde ve platformunuzu seçin.  
  
2.  İçinde **Çözüm Gezgini**, MyOpenGLESApp.Android.Packaging proje için kısayol menüsünü açın ve ardından **yapı**.  
  
     ![Android paketleme projeyi](../cross-platform/media/cppmdd_opengles_andbuild.png "CPPMDD_OpenGLES_AndBuild")  
  
     Android paylaşılan kitaplığı ve Android uygulaması için çıkış penceresini yapı işlemi çıktısını görüntüler.  
  
     ![Android projeler için çıktı yapı](../cross-platform/media/cppmdd_opengles_andoutput.png "CPPMDD_OpenGLES_AndOutput")  
  
3.  VS öykünücüsü birini Android telefonunuzu (x86) profilleri dağıtım hedefi olarak seçin.  
  
     ![Dağıtım hedefini seçin](../cross-platform/media/cppmdd_opengles_pickemulator.png "CPPMDD_OpenGLES_PickEmulator")  
  
     Diğer Öykünücüler yüklediyseniz veya bir Android cihazı bağlı değilse, dağıtım hedef aşağı açılan listeden seçebilirsiniz. Uygulamayı çalıştırmak için yerleşik Çözüm Platformu hedef cihaz platformunun eşleşmesi gerekir.  
  
4.  Hata ayıklamayı başlatmak için F5'e ya da hata ayıklama olmadan başlatmak için Shift + F5'e basın.  
  
     Visual Studio Yük ve kodunuzu dağıtmak için birkaç saniye sürer öykünücüyü başlatır. İşte nasıl Android için Visual Studio öykünücüsü uygulama görünür.  
  
     ![Android öykünücüsünde çalışan uygulama](../cross-platform/media/cppmdd_opengles_andemulator.png "CPPMDD_OpenGLES_AndEmulator")  
  
     Uygulamanızı başladıktan sonra kesme noktalarını ayarlayın ve kod üzerinden adım, Yereller inceleyin ve değerleri izlemek için hata ayıklayıcı kullanın.  
  
5.  Shift + hata ayıklamayı durdurmak için F5 tuşuna basın.  
  
     Öykünücü çalışmaya devam eder ayrı bir işlemdir. Düzenleme, derleme ve kodunuzu birden çok kez aynı öykünücüsü dağıtma. Uygulamanızı öykünücü üzerinde uygulama koleksiyonu görünür ve bunu doğrudan buradan başlatılabilir.  
  
 C++ put oluşturulan Android yerel etkinlik uygulama ve kitaplık projeleri Android platformu ile arabirim oluşturmak için "Yapıştır" kodunu içeren bir dinamik kitaplık kodda paylaşılan. Bu uygulama kodu çoğunu kitaplıkta olduğunu ve bildirim, kaynakları ve yapı yönergeleri paketleme projesinde anlamına gelir. Paylaşılan kod NativeActivity projesinde main.cpp çağrılır. Android yerel aktivite programa hakkında daha fazla bilgi için bkz: Android Geliştirici NDK [kavramları](https://developer.android.com/ndk/guides/concepts.html) sayfası.  
  
 Visual Studio, Android Clang platform araç takımı kullanan NDK, kullanarak Android yerel etkinlik projeleri oluşturur. Visual Studio komut satırı anahtarları NativeActivity proje özelliklerinde eşler ve derlemek için kullanılan seçenekler bağlamak ve hedef platformu üzerinde hata ayıklama. Ayrıntılar için açık **özellik sayfaları** MyOpenGLESApp.Android.NativeActivity proje için iletişim kutusu. Komut satırı anahtarları hakkında daha fazla bilgi için bkz: [Clang derleyici kullanıcının el ile](http://clang.llvm.org/docs/UsersManual.html).  
  
##  <a name="BuildIOS"></a>Derleme ve iOS uygulamasını çalıştırma  
 İOS uygulama projesi oluşturulur ve Visual Studio'da düzenlenir ancak lisans kısıtlamaları nedeniyle bu yerleşik ve bir Mac bilgisayar dağıtılması gerekir Visual Studio proje dosyalarını aktarmak ve derleme, dağıtma ve hata ayıklama komutlarını çalıştırmak için Mac çalıştıran uzak bir aracı ile iletişim kurar. Ayarlama ve Mac ve Visual Studio iOS uygulaması oluşturmadan önce iletişim kurmak için yapılandırmanız gerekir. Ayrıntılı yönergeler için bkz: [yükleme ve yapılandırma araçları iOS kullanılarak derleme](../cross-platform/install-and-configure-tools-to-build-using-ios.md). Uzak aracı çalıştıran ve Visual Studio ile Mac eşleştirilmiş sonra yapı ve yükleme ve Kurulum doğrulamak üzere iOS uygulamasını çalıştırın.  
  
#### <a name="to-build-and-run-the-ios-app"></a>Derleme ve iOS uygulamasını çalıştırmak için  
  
1.  Uzak Aracı Mac'inizde çalıştığını ve bu Visual Studio uzak aracıya eşleştirilmiş doğrulayın. Uzak Aracı başlatmak için bir Terminal uygulama penceresi açın ve girin `vcremote`. Daha fazla bilgi için bkz: [Visual Studio'da uzak aracı yapılandırma](../cross-platform/install-and-configure-tools-to-build-using-ios.md#ConfigureVS).  
  
     ![Vcremote çalıştıran Mac Terminal penceresi](../cross-platform/media/cppmdd_common_vcremote.png "CPPMDD_common_vcremote")  
  
2.  Zaten seçili değilse seçin **x86** gelen **çözüm platformları** aşağı açılan liste.  
  
     ![Çözüm platformu için x86 ayarlamak](../cross-platform/media/cppmdd_opengles_solutionplat.png "CPPMDD_OpenGLES_SolutionPlat")  
  
     X86 iOS simülatörü'nü hedeflemek için kullanın. Bir iOS aygıtı hedefliyorsanız, cihaz işlemci (genellikle bir ARM işlemci) tabanlı çözüm platformu seçin. Varsa **çözüm platformları** listesi görüntülenmiyorsa, seçin **çözüm platformları** gelen **Ekle/Kaldır düğmelerini** listesinde ve platformunuzu seçin.  
  
3.  Çözüm Gezgini'nde, MyOpenGLESApp.iOS.Application projesi için kısayol menüsünü açın ve seçin **yapı**.  
  
     ![İOS uygulama projesi derleme](../cross-platform/media/cppmdd_opengles_iosbuild.png "CPPMDD_OpenGLES_iOSBuild")  
  
     Çıktı penceresi iOS statik kitaplık ve iOS uygulaması için yapılandırma işlemi çıktısını görüntüler. Mac üzerinde Uzak Aracı gösterir çalıştıran Terminal penceresi etkinlik komutu ve dosya aktarın.  
  
     Mac bilgisayarda istenebilir konumundaki bir kod imzalama isteği kabul edin. Devam etmek için izin ver'i seçin.  
  
4.  Seçin **iOS simülatörü** uygulamayı Mac üzerindeki iOS Simulator'da çalıştırmak için araç çubuğunda Simulator başlatmak için bir dakika sürebilir. Simulator çıktısını görmek için Mac ön plana getirmek zorunda kalabilirsiniz.  
  
     ![İOS simülatörü'nü çalıştıran uygulama](../cross-platform/media/cppmdd_opengles_iossimulator.png "CPPMDD_OpenGLES_iOSSimulator")  
  
     Uygulamanızı başladıktan sonra kesme noktaları ayarlayın ve Visual Studio hata ayıklayıcısı Yereller inceleyin, çağrı yığını bakın ve değerleri izlemek için kullanın.  
  
     ![Hata ayıklayıcı iOS uygulama içinde kesme noktasındaki](../cross-platform/media/cppmdd_opengles_iosdebug.png "CPPMDD_OpenGLES_iOSDebug")  
  
5.  Shift + hata ayıklamayı durdurmak için F5 tuşuna basın.  
  
     İOS simülatörü Mac üzerinde çalışmaya devam eden ayrı bir işlemdir Düzenleme, derleme ve kodunuzu birden çok kez aynı iOS simülatörü örneğini dağıtın. Bunu dağıtıldıktan sonra kodunuzu doğrudan benzeticisinde çalıştırabilirsiniz.  
  
 Oluşturulan iOS uygulama ve kitaplık projeleri, yalnızca paylaşılan kod uygulayan statik kitaplığa C++ kodu yerleştirin. Uygulama kodu çoğu uygulama projesinde olur. Bu şablon proje paylaşılan kitaplık kodunda çağrılar GameViewController.m dosyasında yapılır. İOS uygulamanızı oluşturmak için Visual Studio, Mac'te çalıştıran uzak bir istemci ile iletişim gerektiren Xcode platform araç takımı kullanır  
  
 Visual Studio proje dosyalarını aktarır ve komutları Xcode kullanarak uygulamanızı oluşturmak için uzak istemciye gönderir. Uzak istemci gönderir yapı durum bilgisi Visual Studio'ya geri dönün. Uygulama başarıyla oluşturdu, çalıştırmak ve uygulama hatalarını ayıklamak üzere komutlarını göndermek için Visual Studio kullanabilirsiniz. Visual Studio hata ayıklayıcısı Mac ya da ekli iOS cihazında iOS simülatörü çalışır çalışan uygulama denetler. Visual Studio komut satırı anahtarları StaticLibrary proje özelliklerinde eşler ve oluşturmak için kullanılan seçenekler bağlamak ve hedef iOS platformunda hata ayıklama. Derleyici komut satırı seçeneği ayrıntılarını açmak **özellik sayfaları** MyOpenGLESApp.iOS.StaticLibrary proje için iletişim kutusu.  
  
##  <a name="Customize"></a>Uygulamalarınızı özelleştirme  
 Eklemek veya ortak işlevselliği değiştirmek için paylaşılan C++ kodu değiştirebilirsiniz. Eşleştirilecek MyOpenGLESApp.Android.NativeActivity ve MyOpenGLESApp.iOS.Application projelerinde paylaşılan kod çağrıları değiştirmeniz gerekir. Önişlemci makroları ortak kodunuzda platforma özgü bölümleri belirtmek için kullanabilirsiniz. Önişlemci makrosu `__ANDROID__` Android için oluşturduğunuzda önceden tanımlanmış. Önişlemci makrosu `__APPLE__` iOS için oluşturduğunuzda önceden tanımlanmış.  
  
 Belirli bir projede platform için IntelliSense görmek için bağlam değiştirici açılır Düzenleyicisi penceresinin üst gezinti çubuğundaki projesini seçin.  
  
 ![Proje bağlam değiştirici açılır düzenleyicisinde](../cross-platform/media/cppmdd_opengles_contextswitcher.png "CPPMDD_OpenGLES_ContextSwitcher")  
  
 IntelliSense sorunlarını geçerli projede kırmızı dalgalı bir çizgi ile işaretlenir. Diğer projelerdeki sorunları mor dalgalı bir çizgi ile işaretlenir. Varsayılan olarak, Visual Studio kod renklendirme veya IntelliSense Java veya Objective-C dosyaları için desteklemez. Ancak, hala kaynak dosyalarını değiştirebilir ve uygulamanızın adı, simge ve diğer uygulama ayrıntılarını ayarlamak için kaynakları değiştirin.