---
title: C# ASP.NET Core web uygulaması oluşturmak için Visual Studio
description: Visual Studio'da C# ile adım adım ASP.NET Core web uygulaması oluşturmayı öğrenin.
ms.custom: mvc
ms.date: 06/27/2018
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
ms.openlocfilehash: 83811499782fedd5b869ca6587a6d13d60af187d
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39176310"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-app"></a>Hızlı Başlangıç: Kullanım ilk ASP.NET Core web uygulamanızı oluşturmak için Visual Studio

Bu 5-10 dakikalık bir giriş Visual Studio tümleşik geliştirme ortamı (IDE), basit bir C# ASP.NET Core web uygulaması oluşturacaksınız.

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

## <a name="create-a-project"></a>Proje oluşturma

İlk olarak, bir ASP.NET Core web uygulaması projesi oluşturacaksınız. Proje türü şablonu dosyalarıyla bile herhangi bir şey ekledik önce bir işlevsel bir web uygulaması oluşturan gelir!

1. Visual Studio 2017'yi açın.

1. Üstteki menü çubuğundan seçin **dosya** > **yeni** > **proje**.

1. İçinde **yeni proje** iletişim kutusunda, sol bölmede, **Visual C#**, ardından **.NET Core**. Orta bölmede seçin **ASP.NET Core Web uygulaması**, ardından **Tamam**.

     Görmüyorsanız **.NET Core** projesinin şablon kategorisi **açık Visual Studio yükleyicisi** sol bölmede bağlantı. Visual Studio Yükleyicisi'ni başlatır. Seçin **ASP.NET ve web geliştirme** iş yükü, ardından **Değiştir**.

     ![ASP.NET iş yükü VS yükleyicisi](../ide/media/quickstart-aspnet-workload.png)

1. İçinde **yeni ASP.NET Core Web uygulaması** iletişim kutusunda **ASP.NET Core 2.0** üstteki açılan menüden. (Görmüyorsanız **ASP.NET Core 2.0** listesinde izleyerek yükleyin **indirme** iletişim kutusunun üst kısmındaki sarı çubuk gözükeceğini bağlantıyı.) Seçin **Tamam**.

   ![Yeni ASP.NET Core Web uygulaması iletişim kutusu](../ide/media/quickstart-aspnet-core20.png)

## <a name="explore-the-ide"></a>IDE'yi keşfedin

1. İçinde **Çözüm Gezgini** araç genişletin **sayfaları** klasörü seçin **About.cshtml** Düzenleyicisi'nde açın. Bu dosya adında bir sayfasına karşılık gelen **hakkında** web uygulamasında.

1. Düzenleyici'de seçin `AboutModel` ve tuşuna **F12** veya **tanıma** (sağ tıklama) bağlam menüsünden. Bu komut tanımına alan `AboutModel` C# sınıfı.

   ![Tanıma Git bağlam menüsü](../ide/media/quickstart-aspnet-gotodefinition.png)

1. Sonraki temizleme `using` basit kısayolunu kullanarak dosyanın üst kısmındaki yönergeleri. Grileştirilmiş birini yönergeleri kullanarak ve bir [hızlı Eylemler](../ide/quick-actions.md) ampul hemen altına giriş işaretinin veya sol kenar boşluğunda görünür. Ampule ve ardından seçin **gereksiz kullanımları Kaldır**.

     Gereksiz kullanımları dosyasından silinir.

1. İçinde `OnGet()` yöntem gövdesi aşağıdaki kodla değiştirin:

 ```csharp
 public void OnGet()
 {
     string directory = Environment.CurrentDirectory;
     Message = String.Format("Your directory is {0}.", directory);
 }
 ```

1. Altında görünen iki dalgalı çizgiler görürsünüz **ortam** ve **dize**, bu türleri kapsamındaki değildir. Açık **hata listesi** aynı hatalar görmeniz için araç çubuğunda listelenen vardır. (Görmüyorsanız **hata listesi** araç seçin **görünümü** > **hata listesi** üst menü çubuğundan.)

   ![Hata Listesi](../ide/media/quickstart-aspnet-errorlist.png)

1. Düzenleyicisi penceresinde, hata içeren ve ardından sol kenar boşluğunda hızlı Eylemler ampul seçin ya da satıra imleci yerleştirin. Aşağı açılan menüden **sistemiyle;** bu yönerge dosyanızın en üstüne ekleyin ve hataları giderin.

## <a name="run-the-application"></a>Uygulamayı çalıştırın

1. Tuşuna **Ctrl**+**F5** uygulamayı çalıştırın ve bir web tarayıcısında açın.

1. En üstünde Web sitesinin **hakkında** , eklenen ileti directory görmek için `OnGet()` yöntemi **hakkında** sayfası.

1. Web tarayıcısını kapatın.

> [!NOTE]
> Bildiren bir hata iletisi alırsanız **web sunucusu için 'IIS Express' bağlanılamıyor**, Visual Studio'yu kapatın ve ardından kullanarak açın **yönetici olarak çalıştır** sağ tıklayın veya bağlam menüsünde seçenek. Ardından, uygulamayı yeniden çalıştırın.

Bu hızlı başlangıcı tamamladığınızda Tebrikler! Visual Studio IDE hakkında biraz bilgi edindiniz umuyoruz. Lütfen özelliklerini daha ayrıntılı olarak inceleyin istiyorsanız, bir öğreticide devam **öğreticiler** İçindekiler bölümünde.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıcı tamamladığınızda Tebrikler! C#, ASP.NET Core ve Visual Studio IDE hakkında biraz öğrenilen umuyoruz. Ortak bir sunucu üzerinde çalışan uygulamayı görmek için aşağıdaki düğmeyi seçin.

> [!div class="nextstepaction"]
> [Uygulamayı Azure App Service'e dağıtma](..//deployment/quickstart-deploy-to-azure.md)

Daha fazla bilgi edinmek için öğreticileri ile devam [C# ve Visual Studio'da ASP.NET kullanmaya başlama](tutorial-csharp-aspnet-core.md) ve [ASP.NET Core MVC ve Visual Studio ile çalışmaya başlama](/aspnet/core/tutorials/first-mvc-app/start-mvc?tabs=aspnetcore2x).
