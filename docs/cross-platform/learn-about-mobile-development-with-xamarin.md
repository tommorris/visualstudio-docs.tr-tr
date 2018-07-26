---
title: Xamarin ile mobil geliştirme hakkında bilgi edinin | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: e970d936-1df4-4c0c-96e3-ef6191295882
ms.prod: xamarin
ms.technology: xamarin-tools
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 98371b648dc7fe18315904d4759b55701a07f7b1
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39251685"
---
# <a name="learn-about-mobile-development-with-xamarin"></a>Xamarin ile mobil geliştirme hakkında bilgi edinin

Bu makalede, Xamarin ile platformlar arası mobil uygulamalar geliştirmeyi anlamanıza yardımcı olabilecek birkaç genel bakışlar listelenmektedir. Henüz Visual Studio ve Xamarin yüklü değilse, başlangıç [Kurulum ve yükleme](../cross-platform/setup-and-install.md) işlemi ilk olarak, daha sonra dönmek burada yükleyicileri çalışırken bu kaynak ile çalışmak için.

> [!NOTE]
> Başlangıçta aksi belirtilmediği sürece, yalnızca doğrudan buradan ve değil paketinizle sayfaları bağlanan sayfalar okumak isteyebilirsiniz. Bu liste tamamladıktan sonra yükleme işlemi hala çalışıyor, geri dönün ve diğer konu başlıklarını keşfedin çekinmeyin.
>
> Ayrıca, "Temel" olarak işaretlenmiş başlıklara çekinmeyin ve "Daha yakından bakın" konulara daha sonra tekrar deneyin.

## <a name="essentials-introduction-to-xamarin"></a>Temel bileşenleri: Xamarin giriş

*10-20 dakika*

1.  [Visual Studio'da Xamarin ile mobil uygulamalar](https://visualstudio.microsoft.com/xamarin/) (visualstudio.com) birincil Xamarin özelliklerini kısa bir özetini sağlar.

2.  [C# ve Visual Studio kullanarak platformlar arası mobil uygulamalar oluşturmayı](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2015-Final-Release-Event/Building-cross-platform-mobile-apps-using-C-and-Visual-Studio-2015) (Channel9 15m16s) ile Xamarin destekçisi, James Montemagno. İlk üç dakika kod tanıtımlar tarafından izlenen bir Xamarin genel bakış ' dir.

## <a name="essentials-overview-of-the-visual-studio-and-xamarin-environment"></a>Hakkında temel bilgiler: Visual Studio ve Xamarin ortamı genel bakış

*5-15 dakika*

-   Visual Studio ve Xamarin ile yüklenmiş Windows bilgisayarda, işin çoğunu yaparsınız. Bu bilgisayarda, doğrudan Windows ve Android uygulamaları geliştirin ve çalıştırın ve Masaüstü, cihazlar veya öykünücü üzerinde hata ayıklayın. Uzaktan derleme, çalıştırabilir ve Mac aracılığıyla iOS uygulamalarının hatalarını ayıklama Visual Studio Windows bilgisayarda ayrıca iOS görsel taslak Tasarımcısı ve iOS simülatörü bağlanabilirsiniz.

-   Xcode ve yüklü Mac için Visual Studio ile bir Mac derleme konağı, imzalama konak ve iOS uygulamaları için çalışma zamanı ortamı işlevi görür. Bu Mac için Windows bilgisayar temsilciler iOS yapıları Uygulamayı bir iOS simülatörü Mac veya doğrudan bağlı Mac için bir internet paylaşımlı cihaz üzerinde çalışır Mac uygulaması ile etkileşim kurabilir ancak Visual Studio'da hata ayıklama deneyimini gerçekleştirin.

Bu ilişkileri aşağıda gösterilmiştir.

![Xamarin ortamınızdaki Windows ve Mac'te geliştirme bilgisayarlar arasındaki ilişki](../cross-platform/media/crossplat-xamarin-learn-1.png "CrossPlat Xamarin 1 öğrenin")

> [!NOTE]
> Windows Phone bütünlük amacıyla bu diyagramda gösterilmektedir. Xamarin platformunu kullanırken, kod paylaşımı ile Windows Phone veya Windows 10 Mobile cihazları uyumsuz bir .NET Standard 2.0 kitaplığı önerilir.

Daha fazla bilgi edinebilirsiniz üzerinde iOS uygulamalarıyla çalışma hakkında [Visual Studio için Xamarin.ios'a giriş](/xamarin/ios/get-started/installation/windows/introduction-to-xamarin-ios-for-visual-studio/).

## <a name="essentials-how-projects-are-structured"></a>Temel bileşenleri: Projeleri nasıl yapılanmıştır.

*10-30 dakika*

1.  [Paylaşım kod seçenekleri](/xamarin/cross-platform/app-fundamentals/code-sharing/). Yeni uygulamalar için kodu paylaşmak için bir .NET Standard Kitaplığı kullanmanız gerekir. Çoğu iş mantığı kod, veritabanları, REST API çağrıları ve taşınabilir Xamarin bileşenleri çağrıları dahil olmak üzere .NET Standard Kitaplığı'nda yer alacaktır. (Bkz [daha yakından bakın: Xamarin bileşenleri](#components) bu makalenin sonunda). Xamarin.Forms ile yazılmış ortak UI kodunu da bir .NET Standard kitaplığı içinde yer alıyor.

2.  (İsteğe bağlı) [Örnek olay incelemesi: Tasky](/xamarin/cross-platform/app-fundamentals/building-cross-platform-applications/case-study-tasky/) tasarım ve yapı verileri, veri erişimi ve iş katmanları ayıran paylaşılan kod ile proje yapılandırma gibi bir tam özellikli uygulamanız için bazı en iyi uygulamaları açıklar.

## <a name="essentials-native-and-xamarinforms-ui-layers"></a>Temel bileşenleri: yerel ve Xamarin.Forms UI katmanları

*10-40 dakika*

Xamarin harika uygulamalar oluşturmak için iki yol sağlar: Xamarin yerel ve Xamarin.Forms.

Xamarin yerel ile her hedef platformu için ayrı bir kullanıcı Arabirimi kod yazma: iOS, Android ve Windows.  Bu yaklaşımda, doğrudan erişim için özelleştirilmiş bir kullanıcı Arabirimi deneyimi platform başına tasarlamak için platforma özgü API vardır.  De yerel Tasarımcısı ve her platform için denetimleri ile ilgili kullanıcı arabirimini oluşturmaya yardımcı olmak için tam erişim var.

Xamarin.Forms, genelleştirilmiş bir paylaşılan kullanıcı Arabirimi katmanındaki tüm platformlar için .NET standart kitaplığa yazmanızı sağlayan API kümesi sağlar.  Yerel bir görünüm sağlamak için her hedef platformda yerel denetimlere Xamarin.Forms işler.  Bir tasarımcı kullanmak yerine, C# ve XAML kullanarak kullanıcı Arabirimi oluşturun.

Çoğu geliştirici için Xamarin.Forms kullanın. Xamarin için yeni geliştiriciler için önerilen yoldur. Xamarin yerel yaklaşım daha zordur ve daha ayrıntılı bilgi hedef platform gerektirir.

Önden almak için hangi yaklaşımın karar gerekmez; uygulamalar hem Xamarin.Forms, hem de Xamarin yerel bir birleşimini kullanarak uygulanabilir:

-   Genel amaçlı ekranlar oluşturmak için Xamarin.Forms kullanın. Bunlar benzer kullanıcı arabirimi sağlar ve oturum açma bilgileri gibi platformlarda özellikleri forms başvurun ve arama sonuçları.

-   Çeşitli özelleştirme özelliklerini Xamarin.Forms UI platform başına temelinde ayarlamak için kullanın. En basit özelleştirme seçeneği içerir `OnPlatform` API. Özel görünümlerini oluşturma, var olan oluşturucu genişletmek ve özel Oluşturucu oluşturma.

-   Gerekirse her platform için benzersiz bir kullanıcı Arabirimi özelliklerini kullanan ekranlar oluşturmak için Xamarin yerel kullanın. Yerel kamera yakalama ve görüntü işleme kullanan bir ekran bir örnektir.

Genellikle kullanıcı Arabirimi kod paylaşımı platformlar arasında ayarlamak için Xamarin.Forms çözümü ile başlamanız gerekir. Ardından platforma özgü düzenlemeler için özelleştirme özelliklerini kullanın. Tamamen platforma özgü ekranlar ihtiyacınız varsa, bunları ayrı ayrı Xamarin yerel kullanarak ekleyebilirsiniz.

Daha fazla bilgi için:

1.  [Xamarin.Forms](/xamarin/xamarin-forms/) kısa bir genel bakış ve avantajları ve dezavantajları Xamarin.Forms ve yerel UI katmanları (diğer bir deyişle, Xamarin.iOS ve Xamarin.Android) sağlar.

2.  İlk üç dakika James Montemagno'nın video [Xamarin.Forms: yerel iOS, Android ve Windows uygulamaları C# ve XAML ile](https://channel9.msdn.com/events/Visual-Studio/Connect-event-2015/704) (Channel9 13m3s) başka bir genel bakış sağlar ve Tanıtımlar izlemeye devam edebilirsiniz.

3.  (İsteğe bağlı) [Xamarin.Forms'a giriş](/xamarin/xamarin-forms/get-started/introduction-to-xamarin-forms/)

4.  (İsteğe bağlı) Kullanım örnekleri görmek `OnPlatform` özelleştirmesinde için [cihaz sınıfı](/xamarin/xamarin-forms/platform/device/) belgeleri

5.  (İsteğe bağlı) [Çoklu platform - paylaşım kullanıcı Arabirimi kod Xamarin.Forms ile mobil platformlarda](https://msdn.microsoft.com/magazine/dn904669.aspx) Jason Smith (MSDN dergisi) anahatları Xamarin.Forms, kendisi için ayrıntıları ele alınmıştır şirket içinde farklı özelleştirme seçenekleri tarafından [ Özel oluşturucular](/xamarin/xamarin-forms/app-fundamentals/custom-renderer/).

## <a name="deeper-dive-debugging-with-emulators"></a>Derin Dalış: Emulator'lar ile hata ayıklama

*10-15 dakika*

Platformlar arası uygulamalarınızı fiziksel bir cihaz kullanmak zorunda kalmadan hata ayıklamak için burada açıklanan öykünücüleri kullanılacak gerekir:

### <a name="microsofts-android-emulator"></a>Microsoft'un Android öykünücüsü

Microsoft'un kullanmanız önerilir [Android için Visual Studio öykünücüsü](visual-studio-emulator-for-android.md), Visual Studio ile yüklenir.  [Android için Visual Studio öykünücüsü](https://channel9.msdn.com/events/Visual-Studio/Connect-event-2015/711) video (Channel9, 5m55s), bir genel bakış ve tanıtım sunmaktadır.

### <a name="apples-ios-simulator"></a>Apple iOS simülatörü

Daha fazla bilgi edinmek için [iOS Simulator ile çalışmaya başlama](https://developer.apple.com/library/prerelease/content/documentation/IDEs/Conceptual/iOS_Simulator_Guide/GettingStartedwithiOSSimulator/GettingStartedwithiOSSimulator.html#//apple_ref/doc/uid/TP40012848-CH5-SW1) (apple.com).

### <a name="microsofts-windows-phone-emulator"></a>Microsoft'un Windows Phone öykünücüsü

Daha fazla bilgi edinmek için [Windows 10 Mobile için Microsoft Emulator ile Test](/windows/uwp/debug-test-perf/test-with-the-emulator).

<a name="components" />

## <a name="deeper-dive-xamarin-components"></a>Derin Dalış: Xamarin bileşenleri

*10 dakika*

Çok sayıda genişletilmiş özellikler, Xamarin bileşenleri ile Xamarin uygulamaları için kullanılabilir. Ücretsiz olarak kullanılabilir tam katalog bulabilirsiniz [ http://components.xamarin.com/ ](http://components.xamarin.com/), bileşenler için ek kullanıcı Arabirimi denetimleri, kimlik doğrulaması, Microsoft Azure gibi bulut hizmetlerini ve daha fazlasını içerir.