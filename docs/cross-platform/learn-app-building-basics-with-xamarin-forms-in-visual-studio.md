---
title: "Visual Studio'da Xamarin.Forms ile uygulama oluşturma temellerini öğrenin | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2018
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
ms.openlocfilehash: 3a066156f66a4e89132010a8c83edc7029dbe19e
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2018
---
# <a name="learn-app-building-basics-with-xamarinforms-in-visual-studio"></a>Visual Studio'da Xamarin.Forms ile uygulama oluşturma temellerini öğrenin
Adımları yaptıktan sonra [Kurulum ve yükleme](../cross-platform/setup-and-install.md) ve [Xamarin ortamınızı doğrulayın](../cross-platform/verify-your-xamarin-environment.md), bu kılavuzda (aşağıda Xamarin.Forms ile gösterilmiştir) temel bir uygulama oluşturmak gösterilmektedir. Xamarin.Forms ile tüm kullanıcı Arabirimi kodunuzu kez .NET standart bir sınıf kitaplığı'nda yazacaksınız. Xamarin sonra otomatik olarak sokacak iOS, Android ve evrensel Windows için yerel kullanıcı Arabirimi denetimlerini platformlar. Bu yaklaşım (Paylaşılan proje yerine) .NET standart kitaplığı yalnızca bu .NET tüm hedef platformlar arasında desteklenen API'lerini içerdiğinden öneririz ve Xamarin.Forms izin verdiğinden UI kod platformları arasında paylaşın.  
  
 ![Android, iOS ve Windows hava durumu uygulaması örneği](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")  
  
 Bu derleme için bunlardan gerçekleştirirsiniz:  
  
-   [Çözümünüzü ayarlarken ayarlayın](#solution)  
  
-   [Paylaşılan veri hizmeti kod yazma](#dataservice)  
  
-   [Paylaşılan kullanıcı Arabirimi kod yazmaya başlayın](#uicode)  
  
-   [Android için Visual Studio öykünücüsü kullanarak uygulamanızı test etme](#test)  
  
-   [Platformlar arası yerel bir görünümüne sahip kullanıcı arabirimini son](#finish)  
  
> [!TIP]
>  Bu proje için tam kaynak kodunu bulabilirsiniz [xamarin forms örnekleri deposu github'da](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather).  
  
##  <a name="solution"></a>Çözümünüzü ayarlarken ayarlayın  
 Bu adımları bir .NET standart paylaşılan kod sınıf kitaplığı ve iki eklenen NuGet paketlerini içeren bir Xamarin.Forms çözümünü oluşturun.  
  
1.  Visual Studio'da yeni bir oluşturma **platformlar arası uygulama (Xamarin.Forms)** çözüm ve adlandırın **WeatherApp**. Şablonu seçerek görüneceğini **Visual C#** ve **platformlar arası** soldaki listeden.  
  
     Yoksa, olabilir Xamarin yükleyin veya Visual Studio 2017 özelliğini etkinleştirmek için bkz: [Kurulum ve yükleme](../cross-platform/setup-and-install.md).  
  
     ![Yeni bir boş uygulama &#40;oluşturma; Platformlar arası Xamarin.Forms uygulaması &#41; Proje](../cross-platform/media/crossplat-xamarin-formsguide-2.png "CrossPlat Xamarin FormsGuide 2")

2.  Tamam'ı tıklattıktan sonra bazı seçenekler seçme fırsatı sahip olacaksınız. Çekme **boş uygulama**, **Xamarin.Forms** ve **.NET standart**:

     ![Yeni bir Çapraz Platform uygulama projesi oluşturma](../cross-platform/media/crossplat-xamarin-formsguide-3.png "CrossPlat Xamarin FormsGuide 3")
  
3.  Çözüm oluşturmak için Tamam'ı tıklattıktan sonra tek tek projelerinin sayısına sahip olursunuz:  
  
    -   **WeatherApp**: Burada,, ortak iş mantığı ve UI kodu Xamarin.Forms kullanarak da dahil olmak üzere platformları arasında paylaşılan kod yazma .NET standart kitaplığı.  
  
    -   **WeatherApp.Android**: yerel Android kodu içeren projeye. Bu varsayılan başlangıç projesi olarak ayarlanır.  
  
    -   **WeatherApp.iOS**: projenin yerel iOS kodunu içerir.  
  
    -   **WeatherApp.UWP**: Windows 10 UWP kodu içeren projeye.  
  
    > [!NOTE]
    >  Değil hedefleme bir platformu projelerin silmek boş.   
  
     Her yerel proje içinde karşılık gelen platform yerel Tasarımcı Erişimi ve platform belirli ekranları ve gerektiğinde işlevselliği uygulayabilirsiniz.  
  
4.  Çözümünüzü Xamarin.Forms NuGet paketi en son kararlı sürümü aşağıdaki gibi yükseltin. Yeni bir Xamarin çözüm oluşturduğunuzda bunu öneririz:  
  
    -   Seçin **Araçlar > NuGet Paket Yöneticisi > çözüm için NuGet paketlerini Yönet**.  
  
    -   Altında **güncelleştirmeleri** sekmesi, onay **Xamarin.Forms** paketini ve çözümünüzdeki tüm projeleri güncelleştirmek için denetleyin. (Not: tüm güncelleştirmeler için Xamarin.Android.Support işaretini kaldırın.)  
  
    -   Güncelleştirme **sürüm** alanı **en son kararlı** kullanılabilir sürüm.  
  
    -   **Yükle**'ye tıklatın.  
  
         ![Xamarin.Forms NuGet paketi güncelleştirme](../cross-platform/media/crossplat-xamarin-formsguide-4.png "CrossPlat Xamarin FormsGuide 4")  
  
5.  Ekleme **Newtonsoft.Json** NuGet paketi **WeatherApp** hava veri hizmetinden alınan bilgileri işlemek için kullanacağınız proje:  
  
    -   NuGet Paket Yöneticisi'nde (4. adımdan hala açık) seçin **Gözat** sekmesinde ve arama **Newtonsoft**.  
  
    -   Seçin **Newtonsoft.Json**.  
  
    -   Denetleme **WeatherApp** proje (Bu durum, paket yüklemeniz gereken yalnızca proje).  
  
    -   Olun **sürüm** alan ayarlanmış **en son kararlı** sürümü.  
  
    -   **Yükle**'ye tıklatın.  
  
    ![Bulma ve Newtonsoft.Json NuGet paketi Yükleniyor](../cross-platform/media/crossplat-xamarin-formsguide-5.png "CrossPlat Xamarin FormsGuide 5")  
  
6.  Bulmak ve yüklemek için 5. adım yineleme **Microsoft.Net.Http** paket.  
  
7.  Çözümünüzü derlemek ve hiçbir derleme hataları olduğunu doğrulayın.  
  
##  <a name="dataservice"></a>Paylaşılan veri hizmeti kod yazma  
 **WeatherApp** projedir burada tüm platformlarda paylaşılan .NET standart kitaplığı için kod yazacaksınız. Bu kitaplığı otomatik olarak uygulamada bulunan paketleri, projeler iOS, Android ve Windows tarafından oluşturmak.  
  
 Bu örneği çalıştırmak için önce boş bir API anahtarda için kaydolmanız gerekir [http://openweathermap.org/appid](http://openweathermap.org/appid).  
  
 Aşağıdaki adımlar bu durumda, hava durumu hizmetinden veri depolamak ve erişmek için .NET standart kitaplığı kodu ekleyin:  
  
1.  Sağ **WeatherApp** proje ve seçin **Ekle > sınıfı...** . İçinde **Yeni Öğe Ekle** iletişim kutusunda, dosya adı **Weather.cs**. Bu sınıf, hava durumu veri hizmetinden veri depolamak için kullanacaksınız.  
  
2.  Tüm içeriğini değiştirin **Weather.cs** aşağıdaki:  
  
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
  
3.  Başka bir sınıf ekleyin **WeatherApp** adlı projesi **DataService.cs** hava veri hizmetinden işlem JSON verilerini kullanacağınız.  
  
4.  Tüm içeriğini değiştirin **DataService.cs** aşağıdaki kod ile:  
  
    ```csharp  
    using System.Net.Http;  
    using System.Threading.Tasks;  
    using Newtonsoft.Json;  
    
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
  
5.  Bir üçüncü sınıfına ekleyin **WeatherApp** adlı projesi **çekirdek** burada gireceğiniz paylaşılan iş mantığı. Bu kod bir posta koduyla bir sorgu dizesi oluşturur, hava durumu veri hizmeti çağırır ve örneği doldurur **hava durumu** sınıfı.  
  
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
  
7.  Yapı **WeatherApp** kitaplığı proje kodunun doğru olduğundan emin olun.  
  
##  <a name="uicode"></a>Paylaşılan kullanıcı Arabirimi kod yazmaya başlayın  
 Xamarin.Forms .NET standart Kitaplığı'nda paylaşılan UI kodu uygulamanıza olanak sağlar. Bu adımlarda önceki bölümde eklediğiniz kodun kendi verilerle hava durumu verileri tarafından döndürülen güncelleştirmeleri hizmet düğmesiyle projesine bir sayfa ekleyeceksiniz:  
  
1.  Ekle bir **içerik sayfasını** adlı **WeatherPage.cs** sağ tıklanarak **WeatherApp** proje ve seçerek **Ekle > Yeni öğe...** . İçinde **Yeni Öğe Ekle** iletişim kutusunda **içerik sayfasını**. I dikkatli olun **içerik sayfası (C#)** veya **içerik görünümü**. Bu ad **WeatherPage.cs**.  
  
     ![Yeni bir Xamarin.Forms XAML sayfası ekleme](../cross-platform/media/crossplat-xamarin-formsguide-6.png "CrossPlat Xamarin FormsGuide 6")  
  
     Xamarin.Forms XAML tabanlı, bu adımı oluşturur bir **WeatherPage.xaml** iç içe geçmiş arka plan kodu dosyasıyla birlikte dosya **WeatherPage.xaml.cs**. Bu, kullanıcı Arabirimi üzerinden XAML veya kod oluşturmak üzere sağlar. Bu kılavuzda hem de bazıları gerçekleştirirsiniz.  
  
2.  Düğme WeatherPage ekranına eklemek için içeriğini değiştirmek **WeatherPage.xaml** aşağıdaki:  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"  
           xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"  
           x:Class="WeatherApp.WeatherPage"
           Title="Sample Weather App">  
      <Button x:Name="getWeatherBtn" 
              Text="Get Weather"
              Clicked="GetWeatherBtn_Clicked" />  
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
  
                //Set the default binding to a default object for now  
                BindingContext = new Weather();  
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
        InitializeComponent();

        MainPage = new NavigationPage(new WeatherPage());  
    }  
    ```  
  
5.  Yapı **WeatherApp** proje kodunun doğru olduğundan emin olun.  
  
##  <a name="test"></a>Android için Visual Studio öykünücüsü kullanarak uygulamanızı test etme  
 Şimdi uygulamayı çalıştırmak hazırsınız! Şimdi uygulamayı hava durumu hizmetinden veri alınırken doğrulamak şu an yalnızca Android sürümü çalıştırın. Daha sonra daha fazla kullanıcı Arabirimi öğeleri ekledikten sonra da iOS ve UWP sürümlerinde çalıştıracaksınız.   
  
1.  Ayarlama **WeatherApp.Android** projesi sağ ve seçerek başlangıç projesi olarak **başlangıç projesi olarak ayarla**.  
  
2.  Visual Studio araç çubuğunda göreceğiniz **WeatherApp.Android** hedef projesi olarak listelenir. Hata ayıklama için Android öykünücüsünü birini seçin ve isabet **F5**. Aşağıdakilerden birini kullanmanızı öneririz **Visual Studio** uygulama Android için Visual Studio öykünücüsünde çalışacaktır öykünücüsü seçenekleri.  
  
     ![Bir Android öykünücüsü hata ayıklama hedefi seçme](../cross-platform/media/crossplat-xamarin-formsguide-7.png "CrossPlat Xamarin FormsGuide 7")  
  
3.  Uygulama öykünücüsünde başlattığında tıklatın **hava durumu alma** düğmesi. Düğmenin metni için güncelleştirilmiş görmelisiniz **Chicago**, olduğu *başlık* verileri özelliği hava durumu hizmetinden alınan.  
  
     ![Önce ve sonra düğmesine uygulama hava durumu](../cross-platform/media/crossplat-xamarin-formsguide-8.png "CrossPlat Xamarin FormsGuide 8")  
  
##  <a name="finish"></a>Platformlar arası yerel bir görünümüne sahip kullanıcı arabirimini son  
 Uygulamanızı otomatik olarak yerel bir görünümüne sahip olması Xamarin.Forms her platform için yerel kullanıcı Arabirimi denetimlerini işler. Bu görmek için daha fazla Açıkçası, giriş alanını bir posta kodu için kullanıcı Arabirimi şimdi son ve hizmetten döndürülen hava durumu verileri görüntüleyin.  
  
1.  Değiştir **WeatherPage.xaml** aşağıdaki kod ile. Kullanarak adlı öğeleri **x: Name** daha önce açıklandığı gibi özniteliği koddan başvuruda bulunabilir. Xamarin.Forms de sağlayan bir dizi [Düzen Seçenekleri](http://developer.xamarin.com/guides/xamarin-forms/controls/layouts/) (xamarin.com). Burada, WeatherPage kullanarak [kılavuz](http://developer.xamarin.com/api/type/Xamarin.Forms.Grid/) (xamarin.com) ve [StackLayout](http://developer.xamarin.com/api/type/Xamarin.Forms.StackLayout/) (xamarin.com).  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"  
                 xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"  
                 x:Class="WeatherApp.WeatherPage"
                 Title="Sample Weather App">

        <ContentPage.Resources>
            <ResourceDictionary>
                <Style x:Key="labelStyle" TargetType="Label">
                    <Setter Property="FontSize" Value="Small" />
                    <Setter Property="TextColor" Value="#404040" />
                </Style>
                <Style x:Key="fieldStyle" TargetType="Label">
                    <Setter Property="FontSize" Value="Medium" />
                    <Setter Property="Margin" Value="10,0,0,0" />
                </Style>
            </ResourceDictionary>
        </ContentPage.Resources>

        <StackLayout>
            <Grid BackgroundColor="#545454" Padding="10, 10, 10, 10">
                <Grid.RowDefinitions>
                    <RowDefinition Height="Auto" />
                    <RowDefinition Height="Auto" />
                </Grid.RowDefinitions>

                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="Auto" />
                    <ColumnDefinition Width="*" />
                    <ColumnDefinition Width="Auto" />
                </Grid.ColumnDefinitions>
            
                <Label Text="Search by Zip Code" 
                       Grid.Row="0" Grid.Column="0" Grid.ColumnSpan="3"
                       HorizontalOptions="Center"
                       TextColor="White" FontAttributes="Bold" FontSize="Medium" />
            
                <Label x:Name="zipCodeLabel" Text="Zip Code:" 
                       Grid.Row="1" Grid.Column="0"
                       VerticalOptions="Center"
                       Style="{StaticResource labelStyle}"
                       TextColor="#C0C0C0" />
            
                <Entry x:Name="zipCodeEntry"
                       Grid.Row="1" Grid.Column="1"
                       VerticalOptions="Center"
                       Margin="5,0"
                       BackgroundColor="DarkGray"
                       TextColor="White" />
            
                <Button x:Name="getWeatherBtn" Text="Get Weather" 
                        Grid.Row="1" Grid.Column="2"
                        HorizontalOptions="Center"
                        VerticalOptions="Center"
                        BorderWidth="1"
                        BorderColor="White"
                        BackgroundColor="DarkGray"
                        TextColor="White"
                        Clicked="GetWeatherBtn_Clicked" />
            </Grid>

            <ScrollView VerticalOptions="FillAndExpand">
                <StackLayout Padding="10,10,10,10" HorizontalOptions="Start">
                    <Label Text="Location" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Title}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Temperature" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Temperature}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Wind Speed" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Wind}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Humidity" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Humidity}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Visibility" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Visibility}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Time of Sunrise" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Sunrise}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Time of Sunset" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Sunset}" Style="{StaticResource fieldStyle}" />
                </StackLayout>
            </ScrollView>
        </StackLayout>
    </ContentPage>  
     ```  
  
     Burada gösterilmese kullanabileceğiniz **OnPlatform** uygulamayı çalıştıran geçerli platforma özgü bir özellik değeri seçmek için etiket (bkz [temel XAML sözdizimi](http://developer.xamarin.com/guides/xamarin-forms/user-interface/xaml-basics/essential_xaml_syntax/) (xamarin.com). Arka plan kod dosyasına kullandığınız [Device.OnPlatform API](http://developer.xamarin.com/guides/xamarin-forms/platform-features/device/) aynı amaçla.  
  
2.  İçinde **WeatherPage.xaml.cs**, yerine **GetWeatherBtn_Clicked** aşağıdaki kod ile olay işleyicisi. Bu kod doğrular olmadığını girişi alanında bir posta kodu, bu posta kodu için verileri alır, elde edilen için tüm sayfanın bağlama bağlamını ayarlar **hava durumu** örnek sonra düğme metni "Yeniden arama." ayarlar Her etiket kullanıcı arabiriminde bir özelliğe bağlar Not **hava durumu** sınıfı, bunu, ekran bağlama bağlamı ayarladığınızda bir **hava durumu** örneği, etiketlerin güncelleştirme otomatik olarak.  
  
    ```csharp  
    private async void GetWeatherBtn_Clicked(object sender, EventArgs e)  
    {  
        if (!String.IsNullOrEmpty(zipCodeEntry.Text))  
        {  
            Weather weather = await Core.GetWeather(zipCodeEntry.Text);  
            BindingContext = weather;  
            getWeatherBtn.Text = "Search Again";  
        }  
    }  
    ```  
  
3.  Uygulama tüm üç platformlarında çalışan — Android, iOS ve Windows — göre uygun projesine sağ tıklatıp, seçme **başlangıç projesi olarak ayarla**ve bir cihaz veya öykünücü veya benzetici uygulama başlatma. Geçerli Amerika Birleşik Devletleri beş basamaklı posta kodu ve tuşuna basın **alma hava** aşağıda gösterildiği gibi bu bölge için hava durumu verileri görüntülemek için düğmesi. Visual Studio iOS projesinin ağınızdaki bir Mac OS X bilgisayara bağlı olması gerekir.  
  
     ![Android, iOS ve Windows Phone hava durumu uygulaması örneği](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")  
  
 Bu proje için tam kaynak kodu [xamarin forms örnekleri deposu github'da](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather).