---
title: "Platformlar arası Mobil Geliştirme için Visual C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-mobile
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 0bb872d6-981b-4c96-9143-fcec5336bf0d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: 10ac98027a4f7e50f66ec27636507e89f64849ee
ms.sourcegitcommit: 342e5ec5cec4d07864d65379c2add5cec247f3d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/27/2018
---
# <a name="visual-c-for-cross-platform-mobile-development"></a>Platformlar arası Mobil Geliştirme için Visual C++
Yerel C++ uygulamalar oluşturabilir. iOS, Android ve Windows cihazları ve iOS, Android ve Windows için yerleşik kitaplıklarında ortak kodun paylaşımı kullanarak Visual C++ için platformlar arası mobil geliştirme. SDK'ları ve paylaşılan kitaplıklar ve yerel uygulamalar platformlar arası geliştirme için ihtiyaç duyduğunuz araçlarını yükler Visual Studio 2015'te kullanılabilir bir seçenek budur. Yüklendiğinde, iOS ve Android cihazları ve Windows, Windows Phone ve Xbox yanı sıra platformunda çalışan bir kod oluşturmak için Visual C++ kullanabilirsiniz.  
  
 Birden çok platform için kod yazma can sıkıcı olabilir. İOS, Android ve Windows için Araçlar ve birincil geliştirme dilleri her platformda farklıdır. Ancak, tüm platformlar kod yazma C++'da destekler. Platformlar arası çekirdek kodu kullanılmasını sağlamak için kullanabileceğiniz ortak payda budur. C++'da yazılmış yerel kod iki daha fazla kullanıcı olabilir ve dayanıklı tersine mühendislik. Kodu yeniden kullanma, birden çok platform için uygulamalar oluştururken zaman ve çaba kaydedebilirsiniz.  
  
 Platformlar arası Mobil Geliştirme için Visual C++ kullanarak geliştirme çeşitli avantajları vardır:  
  
1.  **Kolay yükleme.** Visual Studio yükleyicisi edinir ve Android ve iOS için uygulamalar veya kitaplıkları oluşturmak için gereken SDK'ları ve gerekli üçüncü taraf araçları yükler. Yapılandırma ve Kurulum, basit ve çoğunlukla otomatik.  
  
2.  **Güçlü ve bilindik yapı ortamı.** Kolaylıkla paylaşılabilir platformlar arası çözümler ve projeler ile Visual Studio şablonları oluşturun. Bir ortak arabirimi kullanarak tüm projeleri özelliklerini yönetin. Visual Studio düzenleyicisinde tüm kodunuzu düzenleyin ve kod tamamlama ve hata vurgulama için yerleşik platformlar arası IntelliSense yararlanabilir.  
  
3.  **Birleştirilmiş hata ayıklama deneyimini.** Dünya çapındaki hata ayıklama araçlarını Visual Studio'da izleme ve Android cihazları ve Öykünücüler, iOS benzeticileri ve aygıtlar ve Windows veya Windows Phone cihazları ve Öykünücüler dahil olmak üzere tüm platformlarda C++ kodu ile adım için kullanın.  
  
## <a name="get-the-tools"></a>Araçları edinin  
 Platformlar arası Mobil Geliştirme için Visual C++, Visual Studio 2015 ile birlikte gelen yüklenebilir bir seçenektir. Önkoşullar ve yükleme yönergeleri için bkz: [platformlar arası Mobil Geliştirme için Visual C++ yüklemek](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md). İOS için kod oluşturmak için ayrıca bir Mac bilgisayar ve bir Apple iOS Geliştirici hesabı gerekir. Daha fazla bilgi için bkz: [yükleme ve yapılandırma araçları iOS kullanılarak derleme](../cross-platform/install-and-configure-tools-to-build-using-ios.md).  
  
## <a name="come-up-to-speed"></a>Hızlıca gelen  
 Android veya iOS geliştirme geliyor, kullanmaya başlama hakkında bazı harika malzeme sunuyoruz. Visual Studio bir açıklayıcı ve özellikli bir geliştirme ortamıdır. Nasıl kullanılacağını öğrenin deneyin [Android geliştiricileri için Başlarken](/previous-versions/windows/apps/dn275875\(v=win.10\)) veya [iOS geliştiricileri için Başlarken](/previous-versions/windows/apps/jj657966\(v=win.10\)). Bu konular için Visual Studio ve Windows ve Windows Phone için platformlar arası uygulamalar geliştirmek gereken kavramlar tanıtılacaktır. İOS ve Android için ilk platformlar arası uygulamanızı yazmaya başlamak için bkz: [OpenGL ES uygulamanın Android ve iOS oluşturmak](../cross-platform/build-an-opengl-es-application-on-android-and-ios.md).  
  
 Platformlar arası Mobil Geliştirme için Visual C++, uygulamaları başlamanıza yardımcı olmak için çeşitli şablonlar içerir:  
  
-   OpenGLES 2 uygulama (Android, iOS, Windows Evrensel)  
  
     Bir dizi Android yerel etkinlik uygulama, bir iOS uygulaması ve bir paylaşılan C++ kod kitaplığı ile birlikte bir evrensel Windows uygulaması oluşturmak için projeleri içeren bir çözüm oluşturur. Bu uygulamaları aynı dönen küp her uygulamada çizmek için ortak C++ OpenGL ES kod kullanılarak oluşturulan platforma özgü kitaplıkları kullanabilirsiniz. Bu şablonu kullanmak için Visual Studio yüklediğinizde Evrensel Windows uygulama geliştirme araçları seçeneğini eklemeniz gerekir.  
  
-   Yerel etkinlik uygulama (Android)  
  
     Tam bir C++ OpenGL uygulama Android yerel etkinlik projesi olarak oluşturur.  
  
-   OpenGLES uygulama (Android, iOS)  
  
     Bir çözüm projeleri Android yerel etkinlik uygulama ve bir iOS uygulaması oluşturmak için bir dizi oluşturur. Bu uygulamaları aynı dönen küp her uygulamada çizmek için ortak C++ OpenGL ES kod kullanılarak oluşturulan platforma özgü kitaplıkları kullanabilirsiniz.  
  
-   Paylaşılan kitaplık (Android, iOS)  
  
     Paylaşılan bir proje ortak C++ kod kullanarak bir Android dinamik kitaplığı (.so) ve bir iOS statik kitaplık dosyası (bir) oluşturmak için projeleri içeren bir çözüm oluşturur.  
  
-   Temel uygulama (Android, karınca)  
  
     Bir Android oluşturur Java kaynak kodu ve Ant oluşturma sistemi yalnızca kullanan "Hello, World" uygulama projesi.  
  
-   Temel uygulama (Android, Gradle)  
  
     Bir Android oluşturur Java kaynak kodu ve Gradle oluşturma sistemi yalnızca kullanan "Hello, World" uygulama projesi.  
  
-   Temel kitaplığı (Android, karınca)  
  
     Bir Android oluşturur Java kaynak kodu ve Ant oluşturma sistemi yalnızca kullanan "Hello, World" kitaplığı projesi.  
  
-   Temel kitaplığı (Android, Gradle)  
  
     Bir Android oluşturur Java kaynak kodu ve Gradle oluşturma sistemi yalnızca kullanan "Hello, World" kitaplığı projesi.  
  
-   Dinamik paylaşılan kitaplığı (Android)  
  
     C++ kodu kullanarak bir Android dinamik kitaplığı (.so) dosyası oluşturur.  
  
-   OpenGLES 2 uygulama (iOS)  
  
     Bir çözüm projeleri OpenGL ES 2 iOS uygulamanızı oluşturmak için bir dizi oluşturur. Uygulamayı bir iOS uygulaması dönen küp çizmek için C++ OpenGL ES kod kitaplığı kullanır. Bu uygulamayı iOS uygulamanıza C++ kitaplıkları içeri aktarma görmek için iyi bir başlangıç noktası olabilir.  
  
-   Statik kitaplık (Android)  
  
     Android için bir statik kitaplık oluşturmak için bir proje oluşturur. Yalnızca bağlantı bir dinamik kitaplığında bir Android uygulaması olabilir, ancak statik kitaplıklar herhangi bir sayıda bağlayabilirsiniz.  
  
-   Statik kitaplık (iOS)  
  
     İOS için bir statik kitaplık oluşturmak için bir proje oluşturur.  
  
-   Derleme görevleri dosyası projesi (Android)  
  
     Kendi Android derleme görevleri dosyası projeleri için proje sarmalayıcı oluşturur.  
  
## <a name="try-out-sample-code"></a>Örnek kod deneyin  
 Windows, Android ve iOS uygulamaları kullanabileceğiniz paylaşılan kodu kitaplıkları oluşturma ve Android için tam yerel etkinlik uygulamaları oluşturmak nasıl gösteren örnekleri indirin. Başlamak için bkz: [platformlar arası mobil geliştirme örnekleri](../cross-platform/cross-platform-mobile-development-examples.md).  
  
## <a name="in-this-section"></a>Bu bölümde  
  
1.  [Platformlar Arası Mobil Geliştirme için Visual C++’ı yükleme](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md)  
  
2.  [İOS Kullanarak Derlemeye Yönelik Araçları Yükleme ve Yapılandırma](../cross-platform/install-and-configure-tools-to-build-using-ios.md)  
  
3.  [Android Yerel Etkinlik Uygulaması Oluşturma](../cross-platform/create-an-android-native-activity-app.md)  
  
4.  [Android ve iOS Üzerinde OpenGL ES Uygulaması Oluşturma](../cross-platform/build-an-opengl-es-application-on-android-and-ios.md)  
  
5.  [Platformlar Arası Mobil Geliştirme Örnekleri](../cross-platform/cross-platform-mobile-development-examples.md)