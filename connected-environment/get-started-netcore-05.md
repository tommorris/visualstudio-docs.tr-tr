---
title: Bir .NET Core geliştirme ortamı oluşturma - adım 5 - bulutta Kubernetes kullanarak kapsayıcıları çağrı başka bir kapsayıcı | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: douge
ms.openlocfilehash: 6ef3a79d0b79feae64adcaebe31daa48ba75ab75
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31887342"
---
# <a name="get-started-on-connected-environment-with-net-core"></a>.NET Core bağlı ortamıyla kullanmaya başlama

Önceki adımda: [Kubernetes kapsayıcısında hata ayıklama](get-started-netcore-04.md)

Bu bölümde ikinci bir hizmet oluşturmak için yapmamız `mywebapi`ve `webfrontend` adlandırılır. Her hizmet ayrı kapsayıcılarında çalışır. Biz sonra arasında her iki kapsayıcıları hata ayıklama.

![](media/multi-container.png)

## <a name="download-sample-code-for-mywebapi"></a>Örnek kodu indirdikten *mywebapi*
Amacıyla, şimdi örnek kod bir GitHub depodan karşıdan yükleme süresi. Git https://github.com/Azure/vsce seçip **kopyalama veya indirme** GitHub deposuna yüklemek için. Bu bölüm için kod `vsce/samples/dotnetcore/getting-started/mywebapi`.


## <a name="run-mywebapi"></a>Çalıştırma *mywebapi*
1. Klasörü açın `mywebapi` içinde bir *ayrı VS Code pencere*.
1. F5'e basın ve hizmet oluşturmak ve dağıtmak bekleyin. VS Code hata ayıklama çubuğu görüntülendiğinde hazır anlarsınız.
1. Not uç nokta URL'sini şu şekilde görünür http://localhost: \<BağlantıNoktasıNumarası\>. **İpucu: VS Code durum çubuğu tıklanabilir bir URL görüntülenir.** Kapsayıcı yerel olarak çalışıyor, ancak gerçekte Azure bizim geliştirme ortamında çalışıyor gibi görünebilir. Localhost adresi çünkü nedeni `mywebapi` ortak uç nokta tanımlı değil ve yalnızca Kubernetes örneği içinde erişilebilir. Size kolaylık sağlamak için ve yerel makinenize özel hizmetinden etkileşimde kolaylaştırmak için bağlı ortam Azure'da çalışan kapsayıcısı geçici bir SSH tüneli oluşturur.
1. Zaman `mywebapi` olan hazır, localhost adresine tarayıcınızı açın. Append `/api/values` için varsayılan GET API çağrılacak URL'ye `ValuesController`. 
1. Tüm adımları başarılı olursa, yanıt görüyor olmalısınız `mywebapi` hizmet.


## <a name="make-a-request-from-webfrontend-to-mywebapi"></a>Gelen istekte *webfrontend* için *mywebapi*
Şimdi kod yazalım `webfrontend` bir istek yapıyorsa `mywebapi`.
1. Geçiş için VS Code penceresine `webfrontend`.
1. *Değiştir* hakkında yöntemi için kod:

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

Yukarıdaki kod örneğinde yapar kullanımını da bir `HeaderPropagatingHttpClient` sınıfı. Bu yardımcı sınıf kodu klasörünüze çalıştırdığınız zaman eklendi `vsce init`. `HeaderPropagatingHttpClient` iyi bilinen gelen dervied olan `HttpClient` sınıfı ve belirli üstbilgileri varolan ASP .NET HttpRequest nesnesi giden bir HttpRequestMessage nesnesi yaymak için işlevsellik ekler. Daha sonra nasıl bu takım senaryolarda daha verimli bir geliştirme deneyimi kolaylaştıran göreceğiz.


## <a name="debug-across-multiple-services"></a>Birden fazla hizmet hata ayıklama
1. Bu noktada, `mywebapi` hata ayıklayıcısı ekli hala çalışıyor olması gerekir. Değilse, F5'e basın `mywebapi` projesi.
1. Bir kesme noktası kümesinde `Get(int id)` işleme yöntemi `api/values/{id}` GET istekleri.
1. İçinde `webfrontend` proje, yalnızca bir GET isteği göndermeden önce bir kesme noktası belirleyerek `mywebapi/api/values`.
1. F5'e basın `webfrontend` projesi.
1. Web uygulaması çağırır ve her iki hizmet kodda adım adım.
1. Web uygulaması hakkında sayfa iki Hizmetleri tarafından birleştirilmiş bir ileti görüntülenir: "Hello ifadesini webfrontend ve mywebapi gelen Hello".


Bravo! Artık burada her kapsayıcı kullanılabilir geliştirilen ve ayrı olarak dağıtılan bir çok kapsayıcı uygulama var.

> [!div class="nextstepaction"]
> [Takım geliştirme hakkında bilgi edinin](get-started-netcore-06.md)

