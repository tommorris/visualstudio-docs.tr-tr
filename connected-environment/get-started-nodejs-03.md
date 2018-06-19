---
title: Bir Node.js geliştirme ortamı oluşturma kapsayıcıları Kubernetes - adım 3 - bulutta kullanarak bir ASP.NET web uygulaması oluşturma | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: douge
ms.openlocfilehash: 34e1f07e173ccba6aab561fb4795abbe938e0127
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31890160"
---
# <a name="get-started-on-connected-environment-with-nodejs"></a>Node.js ile bağlı ortam kullanmaya başlama

Önceki adımda: [Kubernetes geliştirme ortamı oluşturma](get-started-nodejs-02.md)

## <a name="create-a-nodejs-web-app"></a>Bir Node.js Web uygulaması oluşturma
Kod giderek Github'dan indirdiğinizde https://github.com/Azure/vsce seçip **kopyalama veya indirme** yerel ortamınız için GitHub deposuna yüklemek için. Bu kılavuzun kod `vsce/samples/nodejs/getting-started/webfrontend`.

[!INCLUDE[](includes/vsce-init.md)]

[!INCLUDE[](includes/ensure-env-created.md)]

[!INCLUDE[](includes/build-and-run-in-k8s-cli.md)]

## <a name="update-a-content-file"></a>Bir içerik dosyası güncelleştir
Bağlı ortamı değil yalnızca çalışan kodu alma hakkında Kubernetes içinde - bu, hızlı ve yinelemeli olarak bulutta Kubernetes ortamında etkili kod değişiklikleri görmek almaktan ibarettir.

1. Dosyayı bulmak `./public/index.html` ve HTML düzenlersiniz olun. Örneğin, bir mavi gölgelendirme için sayfanın arka plan rengini değiştirin:

```html
<body style="background-color: #95B9C7; margin-left:10px; margin-right:10px;">
```

2. Dosyayı kaydedin. Dakika daha sonra Terminal penceresinde çalışan kapsayıcı dosyasında güncelleştirildi söyleyen bir ileti görürsünüz.
1. Tarayıcınıza gidin ve sayfayı yenileyin. Güncelleştirme renginiz görmeniz gerekir.

Ne oldu? HTML ve CSS, gibi içerik dosyalarına düzenlemeleri yeniden başlatmak için bunu Node.js işlemi gerektirir yok etkin bir `vsce up` komutu otomatik olarak senkronize değiştirilmiş tüm içerik dosyalarını böylece görmek için hızlı bir yol sağlayan Azure çalışan kapsayıcısında doğrudan, İçerik düzenlemeler.

### <a name="test-from-a-mobile-device"></a>Bir mobil aygıttan test
Mobil aygıttaki web uygulamasını açın, UI küçük bir aygıtta düzgün görüntülenmiyor fark edeceksiniz.

Bu sorunu gidermek için ekleyeceğiz bir `viewport` meta etiketi:
1. Dosyasını açın `./public/index.html`
1. Ekleme bir `viewport` mevcut meta etiketi `head` öğe:

```html
<head>
    <!-- Add this line -->
    <meta name="viewport" content="width=device-width, initial-scale=1">
</head>
```

1. Dosyayı kaydedin.
1. Cihazınızın tarayıcıyı yenileyin. Doğru çizilir web uygulaması görmelisiniz. 

Bu uygulama kullanılması amaçlanmıştır cihazlarda test kadar bazı sorunlar yalnızca nasıl bulunan olmayan bir örnektir. Hızlı bir şekilde bağlı VS ortamıyla kodunuz üzerinde yinelemek ve hedef cihazlar herhangi bir değişiklik doğrulayın.

## <a name="update-a-code-file"></a>Kod dosyasını güncelleştirme
Sunucu tarafı kodu dosyaları güncelleştirme, bir Node.js uygulamasını yeniden başlatmanız gerektiği için biraz daha fazla iş gerektirir.

1. Terminal penceresinde tuşlarına basın `Ctrl+C` (durdurmak için `vsce up`).
1. Adlı kod dosyasını açma `server.js`ve hizmetin selamlama iletisine düzenleyin: 

```javascript
res.send('Hello from webfrontend running in Azure!');
```

3. Dosyayı kaydedin.
1. Çalıştırma `vsce up` terminal penceresinde. 

Bu kapsayıcı görüntü yeniden oluşturur ve Helm grafik yeniden dağıtır. Kod değişikliklerinizin etkili görmek için tarayıcı sayfayı yeniden yükleyin.


Ancak bir bile *daha hızlı yöntem* sonraki bölümde ele alacağız kodu geliştirmek için. 
> [!div class="nextstepaction"]
> [Kubernetes kapsayıcısında hata ayıklama](get-started-nodejs-04.md)
