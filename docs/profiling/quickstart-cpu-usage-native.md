---
title: CPU kullanımı verilerini (C++) çözümleme
description: Uygulama performansını CPU kullanımı Tanılama Aracı'nı kullanarak c++
ms.custom: ''
ms.date: 12/05/2017
ms.technology: vs-ide-debug
ms.topic: quickstart
f1_keywords:
- ''
helpviewer_keywords:
- Profiling Tools, quick start
- Diagnostics Tools, CPU Usage
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 674c7f30a325c8d615c76a784b3c4e80e306ead6
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256252"
---
# <a name="quickstart-analyze-cpu-usage-data-in-visual-studio-c"></a>Hızlı Başlangıç: Analiz CPU kullanım verilerini de Visual Studio (C++)

Visual Studio, uygulamanızda performans sorunları analiz etmenize yardımcı olmak üzere pek çok güçlü özellikler sağlar. Bu konuda, temel özelliklerden bazıları öğrenmek için hızlı bir yoludur. Burada, yüksek CPU kullanımından kaynaklanan performans sorunlarını tanımlamak için aracı ele. Tanılama araçları, yerel/C++ geliştirme ve ASP.NET, dahil olmak üzere Visual Studio .NET geliştirme için desteklenir.

Tanılama hub'ı çok çalıştırın ve tanılama oturumunuz yönetmek için diğer seçenekleri sunar. Varsa **CPU kullanımı** burada açıklanan aracı verme, ihtiyaç duyduğunuz, veri [diğer profil oluşturma araçları](../profiling/profiling-feature-tour.md) değişik size yardımcı olabilecek bilgiler sağlar. Çoğu durumda, uygulamanızın performans düşüklüğü, CPU, bellek, işleme kullanıcı Arabirimi veya ağ istek süresi gibi dışında bir şey tarafından kaynaklanıyor olabilir. Tanılama hub'ı çok kaydetmek ve bu tür verilerin çözümlemek için diğer seçenekleri sunar.

## <a name="create-a-project"></a>Proje oluşturma

1. Visual Studio'da, **dosya**>**yeni proje**.

2. Altında **Visual C++**, seçin **Windows Masaüstü**ve ardından Orta bölmede **Windows konsol uygulaması**.

3. Gibi bir ad yazın **Diagnostics_Get_Started_Native** tıklatıp **Tamam**.

    Visual Studio projesi oluşturur.

4. Aşağıdaki kod MyDbgApp.cpp değiştirin

    ```c++
    int main()
    {
        return 0;
    }
    ```

    Bu kod (kaldırmayın `#include "stdafx.h"`):

    ```c++
    #include <iostream>
    #include <limits>
    #include <mutex>
    #include <random>
    #include <functional>
    
    //.cpp file code:
    
    static constexpr int MIN_ITERATIONS = std::numeric_limits<int>::max() / 1000;
    static constexpr int MAX_ITERATIONS = MIN_ITERATIONS + 10000;
    
    long long m_totalIterations = 0;
    std::mutex m_totalItersLock;
    
    int getNumber()
    {
    
        std::uniform_int_distribution<int> num_distribution(MIN_ITERATIONS, MAX_ITERATIONS);
        std::mt19937 random_number_engine; // pseudorandom number generator
        auto get_num = std::bind(num_distribution, random_number_engine);
        int random_num = get_num();
    
        auto result = 0;
        {
            std::lock_guard<std::mutex> lock(m_totalItersLock);
            m_totalIterations += random_num;
        }
        // we're just spinning here  
        // to increase CPU usage 
        for (int i = 0; i < random_num; i++)
        {
            result = get_num();
        }
        return result;
    }
    
    void doWork()
    {
        std::wcout << L"The doWork function is running on another thread." << std::endl;
    
        auto x = getNumber();    
    }
    
    int main()
    {
        std::vector<std::thread> threads;
    
        for (int i = 0; i < 10; ++i) {
    
            threads.push_back(std::thread(doWork));
            std::cout << "The Main() thread calls this after starting the new thread" << std::endl;
        }
    
        for (auto& thread : threads) {
            thread.join();
        }
    
        return 0;
    }
    ```
  
## <a name="step-1-collect-profiling-data"></a>1. adım: profil oluşturma verilerini topla 
  
1.  İlk olarak, bu kod satırı üzerinde uygulamanızda bir kesme noktası belirleyerek `main` işlevi:

    `for (int i = 0; i < 10; ++i) {`

    Cilt payını sola kod satırının tıklayarak bir kesme noktası ayarlayın.

2.  Ardından, sonunda kapanış parantezi ikinci bir kesme noktası ayarlayın `main` işlevi:

     ![Profil oluşturma için kesme noktaları ayarlayın](../profiling/media/quickstart-cpu-usage-breakpoints-cplusplus.png "profil oluşturma için kesme noktaları ayarlayın")

    > [!TIP]
    > İki kesme noktası belirleyerek, çözümlemek istediğiniz kod parçalarını veri toplama sınırlayabilirsiniz.
  
3.  **Tanılama araçları** penceredir zaten görünür, onu devre dışı bırakmış sürece. Pencereyi yeniden getirmek için tıklatın **hata ayıklama**>**Windows**>**tanılama araçları Göster**.

4.  Tıklatın **hata ayıklama**>**hata ayıklamayı Başlat** (veya **Başlat** araç çubuğunda veya **F5**).

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

## <a name="step-2-analyze-cpu-usage-data"></a>2. adım: CPU kullanım verilerini çözümleme

CPU kullanımı altında işlevlerin listesi inceleyerek, en fazla çalışmayı yapan işlevleri tanımlama ve her biri daha ayrıntılı bir bakış alma verilerinizi incelemeye başlamak öneririz.

1. İşlev listesinde en fazla çalışmayı yapan işlevleri inceleyin.

     ![Tanılama araçları CPU kullanımı sekmesi](../profiling/media/quickstart-cpu-usage-cpu-cplusplus.png "DiagToolsCPUUsageTab")

    > [!TIP]
    > İşlevler en fazla çalışmayı yapan olanlar başlangıç sırayla listelenir (çağrı sırayla olmadıklarını). Bu en uzun çalışan işlevleri hızla tanımlamanıza yardımcı olur.

2. İşlev listesinde çift `getNumber` işlevi.

    İşlev çift tıkladığınızda **arayan/Aranan** sol bölmede görünümünü açar. 

    ![Tanılama araçları çağıran Aranan görünümü](../profiling/media/quickstart-cpu-usage-caller-callee-cplusplus.png "DiagToolsCallerCallee")

    Başlık hem de bu görünümde seçili işlevi görüntülenir **geçerli işlevi** kutusunu (`getNumber`, bu örnekte). Solda'nin altında gösterilen geçerli işlevini çağırdı işlevi **işlevi çağırma**, ve geçerli işlev tarafından çağrılan tüm işlevler gösterilir **çağrılan işlevler** sağdaki kutusu. (Geçerli işlevi değiştirmek için ya da kutusunu seçebilirsiniz.)

    Bu görünüm toplam süre (ms) ve genel uygulamayı işlevi tamamlamak için geçen zaman yüzdesini gösterir.

    **İşlev gövdesi** ayrıca toplam zamanı (ve zamanı yüzdesi) işlev gövdesine harcanan zaman hariç içinde arama harcanan ve işlevleri adlı gösterilmektedir. (Bu çizimde, 119 dışı 43602 ms işlev gövdesine harcanan ve bu işlev tarafından çağrılan başka bir kod içinde kalan süreyi harcandığını). Gerçek değerler ortamınıza bağlı olarak çok farklı olacaktır.

    > [!TIP]
    > Yüksek değerleri **işlev gövdesi** işlevi içinde performans sorunu gösteriyor olabilir.

## <a name="next-steps"></a>Sonraki adımlar

- [Bellek kullanımını çözümleme](../profiling/memory-usage.md)performans sorunlarını tanımlamak için.
- [CPU kullanımı analiz](../profiling/cpu-usage.md) CPU kullanımı aracı hakkında daha ayrıntılı bilgi için.
- -Daha fazla bilgi için çalışan bir uygulamanın hedefleyerek veya bir hata ayıklayıcısı ekli olmadan CPU kullanımı analiz [hata ayıklama olmadan profil oluşturma verilerini toplama](../profiling/running-profiling-tools-with-or-without-the-debugger.md#collect-profiling-data-without-debugging) içinde [Profil Araçları ile veya olmadan hata ayıklayıcı çalıştırmak](../profiling/running-profiling-tools-with-or-without-the-debugger.md).

## <a name="see-also"></a>Ayrıca bkz.  

 [Visual Studio'da profil oluşturma](../profiling/index.md)  
 [Profil oluşturma özelliği turu](../profiling/profiling-feature-tour.md)
