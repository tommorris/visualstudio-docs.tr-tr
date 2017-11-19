---
title: "Kurulum ve yükleme | Microsoft Docs"
ms.custom: 
ms.date: 04/13/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2cfcad00-352c-4161-814c-f5ae32d8ada8
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: dba101890bd2f27c85e8e6053944d8781fa03ed4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="setup-and-install"></a>Kurulum ve yükleme
Yerel iOS, Android ve Windows oluşturmak için uygulamalardan ortak C# / .NET kod tabanını kullanarak Xamarin, aşağıdakiler gerekir:  
  
-   Windows ve Android uygulamaları ile çalışmak için: bir Windows geliştirme bilgisayarla Visual Studio 2017 veya yüklü xamarin'le 2015. Yönergeleri izleyerek Visual Studio 2013 de kullanabilirsiniz [doğrudan Xamarin yükleme](https://developer.xamarin.com/guides/cross-platform/getting_started/requirements/#install) (xamarin.com). 
  
-   İOS uygulamaları ile çalışmak için: bir Mac macOS Sierra 10,12 veya üstünde, Xcode ve Xamarin yüklü.  
  
 Windows ve Mac bilgisayarları aynı anda ayarlayabilir ve bu yükleyiciler çalışırken, geçebilir [xamarin'le mobil geliştirme hakkında bilgi edinin](../cross-platform/learn-about-mobile-development-with-xamarin.md) okuyup gerekli arka plan malzeme izleyin.  
 
Bu kurulum ve yükleme yaptıktan sonra Xamarin kullanarak sorunları varsa, sorunuzu ileti [forums.xamarin.com](http://forums.xamarin.com/).
  
> [!NOTE]
>  31 Mart 2016 tüm Xamarin dahil ile gibi hiçbir ek Visual Studio'ya'nin tüm sürümlerinde maliyet ve ayrı bir lisansı gerektirmez. Mac için Xamarin Studio Community, ayrıca Öğrenciler, OSS geliştiriciler ve küçük ekipleri için ücretsizdir. Önceki Xamarin lisansları ile yapılandırılmış olan mevcut yüklemelerinde Visual Studio, Xamarin sürüm 4.0.3.214 güncelleştirmesi gerektiğini not ya da daha yüksek. Bunu yapmak için şu adrese gidin **Araçlar > Seçenekler > Xamarin > diğer**, tıklatın **şimdi denetle** bağlantı ve indirme 4.0.3.214 güncelleştirme. Visual Studio'yu yeniden başlatın, Git **Araçlar > Xamarin hesap...**  ve güncelleştirilmiş durum görmeniz gerekir.  
  
##  <a name="prereq"></a>Ön koşullar  
  
###  <a name="for-targeting-windows-and-android"></a>Windows ve Android hedefleme 
  
1.  Önerilen: Windows 8 veya daha sonra en iyi Android öykünücüsü performansı çalıştıran fiziksel Windows bilgisayar (VM değil). (Biz fiziksel bilgisayar ve bir VM gerektiğini belirten?)  
  
2.  Bu durumda, Xamarin Player için Android öykünücüsü olarak kullanacağınız, Windows 7 veya önceki bir bilgisayarı kullanabilirsiniz. 
    
3. Her iki yapılandırma için doğrudan bağlı fiziksel cihazlarda uygulamalar her zaman çalıştırabilirsiniz.  
  
### <a name="for-targeting-ios"></a>İOS hedefleme  
  
1.  Bir ağ Mac ya da Mac ile macOS Sierra çalışan macOS 10,12 mini veya üzeri (Xcode 8.3 için gerekli).  
  
2.  Visual Studio birincil geliştirme ortamınızı Windows (7 +) bir bilgisayarda kullanırken, ağa bağlı bir Mac yalnızca derleyin ve iOS uygulamaları hata ayıklama, iOS simülatörü ya da internet paylaşımlı cihaz ekleme ve Visual Studio için film şeridi Tasarımcısı'nı kullanmak için gereklidir kullanıcı arabirimini tasarlama. Eski Mac modelleri tamamen ikincil bu rol için yeterlidir.  
  
##  <a name="windows"></a>Windows Kurulumu (Visual Studio ve Xamarin)  
  
> [!TIP]
>  Bu yönergeler, Visual Studio 2017 için geçerlidir. Visual Studio 2015 için bkz: [MSDN](https://msdn.microsoft.com/en-us/library/mt613162.aspx). Xamarin ile Visual Studio 2013 kullanmak için (güncelleştirme 2 gereklidir) yönergelerini izleyin [doğrudan Xamarin yükleme](https://developer.xamarin.com/guides/cross-platform/getting_started/requirements/#install) (xamarin.com).  
  
1.  [Karşıdan yükleme ve herhangi bir sürümünü Visual Studio 2017 için yükleyiciyi başlatma](https://www.visualstudio.com/downloads/) (Community, Professional veya Enterprise). Visual Studio 2017 ücretsiz sürüm topluluktur; Professional ve Enterprise sürümleri deneme esaslı bir lisans satın alma sonra gerekir 30 gün boyunca kullanılabilir.  
  
    1.  Visual Studio yüklü 2017 zaten varsa, çalıştırmanız **Visual Studio yükleyicisi** gelen **Başlat** menüsü.
  
2.  Yükleyici içinde tıklatın **ek seçenekler** (üç çubukları simgesi) düğmesini _yanına_ **başlatma** seçin **Değiştir**.:  
  
     ![Visual Studio yüklemesinde Değiştir seçeneğini belirleyerek](../cross-platform/media/cross-plat-xamarin-setup-1a.png "arası Plat Xamarin Kurulum 1")  
  
3.  Aşağıdaki onay kutularını işaretleyin:  
  
    1.  **Mobil ve oyun > .NET ile Mobil Geliştirme**. Bu genel araçlarını ve yazılım geliştirme setleri altında çeşitli Android araçları da otomatik olarak seçer. Bu seçenek ayrıca herhangi bir varolan Xamarin yüklemesi güncelleştirmeniz gerekir.  
  
         ![Oyun ve mobil geliştirme altında mobil geliştirme seçeneğini](../cross-platform/media/cross-plat-xamarin-setup-2a.png "arası Plat Xamarin Kurulum 2")  
  
    2. (İsteğe bağlı) **Windows > Evrensel Windows platformu geliştirme**. Karşıdan yüklemek için daha uzun sürer Öykünücüler görüntülerinin yüklenmesi için bu INCLUDE seçenekleri; her zaman daha sonra eklemek için Visual Studio yükleyicisi geri dönebilirsiniz. 
  
4.  Tıklatın **Değiştir** düğmesine tıklayın ve çalıştırma işlemi sağlar. Yeniden, bu süre içerisinde Mac Kurulum yönergeleriyle devam etmek ve Git tamamlanması biraz zaman alır [mobil geliştirme hakkında bilgi edinin Xamarin ile](../cross-platform/learn-about-mobile-development-with-xamarin.md).  
  
5.  Yükleme tamamlandıktan sonra Visual Studio ve Microsoft hesabınızla oturum istenirse başlatın (Windows ile kullandığınız hesapla aynıdır).  
      
6.  Android uygulamaları test etmek için [Android SDK öykünücüsü](https://developer.xamarin.com/guides/android/deployment,_testing,_and_metrics/debug-on-emulator/android-sdk-emulator/) fiziksel aygıtların yoksa. Aşağıdaki nota bakın.  
  
 **Windows bilgisayarlarda Öykünücüler hakkında Not:** CPU aynı anda yalnızca bir sanallaştırma teknolojisini desteklemek için yalnızca kullanımda geliştirme bilgisayarınızda bir en iyisidir. Hyper-V (Android ve Windows Phone öykünücüsü için Visual Studio öykünücüsü tarafından kullanılan), sanal (Genymotion tarafından kullanılır) kutusunu ve Intel (Android SDK öykünücüsü tarafından kullanılan) HAXM teknolojilerdir üç ana virtualizations vardır. Hyper-V ve sanal kutusu arasında çeşitli sorunları nedeniyle herhangi belirli bir bilgisayarda, bu nedenle yalnızca bir Öykünücüler kullanmak için en iyi, Hyper-V Windows 8 ve üzeri bilgisayarlar ve Windows 7 üzerinde Intel HAXM Öykünücüler kullanmak için yukarıdaki ve ne zaman yanı sıra önceki öneriler yazın. Windows, Mac'te çalışan  
  
##  <a name="mac"></a>Mac kurulumu (Apple kimliği, Xcode ve Xamarin)  
  
1.  Boş bir Apple kimliği oluşturma [https://appleid.apple.com](https://appleid.apple.com/) zaten yoksa. Bu, yükleme ve Xcode imzalamak için gereklidir.  
  
2.  Xcode gelen yükleyip [https://developer.apple.com/xcode/](https://developer.apple.com/xcode/), Apple Kimliğinizi açıklandığı gibi ekleyin [hesabınız ekleme XCode için](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppStoreDistributionTutorial/AddingYourAccounttoXcode/AddingYourAccounttoXcode.html#//apple_ref/doc/uid/TP40013839-CH40-SW1) (apple.com).  
  
3.  Karşıdan yükleyip Xamarin yönergeleri izleyerek [yükleme ve yapılandırma Xamarin.iOS](http://developer.xamarin.com/guides/ios/getting_started/installation/mac/) (xamarin.com).  
  
4.  Xamarin Windows ve Mac bilgisayarlara yüklenmesini tamamladıktan sonra yönergeleri izleyerek [Mac bilgisayara bağlayarak](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/xamarin-mac-agent/) (xamarin.com) böylece Windows bilgisayarda iOS ve Mac Visual Studio'dan ile çalışabilirsiniz.  
  
     Her iki bilgisayar aynı yerel ağ üzerinde olması gerektiğini unutmayın.