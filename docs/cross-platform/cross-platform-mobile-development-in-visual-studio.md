---
title: "Visual Studio'da platformlar arası Mobil Geliştirme | Microsoft Docs"
ms.custom: 
ms.date: 12/06/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-mobile
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8202717a-e990-45cf-b092-438651ccb38a
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0f047b143a7d0955d8ac3e2708098a903c73da59
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="cross-platform-mobile-development-in-visual-studio"></a>Visual Studio'da platformlar arası Mobil Geliştirme
Visual Studio kullanarak Android, iOS ve Windows cihazlar için uygulamalar oluşturabilirsiniz.  Uygulamanızı tasarlarken, kolayca Office 365, Azure App Service ve Application Insights gibi bağlı hizmetler ekleme için Visual Studio araçlarını kullanın.

 C# ve .NET Framework, HTML ve JavaScript ya da C++ kullanarak uygulamalarınızı oluşturun. Kodu, dize, görüntüleri paylaşabilir ve bazı durumlarda bile kullanıcı arabirimi.

 Oyun ya da derinlikli bir grafik uygulaması oluşturmak istiyorsanız, Unity için Visual Studio Araçları'nı yükleyin ve tüm Visual Studio ile Unity, popüler platformlar arası oyun/grafik altyapısı ve geliştirme ortamı uygulamalar için güçlü verimlilik özelliklerini keyfini çıkarın, iOS, Android, Windows ve diğer platformlar üzerinde çalıştırın.

 **Bu makalede:**

-   [Android, iOS ve Windows (.NET Framework) için bir uygulama oluşturun](#NET)

    -   [Android, iOS ve Windows bir tek kodundan temel hedef](../cross-platform/cross-platform-mobile-development-in-visual-studio.md#AndroidHTML)

    -   [Hedef Windows 10 cihazları](../cross-platform/cross-platform-mobile-development-in-visual-studio.md#WindowsHTML)

-   [Android, iOS ve Windows (HTML/JavaScript) için bir uygulama oluşturun](#HTML)

-   [Android ve Windows (C++) için bir uygulama oluşturun](#CPP)

-   [Unity için Visual Studio araçları kullanarak Android, iOS ve Windows için platformlar arası oyun derleme](#Unity)

##  <a name="NET"></a>Android, iOS ve Windows (.NET Framework) için bir uygulama oluşturun
 ![Devices](../cross-platform/media/homedevices.png "HomeDevices")

 Xamarin ile kod ve hatta UI paylaşımı aynı çözümde, Android, iOS ve Windows hedefleyebilirsiniz.

|**Daha fazla bilgi edinin**|
|--------------------|
|[Visual Studio yükleme](http://www.visualstudio.com/products/visual-studio-community-vs) (VisualStudio.com)|
|[Visual Studio'da Xamarin hakkında bilgi edinin](http://www.visualstudio.com/explore/xamarin-vs) (VisualStudio.com)|
|[Visual Studio ve Xamarin](../cross-platform/visual-studio-and-xamarin.md) (MSDN Kitaplığı)|
|[Xamarin uygulamalarıyla uygulama yaşam döngüsü yönetimi (ALM)](../cross-platform/application-lifecycle-management-alm-with-xamarin-apps.md) (MSDN Kitaplığı)|
|[Visual Studio'da Evrensel Windows uygulamaları hakkında bilgi edinin](https://www.visualstudio.com/vs/universal-windows-platform/) (VisualStudio.com)|
|[SWIFT ve C# arasındaki benzerlikler hakkında bilgi edinin](http://aka.ms/scposter) (download.microsoft.com)|
|[Android için Visual Studio öykünücüsü hakkında bilgi edinin](http://www.visualstudio.com/explore/msft-android-emulator-vs) (VisualStudio.com)|

###  <a name="AndroidHTML"></a>Android, iOS ve Windows bir tek kodundan temel hedef
 C# veya F # (Visual Basic şu anda desteklenmiyor) kullanarak, Android, iOS ve Windows için yerel uygulamalar oluşturabilirsiniz.  Başlamak için Visual Studio 2015 yüklemek, seçin **özel** seçeneğini yükleyicisinde ve onay kutusunu altında **platformlar arası mobil geliştirme > C# / .NET (Xamarin)**. İle de başlatabilirsiniz [Xamarin yükleyici](https://www.xamarin.com/download), Visual Studio 2013 için Xamarin yüklemek için gerekli.

 Visual Studio 2015 yüklü zaten varsa, Yükleyiciden çalıştırmanız **Denetim Masası > Programlar ve Özellikler** ve aynı seçin **özel** yukarıdaki xamarin seçeneği.

 İşiniz bittiğinde, proje şablonları görünür **yeni proje** iletişim kutusu. Yalnızca "Xamarin" üzerinde aramak için Xamarin şablonları bulmanın en kolay yolu olan

 Xamarin Android, iOS ve Windows yerel işlevselliği .NET nesneleri olarak kullanıma sunar. Bu nedenle, uygulamalarınızı yerel API'ları ve yerel kullanıcı denetimleri tam erişimi vardır ve yalnızca, yerel platform dillerde yazılmış uygulamalar olarak yanıt.

 Bir proje oluşturduğunuzda, tüm Visual Studio üretkenlik özelliklerini yararlanın. Örneğin, sayfalarınızı oluşturmak için bir tasarımcı kullanacak ve yerel API'nin mobil platformlardan keşfetmek için IntelliSense kullanma. Uygulamanızı çalıştırın ve nasıl göründüğünü görmek hazır olduğunuzda, Android veya Android SDK öykünücüsü için Visual Studio öykünücüsü kullanarak Windows uygulamaları yerel olarak çalıştırın veya Windows uygulamalarını Windows Phone öykünücüsünde çalıştırın. Internet paylaşımlı Android ve Windows cihazları doğrudan de kullanabilirsiniz. İOS projeleri için ağa bağlı bir Mac bağlanın ve Visual Studio'dan Mac öykünücüyü başlatın veya Internet paylaşımlı bir cihaza bağlanın.

#### <a name="design-one-set-of-pages-that-render-across-all-devices-by-using-xamarinforms"></a>Tasarım bir Xamarin.Forms kullanarak cihazlara işlemek sayfalar kümesi
 Uygulamaları tasarımınızı karmaşıklığına bağlı olarak, kullanarak oluşturmayı düşünebilirsiniz *Xamarin.Forms* şablonlarında **Mobile Apps** proje şablonları grubunu. Xamarin.Forms, Android, iOS ve Windows arasında paylaşabilmek için tek bir arabirim oluşturmanıza olanak sağlayan bir UI araç takımıdır.  Xamarin.Forms çözümünü derlediğinizde, bir Android uygulaması, bir iOS uygulaması ve bir Windows uygulaması elde edersiniz. Daha fazla ayrıntı için bkz: [mobil geliştirme hakkında bilgi edinin Xamarin ile](../cross-platform/learn-about-mobile-development-with-xamarin.md).

####  <a name="ShareHTML"></a>Kod Android, iOS ve Windows uygulamaları arasında paylaşma
 Xamarin.Forms kullanmıyorsanız ve her platform için ayrı ayrı tasarlamak seçerseniz, çoğu kullanıcı Arabirimi olmayan kodunuzun platform projeler (Android, iOS ve Windows) arasında paylaşabilirsiniz. Bu, iş mantığı, bulut tümleştirme, veritabanı erişimi veya .NET Framework hedefleyen başka bir kod içerir. Paylaşan olamaz yalnızca belirli bir platformun hedefleyen kod kodudur.

 ![Kod Windows, iOs ve Android kullanıcı Arabiriminin arasında paylaşmak](../cross-platform/media/sharecode.png "ShareCode")

 Paylaşılan bir proje, taşınabilir sınıf kitaplığı proje ya da her ikisini de kullanarak kodunuzu paylaşabilirsiniz. Paylaşılan bir proje ve bazı kodlar iyi daha fazla yapar bazı kod sığar taşınabilir sınıf kitaplığı proje mantıklı bulabilirsiniz.

|**Daha fazla bilgi edinin**|
|--------------------|
|Paylaşılan projeleri, taşınabilir Sınıf Kitaplığı projelerinde veya her ikisini de kullanarak kodunuzu paylaşmak isteyip istemediğinizi seçin.<br /><br /> [Platformlar arası kod paylaşımını](http://blogs.msdn.com/b/dotnet/archive/2014/04/21/sharing-code-across-platforms.aspx) (.NET Framework blogu)<br /><br /> [Paylaşım kodu seçeneklerini](http://developer.xamarin.com/guides/cross-platform/application_fundamentals/building_cross_platform_applications/sharing_code_options/) (Xamarin)<br /><br /> [.NET Framework ile paylaşım seçeneklerini kodu](http://msdn.microsoft.com/library/dn720832.aspx) (MSDN Kitaplığı)|

###  <a name="WindowsHTML"></a>Hedef Windows 10 cihazları
 ![Windows aygıtları](../cross-platform/media/windowsdevices.png "WindowsDevices")

 Windows 10 cihazları olan tüm tekliflerden hedefler tek bir uygulama oluşturmak istiyorsanız, bir evrensel Windows uygulaması oluşturun. Tek bir proje kullanarak uygulama tasarlama ve hangi cihaz olsun, bunları görüntülemek için kullanılır sayfalarınızı düzgün işlemez.

 Evrensel Windows uygulaması proje şablonu ile başlayın. Sayfalarınızın görsel olarak tasarlamak ve ardından bunları çeşitli cihaz türlerini nasıl göründükleri görmek için Önizleme penceresini açın. Bir sayfa bir cihazda nasıl göründüğünü hoşlanmıyorsanız, sayfanın ekran boyutu, çözüm ya da yatay veya dikey modu gibi çeşitli yönleri daha iyi uyacak şekilde en iyi duruma getirebilirsiniz. Tümünü Visual Studio'da sezgisel aracını windows ve kolayca erişilebilir menü seçeneklerini kullanarak yapabilirsiniz. Uygulama ve adım kodunuzu çalıştırmak hazır olduğunuzda, tüm aygıt benzetmeleri ve benzeticileri farklı türde aygıtlar için birlikte bulunan bir aşağı açılan listesinde bulabilirsiniz **standart** araç.

 Windows 10 oldukça yeni olduğundan, ayrıca Windows 8.1 hedefleyen proje şablonları bulabilirsiniz. İstediğiniz ve uygulamanızı Windows 10 telefon, Tablet ve bilgisayar üzerinde çalışır, bu proje şablonları kullanabilirsiniz. Ancak, Windows 8.1 çalıştıran tüm cihazlara otomatik alacak Windows 10 yükseltme, bu nedenle neden yerine hedef Windows 8.1, belirli nedenleri yoksa öneririz Windows 10 hedef proje şablonları kullanın.

|**Daha fazla bilgi edinin**|
|--------------------|
|[Evrensel Windows uygulamaları hakkında bilgi edinin](https://msdn.microsoft.com/library/windows/apps/dn894631.aspx) (Windows Dev Center)|
|[İlk bir yapı](http://msdn.microsoft.com/library/windows/apps/dn609832.aspx) (Windows Dev Center)|
|[Evrensel Windows Platformu (UWP) için uygulama geliştirme](../cross-platform/develop-apps-for-the-universal-windows-platform-uwp.md)|
|[Uygulamaları Evrensel Windows Platformu (UWP) geçirme](https://msdn.microsoft.com/en-us/library/mt148501.aspx)|

##  <a name="HTML"></a>Android, iOS ve Windows (HTML/JavaScript) için bir uygulama oluşturun
 ![Devices](../cross-platform/media/homedevices.png "HomeDevices")

 Web Geliştiriciyseniz ve HTML ve JavaScript hakkında bilginiz varsa, Apache Cordova için Visual Studio araçları kullanarak Windows, Android ve iOS hedefleyebilirsiniz. Bu uygulamaları, tüm üç platformlar hedefleyebilir ve yetenekleri ve en aşina işlemleri kullanarak oluşturabilirsiniz.

 Apache Cordova bir eklenti modeli içeren bir çerçevedir. Bu eklenti modeli, tüm üç platformlar (Android, iOS ve Windows) yerel cihaz özelliklerine erişmek için kullanabileceğiniz tek bir JavaScript API sağlar.

 Bu API'leri platformlar arası olduğundan, tüm üç platformlar yazma çoğu paylaşabilirsiniz. Bu, geliştirme ve Bakım maliyetlerinizi azaltır. Ayrıca, baştan başlatmaya gerek yoktur. Web uygulamalarının diğer türleri oluşturduysanız, değiştirme veya bunların herhangi bir şekilde yeniden tasarlamanız gerek kalmadan, bu dosyaları Cordova uygulamanız ile paylaşabilirsiniz.

 ![Çoklu &#45; cihaz karma uygulamalar](../cross-platform/media/multidevicehybridapps.png "MultiDeviceHybridApps")

 Başlamak için Visual Studio 2015 yükler ve **HTML/JavaScript (Apache Cordova)** Kurulum sırasında özelliği. Visual Studio 2013 kullanıyorsanız, Apache Cordova uzantısı için Visual Studio Araçları yükleyin. Her iki durumda da, Cordova araçları ve birden çok platform uygulamanızı oluşturmak için gerekli olan tüm üçüncü taraf yazılımları otomatik olarak yükler.

 Uzantıyı yükledikten sonra Visual Studio'yu açın ve oluşturma bir **boş uygulama (Apache Cordova)** projesi. Ardından, JavaScript veya Typescript kullanarak uygulamanızı geliştirebilirsiniz. Uygulamanızı işlevselliğini genişletmek için eklentilerini de ekleyebilirsiniz ve kod yazarken eklentileri API'lerden IntelliSense içinde görünür.

 Uygulama ve adım kodunuzu çalıştırmak hazır olduğunuzda, Apache Ripple öykünücü veya Visual Studio öykünücüsü (Android veya Windows Phone), bir tarayıcı veya bilgisayarınıza doğrudan bağlı bir aygıtı gibi bir öykünücü seçin. Daha sonra uygulamanızı başlatın. Uygulamanızı bir Windows bilgisayarında geliştiriyorsanız bile oturum çalıştırabilirsiniz. Bu seçeneklerin tümü, Visual Studio Araçları'nın bir parçası olarak Visual Studio uygulamasına Apache Cordova için yerleşik olarak bulunur.

 Evrensel Windows uygulamaları oluşturma Visual Studio'da hala kullanılabilir proje şablonları bu nedenle yalnızca Windows cihazları hedef planlıyorsanız, bunları kullanmaya çekinmeyin. Daha sonra hedef Android ve iOS karar verirseniz, kodunuzu bir Cordova projesi için her zaman bağlantı noktası. Bu API tüketir herhangi bir kod yeniden şekilde WinJS API'leri açık kaynak sürümü vardır. Bu, diğer platformlar gelecekte hedef planlıyorsanız, da Apache Cordova için Visual Studio Araçları ile başlamanızı öneririz belirtti.

|**Daha fazla bilgi edinin**|
|--------------------|
|[Visual Studio yükleme](http://www.visualstudio.com/products/visual-studio-community-vs) (VisualStudio.com)|
|[Apache Cordova için Visual Studio Araçları ile çalışmaya başlama](/visualstudio/cross-platform/tools-for-cordova/) (docs.microsoft.com)|
|[Android için Visual Studio öykünücüsü hakkında bilgi edinin](http://www.visualstudio.com/explore/msft-android-emulator-vs) (VisualStudio.com)|

##  <a name="CPP"></a>Android ve Windows (C++) için bir uygulama oluşturun
 ![C &#43; &#43;kullanın; Android, iOS ve Windows için oluşturmak için](../cross-platform/media/cross_plat_cpp_intro_image.png "Cross_Plat_CPP_Intro_Image")

 İlk olarak, Visual Studio 2015 ve Visual C++ platformlar arası mobil geliştirme araçlarını yükleyin. Ardından, Android veya Windows hedefleyen bir uygulama için bir yerel etkinlik uygulaması oluşturabilirsiniz. İOS hedefleyen C++ şablonları henüz kullanılabilir değil. Ve ardından aralarındaki platformlar arası statik veya dinamik paylaşılan bir kitaplık kullanılarak kod paylaşmak istiyorsanız aynı çözüm içinde Android ve Windows hedefleyebilirsiniz.

 Herhangi bir tür bir oyun gibi gelişmiş grafik işleme gerektiren Android için bir uygulama oluşturmak ihtiyacınız varsa, C++ yapmak için kullanabilirsiniz. İle başlayan **yerel etkinlik uygulama (Android)** projesi. Bu proje Clang zincirinin için tam destek vardır.

 ![Yerel etkinlik proje şablonu](../cross-platform/media/cross-plat_cpp_native.png "arası Plat_CPP_Native")

 Uygulamanızı çalıştırmak ve nasıl göründüğünü görmek hazır olduğunuzda, Android için Visual Studio öykünücüsü kullanın. Hızlı, güvenilir ve kolay yüklemek ve yapılandırmak.

 Ayrıca, C++ ve bir evrensel Windows uygulaması proje şablonunu kullanarak Windows 10 cihazları olan tüm tekliflerden hedefleyen bir uygulama oluşturabilirsiniz. Bu konu hakkında daha fazla bilgiyi [hedef Windows 10 cihazları](#WindowsHTML) bu konunun önceki kısımlarında görünür bölümü.

 Statik veya dinamik bir paylaşılan kitaplığı oluşturarak C++ kod Android ve Windows arasında paylaşabilirsiniz.

 ![Statik ve dinamik paylaşılan kitaplıklar](../cross-platform/media/cross_plat_cpp_libraries.png "Cross_Plat_CPP_Libraries")

 Bir Windows ya da daha önce bu bölümde açıklanan olanlar gibi Android projesi bu kitaplığı kullanabilir. Ayrıca, bir uygulamada Xamarin, Java veya yönetilmeyen DLL işlevlerini çağırma olanak sağlayan herhangi bir dil kullanarak oluşturduğunuz kullanmasını sağlayabilirsiniz.

 Bu kitaplıklar kod yazarken, Android ve Windows platformlarında yerel API'leri keşfetmek için IntelliSense kullanabilirsiniz. Kesme noktaları, kod, aracılığıyla adım ayarlayabilir ve bulmak ve tüm hata ayıklayıcı gelişmiş özelliklerini kullanarak sorunları düzeltmek için bu kitaplık projeleri Visual Studio hata ayıklayıcısı ile tam olarak tümleşiktir.

|**Daha fazla bilgi edinin**|
|--------------------|
|[Visual Studio indirin.](http://www.visualstudio.com/products/visual-studio-community-vs) (VisualStudio.com)|
|[Visual C++ için platformlar arası mobil geliştirme araçlarını yükleyin.](https://msdn.microsoft.com/library/dn872463\(v=vs.140\).aspx) (MSDN Kitaplığı)|
|[Hedef birden çok platform için C++ kullanma hakkında daha fazla bilgi edinin.](https://www.visualstudio.com/vs/cplusplus-mdd/) (VisualStudio.com)|
|[Neleri gerekir ve ardından Android için bir yerel etkinlik uygulaması oluşturun yüklemek](https://msdn.microsoft.com/library/dn872463\(v=vs.140\).aspx) (MSDN Kitaplığı)|
|[Android için Visual Studio öykünücüsü hakkında bilgi edinin](http://www.visualstudio.com/explore/msft-android-emulator-vs) (VisualStudio.com)|
|[C++ kodu ile Android ve Windows uygulamaları paylaşma hakkında daha fazla bilgi](https://www.visualstudio.com/vs/cplusplus-mdd/) (VisualStudio.com)|
|[C++ için platformlar arası mobil geliştirme örnekleri](https://msdn.microsoft.com/library/dn707596.aspx) (MSDN Kitaplığı)|
|[C++ için ek platformlar arası mobil geliştirme örnekleri](https://code.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=android&f%5B1%5D.Type=ProgrammingLanguage&f%5B1%5D.Value=C%2B%2B&f%5B1%5D.Text=C%2B%2B) (code.msdn)|

##  <a name="Unity"></a>Unity için Visual Studio araçları kullanarak Android, iOS ve Windows için platformlar arası oyun derleme
 Unity için Visual Studio Araçları, Visual Studio'nun güçlü kod düzenleme, verimliliği ve hata ayıklama araçları ile tümleşir Visual Studio için boş bir uzantısı olduğundan *Unity*, popüler platformlar arası oyun/grafik altyapısı ve geliştirme ortamı hedef Windows, iOS, Android ve web dahil olmak üzere diğer platformlarda modern uygulamalar için.

 ![VSTU geliştirme ortamı](../cross-platform/media/vstu_overview.png "VSTU_Overview")

 Visual Studio Araçları ile Unity (VSTU), oyun ve düzenleyici betikler C# ' ta oluşturma ve ardından güçlü, hata ayıklayıcı bulmak ve hataları düzeltmek için Visual Studio'yu kullanabilirsiniz. VSTU en son sürümünü Unity 5 için destek getirir ve Unity'nın ShaderLab gölgelendirici dil için söz dizimi renklendirme, daha iyi eşitlemesi Unity, daha zengin hata ayıklama ve geliştirilmiş kod oluşturma için MonoBehavior Sihirbazı'nı içerir. VSTU Unity proje dosyalarınıza, konsol iletileri ve daha az zaman için ve Unity Düzenleyicisi'nden kod yazarken geçiş harcayabilir şekilde oyununuzu Visual Studio'ya Başlat yeteneğini de getirir.

 Oyununuzu Unity ve Unity için Visual Studio Araçları ile oluşturmaya hemen başlayın.

|**Daha fazla bilgi edinin**|
|--------------------|
|[Visual Studio ile oyunlar Unity oluşturma hakkında daha fazla bilgi edinin](https://www.visualstudio.com/en-us/features/unitytools-vs.aspx)|
|[Unity için Visual Studio Araçları hakkında daha fazla bilgiyi](../cross-platform/visual-studio-tools-for-unity.md) (MSDN Kitaplığı)|
|[Unity için Visual Studio araçlarını kullanmaya başlama](../cross-platform/getting-started-with-visual-studio-tools-for-unity.md) (MSDN Kitaplığı)|
|[En son geliştirmeleri hakkında Unity 2.0 Önizleme için Visual Studio Araçları okuma](http://blogs.msdn.com/b/visualstudio/archive/2014/12/03/visual-studio-tools-for-unity-2-0-preview.aspx) (Visual Studio blogu)|
|[Visual Studio Araçları bir video girişi Unity 2.0 Önizleme için izleme](http://www.bing.com/videos/search?q=visual+studio+tools+for+unity&qs=n&form=QBVLPG&pq=visual+studio+tools+for+unity&sc=6-29&sp=-1&sk=#view=detail&mid=0A13177F0BC7463A24080A13177F0BC7463A2408) (Video)|
|[Unity hakkında bilgi edinin](http://unity3d.com/) (Unity Web sitesi)|

## <a name="see-also"></a>Ayrıca Bkz.
 - [Office 365 API'nin bir Visual Studio projesi ekleme](http://msdn.microsoft.com/library/office/dn605899\(v=office.15\).aspx)
 - [Azure uygulama hizmetleri - mobil uygulamalar](https://azure.microsoft.com/en-us/services/app-service/mobile/)
 - [Mobil için HockeyApp](https://azure.microsoft.com/en-us/services/hockeyapp/)