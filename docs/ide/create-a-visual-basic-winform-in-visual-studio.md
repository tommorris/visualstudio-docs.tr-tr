---
title: Windows oluşturma Visual Basic ile Visual Studio'da Forms uygulama
description: Visual Basic, adım adım ile Visual Studio'da bir Windows Forms uygulaması oluşturmayı öğrenin.
ms.custom: ''
ms.date: 12/04/2017
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- vb
ms.workload:
- multiple
ms.openlocfilehash: 603fe9c8aaa328e0ae1b42f385a0f8f2b5867955
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="create-a-windows-forms-app-in-visual-studio-with-visual-basic"></a>Windows oluşturma Visual Basic ile Visual Studio'da Forms uygulama

Bu kısa giriş Visual Studio tümleşik geliştirme ortamı (IDE) için bir Windows tabanlı kullanıcı arabirimi (UI) olan basit bir Visual Basic uygulama oluşturacaksınız.

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) ücretsiz yüklemek için sayfa.

## <a name="create-a-project"></a>Proje oluşturma

İlk olarak, bir Visual Basic uygulama projesi oluşturacaksınız. Proje türü herhangi bir şey bile eklediğiniz önce ihtiyacınız vardır tüm şablonu dosyalarıyla birlikte verilir.

1. Visual Studio 2017'ni açın.

2. Üst menü çubuğundan seçin **dosya** > **yeni** > **proje...** .

3. İçinde **yeni proje** iletişim kutusunun sol bölmesinde **Visual Basic**ve ardından **Windows Klasik Masaüstü**. Orta bölmede seçin **Windows Forms uygulaması (.NET Framework)**. Dosya adı `HelloWorld`.

     Görmüyorsanız, **Windows Forms uygulaması (.NET Framework)** proje şablonu, dışı iptal **yeni proje** iletişim kutusuna ve üst menü çubuğundan seçin **Araçları**  >  **Alma araçları ve özelliklerinin...** . Visual Studio yükleyicisi başlatır. Seçin **.NET masaüstü geliştirme** iş yükü, ardından **Değiştir**.

     ![Visual Studio yükleyicisi .NET core iş yükü](../ide/media/install-dot-net-desktop-env.png)

## <a name="create-the-application"></a>Uygulama oluşturma

Visual Basic proje şablonu seçin ve dosyanızın adı sonra Visual Studio bir formu açılır. Bir formu bir Windows kullanıcı arabirimidir. "Hello World" uygulama Forma denetimler ekleyerek oluşturacağız ve ardından biz uygulaması çalıştıracaksınız.

### <a name="add-a-button-to-the-form"></a>Forma düğme ekleme

1. Tıklatın **araç** araç uçarak çıkış penceresini açmak için.

     ![Araç kutusu penceresini açmak için araç'e tıklayın](../ide/media/vb-toolbox-toolwindow.png)

     (Görmüyorsanız **araç** uçarak çıkış seçeneği açabilirsiniz, menü çubuğundan. Bunu yapmak için tıklatın **Görünüm** > **araç**. Veya basın **Ctrl**+**Alt**+**X**.)

2. Tıklatın **PIN** sabitlemek için simge **araç** penceresi.

     ![IDE araç kutusu penceresine sabitlemek için PIN simgesine tıklayın](../ide/media/vb-pin-the-toolbox-window.png)
3. Tıklatın **düğmesini** denetlemek ve form üzerine sürükleyin.

     ![Forma düğme ekleme](../ide/media/vb-add-a-button-to-form1.png)

4. İçinde **Görünüm** bölümünü **özellikleri** penceresinde, türü `Click this`ve tuşuna basarak **Enter**.

     ![Formdaki düğmesinde metin ekleyin](../ide/media/vb-button-control-text.png)

     (Görmüyorsanız **özellikleri** penceresinde açabilirsiniz, menü çubuğundan. Bunu yapmak için tıklatın **Görünüm** > **Özellikler penceresini**. Veya basın **F4**.)

5. İçinde **tasarım** bölümünü **özellikleri** penceresinde adını değiştirmek **Button1** için `btnClickThis`ve tuşuna basarak **Enter**.

     ![Bir işlev formundaki düğmesi ekleyin](../ide/media/vb-button-control-function.png)

### <a name="add-a-label-to-the-form"></a>Forma bir etiket ekleme

Bir eylem oluşturmak için bir düğme denetimi ekledik, metne göndermek için bir etiket denetimi ekleyelim.

1. Seçin **etiket** gelen denetim **araç kutusu** penceresinde ve ardından form üzerine sürükleyin ve altında bırakma **tıklatın** düğmesi.

2. İçinde **tasarım** bölümünü **özellikleri** penceresinde adını değiştirmek **Label1** için `lblHelloWorld`ve tuşuna basarak **Enter**.

### <a name="add-code-to-the-form"></a>Form için kod ekleme

1. İçinde **Form1.vb &#91;tasarım&#93;**  penceresinde, çift **tıklatın** açmak için düğmeye **Form1.vb** penceresi.

      (Alternatif olarak, genişletebilirsiniz **Form1.vb** içinde **Çözüm Gezgini** penceresi ve ardından **Form1**.)

2. İçinde **Form1.vb** penceresi, arasında **özel alt** satır ve **End Sub** satır yazın veya yapıştırın `lblHelloWorld.Text = "Hello World!"`.

     ![Form formun kodu ekleyin](../ide/media/vb-add-code-to-the-form.png)

## <a name="run-the-application"></a>Uygulamayı çalıştırın

1. Tıklatın **Başlat** uygulamayı çalıştırmak için düğmesi.

     ![Hata ayıklama ve uygulamayı çalıştırmak için Başlat'ı tıklatın](../ide/media/vb-click-start-hello-world.png)

   Birkaç şey gerçekleşir. Visual Studio IDE içinde **tanılama araçları** penceresi açılır ve bir **çıkış** penceresi açılır, çok. Ancak IDE dışında bir **Form1** iletişim kutusu görüntülenir. Dahil edilir, **tıklatın** düğmesi ve diyor metin **Label1**.

2. Tıklatın **tıklatın** düğmesini **Form1** iletişim kutusu. Dikkat **Label1** metin değişiklikleri **Hello World!**.

    ![Label1 metin içeren bir Form1 iletişim kutusu ](../ide/media/vb-form1-dialog-hello-world.png)

Bu hızlı başlangıç Tamamlanıyor Tebrikler! Visual Basic ve Visual Studio IDE hakkında biraz öğrenilen umuyoruz. Lütfen daha derin inceleyin istiyorsanız bir öğreticide devam **öğreticileri** içindekiler bölümü.

## <a name="see-also"></a>Ayrıca bkz.

* [Hızlı Başlangıç: Visual Basic ile Visual Studio'da bir konsol uygulaması oluşturun.](quickstart-visual-basic-console.md)
* [Visual Basic IntelliSense hakkında daha fazla bilgi edinin](visual-basic-specific-intellisense.md)
