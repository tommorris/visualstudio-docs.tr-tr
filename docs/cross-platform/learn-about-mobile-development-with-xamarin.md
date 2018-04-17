---
title: Xamarin ile mobil geliştirme hakkında bilgi edinin | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: e970d936-1df4-4c0c-96e3-ef6191295882
ms.technology: vs-ide-mobile
author: ghogen
ms.author: ghogen
manager: douge
ms.workload:
- xamarin
ms.openlocfilehash: 9a174c8712f4ca9151fc30ddd357f53cec2891cf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="learn-about-mobile-development-with-xamarin"></a>Xamarin ile mobil geliştirme hakkında bilgi edinin

Bu makalede xamarin'le platformlar arası mobil uygulamalar geliştirme anlamanıza yardımcı olacak birkaç genel bakışlar listelenmektedir. Henüz Visual Studio ve Xamarin yüklü değilse, başlangıç [Kurulum ve yükleme](../cross-platform/setup-and-install.md) işlem ilk olarak, daha sonra dönmek burada yükleyicileri çalıştırırken bu kaynakları ile çalışmak için.  
  
> [!NOTE]
> Başlangıçta aksi belirtilmediği sürece, yalnızca doğrudan buraya ve değil yan sayfaları bağlı sayfaları oku isteyebilirsiniz. Bu liste tamamladıktan sonra yükleme işlemi hala çalışıyor, geri dönüp ek konular keşfetmek çekinmeyin.  
>   
> Ayrıca, "Temel" olarak işaretlenmiş konularını gözden geçirmek çekinmeyin ve "Daha derin Dalış" konuları daha sonra geri dönün.  
  
## <a name="essentials-introduction-to-xamarin"></a>Essentials: Xamarin giriş  

*10-20 dakika*  
  
1.  [Xamarin ile Visual Studio, Mobile Apps](https://www.visualstudio.com/xamarin/) (visualstudio.com) Xamarin birincil özelliklerini kısa bir özetini sağlar.  
  
2.  [Yapı platformlar arası mobil C# ve Visual Studio kullanarak uygulamaları](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2015-Final-Release-Event/Building-cross-platform-mobile-apps-using-C-and-Visual-Studio-2015) (Channel9, 15m16s) Xamarin destekçisi, Ahmet Montemagno ile. İlk üç dakika kod gösterim tarafından izlenen bir Xamarin genel bakış ' dir.  
  
## <a name="essentials-overview-of-the-visual-studio-and-xamarin-environment"></a>Essentials: Visual Studio ve Xamarin ortam genel bakış  

*5-15 dakika*  
  
-   Visual Studio ve Xamarin ile yüklü Windows bilgisayarda iş çoğunu gerçekleştirirsiniz. Bu bilgisayarda, doğrudan Windows ve Android uygulamaları oluşturmak ve çalıştırmak ve Masaüstü, aygıtları veya Öykünücüler debug. Ayrıca uzaktan yapı, çalıştırabilir ve iOS uygulamaları Mac aracılığıyla hata ayıklama Visual Studio Windows bilgisayarındaki iOS film şeridi Tasarımcısı ve iOS simülatörü da bağlanabilirsiniz.  
  
-   Xcode ve yüklü Mac için Visual Studio ile Mac, yapı konak, imzalama ana bilgisayar ve iOS uygulamaları için çalışma zamanı ortamı olarak görev yapar. Bu Mac için Windows bilgisayar temsilciler iOS derlemeler Uygulamayı bir iOS simülatörü Mac veya doğrudan Mac için bağlı bir internet paylaşımlı cihaz üzerinde çalışır Mac uygulamasını etkileşimde ancak Visual Studio'da hata ayıklama deneyimini yürütün.
  
Bu ilişkileri aşağıda gösterilmiştir.  
  
![Xamarin ortamınızdaki Windows ve Mac geliştirme bilgisayarlar arasındaki ilişkiyi](../cross-platform/media/crossplat-xamarin-learn-1.png "CrossPlat Xamarin öğrenin 1")  

> [!NOTE]
> Windows Phone amaçları eksiksiz olması için bu diyagrama gösterilir. Xamarin platform kullanırken, önerilen kod paylaşımını ile Windows Phone veya Windows 10 Mobile cihazları uyumsuz bir .NET standart 2.0 kitaplığı seçenektir. 

Daha fazla bilgiyi üzerinde iOS uygulamaları ile çalışma hakkında [Visual Studio Xamarin.iOS için giriş](/xamarin/ios/get-started/installation/windows/introduction-to-xamarin-ios-for-visual-studio/).
  
## <a name="essentials-how-projects-are-structured"></a>Essentials: Projeleri nasıl yapılandırıldığı  

*10-30 dakika*  
  
1.  [Paylaşım kodu seçeneklerini](/xamarin/cross-platform/app-fundamentals/code-sharing/). Yeni uygulamalar için kod paylaşmak için bir .NET standart Kitaplığı kullanmanız gerekir. Çoğu iş mantığı kodu erişim veritabanları, REST API çağrıları ve taşınabilir Xamarin bileşenleri çağrıları dahil olmak üzere .NET standart Kitaplığı ' nda yer alacaktır. (Bkz [daha derin Dalış: Xamarin bileşenleri](#components) bu makalenin sonunda). Xamarin.Forms ile yazılmış ortak UI kod ayrıca .NET standart bir kitaplıkta yer alıyor.  
  
2.  (İsteğe bağlı) [Örnek olay incelemesi: Tasky](/xamarin/cross-platform/app-fundamentals/building-cross-platform-applications/case-study-tasky/) tasarım ve yapı proje verileri, veri erişimi ve işletme katmanları ayıran paylaşılan kodu ile yapılandırılması gibi bir tam özellikli uygulamanın, bazı en iyi yöntemleri açıklar.  
  
## <a name="essentials-native-and-xamarinforms-ui-layers"></a>Essentials: yerel ve Xamarin.Forms UI katmanları  

*10-40 dakika*  
  
Xamarin harika uygulamalar oluşturmak için iki yol sağlar: Xamarin yerel ve Xamarin.Forms.  
  
Xamarin yerel, her hedef platformu için ayrı UI kod yazma: iOS, Android ve Windows.  Bu yaklaşımda, doğrudan bir özelleştirilmiş UI deneyimi platformu başına tasarlamak için platforma özgü API'lerine erişebilirsiniz.  Ayrıca yerel Tasarımcısı ve denetimleri her platform için ilgili kullanıcı arabirimini oluşturmaya yardımcı olmak için tam erişimi var.  
  
Xamarin.Forms genelleştirilmiş bir paylaşılan UI katmanındaki tüm platformlar için bir .NET standart kitaplığında yazmanıza olanak sağlayan API kümesi sağlar.  Yerel bir görünüm sağlamak için her hedef platformu yerel denetimlere Xamarin.Forms işler.  Bir tasarımcı kullanmak yerine, C# ve XAML kullanarak UI oluşturun.  

Çoğu geliştirici Xamarin.Forms kullanın. Bu, geliştiriciler için Xamarin yeni için önerilen yoldur. Xamarin yerel yaklaşım daha zordur ve Hedef platformlar bilgisi ayrıntılı gerektirir.
  
Hangi yaklaşımın Önden almaya karar gerekmez; Xamarin yerel ve Xamarin.Forms birleşimini kullanarak uygulamalar uygulanabilir:  
  
-   Xamarin.Forms genel amaçlı ekranlar oluşturmak için kullanın. Bunlar benzer kullanıcı arabirimleri sağlar ve yetenekleri oturumları gibi platform genelinde formlar başvurun ve arama sonuçları.  
  
-   Özelleştirme özellikleri çeşitli içinde Xamarin.Forms UI platform başına temelinde ayarlamak için kullanın. En basit özelleştirme seçeneği içerir `OnPlatform` API. Ayrıca özel görünümlerini oluşturma, varolan Oluşturucu genişletmek ve özel Oluşturucu oluşturma.  
  
-   Gerekirse, her platform için benzersiz kullanıcı Arabirimi özelliklerini kullanmak ekranlar oluşturmak için Xamarin yerel kullanın. Yerel kamera yakalama ve görüntü işleme kullanan bir ekran bir örnektir.  
  
Platformlar arası paylaşımı UI kod ayarlamak için bir Xamarin.Forms çözümünü genellikle başlamanız gerekir. Özelleştirme özellikleri platforma özgü ayarlamalar yapmak için kullanın. Tamamen platforma özgü ekranlar ihtiyacınız varsa, bu Xamarin yerel kullanarak tek tek ekleyebilirsiniz.  
  
Daha fazla bilgi için:  
  
1.  [Xamarin.Forms](/xamarin/xamarin-forms/) kısa bir genel bakış ve avantajları ve dezavantajları Xamarin.Forms (diğer bir deyişle, Xamarin.iOS ve Xamarin.Android) yerel UI katmanları karşılaştırması sağlar.  
  
2.  Ahmet Montemagno'nın videonun ilk üç dakika [Xamarin.Forms: yerel iOS, Android ve Windows uygulamalarını C# & XAML ile](https://channel9.msdn.com/events/Visual-Studio/Connect-event-2015/704) (Channel9, 13m3s) başka bir genel bakış sağlar ve tanıtımları için izlemeye devam edebilirsiniz.  
  
3.  (İsteğe bağlı) [Xamarin.Forms giriş](/xamarin/xamarin-forms/get-started/introduction-to-xamarin-forms/)  
  
4.  (İsteğe bağlı) Kullanım örnekleri görmek `OnPlatform` özelleştirmesinde için [aygıt sınıfı](/xamarin/xamarin-forms/platform/device/) belgeleri
  
5.  (İsteğe bağlı) [Platformlar arası - Mobile platformları arasında paylaşım UI kodu Xamarin.Forms ile](https://msdn.microsoft.com/magazine/dn904669.aspx) Jason Smith (MSDN dergisi) anahatları kendisi için ayrıntıları ele alınmıştır üzerinde Xamarin.Forms içinde farklı özelleştirme seçeneklerini tarafından [ Özel oluşturucu](/xamarin/xamarin-forms/app-fundamentals/custom-renderer/).  
  
## <a name="deeper-dive-debugging-with-emulators"></a>Derin Dalış: Öykünücüler ile hata ayıklama  

*10-15 dakika*  
  
Fiziksel bir aygıtı kullanmak zorunda kalmadan, platformlar arası uygulamalar hata ayıklamak için ele alınan Öykünücüler buraya kullanmanız gerekir:  
  
### <a name="microsofts-android-emulator"></a>Microsoft'un Android öykünücüsü 

Microsoft'un kullanmanız önerilir [Android için Visual Studio öykünücüsü](~/cross-platform/visual-studio-emulator-for-android.md), Visual Studio ile yüklenir.  [Android için Visual Studio öykünücüsü](https://channel9.msdn.com/events/Visual-Studio/Connect-event-2015/711) video (Channel9, 5m55s) genel bir bakış ve tanıtım sağlar.  
  
### <a name="apples-ios-simulator"></a>Apple iOS simülatörü

Daha fazla bilgi edinmek için okuma [iOS simülatörü'nü ile çalışmaya başlama](https://developer.apple.com/library/prerelease/content/documentation/IDEs/Conceptual/iOS_Simulator_Guide/GettingStartedwithiOSSimulator/GettingStartedwithiOSSimulator.html#//apple_ref/doc/uid/TP40012848-CH5-SW1) (apple.com).  
  
### <a name="microsofts-windows-phone-emulator"></a>Microsoft'un Windows Phone öykünücüsü.

Daha fazla bilgi edinmek için okuma [Windows 10 Mobile için Microsoft Emulator ile Test](/windows-uwp/windows-apps-src/debug-test-perf/test-with-the-emulator/).  
  
<a name="components" /> 

## <a name="deeper-dive-xamarin-components"></a>Derin Dalış: Xamarin bileşenleri  

*10 dakika*  
  
Çok sayıda genişletilmiş özellik Xamarin bileşenleri üzerinden Xamarin uygulamaları için kullanılabilir. İndirmek için kullanılabilir tam katalog bulabilirsiniz [ http://components.xamarin.com/ ](http://components.xamarin.com/), ek kullanıcı Arabirimi denetimlerini, kimlik doğrulaması, çeşitli Microsoft Azure gibi bulut hizmetlerine ve daha fazlasını bileşenleri içerir.