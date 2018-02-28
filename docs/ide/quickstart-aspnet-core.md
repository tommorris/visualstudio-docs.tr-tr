---
title: "Bir ASP.NET Core web uygulaması C# ' ta oluşturmak için Visual Studio'yu kullanın | Microsoft Docs"
ms.custom: 
ms.date: 10/10/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 66017b65e3d1201e02272447cbd3ec1c33c8a5d6
ms.sourcegitcommit: 49aa031cbebdd9c7ec070c713afb1a97d1ecb701
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2018
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-app"></a>Hızlı Başlangıç: Kullanım ilk ASP.NET Core web uygulamanızı oluşturmak için Visual Studio

Bu 5-10 dakikalık bir giriş Visual Studio tümleşik geliştirme ortamı (IDE), basit bir C# ASP.NET Core web uygulaması oluşturacaksınız. Visual Studio henüz yüklemediyseniz, ücretsiz yükleme [burada](http://www.visualstudio.com).

## <a name="create-a-project"></a>Proje oluşturma

İlk olarak, bir ASP.NET Core web uygulama projesi oluşturacaksınız. Proje türü bir işlevsel bir web uygulaması bile her şeyi eklediğiniz önce oluşturan şablonu dosyalarıyla birlikte verilir!

1. Visual Studio 2017'ni açın.

1. Üst menü çubuğundan seçin **dosya** > **yeni** > **proje...** .

1. İçinde **yeni proje** iletişim kutusunda, sol bölmede, genişletin **Visual C#**, ardından **.NET Core**. Orta bölmede seçin **ASP.NET çekirdek Web uygulaması**, ardından **Tamam**.

     Görmüyorsanız, **.NET Core** proje şablonu kategorisi, seçin **açık Visual Studio yükleyicisi** sol bölmede bağlantı. Visual Studio yükleyicisi başlatır. Seçin **ASP.NET ve web geliştirme** iş yükü, ardından **Değiştir**.

     ![VS yükleyici ASP.NET iş yükü](../ide/media/quickstart-aspnet-workload.png)

1. İçinde **çekirdek yeni bir ASP.NET Web uygulaması** iletişim kutusunda **ASP.NET Core 2.0** üstteki açılan menüden. (Görmüyorsanız **ASP.NET Core 2.0** listesinde izleyerek yükleyin **karşıdan** iletişim kutusunun üstündeki yanında sarı çubuğu görüntülenmelidir bağlantıyı.) Seçin **Tamam**.

   ![Yeni ASP.NET çekirdek Web uygulaması iletişim kutusu](../ide/media/quickstart-aspnet-core20.png)

## <a name="explore-the-ide"></a>IDE keşfedin

1. İçinde **Çözüm Gezgini** araç genişletin **sayfaları** klasörü, ardından **About.cshtml** düzenleyicisinde açın. Bu dosya adında bir sayfaya karşılık gelen **hakkında** web uygulamasında.

1. Düzenleyicide seçin `AboutModel` ve tuşuna basarak **F12** veya seçin **Tanıma Git** (sağ tıklatma) bağlam menüsünden. Bu komut tanımına alır `AboutModel` C# sınıfı.

   ![Tanıma Git bağlam menüsü](../ide/media/quickstart-aspnet-gotodefinition.png)

1. Sonraki temizleme `using` yönergeleri kullanarak basit bir kısayol dosyasını üstündeki. Gri çıkış birini yönergeleri kullanarak ve [hızlı Eylemler](../ide/quick-actions.md) ampul şapka hemen altındaki veya sol kenar boşluğunda görünür. Ampul seçin ve ardından **gereksiz kullanımları kaldırma**.

     Gereksiz kullanımları dosyasından silinir.

1. İçinde `OnGet()` yöntemi, gövde aşağıdaki kodla değiştirin:

 ```csharp
 public void OnGet()
 {
     string directory = Environment.CurrentDirectory;
     Message = String.Format("Your directory is {0}.", directory);
 }
 ```

1. Altında görüntülenen iki dalgalı alt çizgiler görürsünüz **ortam** ve **dize**, bu tür kapsamında değildir. Açık **hata listesi** aynı hataları görmek için araç listelenir. (Görmüyorsanız **hata listesi** araç seçin **Görünüm** > **hata listesi** üst menü çubuğundan.)

   ![Hata Listesi](../ide/media/quickstart-aspnet-errorlist.png)

1. Düzenleyicisi penceresinde, imlecinizi hata içerir ve ardından sol kenar boşluğunda hızlı Eylemler ampul seçin ya da satırındaki yerleştirin. Aşağı açılır menüden **sistem; kullanarak** bu yönergesi dosyanızın en üstüne ekleyin ve hataları giderin.

## <a name="run-the-application"></a>Uygulamayı çalıştırın

1. Tuşuna **Ctrl**+**F5** uygulamayı çalıştırın ve bir web tarayıcısında açın.

1. Web sitesinin üstünde seçin **hakkında** , eklenen ileti dizin görmek için `OnGet()` yöntemi **hakkında** sayfası.

1. Web tarayıcısını kapatın.

> [!NOTE]
> Bildiren bir hata iletisi alırsanız **web sunucusuna 'IIS Express' bağlanılamıyor**, Visual Studio'yu kapatın ve ardından kullanarak açın **yönetici olarak çalıştır** sağ tıklatın veya bağlam menüsünden seçeneği. Daha sonra uygulamayı yeniden çalıştırın.

Bu hızlı başlangıç Tamamlanıyor Tebrikler! Visual Studio IDE hakkında biraz öğrenilen umuyoruz. Lütfen yeteneklerini daha derin inceleyin istiyorsanız bir öğreticide devam **öğreticileri** içindekiler bölümü.

## <a name="see-also"></a>Ayrıca bkz.

[C# ve Visual Studio'da ASP.NET ile çalışmaya başlama](tutorial-csharp-aspnet-core.md)  
[C# ve Visual Studio kullanarak Visual Basic'e Başlarken](getting-started-with-visual-csharp-and-visual-basic.md)  
[ASP.NET Core Razor sayfalarında ile çalışmaya başlama](/aspnet/core/tutorials/razor-pages/razor-pages-start)