---
title: Visual Studio hata ayıklayıcısını kullanarak hata ayıklamayı öğrenin
ms.description: Learn how to start the Visual Studio debugger, step through code, and inspect data.
ms.custom: mvc
ms.date: 08/01/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
dev_langs:
- CSharp
- C++
helpviewer_keywords:
- debugger
ms.assetid: 62734c0d-a75a-4576-8f73-0e97c19280e1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f12e1e95daed3a4e9c6228808123f87174f2202a
ms.sourcegitcommit: 7bb0225e1fd45999ce09e0b49c2cfae515c27e11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2018
ms.locfileid: "45612694"
---
# <a name="tutorial-learn-to-debug-using-visual-studio"></a>Öğretici: Visual Studio kullanarak hata ayıklamayı öğrenin

Bu makalede, Visual Studio hata ayıklayıcı adım adım kılavuzda özelliklerini tanıtır. Hata ayıklayıcısı özellikleri daha üst düzey bir görünümünü istiyorsanız bkz [hata ayıklayıcısı özellik Turu](../debugger/debugger-feature-tour.md). Olduğunda, *uygulamanızda hata ayıklama*, hata ayıklayıcısı ekli, uygulamanızın çalıştığını genellikle anlamına gelir. Bunu yaptığınızda, hata ayıklayıcı, kodunuzun ne yaptığını görmek için birçok yol sağlar. çalışırken. Kodunuzda adım adım ve değişkenlerinde depolanan değerleri bakmak, gözcüler ayarlayabilirsiniz değerleri değiştiğinde görmek için değişkenlerini kodunuzun yürütme yolunu inceleyin, bir dal kod çalıştırma, vb. olup olmadığını. Bu, kodda hata ayıklamak için girişimde ilk kez ise, okumak isteyebilirsiniz [yeni başlayanlar için hata ayıklama](../debugger/debugging-absolute-beginners.md) bu makalede geçmeden önce.

|         |         |
|---------|---------|
|  ![video kamera simgesini film](../install/media/video-icon.png "bir video izleyin")  |    [Bir video izleyin](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugger-Feature-tour-of-Visual-studio-2017-sqwiwLD6D_1111787171) hata ayıklamayı benzer adımları gösterilmektedir. |

Tanıtım uygulamasını C# ve C++ olsa da, özellikleri, Visual Basic, JavaScript ve (belirtilenler dışında) Visual Studio tarafından desteklenen diğer diller için geçerlidir. Ekran görüntüleri C# ' de var. C# ve C++ bu makaledeki örnek kod arasında geçiş yapmak için bu sayfanın sağ üst köşedeki dil filtresi kullanın.

Bu öğreticide şunları yapacaksınız:

> [!div class="checklist"]
> * Hata ayıklayıcıyı başlatın ve kesme noktaları isabet.
> * Hata ayıklayıcı kodda adım adım için komutları öğrenin
> * Veri ipuçları ve hata ayıklayıcı pencereleri değişkenler inceleyin
> * Çağrı yığınını inceleyin

## <a name="prerequisites"></a>Önkoşullar

* Visual Studio 2017 yüklü olması gerekir ve **.NET masaüstü geliştirme** veya **C++ ile masaüstü geliştirme** iş yükü.

    Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

    İş yükünü yükleyin, ancak Visual Studio'a tıklayın, zaten gerektiğinde **açık Visual Studio yükleyicisi** sol bölmesinde bağlantıyı **yeni proje** iletişim kutusu (seçin **dosya**  >  **Yeni** > **proje**). Visual Studio Yükleyicisi'ni başlatır. Seçin. **NET masaüstü geliştirme** veya **C++ ile masaüstü geliştirme** iş yükü, ardından **Değiştir**.

## <a name="create-a-project"></a>Proje oluşturma

1. Visual Studio'da **Dosya > Yeni proje**.

2. Altında **Visual C#** veya **Visual C++**, seçin **Windows Masaüstü**seçip Ortadaki bölmeden **konsol uygulaması** ( **Windows konsol uygulaması** C++'ta).

    Görmüyorsanız **konsol uygulaması** proje şablonu, tıklayın **açık Visual Studio yükleyicisi** sol bölmesinde bağlantıyı **yeni proje** iletişim kutusu. Visual Studio Yükleyicisi'ni başlatır. Seçin *.NET masaüstü geliştirme** veya **C++ ile masaüstü geliştirme** iş yükü, ardından **Değiştir**.

3. Gibi bir ad yazın **get-başlatıldı-hata ayıklama** tıklatıp **Tamam**.

    Visual Studio projesi oluşturur.

4. İçinde *Program.cs* (C#) veya *get çalışmaya debugging.cpp* (C++), aşağıdaki kodu değiştirin

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;

    namespace get_started_debugging
    {
        class Program
        {
            static void Main(string[] args)
            {
            }
        }
    }
    ```

    ```c++
    int main()
    {
        return 0;
    }
    ```

    Bu kod ile:

    ```csharp
    using System;
    using System.Collections.Generic;

    public class Shape
    {
        // A few example members
        public int X { get; private set; }
        public int Y { get; private set; }
        public int Height { get; set; }
        public int Width { get; set; }
   
        // Virtual method
        public virtual void Draw()
        {
            Console.WriteLine("Performing base class drawing tasks");
        }
    }

    class Circle : Shape
    {
        public override void Draw()
        {
            // Code to draw a circle...
            Console.WriteLine("Drawing a circle");
            base.Draw();
        }
    }

    class Rectangle : Shape
    {
        public override void Draw()
        {
            // Code to draw a rectangle...
            Console.WriteLine("Drawing a rectangle");
            base.Draw();
        }
    }

    class Triangle : Shape
    {
        public override void Draw()
        {
            // Code to draw a triangle...
            Console.WriteLine("Drawing a trangle");
            base.Draw();
        }
    }

    class Program
    {
        static void Main(string[] args)
        {

            var shapes = new List<Shape>
            {
                new Rectangle(),
                new Triangle(),
                new Circle()
            };

            foreach (var shape in shapes)
            {
                shape.Draw();
            }

            // Keep the console open in debug mode.
            Console.WriteLine("Press any key to exit.");
            Console.ReadKey();
        }

    }

    /* Output:
        Drawing a rectangle
        Performing base class drawing tasks
        Drawing a triangle
        Performing base class drawing tasks
        Drawing a circle
        Performing base class drawing tasks
    */
    ```

    ```c++
    #include "pch.h"

    #include <string>
    #include <vector>
    #include <iostream>

    class Shape
    {
        int privateX = 0;
        int privateY = 0;
        int privateHeight = 0;
        int privateWidth = 0;

        int getX() const { return privateX; }
        void setX(int value) { privateX = value; }

        int getY() const { return privateY; }
        void setY(int value) { privateY = value; }

        int getHeight() const { return privateHeight; }
        void setHeight(int value) { privateHeight = value; }

        int getWidth() const { return privateWidth; }
        void setWidth(int value) { privateWidth = value; }

        public:
        // Virtual method
        virtual void Draw()
        {
            std::wcout << L"Performing base class drawing tasks" << std::endl;
        }
    };

    class Circle : public Shape
    {
        public:
        void Draw() override
        {
        // Code to draw a circle...
        std::wcout << L"Drawing a circle" << std::endl;
        Shape::Draw();
        }
    };

    class Rectangle : public Shape
    {
        public:
        void Draw() override
        {
        // Code to draw a rectangle...
        std::wcout << L"Drawing a rectangle" << std::endl;
        Shape::Draw();
        }
    };

    class Triangle : public Shape
    {
        public:
        void Draw() override
        {
        // Code to draw a triangle...
        std::wcout << L"Drawing a trangle" << std::endl;
        Shape::Draw();
        }
    };

    int main(std::vector<std::wstring> &args)
    {
        auto shapes = std::vector<Shape*>
        {
            new Rectangle(),
            new Triangle(),
            new Circle()
        };

        for (auto shape : shapes)
        {
            shape->Draw();
        }
    }

    /* Output:
    Drawing a rectangle
    Performing base class drawing tasks
    Drawing a triangle
    Performing base class drawing tasks
    Drawing a circle
    Performing base class drawing tasks
    */
    ```

## <a name="start-the-debugger"></a>Hata ayıklayıcıyı başlatın!

1. Tuşuna **F5** (**hata ayıklama > hata ayıklamayı Başlat**) veya **hata ayıklamayı Başlat** düğmesi ![hata ayıklamayı Başlat](../debugger/media/dbg-tour-start-debugging.png "hata ayıklamayı Başlat ") hata ayıklama araç çubuğu.

     **F5** başladığında hata ayıklayıcının uygulamayla uygulamaya bağlı işlem ancak biz kodunu incelemek için özel bir şey yapmadınız hemen. Bu nedenle yalnızca uygulamayı yükler ve konsol çıktısı görürsünüz.

    ```
    Drawing a rectangle
    Performing base class drawing tasks
    Drawing a triangle
    Performing base class drawing tasks
    Drawing a circle
    Performing base class drawing tasks
    ```

     Bu öğreticide, biz hata ayıklayıcıyı kullanarak bu uygulamaya daha yakından göz atın ve hata ayıklayıcı göz özelliklerini elde etmek.

2. Kırmızı Durdur tuşuna basarak hata ayıklayıcıyı ![hata ayıklamayı Durdur](../debugger/media/dbg-tour-stop-debugging.png "hata ayıklamayı Durdur") düğmesi.

## <a name="set-a-breakpoint-and-start-the-debugger"></a>Bir kesme noktası ayarlayın ve hata ayıklayıcıyı başlatın

1. İçinde `foreach` , döngü `Main` işlevi (`for` C++ döngüde `main` işlevi), aşağıdaki kod satırının sol kenar boşluğunu tıklayarak kesme noktası ayarlayın:

    `shape.Draw()` (veya `shape->Draw()` c++)

    Kesme noktasının ayarlandığı kırmızı bir daire görünür.

    Kesme noktaları güvenilir hata ayıklama en temel hem de temel özelliğidir. Bir kesme noktası değişkenlerin değerleri veya bellek davranışını göz olabilmesi için Visual Studio çalışan kodunuzu nereye askıya almanız ya da bir dal kod getting run olup olmadığını gösterir. 

6. Tuşuna **F5** veya **hata ayıklamayı Başlat** düğme, uygulama başlatılır ve hata ayıklayıcı, Kesme noktasının ayarlandığı kod satırına çalıştırır.

    ![Ayarlayın ve bir kesme noktası isabet](../debugger/media/get-started-set-breakpoint.gif)

    Sarı ok, aynı zamanda aynı noktayı (Bu bildirimi henüz çalıştırılmadı) uygulama yürütmeyi askıya alır, hata ayıklayıcı durduruldu, deyimi temsil eder.

     Uygulama henüz çalışmıyorsa **F5** hata ayıklayıcıyı başlatır ve ilk kesme noktasında durur. Aksi takdirde, **F5** uygulamayı sonraki kesme noktasına kadar çalışmaya devam eder.

    Kod satırının veya ayrıntılı olarak incelemek istediğiniz kod bölümünün bildiğiniz durumlarda kesme noktaları yararlı bir özelliktir.

## <a name="navigate-code-in-the-debugger-using-step-commands"></a>Kod adım komutları kullanarak hata ayıklayıcısında gidin

Almak için en iyi yolu olduğundan bu çoğunlukla, klavye kısayollarını Burada, kullandığımız hata ayıklayıcı (komutları parantez içinde gösterilen eşdeğer komutları menüsü gibi) uygulamanız çalıştırma sırasında hızlı.

1. İçinde duraklatıldığı sırada `shape.Draw` yöntemi çağırın `Main` yöntemi (`shape->Draw` C++'ta), basın **F11** (veya tercih **hata ayıklama > içine adımla**) için koda ilerlemek için `Rectangle` sınıf.

     ![İçine adımla kodu F11 kullanın](../debugger/media/get-started-f11.png "F11 adımla")

     F11 olan **içine adımla** komut ve aynı anda uygulama yürütme bir deyim ilerler. F11 çoğu ayrıntılı yürütme akışı incelemek için iyi bir yoludur. (Daha hızlı kod boyunca taşımak için başka seçenekleriniz de gösteriyoruz.) Varsayılan olarak, kullanıcı dışı kod üzerinde hata ayıklayıcı atlar (daha ayrıntılı bilgi isterseniz bkz [yalnızca kendi kodum](../debugger/just-my-code.md)).

2. Basın **F10** (veya seçin **hata ayıklama > Step Over**) hata ayıklayıcı birkaç kez durur kadar `base.Draw` yöntem çağrısının (`Shape::Draw` C++'ta) ve tuşuna **F10** bir kez daha.

     ![Step Over kodu F10 kullanın](../debugger/media/get-started-step-over.png "F10 adımla")

     Hata ayıklayıcı içine girmez şu bildirim `Draw` temel sınıf yöntemini (`Shape`). **F10** işlevleri veya yöntemleri (kod hala çalışır), uygulama kodunuzda içine Adımlama olmadan, hata ayıklayıcı ilerler. F10 tuşlarına basarak `base.Draw` (veya `Shape::Draw`) yöntem çağrısının (yerine **F11**), biz uygulama kodunu üzerinden atlandı `base.Draw` (biz İlgilenmiyor, şu anda hangi olabilir).

## <a name="navigate-code-using-run-to-click"></a>Tıkla Çalıştır'ı kullanarak kod gidin

5. Kod Düzenleyicisi'nde, ekranı aşağı kaydırın ve üzerine `Console.WriteLine` yöntemi (`std::cout` C++'ta) içinde `Triangle` sınıfı yeşil kadar **tıklanan satıra kadar Çalıştır** düğmesi ![tıklanan satıra kadar Çalıştır](../debugger/media/dbg-tour-run-to-click.png " RunToClick") soldaki bölmede görünür.

     ![Tıkla Çalıştır kullanın özellik](../debugger/media/get-started-run-to-click.png "tıklanan satıra kadar Çalıştır")

    >  [!NOTE]
    > **Tıklanan satıra kadar Çalıştır** düğmesidir yeni [!include[vs_dev15](../misc/includes/vs_dev15_md.md)]. Yeşil ok düğmesini görmüyorsanız kullanın **F11** Bu örnekte bunun yerine hata ayıklayıcı doğru yere ilerlemek için.

6. Tıklayın **tıklanan satıra kadar Çalıştır** düğmesi ![tıklanan satıra kadar Çalıştır](../debugger/media/dbg-tour-run-to-click.png "RunToClick").

    Bu düğmeyi kullanarak geçici bir kesme noktası ayarlayarak benzer. **Tıklanan satıra kadar Çalıştır** (herhangi bir açık dosyayı tıklayabilirsiniz) uygulama kodu görünür bir bölge içinde hızla dolaşma için kullanışlıdır.

    Hata ayıklayıcı ilerler `Console.WriteLine` yöntem uygulaması için `Triangle` sınıfı (`std::cout` C++'ta).

    Duraklatıldığı sırada bir yazım yanlışı dikkat edin! "Bir trangle çizim" çıkış yanlış yazılmıştır. Biz burada Hata Ayıklayıcısı'nda uygulama çalıştırılırken düzeltebilirsiniz.

## <a name="edit-code-and-continue-debugging"></a>Kodu düzenleme ve hata ayıklamaya devam etme

1. İçine tıklayın "bir trangle çizim" ve "trangle" değiştirme "üçgene", bir düzeltme yazın.

1. Tuşuna **F11** bir kez ve bkz hata ayıklayıcıyı yeniden ilerler.

    > [!NOTE]
    > Ne tür kod hata ayıklayıcıda düzenleme bağlı olarak, bir uyarı iletisi görebilirsiniz. Bazı senaryolarda, kod devam edebilmek derlemeniz gerekir.

## <a name="step-out"></a>Dışına adımla

İşiniz olduğunu düşünelim İnceleme `Draw` yönteminde `Triangle` sınıfı ve istediğiniz get işlevi dışında ancak hata ayıklayıcıda haberdar olun. Bunu kullanarak yapabilirsiniz **Step Out** komutu.

1. Tuşuna **Shift** + **F11** (veya **hata ayıklama > dışarı adımla**).

     Bu komut, uygulama yürütmeyi devam ettirir (ve hata ayıklayıcı ilerler) geçerli işlev dönene kadar.

     Geri olmalıdır `foreach` içinde döngü `Main` yöntemi (`for` C++ döngüde).

## <a name="restart-your-app-quickly"></a>Uygulamanızı hızlı bir şekilde yeniden başlatın

Tıklayın **yeniden** ![yeniden uygulama](../debugger/media/dbg-tour-restart.png "RestartApp") hata ayıklama araç çubuğu düğmesini (**Ctrl** + **kaydırma**   +  **F5**).

Bastığınızda **yeniden**, uygulama durdurup hata ayıklayıcı yerine zaman kaydeder. İlk kesme noktasına isabet kodu yürüterek, hata ayıklayıcı duraklatır.

Hata ayıklayıcıyı yeniden üzerinde sizin ayarladığınız kesme noktasında durur `shape.Draw()` yöntemi (`shape->Draw()` C++'ta).

## <a name="inspect-variables-with-data-tips"></a>Veri ipuçları değişkenlerle inceleyin

Değişkenleri incelemek özellik hata ayıklayıcının en kullanışlı özellikler biridir ve bunu yapmanın farklı yolu vardır. Genellikle, hata ayıklama bir sorun açmayı denediğinde, belirli bir zamanda sahip olmalarını beklediğiniz değerleri değişkenleri olup depoladığını kullanıma bulmak çalışıyorsunuz.

1. Üzerinde duraklatıldığı sırada `shape.Draw()` yöntemi (`shape->Draw()` C++'ta), üzerine `shapes` nesne ve bkz varsayılan özellik değerine `Count` özelliği.

1. Genişletin `shapes` tüm özelliklerini, dizinin ilk dizini gibi görmek için nesne `[0]`, değeri olan `Rectangle` (C#) veya bir bellek adresi (C++).

     ![Bir veri ipucunda görüntülemek](../debugger/media/get-started-data-tip.gif "bir veri ipucunda görüntüleyin")

    Nesneleri gibi özelliklerini görüntülemek için daha da genişletebilirsiniz `Height` dikdörtgeninin özelliği.

    Genellikle, hata ayıklama sırasında istediğiniz nesnelerin özellik değerlerini denetlemek için hızlı bir yol ve veri ipuçları yapmak için iyi bir yoludur.

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>Otolar ve yerel öğeler pencerelerinde değişkenlerle inceleyin

1. Bakmak **Otolar** altındaki kod düzenleyicisi penceresi.

     ![Otomatik değişkenler penceresi değişkenleri İnceleme](../debugger/media/get-started-autos-window.png "otomatik değişkenler penceresi")

    İçinde **Otolar** penceresi değişkenleri ve bunların geçerli değerini görürsünüz. **Otolar** penceresi gösterir geçerli satırı veya önceki satır kullanılan tüm değişkenleri (C++'daki, pencere gösterir değişkenleri kod önceki üç satır. Dile özgü davranışı için belgeleri denetleyin).

    > [!NOTE]
    > JavaScript'te **Yereller** penceresi ancak desteklenen **Otolar** penceresi.

2. Ardından, bakmak **Yereller** penceresinde ileri bir sekmeye **Otolar** penceresi.

    **Yereller** penceresi gösterir, geçerli olan değişkenlere [kapsam](https://www.wikipedia.org/wiki/Scope_(computer_science)).

## <a name="set-a-watch"></a>Bir izleme ayarlayın

1. Ana Kod Düzenleyicisi'ni penceresinde sağ `shapes` seçin ve nesne **Gözcü Ekle**.

    **Watch** Kod Düzenleyicisi sayfanın en penceresi açılır. Kullanabileceğiniz bir **Watch** penceresinin bir değişken (veya bir ifade) takip etmek istediğinizi belirtin.

    Artık, bir izleme ayarlayın sahipsiniz `shapes` nesne ve hata ayıklayıcı geçerken değiştirme değeri görebilirsiniz. Diğer değişken pencerelerini aksine **Watch** penceresi her zaman, izlerken değişkenleri gösterir (bunlar zaman kapsam dışına renkte).

## <a name="examine-the-call-stack"></a>Çağrı yığınını inceleyin

1. İçinde duraklatıldığı sırada `foreach` döngü (`for` C++ döngüde), tıklayın **çağrı yığını** varsayılan alt sağ bölmede açık olarak penceresinde.

1. Tıklayın **F11** birkaç kez duraklatmak, hata ayıklayıcı görene kadar `Circle.Draw` Kod düzenleyicisinde yöntemi. Bakmak **çağrı yığını** penceresi.

    ![Çağrı yığınını incelemek](../debugger/media/get-started-call-stack.png "ExamineCallStack")

    **Çağrı yığını** penceresi, yöntemleri ve işlevleri çağrılır sırasını gösterir. Geçerli işlev en üst satırına gösterir ( `Circle.Draw` veya `Circle::Draw` bu uygulamada yöntemi). İkinci satır gösteren `Circle.Draw` çağırıldığı `Main` yöntemi (`main` C++'ta) ve benzeri.

    >  [!NOTE]
    > **Çağrı yığını** penceresi benzer hata ayıklama perspektifi için Eclipse gibi bazı IDE içinde.

    Çağrı yığınını inceleyebilir ve bir uygulamanın yürütme akışını anlamanıza için iyi bir yoludur.

    Bir satır kod, kaynak koda bakmaktır gitmek için çift tıklayın ve hata ayıklayıcı tarafından denetlenmekte olan geçerli kapsamını da değişiklikler. Bu eylem, hata ayıklayıcı ilerleyin değil.

    Sağ tıklama menülerden kullanabilirsiniz **çağrı yığını** başka şeyler için pencere. Örneğin, belirtilen işlevlere kesme noktaları ekleme, hata ayıklayıcıyı kullanarak ilerleyin **imlece kadar Çalıştır**ve kaynak kodunu inceleyin. Daha fazla bilgi için [nasıl yapılır: çağrı yığını inceleyin](../debugger/how-to-use-the-call-stack-window.md).

## <a name="change-the-execution-flow"></a>Yürütme akışı değiştirme

1. İçinde hata ayıklayıcısı ile duraklatıldı `Circle.Draw` yöntemi çağrısı, tuşuna **F11** üzerinde hata ayıklayıcı birkaç kez duraklatır kadar `base.Draw` yöntem çağrısının (`Shape::Draw` C++'ta).

1. Sol taraftaki sarı ok (yürütme işaretçisi) alıp sarı ok için bir satır yukarı taşı fare kullanma `Console.WriteLine` (`std::cout` C++'ta) yöntem çağrısı.

1. Tuşuna **F11** bir kez daha.

    Hata ayıklayıcıyı yeniden çalıştırır `Console.WriteLine` yöntemi (`std::cout` C++'ta).

    Yürütme akışı değiştirerek farklı kod yürütme yolları test veya hata ayıklayıcı yeniden başlatmadan kodu yeniden gibi işlemler yapabilirsiniz.

    > [!WARNING]
    > Genelde bu özellikle dikkat etmek gerekir ve araç ipucunda bir uyarı görürsünüz. Çok diğer uyarılar görebilirsiniz. İşaretçiyi taşıma uygulamanızı daha önceki bir uygulama durumuna geri alınamaz.

1. Tuşuna **F5** uygulamayı çalıştırmaya devam etmek için.

    Bu öğreticiyi tamamlamak Tebrikler!

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, kodu adımlayın hata ayıklayıcıyı başlatın ve değişkenleri denetleyin öğrendiniz. Daha fazla bilgi için bağlantılar hata ayıklayıcı özelliklerine genel bir bakış almak isteyebilirsiniz.

> [!div class="nextstepaction"]
> [Hata ayıklayıcısı ipuçları ve püf noktaları](../debugger/debugger-tips-and-tricks.md)
