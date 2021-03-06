---
title: Visual Studio'da Visual Basic ile çalışmaya başlama
description: Visual Studio'da, adım adım Visual Basic konsol uygulamaları oluşturmayı öğrenin.
ms.custom: ''
ms.date: 08/10/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: tutorial
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- vb
ms.workload:
- multiple
ms.openlocfilehash: 5b3288bc83e3cbeef9b46be2b3c6c7e17874d20f
ms.sourcegitcommit: db94ca7a621879f98d4c6aeefd5e27da1091a742
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2018
ms.locfileid: "42624318"
---
# <a name="tutorial-get-started-with-visual-basic-in-visual-studio"></a>Öğretici: Visual Studio'da Visual Basic ile çalışmaya başlama

Bu öğreticide Visual Basic (VB) oluşturmak ve birkaç farklı konsol uygulamaları çalıştırma ve bazı özellikleri incelemek için Visual Studio kullanacaksınız [Visual Studio tümleşik geliştirme ortamı (IDE)](visual-studio-ide.md) bunu yaparken.

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

## <a name="create-a-project"></a>Proje oluşturma

İlk olarak, Visual Basic uygulama projesi oluşturacağız. Proje türü bile herhangi bir şey ekledik önce ihtiyacınız olacak tüm şablon dosyaları ile birlikte gelir!

1. Visual Studio 2017'yi açın.

2. Üstteki menü çubuğundan seçin **dosya** > **yeni** > **proje**.

3. İçinde **yeni proje** iletişim kutusunun sol bölmesinde, **Visual Basic**ve ardından **.NET Core**. Orta bölmede seçin **konsol uygulaması (.NET Core)**. Dosya adı *HelloWorld*.

   ![Konsol uygulaması (.NET Core) proje şablonunu yeni proje iletişim kutusunda Visual Studio IDE](../ide/media/new-project-vb-dotnetcore-whatisyourname-console-app.png)

### <a name="add-a-workgroup-optional"></a>(İsteğe bağlı) bir çalışma grubu Ekle

Görmüyorsanız **konsol uygulaması (.NET Core)** proje şablonu, alabilirsiniz, ekleyerek **.NET Core çoklu platform geliştirme** iş yükü. Bu iş yükü, makinenizde yüklü Visual Studio 2017 güncelleştirmeleri bağlı olarak iki aşağıdaki yollardan biriyle ekleyebilirsiniz.

#### <a name="option-1-use-the-new-project-dialog-box"></a>Seçenek 1: Yeni Proje iletişim kutusunu kullanın.

1. Tıklayın **açık Visual Studio yükleyicisi** sol bölmesinde bağlantıyı **yeni proje** iletişim kutusu.

   ![Yeni Proje iletişim kutusundan açık Visual Studio yükleyicisi bağlantısına tıklayın](../ide/media/vs-open-visual-studio-installer-generic.png)

1. Visual Studio Yükleyicisi'ni başlatır. Seçin **.NET Core çoklu platform geliştirme** iş yükü ve ardından **Değiştir**.

   ![.NET core çoklu platform geliştirme iş yükünü Visual Studio yükleyicisi](../ide/media/quickstart-aspnet-workload.png)

#### <a name="option-2-use-the-tools-menu-bar"></a>2. seçenek: araçlar menü çubuğunu kullanın.

1. / İptal **yeni proje** iletişim kutusu ve üst menü çubuğundan seçin **Araçları** > **araçları ve özellikleri Al**.

1. Visual Studio Yükleyicisi'ni başlatır. Seçin **.NET Core çoklu platform geliştirme** iş yükü ve ardından **Değiştir**.

## <a name="create-a-what-is-your-name-application"></a>"Ne olduğunu uygulamanızın adı" uygulaması oluşturma

Adınız için ister ve sonra tarih ve saat ile birlikte görüntüler bir uygulama oluşturalım. İşte nasıl:

1. Zaten açık değilse, ardından açın, *WhatIsYourName* proje.

1. Aşağıdaki Visual Basic kodu izleyen hemen ayraç sonra girin `Sub Main(args As String())` satır ve önce `End Sub` satırı:

     ```vb
     Console.WriteLine(vbCrLf + "What is your name? ")
     Dim name = Console.ReadLine()
     Dim currentDate = DateTime.Now
     Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}")
     Console.Write(vbCrLf + "Press any key to exit... ")
     Console.ReadKey(True)
    ```

    Bu kodu varolan değiştirir <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, ve <xref:System.Console.ReadKey%2A> deyimleri.

   ![Ne olduğunu adınız kodu gösteren kod penceresi](../ide/media/vb-codewindow-what-name.png)

1. Konsol penceresi açıldığında, adınızı girin. Konsol penceresi aşağıdaki ekran görüntüsüne benzer görünmelidir:

   ![Konsol ne olduğunu uygulamanızın adı, saati ve tarihi gösteren penceresi ve ileti devam etmek için herhangi bir tuşa basın](../ide/media/vb-console-what-name.png)

1. Konsol penceresini kapatmak için herhangi bir tuşa basın.

## <a name="create-a-calculate-this-application"></a>"Bu Hesapla" bir uygulama oluşturma

1. Visual Studio 2017'yi açın ve ardından üstteki menü çubuğundan **dosya** > **yeni** > **proje**.

1. İçinde **yeni proje** iletişim kutusunun sol bölmesinde, **Visual Basic**ve ardından **.NET Core**. Orta bölmede seçin **konsol uygulaması (.NET Core)**. Dosya adı *CalculateThis*.

1. Arasına aşağıdaki kodu girin `Module Program` satır ve `End Module` satırı:

   ```vb
   Public num1 As Integer
   Public num2 As Integer
   Public answer As Integer
   Sub Main()
       Console.WriteLine("Type a number and press Enter")
       num1 = Console.ReadLine()
       Console.WriteLine("Type another number to add to it and press Enter")
       num2 = Console.ReadLine()
       answer = num1 + num2
       Console.WriteLine("The answer is " & answer)
       Console.ReadLine()
   End Sub
   ```

   Kod penceresi aşağıdaki ekran görüntüsüne benzer görünmelidir:

   ![Bu kod hesapla gösteren kod penceresi](../ide/media/vb-codewindow-calculate-this.png)

1. Tıklayın **CalculateThis** seçerek programınızı çalıştırın. Konsol penceresi aşağıdaki ekran görüntüsüne benzer görünmelidir:

    ![Konsol penceresi yönergeleri almak için hangi eylemleri içeren CaluculateThis uygulama gösteriliyor.](../ide/media/vb-console-calculate-this.png)

## <a name="quick-answers-faq"></a>Hızlı yanıtlar hakkında SSS

İşte bazı temel kavramları vurgulamak için hızlı bir SSS.

### <a name="what-is-visual-basic"></a>Visual Basic nedir?

Visual Basic öğrenin kolay olacak şekilde tasarlanan bir tür açısından güvenli bir programlama dilidir. Bu, anlamına gelir "Başlangıç çok amaçlı sembolik yönerge kodu" BASİC'ten elde edilir.

### <a name="what-is-visual-studio"></a>Visual Studio nedir?

Visual Studio geliştiricileri için üretkenlik aracından oluşan bir tümleşik geliştirme paketidir. Bunu, programları ve uygulamaları oluşturmak için kullanabileceğiniz bir program olarak düşünün.

### <a name="what-is-a-console-app"></a>Bir konsol uygulaması nedir?

Bir konsol uygulaması girdi alır ve çıktı olarak da bilinir bir komut satırı penceresinde görüntüler bir konsol.

### <a name="what-is-net-core"></a>.NET Core nedir?

.NET core .NET Framework'ün gelişime sonraki adımdır. Burada .NET Framework programlama dilleri arasında kod paylaşma izin .NET Core platformlar arasında kod paylaşma olanağı ekler. Daha da iyi açık kaynak olan. (.NET Framework ve .NET Core kodunuzu çalıştırmak için bir sanal makine olarak davranan bir ortak dil çalışma zamanı (CLR) yanı sıra önceden oluşturulmuş işlevselliği kitaplıkları içerir.)

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticiyi tamamlamak Tebrikler! Daha da fazla bilgi edinmek için aşağıdaki öğreticiye bakın.

> [!div class="nextstepaction"]
> [Video öğretici: Visual Basic temelleri yeni başlayanlar için](https://mva.microsoft.com/en-us/training-courses/visual-basic-fundamentals-for-absolute-beginners-16507)

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Basic'te yenilikler nelerdir?](/dotnet/visual-basic/getting-started/whats-new)
* [Visual Basic kod dosyaları için IntelliSense](visual-basic-specific-intellisense.md)
* [Visual Basic Dil Başvurusu](/dotnet/visual-basic/language-reference/index)