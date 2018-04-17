---
title: Çok iş parçacıklı uygulamalarda hata ayıklama kullanmaya başlama | Microsoft Docs
ms.custom: H1HackMay2017
ms.date: 06/02/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- multithreaded debugging, tutorial
- tutorials, multithreaded debugging
ms.assetid: 62df746b-b0f6-4df4-83cf-b1d9d2e72833
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cea34a609905ea54b00115ee6d9419eb07c58c0d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="get-started-debugging-a-multithreaded-application-in-visual-studio"></a>Visual Studio'da çok iş parçacıklı uygulamada hata ayıklama kullanmaya başlama
Visual Studio çeşitli araçları ve birden çok iş parçacıklı uygulamalarda hata ayıklama yardımcı olması için kullanıcı arabirimi öğeleri sağlar. Bu öğretici iş parçacığı işaretçileri kullanmayı gösterir **Paralel Yığınlar** penceresinde **paralel Gözcü** penceresi, koşullu kesme noktaları ve filtre kesme noktaları. Bu öğretici yalnızca birkaç dakika sürer ancak tamamlanması, çok iş parçacıklı uygulamalarda hata ayıklama için özelliklerle alışmanızı.

|         |         |
|---------|---------|
|  ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin")  |    [Bir video izlemek](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugging-Multi-threaded-Apps-in-Visual-Studio-2017-MoZPKMD6D_111787171) benzer adımları gösteren birden çok iş parçacıklı hata ayıklama üzerinde. |

Diğer konular, diğer birden çok iş parçacıklı hata ayıklama araçları kullanarak ek bilgileri sağlayın:

- Nasıl kullanılacağını gösterir benzer bir konu için **hata ayıklama konumu** araç ve **iş parçacığı** penceresinde bkz [izlenecek yol: birden çok iş parçacıklı uygulamada hata ayıklama](../debugger/how-to-use-the-threads-window.md).

- Kullanan bir örnek ile benzer bir konu için <xref:System.Threading.Tasks.Task> (yönetilen kod) ve Eşzamanlılık Çalışma zamanı (C++) [izlenecek yol: paralel uygulamada hata ayıklama](../debugger/walkthrough-debugging-a-parallel-application.md). En çok iş parçacıklı uygulama türleri için geçerli genel hata ayıklama ipuçları için bu konu ve bağlantılı konu okuyun.
  
Bu öğreticiye başlamadan birden çok iş parçacıklı uygulama projesi gerekir. Bu projeyi oluşturmak için burada listelenen adımları izleyin.  
  
#### <a name="to-create-the-multithreaded-app-project"></a>Birden çok iş parçacıklı uygulama projesi oluşturmak için  
  
1.  Üzerinde **dosya** menüsünde seçin **yeni** ve ardından **proje**.  
  
     **Yeni proje** iletişim kutusu görüntülenir.  
  
2.  İçinde **proje türü**s kutusunda, tercih ettiğiniz dili seçin: **Visual C#**, **Visual C++**, veya **Visual Basic**.  
  
3.  İçinde **şablonları** kutusunda, seçin **konsol uygulaması**.  
  
4.  İçinde **adı** kutusuna MyThreadWalkthroughApp adı yazın.  
  
5.  **Tamam**'ı tıklatın.  
  
     Yeni bir konsol projesi görüntülenir. Proje oluşturduğunuzda bir kaynak dosya görünür. Seçtiğiniz dil bağlı olarak, kaynak dosya Program.cs, MyThreadWalkthroughApp.cpp veya Module1.vb olarak da adlandırılabilir.  
  
6.  Kaynak dosyasında görünen kodu silin ve burada gösterilen örnek kod ile değiştirin.

    ```csharp
    using System;
    using System.Threading;

    public class ServerClass
    {

        static int count = 0;
        // The method that will be called when the thread is started.
        public void InstanceMethod()
        {
            Console.WriteLine(
                "ServerClass.InstanceMethod is running on another thread.");

            int data = count++;
            // Pause for a moment to provide a delay to make
            // threads more apparent.
            Thread.Sleep(3000);
            Console.WriteLine(
                "The instance method called by the worker thread has ended.");
        }
    }

    public class Simple
    {
        public static void Main()
        {
            for (int i = 0; i < 10; i++)
            {
                CreateThreads();
            }
        }
        public static void CreateThreads()
        {
            ServerClass serverObject = new ServerClass();

            Thread InstanceCaller = new Thread(new ThreadStart(serverObject.InstanceMethod));
            // Start the thread.
            InstanceCaller.Start();

            Console.WriteLine("The Main() thread calls this after "
                + "starting the new InstanceCaller thread.");

        }
    }
    ```

    ```C++
    #include "stdafx.h"
    #include <thread>
    #include <iostream>
    #include <vector>

    int count = 0;

    void doSomeWork() {

        std::cout << "The doSomeWork function is running on another thread." << std::endl;
        int data = count++;
        // Pause for a moment to provide a delay to make
        // threads more apparent.
        std::this_thread::sleep_for(std::chrono::seconds(3));
        std::cout << "The function called by the worker thread has ended." << std::endl;
    }

    int main() {
        std::vector<std::thread> threads;

        for (int i = 0; i < 10; ++i) {

            threads.push_back(std::thread(doSomeWork));
            std::cout << "The Main() thread calls this after starting the new thread" << std::endl;
        }

        for (auto& thread : threads) {
            thread.join();
        }

        return 0;
    }
    ```

    ```VB
    Imports System.Threading

    Public Class ServerClass
        ' The method that will be called when the thread is started.
        Public count = 0
        Public Sub InstanceMethod()
            Console.WriteLine(
                    "ServerClass.InstanceMethod is running on another thread.")

            Dim data = count + 1
            ' Pause for a moment to provide a delay to make
            ' threads more apparent.
            Thread.Sleep(3000)
            Console.WriteLine(
                    "The instance method called by the worker thread has ended.")
        End Sub

    End Class

    Public Class Simple

        Public Shared Sub Main()

            Dim ts As New ThreadStarter
            For index = 1 To 10
                ts.CreateThreads()
            Next

        End Sub

    End Class
    Public Class ThreadStarter
        Public Sub CreateThreads()
            Dim serverObject As New ServerClass()

            ' Create the thread object, passing in the
            ' serverObject.InstanceMethod method using a
            ' ThreadStart delegate.
            Dim InstanceCaller As New Thread(AddressOf serverObject.InstanceMethod)

            ' Start the thread.
            InstanceCaller.Start()

            Console.WriteLine("The Main() thread calls this after " _
                        + "starting the new InstanceCaller thread.")

        End Sub
    End Class
    ```
  
7.  Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet**.  
  
#### <a name="to-begin-the-tutorial"></a>Öğretici başlatmak için  
  
-   Kaynak Kodu Düzenleyicisi'nde, aşağıdaki kodu bakın: 
  
    ```csharp  
    Thread.Sleep(3000);  
    Console.WriteLine();  
    ```  
  
    ```C++  
    Thread::Sleep(3000);  
    Console.WriteLine();  
    ```  
    ```VB
    Thread.Sleep(3000)
    Console.WriteLine()
    ```
  
#### <a name="to-start-debugging"></a>Hata ayıklama başlatılamıyor  
  
1.  Sol cilt payı tıklatın `Thread.Sleep` veya `Thread::Sleep` yeni bir kesme noktası eklemek için deyimi.  
  
     Cilt payını içinde kaynak kod düzenleyicisinde sol tarafında, kırmızı bir daire görünür. Bu, bir kesme noktası bu konumda şimdi ayarlandığını gösterir. 
  
2.  Üzerinde **hata ayıklama** menüsünde tıklatın **hata ayıklamayı Başlat** (**F5**).  
  
     Derlemeler Visual Studio çözümü, uygulama hata ayıklayıcısı ekli çalışmaya başlar ve ardından uygulamayı kesme noktasında durur.  
  
    > [!NOTE]
    > Odağı konsol penceresine geçiş yaparsanız tıklatın [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] odağı dönmek için pencereyi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
4.  Kaynak Kod düzenleyicisinde kesme içeren satırı bulun:  
  
    ```csharp  
    Thread.Sleep(3000);  
    ```  
  
    ```C++  
    Thread::Sleep(3000);  
    ```

    ```VB
    Thread.Sleep(3000)
    ```    
  
#### <a name="ShowThreadsInSource"></a>İş parçacığı işaret bulmak için  

1.  Hata ayıklama araç çubuğunda **kaynak iş parçacıkları Göster** düğmesini ![kaynak iş parçacıkları Göster](../debugger/media/dbg-multithreaded-show-threads.png "ThreadMarker").

2. Tuşuna **F11** hata ayıklayıcı tek satırlık bir kod ilerletmek için bir kez.
  
3.  Cilt payını penceresinin sol tarafındaki bakın. Bu satırda göreceğiniz bir *iş parçacığı işaret* simgesi ![iş parçacığı işaret](../debugger/media/dbg-thread-marker.png "ThreadMarker") iki havlu iş parçacığı benzer. İş parçacığı işaret bir iş parçacığı bu konumda durdurulduğunu gösterir.

    Bir iş parçacığı işaret kısmen bir kesme noktası tarafından gizli bilgiler, dikkat edin. 
  
4.  İşaretçinin iş parçacığı işaret gelin. Bir DataTip görünür. DataTip her durdurulan iş parçacığı için adı ve iş parçacığı kimliği numarasını belirtir. Bu durumda, muhtemelen addır `<noname>`. 
  
5.  Kısayol menüsünde kullanılabilir seçenekleri görmek için iş parçacığı işaret sağ tıklayın.
    
## <a name="ParallelStacks"></a>İş parçacığı konumunu görüntüleyin

İçinde **Paralel Yığınlar** penceresinde değiştirebilirsiniz (için görev tabanlı programlama) ve iş parçacıkları görünümü arasında Görevler görünümü ve her iş parçacığı için çağrı yığını bilgileri görüntüleyebilirsiniz. Bu uygulamada, biz iş parçacıkları görünümü kullanabilirsiniz.

1. Açık **Paralel Yığınlar** seçerek penceresi **hata ayıklama > Windows > Paralel Yığınlar**. Buna benzer bir şey görmeniz gerekir (tam bilgileri her bir iş parçacığı, donanımınız ve programlama diliniz geçerli konumuna bağlı olarak farklı olacaktır).

    ![Paralel Yığınlar penceresini](../debugger/media/dbg-multithreaded-parallel-stacks.png "ParallelStacksWindow")

    Bu örnekte, soldan sağa Biz bu bilgileri alın:
    
    - Ana iş parçacığı (sol tarafta) üzerinde durduruldu `Thread.Start` (durma noktası iş parçacığı işaret simgesiyle belirtilir ![iş parçacığı işaret](../debugger/media/dbg-thread-marker.png "ThreadMarker")).
    - İki iş parçacığı girmiş `ServerClass.InstanceMethod`, geçerli iş parçacığının (sarı ok), biri olan başka bir iş parçacığı içinde durdurdu sırada `Thread.Sleep`.
    - Yeni bir iş parçacığı (sağdaki) de başlangıç (üzerinde durduruldu `ThreadHelper.ThreadStart`).

2.  Girişlere sağ **Paralel Yığınlar** kısayol menüsünde kullanılabilir seçenekleri görmek için penceresi.

    Bu sağ menülerden çeşitli eylemler alabilir, ancak bu öğretici için bu ayrıntıları birkaçını göstereceğiz **paralel Gözcü** penceresi (sonraki bölümlerde).

    > [!NOTE]
    > Her iş parçacığı bilgi görüntülemek için kullanmak listesini görmeniz daha ilgileniyorsanız **iş parçacığı** penceresi yerine. Bkz: [izlenecek yol: birden çok iş parçacıklı uygulamada hata ayıklama](../debugger/how-to-use-the-threads-window.md).

## <a name="set-a-watch-on-a-variable"></a>Bir izleme üzerinde bir değişken ayarlayın

1. Açık **paralel Gözcü** seçerek penceresi **hata ayıklama > Windows > paralel Gözcü > paralel Gözcü 1**.

2. Burada gördüğünüz hücreyi tıklatın `<Add Watch>` metin (veya 4 sütundaki boş üst bilgi hücresini) türü `data`, ve Enter tuşuna basın.

    Her iş parçacığı için veri değişken değerlerini penceresinde görünür.

3. Tıklatın yeniden gördüğünüz hücrede `<Add Watch>` metin (veya 5 sütundaki boş üst bilgi hücresini) türü `count`, ve Enter tuşuna basın.

    Her iş parçacığı sayısı değişken değerlerini penceresinde görünür. (Henüz bu kadar bilgi görmüyorsanız, yürütme iş parçacıklarında hata ayıklayıcı işlemi ilerletmek için birkaç kez daha F11 tuşuna basarak deneyin.)

    ![Paralel Gözcü penceresi](../debugger/media/dbg-multithreaded-parallel-watch.png "ParallelWatchWindow")

4. Kullanılabilir seçenekleri görmek için penceresinde satırları birine sağ tıklayın.

## <a name="flagging-and-unflagging-threads"></a>Bayrak ekleme ve Unflagging iş parçacıkları  
Özel dikkat vermek istediğiniz iş parçacıklarını bayrakla işaretleyebilirsiniz. İş parçacığı işaretlemesini bir iyi önemli iş parçacığı izlemek için ve önem verdiğiniz olmayan iş parçacıklarının yoksay yoludur.  
  
#### <a name="to-flag-threads"></a>İş parçacığı bayrak atamak için  

1. İçinde **paralel Gözcü** penceresinde SHIFT tuşunu basılı tutun ve birden çok satır seçin.

2. Sağ tıklatın ve seçin **bayrağı**.

    Şimdi, seçilen tüm iş parçacıklarının işaretlenir. Şimdi, yalnızca bayraklı iş parçacığı göstermek için filtreleyebilirsiniz.
  
3.  İçinde **paralel Gözcü** penceresinde Bul **Göster yalnızca işaretlenen iş parçacığı** düğmesini ![bayrağı iş parçacıkları Göster](../debugger/media/dbg-threads-show-flagged.png "ThreadMarker").  
  
4.  Tıklatın **Göster yalnızca işaretlenen iş parçacığı** düğmesi.  
  
    Bayrak eklenmiş iş parçacığı şimdi listede görüntülenir.

    > [!TIP]
    > Bazı iş parçacıklarını bayrakla zaman bir kod düzenleyicisinde kod satırı sağ tıklatın ve seçin **çalıştırmak işaretlenen iş parçacığı imleç** (tüm iş parçacıklarını bayrakla koda ulaşıp seçtiğinizden emin olun). Bu iş parçacığı tarafından yürütme sırasını denetlemek daha kolay kodunun seçili satırındaki duraklatılır [dondurma ve iş parçacıkları çözme](#bkmk_freeze).

5.  Tıklatın **Göster yalnızca işaretlenen iş parçacığı** geri geçiş yapmak için düğmesi **tüm iş parçacıkları Göster** modu.
    
#### <a name="to-unflag-threads"></a>İş parçacıklarını bayrakla için

İş parçacıklarını bayrakla için bir veya daha fazla bayraklı parçacıklarında tıklayabilir **paralel Gözcü** penceresi ve **Unflag**.

## <a name="bkmk_freeze"></a> Dondurma ve iş parçacığı yürütmeyi çözme 

> [!TIP]
> Dondurma ve çözme (askıya alma ve sürdürme) iş parçacıklarının iş gerçekleştirmek sırasını denetlemek için iş parçacığı sayısı. Bu, kilitlenmeleri gibi eşzamanlılık sorunları çözün ve koşullar durumunu yardımcı olabilir.
  
#### <a name="to-freeze-and-unfreeze-threads"></a>Freeze ve iş parçacıkları Çöz  
  
1.  İçinde **paralel Gözcü** penceresiyle seçili, tüm satırları sağ tıklatın ve seçin **Dondur**.

    İkinci sütunda duraklatma simgesinin her satır için artık görünür. Duraklatma simgesinin iş parçacığı donuk olduğunu gösterir.

2.  Satırlar yalnızca bir satıra tıklayarak seçimini kaldırın.

3.  Bir satır sağ tıklatıp **çözme**.

    Duraklatma simgesinin iş parçacığı artık dondurulmuş belirten bu satırda kaybolduktan.

4.  Kod düzenleyicisine geçip tıklatın **F11**. Yalnızca çözülmüş iş parçacığı çalıştırır.

    Uygulamanın, ayrıca bazı yeni iş parçacıkları örneği. Tüm yeni iş parçacıkları bayrak yok ve değil dondurulmuş dikkat edin.

## <a name="bkmk_follow_a_thread"></a> Koşullu kesme noktaları kullanarak tek bir iş parçacığı izleyin

Bazı durumlarda, tek bir iş parçacığı hata ayıklayıcısında yürütülmesini izlemek faydalı olabilir. Bunu yapabilirsiniz bir yolu ilgilendiğiniz değil iş parçacıklarını dondurmak tarafından ancak bazı senaryolarda (için yeniden oluşturma belirli bir hata, örneğin) diğer iş parçacıklarını dondurmak olmadan tek bir iş parçacığı izleyin isteyebilirsiniz. Diğer iş parçacıklarını dondurmak olmadan bir iş parçacığı izlemek için ilgilendiğiniz iş parçacığı dışında kodu parçalamak kaçınmalısınız. Bunu ayarlayarak yapabilirsiniz bir [koşullu kesme noktası](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression).

İş parçacığı adı veya iş parçacığı kimliği gibi farklı koşullar kesme noktaları ayarlayabilirsiniz Yardımcı olabilecek başka bir yöntem, her iş parçacığı için benzersiz olacaktır bildiğiniz verileri koşul ayarlamaktır. Bu, belirli herhangi bir iş parçacığı bazı belirli veri değerinden fazla ilgi olan bir ortak hata ayıklama, senaryodur.

#### <a name="to-follow-a-single-thread"></a>Tek bir iş parçacığı izlemek için

1. Daha önce oluşturduğunuz kesme noktası sağ tıklatın ve seçin **koşullar**.

2. İçinde **kesme noktası ayarları** penceresinde, türü `data == 5` koşullu ifade için.

    ![Koşullu kesme noktası](../debugger/media/dbg-multithreaded-conditional-breakpoint.png "ConditionalBreakpoint")

    > [!TIP]
    > Ardından belirli bir iş parçacığında daha ilgileniyorsanız, bir iş parçacığı adı veya iş parçacığı kimliği için koşulu kullanın. Bunu yapmak için **kesme noktası ayarları** penceresinde, seçin **filtre** yerine **koşullu ifade**ve filtre ipuçlarını izleyin. (Hata ayıklayıcı yeniden başlattığınızda iş parçacığı kimlikleri değiştiği), iş parçacıkları, uygulama kodunuzda ad vermek isteyebilirsiniz.

3. Kapat **kesme noktası ayarları** penceresi.

4. Yeniden Başlat'ı tıklatın ![yeniden uygulama](../debugger/media/dbg-tour-restart.png "RestartApp") düğmesi, hata ayıklama oturumu yeniden başlatın.

    Veri değişkeni 5 olduğu iş parçacığı üzerinde koda kesintiye uğrar. Sarı ok (geçerli hata ayıklayıcı bağlamını) için konum **paralel Gözcü** penceresi doğrulayın.

5. Artık, kod (F10) adım ve (F11) koda adım ve tek iş parçacığı yürütülmesi izleyin.

    Kesme noktası iş parçacığı için benzersiz bir durumdur ve hata ayıklayıcısı (bunları devre dışı bırakmanız gerekebilir) başka bir iş parçacığı üzerinde diğer bir kesme noktası isabet değil sürece, kod adım ve diğer iş parçacıkları geçmeden koda adım.

    > [!NOTE]
    > Hata ayıklayıcı geçildiğinde, tüm iş parçacıklarının çalıştırın. Ancak, diğer iş parçacıklarından birini bir kesme noktası isabet sürece hata ayıklayıcı başka bir iş parçacığı üzerinde koda bölün olmaz. 
  
## <a name="more-about-the-multithreaded-debugging-windows"></a>Birden çok iş parçacıklı hata ayıklama windows hakkında daha fazla bilgi 

#### <a name="to-switch-to-another-thread"></a>Başka bir iş parçacığı için geçiş yapmak için 

- Başka bir iş parçacığı için geçiş yapmak için bkz: [nasıl yapılır: başka bir iş parçacığı ederken hata ayıklama için geçiş](../debugger/how-to-switch-to-another-thread-while-debugging.md) 

#### <a name="to-learn-more-about-the-parallel-stack-and-parallel-watch-windows"></a>Paralel yığını ve paralel Gözcü pencerelerini hakkında daha fazla bilgi edinmek için  
  
- Bkz: [nasıl yapılır: paralel yığını penceresini kullanma](../debugger/using-the-parallel-stacks-window.md) 

- Bkz: [nasıl yapılır: paralel İzleme penceresini kullanma](../debugger/how-to-use-the-parallel-watch-window.md) 
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birden çok iş parçacıklı uygulamalarda hata ayıklama](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Nasıl yapılır: hata ayıklarken başka bir iş parçacığı için geçiş](../debugger/how-to-switch-to-another-thread-while-debugging.md)
