---
title: Bulutta - 4. adım - Debug Kubernetes kapsayıcısında bir Kubernetes kullanarak kapsayıcılarla .NET Core geliştirme ortamı oluşturma | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Kapsayıcılar ve Azure üzerinde mikro ile hızlı Kubernetes geliştirme
keywords: Docker, Kubernetes, Azure, AKS, Azure kapsayıcı hizmeti, kapsayıcıları
manager: douge
ms.openlocfilehash: 043052dec78251647a3ef12e0b612355b6334692
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31886299"
---
# <a name="get-started-on-connected-environment-with-net-core"></a>.NET Core bağlı ortamıyla kullanmaya başlama
 
Önceki adımda: [bir ASP.NET çekirdek Web uygulaması oluşturma](get-started-netcore-03.md)

[!INCLUDE[](includes/debug-intro.md)]

[!INCLUDE[](includes/init-debug-assets-vscode.md)]


## <a name="select-the-vsce-debug-configuration"></a>VSCE hata ayıklama yapılandırmasını seçin
1. Hata ayıklama görünümünü açmak için hata ayıklama simgeyi tıklatın **etkinlik çubuğu** VS Code yan tarafında.
1. Seçin **.NET Core başlatın (VSCE)** etkin hata ayıklama yapılandırması.

![](media/debug-configuration.png)

> [!Note]
> Herhangi bir komut palet bağlı ortam komut görmüyorsanız, olduğundan emin olun [VS Code uzantısı bağlı ortamı için yüklenen](get-started-netcore-01.md#get-kubernetes-debugging-for-vs-code).


## <a name="debug-the-container-in-kubernetes"></a>Kubernetes kapsayıcısında hata ayıklama
İsabet **F5** Kubernetes kodunuzda hata ayıklamak için.

İle `up` komutu, kod geliştirme ortamına eşitlenen ve bir kapsayıcı oluşturulur ve Kubernetes için dağıtılabilir. Bu süre, doğal olarak, hata ayıklayıcıyı uzak kapsayıcıya eklendi.

[!INCLUDE[](includes/tip-vscode-status-bar-url.md)]

Bir kesme noktası bir sunucu tarafı kodu dosyasında, örneğin içinde ayarlanan `Index()` işlevi `Controllers/HomeController.cs` kaynak dosyası. Tarayıcı sayfayı yenilemeyi kesme noktası isabet neden olur.

Hata ayıklama kodu yerel olarak çalıştırma çağrı yığını, yerel değişkenleri, özel durum bilgileri, vb. gibi yaptığınız gibi bilgileri için tam erişime sahip.

## <a name="edit-code-and-refresh"></a>Kod ve yenileme Düzenle
Debugger etkin bir kodu Düzenle olun. Örneğin, hakkında sayfanın iletisinde değiştirme `Controllers/HomeController.cs`. 

```csharp
public IActionResult About()
{
    ViewData["Message"] = "My custom message in the About page.";
    return View();
}
```

Dosyayı kaydedin ve buna **hata ayıklama Eylemler bölmesi**, tıklatın **yenileme** düğmesi. 

![](media/debug-action-refresh.png)

Yeniden oluşturma ve hangi sıklıkta önemli ölçüde zaman alır, kod düzenlemeler yapılır, her seferinde yeni bir kapsayıcı görüntüsü dağıtarak yerine bağlı ortam artımlı olarak daha hızlı bir düzenleme/debug döngü sağlamak için var olan bir kapsayıcı içindeki kod derlenir.

Tarayıcıda web uygulamasını yenileyin ve hakkında sayfasına gidin. Kullanıcı Arabiriminde görünen özel mesajınız görmeniz gerekir.

**Şimdi hızlı bir şekilde kodu yineleme ve doğrudan Kubernetes içinde hata ayıklama için bir yöntem var!** Ardından, nasıl biz oluşturabilir ve ikinci bir kapsayıcı çağrısı göreceğiz.

> [!div class="nextstepaction"]
> [Ayrı bir kapsayıcıda çalışan bir hizmete çağrı](get-started-netcore-05.md)
