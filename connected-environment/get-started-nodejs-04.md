---
title: Bulutta - 4. adım - Debug Kubernetes kapsayıcısında bir Kubernetes kullanarak kapsayıcıları ile bir Node.js geliştirme ortamı oluşturun | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: douge
ms.openlocfilehash: 2d1ec5fe0436b394083a247faa4519505aa21ceb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-nodejs"></a>Node.js ile bağlı ortam kullanmaya başlama

Önceki adımda: [Kubernetes içinde bir Node.js kapsayıcı oluşturma](get-started-nodejs-03.md)

[!INCLUDE[](includes/debug-intro.md)]

[!INCLUDE[](includes/init-debug-assets-vscode.md)]


## <a name="select-the-vsce-debug-configuration"></a>VSCE hata ayıklama yapılandırmasını seçin
1. Hata ayıklama görünümünü açmak için hata ayıklama simgeyi tıklatın **etkinlik çubuğu** VS Code yan tarafında.
1. Seçin **başlatma programı (VSCE)** etkin hata ayıklama yapılandırması.

![](media/debug-configuration-nodejs.png)

> [!Note]
> Herhangi bir komut palet bağlı ortam komut görmüyorsanız, olduğundan emin olun [VS Code uzantısı bağlı ortamı için yüklenen](get-started-nodejs-01.md#get-kubernetes-debugging-for-vs-code).

## <a name="debug-the-container-in-kubernetes"></a>Kubernetes kapsayıcısında hata ayıklama
İsabet **F5** Kubernetes kodunuzda hata ayıklamak için!

Benzer şekilde `up` komutu, kod hata ayıklama başlattığınızda ve bir kapsayıcı oluşturulur ve Kubernetes için dağıtılan geliştirme ortamına eşitlendi. Bu süre, doğal olarak, hata ayıklayıcıyı uzak kapsayıcıya eklendi.

[!INCLUDE[](includes/tip-vscode-status-bar-url.md)]

Bir kesme noktası bir sunucu tarafı kodu dosyasında, örneğin içinde ayarlanan `app.get('/api'...` içinde `server.js`. Tarayıcı sayfayı yenileyin veya 'Say onu yeniden' düğmesine basın ve kesme noktası isabet ve kod üzerinden adım mümkün olmayacaktır.

Hata ayıklama kodu yerel olarak çalıştırma çağrı yığını, yerel değişkenleri, özel durum bilgileri, vb. gibi yaptığınız gibi bilgileri için tam erişime sahip.

## <a name="edit-code-and-refresh-the-debug-session"></a>Kod düzenleme ve hata ayıklama oturumu yenileyin
Debugger etkin bir kodu Düzenle olun; Örneğin, selamlama iletisine yeniden değiştirin:

```javascript
app.get('/api', function (req, res) {
    res.send('**** Hello from webfrontend running in Azure! ****');
});
```

Dosyayı kaydedin ve buna **hata ayıklama Eylemler bölmesi**, tıklatın **yenileme** düğmesi. 

![](media/debug-action-refresh-nodejs.png)

Yeniden oluşturma ve hangi sıklıkta önemli ölçüde zaman alır, kod düzenlemeler yapılır, her seferinde yeni bir kapsayıcı görüntüsü dağıtarak yerine bağlı ortam Node.js işlemi daha hızlı bir düzenleme/debug döngü sağlamak için hata ayıklama oturumları arasında yeniden başlatır.

Web uygulaması tarayıcı veya press yenileme *onu Say yeniden* düğmesi. Kullanıcı Arabiriminde görünen özel mesajınız görmeniz gerekir.


## <a name="use-nodemon-to-develop-even-faster"></a>Daha hızlı geliştirmek için NodeMon kullanma
*Nodemon* Node.js geliştiricileri kullanan hızlı geliştirme için yaygın olarak kullanılan bir araçtır. El ile düğümü işlemi sunucu tarafı kodu düzenleme yapılan her zaman yeniden başlatmak yerine, geliştiriciler genellikle sağlamak için bunların düğümü proje yapılandıracak *nodemon* dosya değişikliklerini izleme ve sunucu işlemi otomatik olarak yeniden başlatın. Bu çalışma stilde Geliştirici yalnızca tarayıcısında kodu Düzenle yaptıktan sonra yeniler.

Bağlı ortam amacı, yerel olarak geliştirirken uygulamadığınız aynı, üretken geliştirme iş akışları kullanabilmek için ' dir. Bu örnek göstermeye `webfrontend` proje kullanacak şekilde yapılandırılmışsa *nodemon* (dev bağımlılık olarak yapılandırılmış `package.json`).

Aşağıdakileri deneyin:
1. VS Code hata ayıklayıcıyı.
1. Hata ayıklama simgesine tıklayarak **etkinlik çubuğu** VS Code yan tarafında. 
1. Seçin **ekleme (VSCE)** etkin hata ayıklama yapılandırması.
1. F5'e basın.

Bu yapılandırmada, kapsayıcı başlatılacak şekilde yapılandırılmış *nodemon*. Sunucu kodu düzenlemeleri yapıldığında, *nodemon* yalnızca yerel olarak geliştirirken yaptığı gibi düğümü işlemi otomatik olarak yeniden başlatır. 
1. Merhaba iletisinde yeniden düzenleme `server.js`ve dosyayı kaydedin.
1. Tarayıcıyı yenileyin veya tıklatın *onu Say yeniden* etkili yaptığınız değişiklikleri görmek için düğmeyi!

**Şimdi hızlı bir şekilde kodu yineleme ve doğrudan Kubernetes içinde hata ayıklama için bir yöntem var!** Ardından, nasıl biz oluşturabilir ve ikinci bir kapsayıcı çağrısı göreceğiz.

> [!div class="nextstepaction"]
> [Ayrı bir kapsayıcıda çalışan bir hizmete çağrı](get-started-nodejs-05.md)

