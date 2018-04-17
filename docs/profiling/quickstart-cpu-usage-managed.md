---
title: CPU kullanımı verilerini (yönetilen kod) çözümleme | Microsoft Docs
ms.custom: ''
ms.date: 12/05/2017
ms.technology:
- vs-ide-debug
ms.topic: quickstart
helpviewer_keywords:
- Profiling Tools, quick start
- Diagnostics Tools, CPU Usage
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: e94aa17419cca3944f3a884b49069b29c4a24e8c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="analyze-cpu-usage-data-in-visual-studio-managed-code"></a>Visual Studio (yönetilen kod) CPU kullanım verilerini çözümleme

Visual Studio, uygulamanızda performans sorunları analiz etmenize yardımcı olmak üzere pek çok güçlü özellikler sağlar. Bu konuda, temel özelliklerden bazıları öğrenmek için hızlı bir yoludur. Burada, yüksek CPU kullanımından kaynaklanan performans sorunlarını tanımlamak için aracı ele. Tanılama araçları, yerel/C++ geliştirme ve ASP.NET, dahil olmak üzere Visual Studio .NET geliştirme için desteklenir.

Tanılama hub'ı çok çalıştırın ve tanılama oturumunuz yönetmek için diğer seçenekleri sunar. Varsa **CPU kullanımı** burada açıklanan aracı verme, ihtiyaç duyduğunuz, veri [diğer profil oluşturma araçları](../profiling/profiling-feature-tour.md) değişik size yardımcı olabilecek bilgiler sağlar. Çoğu durumda, uygulamanızın performans düşüklüğü, CPU, bellek, işleme kullanıcı Arabirimi veya ağ istek süresi gibi dışında bir şey tarafından kaynaklanıyor olabilir. Tanılama hub'ı çok kaydetmek ve bu tür verilerin çözümlemek için diğer seçenekleri sunar.

> [!NOTE]
> .NET Core ve ASP.NET Core için CPU kullanımını aracı taşınabilir PBDs ile doğru sonuçlar şu anda sağlamaz. Bunun yerine tam pdb kullanın.

## <a name="create-a-project"></a>Proje oluşturma

1. Visual Studio'da, **Dosya > Yeni proje**.

2. Altında **Visual C#** veya **Visual Basic**, seçin **Windows Klasik Masaüstü**ve ardından Orta bölmede **konsol uygulaması (.NET Framework)**.

3. Gibi bir ad yazın **MyProfilerApp** tıklatıp **Tamam**.

    Visual Studio projesi oluşturur.

2. Program.cs açın ve tüm kodu aşağıdaki kodla değiştirin:

    ```cs
    using System;
    using System.Threading;
    public class ServerClass
    {
        const int MIN_ITERATIONS = int.MaxValue / 1000;
        const int MAX_ITERATIONS = MIN_ITERATIONS + 10000;
    
        long m_totalIterations = 0;
        readonly object m_totalItersLock = new object();
        // The method that will be called when the thread is started.
        public void DoWork()
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
        public static void Main()
        {
            for (int i = 0; i < 200; i++)
            {
                CreateThreads();
            }
        }
        public static void CreateThreads()
        {
            ServerClass serverObject = new ServerClass();
    
            Thread InstanceCaller = new Thread(new ThreadStart(serverObject.DoWork));
            // Start the thread.
            InstanceCaller.Start();
    
            Console.WriteLine("The Main() thread calls this after "
                + "starting the new InstanceCaller thread.");
    
        }
    }
    ```

    ```vb
    Imports System
    Imports System.Threading
    
    Namespace MyProfilerApp
        Public Class ServerClass
            Const MIN_ITERATIONS As Integer = Integer.MaxValue / 1000
            Const MAX_ITERATIONS As Integer = MIN_ITERATIONS + 10000
    
            Private m_totalIterations As Long = 0
            ReadOnly m_totalItersLock As New Object()
            ' The method that will be called when the thread is started.
            Public Sub DoWork()
                Console.WriteLine("ServerClass.InstanceMethod is running on another thread.")
    
                Dim x = GetNumber()
            End Sub
    
            Private Function GetNumber() As Integer
                Dim rand = New Random()
                Dim iters = rand.[Next](MIN_ITERATIONS, MAX_ITERATIONS)
                Dim result = 0
                SyncLock m_totalItersLock
                    m_totalIterations += iters
                End SyncLock
                ' we're just spinning here  
                ' and using Random to frustrate compiler optimizations  
                For i As Integer = 0 To iters - 1
                    result = rand.[Next]()
                Next
                Return result
            End Function
        End Class
    
        Public Class Simple
            Public Shared Sub Main()
                For i As Integer = 0 To 199
                    CreateThreads()
                Next
            End Sub
            Public Shared Sub CreateThreads()
                Dim serverObject As New ServerClass()
    
                Dim InstanceCaller As New Thread(New ThreadStart(AddressOf serverObject.DoWork))
                ' Start the thread.
                InstanceCaller.Start()
    
                Console.WriteLine("The Main() thread calls this after " + "starting the new InstanceCaller thread.")
    
            End Sub
        End Class
    End Namespace
    ```

    > [!NOTE]
    > Visual Basic'te Başlangıç nesnesi ayarlandığından emin olun `Sub Main` (**Özellikler > Uygulama > Başlangıç nesnesi**).

##  <a name="BKMK_Quick_start__Collect_diagnostic_data"></a> 1. adım: profil oluşturma verilerini topla 
  
1.  İlk olarak, bu kod satırı üzerinde uygulamanızda bir kesme noktası belirleyerek `Main` işlevi:

    `for (int i = 0; i < 200; i++)`

    veya Visual Basic için:

    `For i As Integer = 0 To 199`

    Cilt payını sola kod satırının tıklayarak bir kesme noktası ayarlayın.

2.  Ardından, sonunda kapanış parantezi ikinci bir kesme noktası ayarlayın `Main` işlevi:

     ![Profil oluşturma için kesme noktaları ayarlayın](../profiling/media/quickstart-cpu-usage-breakpoints.png "profil oluşturma için kesme noktaları ayarlayın")

    > [!TIP]
    > İki kesme noktası belirleyerek, çözümlemek istediğiniz kod parçalarını veri toplama sınırlayabilirsiniz.
  
3.  **Tanılama araçları** penceredir zaten görünür, onu devre dışı bırakmış sürece. Pencereyi yeniden getirmek için tıklatın **hata ayıklama / Windows / Tanılama Araçları Göster**.

4.  Tıklatın **hata ayıklama / hata ayıklamayı Başlat** (veya **Başlat** araç çubuğunda veya **F5**).

     Uygulama yüklemesi tamamlandığında **Özet** Tanılama Araçları'nın görünümü görüntülenir.

5.  Hata ayıklayıcı durdurulduğunda, CPU kullanım verileri toplamayı seçerek etkinleştirin **kayıt CPU profili**ve ardından açın **CPU kullanımı** sekmesi.

     ![Tanılama araçlarını etkinleştirme CPU profil](../profiling/media/quickstart-cpu-usage-summary.png "tanılama araçlarını etkinleştirme CPU profil oluşturma")

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

     ![Tanılama araçları CPU kullanımı sekmesi](../profiling/media/quickstart-cpu-usage-cpu.png "DiagToolsCPUUsageTab")

    > [!TIP]
    > İşlevler en fazla çalışmayı yapan olanlar başlangıç sırayla listelenir (çağrı sırayla olmadıklarını). Bu en uzun çalışan işlevleri hızla tanımlamanıza yardımcı olur.

2. İşlev listesinde çift `ServerClass::GetNumber` işlevi.

    İşlev çift tıkladığınızda **arayan/Aranan** sol bölmede görünümünü açar. 

    ![Tanılama araçları çağıran Aranan görünümü](../profiling/media/quickstart-cpu-usage-caller-callee.png "DiagToolsCallerCallee")

    Başlık hem de bu görünümde seçili işlevi görüntülenir **geçerli işlevi** kutusunu (`GetNumber`, bu örnekte). Solda'nin altında gösterilen geçerli işlevini çağırdı işlevi **işlevi çağırma**, ve geçerli işlev tarafından çağrılan tüm işlevler gösterilir **çağrılan işlevler** sağdaki kutusu. (Geçerli işlevi değiştirmek için ya da kutusunu seçebilirsiniz.)

    Bu görünüm toplam süre (ms) ve genel uygulamayı işlevi tamamlamak için geçen zaman yüzdesini gösterir.

    **İşlev gövdesi** ayrıca toplam zamanı (ve zamanı yüzdesi) işlev gövdesine harcanan zaman hariç içinde arama harcanan ve işlevleri adlı gösterilmektedir. (Bu çizimde, işlev gövdesi ve kalan süreyi 2856 2863 ms dışında harcanan (< 20 ms) Bu işlev tarafından çağrılan dış kodunda harcanan). Gerçek değerler ortamınıza bağlı olarak farklı olacaktır.

    > [!TIP]
    > Yüksek değerleri **işlev gövdesi** işlevi içinde performans sorunu gösteriyor olabilir.

## <a name="next-steps"></a>Sonraki adımlar

- [Bellek kullanımını çözümleme](../profiling/memory-usage.md)performans sorunlarını tanımlamak için.
- [CPU kullanımı analiz](../profiling/cpu-usage.md) CPU kullanımı aracı hakkında daha ayrıntılı bilgi için.
- -Daha fazla bilgi için çalışan bir uygulamanın hedefleyerek veya bir hata ayıklayıcısı ekli olmadan CPU kullanımı analiz [hata ayıklama olmadan profil oluşturma verilerini toplama](../profiling/running-profiling-tools-with-or-without-the-debugger.md#collect-profiling-data-without-debugging) içinde [Profil Araçları ile veya olmadan hata ayıklayıcı çalıştırmak](../profiling/running-profiling-tools-with-or-without-the-debugger.md).

## <a name="see-also"></a>Ayrıca Bkz.  

 [Visual Studio'da profil oluşturma](../profiling/index.md)  
 [Profil oluşturma özelliği turu](../profiling/profiling-feature-tour.md)
