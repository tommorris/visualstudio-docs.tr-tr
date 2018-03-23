---
title: Xamarin Visual Studio kullanarak yerel kullanıcı Arabirimi ile uygulamalar oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: vs-ide-mobile
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30f137e6-595d-4ce7-b8f5-415b07c1caa2
caps.latest.revision: ''
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 71004088d421bcc2e0809fc4004cd7af887b95af
ms.sourcegitcommit: fb1fede41d8c5e459dd222755b0497b9d361bc51
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="build-apps-with-native-ui-using-xamarin-in-visual-studio"></a>Xamarin Visual Studio kullanarak yerel kullanıcı Arabirimi ile uygulamalar oluşturma
Adımları yaptıktan sonra [Kurulum ve yükleme](../cross-platform/setup-and-install.md) ve [Xamarin ortamınızı doğrulayın](../cross-platform/verify-your-xamarin-environment.md), bu kılavuzda (aşağıda yerel UI Katmanlar gösterilmiştir) temel bir Xamarin uygulamasının nasıl oluşturulacağını gösterir. Yerel kullanıcı Arabirimi ile taşınabilir sınıf kitaplığı (PCL) paylaşılan kod bulunur ve tek tek platform projeleri UI tanımları içerir.  
  
 ![Android ve Windows Phone Xamarin uygulaması](../cross-platform/media/cross-plat-xamarin-build-1.png "arası Plat Xamarin derleme 1")  
  
 Bu derleme için bunlardan gerçekleştirirsiniz:  
  
-   [Çözümünüzü ayarlarken ayarlayın](#solution)  
  
-   [Paylaşılan veri hizmeti kod yazma](#dataservice)  
  
-   [Android için kullanıcı Arabirimi tasarımı](#Android)  
  
-   [Windows Phone için kullanıcı Arabirimi tasarımı](#Windows)  
  
-   [Sonraki adımlar](#next)  
  
> [!TIP]
>  Bu proje için tam kaynak kodunu bulabilirsiniz [mobil-samples deposu github'da](https://github.com/xamarin/mobile-samples/tree/master/Weather).
>
>   Sorunlar varsa veya hatalarla karşılaşırsanız lütfen üzerinde sorularınızı [forums.xamarin.com](http://forums.xamarin.com). Birçok hata açıklanan olan son SDK Xamarin tarafından gerekli güncelleştirerek çözülebilir [Xamarin sürüm notları](https://developer.xamarin.com/releases/) her platform için.    
  
> [!NOTE]
>  Xamarin'ın Geliştirici belgeleri de aşağıda listelenen Quickstart ve derin Dalış bölümleri ile birkaç izlenecek yollar sunar. Tüm bu sayfalarda "Visual Studio" Visual Studio özgü izlenecek yollar görmek için sağ üst sayfanın içinde seçili olduğundan emin olun.  
>   
>  -   Xamarin uygulamaları yerel kullanıcı Arabirimi ile:  
>   
>      -   [Merhaba, Android](https://developer.xamarin.com/guides/android/getting_started/hello,android/) (bir ekrana sahip basit uygulama)  
>     -   [Merhaba, Android multiscreen](https://developer.xamarin.com/guides/android/getting_started/hello,android_multiscreen/) (ekranları arasında gezinmeyi uygulamayla)  
>     -   [Android parçaları izlenecek](http://developer.xamarin.com/guides/android/platform_features/fragments/fragments_walkthrough/) (ana/ayrıntı ekranda, başka şeylerin için kullanılır)  
>     -   [Hello, iOS](https://developer.xamarin.com/guides/ios/getting_started/hello,_iOS/)  
>     -   [Çok Ekranlı Hello, iOS ](https://developer.xamarin.com/guides/ios/getting_started/hello,_iOS_multiscreen/)  
> -   Xamarin.Forms (paylaşılan UI) ile Xamarin uygulamaları  
>   
>      -   [Hello, Xamarin.Forms](https://developer.xamarin.com/guides/cross-platform/xamarin-forms/getting-started/hello-xamarin-forms/quickstart/)  
>     -   [Hello, Xamarin.Forms Multiscreen](https://developer.xamarin.com/guides/cross-platform/xamarin-forms/getting-started/hello-xamarin-forms-multiscreen/)  
  
##  <a name="solution"></a> Çözümünüzü ayarlarken ayarlayın  
 Bu adımları paylaşılan kodu için bir PCL ve iki eklenen NuGet paketlerini içeren yerel kullanıcı Arabirimi ile bir Xamarin çözümü oluşturun.  
  
1.  Visual Studio'da yeni bir oluşturma **boş uygulama (yerel taşınabilir)** çözüm ve adlandırın **WeatherApp**. Bu şablon en kolay girerek bulabileceğiniz **yerel taşınabilir** arama alanına.  
  
     Yoksa, olabilir Xamarin yükleyin veya Visual Studio 2015 özelliğini etkinleştirmek için bkz: [Kurulum ve yükleme](../cross-platform/setup-and-install.md).  
  
2.  Çözüm oluşturmak için Tamam'ı tıklattıktan sonra tek tek projelerinin sayısına sahip olursunuz:  
  
    -   **WeatherApp (taşınabilir)**: Burada,, ortak iş mantığı ve UI kodu Xamarin.Forms ile kullanarak da dahil olmak üzere platformlarda paylaşılan kod yazma PCL.  
  
    -   **WeatherApp.Droid**: yerel Android kodu içeren projeye. Bu varsayılan başlangıç projesi olarak ayarlanır.  
  
    -   **WeatherApp.iOS**: projenin yerel iOS kodunu içerir.  
  
    -   **WeatherApp.WinPhone (Windows Phone 8.1)**: yerel Windows Phone kod içeren projeye.  
  
     Her yerel proje içinde karşılık gelen platform yerel Tasarımcı Erişimi ve platform belirli ekranlar uygulayabilirsiniz.  
  
3.  Ekleme **Newtonsoft.Json** ve hava durumu veri hizmetinden alınan bilgileri işlemek için kullanacağınız PCL projesi için NuGet paketi:  
  
    -   Sağ **çözüm 'WeatherApp'** Çözüm Gezgini'nde ve select **çözüm için NuGet paketlerini Yönet...**.  
  
         NuGet penceresinde seçin **Gözat** sekmesinde ve arama **Newtonsoft**.  
  
    -   Seçin **Newtonsoft.Json**.  
  
    -   Pencerenin sağ tarafında denetleyin **WeatherApp** proje (Bu durum, paket yüklemeniz gereken yalnızca proje).  
  
    -   Olun **sürüm** alan ayarlanmış **en son kararlı** sürümü.  
  
    -   **Yükle**'ye tıklatın.  
  
    -   ![Bulma ve Newtonsoft.Json NuGet paketi Yükleniyor](../cross-platform/media/crossplat-xamarin-formsguide-5.png "CrossPlat Xamarin FormsGuide 5")  
  
4.  Adımı yineleyin bulmak ve yüklemek için 3 **Microsoft.Net.Http** paket.  
  
5.  Çözümünüzü derlemek ve hiçbir derleme hataları olduğunu doğrulayın.  
  
##  <a name="dataservice"></a> Paylaşılan veri hizmeti kod yazma  
 **WeatherApp (taşınabilir)** projedir burada tüm platformlarda paylaşılan taşınabilir sınıf kitaplığı (PCL) için kod yazacaksınız. PCL otomatik olarak oluşturulmuş projeler iOS, Android ve Windows Phone uygulama paketleri dahil edilir.  
  
 Aşağıdaki adımlar bu durumda, hava durumu hizmetinden veri depolamak ve erişmek için PCL kodu ekleyin:  
  
1.  Gereken ilk kez oturum zamanında boş bir API anahtar için bu örneği çalıştırmak için [ http://openweathermap.org/appid ](http://openweathermap.org/appid).  
  
2.  Sağ **WeatherApp** proje ve seçin **Ekle > sınıfı...**. İçinde **Yeni Öğe Ekle** iletişim kutusunda, dosya adı **Weather.cs**. Bu sınıf, hava durumu veri hizmetinden veri depolamak için kullanacaksınız.  
  
3.  Tüm içeriğini değiştirin **Weather.cs** aşağıdaki:  
  
    ```csharp  
    namespace WeatherApp  
    {  
        public class Weather  
        {  
            public string Title { get; set; }  
            public string Temperature { get; set; }  
            public string Wind { get; set; }  
            public string Humidity { get; set; }  
            public string Visibility { get; set; }  
            public string Sunrise { get; set; }  
            public string Sunset { get; set; }  
  
            public Weather()  
            {  
                //Because labels bind to these values, set them to an empty string to  
                //ensure that the label appears on all platforms by default.  
                this.Title = " ";  
                this.Temperature = " ";  
                this.Wind = " ";  
                this.Humidity = " ";  
                this.Visibility = " ";  
                this.Sunrise = " ";  
                this.Sunset = " ";  
            }  
        }  
    }  
    ```  
  
4.  Başka bir sınıf adlı PCL projeye ekleyin **DataService.cs** hangi işlem JSON verilerini hava durumu veri hizmetinden kullanacağınız içinde.  
  
5.  Tüm içeriğini değiştirin **DataService.cs** aşağıdaki kod ile:  
  
    ```csharp  
    using System.Threading.Tasks;  
    using Newtonsoft.Json;  
    using System.Net.Http;  
  
    namespace WeatherApp  
    {  
        public class DataService  
        {  
            public static async Task<dynamic> getDataFromService(string queryString)  
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
  
6.  Adlı PCL üçüncü sınıfı ekleme **çekirdek** burada gireceğiniz iş mantığı, bir posta koduyla bir sorgu dizesi forms mantığı hava veri hizmeti çağırır ve örneği doldurur gibi paylaşılan **hava durumu**sınıfı.  
  
7.  Değiştir **Core.cs** aşağıdaki:  
  
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
                string key = "YOUR KEY HERE";  
                string queryString = "http://api.openweathermap.org/data/2.5/weather?zip="  
                    + zipCode + ",us&appid=" + key + "&units=imperial";  

                //Make sure developers running this sample replaced the API key
                if (key == "YOUR API KEY HERE")
                {
                    throw new ArgumentException("You must obtain an API key from openweathermap.org/appid and save it in the 'key' variable.");
                }
  
                dynamic results = await DataService.getDataFromService(queryString).ConfigureAwait(false);  
  
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
  
8.  Değiştir *burada bilgisayarınızı anahtar* içinde elde ettiğiniz API anahtarını koduyla (hala gerekli etrafına tırnak) 1. adımda.  
  
9. Biz kullanıyor olmaz nedeniyle PCL MyClass.cs silin.  
  
10. Yapı **WeatherApp** PCL proje kodunun doğru olduğundan emin olun.  
  
##  <a name="Android"></a> Android için kullanıcı Arabirimi tasarımı  
 Şimdi, biz kullanıcı arabirimini tasarlamak, paylaşılan kodunuzu bağlanmak ve uygulamayı çalıştırın.  
  
### <a name="design-the-look-and-feel-of-your-app"></a>Uygulamanızı Görünüm ve yapısını tasarlama  
  
1.  İçinde **Çözüm Gezgini**, genişletin **WeatherApp.Droid**>**kaynakları**>**düzeni** klasörü ve Açık **Main.axml**. Bu Görsel tasarımcıda dosyasını açar. (Java ilgili bir hata varsa, bu bkz [blog gönderisi](http://forums.xamarin.com/discussion/32365/connection-to-the-layout-renderer-failed-in-xs-5-7-and-xamarinvs-3-9).)  
  
    > [!TIP]
    >  Projede diğer birçok dosyası yok. Bunları keşfetme ancak biraz daha bir Android projesi yapısına başlamak isterseniz, bu konunun kapsamı dışında olup [bölümü 2 derinlemesine](http://developer.xamarin.com/guides/android/getting_started/hello,android/hello,android_deepdive/) Hello Android konunun xamarin.com üzerinde.  
  
2.  Seçin ve Tasarımcısı'nda görünen varsayılan düğme silin.  
  
3.  Araç kutusu açın **Görünüm > Diğer Pencereler > Araç**.  
  
4.  Gelen **araç**, sürükleyin bir **RelativeLayout** tasarımcıya denetim. Bu denetim, diğer denetimler için üst kapsayıcı olarak kullanacaksınız.  
  
    > [!TIP]
    >  Herhangi bir zamanda doğru görüntülenemeyecek kadar düzeni görünmemektedir, dosyayı kaydedin ve arasında geçiş yapma **tasarım** ve **kaynak** sekmeleri yenileyin.  
  
5.  İçinde **özellikleri** penceresindeki ayarlayın **arka plan** (stil grubunda) özelliğine `#545454`.  
  
6.  Gelen **araç**, sürükleyin bir **kutusu TextView** üzerine kontrol **RelativeLayout** denetim.  
  
7.  İçinde **özellikleri** penceresinde, bu özellikleri ayarlama (Not: alfabetik sıralama düğmesini Özellikler penceresi araç çubuğunda kullanarak sıralamak için yardımcı olabilir):  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**text**|**Posta kodu göre ara**|  
    |**id**|`@+id/ZipCodeSearchLabel`|  
    |**layout_marginLeft**|`10dp`|  
    |**textColor**|`@android:color/white`|  
    |**textStyle**|`bold`|  
  
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
        android:layout_centerVertical="true"  
        android:layout_marginLeft="10dp"  
        android:textColor="@android:color/white"  
        android:textStyle="bold" />  
  
    ```  
  
8.  Gelen **araç**, sürükleyin bir **kutusu TextView** üzerine kontrol **RelativeLayout** denetlemek ve ZipCodeSearchLabel denetim yerleştir. Bunun için yeni denetim kontrolü uygun kenarında bırakarak; Bunun için biraz tasarımcıda yakınlaştırma yardımcı olabilir.  
  
9. İçinde **özellikleri** penceresinde, bu özellikleri ayarlayın:  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**text**|**Posta Kodu**|  
    |**id**|`@+id/ZipCodeLabel`|  
    |**layout_marginLeft**|`10dp`|  
    |**layout_marginTop**|`5dp`|  
  
     Kodda **kaynak** görünüm aşağıdaki gibi görünmelidir:  
  
    ```xml  
    <TextView  
        android:text="Zip Code"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_below="@id/ZipCodeSearchLabel"  
        android:id="@+id/ZipCodeLabel"  
        android:layout_marginTop="5dp"  
        android:layout_marginLeft="10dp" />  
    ```  
  
10. Gelen **araç**, sürükleyin bir **numarası** üzerine kontrol **RelativeLayout**, aşağıdaki getirin **posta kodu** etiketi. Ardından aşağıdaki özellikleri ayarlayın:  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**id**|`@+id/zipCodeEntry`|  
    |**layout_marginLeft**|`10dp`|  
    |**layout_marginBottom**|`10dp`|  
    |**width**|`165dp`|  
  
     Yeniden kodu:  
  
    ```xml  
    <EditText  
        android:inputType="number"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_below="@id/ZipCodeLabel"  
        android:id="@+id/zipCodeEntry"  
        android:layout_marginLeft="10dp"  
        android:layout_marginBottom="10dp"  
        android:width="165dp" />  
    ```  
  
11. Gelen **araç**, sürükleyin bir **düğmesini** üzerine **RelativeLayout** denetlemek ve zipCodeEntry denetim sağına yerleştir. Bu özellikleri ayarlayın:  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**id**|`@+id/weatherBtn`|  
    |**text**|**Hava durumu Al**|  
    |**layout_marginLeft**|`20dp`|  
    |**layout_alignBottom**|`@id/zipCodeEntry`|  
    |**width**|`165dp`|  
  
    ```xml  
    <Button    android:text="Get Weather"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_toRightOf="@id/zipCodeEntry"  
        android:id="@+id/weatherBtn"  
        android:layout_marginLeft="20dp"  
        android:layout_alignBottom="@id/zipCodeEntry"  
        android:width="165dp" />  
    ```  
  
12. Artık Android Tasarımcısını kullanarak temel bir kullanıcı Arabirimi oluşturmak için yeterli deneyimi var. Bir kullanıcı Arabirimi sayfası .asxml dosyayı doğrudan biçimlendirme ekleyerek de oluşturabilirsiniz. Bu şekilde UI rest oluşturmak için geçiş kaynağı görünümü Tasarımcısı'nda, ardından aşağıdaki biçimlendirme geçmiş için *altındaki* `</RelativeLayout>` etiketi (bunlar... etiketi altında olan Evet, öğeleri ReleativeLayout almayan).  
  
    ```xml  
    <TextView  
            android:text="Location"  
            android:textAppearance="?android:attr/textAppearanceSmall"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/locationLabel"  
            android:layout_marginLeft="10dp"  
            android:layout_marginTop="10dp" />  
        <TextView  
            android:textAppearance="?android:attr/textAppearanceMedium"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/locationText"  
            android:layout_marginLeft="20dp"  
            android:layout_marginBottom="10dp" />  
        <TextView  
            android:text="Temperature"  
            android:textAppearance="?android:attr/textAppearanceSmall"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/tempLabel"  
            android:layout_marginLeft="10dp" />  
        <TextView  
            android:textAppearance="?android:attr/textAppearanceMedium"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/tempText"  
            android:layout_marginBottom="10dp"  
            android:layout_marginLeft="20dp" />  
        <TextView  
            android:text="Wind Speed"  
            android:textAppearance="?android:attr/textAppearanceSmall"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/windLabel"  
            android:layout_marginLeft="10dp" />  
        <TextView  
            android:textAppearance="?android:attr/textAppearanceMedium"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/windText"  
            android:layout_marginBottom="10dp"  
            android:layout_marginLeft="20dp" />  
        <TextView  
            android:text="Humidity"  
            android:textAppearance="?android:attr/textAppearanceSmall"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/humidtyLabel"  
            android:layout_marginLeft="10dp" />  
        <TextView  
            android:textAppearance="?android:attr/textAppearanceMedium"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/humidityText"  
            android:layout_marginBottom="10dp"  
            android:layout_marginLeft="20dp" />  
        <TextView  
            android:text="Visibility"  
            android:textAppearance="?android:attr/textAppearanceSmall"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/visibilityLabel"  
            android:layout_marginLeft="10dp" />  
        <TextView  
            android:textAppearance="?android:attr/textAppearanceMedium"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/visibilityText"  
            android:layout_marginBottom="10dp"  
            android:layout_marginLeft="20dp" />  
        <TextView  
            android:text="Time of Sunrise"  
            android:textAppearance="?android:attr/textAppearanceSmall"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/sunriseLabel"  
            android:layout_marginLeft="10dp" />  
        <TextView  
            android:textAppearance="?android:attr/textAppearanceMedium"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/sunriseText"  
            android:layout_marginBottom="10dp"  
            android:layout_marginLeft="20dp" />  
        <TextView  
            android:text="Time of Sunset"  
            android:textAppearance="?android:attr/textAppearanceSmall"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/sunsetLabel"  
            android:layout_marginLeft="10dp" />  
        <TextView  
            android:textAppearance="?android:attr/textAppearanceMedium"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/sunsetText"  
            android:layout_marginBottom="10dp"  
            android:layout_marginLeft="20dp" />  
  
    ```  
  
13. Dosyayı kaydedin ve geçiş **tasarım** görünümü. UI aşağıdaki gibi görünmelidir:  
  
     ![Android için kullanıcı Arabirimi](../cross-platform/media/xamarin_androidui.png "Xamarin_AndroidUI")  
  
14. Açık **MainActivity.cs** ve satırları silme *OnCreate* önceki kaldırıldı varsayılan düğme başvuran yöntemi. İşiniz bittiğinde kodu aşağıdaki gibi görünmelidir:  
  
    ```  
    protected override void OnCreate (Bundle bundle)  
    {  
        base.OnCreate (bundle);  
  
        // Set our view from the "main" layout resource  
        SetContentView (Resource.Layout.Main);  
    }  
    ```  
  
15. Çalışmanızı iade etme için Android projesi oluşturun. Yapı ekler Not denetlemek için kimlikleri **Resource.Designer.cs** kod ada göre denetimlere başvurabilmeniz için dosya.  
  
### <a name="consume-your-shared-code"></a>Paylaşılan kodunuzu kullanma  
  
1.  Açık **MainActivity.cs** dosyasının **WeatherApp** proje Kod Düzenleyicisi'nde ve içeriğini aşağıdaki kodla değiştirin. Bu kod çağırır `GetWeather` paylaşılan kodunuzda tanımlanan yöntemi. Daha sonra kullanıcı Arabiriminde uygulamanın o yönteminden alınan verileri gösterir.  
  
    ```csharp  
    using System;  
    using Android.App;  
    using Android.Widget;  
    using Android.OS;  
  
    namespace WeatherApp.Droid  
    {  
        [Activity(Label = "Sample Weather App", MainLauncher = true, Icon = "@drawable/icon")]  
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
  
### <a name="run-the-app-and-see-how-it-looks"></a>Uygulamayı çalıştırın ve nasıl göründüğünü görmek  
  
1.  İçinde **Çözüm Gezgini**, emin olun **WeatherApp.Droid** projesi başlangıç projesi olarak ayarla.  
  
2.  Bir cihaz veya öykünücü hedef seçin ve ardından F5 tuşuna basarak uygulamayı başlatın.  
  
3.  Cihaz veya öykünücü, geçerli bir Amerika Birleşik Devletleri zip kod düzenleme kutusuna yazın (örneğin: 60601) ve basın **alma hava durumu**. Bu bölge için hava durumu verileri, ardından denetimlerinde görüntülenir.  
  
     ![Android ve Windows Phone için hava durumu uygulaması](../cross-platform/media/xamarin_getstarted_results.png "Xamarin_GetStarted_Results")  
  
> [!TIP]
>  Bu proje için tam kaynak kodu [mobil-samples deposu github'da](https://github.com/xamarin/mobile-samples/tree/master/Weather).  
  
##  <a name="Windows"></a> Windows Phone için kullanıcı Arabirimi tasarımı  
 Şimdi biz Windows Phone için kullanıcı arabirimi tasarım, paylaşılan kodunuzu bağlanmak ve uygulamayı çalıştırın.  
  
### <a name="design-the-look-and-feel-of-your-app"></a>Uygulamanızı Görünüm ve yapısını tasarlama  
 Yerel Windows Phone kullanıcı Arabiriminde bir Xamarin uygulaması tasarlama işlemi herhangi diğer yerel Windows Phone uygulamasından farklı değildir. Bu nedenle, biz ayrıntılarını tasarımcının nasıl kullanılacağı buraya gidin olmaz. Bunun için başvurmak [XAML Tasarımcısını kullanarak bir kullanıcı Arabirimi oluşturma](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).  
  
 Bunun yerine, yalnızca MainPage.xaml açın ve tüm XAML kodu aşağıdakilerle değiştirin:  
  
```xaml  
<Page  
    x:Class="WeatherApp.WinPhone.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:local="using:WeatherApp.WinPhone"  
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    mc:Ignorable="d"  
    Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">  
  
    <Grid>  
        <StackPanel HorizontalAlignment="Left" Height="40" Margin="10,0,0,0" VerticalAlignment="Top" Width="400">  
            <TextBlock x:Name="pageTitle" Text="Weather App" FontSize="30" />  
        </StackPanel>  
        <StackPanel HorizontalAlignment="Left" Height="120" Margin="10,40,0,0" VerticalAlignment="Top" Width="400" Background="#FF545454">  
  
            <TextBlock x:Name="zipCodeSearchLabel" TextWrapping="Wrap" Text="Search by Zip Code" FontSize="18" FontWeight="Bold" HorizontalAlignment="Left" Margin="10,10,0,0"/>  
            <TextBlock x:Name="zipCodeLabel" TextWrapping="Wrap" Text="Zip Code" Margin="10,5,0,0" FontSize="14" Foreground="#FFA8A8A8"/>  
            <StackPanel Orientation="Horizontal">  
                <TextBox x:Name="zipCodeEntry" Margin="10,10,0,0" Text="" VerticalAlignment="Top" InputScope="Number" Width="165" />  
                <Button x:Name="weatherBtn" Content="Get Weather" Width="165" Margin="20,0,0,0" Height="60" Click="GetWeatherButton_Click"/>  
            </StackPanel>  
        </StackPanel>  
        <StackPanel Margin="10,175,0,0">  
            <TextBlock x:Name="locationLabel" HorizontalAlignment="Left" FontSize="14" Foreground="#FFA8A8A8" TextWrapping="Wrap" Text="Location" VerticalAlignment="Top"/>  
            <TextBlock x:Name="locationText" Margin="10,0,0,10" HorizontalAlignment="Left" FontSize="18" TextWrapping="Wrap" VerticalAlignment="Top"/>  
            <TextBlock x:Name="tempLabel" HorizontalAlignment="Left" FontSize="14" Foreground="#FFA8A8A8" TextWrapping="Wrap" Text="Temperature" VerticalAlignment="Top"/>  
            <TextBlock x:Name="tempText" Margin="10,0,0,10" HorizontalAlignment="Left" FontSize="18" TextWrapping="Wrap" VerticalAlignment="Top"/>  
            <TextBlock x:Name="windLabel" HorizontalAlignment="Left" FontSize="14" Foreground="#FFA8A8A8" TextWrapping="Wrap" Text="Wind Speed" VerticalAlignment="Top"/>  
            <TextBlock x:Name="windText" Margin="10,0,0,10" HorizontalAlignment="Left" FontSize="18" TextWrapping="Wrap" VerticalAlignment="Top"/>  
            <TextBlock x:Name="humidityLabel" HorizontalAlignment="Left" FontSize="14" Foreground="#FFA8A8A8" TextWrapping="Wrap" Text="Humidity" VerticalAlignment="Top"/>  
            <TextBlock x:Name="humidityText" Margin="10,0,0,10" HorizontalAlignment="Left" FontSize="18" TextWrapping="Wrap" VerticalAlignment="Top"/>  
            <TextBlock x:Name="visibilityLabel" HorizontalAlignment="Left" FontSize="14" Foreground="#FFA8A8A8" TextWrapping="Wrap" Text="Temperature" VerticalAlignment="Top"/>  
            <TextBlock x:Name="visibilityText" Margin="10,0,0,10" HorizontalAlignment="Left" FontSize="18" TextWrapping="Wrap" VerticalAlignment="Top"/>  
            <TextBlock x:Name="sunriseLabel" HorizontalAlignment="Left" FontSize="14" Foreground="#FFA8A8A8" TextWrapping="Wrap" Text="Time of Sunriweatherse" VerticalAlignment="Top"/>  
            <TextBlock x:Name="sunriseText" Margin="10,0,0,10" HorizontalAlignment="Left" FontSize="18" TextWrapping="Wrap" VerticalAlignment="Top"/>  
            <TextBlock x:Name="sunsetLabel" HorizontalAlignment="Left" FontSize="14" Foreground="#FFA8A8A8" TextWrapping="Wrap" Text="Time of Sunset" VerticalAlignment="Top"/>  
            <TextBlock x:Name="sunsetText" Margin="10,0,0,10" HorizontalAlignment="Left" FontSize="18" TextWrapping="Wrap" VerticalAlignment="Top"/>  
        </StackPanel>  
    </Grid>  
</Page>  
```  
  
 Tasarım görünümünde, kullanıcı Arabirimi aşağıdaki gibi görünmelidir:  
  
 ![Windows Phone uygulama kullanıcı Arabirimi](../cross-platform/media/xamarin_winphone_finalui.png "Xamarin_WinPhone_FinalUI")  
  
### <a name="consume-your-shared-code"></a>Paylaşılan kodunuzu kullanma  
  
1.  Tasarımcıda seçin **alma hava** düğmesi.  
  
2.  İçinde **özellikleri** penceresinde, olay işleyici düğmesini seçin (![Visual Studio olay işleyicileri simgesi](../cross-platform/media/blend_vs_eventhandlers_icon.png "blend_VS_EventHandlers_icon")).  
  
     Bu simge üst köşesinde görüntülenen **özellikleri** penceresi.  
  
3.  Yanına **tıklatın** olay, türü **GetWeatherButton_Click**ve ardından ENTER tuşuna basın.  
  
     Bu adlı bir olay işleyicisi oluşturur `GetWeatherButton_Click`. Kod Düzenleyicisi'ni açar ve imleci olay işleyici kod bloğu içinde yerleştirir.  Not: Düzenleyicisi ENTER tuşuna basıldığında açık değilse, yalnızca olay adına çift tıklayın.  
  
4.  Bu olay işleyicisini aşağıdaki kodla değiştirin.  
  
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
  
     Bu kod çağırır `GetWeather` paylaşılan kodunuzda tanımlanan yöntemi. Android uygulamanızda adlı aynı yöntem budur. Bu kod Ayrıca, uygulamanızın UI denetimlerinde yöntemin alınan verileri gösterir.  
  
5.  İçinde tüm kod açık olan MainPage.xaml.cs dosyasında silme **OnNavigatedTo** yöntemi. Bu kod yalnızca biz MainPage.xaml içeriğini yerini yükleyen kaldırıldı varsayılan düğme işlenir.  
  
### <a name="run-the-app-and-see-how-it-looks"></a>Uygulamayı çalıştırın ve nasıl göründüğünü görmek  
  
1.  İçinde **Çözüm Gezgini**ayarlayın **WeatherApp.WinPhone** projesini başlangıç projesi olarak.  
  
2.  F5 tuşuna basarak uygulamayı başlatın.  
  
3.  Windows Phone öykünücüsü, geçerli bir Amerika Birleşik Devletleri zip kod düzenleme kutusuna yazın (örneğin: 60601) ve basın **alma hava durumu**. Bu bölge için hava durumu verileri, ardından denetimlerinde görüntülenir.  
  
     ![Windows sürümü çalışan uygulamanın](../cross-platform/media/xamarin_getstarted_results_windows.png "Xamarin_GetStarted_Results_Windows")  
  
> [!TIP]
>  Bu proje için tam kaynak kodu [mobil-samples deposu github'da](https://github.com/xamarin/mobile-samples/tree/master/Weather).  
  
##  <a name="next"></a> Sonraki adımlar  
 **UI iOS için çözüme ekleyin.**  
  
 Bu örnek, iOS için yerel kullanıcı Arabirimi ekleyerek genişletebilir. Xamarin yüklü ve bunun için bir Mac Xcode sahip yerel ağınızdaki bağlanmak gerekir. Bunu yaptığınızda, doğrudan Visual Studio'da iOS Tasarımcısı'nı kullanabilirsiniz. Bkz: [mobil-samples deposu github'da](https://github.com/xamarin/mobile-samples/tree/master/Weather) tamamlanan uygulama için.  
  
 Ayrıca bkz [Hello, iOS](http://developer.xamarin.com/guides/ios/getting_started/hello,_iOS/hello,iOS_quickstart/) (xamarin.com) Gözden geçirme. Yönergeler doğru kümesini görünmesini sağlayacak şekilde bu sayfada emin bu "Visual Studio" unutmayın sağ üst köşesindeki sayfaları xamarin.com üzerinde seçilir.  
  
 **Platforma özgü kodu paylaşılan bir proje ekleyin**  
  
 Paylaşılan bir PCL kodda PCL kez derlenmiş ve her platforma özgü uygulama paketinde platformdan bağımsız kaynaklanır. Koşullu derleme platforma özgü kodu yalıtmak için kullandığı paylaşılan kod yazmak istiyorsanız, kullanabileceğiniz bir *paylaşılan* projesi. Daha fazla ayrıntı için bkz: [kodu paylaşımı seçenekleri](http://developer.xamarin.com/guides/cross-platform/application_fundamentals/building_cross_platform_applications/sharing_code_options/) (xamarin.com).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Xamarin Geliştirici sitesi](http://developer.xamarin.com/)   
 [Windows Geliştirici Merkezi](https://dev.windows.com/en-us)   
 [SWIFT ve C# hızlı başvuru posteri](http://aka.ms/scposter)