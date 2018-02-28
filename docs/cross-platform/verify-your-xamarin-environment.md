---
title: "Xamarin ortamınızı doğrulayın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd39882e-06d1-4b39-80d2-4d07b6e4f8f5
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- xamarin
ms.openlocfilehash: 5878da6742412a368e7b5ff84d0e0e20a4751914
ms.sourcegitcommit: 342e5ec5cec4d07864d65379c2add5cec247f3d6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/27/2018
---
# <a name="verify-your-xamarin-environment"></a>Xamarin ortamınızı doğrulayın
Yükleyicileri tamamladıktan sonra (bkz [Kurulum ve yükleme](../cross-platform/setup-and-install.md)), her şeyi Xamarin geliştirme deneyimi için hazır olduğunu doğrulamak için birkaç dakikanızı ayırın.  
  
 Bu Doğrulamalar tamamladıktan sonra ya da aşağıdaki izlenecek her ikisi de yapabilirsiniz:  
  
-   [Visual Studio'da Xamarin.Forms ile uygulama oluşturmaya yönelik temel bilgileri öğrenin](../cross-platform/learn-app-building-basics-with-xamarin-forms-in-visual-studio.md)  
  
-   [Visual Studio’da Xamarin kullanarak yerel kullanıcı arabirimi ile uygulama oluşturma](../cross-platform/build-apps-with-native-ui-using-xamarin-in-visual-studio.md)  
  
## <a name="all-platforms"></a>Tüm platformlar  
 İlk olarak seçin **Araçlar > Seçenekler**, genişletin **Xamarin > diğer**, tıklatıp **şimdi denetle** güncelleştirmeleri için bağlantı. Xamarin 4.0.3.214 kullanıyor veya daha önceki lisans sorunlarını önlemek için gerekir.  
  
 Ardından Visual Studio kullanarak yeni bir Xamarin çözüm oluşturun. **Dosya > Yeni proje**, iletişim kutusunda genişletin **şablonları > Diğer diller > Visual C# > platformlar arası**seçin  **Boş uygulama (yerel taşınabilir)**, Tamam'ı tıklatın. Bu çözüm paylaşılan taşınabilir sınıf kitaplığı proje ve tek tek projeleri ile Android, iOS ve Windows için oluşturur:  
  
 ![Boş uygulama &#40;yeni proje oluşturma sonuçlarını; Yerel taşınabilir &#41; Şablon](../cross-platform/media/crossplat-xamarin-verify-1.png "CrossPlat Xamarin doğrula 1")  
  
> [!NOTE]
>  Şablonları olan değil, görürseniz [eksik Xamarin proje şablonu? Bu deneyin](#missing) bu sayfanın sonundaki.  
  
## <a name="android"></a>Android  
  
1. En son Android SDK Araçları giderek yüklü olup olmadığını kontrol edin **Araçlar > Android > Android SDK Manager** ve Android SDK Araçları'nın en yeni sürümünü yükleme Android SDK platformunuzun Araçlar ve Android SDK derleme araçları bileşenleri. Her zaman en son Android API düzeyi yüklemek için gerekli olmadığını göz önünde bulundurun; ihtiyaç duyduğunuz API'yi hedeflemek istediğiniz platform düzeyi bağlıdır. Genel olarak, Xamarin yüklendiğinde gerektirdiği platform düzeyi yüklenir.  

2.  Android Tasarımcısı'nı doğrulayın: Çözüm Gezgini'nde Android projeyi açın **Kaynakları > Düzen > Main.axml** dosya. (Bu dosyayı doğrudan için Çözüm Gezgini'nde; aramayı deneyin görmüyorsanız, yalnızca Android projesi ve iOS projesinde bulunmaktadır.)  
  
    - "Yüklü Android SDK çok eski" bildiren bir hata alırsanız, tıklatın **açık Android SDK** seçin ve yeni SDK sürüm kullanılabilen araçlar olarak yüklemek için bu iletiyi yukarıdaki 1. adımda. 
  
3.  Derleme ve hata ayıklama öykünücü (veya cihaz) doğrulama:  
  
    -   Çözüm Gezgini'nde Android projesine sağ tıklatın ve **başlangıç projesi olarak ayarla**.  
  
         ![Visual Studio ayarlamak başlangıç projesi seçeneği olarak](../cross-platform/media/crossplat-xamarin-verify-2.png "CrossPlat Xamarin doğrula 2")  
  
    -   Hedef Android sürüme göre uygun bir öykünücü seçin; bilgisayarınıza bağlı bir Android geliştirme cihazınız varsa, burada Öykünücüler listelenen de görürsünüz:  
  
        -   Windows 8 +: seçin bir **VS öykünücüsü** aşağıda gösterildiği gibi Visual Studio'nun hata ayıklama açılır hedeflemek ve hata ayıklayıcısı tuşlarına basarak Başlat **F5**. Daha fazla ayrıntı için bkz: [Android için giriş Visual Studio öykünücüsü](http://blogs.msdn.com/b/visualstudioalm/archive/2014/11/12/introducing-visual-studio-s-emulator-for-android.aspx) (Visual Studio ALM blog). Çalışmak için bkz: öykünücü almada sorunlarla karşılaşmanız halinde [Android için Visual Studio öykünücüsü sorun giderme](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md). Seçerek öykünücüsü yeni cihaz profilleri oluşturabilirsiniz **Araçlar > Android için Visual Studio öykünücüsü...** .  
  
             ![Hata ayıklama hedefi olarak Android için Visual Studio öykünücüsü seçme](../cross-platform/media/crossplat-xamarin-verify-3.png "CrossPlat Xamarin doğrulayın 3")  
  
             Not: görmüyorsanız, **Araçlar > Android için Visual Studio öykünücüsü...**  menü seçeneği öykünücüsü kendisini yüklü değil sahip olabilir. Git **Denetim Masası > Programlar ve Özellikler**seçin **Microsoft Visual Studio**, tıklatıp **değişiklik** yükleyici yeniden çalıştırmak için. Tıklatın **Değiştir** Yükleyicisi'nde için kutuyu **platformlar arası mobil geliştirme > Android için Microsoft Visual Studio öykünücüsü**, tıklatıp **güncelleştirme**.  
  
        -   Windows 7 ve önceki sürümleri: açılan Android için Xamarin Player yerine seçin ve çalıştırmak için F5 tuşuna basın. Xamarin Player hakkında daha fazla bilgi için Aygıt Yöneticisi'ni ve sorun giderme ipuçları, okuma [Xamarin Android Player](http://developer.xamarin.com/guides/android/getting_started/installation/android-player/) (xamarin.com).  
  
> [!NOTE]
>  Visual Studio'da özel olarak Google Android öykünücüsü yapılandırmak için kullanılan Aygıt Yöneticisi'ni açar (Göster aşağıdaki), araç Android Emulator Manager (AVD) düğmesini varlığını fark edebilirsiniz.  Bu üzerinde ya da Visual Studio öykünücüsü Android veya Xamarin profillerini yapılandırmak için her biri kendi Aygıt Yöneticisi'ni sahip Player etkisi yoktur.  Bkz: [Android için giriş Visual Studio öykünücüsü](http://blogs.msdn.com/b/visualstudioalm/archive/2014/11/12/introducing-visual-studio-s-emulator-for-android.aspx) (Visual Studio ALM blog) ve [Xamarin Android Player](http://developer.xamarin.com/guides/android/getting_started/installation/android-player/) (xamarin.com) ayrıntıları için.  
> ![CrossPlat Xamarin doğrulayın 7](../cross-platform/media/crossplat-xamarin-verify-7.png "CrossPlat Xamarin 7 doğrulayın")  
  
## <a name="windows-phone"></a>Windows Phone  
  
1.  Windows Phone Tasarımcısı'nı doğrulayın: Windows Phone Çözüm Gezgini'nde projeye açmak **MainPage.xaml** dosya.  
  
2.  Derleme ve hata ayıklama öykünücü veya bir cihazı doğrulamak (Not: Bu adım ya da internet paylaşımlı cihaz için Visual Studio Kurulumu aracılığıyla yüklenen Windows Phone öykünücüsü olması gerekir):  
  
    -   Çözüm Gezgini'nde Windows Phone projesine sağ tıklatın ve **başlangıç projesi olarak ayarla**.  
  
    -   Seçin bir **öykünücüsü 8.1** hedef ya da aşağıda gösterildiği gibi açılır hata ayıklama ve F5 tuşuna basarak hata ayıklayıcısını başlatma ekli bir cihaz Visual Studio'nun içinde.  
  
         ![Hata ayıklama hedefi olarak bir Windows Phone öykünücüsü seçme](../cross-platform/media/crossplat-xamarin-verify-4.png "CrossPlat Xamarin 4 doğrulayın")  
  
    -   İş, okumak için öykünücü almada sorunlarla karşılaşmanız halinde [Windows Phone 8 öykünücüsü sorun giderme](/previous-versions/windows/apps/jj681694\(v%3dvs.105\)).  
  
## <a name="ios"></a>iOS  
  
1.  Mac açıklandığı gibi Visual Studio ile eşleştirilmiş ve ağ üzerindeki kullanılabilir olduğundan emin olun [Mac bilgisayara bağlayarak](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/xamarin-mac-agent/) (xamarin.com).  
  
2.  Film şeridi Tasarımcısı'nı doğrulayın: iOS Çözüm Gezgini'nde projeye açmak **Main.storyboard** dosya. Visual Studio uzaktan Mac üzerinde çalışan Tasarımcısı burada barındırma  
  
3.  Derleme ve hata ayıklama doğrulama:  
  
    1.  Çözüm Gezgini'nde iOS projesine sağ tıklatın ve **başlangıç projesi olarak ayarla**.  
  
    2.  Seçin **iPhoneSimulator** aşağıda gösterildiği gibi Visual Studio'nun yapı açılan listeden hedef veya **iPhone** internet paylaşımlı cihaz varsa hedefleyin. Hiçbir benzeticileri listelenmiyorsa, Mac, select Xcode başlatma **Xcode -> Tercihler**, tıklatıp **karşıdan**. Altında **bileşenleri** indirilebilir simulator sürümleri görmeniz gerekir. Hata ayıklama için ek yönergeler Xamarin üzerinde 's bulunabilir [hata ayıklama](https://developer.xamarin.com/guides/ios/deployment,_testing,_and_metrics/debugging_in_xamarin_ios/#Debugging_on_the_Simulator) sayfa (xamarin.com).  
  
         ![Hedef derleme iPhoneSimulator seçerek](../cross-platform/media/crossplat-xamarin-verify-5.png "CrossPlat Xamarin 5 doğrulayın")  
  
    3.  Aşağıda gösterildiği gibi bir iPhone hedef Visual Studio'nun hata ayıklama açılır listesinden seçin ve F5 tuşuna basarak hata ayıklayıcı başlatın. Bu, burada hata ayıklama Visual Studio'da gerçekleşirken uygulamayla etkileşim kuracağınızı Mac simulator'da çalıştırır. Fiziksel iPhone veya iPad mac'e bağlı varsa, burada görünür ve bunun yerine seçebilirsiniz. Herhangi bir aygıt veya listelenen benzeticileri görmüyorsanız, yukarıdaki 1. adımda bağlantılı konu gözden geçirme ya da gidip Mac bağlantısını denetleyin **Araçları** >**iOS**  > **Xamarin Mac arası**  
  
         ![Bir iPhone hata ayıklama hedefi seçme](../cross-platform/media/crossplat-xamarin-verify-6.png "CrossPlat Xamarin 6 doğrulayın")  
  
    4.  Mac bilgisayara bağlayarak sorunlarla karşılaşırsanız, okuma [bağlantı sorunlarını giderme](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/xamarin-mac-agent/xma-troubleshooting/) (xamarin.com).  
  
    5.  Bir hata bildiren görürseniz "yüklü hiçbir sağlama profilleri imzalama anahtarlarının yüklü iOS eşleşmiyor, aşağıdakileri yapın:  
  
        -   Apple kimliği hesabınızı, açıklandığı gibi Mac xcode'da eklendiğini denetleyin [hesabınız ekleme Xcode için](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppStoreDistributionTutorial/AddingYourAccounttoXcode/AddingYourAccounttoXcode.html#//apple_ref/doc/uid/TP40013839-CH40-SW1) (apple.com).  Hesabınızı eklendikten sonra Visual Studio ve Xcode yeniden başlattığınızdan emin olun.  
  
             ![CrossPlat Xamarin doğrulayın 8](../cross-platform/media/crossplat-xamarin-verify-8.png "CrossPlat Xamarin 8 doğrulayın")  
  
        -   İOS imzalama sekmesini iOS proje özelliklerinde paket, özel yetkilendirme alan etkin hata ayıklama yapılandırması boş olduğundan emin olun.  Not: Bu ayar, yukarıdaki hata iletisini karşılaştıysanız kaldırma yalnızca denemelisiniz.  
  
##  <a name="missing"></a> Xamarin proje şablonları eksik olabilir mi? Bu deneyin  
 Şablonları Xamarin doğrudan Xamarin Web sitesinden yükleyin ve Visual Studio 2013 varsa ve yan yana Visual Studio 2015 yüklü eksik olabilir. Düzeltme, ancak daha kolaydır: yalnızca etkinleştir **Visual Studio 2015 için Xamarin** Xamarin Kurulum programını özelliği.  
  
1.  Denetim Masası'nda açmak **programlar ve Özellikler**, seçin **Xamarin** öğesi öğesini tıklatıp **değişiklik**.  
  
2.  Görüntülenen Xamarin için Kurulum sihirbazındaki düğmesini **sonraki** ve ardından **değişiklik**.  
  
3.  Yüklemek için isteğe bağlı özellikler listesinde genişletin **Visual Studio 2015 için Xamarin**, seçin **yerel sürücüye yüklenecek**, tıklatıp **sonraki** eklemeye devam etme özelliği.