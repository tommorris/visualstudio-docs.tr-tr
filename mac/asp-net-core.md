---
title: "ASP.NET Core'u kullanmaya başlama"
author: asb3993
ms.author: amburns
ms.date: 07/13/2017
ms.topic: article
ms.assetid: 6E8B0C90-33D6-4546-8207-CE0787584565
ms.openlocfilehash: b494128a26691f9916a0fe2380a5f403e61d21d4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="getting-started-with-aspnet-core"></a>ASP.NET Core'u kullanmaya başlama

 Mac için Visual Studio desteğini uygulamanızın hizmetiyle son ASP.NET çekirdek Web geliştirme platformuna yönelik geliştirme kolay hale getirir. ASP.NET Core .NET Framework ve çalışma zamanı son evrimi .NET Core üzerinde çalışır. Hızlı performans için ayarlanmış, küçük yükleme boyutlarını oluşturmak ve Linux ve macOS yanı üzerinde Windows çalıştırmak için yeniden tasarlandı.

## <a name="installing-net-core"></a>.NET Core yükleme

Mac için Visual Studio yüklediğinizde, .NET core 1.1 otomatik olarak yüklenir

## <a name="creating-an-aspnet-core-app-in-visual-studio-for-mac"></a>Mac için Visual Studio'da ASP.NET Core uygulama oluşturma

Mac için açık Visual Studio Hoş Geldiniz sayfasında seçin **yeni proje...**

![Yeni Proje iletişim kutusu](media/asp-net-core-image1.png)

Bu, uygulamanızı oluşturmak için bir şablon seçin olanak tanıyan yeni proje iletişim kutusu görüntülenir.

ASP.NET Core uygulamanızı oluşturmaya başlamak için önceden oluşturulmuş bir şablonu sağlayacaktır projeleri mevcuttur. Bunlar:

- **.NET core > ASP.NET Core boş Web uygulaması**
- **.NET core > ASP.NET Core Web uygulaması**
- **.NET core > ASP.NET Core Web API'si**
- **Birden çok platform > Uygulama > bağlı uygulama**

![ASP.NET proje seçenekleri](media/asp-net-core-image11.png)

Seçin **ASP.NET Core boş Web uygulaması** ve basın **sonraki**. Proje adı ve tuşuna vermek **oluşturma**. Bu, aşağıdaki görüntü benzemelidir yeni bir ASP.NET Core uygulaması oluşturur:

![Yeni ASP.NET Core boş proje görünümü](media/asp-net-core-image4.png)

ASP.NET Core boş Web uygulaması bir web uygulaması ile iki varsayılan dosyaları oluşturur: **Program.cs** ve **haline**, hangi aşağıda açıklanmıştır. Ayrıca, projenizin NuGet Paket bağımlılıklarını ASP.NET Core, .NET Core framework ve projeyi derlemek MSBuild hedefleri gibi içeren bir bağımlılıklar klasörü oluşturur:

![Çözüm paneli bağımlılıkları görüntüleme](media/asp-net-core-image12.png)

### <a name="programcs"></a>Program.cs

Açmak ve incelemek **Program.cs** projenizdeki dosya. İki içinde gerçekleşmesi gerektiğini fark `Main` yöntemi – uygulamanıza girişi:

```csharp
public static void Main(string[] args)
{
    var host = new WebHostBuilder()
        .UseKestrel()
        .UseContentRoot(Directory.GetCurrentDirectory())
        .UseIISIntegration()
        .UseStartup<Startup>()
        .Build();

    host.Run();
}
```
ASP.NET Core uygulama bir web sunucusunu yapılandırarak ve bir ana bilgisayar örneği aracılığıyla başlatma kendi ana yönteminde oluşturur [ `WebHostBuilder` ](https://docs.microsoft.com/aspnet/core/fundamentals/hosting). Bu oluşturucu yapılandırılması için ana izin vermek için yöntemleri sağlar. Şablon uygulamasında aşağıdaki yapılandırmaları kullanılır:

 * `UseKestrel`: Belirtir Kestrel sunucusu uygulama tarafından kullanılır.
 * `UseContentRoot(Directory.GetCurrentDirectory())`: Web projenin kök klasörü uygulamanın içerik kök olarak uygulamanın bu klasörden başlattığınızda kullanır
 * `.UseIISIntegration()`: Uygulama IIS ile çalışmalıdır belirtir. IIS ASP.NET Core ile hem de kullanmak için `UseKestrel` ve `UseIISIntegration` belirtilmesi gerekir.
 * `.UseStartup<Startup>()`: Başlangıç sınıfı belirtir.

 Derleme ve çalıştırma yöntemleri uygulamayı barındırmak ve bunu gelen HTTP isteklerini dinlemeye IWebHost oluşturun.

### <a name="startupcs"></a>Haline

Uygulamanız için başlangıç sınıfı belirtilen `UseStartup()` yöntemi `WebHostBuilder`. İstek işleme ardışık belirteceksiniz bu sınıfta olduğundan ve diğer hizmetler yapılandırdığınız.

Açmak ve incelemek **haline** projenizi dosyasında:

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
    }

    public void Configure(IApplicationBuilder app, IHostingEnvironment env, ILoggerFactory loggerFactory)
    {
        loggerFactory.AddConsole();

        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }

        app.Run(async (context) =>
        {
            await context.Response.WriteAsync("Hello World!");
        });
    }
}
```

Bu başlangıç sınıfı, her zaman aşağıdaki kurallara uyması gerekir:

 - Her zaman ortak olmalıdır
 - İki genel yöntemini içermelidir: `ConfigureServices` ve`Configure`

`ConfigureServices` Yöntemi, uygulamanız tarafından kullanılan hizmetler tanımlar.

`Configure` İsteği kullanılarak ardışık düzeni oluşturma sayesinde [Ara](https://docs.microsoft.com/aspnet/core/fundamentals/middleware). Bunlar içinde bir ASP.NET uygulaması ardışık düzeni istekleri ve yanıtları işlemek için kullanılan bileşenleridir. İstek temsilciler sırayla çağrılır, çeşitli HTTP ardışık düzen oluşur. Her temsilci isteği ya da sonraki temsilciye geçirmek seçebilirsiniz.

Temsilcileri kullanarak yapılandırabilirsiniz `Run`,`Map`, ve `Use` yöntemlere `IApplicationBuilder`, ancak `Run` yöntemi hiçbir zaman bir sonraki temsilci çağırır ve hattınızı sonunda her zaman kullanılmalıdır.

`Configure` Yöntemi önceden derlenmiş şablon birkaç şey yapmak için oluşturulur. İlk olarak, bir özel durum geliştirme sırasında kullanmak için sayfa işleme yapılandırır. Ardından, istekte bulunan bir basit "Hello World" web sayfası yanıt gönderir.

Bu basit Hello World proje şimdi eklenmekte olan ek kod çalıştırabilirsiniz. Uygulamayı çalıştırın ve tarayıcınızda görüntülemek için araç çubuğunda Yürüt (üç taraflı) düğmesine basın:

![Uygulamayı çalıştırma](media/asp-net-core-image5.png)

Mac için Visual Studio web projenizi başlatmak için rastgele bir bağlantı noktasını kullanır. Bu bağlantı çıkışı bulmaktır, açık altında listelenen uygulama çıktısı **Görünüm > klavye takımı**. Çıktı aşağıda gösterilen benzer bulmanız gerekir:

![Uygulama çıkış dinleme bağlantı noktası görüntüleme](media/asp-net-core-image6.png)

Tercih ettiğiniz tarayıcınızı açın ve girin `http://localhost:5000/`değiştirerek `5000` uygulama çıktıda Visual Studio çıkış bağlantı noktasına sahip. Metin görmelisiniz `Hello World!`:

![Tarayıcı gösteren metin](media/asp-net-core-image7.png)

## <a name="adding-a-controller"></a>Bir denetleyici ekleme

ASP.NET Core uygulamaları Model-View-Controller (MVC) tasarım düzenini tüm uygulama için sorumluluk mantıksal ayırma sağlamak için kullanın. MVC aşağıdakilerden oluşur:

- **Model**: uygulama verilerini temsil eden bir sınıf.
- **Görünüm**: (olduğu çoğunlukla model verileri) uygulamanın kullanıcı arabirimini görüntüler.
- **Denetleyici**: kullanıcı girişini ve etkileşimini tarayıcı isteklerini işleyen bir sınıf yanıt verir.

MVC kullanma hakkında daha fazla bilgi için bkz [ASP.NET Core MVC genel bakış](https://docs.microsoft.com/aspnet/core/mvc/overview) Kılavuzu.

Bir denetleyici eklemek için aşağıdakileri yapın:

1. Proje adına sağ tıklayıp **Ekle > Yeni dosyalar**. Seçin **genel > boş sınıfı**ve bir denetleyici adı girin:

    ![Yeni dosya iletişim kutusu](media/asp-net-core-image8.png)

2. Yeni denetleyicisine aşağıdaki kodu ekleyin:

    ```
    using System;
    using Microsoft.AspNetCore.Mvc;
    using System.Text.Encodings.Web;

    namespace Hello_ASP
    {
        public class HelloWorldController : Controller
        {
            //
            // GET: /HelloWorld/

            public string Index()
            {
                return "This is my default action...";
            }

        }
    }
    ```

3. Ekle `Microsoft.AspNetCore.Mvc` sağ tıklanarak projeye bağımlılık **bağımlılık** klasörü ve seçerek **Paketi Ekle...** .

4. NuGet kitaplığının göz atmak için arama kutusunu kullanmak `Microsoft.AspNetCore.Mvc`seçip **Paketi Ekle**. Bu yüklemek için birkaç dakika sürebilir ve gerekli bağımlılıkları için çeşitli lisans kabul istenebilir:

    ![Nuget ekleme](media/asp-net-core-image9.png)

5. Başlangıç sınıfında kaldırmak `app.Run` lambda ve kümesi MVC tarafından hangi kod belirlemek için kullanılan URL yönlendirme mantığı aşağıdaki çağırma:

    ```csharp
    app.UseMvc(routes =>
    {
        routes.MapRoute(
        name: "default",
        template: "{controller=HelloWorld}/{action=Index}/{id?}");
    });
    ```

    Kaldırdığınızdan emin olun `app.Run` bu olarak lambda yönlendirme mantığı geçersiz kılar.

    MVC çalıştırmak için hangi kod belirlemek için aşağıdaki biçimi kullanır:

    `/[Controller]/[ActionName]/[Parameters]`

    Yukarıdaki kod parçacığında eklediğinizde, varsayılan olarak uygulamaya söylemiş olursunuz `HelloWorld` denetleyicisi ve `Index` eylem yöntemi.

6. Ekleme `services.AddMvc();` çağrısı `ConfigureServices` aşağıda gösterildiği gibi yöntemi:

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();
    }
    ```

    Parametre bilgileri URL'den denetleyiciye de geçirebilirsiniz.

7. Başka bir yöntem, HelloWorldController için aşağıda gösterildiği gibi ekleyin:

    ```csharp
    public string Xamarin(string name)
    {
        return HtmlEncoder.Default.Encode($"Hello {name}, welcome to Visual Studio for Mac");
    }
    ```

8. Uygulamayı şimdi çalıştırırsanız, otomatik olarak tarayıcınızı açın:

    ![Tarayıcıda çalışan uygulama](media/asp-net-core-image13.png)

9. Gözatmak deneyin `http://localhost:xxxx/HelloWorld/Xamarin?name=Amy` (değiştirme `xxxx` doğru bağlantı noktası ile), aşağıdaki görmeniz gerekir:

    ![Bağımsız değişkenlerle tarayıcıda çalışan uygulama](media/asp-net-core-image10.png)


## <a name="troubleshooting"></a>Sorun giderme

.NET Core el ile Mac OS 10.11 sürümünü (El Capitan) ve daha yüksek yüklemeniz gerekiyorsa, aşağıdakileri yapın:

1. .NET Core yüklemeye başlamadan önce en yeni kararlı sürüm için güncelleştirilen tüm işletim sistemi güncelleştirmelerini emin olun. Bu uygulama mağazası uygulamaya giderek ve Güncelleştirmeler sekmesini seçerek kontrol edebilirsiniz.

2. Listelenen adımları izleyin [.NET Core site](https://www.microsoft.com/net/core#macos).

Başarıyla .NET Core başarıyla yüklendiğinden emin olmak için tüm dört adımları tamamlamak emin olun.

## <a name="summary"></a>Özet

Bu kılavuz, ASP.NET Core giriş verdi. Ne, ne zaman, kullanılacağı olduğundan ve bunu Visual Studio'da Mac için kullanarak bilgi sağlanan açıklar
Burada yer alan sonraki adımları hakkında daha fazla bilgi için aşağıdaki kılavuzlara bakın:
- [ASP.NET Core](https://docs.microsoft.com/aspnet/core/#build-web-ui-and-web-apis-using-aspnet-core-mvc) belgeleri.
- [Yerel mobil uygulamalar için arka uç hizmetlerini oluşturma](https://docs.microsoft.com/aspnet/core/mobile/native-mobile-backend), bir Xamarin.Forms uygulaması için ASP.NET Core kullanarak bir REST hizmeti nasıl oluşturulacağını gösterir.
- [ASP.NET Core uygulamalı Laboratuvar](https://github.com/Microsoft/vs4mac-labs/tree/master/Web/Getting-Started).
