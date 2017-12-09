---
title: "Hızlı Başlangıç: Windows oluşturma Visual Basic ile Visual Studio Forms uygulamasında | Microsoft Docs"
ms.custom: 
ms.date: 12/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: quickstart
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: ghogen
dev_langs: vb
ms.openlocfilehash: 22da6f18406331a67a06d030551f7068dd5254fc
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2017
---
# <a name="quickstart-create-a-windows-forms-app-in-visual-studio-with-visual-basic"></a>Hızlı Başlangıç: Windows oluşturma Visual Basic ile Visual Studio'da Forms uygulama
Bu 5-10 dakikalık bir giriş Visual Studio tümleşik geliştirme ortamı (IDE), bir Windows tabanlı kullanıcı arabirimi (UI) olan basit bir Visual Basic uygulama oluşturacaksınız.

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

     (Araç kutusu uçarak çıkış seçeneği görmüyorsanız, menü çubuğundan açabilirsiniz. Bunu yapmak için tıklatın **Görünüm** > **araç**. Veya basın **Ctrl**+**Alt**+**X**.)

2. Tıklatın **PIN** araç kutusu pencere sabitlemek için simge.

     ![IDE araç kutusu penceresine sabitlemek için PIN simgesine tıklayın](../ide/media/vb-pin-the-toolbox-window.png)  
3. Tıklatın **düğmesini** denetlemek ve form üzerine sürükleyin.

     ![Forma düğme ekleme](../ide/media/vb-add-a-button-to-form1.png)

4. İçinde **Görünüm** bölümünü **özellikleri** penceresinde, "Bu tıklayın" yazın ve sonra basın **Enter**.

     ![Formdaki düğmesinde metin ekleyin](../ide/media/vb-button-control-text.png)  

     (Özellikler penceresini görmüyorsanız, menü çubuğundan açabilirsiniz. Bunu yapmak için tıklatın **Görünüm** > **Özellikler penceresini**. Veya basın **F4**.)

5. İçinde **tasarım** bölümünü **özellikleri** penceresinde "btnClickThis" için "Button1" adını değiştirmek ve tuşuna basarak **Enter**.

     ![Bir işlev formundaki düğmesi ekleyin](../ide/media/vb-button-control-function.png)

### <a name="add-a-label-to-the-form"></a>Forma bir etiket ekleme
Bir eylem oluşturmak için bir düğme denetimi ekledik, metne göndermek için bir etiket denetimi ekleyelim.

1. Seçin **etiket** Denetim araç kutusu penceresinden form üzerine sürükleyin ve altında bırakma **tıklatın** düğmesi.

2. İçinde **tasarım** bölümünü **özellikleri** penceresinde "lblHelloWorld" için "Label1" adını değiştirmek ve tuşuna basarak **Enter**.

### <a name="add-code-to-the-form"></a>Form için kod ekleme

1. İçinde **Form1.vb &#91; tasarım &#93;** penceresinde, çift **tıklatın** açmak için düğmeye **Form1.vb** penceresi.

      (Alternatif olarak, genişletebilirsiniz **Form1.vb** içinde **Çözüm Gezgini** penceresi ve ardından **Form1**.)

2. İçinde **Form1.vb** penceresi, arasında **özel alt** satır ve **End Sub** satır yazın veya yapıştırın `lblHelloWorld.Text = "Hello World!"`.

     ![Form formun kodu ekleyin](../ide/media/vb-add-code-to-the-form.png)

## <a name="run-the-application"></a>Uygulamayı çalıştırın
1. Tıklatın **Başlat** uygulamayı çalıştırmak için düğmesi.

     ![Hata ayıklama ve uygulamayı çalıştırmak için Başlat'ı tıklatın](../ide/media/vb-click-start-hello-world.png)

   Birkaç şey gerçekleşir. Visual Studio IDE tanılama araçları penceresini açın ve bir çıktı penceresi çok açılacaktır. Ancak IDE dışında bir Form1 iletişim kutusu görüntülenir. Dahil edilir, **tıklatın** düğmesi ve "Label1" diyor metin.

2. Tıklatın **tıklatın** düğmesini **Form1** iletişim kutusu. "Label1" metin "İçin Hello World!" değiştiğine dikkat edin.

    ![Label1 metin içeren bir Form1 iletişim kutusu ](../ide/media/vb-form1-dialog-hello-world.png)

Bu hızlı başlangıç Tamamlanıyor Tebrikler! Visual Basic ve Visual Studio IDE hakkında biraz öğrenilen umuyoruz. Lütfen daha derin inceleyin istiyorsanız bir öğreticide devam **öğreticileri** içindekiler bölümü.  

## <a name="see-also"></a>Ayrıca bkz.   
* [Visual Basic "Hello World" konsol uygulaması Visual Studio 2017 .NET çekirdek ile derleme](https://docs.microsoft.com/dotnet/core/tutorials/vb-with-visual-studio)
* [Visual Basic IntelliSense](visual-basic-specific-intellisense.md)  
