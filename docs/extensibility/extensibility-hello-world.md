---
title: "Merhaba Dünya | Microsoft Docs"
ms.custom: 
ms.date: 07/10/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f74e1ad1-1ee5-4360-9bd5-d82467b884ca
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 18a0e18589574c689ebbddbaf28448cf5539ad96
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-your-first-extension-hello-world"></a>İlk uzantınızı oluşturma: Merhaba Dünya

Bu Hello World örnek ilk uzantınızın Visual Studio için oluşturmada size yol gösterir. Bu öğreticide Visual Studio için yeni bir komut eklemek nasıl yapacağınızı gösterir.

Bu süreçte şunları öğreneceksiniz nasıl yapılır:

* **[Genişletilebilirlik projesi oluşturma](#create-an-extensibility-project)**
* **[Özel komut ekleme](#add-a-custom-command)**
* **[Kaynak kodunu değiştirme](#modify-the-source-code)**
* **[Çalıştırın](#run-it)**

Bu örnekte, Visual C# özel menü düğmesi "Söyleyin. Hello World!" adlı eklemek için kullanacağınız şuna benzer:

![Hello world komutu](media/hello-world-say-hello-world.png)

## <a name="prerequisites"></a>Önkoşullar

Başlamadan önce yüklediğinizden emin olun **Visual Studio uzantısı geliştirme** gerekir ve örnek kod VSIX şablonu içeren iş yükü.

Not: Herhangi bir sürümünü Visual Studio (Community, Professional veya Enterprise) Visual Studio genişletilebilirlik projesi oluşturmak için kullanabilirsiniz.

## <a name="create-an-extensibility-project"></a>Genişletilebilirlik projesi oluşturma

Adım 1. Gelen **dosya** menüsünde tıklatın **yeni proje**. Ekranın alt kısmındaki projenizin adını girebilirsiniz.

Adım 2. Gelen **şablonları** menüsünde tıklatın **Visual C#**, tıklatın **genişletilebilirlik**ve ardından **VSIX proje**.

![Yeni Proje](media/hello-world-new-project.png)

Başlarken sayfa ve bazı örnek kaynaklar görmelisiniz.

Bu öğretici bırakın ve kendisine döndürülmesini ihtiyacınız varsa, yeni HelloWorld projeniz bulabilirsiniz **başlangıç sayfası** içinde **son** bölümü.

## <a name="add-a-custom-command"></a>Özel komut ekleme

Adım 1. Bildirim seçerseniz, hangi seçenekleri örneği, meta verileri, açıklama ve sürüm değiştirilebilir görebilirsiniz.

Adım 2. Proje (çözümü değil) sağ tıklayın. Bağlam menüsünde **Ekle**ve ardından **kullanıcı denetimi**.

Adım 3. Geri dönerek **genişletilebilirlik** bölümünde ve ardından **özel komut**.

4. adım. İçinde **adı** alanında kısımda, Command.cs örneği için bir ad verin.

![özel komut](media/hello-world-custom-command.png)

Yeni komutunuzu listelenen **Çözüm Gezgini** altında **kaynakları** dal. Görüntünün değiştirmek isterseniz, PNG ve ICO dosyaları gibi komutunuzu ilgili diğer dosyaları burada bulabilirsiniz budur.

## <a name="modify-the-source-code"></a>Kaynak kodunu değiştirme

Bu noktada, eklemekte düğmesi oldukça geneldir. Değişiklik yapmak istiyorsanız VSCT dosya ve CS dosya değiştirmeniz gerekir.

* VSCT Burada,, komutlarını yeniden adlandırma yanı sıra Visual Studio komut sisteminde gidebilecekleri tanımlamak dosyasıdır. VSCT dosya keşfetmenizde çok fazla kod denetimlerinin her hangi bir bölümde açıklanmıştır açıklamalı kod fark edeceksiniz.

* Burada click işleyicisi gibi eylemleri tanımlayabilirsiniz CS dosyasıdır.

Adım 1. İçinde **Çözüm Gezgini**, yeni komutunuzu VSCT dosyasını bulun. Bu durumda, CommandPackage.vsct çağrılır.

![komut paket vsct](media/hello-world-command-package-vsct.png)

Adım 2. Değişiklik `ButtonText` "Hello World söylemek için!" parametresi

```xml
  ...
  <Button guid="guidCommandPackageCmdSet" id="CommandId" priority="0x0100" type="Button">
     <Parent guid="guidCommandPackageCmdSet" id="MyMenuGroup" />
     <Icon guid="guidImages" id="bmpPic1" />
     <Strings>
        <ButtonText>Say Hello World!</ButtonText>
     </Strings>
  </Button>
  ...
```

Adım 3. Geri dönerek **Çözüm Gezgini** ve Command.cs dosyasını bulun. Dize değiştirme `message` komutu için `string.Format(..)` "Hello World!" için

```csharp
  ...
  private void MenuItemCallback(object sender, EventArgs e)
  {
    string message = "Hello World!";
    string title = "Command1";

    // Show a message box to prove we were here
    VsShellUtilities.ShowMessageBox(
        this.ServiceProvider,
        message,
        title,
        OLEMSGICON.OLEMSGICON_INFO,
        OLEMSGBUTTON.OLEMSGBUTTON_OK,
        OLEMSGDEFBUTTON.OLEMSGDEFBUTTON_FIRST);
  }
  ...
```

Her dosya için yaptığınız değişiklikleri kaydetmek emin olun.

## <a name="run-it"></a>Çalıştırın

Bu gibi durumlarda, kaynak kodu artık Visual Studio deneysel örneğinde çalıştırabilirsiniz.

Adım 1. Tıklatın **Başlat** araç. Bu, projeyi oluşturun ve Visual Studio adlı yeni bir örneğini başlatma hata ayıklayıcısını başlatma **deneysel örneği**.

Visual Studio başlık çubuğunda "Deneysel örneği" sözcükler görürsünüz.

![deneysel örneği başlık çubuğu](media/hello-world-exp-instance.png)

Adım 2. Üzerinde **Araçları** menüsünü **deneysel örneği**, tıklatın **Say Hello World!**.

![nihai sonucu](media/hello-world-final-result.png)

Bu durumda Merkezi'ndeki iletişim "Hello World!" verir ekran, yeni özel komut bir çıktı görmeniz gerekir İleti.

## <a name="next-steps"></a>Sonraki adımlar

Visual Studio genişletilebilirliğini ile çalışmanın temelleri bildiğinize göre daha fazla bilgi burada şöyledir:

* [Visual Studio uzantıları geliştirmek başlangıç](starting-to-develop-visual-studio-extensions.md) -öğreticiler, örnekler. ve uzantınızı yayımlama.
* [Visual Studio 2017 SDK yenilikler](what-s-new-in-the-visual-studio-2017-sdk.md) -Visual Studio 2017 yeni genişletilebilirlik özellikleri
* [Visual Studio SDK içinde](internals/inside-the-visual-studio-sdk.md) -Visual Studio genişletilebilirliğini ayrıntılarını öğrenin