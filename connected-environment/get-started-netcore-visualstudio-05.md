---
title: .NET Core geliştirme ortamı Visual Studio - adım 5 - çağrısı ile bulutta Kubernetes kullanarak kapsayıcıları ile başka bir kapsayıcı oluşturun. | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: douge
ms.openlocfilehash: ab3934e6f7f013dd21309dc8c98461983bdfe30a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>Bağlı ortam .NET Core ve Visual Studio ile çalışmaya başlama

Önceki adımda: [Kubernetes kapsayıcısında hata ayıklama](get-started-netcore-visualstudio-04.md)

## <a name="call-another-container"></a>Başka bir kapsayıcı çağırın
Bu bölümde ikinci bir hizmet oluşturmak için yapmamız `mywebapi`ve `webfrontend` adlandırılır. Her hizmet ayrı kapsayıcılarında çalışır. Biz sonra arasında her iki kapsayıcıları hata ayıklama.

![](media/multi-container.png)

## <a name="download-sample-code-for-mywebapi"></a>Örnek kodu indirdikten *mywebapi*
Amacıyla, şimdi örnek kod bir GitHub depodan karşıdan yükleme süresi. Git https://github.com/Azure/vsce seçip **kopyalama veya indirme** GitHub deposuna yüklemek için. Bu bölüm için kod `vsce/samples/dotnetcore/getting-started/mywebapi`.

## <a name="run-mywebapi"></a>Çalıştırma *mywebapi*
1. Projeyi açın `mywebapi` içinde bir *ayrı Visual Studio penceresi*.
1. Seçin **bağlı ortam AKS için** yazarken başlatma ayarları açılır alanından daha önce yaptığınız `webfrontend` projesi. Bu zaman yeni bir geliştirme ortamı oluşturmak yerine, aynı önceden oluşturulmuş seçin. Olarak daha önce alan varsayılan için bırakın `mainline` tıklatıp **Tamam**. Çıkış penceresinde "Bu yeni hizmet geliştirme ortamınızı ayarlama hata ayıklama, başlattığınızda interneti hızlandırmak için normal" Visual Studio başladığında karşılaşabilirsiniz
1. F5'e basın ve hizmet oluşturmak ve dağıtmak bekleyin. Visual Studio durum çubuğu turuncu döndüğünde hazır olduğunu biliyor olmalısınız
1. URL görüntülenen endpoint not edin **bağlı ortam AKS için** bölmesinde **çıkış** penceresinde, onu görünür aşağıdakine benzer http://localhost: \<BağlantıNoktasıNumarası\>. Kapsayıcı yerel olarak çalışıyor, ancak gerçekte Azure bizim geliştirme ortamında çalışıyor gibi görünebilir.
1. Zaman `mywebapi` hazır, localhost adresine tarayıcınızı açın ve sona `/api/values` için varsayılan GET API çağrılacak URL'ye `ValuesController`. 
1. Tüm adımları başarılı olursa, yanıt görüyor olmalısınız `mywebapi` şöyle hizmet.

    ![](images/WebAPIResponse.png)

## <a name="make-a-request-from-webfrontend-to-mywebapi"></a>Gelen istekte *webfrontend* için *mywebapi*
Şimdi kod yazalım `webfrontend` bir istek yapıyorsa `mywebapi`. Geçiş olan Visual Studio penceresi `webfrontend` projesi. İçinde `HomeController.cs` dosya *Değiştir* aşağıdaki hakkında yöntemiyle için kod:

 ```csharp
    public async Task<IActionResult> About()
    {
        ViewData["Message"] = "Hello from webfrontend";
        
        // Use HeaderPropagatingHttpClient instead of HttpClient so we can propagate
        // headers in the incoming request to any outgoing requests
        using (var client = new HeaderPropagatingHttpClient(this.Request))
        {
            // Call *mywebapi*, and display its response in the page
            var response = await client.GetAsync("http://mywebapi/api/values/1");
            ViewData["Message"] += " and " + await response.Content.ReadAsStringAsync();
        }
    
        return View();
    }

```

Kubernetes'DNS hizmet bulma hizmet olarak başvurmak için nasıl işe Not `http://mywebapi`. **Bizim geliştirme ortamında kod üretimde çalışacak şekilde çalışan**.

Yukarıdaki kod örneğinde yapar kullanımını da bir `HeaderPropagatingHttpClient` sınıfı. Bu yardımcı sınıf dosyasıdır `HeaderPropagation.cs` bağlı ortam kullanacak şekilde yapılandırıldığında projenize eklenen. `HeaderPropagatingHttpClient` iyi bilinen türetilen `HttpClient` sınıfı ve belirli üstbilgileri varolan ASP .NET HttpRequest nesnesi giden bir HttpRequestMessage nesnesi yaymak için işlevsellik ekler. Daha sonra nasıl bu takım senaryolarda daha verimli bir geliştirme deneyimi kolaylaştıran göreceğiz.

## <a name="debug-across-multiple-services"></a>Birden fazla hizmet hata ayıklama
1. Bu noktada, `mywebapi` hata ayıklayıcısı ekli hala çalışıyor olması gerekir. Değilse, F5'e basın `mywebapi` projesi.
1. Bir kesme noktası kümesinde `Get(int id)` yönteminde `ValuesController.cs` işler dosya `api/values/{id}` GET istekleri.
1. İçinde `webfrontend` projesini Yukarıdaki kod biz yapıştırılan burada yalnızca bir GET isteği göndermeden önce bir kesme noktası ayarlayın `mywebapi/api/values`.
1. F5'e basın `webfrontend` projesi. Visual Studio yeniden uygun localhost bağlantı noktasına bir tarayıcı açın ve web uygulaması görüntülenir.
1. Tıklayın "**hakkında**" bağlantı kesme tetiklemek için sayfanın üstündeki `webfrontend` projesi. 
1. Devam etmek için F10'a basın. Kesme `mywebapi` proje şimdi tetiklenir.
1. Devam etmek için isabet F5 ve olacak geri kodda `webfrontend` projesi.
1. Bir kez daha F5 tuşuna isteği tamamlamak ve tarayıcıda bir sayfaya dönün. Web uygulaması hakkında sayfa iki Hizmetleri tarafından birleştirilmiş bir ileti görüntülenir: "Hello ifadesini webfrontend ve mywebapi gelen Hello".

Bravo! Artık burada her kapsayıcı kullanılabilir geliştirilen ve ayrı olarak dağıtılan bir çok kapsayıcı uygulama var.

> [!div class="nextstepaction"]
> [Takım geliştirme hakkında bilgi edinin](get-started-netcore-visualstudio-06.md)

