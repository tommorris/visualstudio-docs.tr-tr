---
title: Visual Studio'da Xamarin.Forms ile uygulama oluşturma temellerini öğrenin | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: d22b5186-9e03-4e85-afc9-7cbe28522a6d
ms.technology: vs-ide-mobile
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 608eebc113c9df7a8978299cc69907e28d81a16f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="learn-app-building-basics-with-xamarinforms-in-visual-studio"></a>Visual Studio'da Xamarin.Forms ile uygulama oluşturma temellerini öğrenin

Adımları yaptıktan sonra [Kurulum ve yükleme](../cross-platform/setup-and-install.md) ve [Xamarin ortamınızı doğrulayın](../cross-platform/verify-your-xamarin-environment.md), bu kılavuzda Xamarin.Forms ile temel bir uygulama oluşturmak gösterilmektedir. Xamarin.Forms ile tüm kullanıcı Arabirimi kodunuzu kez .NET standart bir sınıf kitaplığı'nda yazacaksınız. Xamarin sonra otomatik olarak sokacak iOS, Android ve evrensel Windows için yerel kullanıcı Arabirimi denetimlerini platformlar. 

Genellikle bu ortak kodu için bir paylaşılan proje yerine .NET standart kitaplığı kullanmak daha iyidir. .NET standart kitaplığı, tüm hedef platformlarda çalışabilir bu .NET API'lerini içerir.  

Burada, oluşturacağınız uygulama verilmiştir. (Yazmak için soldan) iOS ve Android telefonlar ve Windows 10 Evrensel Windows Platformu (UWP) üzerinde çalıştığı:
  
[![İOS, Android ve UWP hava durumu uygulaması örneği](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")](../cross-platform/media/crossplat-xamarin-formsguide-1-Large.png#lightbox)
  
Bu uygulama oluşturmak için aşağıdaki adımları gerçekleştirirsiniz:  
  
-   [Çözümünüzü ayarlarken ayarlayın](#solution)  
  
-   [Paylaşılan veri hizmeti kod yazma](#dataservice)  
  
-   [Paylaşılan kullanıcı Arabirimi kod yazmaya başlayın](#uicode)  
  
-   [Android için Visual Studio öykünücüsü kullanarak uygulamanızı test etme](#test)  
  
-   [Platformlar arası yerel bir görünümüne sahip kullanıcı arabirimini son](#finish)  
  
> [!TIP]
> Bu proje için tam kaynak kodunu bulabilirsiniz [xamarin forms örnekleri deposu github'da](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather).  
  
<a name="solution" />

## <a name="set-up-your-solution"></a>Çözümünüzü ayarlarken ayarlayın  

Bu adımları bir .NET standart paylaşılan kod sınıf kitaplığı ve iki eklenen NuGet paketlerini içeren bir Xamarin.Forms çözümünü oluşturun. 
  
1. Visual Studio'da yeni bir oluşturma **platformlar arası uygulama (Xamarin.Forms)** çözüm ve adlandırın **WeatherApp**. Şablonu seçerek görüneceğini **Visual C#** ve **platformlar arası** soldaki listeden.  
    
    ![Yeni bir platformlar arası Xamarin.Forms uygulaması projesi oluşturma](../cross-platform/media/crossplat-xamarin-formsguide-2.png "CrossPlat Xamarin FormsGuide 2")

    Şablon yoksa, Xamarin yükleyin veya Visual Studio 2017 özelliğini etkinleştirmeniz gerekebilir. Bkz: [Kurulum ve yükleme](../cross-platform/setup-and-install.md).  

2.  Tamam'ı tıklattıktan sonra bazı seçenekler seçme fırsatı sahip olacaksınız. Çekme **boş uygulama** ve **.NET standart**:

    ![Yeni bir Çapraz Platform uygulama projesi oluşturma](../cross-platform/media/crossplat-xamarin-formsguide-3.png "CrossPlat Xamarin FormsGuide 3")
  
3.  Çözüm oluşturmak için Tamam'ı tıklattıktan sonra dört projeleri ile bir çözüm gerekir:  
  
    -   **WeatherApp**: Burada,, ortak iş mantığı ve UI kodu Xamarin.Forms kullanarak da dahil olmak üzere platformları arasında paylaşılan kod yazma .NET standart kitaplığı.  
  
    -   **WeatherApp.Android**: yerel Android kodu içeren projeye.  
  
    -   **WeatherApp.iOS**: projenin yerel iOS kodunu içerir.  
  
    -   **WeatherApp.UWP**: Windows 10 UWP kodu içeren projeye.  
  
    > [!NOTE]
    >  Değil hedefleme bir platformu projelerin silmek boş.   
  
     Yerel her proje içinde karşılık gelen platform yerel Tasarımcı Erişimi ve platforma özgü ekranları ve gerektiğinde işlevselliği uygulayabilirsiniz.  
  
4.  Çözümünüzü Xamarin.Forms NuGet paketi en son kararlı sürümü gibi yükseltin:  
  
    -   Seçin **Araçlar > NuGet Paket Yöneticisi > çözüm için NuGet paketlerini Yönet**.  
  
    -   Altında **güncelleştirmeleri** sekmesi, onay **Xamarin.Forms** paketini ve çözümünüzdeki tüm projeleri güncelleştirmek için denetleyin. (Xamarin Android destek kitaplıkları için güncelleştirme seçmeyin.)  
  
    -   Güncelleştirme **sürüm** alanı **en son kararlı** kullanılabilir sürüm.  
  
    -   **Yükle**'ye tıklatın.  
  
         ![Xamarin.Forms NuGet paketi güncelleştirme](../cross-platform/media/crossplat-xamarin-formsguide-4.png "CrossPlat Xamarin FormsGuide 4")  

    Yeni bir Xamarin.Forms çözüm oluşturduğunuzda, bir Xamarin.Forms sürümünden yükseltme alýþkanlýk almanız gerekir. Tüm Android destek kitaplıkları güncelleştirmez. Xamarin.Forms sürüm güncelleştirdiğinizde gerekirse, bu kitaplıklar güncelleştirilir.
  
5.  Ekleme **Newtonsoft.Json** NuGet paketi **WeatherApp** projesi. Bu kitaplık, hava durumu veri hizmetinden alınan bilgileri işlemek için kullanılır:  
  
    -   NuGet Paket Yöneticisi'nde (4. adımdan hala açık) seçin **Gözat** sekmesinde ve arama **Newtonsoft**.  
  
    -   Seçin **Newtonsoft.Json**.  
  
    -   Denetleme **WeatherApp** içinde paketini yüklemeniz gereken tek proje projesi.  
  
    -   Olun **sürüm** alan ayarlanmış **en son kararlı** sürümü.  
  
    -   **Yükle**'ye tıklatın.  
  
    ![Bulma ve Newtonsoft.Json NuGet paketi Yükleniyor](../cross-platform/media/crossplat-xamarin-formsguide-5.png "CrossPlat Xamarin FormsGuide 5")  
  
6.  Bulmak ve yüklemek için 5. adım yineleme **Microsoft.CSharp** .NET standart proje paketinde. C# kullanmak bu kitaplığı gereklidir `dynamic` .NET standart Kitaplığı'nda veri türü.
  
7.  Çözümünüzü derlemek ve hiçbir derleme hataları olduğunu doğrulayın.  
  
<a name="dataservice" /> 

## <a name="write-shared-data-service-code"></a>Paylaşılan veri hizmeti kod yazma  

**WeatherApp** .NET standart kitaplığı projedir burada tüm platformlarda paylaşılan kod yazacaksınız. Bu kitaplık uygulama tarafından başvurulan paketleri, projeler iOS, Android ve Windows tarafından oluşturmak.  
  
Bu örneği çalıştırmak için önce boş bir API anahtarda için kaydolmanız gerekir [ http://openweathermap.org/appid ](http://openweathermap.org/appid).  
  
Aşağıdaki adımlar bu durumda, hava durumu hizmetinden veri depolamak ve erişmek için .NET standart kitaplığı kodu ekleyin:  
  
1.  Sağ **WeatherApp** proje ve seçin **Ekle > sınıfı...** . İçinde **Yeni Öğe Ekle** iletişim kutusunda, dosya adı **Weather.cs**. Bu sınıf, hava durumu veri hizmetinden veri depolamak için kullanacaksınız.  
  
2.  Tüm içeriğini değiştirin **Weather.cs** aşağıdaki kod ile:  
  
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
  
5.  Bir üçüncü sınıfına ekleyin **WeatherApp** adlı projesi **Core.cs** burada gireceğiniz paylaşılan iş mantığı. Bu kod bir posta koduyla bir sorgu dizesi oluşturur, hava durumu veri hizmeti çağırır ve örneği doldurur `Weather` sınıfı.  
  
6.  Değiştir **Core.cs** aşağıdaki kod ile:  
  
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

7. Değiştir *burada bilgisayarınızı API anahtarı* elde ettiğiniz API anahtarı ile. Hala, etrafına tırnak işareti gerekiyor!     
  
8.  Yapı **WeatherApp** kitaplığı proje kodunun doğru olduğundan emin olun.  
  
 <a name="uicode" /> 

## <a name="begin-writing-shared-ui-code"></a>Paylaşılan kullanıcı Arabirimi kod yazmaya başlayın  

Xamarin.Forms .NET standart Kitaplığı'nda paylaşılan UI kodu uygulamanıza olanak sağlar. Bu adımlarda, bir sayfa bir düğme projeyle eklenecektir. Önceki bölümde gördüğünüz metin verilerle sayfasında hava hizmet tarafından döndürülen bu düğme güncelleştirmeleri:  
  
1.  Ekle bir **içerik sayfasını** adlı **WeatherPage** sağ tıklanarak **WeatherApp** proje ve seçerek **Ekle > Yeni öğe...** . İçinde **Yeni Öğe Ekle** iletişim kutusunda **içerik sayfasını**. I dikkatli olun **içerik sayfası (C#)** veya **içerik görünümü**. Bu ad **WeatherPage.xaml**.  
  
    ![Yeni bir Xamarin.Forms XAML sayfası ekleme](../cross-platform/media/crossplat-xamarin-formsguide-6.png "CrossPlat Xamarin FormsGuide 6")  
  
     Xamarin.Forms XAML tabanlı, bu adımı oluşturur bir **WeatherPage.xaml** iç içe geçmiş arka plan kodu dosyasıyla birlikte dosya **WeatherPage.xaml.cs**. Kullanıcı arabirimi mantığı XAML veya kod yazabilirsiniz. Bu kılavuzda hem de bazıları gerçekleştirirsiniz.  
  
2.  Düğme eklemek için **WeatherPage** ekranında, Değiştir **WeatherPage.xaml** aşağıdaki biçimlendirme ile:  
  
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
  
     Düğmenin adı kullanılarak tanımlanmalıdır fark `x:Name` arka plan kod dosyası içinde adıyla bu düğme başvurabilmek özniteliği.  
  
3.  Düğme için bir olay işleyicisi eklemek için `Clicked` Değiştir düğmesi metni güncelleştirmek için olay **WeatherPage.xaml.cs** aşağıdaki kod ile. ("60601" değiştirmek için başka bir posta kodu çekinmeyin.)  
  
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
  
4.  Açmak için **WeatherPage** uygulama başlattığında, ilk ekran olarak varsayılan oluşturucuda Değiştir **App.xaml.cs** aşağıdaki kod ile:  
  
    ```csharp  
    public App()  
    {
        InitializeComponent();

        MainPage = new NavigationPage(new WeatherPage());  
    }  
    ```  
  
5.  Yapı **WeatherApp** proje kodunun doğru olduğundan emin olun.  
  
<a name="test" /> 

## <a name="test-your-app-using-the-visual-studio-emulator-for-android"></a>Android için Visual Studio öykünücüsü kullanarak uygulamanızı test etme  

Şimdi uygulamayı çalıştırmak hazırsınız! Şimdi uygulamayı hava durumu hizmetinden veri alınırken doğrulamak şu an yalnızca Android sürümü çalıştırın. Daha sonra daha fazla kullanıcı Arabirimi öğeleri ekledikten sonra da iOS ve UWP sürümlerinde çalıştıracaksınız.   
  
1.  Ayarlama **WeatherApp.Android** projesi sağ ve seçerek başlangıç projesi olarak **başlangıç projesi olarak ayarla**.  
  
2.  Visual Studio araç çubuğunda göreceğiniz **WeatherApp.Android** hedef projesi olarak listelenir. Hata ayıklama için Android öykünücüsünü birini seçin ve isabet **F5**. Aşağıdakilerden birini kullanmanızı öneririz **Visual Studio** uygulama Android için Visual Studio öykünücüsünde çalışacaktır öykünücüsü seçenekleri.  
  
    ![Bir Android öykünücüsü hata ayıklama hedefi seçme](../cross-platform/media/crossplat-xamarin-formsguide-7.png "CrossPlat Xamarin FormsGuide 7")

    > [!NOTE]
    > Visual Studio Android projesi Newtonsoft.Json dosyası bulunamıyor gösteriyorsa, bu NuGet paketi Android projeye ekleyin.   
  
3.  Uygulama öykünücüsünde başlattığında tıklatın **hava durumu alma** düğmesi. Düğmenin metni için güncelleştirilmiş görmelisiniz **Chicago**, olduğu `Title` verileri özelliği hava durumu hizmetinden alınan.  
  
     ![Önce ve sonra düğmesine uygulama hava durumu](../cross-platform/media/crossplat-xamarin-formsguide-8.png "CrossPlat Xamarin FormsGuide 8")  

<a name="finish" /> 

## <a name="finish-the-ui-with-a-native-look-and-feel-across-platforms"></a>Platformlar arası yerel bir görünümüne sahip kullanıcı arabirimini son  

Uygulamanızı otomatik olarak yerel bir görünümüne sahip olması Xamarin.Forms her platform için yerel kullanıcı Arabirimi denetimlerini işler. Bir posta kodu ve hava durumu verilerini göstermek için denetimleri için giriş alanını dahil etmek için UI tamamlanmasıyla, yerel bu görünümüne daha net bir şekilde görebilirsiniz.  
  
1.  Değiştir **WeatherPage.xaml** biçimlendirme ile. Kullanarak adlı öğeleri `x:Name` daha önce açıklandığı gibi özniteliği koddan başvuruda bulunabilir. Xamarin.Forms de sağlayan bir dizi [Düzen Seçenekleri](/xamarin/xamarin-forms/controls/layouts/). Burada, WeatherPage kullanarak [kılavuz](http://developer.xamarin.com/api/type/Xamarin.Forms.Grid/) ve [StackLayout](http://developer.xamarin.com/api/type/Xamarin.Forms.StackLayout/).  
  
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
  
     Burada gösterilmese kullanabileceğiniz `OnPlatform` uygulamayı çalıştıran geçerli platforma özgü bir özellik değeri seçmek için XAML dosyaları etiketinde (bkz [temel XAML sözdizimi](/xamarin/xamarin-forms/xaml/xaml-basics/essential-xaml-syntax/).) Arka plan kod dosyasına, uygulama üzerinde çalıştığından karşılaştırarak hangi platformu belirleyebilirsiniz [ `Device.RuntimePlatform` ](https://developer.xamarin.com/api/property/Xamarin.Forms.Device.RuntimePlatform/) tanımlanan sabitleri özelliğiyle [ `Device` ](https://developer.xamarin.com/api/type/Xamarin.Forms.Device/) adlısınıfı[ `Device.iOS` ](https://developer.xamarin.com/api/field/Xamarin.Forms.Device.iOS/), [ `Device.Android` ](https://developer.xamarin.com/api/field/Xamarin.Forms.Device.Android/), ve [ `Device.UWP` ](https://developer.xamarin.com/api/field/Xamarin.Forms.Device.UWP/).  
  
2.  İçinde **WeatherPage.xaml.cs**, yerine `GetWeatherBtn_Clicked` aşağıdaki kod ile olay işleyicisi. Bu kod bir posta kodu girişi alanında olmadığını ve bu posta kodu verilerini alır doğrular. Elde edilen için sonra tüm sayfanın bağlama bağlamını ayarlar `Weather` örneği. Düğme metni "Yeniden arama." ayarlayarak kod burada son bulur Her etiket kullanıcı arabiriminde bir özelliğe bağlar `Weather` sınıfı. Belirlediğinizde ekranının bağlama bağlamı bir `Weather` örneği, etiketlerin güncelleştirme otomatik olarak.  
  
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
  
3.  Uygun projeyi sağ tıklayarak uygulamanın tüm üç platformlarında çalışan seçme **başlangıç projesi olarak ayarla**ve bir cihaz veya öykünücü üzerinde uygulama başlatma. Geçerli Amerika Birleşik Devletleri beş basamaklı posta kodu ve tuşuna basın **hava durumu alma** bu bölge için hava durumu verileri görüntülemek için düğmesi. Visual Studio iOS projesinin ağınızdaki bir Mac bilgisayara bağlı olması gerekir.  
  
     [![İOS, Android ve UWP hava durumu uygulaması örneği](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")](../cross-platform/media/crossplat-xamarin-formsguide-1-Large.png#lightbox)
  
Bu proje için tam kaynak kodu [xamarin forms örnekleri deposu github'da](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather).