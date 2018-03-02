---
title: "Kurulum, yükleme ve Doğrulamalar Mac kullanıcıları için | Microsoft Docs"
ms.custom: 
ms.date: 04/13/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22725520-59ba-4f6f-80e4-097b1287a34b
ms.technology: vs-ide-mobile
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- xamarin
ms.openlocfilehash: 366dd699555cd3eed637687668fc194ba00d5be4
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2018
---
# <a name="setup-install-and-verifications-for-mac-users"></a>Kurulum, yükleme ve Doğrulamalar Mac kullanıcıları için
Bu konu öncelikle Mac üzerinde çalışan ve Visual Studio Mac üzerinde bir Windows sanal makine içinde isteğe bağlı olarak kullanacak geliştiriciler için tasarlanmıştır Öncelikle bir Windows bilgisayarda çalışan bir geliştirici olan ve ikincil Mac iOS hedeflemek için ayarlamanız gerekir, ana bkz [Kurulum ve yükleme](../cross-platform/setup-and-install.md) konu.

 Xamarin Mac üzerinde çalışmak için şunlar gerekir:

-   MacOS Sierra 10,12 veya üstünde, Xcode ve Xamarin yüklü Mac.

-   Aşağıdaki yapılandırmalardan biri:

    -   **Xamarin Studio doğrudan Mac üzerinde çalıştırmak için:** Xamarin Studio olan yapı destekleyen Xamarin'ın geliştirme ortamı C# kullanarak Android, iOS ve Windows uygulamaları.  Xamarin Studio hızlı bir genel bakış almak için bkz [Xamarin Studio genel bakış](https://xamarin.com/studio) (xamarin.com).

    -   **Parallels zaten varsa veya VMWare yapılandırılmış Mac'inizde:** Visual Studio 2017 ve Xamarin Parallels veya VMWare içinde Windows çalıştırın.  Bu yapılandırma ile Xamarin, C# kullanarak Android, iOS ve Windows uygulamaları oluşturmak için Visual Studio geliştirme ortamınızı kullanmanıza olanak sağlayan Visual Studio yüklü olduğu bir uzantısıdır.  Visual Studio Geliştirici Essentials programın bir parçası olarak ücretsiz 3 aylık Parallels abonelik edinebilirsiniz unutmayın. Bkz: [Microsoft Visual Studio geliştirme Essentials olacak dahil Parallels Desktop Pro ve Parallels erişim](http://blog.parallels.com/blog/2015/11/18/visual-studio-dev-essentials/) (Parallels blog).

 Bu konuda bu gereksinimleri için yönergeler sağlar.  Yükleme işlemi devam ederken konuyu gözden geçirebilirsiniz [mobil geliştirme hakkında bilgi edinin Xamarin ile](../cross-platform/learn-about-mobile-development-with-xamarin.md) okuyup gerekli arka plan malzeme izleyin.

##  <a name="mac"></a> Mac kurulumu (Apple kimliği, Xcode ve Xamarin)

1.  Boş bir Apple kimliği oluşturma [My Apple kimliği](https://appleid.apple.com/) zaten yoksa. Bu, yükleme ve Xcode imzalamak için gereklidir.

2.  Xcode gelen yükleyip [https://developer.apple.com/xcode/](https://developer.apple.com/xcode/).

3.  Karşıdan yükleyip Xamarin yönergeleri izleyerek [yükleme ve yapılandırma Xamarin.iOS](http://developer.xamarin.com/guides/ios/getting_started/installation/mac/) (xamarin.com).

4.  Xamarin Windows ve Mac bilgisayarlara yüklenmesini tamamladıktan sonra yönergelerini izleyin [XMA kullanarak Mac bilgisayara bağlayarak](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/#Connecting_to_the_Mac_Using_XMA) (xamarin.com), iOS ve Mac Visual Studio'dan Windows çalışabilmeniz için bilgisayar.

##  <a name="windows"></a> Parallels (Visual Studio ve Xamarin) içinde Windows Kurulumu

1.  Parallels/VMWare içinde yapılandırdığınız Windows Masaüstü'nü kullanarak [indirin ve herhangi bir sürümünü Visual Studio 2017 için yükleyiciyi başlatma](https://www.visualstudio.com/downloads/) (Community, Professional veya Enterprise). Visual Studio 2017 ücretsiz sürüm topluluktur; Professional ve Enterprise sürümleri deneme esaslı 30 gün boyunca kullanılabilir.

2.  Yükleyici içinde tıklatın **ek seçenekler** (üç çubukları simgesi) düğmesini _yanına_ **başlatma** seçin **Değiştir**.:  
  
     ![Visual Studio yüklemesinde Değiştir seçeneğini belirleyerek](../cross-platform/media/cross-plat-xamarin-setup-1a.png "arası Plat Xamarin Kurulum 1")  
  
3.  Aşağıdaki onay kutularını işaretleyin:

    1.  **Mobil ve oyun > .NET ile Mobil Geliştirme**. Bu genel araçlarını ve yazılım geliştirme setleri altında çeşitli Android araçları da otomatik olarak seçer. Bu seçenek ayrıca herhangi bir varolan Xamarin yüklemesi güncelleştirmeniz gerekir.  
  
         ![Oyun ve mobil geliştirme altında mobil geliştirme seçeneğini](../cross-platform/media/cross-plat-xamarin-setup-2a.png "arası Plat Xamarin Kurulum 2")  
  
    2. (İsteğe bağlı) **Windows > Evrensel Windows platformu geliştirme**. Bu yüklemeye daha uzun sürer Öykünücüler görüntülerinin yüklenmesi için seçenekleri içerir; her zaman daha sonra eklemek için Visual Studio yükleyicisi geri dönebilirsiniz.  

4.  Tıklatın **Değiştir** düğmesine tıklayın ve çalıştırma işlemi sağlar. Yeniden, bu süre içerisinde Mac Kurulum yönergeleriyle devam etmek ve Git tamamlanması biraz zaman alır [mobil geliştirme hakkında bilgi edinin Xamarin ile](../cross-platform/learn-about-mobile-development-with-xamarin.md).

5.  Yükleme tamamlandıktan sonra Visual Studio ve Microsoft hesabınızla oturum istenirse başlatın (Windows ile kullandığınız hesapla aynıdır).

6.  Xamarin Windows ve Mac bilgisayarlara yüklenmesini tamamladıktan sonra yönergelerini izleyin [XMA kullanarak Mac bilgisayara bağlayarak](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/#Connecting_to_the_Mac_Using_XMA) (xamarin.com) böylece Visual Studio'dan iOS birlikte çalışabilir.

##  <a name="verify"></a> Ortamınızı doğrulayın
 Yükleyicileri tamamladıktan sonra her şeyi Xamarin geliştirme deneyimi için hazır olduğunu doğrulamak için birkaç dakikanızı ayırın.

### <a name="xamarin-studio"></a>Xamarin Studio
 Sağlanan bağlantılar gittiğinizde ilk olarak, şunları yapın **Xamarin Studio** Xamarin belgelerine doğru sürümü görebilmesi için sağ üst köşede seçili:

 ![Doğru belge üzerinde Xamarin.com görmek için Xamarin Studio seçme](../cross-platform/media/crossplat-xamarin-mac-1.png "CrossPlat Xamarin Mac 1")

**Outlook Web Access (OWA)**

1.  Yönergeleri izleyerek bir Android projesi oluşturma doğrulamak [bir Android projesi oluşturma](http://developer.xamarin.com/recipes/android/general/projects/create_an_android_project/) (xamarin.com).

2.  Android öykünücüsünde hata ayıklamayı doğrulamak [Android Player > Xamarin Studio belgeleri ile tümleştirme](https://developer.xamarin.com/guides/android/getting_started/installation/android-player/#Integration_with_Xamarin_Studio) (xamarin.com).

**iOS**

1.  Yönergeleri izleyerek bir iOS projesi oluşturma doğrulamak [iOS oluşturma](http://developer.xamarin.com/recipes/ios/general/projects/create_an_ios_project/) (xamarin.com).

2.  İOS simülatörü hata ayıklamayı doğrulamak [Simulator belgelerinde hata ayıklama](https://developer.xamarin.com/guides/ios/deployment,_testing,_and_metrics/debugging_in_xamarin_ios/#Debugging_on_the_Simulator) (xamarin.com).

### <a name="visual-studio"></a>Visual Studio
 Sağlanan bağlantılar gittiğinizde ilk olarak, şunları yapın **Visual Studio** Xamarin belgelerine doğru sürümü görebilmesi için sağ üst köşede seçili:

 ![Doğru belge üzerinde Xamarin.com görmek için Visual Studio seçme](../cross-platform/media/crossplat-xamarin-mac-2.png "CrossPlat Xamarin Mac 2")

**Outlook Web Access (OWA)**

1.  Yönergeleri izleyerek bir Android projesi oluşturma doğrulamak [bir Android projesi oluşturma](http://developer.xamarin.com/recipes/android/general/projects/create_an_android_project/) (xamarin.com).

2.  Android Tasarımcısı'nı doğrulayın: Çözüm Gezgini'nde Android projeyi açın **Kaynakları > Düzen > Main.axml** dosya.

    -   "Yüklü Android SDK çok eski" bildiren bir hata alırsanız, tıklatın **açık Android SDK** , iletisini ve en yeni SDK sürümü seçin. Visual Studio SDK güncelleştirmek için bir yönetici olarak çalıştırıyor olması gerektiğini unutmayın.

3.  Mac üzerinde yüklü öykünücüsü Visual Studio'dan bağlanabildiğinizi doğrulayın  Bu Visual Studio'da hata ayıklama için seçebileceğiniz Öykünücüler listesinde Xamarin Player göreceğiniz sonucudur.  Bunu yapmak için yönergeleri izleyin [bağlanma Visual Studio için Xamarin Android Player](http://developer.xamarin.com/guides/android/deployment,_testing,_and_metrics/android-player-with-visual-studio-in-vm/) (xamarin.com).

**iOS**

1.  Mac açıklandığı gibi Visual Studio ile eşleştirilmiş ve ağ üzerindeki kullanılabilir olduğundan emin olun [Mac bilgisayara bağlayarak](https://developer.xamarin.com/guides/ios/getting_started/installation/windows/#Connecting_to_the_Mac) (xamarin.com).

2.  Yönergeleri izleyerek bir iOS projesi oluşturma doğrulamak [iOS oluşturma](http://developer.xamarin.com/recipes/ios/general/projects/create_an_ios_project/) (xamarin.com).

3.  Film şeridi Tasarımcısı'nı doğrulayın: iOS Çözüm Gezgini'nde projeye açmak **MainStoryboard.storyboard** dosya. Visual Studio uzaktan Mac üzerinde çalışan Tasarımcısı burada barındırma

4.  Derleme ve hata ayıklama doğrulama:

    1.  Çözüm Gezgini'nde iOS projesine sağ tıklatın ve **başlangıç projesi olarak ayarla**.

    2.  Seçin **iPhoneSimulator** aşağıda gösterildiği gibi Visual Studio'nun yapı açılan listeden hedefleyin. Hiçbir benzeticileri listelenmiyorsa, Mac, select Xcode başlatma **Xcode -> Tercihler**, tıklatıp **karşıdan**. Altında **bileşenleri** indirilebilir simulator sürümleri görmeniz gerekir. Hata ayıklama için ek yönergeler Xamarin üzerinde 's bulunabilir [hata ayıklama](https://developer.xamarin.com/guides/ios/deployment,_testing,_and_metrics/debugging_in_xamarin_ios/#Debugging_on_the_Simulator) sayfa (xamarin.com).

         ![Hedef derleme iPhoneSimulator seçerek](../cross-platform/media/crossplat-xamarin-verify-5.png "CrossPlat Xamarin 5 doğrulayın")

    3.  Aşağıda gösterildiği gibi bir iPhone hedef Visual Studio'nun hata ayıklama açılır listesinden seçin ve F5 tuşuna basarak hata ayıklayıcı başlatın. Bu, burada hata ayıklama Visual Studio'da gerçekleşirken uygulamayla etkileşim kuracağınızı Mac simulator'da çalıştırır.

         ![Bir iPhone hata ayıklama hedefi seçme](../cross-platform/media/crossplat-xamarin-verify-6.png "CrossPlat Xamarin 6 doğrulayın")