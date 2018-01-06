---
title: "Xamarin ile mobil geliştirme hakkında bilgi edinin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e970d936-1df4-4c0c-96e3-ef6191295882
caps.latest.revision: "12"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: xamarin
ms.openlocfilehash: 9e2c341d9516959fcc7ef6bc40215023891d618a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="learn-about-mobile-development-with-xamarin"></a>Xamarin ile mobil geliştirme hakkında bilgi edinin
Bu konu, Xamarin ile geliştirme platformlar arası mobil uygulamalar anlamanıza yardımcı olacak genel bakış malzeme yönlendirir. Henüz Visual Studio ve Xamarin yüklü değilse, başlangıç [Kurulum ve yükleme](../cross-platform/setup-and-install.md) işlem ilk olarak, daha sonra dönmek burada yükleyicileri çalıştırırken bu kaynakları ile çalışmak için.  
  
> [!NOTE]
>  Aksi belirtilmediği sürece, başlangıçta yalnızca bu doğrudan buraya bağlı sayfaları ve değil yan sayfaları okuma öneririz. Bu liste tamamladıktan sonra yükleme işlemi hala çalışıyor, geri dönüp ek konular keşfetmek çekinmeyin.  
>   
>  Ayrıca, "Temel" olarak işaretlenmiş konularını gözden geçirmek çekinmeyin ve "Daha derin Dalış" konuları daha sonra geri dönün.  
  
## <a name="essentials-introduction-to-xamarin"></a>Essentials: Xamarin giriş  
 *10-20 dakika*  
  
1.  [Xamarin ile Visual Studio, Mobile Apps](https://www.visualstudio.com/explore/xamarin-vs) (visualstudio.com) Xamarin birincil özelliklerini çok kısa bir özetini sağlar.  
  
2.  [Yapı platformlar arası mobil C# ve Visual Studio kullanarak uygulamaları](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2015-Final-Release-Event/Building-cross-platform-mobile-apps-using-C-and-Visual-Studio-2015) (Channel9, 15m16s) Xamarin destekçisi, Ahmet Montemagno ile. İlk üç dakika kod gösterim tarafından izlenen bir Xamarin genel bakış ' dir.  
  
## <a name="essentials-overview-of-the-visual-studio-and-xamarin-environment"></a>Essentials: Visual Studio ve Xamarin ortam genel bakış  
 *5-15 dakika*  
  
-   Visual Studio ve Xamarin ile Windows bilgisayarı iş çoğunu burada gerçekleştirirsiniz ' dir. Bu bilgisayarda, doğrudan Windows ve Android uygulamaları oluşturmak ve çalıştırmak ve bunları bir aygıt veya bir öykünücü hata ayıklama. Ayrıca uzaktan oluşturmak, çalıştırmak ve Mac yoluyla iOS uygulamaları hata ayıklama Visual Studio Windows bilgisayarındaki iOS film şeridi Tasarımcısı ve iOS simülatörü da bağlanabilirsiniz.  
  
-   Mac Xcode ve Xamarin derleme/imzalama olarak hizmet veren iOS uygulamaları için ana bilgisayar ve çalışma zamanı ortamı. Visual Studio'dan bir iOS Windows bilgisayarındaki için derlemeleri bu Mac için yetki verilen; bir iOS uygulamasını Visual Studio'da hata ayıklama sırasında iOS benzeticisinde doğrudan Mac için bağlı bir internet paylaşımlı cihaz veya Mac üzerinde çalıştığı Bu durumda uygulama ya da Mac yanına etkileşim ve Visual Studio'da hata ayıklama deneyiminizi olması.  
  
 Bu ilişkileri aşağıda gösterilmiştir ve daha fazla bilgiyi üzerinde iOS uygulamaları ile çalışma hakkında [Visual Studio Xamarin.iOS için giriş](http://developer.xamarin.com/guides/ios/getting_started/installation/windows/introduction_to_xamarin_ios_for_visual_studio/) (xamarin.com).  
  
 ![Xamarin ortamınızdaki Windows ve Mac geliştirme bilgisayarlar arasındaki ilişkiyi](../cross-platform/media/crossplat-xamarin-learn-1.png "CrossPlat Xamarin öğrenin 1")  
  
## <a name="essentials-how-projects-are-structured"></a>Essentials: Projeleri nasıl yapılandırıldığı  
 *10-30 dakika*  
  
1.  [Paylaşım kodu seçeneklerini](http://developer.xamarin.com/guides/cross-platform/application_fundamentals/building_cross_platform_applications/sharing_code_options/) (xamarin.com). Taşınabilir sınıf kitaplıkları seçeneği en iyi kullanmadan yalnızca bu .NET tüm hedef platformlar arasında desteklenen API'lerini kullanarak destekleyen öneririz. Çoğu iş mantığı kodu erişim veritabanları, REST API çağrıları ve taşınabilir Xamarin bileşenleri çağrıları dahil olmak üzere, PCL içinde yer alacağını (bkz [daha derin Dalış: Xamarin bileşenleri](#components) , bu konunun sonunda). Xamarin.Forms ile yazılmış ortak UI kod ayrıca bir PCL bulunabilir.  
  
2.  (İsteğe bağlı) [Örnek olay incelemesi: Tasky](http://developer.xamarin.com/guides/cross-platform/application_fundamentals/building_cross_platform_applications/case_study-tasky/) (xamarin.com), tasarım ve tam özellikli bir uygulama verileri, veri erişimi ve işletme katmanları ayıran paylaşılan kodu için bir PCL projeyle yapılandırılması gibi yapısını için bazı en iyi uygulamaları açıklar.  
  
## <a name="essentials-native-and-xamarinforms-ui-layers"></a>Essentials: yerel ve Xamarin.Forms UI katmanları  
 *10-40 dakika*  
  
 Xamarin harika yerel uygulamalar oluşturmak için iki yol sağlar: Xamarin yerel ve Xamarin.Forms.  
  
 Xamarin yerel her hedef platformu için ayrı UI kodu yazın: iOS, Android ve Windows.  Bu yaklaşımda, doğrudan platformu başına özelleştirilmiş bir UI deneyimi sağlayan platforma özgü API erişimi.  Ayrıca yerel Tasarımcısı ve denetimleri her platform için ilgili kullanıcı arabirimini oluşturmaya yardımcı olmak için tam erişimi var.  
  
 Xamarin.Forms genelleştirilmiş bir paylaşılan UI katmanındaki tüm platformlar için taşınabilir Sınıf Kitaplığı'nda yazmanıza olanak sağlayan API kümesi sağlar.  Yerel bir görünüm vermek için her hedef platformu yerel denetimlere Xamarin.Forms işler.  Xamarin.Forms ile bir tasarımcı kullanmak yerine, C# ve XAML kullanarak UI oluşturun.  
  
 Hangi yaklaşımın Önden almaya karar gerekmez; Xamarin yerel ve Xamarin.Forms birleşimini kullanarak uygulamalar uygulanabilir:  
  
-   Oturum açma gibi platformlar genelinde benzer kullanıcı Arabirimi ve özellikleri sağlayan genel amaçlı ekranlar oluşturmak için kullanım Xamarin.Forms forms başvurun ve arama sonuçları.  
  
-   Özelleştirme özellikleri çeşitli içinde Xamarin.Forms UI bir platform başına temelinde ayarlamak için kullanın. Bunlar, hem koddan kullanılabilir OnPlatform API ve özel görünüm oluşturma, varolan bir oluşturucu genişletme ve özel Oluşturucu Oluşturma XAML içerir.  
  
-   Gerekirse, örneğin her platformun benzersiz kullanıcı Arabirimi özelliklerini kullanan ekranlar, yerel kamera yakalama ve görüntü işleme kullanan bir ekran oluşturmak için Xamarin yerel kullanın.  
  
 Platformlar arası paylaşımı ve platforma özgü ayarlamalar yapmak için özelleştirme özelliklerini kullanarak kullanıcı Arabirimi kodu ayarlamak için bir Xamarin.Forms çözümünü her zaman başlayarak öneririz. Tamamen platforma özgü ekranlar ihtiyacınız varsa, bu Xamarin yerel kullanarak tek tek ekleyebilirsiniz.  
  
 Daha fazla bilgi için:  
  
1.  [Xamarin.Forms](http://developer.xamarin.com/guides/cross-platform/xamarin-forms/) kısa bir genel bakış ve avantajları ve dezavantajları Xamarin.Forms (diğer bir deyişle, Xamarin.iOS ve Xamarin.Android) yerel UI katmanları karşılaştırması (xamarin.com) sağlar.  
  
2.  Ahmet Montemagno'nın videonun ilk üç dakika [Xamarin.Forms: yerel iOS, Android ve Windows uygulamalarını C# & XAML ile](https://channel9.msdn.com/events/Visual-Studio/Connect-event-2015/704) (Channel9, 13m3s) başka bir genel bakış sağlar ve tanıtımları için izlemeye devam edebilirsiniz.  
  
3.  (İsteğe bağlı) [Xamarin.Forms giriş](http://developer.xamarin.com/guides/cross-platform/xamarin-forms/getting-started/introduction-to-xamarin-forms/) (xamarin.com)  
  
4.  (İsteğe bağlı) Özelleştirme için OnPlatform kullanma örnekleri görmek [aygıt sınıfı](http://developer.xamarin.com/guides/xamarin-forms/platform-features/device/) belgeleri (xamarin.com)  
  
5.  (İsteğe bağlı) [Platformlar arası - Mobile platformları arasında paylaşım UI kodu Xamarin.Forms ile](https://msdn.microsoft.com/magazine/dn904669.aspx) Jason Smith (MSDN dergisi) anahatları kendisi için ayrıntıları ele alınmıştır üzerinde Xamarin.Forms içinde farklı özelleştirme seçeneklerini tarafından [ Her platformda denetimleri özelleştirme](http://developer.xamarin.com/guides/xamarin-forms/custom-renderer/) (xamarin.com).  
  
## <a name="deeper-dive-debugging-with-emulators"></a>Derin Dalış: Öykünücüler ile hata ayıklama  
 *10-15 dakika*  
  
 Fiziksel bir aygıtı kullanmak zorunda kalmadan, platformlar arası uygulamalar hata ayıklamak için aşağıdaki kullanmanız gerekecektir:  
  
1.  **Android öykünücüsünde.** Kullandığınız Windows sürümüne bağlı olarak, ya da Microsoft Visual Studio öykünücüsü Android veya Xamarin her ikisi de hızlı performans sağlar ve cihaz özellikleri çeşitli destek Player öneririz:  
  
    -   **Windows 8 + makineler:** Microsoft'un kullanarak önerilir [Android için Visual Studio öykünücüsü](https://www.visualstudio.com/en-us/features/msft-android-emulator-vs.aspx), Visual Studio ile yüklenir.  [Android için Visual Studio öykünücüsü](https://channel9.msdn.com/events/Visual-Studio/Connect-event-2015/711) video (Channel9, 5m55s) genel bir bakış ve tanıtım sağlar.  
  
    -   **Windows 7 veya önceki/Mac OS X üzerinde çalışan Windows**: kullanmak [Xamarin Android Player](http://developer.xamarin.com/guides/android/getting_started/installation/android-player) (xamarin.com).  
  
2.  **Apple iOS simülatörü.** Daha fazla bilgi edinmek için okuma [iOS simülatörü'nü ile çalışmaya başlama](https://developer.apple.com/library/prerelease/content/documentation/IDEs/Conceptual/iOS_Simulator_Guide/GettingStartedwithiOSSimulator/GettingStartedwithiOSSimulator.html#//apple_ref/doc/uid/TP40012848-CH5-SW1) (apple.com).  
  
3.  **Microsoft'un Windows Phone öykünücüsü.** Daha fazla bilgi edinmek için okuma [Windows Phone 8 için Windows Phone öykünücüsü](../debugger/run-windows-phone-apps-in-the-emulator.md).  
  
##  <a name="components"></a>Derin Dalış: Xamarin bileşenleri  
 *10 dakika*  
  
 Çok sayıda genişletilmiş özellik Xamarin bileşenleri üzerinden Xamarin uygulamaları için kullanılabilir. İndirmek için kullanılabilir tam katalog bulabilirsiniz [http://components.xamarin.com/](http://components.xamarin.com/), ek kullanıcı Arabirimi denetimlerini, kimlik doğrulaması, çeşitli Microsoft Azure gibi bulut hizmetlerine ve daha fazlasını bileşenleri içerir.