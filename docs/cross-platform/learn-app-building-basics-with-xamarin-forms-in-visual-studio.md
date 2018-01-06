---
title: "Visual Studio'da Xamarin.Forms ile uygulama oluşturma temellerini öğrenin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d22b5186-9e03-4e85-afc9-7cbe28522a6d
caps.latest.revision: "11"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: xamarin
ms.openlocfilehash: b25344afa89c3b1244203a914b9b64347223870d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="learn-app-building-basics-with-xamarinforms-in-visual-studio"></a>Visual Studio'da Xamarin.Forms ile uygulama oluşturma temellerini öğrenin
Adımları yaptıktan sonra [Kurulum ve yükleme](../cross-platform/setup-and-install.md) ve [Xamarin ortamınızı doğrulayın](../cross-platform/verify-your-xamarin-environment.md), bu kılavuzda (aşağıda Xamarin.Forms ile gösterilmiştir) temel bir uygulama oluşturmak gösterilmektedir. Xamarin.Forms ile tüm kullanıcı Arabirimi kodunuzu bir kez bir taşınabilir Sınıf Kitaplığı'nda (PCL) yazacaksınız. Xamarin sonra otomatik olarak sokacak iOS, Android ve Windows için yerel kullanıcı Arabirimi denetimlerini platformlar. Yalnızca bu .NET tüm hedef platformlar arasında desteklenen API'lerini kullanarak en iyi PCL seçeneğini desteklediği için bu yaklaşım önerilir ve Xamarin.Forms izin verdiğinden platformlarında UI kod paylaşın.  
  
 ![Android, iOS ve Windows Phone hava durumu uygulaması örneği](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")  
  
 Bu derleme için bunlardan gerçekleştirirsiniz:  
  
-   [Çözümünüzü ayarlarken ayarlayın](#solution)  
  
-   [Paylaşılan veri hizmeti kod yazma](#dataservice)  
  
-   [Paylaşılan kullanıcı Arabirimi kod yazmaya başlayın](#uicode)  
  
-   [Android için Visual Studio öykünücüsü kullanarak uygulamanızı test etme](#test)  
  
-   [Platformlar arası yerel bir görünümüne sahip kullanıcı arabirimini son](#finish)  
  
> [!TIP]
>  Bu proje için tam kaynak kodunu bulabilirsiniz [xamarin forms örnekleri deposu github'da](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather).  
  
##  <a name="solution"></a>Çözümünüzü ayarlarken ayarlayın  
 Bu adımları paylaşılan kodu için bir PCL ve iki eklenen NuGet paketlerini içeren bir Xamarin.Forms çözümünü oluşturun.  
  
1.  Visual Studio'da yeni bir oluşturma **boş uygulama (Xamarin.Forms taşınabilir)** çözüm ve adlandırın **WeatherApp**. Bu şablon en kolay girerek bulabileceğiniz **Xamarin.Forms** arama alanına.  
  
     Yoksa, olabilir Xamarin yükleyin veya Visual Studio 2015 özelliğini etkinleştirmek için bkz: [Kurulum ve yükleme](../cross-platform/setup-and-install.md).  
  
     ![Yeni bir boş uygulama &#40;oluşturma; Xamarin.Forms taşınabilir &#41; Proje](../cross-platform/media/crossplat-xamarin-formsguide-2.png "CrossPlat Xamarin FormsGuide 2")  
  
2.  Çözüm oluşturmak için Tamam'ı tıklattıktan sonra tek tek projelerinin sayısına sahip olursunuz:  
  
    -   **WeatherApp (taşınabilir)**: Burada,, ortak iş mantığı ve UI kodu Xamarin.Forms ile kullanarak da dahil olmak üzere platformlarda paylaşılan kod yazma PCL.  
  
    -   **WeatherApp.Droid**: yerel Android kodu içeren projeye. Bu varsayılan başlangıç projesi olarak ayarlanır.  
  
    -   **WeatherApp.iOS**: projenin yerel iOS kodunu içerir.  
  
    -   **WeatherApp.UWP**: Windows 10 UWP kodu içeren projeye.  
  
    -   **WeatherApp.Windows (Windows 8.1)**: yerel Windows 8.1 kod içeren projeye.  
  
    -   **WeatherApp.WinPhone (Windows Phone 8.1)**: yerel Windows Phone kod içeren projeye.  
  
    > [!NOTE]
    >  Değil hedefleme bir platformu projelerin silmek boş. Bu kılavuzda amaçları doğrultusunda, biz Android, iOS ve Windows Phone 8.1 projelere başvuran. UWP ve Windows 8.1 çalışma projeleri Windows Phone 8.1 proje ile çalışmaya çok benzer.  
  
     Her yerel proje içinde karşılık gelen platform yerel Tasarımcı Erişimi ve platform belirli ekranları ve gerektiğinde işlevselliği uygulayabilirsiniz.  
  
3.  Çözümünüzü Xamarin.Forms NuGet paketi en son kararlı sürümü aşağıdaki gibi yükseltin. Yeni bir Xamarin çözüm oluşturduğunuzda bunu öneririz:  
  
    -   Seçin **Araçlar > NuGet Paket Yöneticisi > çözüm için NuGet paketlerini Yönet**.  
  
    -   Altında **güncelleştirmeleri** sekmesi, onay **Xamarin.Forms** güncelleştirin ve çözümünüzdeki tüm projeleri güncelleştirmek için denetleyin. (Not: tüm güncelleştirmeler için Xamarin.Android.Support işaretini kaldırın.)  
  
    -   Güncelleştirme **sürüm** alanı **en son kararlı** kullanılabilir sürüm.  
  
    -   Tıklatın **güncelleştirme**.  
  
         ![Xamarin.Forms NuGet paketi güncelleştirme](../cross-platform/media/crossplat-xamarin-formsguide-4.png "CrossPlat Xamarin FormsGuide 4")  
  
4.  Ekleme **Newtonsoft.Json** ve hava durumu veri hizmetinden alınan bilgileri işlemek için kullanacağınız PCL projesi için NuGet paketi:  
  
    -   NuGet Paket Yöneticisi'nde (3. adımdan hala açık) seçin **Gözat** sekmesinde ve arama **Newtonsoft**.  
  
    -   Seçin **Newtonsoft.Json**.  
  
    -   Denetleme **WeatherApp** proje (Bu durum, paket yüklemeniz gereken yalnızca proje).  
  
    -   Olun **sürüm** alan ayarlanmış **en son kararlı** sürümü.  
  
    -   **Yükle**'ye tıklatın.  
  
    -   ![Bulma ve Newtonsoft.Json NuGet paketi Yükleniyor](../cross-platform/media/crossplat-xamarin-formsguide-5.png "CrossPlat Xamarin FormsGuide 5")  
  
5.  Yineleme adım bulmak ve yüklemek için 4 **Microsoft.Net.Http** paket.  
  
6.  Çözümünüzü derlemek ve hiçbir derleme hataları olduğunu doğrulayın.  
  
##  <a name="dataservice"></a>Paylaşılan veri hizmeti kod yazma  
 **WeatherApp (taşınabilir)** projedir burada tüm platformlarda paylaşılan taşınabilir sınıf kitaplığı (PCL) için kod yazacaksınız. PCL otomatik olarak uygulamada bulunan paketleri iOS, Android ve Windows Phone projeleri oluşturmak.  
  
 Gereken ilk kez oturum zamanında boş bir API anahtar için bu örneği çalıştırmak için [http://openweathermap.org/appid](http://openweathermap.org/appid).  
  
 Aşağıdaki adımlar bu durumda, hava durumu hizmetinden veri depolamak ve erişmek için PCL kodu ekleyin:  
  
1.  Sağ **WeatherApp** proje ve seçin **Ekle > sınıfı...** . İçinde **Yeni Öğe Ekle** iletişim kutusunda, dosya adı **Weather.cs**. Bu sınıf, hava durumu veri hizmetinden veri depolamak için kullanacaksınız.  
  
2.  Tüm içeriğini değiştirin **Weather.cs** aşağıdaki:  
  
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
  
3.  Başka bir sınıf adlı PCL projeye ekleyin **DataService.cs** hangi işlem JSON verilerini hava durumu veri hizmetinden kullanacağınız içinde.  
  
4.  Tüm içeriğini değiştirin **DataService.cs** aşağıdaki kod ile:  
  
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
  
5.  Adlı PCL üçüncü sınıfı ekleme **çekirdek** burada gireceğiniz iş mantığı, bir posta koduyla bir sorgu dizesi forms mantığı hava veri hizmeti çağırır ve örneği doldurur gibi paylaşılan **hava durumu**sınıfı.  
  
6.  Değiştir **Core.cs** aşağıdaki:  
  
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
  
7.  Yapı **WeatherApp** PCL proje kodunun doğru olduğundan emin olun.  
  
##  <a name="uicode"></a>Paylaşılan kullanıcı Arabirimi kod yazmaya başlayın  
 Xamarin.Forms PCL paylaşılan UI kodu uygulamanıza olanak sağlar. Bu adımlarda önceki bölümde eklediğiniz kodun kendi verilerle hava durumu verileri tarafından döndürülen güncelleştirmeleri hizmet düğmesiyle PCL ekran eklenecektir:  
  
1.  Ekle bir **Forms Xaml sayfası** adlı **WeatherPage.cs** sağ tıklanarak **WeatherApp** proje ve seçerek **Ekle > Yeni öğe...** . İçinde **Yeni Öğe Ekle** iletişim kutusunda, arama formlarda"," select **Forms Xaml sayfası**ve adlandırın **WeatherPage.cs**.  
  
     Xamarin.Forms XAML tabanlı, bu adımı oluşturur bir **WeatherPage.xaml** iç içe geçmiş arka plan kodu dosyasıyla birlikte dosya **WeatherPage.xaml.cs**. Bu, kullanıcı Arabirimi üzerinden XAML veya kod oluşturmak üzere sağlar. Bu kılavuzda hem de bazıları gerçekleştirirsiniz.  
  
     ![Yeni bir Xamarin.Forms XAML sayfası ekleme](../cross-platform/media/crossplat-xamarin-formsguide-6.png "CrossPlat Xamarin FormsGuide 6")  
  
2.  Düğme WeatherPage ekranına eklemek için WeatherPage.xaml içeriğini aşağıdakiyle değiştirin:  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"  
           xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"  
           x:Class="WeatherApp.WeatherPage">  
      <Button x:Name="getWeatherBtn" Text="Get Weather"/>  
    </ContentPage>  
    ```  
  
     Düğmenin adı kullanılarak tanımlanmalıdır fark **x: Name** arka plan kod dosyası içinde adıyla bu düğme başvurabilmek özniteliği.  
  
3.  Düğme için bir olay işleyicisi eklemek için **tıklama** Değiştir düğmesi metni güncelleştirmek için olay **WeatherPage.xaml.cs** aşağıdaki kod ile. ("60601" değiştirmek için başka bir posta kodu çekinmeyin.)  
  
    ```csharp  
    using System;  
    using Xamarin.Forms;  
  
    namespace WeatherApp  
    {  
        public partial class WeatherPage: ContentPage  
        {  
            public WeatherPage()  
            {  
                InitializeComponent();  
                this.Title = "Sample Weather App";  
                getWeatherBtn.Clicked += GetWeatherBtn_Clicked;  
  
                //Set the default binding to a default object for now  
                this.BindingContext = new Weather();  
            }  
  
            private async void GetWeatherBtn_Clicked(object sender, EventArgs e)  
            {  
                Weather weather = await Core.GetWeather("60601");  
                getWeatherBtn.Text = weather.Title;  
            }  
        }  
    }  
    ```  
  
4.  Açmak için **WeatherPage** uygulama başlattığında, ilk ekran olarak varsayılan oluşturucuda Değiştir **App.cs** aşağıdaki kod ile:  
  
    ```csharp  
    public App()  
    {  
        MainPage = new NavigationPage(new WeatherPage());  
    }  
    ```  
  
5.  Kodunun doğru olduğundan emin olmak için WeatherApp PCL projesi oluşturun.  
  
##  <a name="test"></a>Android için Visual Studio öykünücüsü kullanarak uygulamanızı test etme  
 Şimdi uygulamayı çalıştırmak hazırsınız! Şimdi uygulamayı hava durumu hizmetinden veri alınırken doğrulamak şu an yalnızca Android sürümü çalıştırın. Daha sonra daha fazla kullanıcı Arabirimi öğeleri ekledikten sonra da iOS ve Windows Phone sürümlerini çalıştıracaksınız. (Not: Windows 7'de Visual Studio çalıştırıyorsanız, aynı adımları ancak Xamarin Player yerine olur.)  
  
1.  Ayarlama **WeatherApp.Droid** projesi sağ ve seçerek başlangıç projesi olarak **başlangıç projesi olarak ayarla**.  
  
2.  Visual Studio araç çubuğunda göreceğiniz **WeatherApp.Droid** hedef projesi olarak listelenir. Hata ayıklama için Android öykünücüsünü birini seçin ve isabet **F5**. Aşağıdakilerden birini kullanmanızı öneririz **VS öykünücüsü** uygulama Android seçenekleri için Visual Studio öykünücüsü çalışacak seçenekleri.  
  
     ![VS öykünücüsü hata ayıklama hedef seçme](../cross-platform/media/crossplat-xamarin-formsguide-7.png "CrossPlat Xamarin FormsGuide 7")  
  
3.  Uygulama öykünücüsünde başlattığında tıklatın **hava durumu alma** düğmesi. Düğmenin metni için güncelleştirilmiş görmelisiniz **Chicago, IL**, olduğu *başlık* verileri özelliği hava durumu hizmetinden alınan.  
  
     ![Önce ve sonra düğmesine uygulama hava durumu](../cross-platform/media/crossplat-xamarin-formsguide-8.png "CrossPlat Xamarin FormsGuide 8")  
  
##  <a name="finish"></a>Platformlar arası yerel bir görünümüne sahip kullanıcı arabirimini son  
 Uygulamanızı otomatik olarak yerel bir görünümüne sahip olması Xamarin.Forms her platform için yerel kullanıcı Arabirimi denetimlerini işler. Bu görmek için daha fazla Açıkçası, giriş alanını bir posta kodu için kullanıcı Arabirimi şimdi son ve hizmetten döndürülen hava durumu verileri görüntüleyin.  
  
1.  Değiştir **WeatherPage.xaml** aşağıdaki kod ile. Her öğe, kullanarak olarak adlandırılır Not **x: Name** öznitelik öğe koddan başvurulabilir böylece daha önce açıklandığı gibi. Xamarin.Forms de sağlayan bir dizi [Düzen Seçenekleri](http://developer.xamarin.com/guides/xamarin-forms/controls/layouts/) (xamarin.com); burada, WeatherPage kullanarak [StackLayout](http://developer.xamarin.com/api/type/Xamarin.Forms.StackLayout/) (xamarin.com).  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"  
           xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"  
           x:Class="WeatherApp.WeatherPage">  
  
      <ContentPage.Resources>  
        <ResourceDictionary>  
          <Style x:Key="labelStyle" TargetType="Label">  
            <Setter Property="TextColor" Value="#a8a8a8" />  
            <Setter Property="FontSize" Value="Small" />  
          </Style>  
          <Style x:Key="fieldStyle" TargetType="Label">  
            <Setter Property="TextColor">  
              <OnPlatform x:TypeArguments="Color" iOS="Black" Android="White" WinPhone="White" />  
            </Setter>  
            <Setter Property="FontSize" Value="Medium" />  
          </Style>  
          <Style x:Key="fieldView" TargetType="ContentView">  
            <Setter Property="Padding" Value="10,0,0,0" />  
          </Style>  
        </ResourceDictionary>  
      </ContentPage.Resources>  
  
      <ContentPage.Content>  
        <ScrollView>  
          <StackLayout>  
            <StackLayout Orientation="Horizontal" HorizontalOptions="FillAndExpand"  
                  BackgroundColor="#545454">  
              <StackLayout Padding="10,10,10,10" HorizontalOptions="Start">  
                <Label Text="Search by Zip Code" TextColor="White" FontAttributes="Bold"  
                    FontSize="Medium" />  
                <Label x:Name="zipCodeLabel" Text="Zip Code" Style="{StaticResource labelStyle}" />  
                <Entry x:Name="zipCodeEntry" />  
              </StackLayout>  
              <StackLayout Padding="0,0,0,10" VerticalOptions="End">  
                <Button x:Name="getWeatherBtn" Text="Get Weather" WidthRequest="185" BorderWidth="1" >  
                  <!-- Set iOS colors; use defaults on other platforms -->  
                  <Button.TextColor>  
                    <OnPlatform x:TypeArguments="Color" iOS="White"/>  
                  </Button.TextColor>  
                  <Button.BorderColor>  
                    <OnPlatform x:TypeArguments="Color" iOS="White"/>  
                  </Button.BorderColor>  
                </Button>  
              </StackLayout>  
            </StackLayout>  
            <StackLayout Padding="10,10,10,10" HorizontalOptions="Start">  
              <Label Text="Location" Style="{StaticResource labelStyle}" />  
              <ContentView Style="{StaticResource fieldView}">  
                <Label Text="{Binding Title}" Style="{StaticResource fieldStyle}" />  
              </ContentView>  
              <Label Text="Temperature" Style="{StaticResource labelStyle}" />  
              <ContentView Style="{StaticResource fieldView}">  
                <Label x:Name="tempLabel" Text="{Binding Temperature}"  
                    Style="{StaticResource fieldStyle}" />  
              </ContentView>  
              <Label Text="Wind Speed" Style="{StaticResource labelStyle}" />  
              <ContentView Style="{StaticResource fieldView}">  
                <Label x:Name="windLabel" Text="{Binding Wind}" Style="{StaticResource fieldStyle}" />  
              </ContentView>  
              <Label Text="Humidity" Style="{StaticResource labelStyle}" />  
              <ContentView Style="{StaticResource fieldView}">  
                <Label x:Name="humidityLabel" Text="{Binding Humidity}"  
                    Style="{StaticResource fieldStyle}" />  
              </ContentView>  
              <Label Text="Visibility" Style="{StaticResource labelStyle}" />  
              <ContentView Style="{StaticResource fieldView}">  
                <Label x:Name="visibilitylabel" Text="{Binding Visibility}"  
                    Style="{StaticResource fieldStyle}" />  
              </ContentView>  
              <Label Text="Time of Sunrise" Style="{StaticResource labelStyle}" />  
              <ContentView Style="{StaticResource fieldView}">  
                <Label x:Name="sunriseLabel" Text="{Binding Sunrise}"  
                    Style="{StaticResource fieldStyle}" />  
              </ContentView>  
              <Label Text="Time of Sunset" Style="{StaticResource labelStyle}" />  
              <ContentView Style="{StaticResource fieldView}">  
                <Label x:Name="sunsetLabel" Text="{Binding Sunset}"  
                    Style="{StaticResource fieldStyle}" />  
              </ContentView>  
            </StackLayout>  
          </StackLayout>  
        </ScrollView>  
      </ContentPage.Content>  
    </ContentPage>  
    ```  
  
     Kullanımına dikkat edin **OnPlatform** Xamarin.Forms etiketinde. **OnPlatform** uygulamayı çalıştıran geçerli platforma özgü bir özellik değeri seçer (bkz [dış XAML sözdizimi](http://developer.xamarin.com/guides/xamarin-forms/user-interface/xaml-basics/essential_xaml_syntax/) (xamarin.com). Biz buraya veri alanları farklı metin rengini ayarlamak için kullanmakta olduğunuz: Android ve Windows Phone, iOS siyah beyaz. Kullanabileceğiniz **OnPlatform** tüm özellikleri ve XAML içinde herhangi bir yere platforma özgü ayarlamalar yapmak için hiçbir veri türleri için. Arka plan kod dosyasına kullandığınız [Device.OnPlatform API](http://developer.xamarin.com/guides/xamarin-forms/platform-features/device/) aynı amaçla.  
  
2.  İçinde **WeatherPage.xaml.cs**, yerine **GetWeatherBtn_Clicked** aşağıdaki kod ile olay işleyicisi. Bu kod olmadığını girişi alanında bir posta kodu, bu posta kodu için verileri alır, tam ekran bağlama bağlamı sonuçta elde edilen hava durumu örneğine ayarlar ve sonra "Yeniden arama." düğmesi metni ayarlar doğrular Her etiket kullanıcı arabiriminde bir özelliğe hava durumu sınıfının böylece ne zaman bağlar, Not ekranının bağlama bağlamı kümesine bir **hava durumu** örneği, etiketlerin güncelleştirme otomatik olarak.  
  
    ```csharp  
    private async void GetWeatherBtn_Clicked(object sender, EventArgs e)  
    {  
        if (!String.IsNullOrEmpty(zipCodeEntry.Text))  
        {  
            Weather weather = await Core.GetWeather(zipCodeEntry.Text);  
            this.BindingContext = weather;  
            getWeatherBtn.Text = "Search Again";  
        }  
    }  
    ```  
  
3.  Uygulama tüm üç platformlarında çalışan — Android, iOS ve Windows Phone — uygun projeyi sağ, başlangıç projesi olarak ayarla seçerek ve uygulamayı bir cihaz veya öykünücü veya benzetici başlatılıyor. Geçerli bir Amerika Birleşik Devletleri zip kod (örneğin, 60601) girin ve aşağıda gösterildiği gibi bu bölge için hava durumu verileri görüntülemek için alma hava düğmesine basın. Elbette Visual Studio iOS projesinin ağınızdaki bir Mac OS X bilgisayara bağlı olması gerekir.  
  
     ![Android, iOS ve Windows Phone hava durumu uygulaması örneği](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")  
  
 Bu proje için tam kaynak kodu [xamarin forms örnekleri deposu github'da](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather).