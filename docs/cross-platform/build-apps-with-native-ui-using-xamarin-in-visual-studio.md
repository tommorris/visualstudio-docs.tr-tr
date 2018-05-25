---
title: Xamarin Visual Studio kullanarak yerel kullanıcı Arabirimi ile uygulamalar oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 30f137e6-595d-4ce7-b8f5-415b07c1caa2
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 67d8b2147426a048f2af92b0525fd6c8139b4558
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/24/2018
---
# <a name="build-apps-with-native-ui-using-xamarin-in-visual-studio"></a>Xamarin Visual Studio kullanarak yerel kullanıcı Arabirimi ile uygulamalar oluşturma

Platformlar arası mobil uygulamaları yazmak için Xamarin, C# seçen Çoğu geliştirici Xamarin.Forms kullanın. Xamarin.Forms iOS, Android ve evrensel Windows Platformu (UWP) yerel denetimlerinde eşleyen bir kullanıcı arabirimi tanımlar. Xamarin.Forms makalesinde açıklanan [Xamarin.Forms Visual Studio ile uygulama oluşturma temellerini öğrenin](learn-app-building-basics-with-xamarin-forms-in-visual-studio.md).

Bu makalede, yerel kullanıcı arabirimi API'leri her platform için erişimi içeren farklı bir yaklaşım açıklanmaktadır. Her platform için kapsamlı bilgi gerektirdiğinden yerel API'leri ile çalışma bir çok daha zor Xamarin.Forms daha yaklaşımdır. Avantajı, temel alınan iş mantığı hala paylaşırken belirli güçlü ve yetenekleri her platform için kullanıcı arabirimi uyarlayabileceğiniz olmasıdır.

Adımları yaptıktan sonra [Kurulum ve yükleme](../cross-platform/setup-and-install.md) ve [Xamarin ortamınızı doğrulayın](../cross-platform/verify-your-xamarin-environment.md), bu kılavuzda yerel UI katmanlar ile temel bir Xamarin uygulamasının nasıl oluşturulacağını gösterir. Yerel kullanıcı Arabirimi ile bir .NET standart kitaplığında paylaşılan kod bulunur ve tek tek platform projeleri UI tanımları içerir. (Soldan sağa) üzerinde çalışan oluşturacağınız uygulama İşte iOS ve Android telefonlar ve Windows 10 Masaüstü.
  
[![İOS, Android ve Windows Xamarin uygulaması](../cross-platform/media/cross-plat-xamarin-build-1.png "arası Plat Xamarin derleme 1")](../cross-platform/media/cross-plat-xamarin-build-1-Large.png#lightbox)
  
Bu derleme için bunlardan gerçekleştirirsiniz:  
  
- [Çözümünüzü ayarlarken ayarlayın](#solution)  
  
- [Paylaşılan veri hizmeti kod yazma](#dataservice)  
  
- [Android için kullanıcı Arabirimi tasarımı](#Android)  

- [Windows için kullanıcı Arabirimi tasarımı](#Windows)  
  
- [Sonraki adımlar](#next), aşağıdakileri içeren bir iOS kullanıcı arabirimini tasarlama
  
> [!TIP]
> Bu proje için tam kaynak kodunu bulabilirsiniz [mobil-samples deposu github'da](https://github.com/xamarin/mobile-samples/tree/master/Weather).
>
> Sorunlar varsa veya hatalarla karşılaşırsanız lütfen üzerinde sorularınızı [forums.xamarin.com](http://forums.xamarin.com). Birçok hata açıklanan olan son SDK Xamarin tarafından gerekli güncelleştirerek çözülebilir [Xamarin sürüm notları](https://developer.xamarin.com/releases/) her platform için.    
  
> [!NOTE]
> Xamarin'ın Geliştirici belgeleri de aşağıda listelenen Quickstart ve derin Dalış bölümleri ile birkaç izlenecek yollar sunar. Tüm bu sayfalarda "Visual Studio" izlenecek yollar için Visual Studio belirli görmek için seçildiğinden emin olun.  
>   
>  -   Xamarin uygulamaları yerel kullanıcı Arabirimi ile:  
>     -   [Merhaba, Android](/xamarin/android/get-started/hello-android/) (bir ekrana sahip basit uygulama)  
>     -   [Merhaba, Android multiscreen](/xamarin/android/get-started/hello-android-multiscreen/) (ekranları arasında gezinmeyi uygulamayla)  
>     -   [Android parçaları izlenecek](/xamarin/android/platform/fragments/fragments/implementing-with-fragments/walkthrough/) (ana/ayrıntı ekranda, başka şeylerin için kullanılır)  
>     -   [Hello, iOS](/xamarin/ios/get-started/hello-iOS/)  
>     -   [Çok Ekranlı Hello, iOS ](/xamarin/ios/get-started/hello-iOS-multiscreen/) 

>  -   Xamarin.Forms (paylaşılan UI) ile Xamarin uygulamaları  
>     -   [Hello, Xamarin.Forms](/xamarin/xamarin-forms/get-started/hello-xamarin-forms/quickstart/)  
>     -   [Hello, Xamarin.Forms Multiscreen](/xamarin/xamarin-forms/get-started/hello-xamarin-forms-multiscreen/)  
  
<a name="solution" />

##  <a name="set-up-your-solution"></a>Çözümünüzü ayarlarken ayarlayın  

Visual Studio .NET standart bir kitaplık paylaşımı yerel UI uygulamaları oluşturmak için bir çözüm şablonu yok. Ancak, bu tür bir çözümü ayrı ayrı projelerden oluşturmak sabit değil. Bu adımları projeleri her tür uygulama platformu ve .NET standart kitaplığı paylaşılan kodu için bir Xamarin çözümü oluşturun.  
  
1.  Visual Studio'da yeni bir oluşturma **sınıf kitaplığı (.NET standart)** çözüm ve adlandırın **WeatherApp**. Bu şablon en kolay seçerek bulabileceğiniz **Visual C#** sol ve ardından **.NET standart**: 

    ![.NET standart çözüm oluşturma](../cross-platform/media/cross-plat-xamarin-build-2.png "platformlar arası Xamarin derleme 2")

    Tamam'ı tıklattıktan sonra **WeatherApp** çözüm oluşur adlı tek bir projenin **WeatherApp**. 

2.  Hedef iOS istiyorsanız, bir iOS projesi çözüme ekleyin. Çözüm adı sağ **Çözüm Gezgini** seçip **Ekle** ve **yeni proje**.  İçinde **yeni proje** iletişim kutusunda, sol seçin **Visual C#** ve ardından **iOS** ve **Evrensel**. (Yoksa, olabilir Xamarin yükleyin veya Visual Studio 2017 özelliğini etkinleştirmek için bkz: [Kurulum ve yükleme](../cross-platform/setup-and-install.md).) Şablonları listesinde seçin **Single View uygulaması (iOS)**. Bu ad **WeatherApp.iOS**.

3.  Android hedeflemek istiyorsanız, bir Android projesi çözüme ekleyin. İçinde **yeni proje** iletişim kutusunda, sol seçin **Visual C#** ve **Android**. Şablonu listeden seçin **boş uygulama (Android)**. Bu ad **WeatherApp.Android**. 

4. Evrensel Windows platformu de hedeflemek istiyorsanız **yeni proje** iletişim kutusunda, sol seçin **Visual C#** ve **Windows Evrensel**. Şablonu listeden seçin **boş uygulama (Evrensel Windows)** ve adlandırın **WeatherApp.UWP**.
  
5. Her bir uygulama için projeleri (iOS, Android ve UWP) sağ **başvuruları** bölümüne **Çözüm Gezgini** seçip **Başvuru Ekle**. İçinde **başvuru Yöneticisi** iletişim kutusunda, sol seçin **proje** ve **çözüm**. Başvuruları yönetme proje dışında Çözümdeki tüm projeleri listesini görürsünüz:

   ![.NET standart projesine bir başvuru ayarlama](../cross-platform/media/cross-plat-xamarin-build-3.png "platformlar arası Xamarin derleme 3")

   Yanındaki onay kutusunu işaretleyin **WeatherApp**. 

   Her uygulama projeleri için bu kutuyu denetlediyseniz sonra tüm projeleri .NET standart kitaplığına başvurular içeriyor ve bu Kitaplığı'nda kod paylaşabilirsiniz.
  
6. Ekleme **Newtonsoft.Json** hava veri hizmetinden alınan bilgileri işlemek için kullanacağınız .NET standart proje için NuGet paketi:  
  
    -   Sağ **WeatherApp** proje **Çözüm Gezgini** seçip **NuGet paketlerini Yönet...** .  
  
         NuGet penceresinde seçin **Gözat** sekmesinde ve arama **Newtonsoft**.  
  
    -   Seçin **Newtonsoft.Json**.  
  
    -   Olun **sürüm** alan ayarlanmış **en son kararlı** sürümü.  
  
    -   **Yükle**'ye tıklatın.  
  
7.  Yineleme adım bulmak ve yüklemek için 6 **Microsoft.CSharp** .NET standart proje paketinde. C# kullanmak bu kitaplığı gereklidir `dynamic` .NET standart Kitaplığı'nda veri türü.
  
8.  Çözümünüzü derlemek ve hiçbir derleme hataları olduğunu doğrulayın.  
  
<a name="dataservice" />

## <a name="write-shared-data-service-code"></a>Paylaşılan veri hizmeti kod yazma  

 **WeatherApp** projedir .NET standart kitaplığı. Burada tüm platformlarda paylaşılan kod yazacaksınız bu projesidir. Her uygulama projesi .NET standart kitaplığına bir başvuru olduğundan, iOS, Android ve UWP dahil kitaplığıdır uygulama paketleri.  
  
 Aşağıdaki adımlar, hava durumu hizmetinden veri depolamak ve erişmek için .NET standart kitaplığı kodu ekleyin:  
  
1.  İlk için kaydolun bir ücretsiz hava durumu API anahtarda [ http://openweathermap.org/appid ](http://openweathermap.org/appid). Bu API anahtarı, Amerika Birleşik Devletleri zip kod hava almak uygulama izin verir. (Bunu Amerika Birleşik Devletleri dışında posta kodlarının çalışmaz.)
  
2.  Sağ **WeatherApp** proje ve seçin **Ekle > sınıfı...** . İçinde **Yeni Öğe Ekle** iletişim kutusunda, dosya adı **Weather.cs**. Bu sınıf, hava durumu veri hizmetinden veri depolamak için kullanacaksınız.  
  
3.  Tüm içeriğini değiştirin **Weather.cs** aşağıdaki kod ile:  
  
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
  
4.  Başka bir sınıf adlı .NET standart projeye ekleyin **DataService.cs**. Bu sınıf hava durumu veri hizmetinden JSON veri işlemek için kullanacaksınız.  
  
5.  Tüm içeriğini değiştirin **DataService.cs** aşağıdaki kod ile:  
  
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
  
6.  Bir üçüncü sınıf adlı .NET standart kitaplığına ekleyin **Core.cs**. Bu sınıf posta koduyla bir sorgu dizesi form, hava durumu veri hizmeti çağırmak ve bir örneğini doldurmak için kullanacağınız **hava durumu** sınıfı.  
  
7.  Değiştir **Core.cs** aşağıdaki kod ile:  
  
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
  
8. İlk örneğini değiştirmek *burada bilgisayarınızı API anahtarı* 1. adımda elde ettiğiniz API anahtarı ile. Hala, etrafına tırnak işareti gerekiyor!
  
9. Silme **MyClass.cs** .NET standart Kitaplığı'nda çünkü kullanılıyor olmaz.  
  
10. Yapı **WeatherApp** proje kodunun doğru olduğundan emin olun.  
  
<a name="Android" />

## <a name="design-ui-for-android"></a>Android için kullanıcı Arabirimi tasarımı  

 Artık kullanıcı arabirimini tasarlamak, paylaşılan kodunuzu bağlanmak ve uygulamayı çalıştırın.  
  
### <a name="design-the-look-and-feel-of-your-app"></a>Uygulamanızı Görünüm ve yapısını tasarlama  
  
1.  İçinde **Çözüm Gezgini**, genişletin **WeatherApp.Droid > kaynak > düzeni** klasörü ve açık **Main.axml**. Bu komut dosyasını visual Tasarımcısı'nda açar. (Java ilgili bir hata varsa, bu bkz [blog gönderisi](http://forums.xamarin.com/discussion/32365/connection-to-the-layout-renderer-failed-in-xs-5-7-and-xamarinvs-3-9).)  
  
    > [!TIP]
    >  Projede diğer birçok dosyası yok. Bunları keşfetme ancak biraz daha bir Android projesi yapısına başlamak isterseniz, bu makalenin kapsamı dışında olup [bölümü 2 derinlemesine](/xamarin/android/get-started/hello-android/hello-android-deepdive/) Hello Android makalenin.  
  
2.  Araç kutusu açın **Görünüm > Diğer Pencereler > Araç**.  
  
3.  Gelen **araç**, sürükleyin bir **RelativeLayout** tasarımcıya denetim. Bu denetim, diğer denetimler için üst kapsayıcı olarak kullanacaksınız.  
  
    > [!TIP]
    >  Herhangi bir zamanda doğru görüntülenemeyecek kadar düzeni görünmemektedir, dosyayı kaydedin ve arasında geçiş yapma **tasarım** ve **kaynak** sekmeleri yenileyin.  
  
4.  İçinde **özellikleri** penceresindeki ayarlayın **arka plan** (stil grubunda) özelliğine `#545454`.  Başlıkta tarafından emin olun **özellikleri** arka planını ayarlama penceresi **RelativeLayout**.
  
5.  Gelen **araç**, sürükleyin bir **kutusu TextView** üzerine kontrol **RelativeLayout** denetim.  
  
6.  İçinde **özellikleri** penceresinde, bu özellikleri ayarlayın. (Bunu alfabetik sıralama düğmesini Özellikler penceresi araç çubuğunda kullanarak sıralamak için yardımcı olabilir.):  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Metin**|**Posta kodu göre ara**|  
    |**id**|`@+id/ZipCodeSearchLabel`|  
    |**layout_marginStart**|`10dp`|  
    |**textColor**|`@android:color/white`|  
    |**metin stili**|`bold`|  
  
    > [!TIP]
    >  Pek çok özellik seçebileceğiniz değerler açılan listesini içermeyen dikkat edin.  Belirli bir özellik için kullanılacak dize değeri tahmin etmesi zor olabilir. Bir özelliğin adını arama önerileri için deneyin [R.attr](http://developer.android.com/reference/android/R.attr.html) sınıfı sayfası.  
    >   
    >  Ayrıca, hızlı web araması genellikle bir sayfaya müşteri adayları [ http://stackoverflow.com/ ](http://stackoverflow.com/) başkalarının kullanıldığı aynı özelliği.  
  
     Geçiş yaparsanız, başvuru için **kaynak** görünümü, bu öğe için aşağıdaki kodu görmeniz gerekir:  
  
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
  
7.  Gelen **araç**, sürükleyin bir **kutusu TextView** üzerine kontrol **RelativeLayout** denetlemek ve ZipCodeSearchLabel denetim yerleştir. Yeni Denetim kontrolü uygun kenarında bırakın. Tasarımcıda biraz denetim konumlandırmak için yakınlaştırma yardımcı olabilir.  
  
8. İçinde **özellikleri** penceresinde, bu özellikleri ayarlayın:  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Metin**|**Posta Kodu**|  
    |**id**|`@+id/ZipCodeLabel`|  
    |**layout_marginStart**|`10dp`|  
    |**layout_marginTop**|`6dp`|  
    |**textColor**|`@android:color/white`|  
  
    İşte nasıl kodda **kaynak** görünüm görünmelidir:  
  
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
  
9. Gelen **araç**, sürükleyin bir **numarası** üzerine kontrol **RelativeLayout**, aşağıdaki getirin **posta kodu** etiketi. Ardından aşağıdaki özellikleri ayarlayın:  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**id**|`@+id/zipCodeEntry`|  
    |**layout_marginStart**|`10dp`|  
    |**layout_marginBottom**|`10dp`|  
    |**Genişlik**|`165dp`|  
    |**textColor**|`@android:color/white`|  
  
    **Numarası** denetimidir kullanıcı beş basamaklı Amerika Birleşik Devletleri zip kodda girildiği. Bu denetim için karşılık gelen biçimlendirme aşağıdaki gibidir:  
  
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
  
10. Gelen **araç**, sürükleyin bir **düğmesini** üzerine **RelativeLayout** denetlemek ve zipCodeEntry denetim sağına yerleştir. Bu özellikleri ayarlayın:  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**id**|`@+id/weatherBtn`|  
    |**Metin**|**Hava durumu Al**|  
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
  
11. Şimdi Android Tasarımcısını kullanarak temel bir kullanıcı Arabirimi oluşturmak için yeterli bildiğiniz. Bir kullanıcı Arabirimi sayfası Main.axml dosyayı doğrudan biçimlendirme ekleyerek de oluşturabilirsiniz. Kalan kaynağı görünümü Tasarımcısı'nda şekilde geçmek UI yapı, ardından aşağıdaki biçimlendirme Yapıştır *altındaki* `</RelativeLayout>` bitiş etiketi. (Bu öğeleri olduğundan etiketi altında olmalıdır *değil* içinde yer alan `RelativeLayout`.)  
  
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
  
12. Dosyayı kaydedin ve geçiş **tasarım** görünümü. UI aşağıdaki gibi görünmelidir:  
  
     ![Android için kullanıcı Arabirimi](../cross-platform/media/xamarin_androidui.png "Xamarin_AndroidUI")  
  
13. Açık **MainActivity.cs**. İşte kodu nasıl görünmelidir:  
  
    ```  
    protected override void OnCreate (Bundle bundle)  
    {  
        base.OnCreate (bundle);  
  
        // Set our view from the "main" layout resource  
        SetContentView (Resource.Layout.Main);  
    }  
    ```  
  
14. Çalışmanızı iade etme için Android projesi oluşturun. Derleme işlemi Denetim kimliklerinin ekler için **Resource.Designer.cs** kod ada göre denetimlere başvurabilmeniz için dosya.  
  
### <a name="consume-your-shared-code"></a>Paylaşılan kodunuzu kullanma  
  
1.  Açık **MainActivity.cs** dosyasının **WeatherApp** proje Kod Düzenleyicisi'nde ve içeriğini aşağıdaki kodla değiştirin. Bu kod çağırır `GetWeather` paylaşılan kodunuzda tanımlanan yöntemi. Daha sonra kullanıcı Arabiriminde uygulamanın o yönteminden alınan verileri gösterir.  
  
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

    Etkinlik için açık bir arka plan tema verilmiş dikkat edin.
  
### <a name="run-the-app-and-see-how-it-looks"></a>Uygulamayı çalıştırın ve nasıl göründüğünü görmek  
  
1.  İçinde **Çözüm Gezgini**, emin olun **WeatherApp.Droid** projesi başlangıç projesi olarak ayarla.  
  
2.  Bir cihaz veya öykünücü hedef seçin ve ardından F5 tuşuna basarak uygulamayı başlatın.  

    > [!NOTE]
    > Visual Studio Android projesi Newtonsoft.Json dosyası bulunamıyor gösteriyorsa, bu NuGet paketi Android projeye ekleyin. 
  
3.  Cihaz veya öykünücü, Amerika Birleşik Devletleri beş basamaklı bir geçerli ZIP kodu düzenleme kutusu ve tuşuna yazın **alma hava durumu**. Bu bölge için hava durumu verileri, ardından denetimlerinde görüntülenir.  
  
    [![Xamarin Android uygulamasını](../cross-platform/media/cross-plat-xamarin-build-1-android.png "arası Plat Xamarin derleme 1 Android")](../cross-platform/media/cross-plat-xamarin-build-1-android-Large.png#lightbox)  
  
> [!TIP]
>  Bu proje için tam kaynak kodu [mobil-samples deposu github'da](https://github.com/xamarin/mobile-samples/tree/master/Weather).  
  
<a name="Windows" /> 

## <a name="design-ui-for-windows"></a>Windows için kullanıcı Arabirimi tasarımı

Windows için kullanıcı arabirimi tasarlama, paylaşılan kodunuzu bağlanmak ve ardından uygulamayı çalıştırmak için sonraki adım olacaktır.  
  
### <a name="design-the-look-and-feel-of-your-app"></a>Uygulamanızı Görünüm ve yapısını tasarlama  

 Xamarin uygulaması yerel bir UWP kullanıcı arabiriminde tasarlama işlemi herhangi diğer yerel UWP uygulamasını farklı değildir. Bu nedenle, Tasarımcı kullanımı burada tartışılan olmaz. Ayrıntılı bilgi için bkz [XAML Tasarımcısını kullanarak bir kullanıcı Arabirimi oluşturma](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).  
  
 Bunun yerine, açın **MainPage.xaml** ve tüm XAML içeriği aşağıdaki biçimlendirme ile değiştirin:   
  
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
  
### <a name="consume-your-shared-code"></a>Paylaşılan kodunuzu kullanma  
  
İçinde **MainPage.xaml.cs** arka plan kod dosyası, düğme için aşağıdaki olay işleyicisini ekleyin: 
  
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
  
Bu kod çağırır `GetWeather` paylaşılan kodunuzda tanımlanan yöntemi. `GetWeather` Android uygulamanızda çağrılan yöntem ile aynıdır. Bu kod Ayrıca, uygulamanızın UI denetimlerinde yöntemin alınan verileri gösterir.  
  
### <a name="run-the-app-and-see-how-it-looks"></a>Uygulamayı çalıştırın ve nasıl göründüğünü görmek  
  
1.  İçinde **Çözüm Gezgini**ayarlayın **WeatherApp.UWP** projesini başlangıç projesi olarak.  

2.  İçinde **çözüm platformları** açılır kutusunda **x86** seçip **yerel makine** Windows 10 Masaüstü uygulamasını dağıtmak için.
  
3.  F5 tuşuna basarak uygulamayı başlatın.  
  
4.  Geçerli bir beş basamaklı Amerika Birleşik Devletleri zip kod düzenleme kutusu ve tuşuna yazın **alma hava durumu**. Bu bölge için hava durumu veri sonra sayfada görüntülenir.  

    [![Xamarin uygulaması UWP üzerinde](../cross-platform/media/cross-plat-xamarin-build-1-uwp.png "arası Plat Xamarin derleme 1 UWP")](../cross-platform/media/cross-plat-xamarin-build-1-uwp-Large.png#lightbox)  

> [!TIP]
>  Bu proje için tam kaynak kodu [mobil-samples deposu github'da](https://github.com/xamarin/mobile-samples/tree/master/Weather).  

<a name="next" /> 

## <a name="next-steps"></a>Sonraki adımlar  

 **UI iOS için çözüme ekleyin.**  
  
 Bu örnek, iOS için yerel kullanıcı Arabirimi ekleyerek genişletebilir. İOS kodu test etmek için bir Mac Xcode sahip yerel ağınızdaki bağlamanız gerekecektir ve Xamarin yüklü. Bunu gerçekleştirdikten sonra doğrudan Visual Studio'da iOS Tasarımcısı'nı kullanabilirsiniz. Bkz: [mobil-samples deposu github'da](https://github.com/xamarin/mobile-samples/tree/master/Weather) tamamlanan uygulama için.  
  
 Ayrıca bkz [Hello, iOS](/xamarin/ios/get-started/hello-ios/hello-ios-quickstart?tabs=vswin) gözden geçirme.   
  
 **Platforma özgü kodu paylaşılan bir proje ekleyin**  
  
 Paylaşılan bir .NET standart kitaplığında platformdan bağımsız kodudur. Kitaplık kez derlenmiş ve her platforma özgü uygulama paketinde. Koşullu derleme platforma özgü kodu yalıtmak için kullandığı paylaşılan kod yazmak istiyorsanız, kullanabileceğiniz bir *paylaşılan* projesi. Daha fazla bilgi için bkz: [kodu paylaşım seçeneklerini](/xamarin/cross-platform/app-fundamentals/building-cross-platform-applications/practical-code-sharing-strategies).  
  
## <a name="see-also"></a>Ayrıca Bkz.  

 [Xamarin belgeleri](http://docs.microsoft.com/xamarin)   
 [Windows Geliştirici Merkezi](https://dev.windows.com/en-us)   
 [SWIFT ve C# hızlı başvuru posteri](http://aka.ms/scposter)
