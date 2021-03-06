---
title: C# ASP.NET Core web uygulaması oluşturmak için Visual Studio
description: Visual Studio'da C# ve ASP.NET Core, adım adım ile basit bir Hello World web uygulaması oluşturmayı öğrenin.
ms.custom: mvc
ms.date: 07/20/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: quickstart
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 90b1f8209928922c388325163f37f0b1d7e983bb
ms.sourcegitcommit: b9a32c3d94b19e7344f4872bc026efd3157cf220
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135617"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-app"></a>Hızlı Başlangıç: Kullanım ilk ASP.NET Core web uygulamanızı oluşturmak için Visual Studio

Bu 5-10 dakikalık bir giriş Visual Studio'nun nasıl kullanılacağını, bir ASP.NET projesi şablonunu ve C# programlama dilini kullanarak basit bir "Hello World" web uygulaması oluşturacaksınız.

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

## <a name="create-a-project"></a>Proje oluşturma

İlk olarak, bir ASP.NET Core web uygulaması projesi oluşturacaksınız. Proje türü bile herhangi bir şey ekledik önce bir web uygulaması oluşturmak için şablonu dosyalarıyla birlikte gelir!

1. Visual Studio 2017'yi açın.

1. Üstteki menü çubuğundan seçin **dosya** > **yeni** > **proje**.

1. Sol bölmesinde **yeni proje** iletişim kutusunda **Visual C#** ve ardından **.NET Core**. Orta bölmede seçin **ASP.NET Core Web uygulaması**. Ardından dosyanızı adlandırın `HelloWorld` ve **Tamam**.

   ![Yeni ASP.NET Core Web uygulaması projesi oluşturmak için C#](../ide/media/csharp-aspnet-choose-template-name-file.png)

   > [!NOTE]
   > Görmüyorsanız **.NET Core** projesinin şablon kategorisi **açık Visual Studio yükleyicisi** sol bölmede bağlantı.
   >
   > ![Visual Studio yükleyicisi yeni proje iletişim kutusundan açın](../ide/media/open-visual-studio-installer.png)
   >
   > Visual Studio Yükleyicisi'ni başlatır. Seçin **ASP.NET ve web geliştirme** iş yükü ve ardından **Değiştir**.
   >
   > ![ASP.NET iş yükü VS yükleyicisi](../ide/media/quickstart-aspnet-workload.png)
   >
   > (Yeni iş yükünü yüklemek devam etmeden önce Visual Studio'yu kapatın gerekebilir.)

1. İçinde **yeni ASP.NET Core Web uygulaması** iletişim kutusunda, doğrulayın **ASP.NET Core 2.0** üstteki açılan menüde görünür. Ardından, **Web uygulaması** ve **Tamam**.

   ![Yeni ASP.NET Core Web uygulaması iletişim kutusu](../ide/media/quickstart-aspnet-core20.png)

Hemen sonra Visual Studio proje dosyanızı açar.

## <a name="create-the-app"></a>Uygulama oluşturma

1. İçinde **Çözüm Gezgini**, genişletme **sayfaları** klasörünü ve ardından **About.cshtml**.

   ![Çözüm Gezgini'nden About.cshtml dosyayı seçin](../ide/media/csharp-aspnet-about-page-html-file.png)

   Bu dosya adında bir sayfaya karşılık gelen **hakkında** web uygulaması.

   ![Web uygulaması hakkında sayfası](../ide/media/csharp-aspnet-about-page.png)

   Düzenleyicide HTML görürsünüz "ek bilgileri" alanı için kod **hakkında** sayfası.

   ![Visual Studio düzenleyicisinde ek bilgi alanının HTML kodu](../ide/media/csharp-aspnet-about-cshtml-page.png)

1. Okunacak "ek bilgileri" metni değiştirme "**Merhaba Dünya!**".

   ![Visual Studio Düzenleyicisi ek bilgi alanında varsayılan HTML kodunu değiştirme](../ide/media/csharp-aspnet-about-cshtml-page-hello-world.png)

1. İçinde **Çözüm Gezgini**, genişletme **About.cshtml**ve ardından **About.cshtml.cs**. (Bu dosya ayrıca karşılık **hakkında** sayfası, web uygulamanızın.)

   ![Çözüm Gezgini'nden About.cshtml dosyayı seçin](../ide/media/csharp-aspnet-about-page-code-file.png)

   Düzenleyici'de C# göreceğiniz "uygulama açıklaması" alanı için metin içeren kod **hakkında** sayfası.

   ![Visual Studio Düzenleyicisi uygulama açıklama alanında için C# kodu](../ide/media/csharp-aspnet-about-cshtml-cs-code.png)

1. Okunacak "uygulama açıklaması" ileti metni değiştirme "**iletime nedir?**".

   ![Visual Studio Düzenleyicisi'nde uygulama açıklama alanı için varsayılan ileti metni değiştirme](../ide/media/csharp-aspnet-about-cshtml-cs-message.png)

## <a name="run-the-app"></a>Uygulamayı çalıştırma

1. Tuşuna **Ctrl**+**F5** uygulamayı çalıştırın ve bir web tarayıcısında açın.

   > [!NOTE]
   > Yazan bir hata iletisi alırsanız **web sunucusu için 'IIS Express' bağlanılamıyor**, Visual Studio'yu kapatın ve ardından kullanarak açın **yönetici olarak çalıştır** sağ tıklayın veya bağlam menüsünde seçenek. Ardından, uygulamayı yeniden çalıştırın.

1. Web sayfasının en üstünde **hakkında**.

   ![Web sayfasından hakkında seçin](../ide/media/csharp-aspnet-home-page-about.png)

1. Eklenen, güncelleştirilen metin görüntülemek **hakkında** sayfası.

   ![Eklediğiniz metin içeren bir sayfa hakkında güncelleştirilmiş görüntüleyin](../ide/media/csharp-aspnet-about-page-hello-world.png)

1. Web tarayıcısını kapatın.

Bu hızlı başlangıcı tamamladığınızda Tebrikler! C#, ASP.NET Core ve Visual Studio IDE (tümleşik geliştirme ortamı) hakkında biraz öğrenilen umuyoruz.

## <a name="next-steps"></a>Sonraki adımlar

Daha fazla bilgi için şu öğreticiyle devam edin:

> [!div class="nextstepaction"]
> [C# ve Visual Studio'da ASP.NET kullanmaya başlama](tutorial-csharp-aspnet-core.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio kullanarak web uygulamanızı Azure App Service'e yayımlama](..//deployment/quickstart-deploy-to-azure.md)
