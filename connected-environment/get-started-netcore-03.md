---
title: Bir .NET Core geliştirme ortamı oluşturma kapsayıcıları Kubernetes - adım 3 - bulutta kullanarak bir ASP.NET Core web uygulaması oluşturma | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: ghogen
ms.openlocfilehash: f858a013e4b0c2ce1c30b8f26f2dc33eebf19c27
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-on-connected-environment-with-net-core"></a>.NET Core bağlı ortamıyla kullanmaya başlama

Önceki adımda: [Kubernetes geliştirme ortamı oluşturma](get-started-netcore-02.md)

## <a name="create-an-aspnet-core-web-app"></a>Bir ASP.NET Core Web uygulaması oluşturma
Varsa [.NET Core](https://www.microsoft.com/net) yüklü, hızlı bir şekilde ASP.NET çekirdek Web uygulamasını adlı bir klasörde oluşturabileceğiniz `webfrontend`.
```cmd
dotnet new mvc --name webfrontend
```

Alternatif olarak, **Github'dan örnek kodu indirdikten** giderek https://github.com/Azure/vsce seçip **kopyalama veya indirme** yerel ortamınız için GitHub deposuna yüklemek için. Bu kılavuzun kod `vsce/samples/dotnetcore/getting-started/webfrontend`.

[!INCLUDE[](includes/vsce-init.md)]

[!INCLUDE[](includes/ensure-env-created.md)]

[!INCLUDE[](includes/build-and-run-in-k8s-cli.md)]

## <a name="update-a-content-file"></a>Bir içerik dosyası güncelleştir
Bağlı ortamı değil yalnızca çalışan kodu alma hakkında Kubernetes içinde - bu, hızlı ve yinelemeli olarak bulutta Kubernetes ortamında etkili kod değişiklikleri görmek almaktan ibarettir.

1. Dosyayı bulmak `./Views/Home/Index.cshtml` ve HTML düzenlersiniz olun. Örneğin, okur 70 satırı değiştirin `<h2>Application uses</h2>` gibi bir: `<h2>Hello k8s in Azure!</h2>`
1. Dosyayı kaydedin. Dakika daha sonra Terminal penceresinde çalışan kapsayıcı dosyasında güncelleştirildi söyleyen bir ileti görürsünüz.
1. Tarayıcınıza gidin ve sayfayı yenileyin. Güncelleştirilmiş HTML görüntülemek web sayfasını görmeniz gerekir.

Ne oldu? HTML ve CSS, gibi içerik dosyalarına düzenlemeleri yok gerektiren bir .NET Core web uygulamasında yeniden derleme kadar etkin bir `vsce up` komutu otomatik olarak senkronize değiştirilmiş tüm içerik dosyalarını böylece içeriğinizi görmek için hızlı bir yol sağlayan Azure çalışan kapsayıcısında içine düzenler.

## <a name="update-a-code-file"></a>Kod dosyasını güncelleştirme
Kod dosyaları güncelleştirme, .NET Core uygulama yeniden oluşturun ve güncelleştirilmiş uygulama ikili dosyaları üretmek gerektiğinden, biraz daha fazla iş gerektirir.

1. Terminal penceresinde tuşlarına basın `Ctrl+C` (durdurmak için `vsce up`).
1. Adlı kod dosyasını açma `Controllers/HomeController.cs`ve hakkında sayfasında görüntülenecek iletiyi düzenleyin: `ViewData["Message"] = "Your application description page.";`
1. Dosyayı kaydedin.
1. Çalıştırma `vsce up` terminal penceresinde. 

Bu kapsayıcı görüntü yeniden oluşturur ve Helm grafik yeniden dağıtır. Uygulama çalışırken etkili kod değişiklikleri görmek için web uygulamasında hakkında menüsüne gidin.


Ancak bir bile *daha hızlı yöntem* sonraki bölümde ele alacağız kodu geliştirmek için. 
> [!div class="nextstepaction"]
> [Kubernetes kapsayıcısında hata ayıklama](get-started-netcore-04.md)

