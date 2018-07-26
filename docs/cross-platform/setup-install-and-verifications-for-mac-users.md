---
title: Kurulum, yükleme ve Doğrulamalar Mac kullanıcıları için | Microsoft Docs
ms.custom: ''
ms.date: 04/13/2017
ms.topic: conceptual
ms.assetid: 22725520-59ba-4f6f-80e4-097b1287a34b
ms.prod: visual-studio-dev15
ms.technology: vs-ide-mobile
author: asb3993
ms.author: amburns
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: f0c4193d68eabd5a5427629cb9a4c7a3be18db3c
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39251926"
---
# <a name="setup-install-and-verifications-for-mac-users"></a>Mac kullanıcıları için kurulum, yükleme ve doğrulamalar

Bu konuda, Mac'te bir Windows sanal makine içinde Visual Studio isteğe bağlı olarak kullanacak, öncelikle bir Mac üzerinde çalışan geliştiriciler için tasarlanmıştır Öncelikle bir Windows bilgisayarda çalışan bir geliştirici olan ve ikincil Mac iOS hedeflemek için ayarlanacak ihtiyacınız varsa, ana bkz [Kurulum ve yükleme](../cross-platform/setup-and-install.md) konu.

Mac'te Xamarin ile çalışmak için şunlar gerekir:

-   MacOS Sierra 10.12 veya üstünde, Xcode ve Xamarin yüklü Mac.

-   Aşağıdaki yapılandırmalardan biri:

    -   **Xamarin Studio doğrudan Mac üzerinde çalıştırmak için:** Xamarin Studio yapı destekleyen Xamarin'in geliştirme ortamı, C# kullanarak Android, iOS ve Windows uygulamaları.  Xamarin Studio hızlı bir genel bakış için bkz [Xamarin Studio genel bakış](https://xamarin.com/studio) (xamarin.com).

    -   **Zaten sahip olduğunuz Parallels ya da VMWare Mac'inizde yapılandırılmış:** Windows Visual Studio 2017 ve Xamarin Parallels veya VMWare içinde çalıştırın.  Bu yapılandırma ile Xamarin, C# kullanarak Android, iOS ve Windows uygulamaları oluşturmak için Visual Studio geliştirme ortamı olarak kullanma olanağı sağlayan Visual Studio ile yüklenen bir uzantısıdır.  Visual Studio Geliştirici temel bileşenleri programı kapsamında ücretsiz 3 aylık Parallels abonelik edinebilirsiniz unutmayın. Bkz: [Microsoft Visual Studio Dev Essentials, Parallels Desktop Pro ve Parallels erişim içerecektir](http://blog.parallels.com/blog/2015/11/18/visual-studio-dev-essentials/) (Parallels blog).

Bu konuda, bu gereksinimleri için yönergeler sağlar.  Yükleme işlemi devam ederken, konuyu gözden geçirebilirsiniz [Xamarin ile mobil geliştirme hakkında bilgi edinin](../cross-platform/learn-about-mobile-development-with-xamarin.md) okuyup gerekli arka plan bilgilerini izleyin.

##  <a name="mac"></a> Mac kurulumu (Apple kimliği, Xcode ve Xamarin)

1.  Ücretsiz bir Apple kimliği Oluştur [My Apple kimliği](https://appleid.apple.com/) zaten yoksa. Bu, yükleme ve Xcode ile imzalama gereklidir.

2.  Xcode'dan yükleyip [ https://developer.apple.com/xcode/ ](https://developer.apple.com/xcode/).

3.  İndirme ve yönergeleri izleyerek Xamarin yükleme [yükleme ve yapılandırma Xamarin.iOS](http://developer.xamarin.com/guides/ios/getting_started/installation/mac/) (xamarin.com).

4.  Xamarin hem Windows hem de Mac bilgisayarlara yükleme işlemini tamamladıktan sonra yönergeleri takip edin [XMA kullanarak Mac Bağlan](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/#Connecting_to_the_Mac_Using_XMA) (xamarin.com) Windows bilgisayarda iOS ve Mac Visual Studio'dan ile çalışabilirsiniz.

##  <a name="windows"></a> Windows Kurulum içinde Parallels (Visual Studio ve Xamarin)

1.  / VMWare, Parallels içinde yapılandırdığınız Windows Masaüstü'nü kullanarak [indirin ve herhangi bir sürümünü Visual Studio 2017 için yükleyiciyi başlatın](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) (Community, Professional veya Enterprise). Visual Studio 2017 Community'yi ücretsiz bir sürümüdür; Professional ve Enterprise sürümleri deneme olarak 30 gün boyunca kullanılabilir.

2.  Installer içinde **ek seçenekler** (üç çubukları simgesi) düğmesine _yanındaki_ **başlatma** ardından **Değiştir**.:

     ![Visual Studio Kurulumu içinde Değiştir seçeneğini seçerek](../cross-platform/media/cross-plat-xamarin-setup-1a.png "çapraz-Plat Xamarin Kurulum 1")

3.  Aşağıdaki kutuları işaretleyin:

    1.  **Mobil ve oyun > .NET ile Mobil Geliştirme**. Bu, yaygın kullanılan araçlar ve yazılım geliştirme setleri altında çeşitli Android araçları da otomatik olarak seçer. Bu seçenek var olan bir Xamarin yüklemesini de güncelleştirmeniz gerekir.

         ![Oyun ve mobil geliştirme altında mobil geliştirme seçeneğini](../cross-platform/media/cross-plat-xamarin-setup-2a.png "çapraz-Plat Xamarin Kurulum 2")

    2. (İsteğe bağlı) **Windows > Evrensel Windows platformu geliştirme**. Bu indirme daha uzun sürer öykünücü görüntüleri yükleme seçenekleri içerir; Ayrıca, daha sonra eklemek için Visual Studio yükleyicisi her zaman geri dönebilirsiniz.

4.  Tıklayın **Değiştir** düğmesine tıklayın ve çalıştırma işlemi sağlar. Yeniden, bu süre içerisinde Mac kurulum yönergeleri ile devam edin ve Git tamamlanması biraz zaman alabilir [Xamarin ile mobil geliştirme hakkında bilgi edinin](../cross-platform/learn-about-mobile-development-with-xamarin.md).

5.  Yükleme tamamlandıktan sonra Visual Studio ve Microsoft hesabınızla oturum istenirse başlatın (Windows ile kullandığınız hesapla aynıdır).

6.  Xamarin hem Windows hem de Mac bilgisayarlara yükleme işlemini tamamladıktan sonra yönergeleri takip edin [XMA kullanarak Mac bilgisayara bağlayarak](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/#Connecting_to_the_Mac_Using_XMA) (xamarin.com) Visual Studio'dan iOS ile çalışabilirsiniz.

##  <a name="verify"></a> Ortamınızı doğrulayın

Yükleyicileri tamamladıktan sonra her şeyi Xamarin geliştirme deneyimi hazır olduğunu doğrulamak için birkaç dakikanızı ayırın.

### <a name="xamarin-studio"></a>Xamarin Studio

Sağlanan bağlantılar gittiğinizde ilk olarak, sahip olduğunuzdan emin olun **Xamarin Studio** Xamarin belgeleri doğru sürümünü görmek için sağ üst köşede seçili:

![Üzerinde Xamarin.com doğru belgeleri görmek için Xamarin Studio seçin](../cross-platform/media/crossplat-xamarin-mac-1.png "CrossPlat Xamarin Mac 1")

**Android**

1.  Yönergeleri izleyerek bir Android projesi oluşturma doğrulama [bir Android projesi oluşturma](http://developer.xamarin.com/recipes/android/general/projects/create_an_android_project/) (xamarin.com).

2.  Hata ayıklama Android öykünücüsünde doğrulama [Android Player > Xamarin Studio belgeleri ile tümleştirme](https://developer.xamarin.com/guides/android/getting_started/installation/android-player/#Integration_with_Xamarin_Studio) (xamarin.com).

**iOS**

1.  Yönergeleri izleyerek bir iOS projesi oluşturma doğrulama [iOS oluşturma](http://developer.xamarin.com/recipes/ios/general/projects/create_an_ios_project/) (xamarin.com).

2.  İOS simülatöründe hata ayıklama doğrulama [simülatör belgelerinde hata ayıklama](https://developer.xamarin.com/guides/ios/deployment,_testing,_and_metrics/debugging_in_xamarin_ios/#Debugging_on_the_Simulator) (xamarin.com).

### <a name="visual-studio"></a>Visual Studio

Sağlanan bağlantılar gittiğinizde ilk olarak, sahip olduğunuzdan emin olun **Visual Studio** Xamarin belgeleri doğru sürümünü görmek için sağ üst köşede seçili:

![Üzerinde Xamarin.com doğru belgeleri görmek için Visual Studio seçerek](../cross-platform/media/crossplat-xamarin-mac-2.png "CrossPlat Xamarin Mac 2")

**Android**

1.  Yönergeleri izleyerek bir Android projesi oluşturma doğrulama [bir Android projesi oluşturma](http://developer.xamarin.com/recipes/android/general/projects/create_an_android_project/) (xamarin.com).

2.  Android designer doğrula: Çözüm Gezgini'nde Android projeyi **Kaynakları > Düzen > Main.axml** dosya.

    -   "Android SDK yüklü olduğu çok eski" belirten bir hata alırsanız, tıklayın **açık Android SDK** , ileti ve en yeni SDK sürümü seçin. Visual Studio SDK'yı güncelleştirmek için yönetici olarak çalıştırıyor olması gerektiğini unutmayın.

3.  Mac'inizde yüklü öykünücüsü'nü Visual Studio'dan bağlanabildiğinizi doğrulayın  Bunun sonucu olarak, Visual Studio'da hata ayıklama için seçebileceğiniz öykünücüleri listesinde Xamarin Player görecek olmasıdır.  Bunu yapmak için yönergeleri takip edin [bağlanma Visual Studio için Xamarin Android Player](http://developer.xamarin.com/guides/android/deployment,_testing,_and_metrics/android-player-with-visual-studio-in-vm/) (xamarin.com).

**iOS**

1.  Ağ üzerinde kullanılabilir ve açıklandığı gibi Visual Studio ile eşleştirilmiş Mac'inizde olduğundan emin olun [mac'e Bağlan](https://developer.xamarin.com/guides/ios/getting_started/installation/windows/#Connecting_to_the_Mac) (xamarin.com).

2.  Yönergeleri izleyerek bir iOS projesi oluşturma doğrulama [iOS oluşturma](http://developer.xamarin.com/recipes/ios/general/projects/create_an_ios_project/) (xamarin.com).

3.  Görsel taslak Tasarımcı doğrula: iOS Çözüm Gezgini'nde projeyi **MainStoryboard.storyboard** dosya. Visual Studio Mac üzerinde çalışan uzaktan Tasarımcı burada barındırma

4.  Derleme ve hata ayıklama doğrulama:

    1.  Çözüm Gezgini'nde iOS projesine sağ tıklayıp **başlangıç projesi olarak ayarla**.

    2.  Seçin **iPhoneSimulator** aşağıda gösterildiği gibi Visual Studio'nun derleme açılan listeden hedefleyin. Mac bilgisayarınızda, select Xcode hiçbir simülatörleri listede yoksa, başlatma **Xcode -> Tercihler**, tıklatıp **indirin**. Altında **bileşenleri** indirilebilir simülatör sürümleri görmeniz gerekir. Hata ayıklama için ek yönergeler için Xamarin'in üzerinde [hata ayıklama](https://developer.xamarin.com/guides/ios/deployment,_testing,_and_metrics/debugging_in_xamarin_ios/#Debugging_on_the_Simulator) sayfa (xamarin.com).

         ![Hedef derleme iPhoneSimulator seçerek](../cross-platform/media/crossplat-xamarin-verify-5.png "CrossPlat Xamarin 5 doğrulayın")

    3.  Aşağıda gösterildiği gibi Visual Studio'nun hata ayıklama açılır listeden bir iPhone hedefini seçin ve F5 tuşuna basarak hata ayıklayıcıyı başlatın. Bu, simülatör burada Visual Studio'da hata ayıklama işlem sırasında uygulamayla etkileşim kuracağınızı Mac üzerinde çalıştırır.

         ![Bir iPhone hata ayıklama hedefi seçme](../cross-platform/media/crossplat-xamarin-verify-6.png "CrossPlat Xamarin 6 doğrulayın")