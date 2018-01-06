---
title: "Bir Android yerel etkinlik uygulaması oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 884014b1-5208-45ec-b0da-ad0070d2c24d
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: xplat-cplusplus
ms.openlocfilehash: 910e04d9aafcd549e2192c8d54da87e01abd6d18
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="create-an-android-native-activity-app"></a>Android yerel etkinlik uygulama oluşturma
Platformlar arası mobil geliştirme seçeneği için Visual C++ yüklediğinizde Visual Studio 2015 tam olarak işlevsel Android yerel etkinlik uygulamaları oluşturmak için kullanılabilir. Android yerel Geliştirme Seti (NDK) saf C/C++ kod kullanarak Android uygulamanızı çoğunluğu uygulamak olanak tanıyan bir araç setidir. Bazı Java JNI kodu, C/C++ kodu Android ile etkileşim kurmasına izin vermek için bağlantılı olarak görev yapar. Android NDK yerel etkinlik uygulamaları ile Android API Düzey 9 oluşturabilme sunmuştur. Yerel etkinlik kod Unreal Engine veya OpenGL kullanan oyun ve grafik yoğun uygulamalar oluşturmak için yaygın olarak kullanılır. Bu konuda OpenGL kullanan basit bir yerel etkinlik uygulama oluşturulmasını yol gösterecektir. Ek konular düzenleme, oluşturma, hata ayıklama ve yerel etkinlik kod dağıtma Geliştirici yaşam döngüsü yol.  
  
 [Gereksinimleri](#req)   
 [Yeni bir yerel etkinlik projesi oluşturma](#Create)   
 [Derleme ve varsayılan Android yerel etkinlik uygulamayı çalıştırma](#BuildHello)  
  
##  <a name="req"></a>Gereksinimleri  
 Android yerel etkinlik uygulamayı oluşturmadan önce tüm sistem gereksinimleri karşılanıyor ve Visual Studio 2015'te Visual C++ mobil geliştirme seçeneği yüklü emin olmanız gerekir. Daha fazla bilgi için bkz: [platformlar arası Mobil Geliştirme için Visual C++ yüklemek](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md). SDK'ları ve gerekli üçüncü taraf araçları yüklemeye dahil edilir ve Android için Microsoft Visual Studio öykünücüsü yüklü olduğundan emin olun.  
  
##  <a name="Create"></a>Yeni bir yerel etkinlik projesi oluşturma  
 Bu öğreticide, önce yeni bir Android yerel etkinlik projesi oluşturun ve ardından oluşturup varsayılan uygulama Visual Studio öykünücüsü Android için çalıştırın.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Visual Studio'yu açın. Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **şablonları**, seçin **Visual C++**, **Çapraz Platform**ve ardından  **Yerel etkinlik uygulama (Android)** şablonu.  
  
3.  Uygulama gibi bir ad verin `MyAndroidApp`ve ardından **Tamam**.  
  
     ![Bir yerel etkinlik projesi oluşturma](../cross-platform/media/cppmdd_newproject.PNG "CppMDD_NewProject")  
  
     Visual Studio yeni çözüm oluşturur ve Çözüm Gezgini açar.  
  
     ![Çözüm Gezgini'nde yerel etkinlik projeye](../cross-platform/media/cppmdd_rc_na_solutionexp.PNG "CPPMDD_RC_NA_SolutionExp")  
  
 Yeni bir Android yerel etkinlik uygulama çözüm iki proje içerir:  
  
-   **MyAndroidApp.NativeActivity** başvuruları ve Android yerel bir etkinlik olarak çalıştırmak, uygulamanız için Birleştirici kodunu içerir. Giriş noktaları Birleştirici kodundan uyarlamasını main.cpp içinde olan. Önceden derlenmiş üst bilgiler pch.h içinde ' dir. Bu yerel etkinlik uygulama projesi paketleme projenin toplanma bir paylaşılan kitaplık .so dosyası derlenir.  
  
-   **MyAndroidApp.Packaging** bir Android cihaz veya öykünücü üzerinde dağıtım için .apk dosyası oluşturur. Bu, kaynakları ve bildirim özellikleri ayarladığınız AndroidManifest.xml dosyasında içerir. Ayrıca, Ant oluşturma işlemi denetimleri build.xml dosyası içerir. Böylece dağıtılan ve doğrudan Visual Studio'dan çalıştırma başlangıç projesi olarak varsayılan olarak ayarlanır.  
  
##  <a name="BuildHello"></a>Derleme ve varsayılan Android yerel etkinlik uygulamayı çalıştırma  
 Derleme ve yükleme ve Kurulum doğrulamak için şablon tarafından oluşturulan uygulama çalıştırın. Bu ilk test için Android için Visual Studio öykünücüsü tarafından yüklenen aygıt profillerinden birini uygulamayı çalıştırın. Başka bir hedef uygulamanızı test etmek isterseniz, hedef öykünücüsü yükünü ya da cihaz bilgisayarınıza bağlayın.  
  
#### <a name="to-build-and-run-the-default-native-activity-app"></a>Derleme ve varsayılan yerel etkinlik uygulamayı çalıştırmak için  
  
1.  Zaten seçili değilse seçin **x86** gelen **çözüm platformları** açılır liste.  
  
     ![Çözüm platformları açılır x86 seçimi](../cross-platform/media/cppmdd_rc_na_solution_x86.png "CPPMDD_RC_NA_Solution_x86")  
  
     Varsa **çözüm platformları** listesi değil, seçin **çözüm platformları** gelen **Ekle/Kaldır düğmelerini** listesinde ve platformunuzu seçin.  
  
2.  Menü çubuğunda seçin **yapı**, **yapı çözümü**.  
  
     Çıktı penceresi çözümde iki proje için yapılandırma işlemi çıktısını görüntüler.  
  
3.  VS öykünücüsü birini Android telefonunuzu (x86) profilleri dağıtım hedefi olarak seçin.  
  
     Diğer Öykünücüler yüklediyseniz veya bir Android cihazı bağlı değilse, dağıtım hedef açılır listeden seçebilirsiniz.  
  
4.  Hata ayıklamayı başlatmak için F5'e ya da hata ayıklama olmadan başlatmak için Shift + F5'e basın.  
  
     İşte ne varsayılan uygulama Visual Studio öykünücüsü Android için benzer.  
  
     ![Uygulamanızı çalıştıran öykünücüsü](../cross-platform/media/cppmdd_emulator_running_app.PNG "CppMDD_Emulator_Running_App")  
  
     Visual Studio Yük ve kodunuzu dağıtmak için birkaç saniye sürer öykünücüyü başlatır. Uygulamanızı başladıktan sonra kesme noktalarını ayarlayın ve kod üzerinden adım, Yereller inceleyin ve değerleri izlemek için hata ayıklayıcı kullanın.  
  
5.  Shift + hata ayıklamayı durdurmak için F5 tuşuna basın.  
  
     Öykünücü çalışmaya devam eder ayrı bir işlemdir. Düzenleme, derleme ve kodunuzu birden çok kez aynı öykünücüsü dağıtma.