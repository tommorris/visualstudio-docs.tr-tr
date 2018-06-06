---
title: Hata ayıklayıcısını kullanmaya başlama
ms.description: Learn how to start the Visual Studio debugger, step through code, and inspect data.
ms.custom: mvc
ms.date: 03/16/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
helpviewer_keywords:
- debugger
ms.assetid: 62734c0d-a75a-4576-8f73-0e97c19280e1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0f3d4c27f0aedf879137b3ef7a154fb7dd6f9164
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766265"
---
# <a name="tutorial-learn-to-debug-using-visual-studio"></a>Öğretici: Visual Studio kullanarak hata ayıklama öğrenin

Bu konu, Visual Studio Hata Ayıklayıcısı'ndaki bir adım adım kılavuz özelliklerini tanıtır. Hata ayıklayıcı özellikleri üst düzey bir görünümünü istiyorsanız, bkz: [hata ayıklayıcı özelliği Turu](../debugger/debugger-feature-tour.md).

Ya da boyunca hata ayıklayıcı özelliklerini görmek için okuyabilirsiniz veya özellik tur kullanılan tam örnek karşıdan yükleyip kendiniz adımları izleyin. Örneği indirmek ve izlemek için Git [Fotoğraf Görüntüleyicisi Demo](https://code.msdn.microsoft.com/windowsdesktop/WPF-Photo-Viewer-Demo-be75662a).

|         |         |
|---------|---------|
|  ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin")  |    [Bir video izlemek](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugger-Feature-tour-of-Visual-studio-2017-sqwiwLD6D_1111787171) hata ayıklamayı benzer adımları gösterir. |

Tanıtım uygulamasını C# olsa da, özellikleri, C++, Visual Basic, JavaScript ve (belirtilenler dışında) Visual Studio tarafından desteklenen diğer diller için geçerlidir.

Bu öğreticide şunları yapacaksınız:

> [!div class="checklist"]
> * Hata ayıklayıcı başlatın ve kesme noktası isabet.
> * Hata ayıklayıcı kodda adım adım komutlarını öğrenin
> * Veri ipuçları ve hata ayıklayıcı windows değişkenler inceleyin.
> * Çağrı yığını inceleyin
> * Özel durum Yardımcısını kullanma

## <a name="prerequisites"></a>Önkoşullar

* Visual Studio 2017 yüklü olması gerekir ve. **NET masaüstü geliştirme** iş yükü.

    Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

    İş yükü yüklenir ancak tıklatın Visual Studio zaten gerektiğinde **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu (seçin **dosya**  >  **Yeni** > **proje**). Visual Studio yükleyicisi başlatır. ' I seçin. **NET masaüstü geliştirme** iş yükü, ardından **Değiştir**.

## <a name="start-the-debugger"></a>Hata ayıklayıcı başlayın!

1. Visual Studio'da bu adımları boyunca takip etmek için örnek indirme [bu sayfadaki](https://code.msdn.microsoft.com/windowsdesktop/WPF-Photo-Viewer-Demo-be75662a).

    > [!IMPORTANT]
    > Kullanmakta olduğunuz uygulama gösteride çalıştırmak için .NET masaüstü geliştirme iş yükü ile Visual Studio yüklemeniz gerekir.

2. Projeyi ayıklayın.

3. Visual Studio'yu açın ve seçin **Dosya > Aç** menü komut'ı seçin **proje/çözüm**ve sonra projeyi indirdiğiniz klasörünü açın.

     ![Örnek Proje Aç](../debugger/media/dbg-tour-open-project.png "Proje Aç")

3. WPF Fotoğraf Görüntüleyicisi Demo açmak > C# klasörü, photoapp.sln dosyayı seçin ve Seç **açık**.

     Visual Studio'da projeyi açar. Çözüm Gezgini sağ bölmedeki tüm proje dosyalarını gösterir.

    ![Çözüm Gezgini dosyaları](../debugger/media/dbg-tour-solution-explorer.png "Çözüm Gezgini")

4. F5 tuşuna basın (**hata ayıklama > hata ayıklamayı Başlat** veya **hata ayıklamayı Başlat** düğmesini ![hata ayıklamayı Başlat](../debugger/media/dbg-tour-start-debugging.png "hata ayıklamayı Başlat") hata ayıklama araç çubuğunda).

     ![Fotoğraf Görüntüleyicisi uygulaması](../debugger/media/dbg-tour-wpf-app.png "Fotoğraf Görüntüleyicisi uygulama")

     F5 hata ayıklayıcısı uygulama işlemini, ancak sağ biz henüz tüm kesme noktalarını eklenen veya kodu incelemek için özel bir şey bitti artık ekli uygulama başlatır. Bu nedenle yalnızca uygulamayı yükler ve fotoğraf görüntüleri bakın.

     Bu tur, biz daha yakın bir hata ayıklayıcı kullanarak bu uygulamaya göz atın ve hata ayıklayıcı göz özellikleri almak.

5. Kırmızı Durdur tuşlarına basarak hata ayıklayıcıyı ![durdurma hata ayıklama](../debugger/media/dbg-tour-stop-debugging.png "durdurma hata ayıklama") düğmesi.

## <a name="set-a-breakpoint-and-start-the-debugger"></a>Bir kesme noktası ayarlayın ve hata ayıklayıcısı başlatın

Hata ayıklamak için uygulamanızı hata ayıklayıcısı ekli uygulama işlemi ile başlamanız gerekir.

1. İçinde `MainWindow` MainWindow.xaml.cs, oluşturucusunun kod ilk satırının sol kenar boşluğu tıklayarak bir kesme noktası ayarlayın.

     ![Bir kesme noktası belirleyerek](../debugger/media/dbg-tour-set-a-breakpoint.gif "SetABreakPoint")

6. F5 tuşuna basın veya **hata ayıklamayı Başlat** button, uygulama başlatır ve kesme ayarladığınız kod satırına hata ayıklayıcı çalıştırır.

    Sarı ok üzerinde hata ayıklayıcı duraklatıldı, deyim Ayrıca uygulama (Bu deyim henüz çalıştırılmadı) noktada durduran temsil eder.

    F5 sonraki kesme uygulama çalışmaya devam eder. (Uygulama henüz çalışmıyorsa, F5 hata ayıklayıcıyı başlatır ve ilk kesme noktasında durur.)

    Kod satırını veya bir bölümünü ayrıntılı olarak incelemek istediğiniz kod bildiğinizde kesme noktaları yararlı bir özelliktir.

## <a name="restart-your-app-quickly"></a>Uygulamanızı hızlı bir şekilde yeniden başlatın

Tıklatın **yeniden** ![yeniden uygulama](../debugger/media/dbg-tour-restart.png "RestartApp") hata ayıklama araç çubuğunda düğmesini (Ctrl + Shift + F5).

Bastığınızda **yeniden**, uygulama durdurup hata ayıklayıcı karşı zamandan tasarruf sağlar. Hata ayıklayıcı kodu yürüterek isabet ilk kesme noktasındaki duraklatır.

Hata ayıklayıcı yeniden de, ayarlayabileceğiniz kesme noktasında durur `MainWindow` Oluşturucusu.

## <a name="navigate-code-in-the-debugger-using-step-commands"></a>Kod adım komutlarını kullanarak hata ayıklayıcısında gidin

Almak için en iyi yolu olduğundan çoğunlukla, klavye kısayollarını burada kullanıyoruz (komutları parantez içinde gösterilen eşdeğer komutları menüsü gibi) hata ayıklayıcısında uygulamanızı yürütülürken en hızlı.

1. F11 tuşuna basın (**hata ayıklama > Step Into**) iki kez yürütülmesi için uygulama, ilerlemek için `InitializeComponent()` işlevi.

     ![Step Into kodu F11 kullanmak](../debugger/media/dbg-tour-f11.png "F11 adımla")

     F11 olan **Step Into** komut ve aynı anda uygulama yürütme bir deyim ilerletir. F11 yürütme akış çoğu ayrıntılı incelemek için iyi bir yoludur. (Daha hızlı kod üzerinden taşımak için diğer bir seçenek de gösteriyoruz.) Varsayılan olarak, hata ayıklayıcı kullanıcı olmayan kod atlar (daha ayrıntılı bilgi isterseniz bkz [sadece kendi kodumu](../debugger/just-my-code.md)).

     >[!NOTE]
     > Yönetilen kodda özellikleri ve işleçler (varsayılan davranış) otomatik olarak adım için bildirim isteyip istemediğinizi soran bir iletişim kutusu görürsünüz. Ayarı değiştirmek istiyorsanız, devre dışı daha sonra **özellikleri ve işleçleri Adımlama** ayarı **Araçlar > Seçenekler** menüsünün altında **hata ayıklama**.

2. F10 tuşlarına basın (**hata ayıklama > Step Over**) kod ilk satırdaki hata ayıklayıcı birkaç kez durdurur kadar `OnApplicationStartup` olay işleyicisi.

     ![Step Over kodu F10 kullanmak](../debugger/media/dbg-tour-f10-step-over.png "F10 Step Over")

     F10 işlevler veya yöntemler (kod hala çalıştırır), uygulama kodunuzda içine atlamadan hata ayıklayıcı ilerler. F10 tuşlarına basarak `InitializeComponent` yöntem çağrısı uygulama kodunu üzerinden atlandı (F11 yerine), biz `InitializeComponent` (biz değil ilgileniyor içinde şu anda hangi olabilir).

## <a name="step-into-a-property"></a>Bir özellikte adım

1. Hata ayıklayıcısını kullanmaya Bu kod satırı duraklatıldı:

    ````
    mainWindow.Photos.Path = Environment.CurrentDirectory + "\\images";
    ````

    Kod satırı sağ tıklatın ve seçin **içine belirli adım**, ardından **SDKSamples.ImageSample.PhotoCollection.Path.set**

     ![Belirli özellik adımla kullanmak](../debugger/media/dbg-tour-step-into-specific.png "içine belirli adım")

    Hata ayıklayıcı atlar yönetilen özellikleri ve alanları üzerinde varsayılan olarak daha önce belirtildiği gibi ancak **içine belirli adım** komutu bu davranışı geçersiz kılmanıza olanak sağlar. Şu an için olanlar Ara istiyoruz zaman `Path.set` özellik ayarlayıcı çalıştırır. **İçine belirli adım** bize alır `Path.set` burada kod.

     ![Özel adımla sonucunu](../debugger/media/dbg-tour-step-into-specific-2.png "içine belirli adım")

     `Update` Yöntemi bu kodda ilgi çekici olabilir görülüyor bunu sağlar, bu kodu yakından incelemek için hata ayıklayıcı kullanın.

5. Üzerine gelerek `Update` yeşil kadar yöntemi **tıklatın çalıştırmak** düğmesini ![çalıştırmak için tıklatın](../debugger/media/dbg-tour-run-to-click.png "RunToClick") soldaki bölmede görüntülenir.

     ![Tıklatın Çalıştır kullanma özelliği](../debugger/media/dbg-tour-run-to-click-2.png "çalıştırmak için tıklatın")

    >  [!NOTE] 
    > **Tıklatın çalıştırmak** düğmesi yeni [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]. Yeşil ok düğmesini görmüyorsanız, F11 Bu örnekte, hata ayıklayıcı ilerletmek için bunun yerine kullanın.

6. Tıklatın **çalıştırmak için tıklatın** düğmesini ![tıklatın çalıştırmak](../debugger/media/dbg-tour-run-to-click.png "RunToClick").

    Bu düğme kullanarak geçici bir kesme noktası ayarlama benzer. **I Çalıştır** (herhangi bir açık dosyada tıklatabilirsiniz) uygulama kodunun görünür bir bölgedeki hızla dolaşma için kullanışlıdır.

    Hata ayıklayıcı için ilerleyen `Update` yöntem uygulaması.

7. Basın adımla F11 `Update` yöntemi.

     ![Güncelleştirme yöntemi Adımlama sonucunu](../debugger/media/dbg-tour-update-method.png "Step Into güncelleştirme yöntemi")

    Burada, ilginç görünüyor biraz daha fazla kod Bul; uygulamanın belirli bir dizinde bulunan ve her dosya için bir fotoğraf nesnesi oluşturma tüm *.jpg dosyaları alınıyor. Bu kod bize uygulama durumu (değişkenler) hata ayıklayıcısı ile inceleniyor başlatmak için iyi bir fırsat sunar. Bu öğreticinin sonraki bölümlerde bunu.

    Değişkenleri incelemek sağlayan özellikler hata ayıklayıcısının en kullanışlı özelliklerinden biridir ve yapmak için farklı yolu vardır. Genellikle, bir sorun hata ayıklamak çalıştığınızda değişkenleri olup onlara belirli bir zamanda beklediğiniz değerlerini depolayan çıkışı bulmak çalışıyorsunuz.

## <a name="examine-the-call-stack"></a>Çağrı yığını inceleyin

İçinde duraklatıldı sırada `Update` yöntemi tıklatın **çağrı yığını** , varsayılan alt sağ bölmede açık olan penceresinin.

![Çağrı yığınını incelemek](../debugger/media/dbg-tour-call-stack.png "ExamineCallStack")

**Çağrı yığını** penceresi içinde yöntemleri ve işlevleri denir sipariş gösterir. Üst çizgi geçerli işlevi gösterir ( `Update` turu uygulama yönteminde). İkinci satır gösterir `Update` çağırıldığı `Path.set` özelliği ve benzeri.

>  [!NOTE]
> **Çağrı yığını** penceresi benzer hata ayıklama perspektife Eclipse gibi bazı IDE içinde.

Çağrı yığınını incelemek ve bir uygulamanın yürütme akışını anlamak için iyi bir yoludur.

Bu kaynak koduna bakmanız gitmek için kod satırı çift tıklatın ve hata ayıklayıcı tarafından denetlenmekte olan geçerli kapsam, ayrıca değiştirir. Bu eylem, hata ayıklayıcı ilerleyin değil.

Sağ menülerden de kullanabilirsiniz **çağrı yığını** başka şeyler için penceresi. Örneğin, belirtilen işlevlerini kesme noktaları ekleme, kullanarak hata ayıklayıcı ilerletmek **çalıştırmak için imleç**ve kaynak kodunu incelemek gidin. Daha fazla bilgi için bkz: [nasıl yapılır: çağrı yığını inceleyin](../debugger/how-to-use-the-call-stack-window.md).

## <a name="step-out"></a>Dışarı Adım

Yapılır olduğunu düşünelim inceleniyor `Update` yöntemi Data.cs ve istediğiniz dışında işlevi alır ancak hata ayıklayıcısı'ndaki kalır. Kullanarak bunu yapabilirsiniz **Step Out** komutu.

1. Shift + F11 tuşlarına basın (veya **hata ayıklama > dışarı adım**).

     Bu komut, uygulama yürütme sürdürür (ve hata ayıklayıcısı ilerler) kadar geçerli işlevi döndürür.

     Geri olmalıdır `Update` Data.cs yöntem çağrısında.

2. Shift + F11 yeniden ve hata ayıklayıcısı basın çağrı yığını yukarı gider başa `OnApplicationStartup` olay işleyicisi.

## <a name="run-to-cursor"></a>İmleci çalıştırın

1. Seçin **durdurma hata ayıklama** kırmızı düğme ![durdurma hata ayıklama](../debugger/media/dbg-tour-stop-debugging.png "durdurma hata ayıklama") ya da Shift + F5'e.

2. İçinde `Update` Data.cs, yönteminde sağ `Add` yöntemini çağırın ve seçin **çalıştırmak için imleç**. Bu komut, hata ayıklama başlatır ve geçici bir kesme noktası geçerli kod satırında ayarlar.

     ![İmleç özelliği için Çalıştır'ı kullanın](../debugger/media/dbg-tour-run-to-cursor.png "için imleç çalıştırın")

    Kesme üzerinde duraklatıldı `MainWindow` (ilk kesme olduğu için ayarladığınız).

3. İlerletmek için F5 tuşuna basın `Add` seçtiğiniz yöntemi **çalıştırmak için imleç**.

    Bu komut, kod düzenleme ve hızlı bir şekilde geçici bir kesme noktası ayarlayın ve hata ayıklayıcısı başlatmak istediğinizde yararlıdır.

## <a name="change-the-execution-flow"></a>Yürütme akışını değiştirme

1. Hata ayıklayıcısını kullanmaya üzerinde duraklatıldı `Add` yöntem çağrısı, soldaki sarı ok (yürütme işaretçisi) şablonlarınızdan fare kullanın ve sarı ok bir satır yukarı taşı `foreach` döngü.

     ![Yürütme işaretçiyi](../debugger/media/dbg-tour-move-the-execution-pointer.gif "yürütme işaretçiyi taşıyın")

    Yürütme akış değiştirerek farklı kod yürütme yollarını test veya hata ayıklayıcı başlatmadan kodu yeniden gibi işlemler yapabilirsiniz.

2. Şimdi, F5 tuşuna basın.

    Uygulama penceresine eklenen görüntüleri görebilirsiniz. Kodu yeniden çünkü `foreach` döngü, bazı resimler iki kez eklendi!
    
    > [!WARNING]
    > Genellikle bu özellikle dikkatli olmanız gerekir ve araç ipucunda bir uyarı görürsünüz. Diğer uyarılar çok görebilirsiniz. İşaretçinin taşınması bir önceki uygulama durumu uygulamanıza geri alınamaz.

## <a name="inspect-variables-with-data-tips"></a>Veri ipuçları değişkenlerle inceleyin.

1. Data.cs Fotoğraf Görüntüleyicisi tanıtım uygulamasını açın, sağ `private void Update` işlevi bildiriminde ve seçin **çalıştırmak için imleç** (zaten çalışıyorsa, uygulamayı ilk durdurun).

    Bu uygulama hata ayıklayıcısı ekli duraklatılır. Bu bize durumunu incelemek sağlar.

2. Üzerine gelerek `Add` yöntemini çağırın ve tıklatın **çalıştırmak için tıklatın** düğmesi ![tıklatın çalıştırmak](../debugger/media/dbg-tour-run-to-click.png "RunToClick").

3. Şimdi, dosya nesnenin üzerine getirin (`f`) ve varsayılan özellik değeri, dosya adı gördüğünüz `market 031.jpg`.

     ![Veri ipucunu görüntüleme](../debugger/media/dbg-tour-data-tips.gif "veri ipucunu görüntüleme")

4. Tüm özelliklerini gibi görmek için nesnesini genişletin `FullPath` özelliği.

    Genellikle, hata ayıklama sırasında istediğiniz nesnelerin özellik değerlerini kontrol etmenin hızlı bir yolu ve veri ipuçları yapmak için iyi bir yoldur.

    > [!TIP]
    > Değiştirmek istediğiniz bir şey fark ederseniz, en desteklenen dilleri kodu bir hata ayıklayıcı oturumu ortasında düzenleyebilirsiniz. Daha fazla bilgi için bkz: [Düzenle ve devam et](../debugger/edit-and-continue.md). Bu uygulamada bu özelliği kullanmak için ancak biz öncelikle uygulamanın .NET Framework sürümünü güncelleştirmek gerekir.

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>Otomatik değişkenler ve yerel windows değişkenlerle inceleyin.

1. Bakmak **otomobiller** Kod düzenleyicisinde sonundaki penceresi.

     ![Otomatik değişkenler penceresi değişkenlerde incelemek](../debugger/media/dbg-tour-autos-window.png "otomatik değişkenler penceresi")

    İçinde **otomobiller** penceresinde, değişkenler ve bunların geçerli değerini bakın. **Otomobiller** penceresi geçerli veya önceki satır üzerinde kullanılan tüm değişkenleri gösterir (içinde C++ pencere gösterir değişkenleri önceki üç kod satırıyla. Dile özgü davranışı için belgelere bakın).

    > [!NOTE]
    > JavaScript'te, **Yereller** penceresi ancak desteklenen **otomobiller** penceresi.

2. Ardından, bakmak **Yereller** penceresi.

    **Yereller** penceresi geçerli kapsamdaki değişkenler gösterir.

    ![Yerel öğeler penceresi değişkenlerde incelemek](../debugger/media/dbg-tour-locals-window.png "yerel öğeler penceresi")

    Şu anda `this` nesnesi ve dosya nesnesi (`f`) geçerli kapsam içindedir. Daha fazla bilgi için bkz: [otomobiller ve yerel Windows incelemek değişkenler](../debugger/autos-and-locals-windows.md).

## <a name="set-a-watch"></a>Bir izleme ayarlama

1. Ana Kod Düzenleyicisi penceresinde, dosya nesneye sağ tıklayın (`f`) ve **Gözcü Ekle**.

    Kullanabileceğiniz bir **izleme** penceresi bir değişken (veya bir ifade) takip istediğinizi belirtin.

    Artık Ayarla izleme zorunda `File` nesne ve hata ayıklayıcı taşırken değiştirme değeri görebilirsiniz. Diğer değişken windows aksine **izleme** penceresi her zaman, izlerken değişkenleri gösterir (bunlar zaman kapsamının dışına gri).

2. Üzerinde `Add` yöntemi, yeşil tıklatın ![çalıştırmak için tıklatın](../debugger/media/dbg-tour-run-to-click.png "RunToClick") yeniden düğmesini (veya F11 birkaç kez basın) aracılığıyla ilerletmek için `foreach` döngü.

    ![Bir izleme üzerinde bir değişken ayarlamak](../debugger/media/dbg-tour-watch-window.png "Gözcü penceresi")

    Ayrıca, çalışan ana pencereyi eklenir ilk resim görebilirsiniz örnek uygulaması, ancak bu görüntüleri henüz görünür olmayabilir için farklı uygulama iş parçacığı üzerinde olur.

    Daha fazla bilgi için bkz: [izleme ve QuickWatch Windows kullanılarak izleme ayarlama](../debugger/watch-and-quickwatch-windows.md)

## <a name="examine-an-exception"></a>Bir özel durum inceleyin

1. Çalışan uygulama penceresinde metni silin **yolu** giriş kutusu ve select **değişiklik** düğmesi.

     ![Bir özel durum oluşturulmasına neden](../debugger/media/dbg-tour-cause-an-exception.png "bir özel durum neden")

     Uygulama bir özel durum oluşturur ve hata ayıklayıcısını özel durum oluşturdu kod satırına alır.
     
     ![Özel durum Yardımcısı](../debugger/media/dbg-tour-exception-helper.png "özel durum Yardımcısı")

     Burada, **özel durum Yardımcısı** , gösterir bir `System.ArgumentException` ve yolun geçerli bir biçimde olmadığını bildiren bir hata iletisi. Bu nedenle, bir yöntemi veya işlev bağımsız değişken bir hata oluştu biliyoruz.

     Bu örnekte, `DirectoryInfo` çağrısı depolanan boş dize üzerinde hata vermiş `value` değişkeni. (Üzerine gelerek `value` boş dize görmek için.)

     Özel durum Yardımcısı hataları hata ayıklama yardımcı olabilecek harika bir özelliktir. Ayrıca, hata ayrıntıları görünümü gibi şeyler ve özel durum Yardımcısı bir izleme ekleyin. Ya da gerekirse, belirli özel durum atma koşulları değiştirebilirsiniz.

    >  [!NOTE] 
    > Özel durum Yardımcısı özel durum Yardımcısı'nda değiştirir [!include[vs_dev15](../misc/includes/vs_dev15_md.md)].

2. Genişletme **Exception ayarlarını** düğümü bu özel durum türü, ancak işleme konusunda daha fazla seçenek görmek için bu tur değişikliği gerekmez!

3. Uygulama devam etmek için F5 tuşuna basın.

Hata ayıklayıcı özellikleri hakkında daha fazla bilgi için bkz: [hata ayıklayıcı ipuçları ve püf noktaları](../debugger/debugger-tips-and-tricks.md).

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, adım kodlarda, hata ayıklayıcı başlatmak ve değişkenleri incelemek üzere nasıl öğrendiniz. Daha fazla bilgi için bağlantılar ile birlikte hata ayıklama özellikleri en üst düzey bir görünüm elde isteyebilirsiniz.

> [!div class="nextstepaction"]
> [Hata ayıklayıcısı özellik turu](../debugger/debugger-feature-tour.md)
