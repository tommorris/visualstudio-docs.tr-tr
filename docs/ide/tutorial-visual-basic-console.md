---
title: Visual Basic Visual Studio ile çalışmaya başlama
ms.custom: ''
ms.date: 12/08/2017
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
ms.openlocfilehash: ce1c40a7031145a13eb2eebf8adaee4eba51e9fc
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36280344"
---
# <a name="get-started-with-visual-basic-in-visual-studio"></a>Visual Basic Visual Studio ile çalışmaya başlama

Bu öğreticide için Visual Basic (VB), oluşturmak ve birkaç farklı konsol uygulamaları çalıştırmak için Visual Studio'yu kullanın ve bazı özellikleri keşfedin [Visual Studio tümleşik geliştirme ortamı (IDE)](visual-studio-ide.md) bunu yaparken.

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

## <a name="before-you-begin"></a>Başlamadan önce

Burada, bazı temel kavramları tanıtmak için bir hızlı sık sorulan sorular verilmiştir.

### <a name="what-is-visual-basic"></a>Visual Basic nedir?

Visual Basic öğrenmek kolay olması için tasarlanmış bir tür kullanımı uyumlu programlama dilidir. "Başlangıç çok amaçlı simgesel yönerge kodu" anlamına gelir BASİC'ten türetilir.

### <a name="what-is-visual-studio"></a>Visual Studio nedir?

Visual Studio, geliştiriciler için üretkenlik araçları'nın bir tümleşik geliştirme paketidir. Bunu, programları ve uygulamaları oluşturmak için kullanabileceğiniz bir program olarak düşünün.

### <a name="what-is-a-console-app"></a>Bir konsol uygulaması nedir?

Bir konsol uygulaması girdi alır ve çıktı paketini bir komut satırı penceresinde görüntüler bir konsol.

### <a name="what-is-net-core"></a>.NET Core nedir?

.NET core .NET Framework'ün Açılım sonraki adımdır. Burada .NET Framework, kod programlama dilleri arasında paylaşmak izin .NET Core kod platformları arasında paylaşmak yeteneği ekler. Bile, onu açık kaynak daha iyidir. (.NET Framework ve .NET Core kitaplıkları, kodunuzu çalıştırmak için bir sanal makine olarak davranan bir ortak dil çalışma zamanı (CLR) yanı sıra önceden oluşturulmuş işlevselliği içerir.)

## <a name="start-developing"></a>Geliştirmeye başlayın

Geliştirmeye başlamak hazır mısınız? Gidelim!

### <a name="create-a-project"></a>Proje oluşturma

İlk olarak, bir Visual Basic uygulama projesi oluşturacağız. Proje türü herhangi bir şey bile eklediğiniz önce ihtiyacınız vardır tüm şablonu dosyalarıyla birlikte verilir!

1. Visual Studio 2017'ni açın.

2. Üst menü çubuğundan seçin **dosya** > **yeni** > **proje**.

3. İçinde **yeni proje** iletişim kutusunun sol bölmesinde **Visual Basic**ve ardından **.NET Core**. Orta bölmede seçin **konsol uygulaması (.NET Core)**. Dosya adı *HelloWorld*.

   ![Uygulama (.NET Core) proje şablonu Visual Studio IDE'de yeni proje iletişim kutusundaki konsol](../ide/media/new-project-vb-dotnetcore-whatisyourname-console-app.png)

#### <a name="add-a-workgroup-optional"></a>(İsteğe bağlı) bir çalışma grubu Ekle

Görmüyorsanız, **konsol uygulaması (.NET Core)** proje şablonu, alabilirsiniz, ekleyerek **.NET Core platformlar arası geliştirme** iş yükü. Bu iş yükü bağlı olarak Visual Studio 2017 güncelleştirmeleri makinenize yüklü iki aşağıdaki yollardan biriyle ekleyebilirsiniz.

##### <a name="option-1-use-the-new-project-dialog-box"></a>Seçenek 1: Yeni Proje iletişim kutusunu kullanın

1. Tıklatın **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu.

  ![Yeni Proje iletişim kutusundan açık Visual Studio yükleyicisi bağlantısına tıklayın](../ide/media/vs-open-visual-studio-installer-generic.png)

2. Visual Studio yükleyicisi başlatır. Seçin **.NET Core platformlar arası geliştirme** iş yükü ve ardından **Değiştir**.

   ![Visual Studio yükleyicisi .NET core platformlar arası geliştirme iş yükü](../ide/media/dot-net-core-xplat-dev-workload.png)

##### <a name="option-2-use-the-tools-menu-bar"></a>Seçenek 2: araçlar menü çubuğu'nu kullanın

1. İşyeri dışında iptal **yeni proje** iletişim kutusuna ve üst menü çubuğundan seçin **Araçları** > **alma araçları ve özelliklerinin**.

2. Visual Studio yükleyicisi başlatır. Seçin **.NET Core platformlar arası geliştirme** iş yükü ve ardından **Değiştir**.

## <a name="create-a-what-is-your-name-application"></a>"Ne olduğunu adınız" uygulaması oluşturma

İçin adınızı ister ve sonra tarih ve saati ile birlikte görüntüleyen bir uygulama oluşturalım. İşte nasıl:

1. Zaten açık değilse, ardından açın, *WhatIsYourName* projesi.

2. Aşağıdaki hemen ayraç sonra aşağıdaki Visual Basic kodu girin `Sub Main(args As String())` satır ve önce `End Sub` satır:

     ```vb
     Console.WriteLine(vbCrLf + "What is your name? ")
     Dim name = Console.ReadLine()
     Dim currentDate = DateTime.Now
     Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}")
     Console.Write(vbCrLf + "Press any key to exit... ")
     Console.ReadKey(True)
    ```

    Bu kod varolan değiştirir <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, ve <xref:System.Console.ReadKey%2A> deyimleri.

 ![Kod penceresi ne olduğunu adınız kodu gösterme](../ide/media/vb-codewindow-what-name.png)

3. Konsol penceresi açıldığında, adınızı girin. Konsol penceresinde aşağıdaki ekran görüntüsüne benzer görünmelidir:

   ![Pencere ne olduğunu adınız, tarih ve saati gösteren konsol ve ileti devam etmek için herhangi bir tuşa basın](../ide/media/vb-console-what-name.png)

5. Konsol penceresini kapatmak için herhangi bir tuşa basın.

## <a name="create-a-calculate-this-application"></a>"Bu Hesapla" bir uygulama oluşturma

1. Visual Studio 2017'ni açın ve ardından üst menü çubuğundan **dosya** > **yeni** > **proje**.

2. İçinde **yeni proje** iletişim kutusunun sol bölmesinde **Visual Basic**ve ardından **.NET Core**. Orta bölmede seçin **konsol uygulaması (.NET Core)**. Dosya adı *CalculateThis*.

3. Aşağıdaki kod arasında girin `Module Program` satır ve `End Module` satır:

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

  Kod pencerenizi aşağıdaki ekran görüntüsüne görünmelidir:

   ![Bu kod hesapla gösteren kod penceresi](../ide/media/vb-codewindow-calculate-this.png)

4. Tıklatın **CalculateThis** programınızı çalıştırmak için. Konsol penceresinde aşağıdaki ekran görüntüsüne benzer görünmelidir:

    ![Hangi eylemler istemlerinde içeren CaluculateThis uygulama gösteren konsol penceresi.](../ide/media/vb-console-calculate-this.png)

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticiyi tamamlamak Tebrikler! Visual Basic ve Visual Studio IDE hakkında daha fazla bilgi edinmek için şu sayfalara bakın.

* [Visual Basic Kılavuzu](/dotnet/visual-basic/index)
* [Visual Basic'te yenilikler nelerdir?](/dotnet/visual-basic/getting-started/whats-new)
* [Visual Basic kodu dosyaları için IntelliSense](visual-basic-specific-intellisense.md)
* [Visual Basic Dil Başvurusu](/dotnet/visual-basic/language-reference/index)
* [Visual Basic temelleri yeni başlayanlar için](https://mva.microsoft.com/en-us/training-courses/visual-basic-fundamentals-for-absolute-beginners-16507) video indirmelere
