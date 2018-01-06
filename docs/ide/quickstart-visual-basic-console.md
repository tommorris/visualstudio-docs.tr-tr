---
title: "Hızlı Başlangıç: Visual Basic ile Visual Studio'da ilk Konsol uygulamanızı oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 12/10/2017
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
ms.workload: multiple
ms.openlocfilehash: 2573e1a2344b858b721fb234d6b228b421a36550
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="quickstart-create-your-first-console-app-in-visual-studio-with-visual-basic"></a>Hızlı Başlangıç: Visual Basic ile Visual Studio'da ilk Konsol uygulamanızı oluşturma
Bu 5-10 dakikalık bir giriş Visual Studio tümleşik geliştirme ortamı (IDE), konsolda çalışan basit bir Visual Basic uygulaması oluşturacaksınız.

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) ücretsiz yüklemek için sayfa.

## <a name="create-a-project"></a>Proje oluşturma
İlk olarak, bir Visual Basic uygulama projesi oluşturacaksınız. Proje türü herhangi bir şey bile eklediğiniz önce ihtiyacınız vardır tüm şablonu dosyalarıyla birlikte verilir!

1. Visual Studio 2017'ni açın.

2. Üst menü çubuğundan seçin **dosya** > **yeni** > **proje...** .

3. İçinde **yeni proje** iletişim kutusunun sol bölmesinde **Visual Basic**ve ardından **.NET Core**. Orta bölmede seçin **konsol uygulaması (.NET Core)**. Proje adı *HelloWorld*.

   ![Uygulama (.NET Core) proje şablonu Visual Studio IDE'de yeni proje iletişim kutusundaki konsol](../ide/media/new-project-vb-dotnetcore-helloworld-console-app.png)

     Görmüyorsanız, **konsol uygulaması (.NET Core)** proje şablonu, tıklatın **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu.

   ![Yeni Proje iletişim kutusundan açık Visual Studio yükleyicisi bağlantısına tıklayın](../ide/media/vb-open-visual-studio-installer-hello-world.png)

     Visual Studio yükleyicisi başlatır. Seçin **.NET Core platformlar arası geliştirme** iş yükü ve ardından **Değiştir**.

     ![Visual Studio yükleyicisi .NET core platformlar arası geliştirme iş yükü](../ide/media/dot-net-core-xplat-dev-workload.png)

## <a name="create-the-application"></a>Uygulama oluşturma
Visual Basic proje şablonu seçin ve projenizin adı sonra Visual Studio sizin için basit bir "Hello World" uygulama oluşturur. Çağırır <xref:System.Console.WriteLine%2A> değişmez değer dize "Hello World!" görüntülenecek yöntemi Konsol penceresinde.

![Şablonun varsayılan Hello World kodundan görüntüleyin](../ide/media/vb-console-helloworld-template.png)

Tıklatırsanız **HelloWorld** düğmesi IDE içinde hata ayıklama modunda program çalışabilir.

  ![Program hata ayıklama modunda çalıştırmak için Hello World düğmesini tıklatın](../ide/media/vb-console-hello-world-button.png)

Bunu yaptığınızda, konsol penceresi kapanmadan önce yalnızca bir süre için görünür olur. Çünkü böyle `Main` yöntemi, tek bir deyimde yürütüldükten sonra ve uygulama sona şekilde sonlandırır.

### <a name="add-some-code"></a>Bazı kodlar ekleyin
Uygulama duraklatma ve kullanıcı girdisi isteyin biraz kod ekleyelim.

1. Çağırdıktan hemen sonra aşağıdaki kodu ekleyin <xref:System.Console.WriteLine%2A> yöntemi:

   ```vb
   Console.Write("Press any key to continue...")
   Console.ReadKey(true)
   ```
   Bir tuşa basın kadar bu program duraklatır.

2. Menü çubuğunda seçin **yapı** > **yapı çözümü**.

   Tam zamanında (JIT) derleyici tarafından ikili koda dönüştürülür bir ara dile (IL) programınızı derler.

## <a name="run-the-application"></a>Uygulamayı çalıştırın
1. Tıklatın **HelloWorld** araç çubuğunda.

   ![Araç çubuğundan programı çalıştırmak için Hello World düğmesini tıklatın](../ide/media/vb-console-hello-world-button.png)

2. Konsol penceresini kapatmak için herhangi bir tuşa basın.

   ![Hello World gösteren penceresi konsol ve devam etmek için herhangi bir tuşa basın](../ide/media/vb-console-hello-world-press-any-key.png)

Bu hızlı başlangıç Tamamlanıyor Tebrikler! Visual Basic ve Visual Studio IDE hakkında biraz öğrenilen umuyoruz. Lütfen daha derin inceleyin istiyorsanız bir öğreticide devam **öğreticileri** içindekiler bölümü.

## <a name="see-also"></a>Ayrıca bkz.
* [Hızlı Başlangıç: "Hello World" Windows oluşturma Visual Studio ile Visual Basic'te form uygulama](quickstart-visual-basic-winforms.md)
* [Öğretici: Visual Basic'te Visual Studio ile çalışmaya başlama](tutorial-visual-basic-console.md)
* [Visual Basic kodu dosyaları için IntelliSense](visual-basic-specific-intellisense.md)
