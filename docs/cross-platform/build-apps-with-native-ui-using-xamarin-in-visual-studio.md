---
title: Visual Studio'da Xamarin kullanarak yerel UI ile uygulamalar oluşturun. | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 30f137e6-595d-4ce7-b8f5-415b07c1caa2
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: b68dd62de137e3c9427715c647ba4a53f07bd281
ms.sourcegitcommit: 9765b3fcf89375ca499afd9fc42cf4645b66a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2018
ms.locfileid: "46496161"
---
# <a name="build-apps-with-native-ui-using-xamarin-in-visual-studio"></a>Visual Studio’da Xamarin kullanarak yerel kullanıcı arabirimi ile uygulama oluşturma

Platformlar arası mobil uygulamalar yazmak için Xamarin ve C# seçen Çoğu geliştirici için Xamarin.Forms kullanın. Xamarin.Forms, iOS, Android ve evrensel Windows Platformu (UWP) yerel denetimlere eşleyen bir kullanıcı arabirimi tanımlar. Xamarin.Forms makalesinde açıklanan [Visual Studio'da Xamarin.Forms ile uygulama oluşturmaya yönelik temel bilgileri öğrenin](learn-app-building-basics-with-xamarin-forms-in-visual-studio.md).

Bu makalede, her platform için yerel kullanıcı arabirimi API'leri erişim gerektirir ve farklı bir yaklaşım açıklanmaktadır. Yerel API'lerin çalışma Xamarin.Forms daha bir çok daha zor yaklaşım çünkü her platform için kapsamlı bilgi gerektirir. Her platform özellikleri ve özel güçler kullanıcı arabirimine yine de temel alınan iş mantığı paylaşırken uyarlayabileceğiniz avantajlarındandır.

Adımları yaptıktan sonra [Kurulum ve yükleme](../cross-platform/setup-and-install.md) ve [Xamarin ortamınızı doğrulama](../cross-platform/verify-your-xamarin-environment.md), bu izlenecek yol, yerel UI katmanlar ile temel bir Xamarin uygulaması oluşturma işlemini göstermektedir. Yerel UI ile paylaşılan kod bir .NET Standard kitaplığı içinde bulunan ve ayrı bir platform projeleri kullanıcı Arabirimi tanımları içerir. İşte (soldan sağa) üzerinde çalışan oluşturacaksınız uygulaması iOS ve Android telefonlar ve Windows 10 Masaüstü.

![İOS, Android ve Windows Xamarin uygulaması](../cross-platform/media/cross-plat-xamarin-build-1-Large.png#lightbox)

Derlemek için bu işlemleri yapmanız:

- [Çözümünüzü ayarlama](#solution)

- [Paylaşılan veri hizmeti kod yazma](#dataservice)

- [Android için kullanıcı Arabirimi tasarımı](#Android)

- [Windows için kullanıcı Arabirimi tasarımı](#Windows)

- [Sonraki adımlar](#next), aşağıdakileri içeren bir iOS kullanıcı arabirimi tasarlama

> [!TIP]
> Bu proje için tam kaynak kodunu bulabilirsiniz [github'daki mobil-samples deposuna](https://github.com/xamarin/mobile-samples/tree/master/Weather).
>
> Güçlük veya hatalarla karşılaşırsanız lütfen hakkında sorularınızı [forums.xamarin.com](http://forums.xamarin.com). Birçok hataları açıklanan olan en son SDK Xamarin tarafından gerekli güncelleştirerek çözülebilir [Xamarin sürüm notları](https://developer.xamarin.com/releases/) her platform için.

> [!NOTE]
> Xamarin Geliştirici belgeleri, aşağıda listelenen birkaç izlenecek yollar hem hızlı başlangıç hem de yakından bölümleri ile de sunar. Tüm bu sayfalarda belirli Visual Studio için izlenecek yollar görmek için "Visual Studio" seçili olduğundan emin olun.
>
>  -   Xamarin uygulamaları yerel UI ile:
>     -   [Hello, Android](/xamarin/android/get-started/hello-android/) (tek ekranlı basit uygulama)
>     -   [Hello, Android çoklu ekranı](/xamarin/android/get-started/hello-android-multiscreen/) (ekranlar arasında gezintiyi uygulamayla)
>     -   [Android parçaları izlenecek](/xamarin/android/platform/fragments/implementing-with-fragments/) (diğer özelliklerin yanı sıra ana/ayrıntı ekranları için kullanılır)
>     -   [Hello, iOS](/xamarin/ios/get-started/hello-iOS/)
>     -   [Çok Ekranlı Hello, iOS ](/xamarin/ios/get-started/hello-iOS-multiscreen/)

>  -   Xamarin.Forms (paylaşılan UI) ile Xamarin uygulamaları
>     -   [Hello, Xamarin.Forms](/xamarin/xamarin-forms/get-started/hello-xamarin-forms/quickstart/)
>     -   [Hello, Xamarin.Forms Multiscreen](/xamarin/xamarin-forms/get-started/hello-xamarin-forms-multiscreen/)

<a name="solution" />

##  <a name="set-up-your-solution"></a>Çözümünüzü ayarlama

Visual Studio, .NET Standard kitaplığı paylaşımı yerel UI uygulamalar oluşturmaya yönelik bir çözüm şablonu yok. Ancak, tek tek projeler gibi bir çözüm oluşturmak zor değildir. Bu adımları her tür uygulama platformu projeleri ve paylaşılan kod için bir .NET Standard kitaplığı ile bir Xamarin çözümü oluşturun.

1.  Visual Studio'da yeni bir oluşturma **sınıf kitaplığı (.NET Standard)** çözüm ve adlandırın **WeatherApp**. Seçerek bu şablonu en bir kolayca bulabilirsiniz **Visual C#** sol ardından **.NET Standard**:

    ![.NET Standard çözümü oluşturma](../cross-platform/media/cross-plat-xamarin-build-2.png)

    Tamam'ı tıklattıktan sonra **WeatherApp** çözüm oluşur adlı tek bir projenin **WeatherApp**.

2.  Hedef iOS istiyorsanız, bir iOS projesi çözüme ekleyin. İçinde çözüm adına sağ tıklayın **Çözüm Gezgini** seçip **Ekle** ve **yeni proje**.  İçinde **yeni proje** iletişim kutusunda, sol Seç **Visual C#**, ardından **iOS** ve **Evrensel**. (Yoksa, olabilir Xamarin'i yükleyin veya Visual Studio 2017 özelliğini etkinleştirmek için bkz: [Kurulum ve yükleme](../cross-platform/setup-and-install.md).) Şablonlar listesinde seçin **tek görünüm uygulaması (iOS)**. Adlandırın **WeatherApp.iOS**.

3.  Android hedeflemek istiyorsanız, bir Android projesi çözüme ekleyin. İçinde **yeni proje** iletişim kutusunda, sol Seç **Visual C#** ve **Android**. Şablon listesinde **boş uygulama (Android)**. Adlandırın **WeatherApp.Android**.

4. Evrensel Windows platformu hedeflemek istiyorsanız **yeni proje** iletişim kutusunda, sol Seç **Visual C#** ve **Windows Evrensel**. Şablon listesinde **boş uygulama (Evrensel Windows)** ve adlandırın **WeatherApp.UWP**.

5. Her bir uygulama (iOS, Android ve UWP) projeleri sağ **başvuruları** konusundaki **Çözüm Gezgini** seçip **Başvuru Ekle**. İçinde **başvuru Yöneticisi** iletişim kutusunda, sol Seç **proje** ve **çözüm**. Başvuruları olduğunuz proje dışındaki bir çözümdeki tüm projeleri listesini görürsünüz:

   ![.NET Standard projesine bir başvuru ayarlama](../cross-platform/media/cross-plat-xamarin-build-3.png)

   Yanındaki onay kutusunu işaretleyin **WeatherApp**.

   Her uygulama projeleri için bu kutuyu denetledikten sonra tüm projeleri .NET Standard kitaplığı için başvurular ve kod bu Kitaplığı'nda paylaşabilirsiniz.

6. Ekleme **Newtonsoft.Json** , hava durumu verileri hizmetten alınan bilgi işlem için kullanacağınız .NET Standard projesine NuGet paketi:

    -   Sağ **WeatherApp** projesi **Çözüm Gezgini** seçip **NuGet paketlerini Yönet...** .

         NuGet penceresinde **Gözat** sekmesinde ve arama **Newtonsoft**.

    -   Seçin **Newtonsoft.Json**.

    -   Olun **sürüm** ayarlanmış **en son kararlı** sürümü.

    -   **Yükle**'ye tıklatın.

7.  Bulmak ve yüklemek için 6. adımı yineleyin **Microsoft.CSharp** .NET Standard projesi bir pakette. Bu kitaplık C# kullanmaya gerek `dynamic` .NET Standard Kitaplığı'nda veri türü.

8.  Çözümünüzü oluşturun ve herhangi bir yapı hatası olmadığını doğrulayın.

<a name="dataservice" />

## <a name="write-shared-data-service-code"></a>Paylaşılan veri hizmeti kod yazma

 **WeatherApp** .NET standart kitaplık projesidir. Burada tüm platformlar arasında paylaşılabilir kod yazacaksınız bu projesidir. Her uygulama projesi .NET Standard kitaplığı için bir başvuru bulunduğundan, iOS, Android ve UWP dahil kitaplıktır uygulama paketleri.

 Aşağıdaki adımlar, hava durumu hizmetinden veri depolamak ve erişmek için .NET Standard kitaplığı kodu ekleyin:

1.  İlk kaydolma bir ücretsiz hava durumu API anahtarı [ http://openweathermap.org/appid ](http://openweathermap.org/appid). Bu API anahtarı herhangi bir Amerika Birleşik Devletleri posta kodu için hava durumunu almak uygulama izin verir. (Bu birleşik Devletler'in dışında posta kodları için çalışmaz.)

2.  Sağ **WeatherApp** seçin ve proje **Ekle > sınıfı...** . İçinde **Yeni Öğe Ekle** iletişim kutusunda, dosya adı *Weather.cs*. Bu sınıf, hava durumu verileri hizmetten alınan verileri depolamak için kullanacaksınız.

3.  Tüm içeriğini değiştirin *Weather.cs* aşağıdaki kod ile:

    ```csharp
    namespace WeatherApp
    {
        public class Weather
        {
            // Because labels bind to these values, set them to an empty string to
            // ensure that the label appears on all platforms by default.
            public string Title { get; set; } = " ";
            public string Temperature { get; set; } = " ";
            public string Wind { get; set; } = " ";
            public string Humidity { get; set; } = " ";
            public string Visibility { get; set; } = " ";
            public string Sunrise { get; set; } = " ";
            public string Sunset { get; set; } = " ";
        }
    }
    ```

4.  .NET Standard projesine adlı başka bir sınıf ekleyin `DataService.cs`. Bu sınıf hava durumu verileri hizmetinden JSON verilerini işlemek için kullanacaksınız.

5.  Tüm içeriğini değiştirin *DataService.cs* aşağıdaki kod ile:

    ```csharp
    using System.Net.Http;
    using System.Threading.Tasks;
    using Newtonsoft.Json;

    namespace WeatherApp
    {
        public class DataService
        {
            public static async Task<dynamic> GetDataFromService(string queryString)
            {
                HttpClient client = new HttpClient();
                var response = await client.GetAsync(queryString);

                dynamic data = null;
                if (response != null)
                {
                    string json = response.Content.ReadAsStringAsync().Result;
                    data = JsonConvert.DeserializeObject(json);
                }

                return data;
            }
        }
    }
    ```

6.  Bir üçüncü sınıf adlı .NET standart kitaplığa eklemek *Core.cs*. Bu sınıf, bir posta kodu ile bir sorgu dizesi form, hava durumu verileri hizmeti çağırmak ve bir örneğini doldurmak için kullanacağınız **hava durumu** sınıfı.

7.  Öğesinin içeriğini değiştirin *Core.cs* aşağıdaki kod ile:

    ```csharp
    using System;
    using System.Threading.Tasks;

    namespace WeatherApp
    {
        public class Core
        {
            public static async Task<Weather> GetWeather(string zipCode)
            {
                //Sign up for a free API key at http://openweathermap.org/appid
                string key = "YOUR API KEY HERE";
                string queryString = "http://api.openweathermap.org/data/2.5/weather?zip="
                    + zipCode + ",us&appid=" + key + "&units=imperial";

                //Make sure developers running this sample replaced the API key
                if (key == "YOUR API KEY HERE")
                {
                    throw new ArgumentException("You must obtain an API key from openweathermap.org/appid and save it in the 'key' variable.");
                }

                dynamic results = await DataService.GetDataFromService(queryString).ConfigureAwait(false);

                if (results["weather"] != null)
                {
                    Weather weather = new Weather();
                    weather.Title = (string)results["name"];
                    weather.Temperature = (string)results["main"]["temp"] + " F";
                    weather.Wind = (string)results["wind"]["speed"] + " mph";
                    weather.Humidity = (string)results["main"]["humidity"] + " %";
                    weather.Visibility = (string)results["weather"][0]["main"];

                    DateTime time = new System.DateTime(1970, 1, 1, 0, 0, 0, 0);
                    DateTime sunrise = time.AddSeconds((double)results["sys"]["sunrise"]);
                    DateTime sunset = time.AddSeconds((double)results["sys"]["sunset"]);
                    weather.Sunrise = sunrise.ToString() + " UTC";
                    weather.Sunset = sunset.ToString() + " UTC";
                    return weather;
                }
                else
                {
                    return null;
                }
            }
        }
    }
    ```

8. İlk geçtiği değiştirme *burada bilgisayarınızı API anahtarı* 1. adımda elde ettiğiniz API anahtarına sahip. Yine, tırnak içine gerekiyor!

9. Silme *MyClass.cs* .NET Standard Kitaplığı'nda kullanılan olmaz.

10. Derleme **WeatherApp** kodu doğru olduğundan emin olmak için proje.

<a name="Android" />

## <a name="design-ui-for-android"></a>Android için kullanıcı Arabirimi tasarımı

 Artık kullanıcı arabirimi tasarlamanıza, paylaşılan kodunuza bağlayın ve sonra uygulamayı çalıştırın.

### <a name="design-the-look-and-feel-of-your-app"></a>Tasarım görünümü uygulama

1.  İçinde **Çözüm Gezgini**, genişletin **WeatherApp.Droid > kaynak > Düzen** klasörü ve açık *Main.axml*. Bu komut dosyası Görsel tasarımcıda açılır. (Java ile ilgili bir hata varsa, bkz. Bu [blog gönderisi](http://forums.xamarin.com/discussion/32365/connection-to-the-layout-renderer-failed-in-xs-5-7-and-xamarinvs-3-9).)

    > [!TIP]
    >  Projede diğer birçok dosyası vardır. Bunları keşfetmeye biraz daha fazla, bir Android projesi yapısına başlamak istiyorsanız ancak bu makalenin kapsamı dışında olup [2. Bölüm yakından](/xamarin/android/get-started/hello-android/hello-android-deepdive/) Hello Android makalenin.

2.  Araç kutusu açın **Görünüm > diğer Windows > Araç kutusu**.

3.  Gelen **araç kutusu**, sürükleyin bir **RelativeLayout** tasarımcıya denetim. Bu denetim, diğer denetimler için üst kapsayıcı olarak kullanacaksınız.

    > [!TIP]
    >  Herhangi bir zamanda düzenini düzgün görüntülenmesi yaramadı, dosyayı kaydedin ve arasında geçiş yapma **tasarım** ve **kaynak** yenilemek için sekmeler.

4.  İçinde **özellikleri** penceresinde **arka plan** (stil grubunda) özelliğine `#545454`.  Başlığa göre emin **özellikleri** arka planını tutunun penceresi **RelativeLayout**.

5.  Gelen **araç kutusu**, sürükleyin bir **TextView** denetimi **RelativeLayout** denetimi.

6.  İçinde **özellikleri** penceresinde bu özellikleri ayarlayın. (Bu listeyi alfabetik olarak sırala düğmesine Özellikler penceresi araç kullanarak sıralamak için yardımcı olabilir.):

    |Özellik|Değer|
    |--------------|-----------|
    |**Metin**|**Posta kodu göre ara**|
    |**id**|`@+id/ZipCodeSearchLabel`|
    |**layout_marginStart**|`10dp`|
    |**textColor**|`@android:color/white`|
    |**metin stili**|`bold`|

    > [!TIP]
    >  Pek çok özellik seçebileceğiniz değerler, aşağı açılan listesini içermeyen dikkat edin.  Belirli bir özellik için kullanılacak dize değeri tahmin etmek zor olabilir. Öneriler için bir özelliğin adını aramayı deneyin [ `R.attr` ](http://developer.android.com/reference/android/R.attr.html) sınıfı sayfası.
    >
    >  Ayrıca, hızlı web arama genellikle bir sayfaya müşteri adayları [ http://stackoverflow.com/ ](http://stackoverflow.com/) başkalarının kullanıldığı aynı özellik.

     Geçiş yaparsanız, başvuru için **kaynak** görünümü, bu öğe için şu kodu görürsünüz:

    ```xml
    <TextView
        android:text="Search by Zip Code"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/ZipCodeSearchLabel"
        android:layout_marginStart="10dp"
        android:textColor="@android:color/white"
        android:textStyle="bold" />

    ```

7.  Gelen **araç kutusu**, sürükleyin bir **TextView** denetimi **RelativeLayout** denetlemek ve ZipCodeSearchLabel denetimi yerleştirin. Yeni denetim varolan bir denetimi uygun kenarındaki aşağı açılır. Tasarımcıda biraz denetim konumuna yakınlaştırmak için yardımcı olur.

8. İçinde **özellikleri** penceresinde bu özellikleri ayarlayın:

    |Özellik|Değer|
    |--------------|-----------|
    |**Metin**|**Posta Kodu**|
    |**id**|`@+id/ZipCodeLabel`|
    |**layout_marginStart**|`10dp`|
    |**layout_marginTop**|`6dp`|
    |**textColor**|`@android:color/white`|

    İşte nasıl kodda **kaynak** görünüm aşağıdaki gibi görünür:

    ```xml
    <TextView
        android:text="Zip Code"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/ZipCodeSearchLabel"
        android:id="@+id/ZipCodeLabel"
        android:layout_marginStart="10dp"
        android:layout_marginTop="6dp"
        android:textColor="@android:color/white" />
    ```

9. Gelen **araç kutusu**, sürükleyin bir **numarası** denetimi **RelativeLayout**, aşağıdaki konumlandırın **posta kodu** etiketi. Ardından aşağıdaki özellikleri ayarlayın:

    |Özellik|Değer|
    |--------------|-----------|
    |**id**|`@+id/zipCodeEntry`|
    |**layout_marginStart**|`10dp`|
    |**layout_marginBottom**|`10dp`|
    |**Genişlik**|`165dp`|
    |**textColor**|`@android:color/white`|

    **Numarası** denetimi, kullanıcının bir beş basamaklı Amerika Birleşik Devletleri, posta kodu yazdığınız yerdir. Bu denetim için karşılık gelen biçimlendirmesi şöyledir:

    ```xml
    <EditText
        android:inputType="number"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/ZipCodeLabel"
        android:id="@+id/zipCodeEntry"
        android:layout_marginStart="10dp"
        android:layout_marginBottom="10dp"
        android:width="165dp"
        android:textColor="@android:color/white" />
    ```

10. Gelen **araç kutusu**, sürükleyin bir **düğmesi** üzerine **RelativeLayout** denetlemek ve zipCodeEntry denetimi sağa konumlandırın. Bu özellikleri ayarlayın:

    |Özellik|Değer|
    |--------------|-----------|
    |**id**|`@+id/weatherBtn`|
    |**Metin**|**Hava durumunu alın**|
    |**layout_marginStart**|`20dp`|
    |**layout_alignBottom**|`@id/zipCodeEntry`|
    |**Genişlik**|`165dp`|

    ```xml
    <Button
        android:text="Get Weather"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@id/zipCodeEntry"
        android:id="@+id/weatherBtn"
        android:layout_marginStart="20dp"
        android:layout_alignBottom="@id/zipCodeEntry"
        android:width="165dp" />
    ```

11. Artık Android designer kullanarak temel bir kullanıcı Arabirimi oluşturmak için yeterli biliyorsunuz. Biçimlendirme doğrudan ekleyerek bir kullanıcı Arabirimi oluşturabilirsiniz *Main.axml* sayfanın dosya. Rest kaynağı görünümü Tasarımcısı'nda şekilde geçiş kullanıcı arabirimi oluşturun ve ardından aşağıdaki biçimlendirme yapıştırın *altındaki* `</RelativeLayout>` bitiş etiketi. (Bu öğeler olduğundan etiketi altında olmalıdır *değil* bulunan `RelativeLayout`.)

    ```xml
    <TextView
        android:text="Location"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/locationLabel"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/locationText"
        android:layout_marginStart="20dp"
        android:layout_marginBottom="10dp" />
    <TextView
        android:text="Temperature"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/tempLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/tempText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    <TextView
        android:text="Wind Speed"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/windLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/windText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    <TextView
        android:text="Humidity"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/humidtyLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/humidityText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    <TextView
        android:text="Visibility"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/visibilityLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/visibilityText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    <TextView
        android:text="Time of Sunrise"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/sunriseLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/sunriseText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    <TextView
        android:text="Time of Sunset"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/sunsetLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/sunsetText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    ```

12. Dosyayı kaydedin ve geçiş **tasarım** görünümü. Kullanıcı Arabirimi aşağıdaki gibi görünmelidir:

     ![Android uygulaması için kullanıcı Arabirimi](../cross-platform/media/xamarin_androidui.png)

13. Açık **MainActivity.cs**. Kod nasıl görünmelidir aşağıda verilmiştir:

    ```csharp
    protected override void OnCreate (Bundle bundle)
    {
        base.OnCreate (bundle);

        // Set our view from the "main" layout resource
        SetContentView (Resource.Layout.Main);
    }
    ```

14. İş kontrol etmek için Android projesi oluşturun. Derleme işlemi denetimi kimlikleri ekler için *Resource.Designer.cs* kod ada göre denetimlere başvurabilmeniz için dosya.

### <a name="consume-your-shared-code"></a>Paylaşılan kod kullanma

1.  Açık *MainActivity.cs* dosya **WeatherApp** Kod Düzenleyicisi'nde proje ve içeriğini aşağıdaki kodla değiştirin. Bu kod `GetWeather` paylaşılan kodunuzda tanımlanan yöntemi. Ardından kullanıcı Arabiriminde uygulamanın Bu yöntemden alınan verileri gösterir.

    ```csharp
    using System;
    using Android.App;
    using Android.Widget;
    using Android.OS;

    namespace WeatherApp.Droid
    {
        [Activity(Label = "Sample Weather App",
                  Theme = "@android:style/Theme.Material.Light",
                  MainLauncher = true)]
        public class MainActivity : Activity
        {
            protected override void OnCreate(Bundle bundle)
            {
                base.OnCreate(bundle);

                SetContentView(Resource.Layout.Main);

                Button button = FindViewById<Button>(Resource.Id.weatherBtn);

                button.Click += Button_Click;
            }

            private async void Button_Click(object sender, EventArgs e)
            {
                EditText zipCodeEntry = FindViewById<EditText>(Resource.Id.zipCodeEntry);

                if (!String.IsNullOrEmpty(zipCodeEntry.Text))
                {
                    Weather weather = await Core.GetWeather(zipCodeEntry.Text);
                    FindViewById<TextView>(Resource.Id.locationText).Text = weather.Title;
                    FindViewById<TextView>(Resource.Id.tempText).Text = weather.Temperature;
                    FindViewById<TextView>(Resource.Id.windText).Text = weather.Wind;
                    FindViewById<TextView>(Resource.Id.visibilityText).Text = weather.Visibility;
                    FindViewById<TextView>(Resource.Id.humidityText).Text = weather.Humidity;
                    FindViewById<TextView>(Resource.Id.sunriseText).Text = weather.Sunrise;
                    FindViewById<TextView>(Resource.Id.sunsetText).Text = weather.Sunset;
                }
            }
        }
    }
    ```

    Etkinlik açık bir arka plan bilgileri için bir tema verildi dikkat edin.

### <a name="run-the-app-and-see-how-it-looks"></a>Uygulamayı çalıştırın ve nasıl göründüğüne bakın

1.  İçinde **Çözüm Gezgini**, emin **WeatherApp.Droid** projeyi başlangıç projesi olarak ayarlayın.

2.  Bir uygun cihaz veya öykünücü hedef seçin ve ardından F5 tuşuna basarak uygulamayı başlatın.

    > [!NOTE]
    > Visual Studio Android projesi Newtonsoft.Json dosyasını bulamıyor gösteriyorsa, bu NuGet paketi Android projesine ekleyin.

3.  Cihaz veya öykünücü, geçerli bir Amerika Birleşik Devletleri beş basamaklı posta kodu düzenleme kutusu ve tuşuna yazın **hava durumunu alın**. Bu bölge için hava durumu verileri, ardından denetimleri görünür.

    [![Xamarin Android uygulaması](../cross-platform/media/cross-plat-xamarin-build-1-android.png)](../cross-platform/media/cross-plat-xamarin-build-1-android-Large.png#lightbox)

> [!TIP]
>  Bu proje için tam kaynak kodu [github'daki mobil-samples deposuna](https://github.com/xamarin/mobile-samples/tree/master/Weather).

<a name="Windows" />

## <a name="design-ui-for-windows"></a>Windows için kullanıcı Arabirimi tasarımı

Sonraki adım, ardından uygulamayı çalıştırmak için Windows kullanıcı arabirimini tasarlayabileceğiniz ve paylaşılan kodunuza bağlayın sağlamaktır.

### <a name="design-the-look-and-feel-of-your-app"></a>Tasarım görünümü uygulama

 Bir yerel UWP kullanıcı arabiriminin bir Xamarin uygulaması tasarlama işlemi herhangi diğer yerel UWP uygulamasından farklı değildir. Bu nedenle, tasarımcının kullanım burada tartışılan olmaz. Ayrıntılı bilgi için bkz [XAML Tasarımcısını kullanarak kullanıcı Arabirimi oluşturma](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).

 Bunun yerine açık *MainPage.xaml* ve tüm XAML içeriğini aşağıdaki biçimlendirme ile değiştirin:

```xaml
<Page
    x:Class="WeatherApp.UWP.MainPage"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:WeatherApp.UWP"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    mc:Ignorable="d">

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">

        <StackPanel HorizontalAlignment="Left"
                    VerticalAlignment="Top"
                    Height="40" Margin="10,0,0,0" Width="400">
            <TextBlock Text="Weather App" FontSize="30" />
        </StackPanel>
        <StackPanel HorizontalAlignment="Left"
                    VerticalAlignment="Top"
                    Height="120" Margin="10,40,0,0" Width="400"
                    Background="#FF545454">

            <TextBlock Text="Search by Zip Code" TextWrapping="Wrap"
                       HorizontalAlignment="Left" Margin="10,10,0,0"
                       Foreground="White" FontSize="18" FontWeight="Bold" />

            <TextBlock Text="Zip Code" TextWrapping="Wrap"
                       Margin="10,5,0,0" FontSize="14" Foreground="#FFA8A8A8"/>

            <StackPanel Orientation="Horizontal">

                <TextBox x:Name="zipCodeEntry" Text=""
                         Margin="10,10,0,0" VerticalAlignment="Top"
                         InputScope="Number" Width="165" />

                <Button x:Name="weatherBtn" Content="Get Weather"
                        Foreground="White" Width="165" Margin="20,0,0,0" Height="60"
                        Click="GetWeatherButton_Click"/>
            </StackPanel>
        </StackPanel>

        <StackPanel Margin="10,175,0,0">
            <StackPanel.Resources>
                <Style x:Key="commonText" TargetType="TextBlock">
                    <Setter Property="HorizontalAlignment" Value="Left" />
                    <Setter Property="VerticalAlignment" Value="Top" />
                    <Setter Property="TextWrapping" Value="Wrap" />
                </Style>

                <Style x:Key="labelText" TargetType="TextBlock" BasedOn="{StaticResource commonText}">
                    <Setter Property="FontSize" Value="14" />
                    <Setter Property="Foreground" Value="#FFA8A8A8" />
                </Style>

                <Style x:Key="valueText" TargetType="TextBlock" BasedOn="{StaticResource commonText}">
                    <Setter Property="FontSize" Value="18" />
                    <Setter Property="Margin" Value="10, 0, 0, 10" />
                </Style>
            </StackPanel.Resources>

            <TextBlock Text="Location" Style="{StaticResource labelText}" />
            <TextBlock x:Name="locationText" Style="{StaticResource valueText}" />

            <TextBlock Text="Temperature" Style="{StaticResource labelText}" />
            <TextBlock x:Name="tempText" Style="{StaticResource valueText}" />

            <TextBlock Text="Wind Speed" Style="{StaticResource labelText}" />
            <TextBlock x:Name="windText" Style="{StaticResource valueText}" />

            <TextBlock Text="Humidity" Style="{StaticResource labelText}" />
            <TextBlock x:Name="humidityText" Style="{StaticResource valueText}" />

            <TextBlock Text="Temperature" Style="{StaticResource labelText}" />
            <TextBlock x:Name="visibilityText" Style="{StaticResource valueText}" />

            <TextBlock Text="Time of Sunrise" Style="{StaticResource labelText}" />
            <TextBlock x:Name="sunriseText" Style="{StaticResource valueText}" />

            <TextBlock Text="Time of Sunset" Style="{StaticResource labelText}" />
            <TextBlock x:Name="sunsetText" Style="{StaticResource valueText}" />
        </StackPanel>
    </Grid>
</Page>
```

### <a name="consume-your-shared-code"></a>Paylaşılan kod kullanma

İçinde *MainPage.xaml.cs* arka plan kod dosyası, düğme için aşağıdaki olay işleyicisini ekleyin:

```csharp
private async void GetWeatherButton_Click(object sender, RoutedEventArgs e)
{
    if (!String.IsNullOrEmpty(zipCodeEntry.Text))
    {
        Weather weather = await Core.GetWeather(zipCodeEntry.Text);
        locationText.Text = weather.Title;
        tempText.Text = weather.Temperature;
        windText.Text = weather.Wind;
        visibilityText.Text = weather.Visibility;
        humidityText.Text = weather.Humidity;
        sunriseText.Text = weather.Sunrise;
        sunsetText.Text = weather.Sunset;

        weatherBtn.Content = "Search Again";
    }
}
```

Bu kod `GetWeather` paylaşılan kodunuzda tanımlanan yöntemi. `GetWeather` Android uygulamanızda çağrılan yöntem ile aynıdır. Bu kod Ayrıca, uygulamanızın kullanıcı Arabirimi denetimleri yönteminde alınan verileri gösterir.

### <a name="run-the-app-and-see-how-it-looks"></a>Uygulamayı çalıştırın ve nasıl göründüğüne bakın

1.  İçinde **Çözüm Gezgini**ayarlayın **WeatherApp.UWP** projeyi başlangıç projesi olarak.

2.  İçinde **çözüm platformları** açılır kutusunda, select **x86** seçip **yerel makine** Windows 10 Masaüstü uygulamasını dağıtmak için.

3.  Tuşlarına basarak uygulamayı başlatın **F5** anahtarı.

4.  Geçerli bir beş basamaklı Amerika Birleşik Devletleri posta kodu düzenleme kutusu ve tuşuna yazın **hava durumunu alın**. Bu bölge için hava durumu verileri daha sonra sayfada görüntülenir.

    [![UWP üzerinde bir Xamarin uygulaması](../cross-platform/media/cross-plat-xamarin-build-1-uwp.png)](../cross-platform/media/cross-plat-xamarin-build-1-uwp-Large.png#lightbox)

> [!TIP]
>  Bu proje için tam kaynak kodu [github'daki mobil-samples deposuna](https://github.com/xamarin/mobile-samples/tree/master/Weather).

<a name="next" />

## <a name="next-steps"></a>Sonraki adımlar

 **Kullanıcı Arabirimi, iOS için çözüme ekleyin.**

 Bu örnek, iOS için yerel UI ekleyerek genişletin. İos'ta kodu test etmek için yerel ağınızda Xcode sahip bir Mac bağlamanız gerekecektir ve Xamarin yüklü. Bunu yaptığınızda, doğrudan Visual Studio'da iOS Tasarımcısı'nı kullanabilirsiniz. Bkz: [github'daki mobil-samples deposuna](https://github.com/xamarin/mobile-samples/tree/master/Weather) tamamlanan uygulama için.

 Ayrıca bkz [Hello, iOS](/xamarin/ios/get-started/hello-ios/hello-ios-quickstart?tabs=vswin) gözden geçirme.

 **Paylaşılan projede platforma özgü kod ekleyin**

 Paylaşılan bir .NET Standard Kitaplığı'nda platform nötr kodudur. Kitaplıkta bir kez derlenmiş ve her platforma özgü uygulama paketine dahil. Koşullu derleme platforma özgü kod yalıtmak için kullandığı paylaşılan kod yazmak istiyorsanız, kullanabileceğiniz bir *paylaşılan* proje. Daha fazla bilgi için [kod paylaşma seçenekleri](/xamarin/cross-platform/app-fundamentals/building-cross-platform-applications/practical-code-sharing-strategies).

## <a name="see-also"></a>Ayrıca bkz.

- [Xamarin belgeleri](http://docs.microsoft.com/xamarin)
- [Windows Geliştirme Merkezi](https://dev.windows.com/en-us)
- [Swift ve C# hızlı başvuru posteri](http://aka.ms/scposter)
