---
title: CPU kullanımı verilerini (ASP.NET) çözümleme
description: CPU kullanımı Tanılama Aracı'nı kullanarak ASP.NET uygulamaları, uygulama performansını
ms.custom: mvc
ms.date: 12/05/2017
ms.technology: vs-ide-debug
ms.topic: quickstart
helpviewer_keywords:
- Profiling Tools, quick start
- Diagnostics Tools, CPU Usage
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 3309435600991db85540c95dc969206619438e51
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="quickstart-analyze-cpu-usage-data-in-visual-studio-aspnet"></a>Hızlı Başlangıç: CPU kullanım verileri, Visual Studio (ASP.NET) analiz etme

Visual Studio, uygulamanızda performans sorunları analiz etmenize yardımcı olmak üzere pek çok güçlü özellikler sağlar. Bu konuda, temel özelliklerden bazıları öğrenmek için hızlı bir yoludur. Burada, yüksek CPU kullanımından kaynaklanan performans sorunlarını tanımlamak için bir aracı ele. Tanılama araçları, yerel/C++ geliştirme ve ASP.NET, dahil olmak üzere Visual Studio .NET geliştirme için desteklenir.

Tanılama hub'ı çok çalıştırın ve tanılama oturumunuz yönetmek için diğer seçenekleri sunar. Varsa **CPU kullanımı** burada açıklanan aracı verme, ihtiyaç duyduğunuz, veri [diğer profil oluşturma araçları](../profiling/Profiling-Tools.md) değişik size yardımcı olabilecek bilgiler sağlar. Çoğu durumda, uygulamanızın performans düşüklüğü, CPU, bellek, işleme kullanıcı Arabirimi veya ağ istek süresi gibi dışında bir şey tarafından kaynaklanıyor olabilir.

> [!NOTE]
> .NET Core ve ASP.NET Core için CPU kullanımını aracı taşınabilir PBDs ile doğru sonuçlar şu anda sağlamaz. Bunun yerine tam pdb kullanın.

## <a name="create-a-project"></a>Proje oluşturma

1. Visual Studio'da, **Dosya > Yeni proje**.

1. Altında **Visual C#**, seçin **Web**ve ardından Orta bölmede **ASP.NET Web uygulaması (.NET Framework)**.

    > [!NOTE]
    > CPU kullanımı aracı ASP.NET Core şu anda desteklenmiyor.

1. Gibi bir ad yazın **MyProfilingApp_MVC** tıklatıp **Tamam**.

1. Görüntülenen iletişim kutusunda seçin **MVC** orta bölmesinde ve ardından **Tamam**.

    Visual Studio projesi oluşturur. Çözüm Gezgini (sağ bölme), proje dosyalarını gösterir.

1. Çözüm Gezgini'nde, modeller klasörü sağ tıklatın ve seçin **Ekle** > **sınıfı**.

1. Yeni sınıf `Data.cs` ve **Ekle**.

1. Çözüm Gezgini'nde açık `Models/Data.cs` ve aşağıdakileri ekleyin `using` dosyanın en üstüne ifadesine:

    ```cs
    using System.Threading;
    ```

1. Aşağıdaki kod Data.cs değiştirin:

    ```cs
    public class Data
    {
    }
    ```

    Bu kodu:

    ```cs
    public class ServerClass
    {
        const int MIN_ITERATIONS = int.MaxValue / 1000;
        const int MAX_ITERATIONS = MIN_ITERATIONS + 10000;

        long m_totalIterations = 0;
        readonly object m_totalItersLock = new object();
        // The method that will be called when the thread is started.
        public void GenerateData()
        {
            Console.WriteLine(
                "ServerClass.InstanceMethod is running on another thread.");

            var x = GetNumber();
        }

        private int GetNumber()
        {
            var rand = new Random();
            var iters = rand.Next(MIN_ITERATIONS, MAX_ITERATIONS);
            var result = 0;
            lock (m_totalItersLock)
            {
                m_totalIterations += iters;
            }
            // we're just spinning here  
            // and using Random to frustrate compiler optimizations  
            for (var i = 0; i < iters; i++)
            {
                result = rand.Next();
            }
            return result;
        }
    }

    public class Simple
    {
        int numberOfThreads = 200;

        public Simple()
        {
            for (int i = 0; i < numberOfThreads; i++)
            {
                CreateThreads();
            }
        }
        public static void CreateThreads()
        {
            ServerClass serverObject = new ServerClass();

            Thread InstanceCaller = new Thread(new ThreadStart(serverObject.GenerateData));
            // Start the thread.
            InstanceCaller.Start();

            Console.WriteLine("The Main() thread calls this after "
                + "starting the new InstanceCaller thread.");

        }

        public int GetData()
        {
            // Not returning any meaningful data.
            return numberOfThreads;
        }
    }
    ```

1. Çözüm Gezgini'nde, Controller/HomeControllers.cs açın ve aşağıdaki kodu değiştirin:

    ```cs
    public ActionResult About()
    {
        ViewBag.Message = "Your application description page.";

        return View();
    }
    ```

    Bu kodu:

    ```cs
    public ActionResult About()
    {
        Models.Simple s = new Models.Simple();

        ViewBag.Message = "Your application description page.";

        return View(s.GetData());
    }
    ```

##  <a name="BKMK_Quick_start__Collect_diagnostic_data"></a> 1. adım: profil oluşturma verilerini topla 
  
1.  İlk olarak, bu kod satırı üzerinde uygulamanızda bir kesme noktası belirleyerek `Simple` Oluşturucusu:

    `for (int i = 0; i < 200; i++)`

    Cilt payını sola kod satırının tıklayarak bir kesme noktası ayarlayın.

1.  Ardından, sonunda kapanış parantezi ikinci bir kesme noktası ayarlayın `Simple` Oluşturucusu:

     ![Profil oluşturma için kümesi kesme noktaları](../profiling/media/quickstart-cpu-usage-breakpoints-aspnet.png)

    > [!TIP]
    > İki kesme noktası belirleyerek, çözümlemek istediğiniz kod parçalarını veri toplama sınırlayabilirsiniz.
  
1.  **Tanılama araçları** penceredir zaten görünür, onu devre dışı bırakmış sürece. Pencereyi yeniden getirmek için tıklatın **hata ayıklama / Windows / Tanılama Araçları Göster**.

1.  Tıklatın **hata ayıklama / hata ayıklamayı Başlat** (veya **Başlat** araç çubuğunda veya **F5**).

1.  Uygulama yükleme bittiğinde, bilgisayarınızı **hakkında** yeni kod başlamasını web sayfasının üst bağlantı.

1.  Bakmak **Özet** Tanılama Araçları'nın görünümü görüntülenir.

1.  Hata ayıklayıcı durdurulduğunda, CPU kullanım verileri toplamayı seçerek etkinleştirin **kayıt CPU profili**ve ardından açın **CPU kullanımı** sekmesi.

     ![CPU profil tanılama araçlarını etkinleştirme](../profiling/media/quickstart-cpu-usage-summary.png)

     Veri toplama etkin olduğunda, kırmızı bir daire Kaydet düğmesine görüntüler.

     Seçtiğinizde **kayıt CPU profili**, Visual Studio işlevlerinizi kaydı başlayacak ve aldıkları yürütmek için ne kadar süre ve ayrıca belirli örnekleme oturum kesimlerinde odaklanmak için kullanabileceğiniz bir zaman çizelgesi grafik sağlar. Uygulamanızı bir kesme noktasında durdurulamaz olduğunda, yalnızca bu toplanan verileri görüntüleyebilirsiniz.

6.  İkinci isabetini uygulamayı çalıştırmak için F5'e basın.

     Şimdi, artık performans verilerini bölge için özellikle uygulamanıza iki kesme noktaları arasında çalışan kod sahipsiniz.

     Profil Oluşturucu iş parçacığı verileri hazırlama başlar. Bitmesini bekleyin.
  
     Raporda CPU kullanımı araç görüntüler **CPU kullanımı** sekmesi.

     Bu noktada, verileri çözümlemek başlayabilirsiniz.

## <a name="Step2"></a> 2. adım: CPU kullanım verilerini çözümleme

CPU kullanımı altında işlevlerin listesi inceleyerek, en fazla çalışmayı yapan işlevleri tanımlama ve her biri daha ayrıntılı bir bakış alma verilerinizi incelemeye başlamak öneririz.

1. İşlev listesinde en fazla çalışmayı yapan işlevleri inceleyin.

     ![CPU kullanımı sekmesi tanılama araçları](../profiling/media/quickstart-cpu-usage-cpu-aspnet.png)

    > [!TIP]
    > İşlevler en fazla çalışmayı yapan olanlar başlangıç sırayla listelenir (çağrı sırayla olmadıklarını). Bu en uzun çalışan işlevleri hızla tanımlamanıza yardımcı olur.

2. İşlev listesinde çift `MyProfilingApp_MVC.Models.ServerClass::GetNumber` işlevi.

    İşlev çift tıkladığınızda **arayan/Aranan** sol bölmede görünümünü açar. 

    ![Tanılama araçları çağıran Aranan görünümü](../profiling/media/quickstart-cpu-usage-caller-callee-aspnet.png)

    Başlık hem de bu görünümde seçili işlevi görüntülenir **geçerli işlevi** kutusunu (`ServerClass::GetNumber`, bu örnekte). Solda'nin altında gösterilen geçerli işlevini çağırdı işlevi **işlevi çağırma**, ve geçerli işlev tarafından çağrılan tüm işlevler gösterilir **çağrılan işlevler** sağdaki kutusu. (Geçerli işlevi değiştirmek için ya da kutusunu seçebilirsiniz.)

    Bu görünüm toplam süre (ms) ve genel uygulamayı işlevi tamamlamak için geçen zaman yüzdesini gösterir.

    **İşlev gövdesi** ayrıca toplam zamanı (ve zamanı yüzdesi) işlev gövdesine harcanan zaman hariç içinde arama harcanan ve işlevleri adlı gösterilmektedir. (Bu çizimde, işlev gövdesi ve kalan süreyi 2235 ms dışında 2220 harcanan (< 20 ms) Bu işlev tarafından çağrılan dış kodunda harcanan). Gerçek değerler ortamınıza bağlı olarak farklı olacaktır.

    > [!TIP]
    > Yüksek değerleri **işlev gövdesi** işlevi içinde performans sorunu gösteriyor olabilir.

## <a name="next-steps"></a>Sonraki adımlar

- [Bellek kullanımını çözümleme](../profiling/memory-usage.md)performans sorunlarını tanımlamak için.
- [CPU kullanımı analiz](../profiling/cpu-usage.md) CPU kullanımı aracı hakkında daha ayrıntılı bilgi için.
- -Daha fazla bilgi için çalışan bir uygulamanın hedefleyerek veya bir hata ayıklayıcısı ekli olmadan CPU kullanımı analiz [hata ayıklama olmadan profil oluşturma verilerini toplama](../profiling/running-profiling-tools-with-or-without-the-debugger.md#collect-profiling-data-without-debugging) içinde [Profil Araçları ile veya olmadan hata ayıklayıcı çalıştırmak](../profiling/running-profiling-tools-with-or-without-the-debugger.md).

## <a name="see-also"></a>Ayrıca Bkz.  

 [Visual Studio'da profil oluşturma](../profiling/index.md)  
 [Profil oluşturma özelliği turu](../profiling/profiling-feature-tour.md)
