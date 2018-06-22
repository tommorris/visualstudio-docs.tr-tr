---
title: Visual Studio'da platformlar arası Mobil Geliştirme | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2018
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 8202717a-e990-45cf-b092-438651ccb38a
author: asb3993
ms.author: amburns
manager: crdun
ms.workload:
- multiple
ms.openlocfilehash: fdb86d41096ddcd45cbef9bf9a3a6ffbffe188c0
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36281812"
---
# <a name="cross-platform-mobile-development-in-visual-studio"></a>Visual Studio'da platformlar arası Mobil Geliştirme

Visual Studio kullanarak Android, iOS ve Windows cihazlar için uygulamalar oluşturabilirsiniz.  Uygulamanızı tasarlarken, kolayca Office 365, Azure App Service ve Application Insights gibi bağlı hizmetler ekleme için Visual Studio araçlarını kullanın.

C# ve .NET Framework, HTML ve JavaScript ya da C++ kullanarak uygulamalarınızı oluşturun. Kodu, dize, görüntüleri paylaşabilir ve bazı durumlarda bile kullanıcı arabirimi.

Oyun ya da derinlikli bir grafik uygulaması oluşturmak istiyorsanız, Unity için Visual Studio Araçları'nı yükleyin ve tüm Visual Studio ile Unity, popüler platformlar arası oyun/grafik altyapısı ve geliştirme ortamı uygulamalar için güçlü verimlilik özelliklerini keyfini çıkarın, iOS, Android, Windows ve diğer platformlar üzerinde çalıştırın.

## <a name="build-an-app-for-android-ios-and-windows-net-framework"></a>Android, iOS ve Windows (.NET Framework) için bir uygulama oluşturun

![Aygıtları](../cross-platform/media/homedevices.png "HomeDevices")

Xamarin için Visual Studio Araçları ile kod ve hatta UI paylaşımı aynı çözümde, Android, iOS ve Windows hedefleyebilirsiniz.

|**Daha fazla bilgi edinin**|
|--------------------|
|[Visual Studio yükleme](http://visualstudio.microsoft.com/products/visual-studio-community-vs) (VisualStudio.com)|
|[Visual Studio'da Xamarin hakkında bilgi edinin](http://visualstudio.microsoft.com/explore/xamarin-vs) (VisualStudio.com)|
|[Xamarin mobil uygulama geliştirme belgeleri](/xamarin/) |
|[Xamarin uygulamalarıyla Uygulama Yaşam Döngüsü Yönetimi (ALM)](../cross-platform/application-lifecycle-management-alm-with-xamarin-apps.md) |
|[Visual Studio'da Evrensel Windows uygulamaları hakkında bilgi edinin](https://visualstudio.microsoft.com/vs/universal-windows-platform/) (VisualStudio.com)|
|[SWIFT ve C# arasındaki benzerlikler hakkında bilgi edinin](http://aka.ms/scposter) (download.microsoft.com)|

###  <a name="AndroidHTML"></a> Android, iOS ve Windows bir tek kodundan temel hedef

 C# veya F # (Visual Basic şu anda desteklenmiyor) kullanarak, Android, iOS ve Windows için yerel uygulamalar oluşturabilirsiniz.  Başlamak için Visual Studio 2017 yüklemek, seçin **mobil geliştirme .NET ile** yükleyici seçeneği.

 Visual Studio yüklü 2017 zaten varsa, yeniden çalıştırmanız **Visual Studio yükleyicisi** ve aynı seçin **mobil geliştirme .NET ile** xamarin seçeneği (yukarıdaki gibi).

 İşiniz bittiğinde, proje şablonları görünür **yeni proje** iletişim kutusu. Yalnızca "Xamarin" üzerinde aramak için Xamarin şablonları bulmanın en kolay yolu olan

 Xamarin Android, iOS ve Windows yerel işlevselliği .NET sınıflar ve yöntemler olarak kullanıma sunar. Bu, uygulamalarınızı yerel API'ları ve yerel denetimlere tam erişimi vardır ve bunlar yalnızca, yerel platform dillerde yazılmış uygulamalar gibi esnek anlamına gelir.

 Bir proje oluşturduğunuzda, tüm Visual Studio üretkenlik özelliklerini yararlanın. Örneğin, sayfalarınızı oluşturmak için bir tasarımcı kullanacak ve yerel API'nin mobil platformlardan keşfetmek için IntelliSense kullanma. Uygulamanızı çalıştırmak ve nasıl göründüğünü görmek hazır olduğunuzda, Android SDK öykünücüsü kullanın ve Windows uygulamalarını yerel olarak çalıştırın. Internet paylaşımlı Android ve Windows cihazları doğrudan de kullanabilirsiniz. İOS projeleri için ağa bağlı bir Mac bağlanın ve Visual Studio'dan iOS öykünücüyü başlatın veya Internet paylaşımlı bir cihaza bağlanma.

#### <a name="design-one-set-of-pages-that-render-across-all-devices-by-using-xamarinforms"></a>Tasarım bir Xamarin.Forms kullanarak cihazlara işlemek sayfalar kümesi

 Uygulamaları tasarımınızı karmaşıklığına bağlı olarak, kullanarak oluşturmayı düşünebilirsiniz *Xamarin.Forms* şablonlarında **Mobile Apps** proje şablonları grubunu. Xamarin.Forms, Android, iOS ve Windows arasında paylaşabilmek için tek bir arabirim oluşturmanıza olanak sağlayan bir UI araç takımıdır.  Xamarin.Forms çözümünü derlediğinizde, bir Android uygulaması, bir iOS uygulaması ve bir Windows uygulaması elde edersiniz. Daha fazla ayrıntı için bkz: [mobil geliştirme hakkında bilgi edinin xamarin'le](../cross-platform/learn-about-mobile-development-with-xamarin.md) ve [Xamarin.Forms belgelerine](/xamarin/xamarin-forms/).

####  <a name="ShareHTML"></a> Kod Android, iOS ve Windows uygulamaları arasında paylaşma

 Xamarin.Forms kullanmıyorsanız ve her platform için ayrı ayrı tasarlamak seçerseniz, çoğu kullanıcı Arabirimi olmayan kodunuzun platform projeler (Android, iOS ve Windows) arasında paylaşabilirsiniz. Bu, iş mantığı, bulut tümleştirme, veritabanı erişimi veya .NET Framework hedefleyen başka bir kod içerir. Paylaşan olamaz yalnızca belirli bir platformun hedefleyen kod kodudur.

 ![Kod Windows, iOs ve Android kullanıcı Arabiriminin arasında paylaşmak](../cross-platform/media/sharecode.png "ShareCode")

 Paylaşılan bir proje, taşınabilir sınıf kitaplığı proje ya da her ikisini de kullanarak kodunuzu paylaşabilirsiniz. Paylaşılan bir proje ve bazı kodlar iyi daha fazla yapar bazı kod sığar taşınabilir sınıf kitaplığı proje mantıklı bulabilirsiniz.

|**Daha fazla bilgi edinin**|
|--------------------|
|[Paylaşım kodu seçeneklerini](/xamarin/cross-platform/app-fundamentals/code-sharing/) (Xamarin) |
|[.NET ile paylaşım seçeneklerini kodu](/dotnet/standard/cross-platform/) |

###  <a name="WindowsHTML"></a> Hedef Windows 10 cihazları

 ![Windows aygıtları](../cross-platform/media/windowsdevices.png "Windows cihazları")

 Windows 10 cihazları olan tüm tekliflerden hedefler tek bir uygulama oluşturmak istiyorsanız, bir evrensel Windows uygulaması oluşturun. Tek bir proje kullanarak uygulama tasarlama ve hangi cihaz olsun, bunları görüntülemek için kullanılır sayfalarınızı düzgün işlemez.

 Evrensel Windows Platformu (UWP) uygulaması proje şablonu ile başlayın. Sayfalarınızın görsel olarak tasarlamak ve ardından bunları çeşitli cihaz türlerini nasıl göründükleri görmek için Önizleme penceresini açın. Bir sayfa bir cihazda nasıl göründüğünü hoşlanmıyorsanız, sayfanın ekran boyutu, çözüm ya da yatay veya dikey modu gibi çeşitli yönleri daha iyi uyacak şekilde en iyi duruma getirebilirsiniz. Tümünü Visual Studio'da sezgisel aracını windows ve kolayca erişilebilir menü seçeneklerini kullanarak yapabilirsiniz. Uygulama ve adım kodunuzu çalıştırmak hazır olduğunuzda, tüm aygıt benzetmeleri ve benzeticileri farklı türde aygıtlar için birlikte bulunan bir aşağı açılan listesinde bulabilirsiniz **standart** araç.

|**Daha fazla bilgi edinin**|
|--------------------|
|[Evrensel Windows platformu giriş](/windows/uwp/get-started/universal-application-platform-guide)|
|[İlk uygulamanızı oluşturma](/windows/uwp/get-started/your-first-app)|
|[Evrensel Windows Platformu (UWP) için uygulama geliştirme](../cross-platform/develop-apps-for-the-universal-windows-platform-uwp.md)|
|[Uygulamaları Evrensel Windows Platformu (UWP) geçirme](https://msdn.microsoft.com/en-us/library/mt148501.aspx)|

##  <a name="HTML"></a> Android, iOS ve Windows (HTML/JavaScript) için bir uygulama oluşturun

 ![Windows, iOS ve Android cihazları](../cross-platform/media/homedevices.png "Windows, iOS ve Android cihazları")

 Web Geliştiriciyseniz ve HTML ve JavaScript hakkında bilginiz varsa, Apache Cordova için Visual Studio araçları kullanarak Windows, Android ve iOS hedefleyebilirsiniz. Bu uygulamaları, tüm üç platformlar hedefleyebilir ve yetenekleri ve en aşina işlemleri kullanarak oluşturabilirsiniz.

 Apache Cordova bir eklenti modeli içeren bir çerçevedir. Bu eklenti modeli, tüm üç platformlar (Android, iOS ve Windows) yerel cihaz özelliklerine erişmek için kullanabileceğiniz tek bir JavaScript API sağlar.

 Bu API'leri platformlar arası olduğundan, tüm üç platformlar yazma çoğu paylaşabilirsiniz. Bu, geliştirme ve Bakım maliyetlerinizi azaltır. Ayrıca, baştan başlatmaya gerek yoktur. Web uygulamalarının diğer türleri oluşturduysanız, değiştirme veya bunların herhangi bir şekilde yeniden tasarlamanız gerek kalmadan, bu dosyaları Cordova uygulamanız ile paylaşabilirsiniz.

 ![Javascript ile çok cihazlı karma uygulamalar](../cross-platform/media/multidevicehybridapps.png "Javascript ile çok cihazlı karma uygulamalar")

 Başlamak için Visual Studio 2017 yükler ve **Javascript ile Mobil Geliştirme** Kurulum sırasında özelliği. Cordova araçları ve birden çok platform uygulamanızı oluşturmak için gerekli olan tüm üçüncü taraf yazılımları otomatik olarak yükler.

 Uzantıyı yükledikten sonra Visual Studio'yu açın ve oluşturma bir **boş uygulama (Apache Cordova)** projesi. Ardından, JavaScript veya Typescript kullanarak uygulamanızı geliştirebilirsiniz. Uygulamanızı işlevselliğini genişletmek için eklentilerini de ekleyebilirsiniz ve kod yazarken eklentileri API'lerden IntelliSense içinde görünür.

 Uygulama ve adım kodunuzu çalıştırmak hazır olduğunuzda, Apache Ripple öykünücü veya Android öykünücüsü, bir tarayıcı veya bilgisayarınıza doğrudan bağlı bir aygıtı gibi bir öykünücü seçin. Daha sonra uygulamanızı başlatın. Uygulamanızı bir Windows bilgisayarında geliştiriyorsanız bile oturum çalıştırabilirsiniz. Bu seçeneklerin tümü, Visual Studio Araçları'nın bir parçası olarak Visual Studio uygulamasına Apache Cordova için yerleşik olarak bulunur.

 Oluşturma Evrensel Windows Platformu (UWP) uygulamaları Visual Studio'da hala kullanılabilir proje şablonları bu nedenle yalnızca Windows cihazları hedef planlıyorsanız, bunları kullanmaya çekinmeyin. Daha sonra hedef Android ve iOS karar verirseniz, kodunuzu bir Cordova projesi için her zaman bağlantı noktası.

|**Daha fazla bilgi edinin**|
|--------------------|
|[Visual Studio yükleme](http://visualstudio.microsoft.com/products/visual-studio-community-vs) (VisualStudio.com)|
|[Apache Cordova için Visual Studio Araçları ile çalışmaya başlama](/visualstudio/cross-platform/tools-for-cordova/)|
|[Android için Visual Studio öykünücüsü hakkında bilgi edinin](http://visualstudio.microsoft.com/explore/msft-android-emulator-vs) (VisualStudio.com)|

<a name="CPP"></a>

## <a name="build-an-app-for-android-and-windows-c"></a>Android ve Windows (C++) için bir uygulama oluşturun
 ![Kullanım C&#43; &#43; Android, iOS ve Windows için oluşturmak için](../cross-platform/media/cross_plat_cpp_intro_image.png "Cross_Plat_CPP_Intro_Image")

 İlk olarak, Visual Studio 2017 yükleyin ve **mobil geliştirme C++ ile** iş yükü. Ardından, Android veya Windows hedefleyen bir uygulama için bir yerel etkinlik uygulaması oluşturabilirsiniz. İOS hedefleyen C++ şablonları henüz kullanılabilir değil. Ve ardından aralarındaki platformlar arası statik veya dinamik paylaşılan bir kitaplık kullanılarak kod paylaşmak istiyorsanız aynı çözüm içinde Android ve Windows hedefleyebilirsiniz.

 Herhangi bir tür bir oyun gibi gelişmiş grafik işleme gerektiren Android için bir uygulama oluşturmak ihtiyacınız varsa, C++ yapmak için kullanabilirsiniz. İle başlayan **yerel etkinlik uygulama (Android)** projesi. Bu proje Clang zincirinin için tam destek vardır.

 ![Yerel etkinlik proje şablonu](../cross-platform/media/cross-plat_cpp_native.png "yerel etkinlik proje şablonu")

 Uygulamanızı çalıştırmak ve nasıl göründüğünü görmek hazır olduğunuzda, Android öykünücüsünde kullanın. Hızlı, güvenilir ve kolay yüklemek ve yapılandırmak.

 Ayrıca, C++ ve Uiversal Windows Platformu (UWP) uygulaması proje şablonunu kullanarak Windows 10 cihazları olan tüm tekliflerden hedefleyen bir uygulama oluşturabilirsiniz. Bu konu hakkında daha fazla bilgiyi [hedef Windows 10 cihazları](#WindowsHTML) bu konunun önceki kısımlarında görünür bölümü.

 Statik veya dinamik bir paylaşılan kitaplığı oluşturarak C++ kod Android ve Windows arasında paylaşabilirsiniz.

 ![Statik ve dinamik paylaşılan kitaplıklar](../cross-platform/media/cross_plat_cpp_libraries.png "statik ve dinamik paylaşılan kitaplıklar")

 Bir Windows ya da daha önce bu bölümde açıklanan olanlar gibi Android projesi bu kitaplığı kullanabilir. Ayrıca, bir uygulamada Xamarin, Java veya yönetilmeyen DLL işlevlerini çağırma olanak sağlayan herhangi bir dil kullanarak oluşturduğunuz kullanmasını sağlayabilirsiniz.

 Bu kitaplıklar kod yazarken, Android ve Windows platformlarında yerel API'leri keşfetmek için IntelliSense kullanabilirsiniz. Kesme noktaları, kod, aracılığıyla adım ayarlayabilir ve bulmak ve tüm hata ayıklayıcı gelişmiş özelliklerini kullanarak sorunları düzeltmek için bu kitaplık projeleri Visual Studio hata ayıklayıcısı ile tam olarak tümleşiktir.

|**Daha fazla bilgi edinin**|
|--------------------|
|[Visual Studio indirin.](http://visualstudio.microsoft.com/products/visual-studio-community-vs) (VisualStudio.com)|
|[Visual C++ için platformlar arası mobil geliştirme araçlarını yükleyin.](https://msdn.microsoft.com/library/dn872463\(v=vs.140\).aspx) (MSDN Kitaplığı)|
|[Hedef birden çok platform için C++ kullanma hakkında daha fazla bilgi edinin.](https://visualstudio.microsoft.com/vs/cplusplus-mdd/) (VisualStudio.com)|
|[Neleri gerekir ve ardından Android için bir yerel etkinlik uygulaması oluşturun yüklemek](https://msdn.microsoft.com/library/dn872463\(v=vs.140\).aspx) (MSDN Kitaplığı)|
|[C++ kodu ile Android ve Windows uygulamaları paylaşma hakkında daha fazla bilgi](https://visualstudio.microsoft.com/vs/cplusplus-mdd/) (VisualStudio.com)|
|[C++ için platformlar arası mobil geliştirme örnekleri](https://msdn.microsoft.com/library/dn707596.aspx) (MSDN Kitaplığı)|
|[C++ için ek platformlar arası mobil geliştirme örnekleri](https://code.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=android&f%5B1%5D.Type=ProgrammingLanguage&f%5B1%5D.Value=C%2B%2B&f%5B1%5D.Text=C%2B%2B) (code.msdn)|

<a name="Unity"></a>

## <a name="build-a-cross-platform-game-for-android-ios-and-windows-by-using-visual-studio-tools-for-unity"></a>Unity için Visual Studio araçları kullanarak Android, iOS ve Windows için platformlar arası oyun derleme

 Unity için Visual Studio Araçları, Visual Studio'nun güçlü kod düzenleme, verimliliği ve hata ayıklama araçları ile tümleşir Visual Studio için boş bir uzantısı olduğundan *Unity*, popüler platformlar arası oyun/grafik altyapısı ve geliştirme ortamı hedef Windows, iOS, Android ve web dahil olmak üzere diğer platformlarda modern uygulamalar için.

 ![VSTU geliştirme ortamı](../cross-platform/media/vstu_overview.png "Unity genel bakış için Visual Studio Araçları")

 Visual Studio Araçları ile Unity (VSTU), oyun ve düzenleyici betikler C# ' ta oluşturma ve ardından güçlü, hata ayıklayıcı bulmak ve hataları düzeltmek için Visual Studio'yu kullanabilirsiniz. VSTU en son sürümünü Unity 2018.1 için destek getirir ve Unity'nın ShaderLab gölgelendirici dil için söz dizimi renklendirme, daha iyi eşitlemesi Unity, daha zengin hata ayıklama ve geliştirilmiş kod oluşturma için MonoBehavior Sihirbazı'nı içerir. VSTU Unity proje dosyalarınıza, konsol iletileri ve daha az zaman için ve Unity Düzenleyicisi'nden kod yazarken geçiş harcayabilir şekilde oyununuzu Visual Studio'ya Başlat yeteneğini de getirir.

|**Daha fazla bilgi edinin**|
|--------------------|
|[Visual Studio ile oyunlar Unity oluşturma hakkında daha fazla bilgi edinin](https://visualstudio.microsoft.com/vs/features/game-development/#tab-4b0d0be8de5f65564ad)|
|[Unity için Visual Studio Araçları hakkında daha fazla bilgi](../cross-platform/visual-studio-tools-for-unity.md) |
|[Unity için Visual Studio araçlarını kullanmaya başlama](../cross-platform/getting-started-with-visual-studio-tools-for-unity.md) |
|[En son geliştirmeleri hakkında Unity 2.0 Önizleme için Visual Studio Araçları okuma](http://blogs.msdn.com/b/visualstudio/archive/2014/12/03/visual-studio-tools-for-unity-2-0-preview.aspx) (Visual Studio blogu)|
|[Visual Studio Araçları bir video girişi Unity 2.0 Önizleme için izleme](http://www.bing.com/videos/search?q=visual+studio+tools+for+unity&qs=n&form=QBVLPG&pq=visual+studio+tools+for+unity&sc=6-29&sp=-1&sk=#view=detail&mid=0A13177F0BC7463A24080A13177F0BC7463A2408) (Video)|
|[Unity hakkında bilgi edinin](http://unity3d.com/) (Unity Web sitesi)|

## <a name="see-also"></a>Ayrıca Bkz.

- [Office 365 API'nin bir Visual Studio projesi ekleme](http://msdn.microsoft.com/library/office/dn605899\(v=office.15\).aspx)
- [Azure uygulama hizmetleri - mobil uygulamalar](https://azure.microsoft.com/services/app-service/mobile/)
- [Visual Studio App Center](https://docs.microsoft.com/appcenter)