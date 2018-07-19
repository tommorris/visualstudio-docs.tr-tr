---
title: Visual Studio'da Xamarin.Forms ile uygulama oluşturmaya yönelik temel bilgileri öğrenin | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: d22b5186-9e03-4e85-afc9-7cbe28522a6d
ms.prod: visual-studio-dev15
ms.technology: vs-ide-mobile
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: f9f233b5f43555f86f0a49c5e5853cad6d7456b1
ms.sourcegitcommit: db680e8fa8066f905e7f9240342ece7ab9259308
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2018
ms.locfileid: "37924430"
---
# <a name="learn-app-building-basics-with-xamarinforms-in-visual-studio"></a>Visual Studio'da Xamarin.Forms ile uygulama oluşturmaya yönelik temel bilgileri öğrenin

Adımları yaptıktan sonra [Kurulum ve yükleme](../cross-platform/setup-and-install.md) ve [Xamarin ortamınızı doğrulama](../cross-platform/verify-your-xamarin-environment.md), bu izlenecek yol, Xamarin.Forms ile temel bir uygulama oluşturma işlemini göstermektedir. Xamarin.Forms ile UI kodunuzun tamamını bir kez bir .NET standart sınıf kitaplığında yazmanız. Xamarin sonra otomatik olarak işleme iOS, Android ve evrensel Windows için yerel kullanıcı Arabirimi denetimleri platformlar.

Genellikle bu ortak kodun bir paylaşılan proje yerine bir .NET Standard kitaplığı kullanmak daha iyidir. Tüm Hedef platformlar üzerinde çalışabilen bu .NET API .NET Standard kitaplığı içerir.

Burada, oluşturacağınız uygulamasıdır. İOS ve Android telefonlar ve Windows 10 Evrensel Windows Platformu (UWP) (soldan sağa) çalıştığı:

[![İOS, Android ve UWP hava durumu uygulaması örneği](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")](../cross-platform/media/crossplat-xamarin-formsguide-1-Large.png#lightbox)

Bu uygulamayı oluşturmak için aşağıdaki adımları gerçekleştirin:

-   [Çözümünüzü ayarlama](#solution)

-   [Paylaşılan veri hizmeti kod yazma](#dataservice)

-   [Paylaşılan kullanıcı Arabirimi kod yazmaya başlayın](#uicode)

-   [Android için Visual Studio öykünücüsü'nü kullanarak uygulamanızı test edin](#test)

-   [Yerel bir görünüme kullanıcı Arabirimiyle platformlar arasında son](#finish)

> [!TIP]
> Bu proje için tam kaynak kodunu bulabilirsiniz [xamarin forms örnekleri GitHub deposunda](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather).

<a name="solution" />

## <a name="set-up-your-solution"></a>Çözümünüzü ayarlama

Bu adımlar paylaşılan kod için bir .NET Standard sınıf kitaplığı ve iki eklenen NuGet paketlerini içeren bir Xamarin.Forms çözümü oluşturun.

1. Visual Studio'da yeni bir oluşturma **platformlar arası uygulama (Xamarin.Forms)** çözüm ve adlandırın **WeatherApp**. Şablonu seçerek görüneceğini **Visual C#** ve **platformlar arası** soldaki listeden.

    ![Yeni platformlar arası Xamarin.Forms uygulaması projesi oluşturma](../cross-platform/media/crossplat-xamarin-formsguide-2.png "CrossPlat Xamarin FormsGuide 2")

    Bir şablon yoksa, Xamarin'i yükleyin veya Visual Studio 2017 özelliği etkinleştirmeniz gerekebilir. Bkz: [Kurulum ve yükleme](../cross-platform/setup-and-install.md).

2.  Tamam'a tıkladıktan sonra bazı seçenekler seçme fırsatı sahip olacaksınız. Çekme **boş uygulama** ve **.NET Standard**:

    ![Yeni bir Çapraz Platform uygulaması projesi oluşturma](../cross-platform/media/crossplat-xamarin-formsguide-3.png "CrossPlat Xamarin FormsGuide 3")

3.  Çözümü oluşturmak için Tamam'a tıkladıktan sonra dört projeleri içeren bir çözüm gerekir:

    -   **WeatherApp**: Burada, dahil olmak üzere genel iş mantığı ve UI kodunu kullanarak Xamarin.Forms platformlar arasında paylaşılan kod yazma .NET Standard kitaplığı.

    -   **WeatherApp.Android**: projenin yerel Android kodunu içerir.

    -   **WeatherApp.iOS**: yerel iOS kodu içeren bir proje.

    -   **WeatherApp.UWP**: Windows 10 UWP kodu içeren bir proje.

    > [!NOTE]
    >  Projelerin değil hedeflediğiniz platform için silmek boş.

     Her yerel proje içinde karşılık gelen bir platform için yerel Tasarımcı erişimi vardır ve platforma özgü ekranları ve gerektiğinde işlevi uygulayabilirsiniz.

4.  Çözümünüzdeki Xamarin.Forms NuGet paketini en son kararlı sürüme aşağıdaki gibi yükseltin:

    -   Seçin **Araçlar > NuGet Paket Yöneticisi > çözüm için NuGet paketlerini Yönet**.

    -   Altında **güncelleştirmeleri** sekmesinde, onay **Xamarin.Forms** paketini ve çözümünüzdeki tüm projeleri güncelleştir denetleyin. (Güncelleştirmeler için Xamarin Android desteği kitaplıklarını kendim seçmeyin.)

    -   Güncelleştirme **sürüm** alanı **en son kararlı** kullanılabilir olan sürümü.

    -   **Yükle**'ye tıklatın.

         ![Xamarin.Forms NuGet paketi güncelleştirme](../cross-platform/media/crossplat-xamarin-formsguide-4.png "CrossPlat Xamarin FormsGuide 4")

    Yeni bir Xamarin.Forms çözümü oluşturduğunuzda, bir Xamarin.Forms sürümünden yükseltme alýþkanlýk almanız gerekir. Tüm Android desteği kitaplıklarını kendim güncelleştirmez. Xamarin.Forms sürüm güncelleştirdiğinizde, gerekirse, bu kitaplıkları güncelleştirilecektir.

5.  Ekleme **Newtonsoft.Json** NuGet paketini **WeatherApp** proje. Bu kitaplık, hava durumu verileri hizmetten alınan bilgileri işlemek için kullanılır:

    -   NuGet Paket Yöneticisi'nde (4. adımdan hala açık) **Gözat** sekmesinde ve arama **Newtonsoft**.

    -   Seçin **Newtonsoft.Json**.

    -   Denetleme **WeatherApp** gerektiği paketini yüklemek yalnızca bir proje olan proje.

    -   Olun **sürüm** ayarlanmış **en son kararlı** sürümü.

    -   **Yükle**'ye tıklatın.

    ![Bulma ve Newtonsoft.Json NuGet paketini yükleme](../cross-platform/media/crossplat-xamarin-formsguide-5.png "CrossPlat Xamarin FormsGuide 5")

6.  Bulmak ve yüklemek için 5. adımı yineleyin **Microsoft.CSharp** .NET Standard projesi bir pakette. Bu kitaplık C# kullanmaya gerek `dynamic` .NET Standard Kitaplığı'nda veri türü.

7.  Çözümünüzü oluşturun ve herhangi bir yapı hatası olmadığını doğrulayın.

<a name="dataservice" />

## <a name="write-shared-data-service-code"></a>Paylaşılan veri hizmeti kod yazma

**WeatherApp** .NET Standard kitaplığı projesi olduğundan burada tüm platformlar arasında paylaşılabilir kod yazacaksınız. Bu kitaplık, uygulama tarafından başvurulan paketleri iOS, Android ve Windows projeleri oluşturun.

Bu örneği çalıştırmak için önce boş bir API anahtarı için kaydolmalısınız [ http://openweathermap.org/appid ](http://openweathermap.org/appid).

Aşağıdaki adımlar bu durumda, hava durumu hizmetinden veri depolamak ve erişmek için .NET Standard kitaplığı kodu ekleyin:

1.  Sağ **WeatherApp** seçin ve proje **Ekle > sınıfı...** . İçinde **Yeni Öğe Ekle** iletişim kutusunda, dosya adı **Weather.cs**. Bu sınıf, hava durumu verileri hizmetten alınan verileri depolamak için kullanacaksınız.

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

3.  Başka bir sınıfa eklemek **WeatherApp** adlı proje **DataService.cs** hava durumu verileri hizmetten JSON verilerini işleme için kullanacağınız.

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

5.  Bir üçüncü sınıfa eklemek **WeatherApp** adlı proje **Core.cs** paylaşılan iş mantığı burada giriyorum. Bu kod bir posta kodu ile bir sorgu dizesi oluşturur, hava durumu verileri hizmetini çağıran ve örneği doldurur `Weather` sınıfı.

6.  Öğesinin içeriğini değiştirin **Core.cs** aşağıdaki kod ile:

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

7. Değiştirin *burada bilgisayarınızı API anahtarı* elde ettiğiniz API anahtarına sahip. Yine, tırnak içine gerekiyor!

8.  Derleme **WeatherApp** kodu doğru olduğundan emin olmak için kitaplığı projesi.

 <a name="uicode" />

## <a name="begin-writing-shared-ui-code"></a>Paylaşılan kullanıcı Arabirimi kod yazmaya başlayın

Xamarin.Forms, .NET Standard Kitaplığı'nda paylaşılan kullanıcı Arabirimi kodunu uygulamak sağlar. Bu adımlarda, projeye bir düğmeye sahip bir sayfa ekleyeceksiniz. Bu düğme önceki bölümde anlatıldığı verilerle sayfasında metni hava durumu hizmeti tarafından döndürülen güncelleştirmeleri:

1.  Ekle bir **içerik sayfası** adlı **WeatherPage** sağ tıklanarak **WeatherApp** proje ve seçerek **Ekle > Yeni öğe...** . İçinde **Yeni Öğe Ekle** iletişim kutusunda **içerik sayfası**. I özen **içerik sayfası (C#)** veya **içerik görünümü**. Adlandırın **WeatherPage.xaml**.

    ![Yeni bir Xamarin.Forms XAML sayfası ekleme](../cross-platform/media/crossplat-xamarin-formsguide-6.png "CrossPlat Xamarin FormsGuide 6")

     Xamarin.Forms XAML tabanlı, bu adımı oluşturur bir **WeatherPage.xaml** dosya iç içe geçmiş arka plan kod dosyası ile birlikte **WeatherPage.xaml.cs**. Kullanıcı arabirimi mantığı, XAML veya kod yazabilirsiniz. Bu kılavuzda hem de bazı yaparsınız.

2.  Bir düğme eklemek için **WeatherPage** ekranında, içeriklerini **WeatherPage.xaml** aşağıdaki işaretlemeyle:

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

     Düğmenin adı kullanılarak tanımlanmalıdır fark `x:Name` bu düğme, arka plan kod dosyasında adıyla başvurabilir, böylece öznitelik.

3.  Düğme için bir olay işleyicisi eklemek için `Clicked` düğme metnini güncelleştirme içeriğini değiştirmek için olay **WeatherPage.xaml.cs** aşağıdaki kod ile. ("60601" değiştirmek için başka bir posta kodu çekinmeyin.)

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

4.  Açmak için **WeatherPage** uygulaması başlatıldığında ilk ekran varsayılan oluşturucu değiştirin **App.xaml.cs** aşağıdaki kod ile:

    ```csharp
    public App()
    {
        InitializeComponent();

        MainPage = new NavigationPage(new WeatherPage());
    }
    ```

5.  Derleme **WeatherApp** kodu doğru olduğundan emin olmak için proje.

<a name="test" />

## <a name="test-your-app-using-the-visual-studio-emulator-for-android"></a>Android için Visual Studio öykünücüsü'nü kullanarak uygulamanızı test edin

Uygulamayı çalıştırmak artık hazırsınız! Uygulama hava durumu hizmetinden veri alma doğrulamak şimdilik yalnızca Android sürümü çalıştıralım. Daha sonra daha fazla kullanıcı Arabirimi öğeleri ekledikten sonra da iOS ve UWP sürümlerinde çalıştıracaksınız.

1.  Ayarlama **WeatherApp.Android** tıklayıp seçerek başlangıç projesi olarak proje **başlangıç projesi olarak ayarla**.

2.  Visual Studio araç çubuğunda, gördüğünüz **WeatherApp.Android** hedef projesi olarak listelenir. Hata ayıklama için Android öykünücüleri birini seçin ve isabet **F5**. Aşağıdakilerden birini kullanmanızı öneririz **VisualStudio** uygulama Android için Visual Studio öykünücüsü'nün içinde çalıştırılır öykünücü seçenekleri.

    ![Bir Android öykünücüsü hata ayıklama hedefi seçme](../cross-platform/media/crossplat-xamarin-formsguide-7.png "CrossPlat Xamarin FormsGuide 7")

    > [!NOTE]
    > Visual Studio Android projesi Newtonsoft.Json dosyasını bulamıyor gösteriyorsa, bu NuGet paketi Android projesine ekleyin.

3.  Uygulamayı öykünücüde başlattığında tıklayın **hava durumunu alın** düğmesi. Düğmenin metni için güncelleştirilen görmelisiniz **Chicago**, olduğu `Title` verileri özelliği hava durumu hizmetinden alınır.

     ![Önce ve sonra bir düğmeye dokunarak uygulama hava durumu](../cross-platform/media/crossplat-xamarin-formsguide-8.png "CrossPlat Xamarin FormsGuide 8")

<a name="finish" />

## <a name="finish-the-ui-with-a-native-look-and-feel-across-platforms"></a>Yerel bir görünüme kullanıcı Arabirimiyle platformlar arasında son

Uygulamanızı otomatik olarak yerel bir görünümüne sahip olacak şekilde Xamarin.Forms her platform için yerel kullanıcı Arabirimi denetimleri oluşturur. Bir posta kodu ve hava durumu verileri görüntülemek için denetimler için giriş alanını dahil etmek için kullanıcı Arabirimi tamamlanmasıyla yerel bu görünüme daha net bir şekilde görebilirsiniz.

1.  Öğesinin içeriğini değiştirin **WeatherPage.xaml** aşağıdaki biçimlendirmeye sahip. Kullanılarak adlandırılmış öğeleri `x:Name` daha önce açıklandığı gibi öznitelik koddan başvurulabilir. Xamarin.Forms da çok sayıda sunar [düzen seçeneklerini](/xamarin/xamarin-forms/user-interface/controls/layouts). Burada, WeatherPage kullanıyor [kılavuz](http://developer.xamarin.com/api/type/Xamarin.Forms.Grid/) ve [StackLayout](http://developer.xamarin.com/api/type/Xamarin.Forms.StackLayout/).

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

     Burada gösterilmez, ancak kullanabilirsiniz `OnPlatform` uygulamanın üzerinde çalıştığı geçerli platforma özgü bir özellik değeri seçmek için XAML dosyalarındaki etiket (bkz [temel XAML sözdizimi](/xamarin/xamarin-forms/xaml/xaml-basics/essential-xaml-syntax/).) Arka plan kod dosyasında, uygulamanın çalıştığı karşılaştırarak platformdan belirleyebilirsiniz [ `Device.RuntimePlatform` ](https://developer.xamarin.com/api/property/Xamarin.Forms.Device.RuntimePlatform/) tanımlı sabitler özelliğiyle [ `Device` ](https://developer.xamarin.com/api/type/Xamarin.Forms.Device/) adlısınıfı[ `Device.iOS` ](https://developer.xamarin.com/api/field/Xamarin.Forms.Device.iOS/), [ `Device.Android` ](https://developer.xamarin.com/api/field/Xamarin.Forms.Device.Android/), ve [ `Device.UWP` ](https://developer.xamarin.com/api/field/Xamarin.Forms.Device.UWP/).

2.  İçinde **WeatherPage.xaml.cs**, değiştirin `GetWeatherBtn_Clicked` aşağıdaki kod ile olay işleyicisi. Bu kod doğrular, posta kodu girişi alanında ve, posta kodu için verileri alır. Ortaya çıkan sonra tüm sayfanın bağlama bağlamı ayarlar `Weather` örneği. "Tekrar arama." düğme metnini ayarlayarak, kod burada sona eriyor Kullanıcı arabiriminde her etiket bir özelliğine bağlayan `Weather` sınıfı. Ekranın bağlama bağlamı ayarlandığında bir `Weather` etiketlerin örneği, güncelleştirme otomatik olarak.

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

3.  Uygun projeye sağ tıklayarak uygulamayı üç tüm platformlarda çalıştırın seçerek **başlangıç projesi olarak ayarla**ve bir cihaz veya öykünücü üzerinde uygulama başlatılıyor. Bir geçerli Amerika Birleşik Devletleri beş basamaklı posta kodu ve enter tuşuna basın **hava durumunu alın** bu bölge için hava durumu verileri görüntülemek için düğme. Visual Studio iOS projesi için ağınızdaki bir Mac bilgisayara bağlı olması gerekir.

     [![İOS, Android ve UWP hava durumu uygulaması örneği](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")](../cross-platform/media/crossplat-xamarin-formsguide-1-Large.png#lightbox)

Bu proje için tam kaynak kodu [xamarin forms örnekleri GitHub deposunda](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather).
