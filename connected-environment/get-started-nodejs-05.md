---
title: Bir Node.js geliştirme ortamı oluşturma - adım 5 - bulutta Kubernetes kullanarak kapsayıcıları çağrı başka bir kapsayıcı | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: douge
ms.openlocfilehash: 89565869feec746aff75327b59ee7d0b466f26c1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31887511"
---
# <a name="get-started-on-connected-environment-with-nodejs"></a>Node.js ile bağlı ortam kullanmaya başlama

Önceki adımda: [Kubernetes kapsayıcısında hata ayıklama](get-started-nodejs-04.md)

Bu bölümde ikinci bir hizmet oluşturmak için yapmamız `mywebapi`ve `webfrontend` adlandırılır. Her hizmet ayrı kapsayıcılarında çalışır. Biz sonra arasında her iki kapsayıcıları hata ayıklama.

![](media/multi-container.png)

## <a name="open-sample-code-for-mywebapi"></a>Açmak için örnek kod *mywebapi*
Örnek kod için zaten yüklü olmalıdır `mywebapi` adlı bir klasörü altında bu kılavuzun `vsce/samples` (değilse, Git https://github.com/Azure/vsce seçip **kopyalama veya indirme** GitHub deposuna yüklemek için.) Bu bölüm için kod `vsce/samples/nodejs/getting-started/mywebapi`.

## <a name="run-mywebapi"></a>Çalıştırma *mywebapi*
1. Klasörü açın `mywebapi` içinde bir *ayrı VS Code pencere*.
1. F5'e basın ve hizmet oluşturmak ve dağıtmak bekleyin. VS Code hata ayıklama çubuğu görüntülendiğinde hazır anlarsınız.
1. Not uç nokta URL'sini şu şekilde görünür http://localhost: \<BağlantıNoktasıNumarası\>. **İpucu: VS Code durum çubuğu tıklanabilir bir URL görüntülenir.** Kapsayıcı yerel olarak çalışıyor, ancak gerçekte Azure bizim geliştirme ortamında çalışıyor gibi görünebilir. Localhost adresi çünkü nedeni `mywebapi` ortak uç nokta tanımlı değil ve yalnızca Kubernetes örneği içinde erişilebilir. Size kolaylık sağlamak için ve yerel makinenize özel hizmetinden etkileşimde kolaylaştırmak için bağlı ortam Azure'da çalışan kapsayıcısı geçici bir SSH tüneli oluşturur.
1. Zaman `mywebapi` olan hazır, localhost adresine tarayıcınızı açın. Bir yanıt görmeniz gerekir `mywebapi` hizmet mywebapi gelen ("Merhaba").


## <a name="make-a-request-from-webfrontend-to-mywebapi"></a>Gelen istekte *webfrontend* için *mywebapi*
Şimdi kod yazalım `webfrontend` bir istek yapıyorsa `mywebapi`.
1. Geçiş için VS Code penceresine `webfrontend`.
1. Bu kod satırları en üstünde eklemek `server.js`:
```javascript
var request = require('request');
var propagateHeaders = require('./propagateHeaders');
```

3. *Değiştir* kodunu `/api` GET işleyici. Bir isteği işlerken sırayla yapılan bir çağrı kolaylaştırır `mywebapi`ve ardından her iki Hizmetleri'nden sonuçları döndürür.

```javascript
app.get('/api', function (req, res) {
    request({
        uri: 'http://mywebapi',
        headers: propagateHeaders.from(req) // propagate headers to outgoing requests
    }, function (error, response, body) {
        res.send('Hello from webfrontend and ' + body);
    });
});
```

Kubernetes'DNS hizmet bulma hizmet olarak başvurmak için nasıl işe Not `http://mywebapi`. **Bizim geliştirme ortamında kod üretimde çalışacak şekilde çalışan**.

Yukarıdaki kod örneğinde adlı bir yardımcı modül yararlanan `propagateHeaders`. Bu yardımcı kod klasörünüze çalıştırdığınız zaman eklendi `vsce init`. `propagateHeaders.from()` İşlevi, varolan bir http belirli üstbilgileri yayar. Giden bir istek için üstbilgileri nesnesine IncomingMessage nesnesi. Daha sonra nasıl bu takım senaryolarda daha verimli bir geliştirme deneyimi kolaylaştıran göreceğiz.


## <a name="debug-across-multiple-services"></a>Birden fazla hizmet hata ayıklama
1. Bu noktada, `mywebapi` hata ayıklayıcısı ekli hala çalışıyor olması gerekir. Değilse, F5'e basın `mywebapi` projesi.
1. Varsayılan GET bir kesme noktası belirleyerek `/` işleyicisi.
1. İçinde `webfrontend` proje, yalnızca bir GET isteği göndermeden önce bir kesme noktası belirleyerek `http://mywebapi`.
1. F5'e basın `webfrontend` projesi.
1. Web uygulamasını açın ve her iki hizmet kodda adım adım. Web uygulaması iki Hizmetleri tarafından birleştirilmiş bir ileti görüntülenmelidir: "Hello ifadesini webfrontend ve mywebapi gelen Hello".


Bravo! Artık burada her kapsayıcı kullanılabilir geliştirilen ve ayrı olarak dağıtılan bir çok kapsayıcı uygulama var.

> [!div class="nextstepaction"]
> [Takım geliştirme hakkında bilgi edinin](get-started-nodejs-06.md)
