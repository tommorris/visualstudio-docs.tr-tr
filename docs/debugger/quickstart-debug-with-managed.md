---
title: Yönetilen kodda hata ayıklama | Microsoft Docs
description: C# veya Visual Basic, Visual Studio hata ayıklayıcısı kullanarak hata ayıklama
ms.custom: mvc
ms.date: 03/18/2018
ms.technology: vs-ide-debug
ms.topic: quickstart
helpviewer_keywords:
- debugger
ms.assetid: f4cea2e1-08dc-47ac-aba2-3b8c338e607f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 4dc9c9acfed229e4215c32e2e924ba1601ce88b6
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/24/2018
---
# <a name="quickstart-debug-with-managed-code-using-the-visual-studio-debugger"></a>Hızlı Başlangıç: Visual Studio hata ayıklayıcısı kullanarak yönetilen kod ile hata ayıklama

Visual Studio hata ayıklayıcısı uygulamalarınızı hata ayıklama yardımcı olmak üzere pek çok güçlü özellikler sağlar. Bu konuda, temel özelliklerden bazıları öğrenmek için hızlı bir yoludur.

## <a name="create-a-new-project"></a>Yeni bir proje oluşturma 

1. Visual Studio'da, **Dosya > Yeni proje**.

2. Altında **Visual C#** veya **Visual Basic**, seçin **.NET Core**ve ardından Orta bölmede **konsol uygulaması (.NET Core)**.

     Görmüyorsanız, **konsol uygulaması (.NET Core)** proje şablonu, tıklatın **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu. Visual Studio yükleyicisi başlatır. Seçin **.NET masaüstü geliştirme** ve **.NET Core** iş yükü, ardından **Değiştir**.

3. Gibi bir ad yazın **MyDbgApp** tıklatıp **Tamam**.

    Visual Studio projesi oluşturur.

4. Program.cs veya Module1.vb, aşağıdaki kod değiştirin

    ```csharp
    class Program
    {
        static void Main(string[] args)
        {
        }
    }
    ```

    ```vb
    Module Module1
        Sub Main()
        End Sub
    End Module
    ```

    Bu kodu:

    ```csharp
    class Program
    {
        private static void doWork()
        {
            LinkedList<int> c1 = new LinkedList<int>();

            c1.AddLast(10);
            c1.AddLast(20);

            LinkedList<int> c2 = new LinkedList<int>(c1);
            int i = c2.First.Value;
            int j = c2.First.Value;
            Console.Write("The first element is ");
            Console.Write(i);
            Console.Write("\n");
            Console.Write("The second element is ");
            Console.Write(j);
            Console.Write("\n");

        }

        static int Main()
        {
            // using namespace std;
            doWork();
            return 0;

        }
    }
    ```

    ```vb
    Imports System.Collections.Generic

    Namespace MyDbgApp
        Class Program
            Private Shared Sub doWork()
                Dim c1 As New LinkedList(Of Integer)()

                c1.AddLast(10)
                c1.AddLast(20)

                Dim c2 As New LinkedList(Of Integer)(c1)
                Dim i As Integer = c2.First.Value
                Dim j As Integer = c2.First.Value
                Console.Write("The first element is ")
                Console.Write(i)
                Console.Write(vbLf)
                Console.Write("The second element is ")
                Console.Write(j)
                Console.Write(vbLf)

            End Sub

            Public Shared Function Main() As Integer
                ' using namespace std;
                doWork()
                Return 0

            End Function
        End Class
    End Namespace
    ```

    > [!NOTE]
    > Visual Basic'te Başlangıç nesnesi ayarlandığından emin olun `Sub Main` (**Özellikler > Uygulama > Başlangıç nesnesi**).

## <a name="set-a-breakpoint"></a>Bir kesme noktası ayarlama

A *kesme noktası* Visual Studio, çalışan burada askıya gösteren bir işaretçi kod değişkenlerin değerleri veya bellek veya karşılamadığını kod dalı çalıştırıldığında davranışını göz atın biçimde değil. Hata ayıklama, en temel özelliğidir.

1. Cilt payını solundaki kesme noktası ayarlamak için tıklayın `doWork` işlev çağrısı (veya kod ve tuşuna satırını seçin **F9**).

    ![Bir kesme noktası belirleyerek](../debugger/media/dbg-qs-set-breakpoint-csharp.png "bir kesme noktası ayarlama")

2. Şimdi basın **F5** (veya tercih **hata ayıklama > hata ayıklamayı Başlat**).

    ![Bir kesme noktası isabet](../debugger/media/dbg-qs-hit-breakpoint-csharp.png "bir kesme noktası isabet")

    Kesme noktası ayarladığınız hata ayıklayıcı duraklatır. Hata ayıklayıcı ve uygulama yürütme burada duraklatıldı deyimi sarı okla belirtilir. İçeren satırı `doWork` işlev çağrısı kurmadı henüz yürütülür.

    > [!TIP]
    > Döngü veya özyineleme bir kesme noktası varsa veya sık, adım adım birçok kesme noktaları varsa bir [koşullu kesme noktası](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression) yalnızca belirli koşullar karşılandığında, kodunuzu askıya emin olmak için. Koşullu kesme noktası zamandan tasarruf edebilirsiniz ve bu da, yeniden sabit ayıklanır kolaylaştırabilir.

## <a name="navigate-code"></a>Kod gidin

Devam etmek için hata ayıklayıcı istemek üzere farklı komutlar vardır. Visual Studio 2017 içinde yeni bir yararlı kod Gezinti komutu gösteriyoruz.

Duraklatılmış kesme noktasında olsa da, deyimi vurgulu `c1.AddLast(20)` yeşil kadar **Çalıştır'ı tıklatın** düğmesini ![çalıştırmak için tıklatın](../debugger/media/dbg-tour-run-to-click.png "RunToClick") görünür ve tuşuna basın **Çalıştır'ı tıklatın** düğmesi.

![Çalıştır'ı tıklatın](../debugger/media/dbg-qs-run-to-click-csharp.png "Çalıştır'ı tıklatın")

Uygulama yürütülmeye çağırma `doWork`ve düğmesini tıklattığınız kod satırında duraklatır.

Ortak klavye komutları için kullanılan kod aracılığıyla adım dahil **F10** ve **F11**. Daha fazla ayrıntılı yönergeler için bkz: [Başlangıç Kılavuzu](../debugger/getting-started-with-the-debugger.md).

## <a name="inspect-variables-in-a-datatip"></a>Bir datatip değişkenlerde inceleyin.

1. Geçerli satırda (sarı yürütme işaretçi işaretli) kodunun, üzerine gelerek `c1` bir datatip göstermek için fare nesnesiyle.

    ![Bir datatip görüntülemek](../debugger/media/dbg-qs-data-tip-csharp.png "bir datatip görüntüleyin")

    Geçerli değeri gösterir datatip `c1` değişkeni ve özelliklerini inceleme olanak sağlar. Beklediğiniz olmayan bir değer görürseniz, hata ayıklama sırasında bir hata kodu yukarıdaki veya arama satırlarında büyük olasılıkla sahip olursunuz. 

2. Geçerli özellik değerlerini aramak için datatip genişletin `c1` nesnesi.

3. Değerini görmeye devam edebilmesi için bu datatip PIN istiyorsanız `c1` kod yürütmek olsa da, küçük PIN simgesine tıklayın. (Uygun bir konuma sabitlenmiş datatip taşıyabilirsiniz.)

## <a name="edit-code-and-continue-debugging"></a>Kod düzenleme ve hata ayıklama devam et

Hata ayıklama oturumu sırasında ortasında kodunuzu test etmek istediğiniz bir değişiklik tanımlamak istiyorsanız, çok yapabilirsiniz.

1. İkinci bir örneğini tıklatın `c2.First.Value` değiştirip `c2.First.Value` için `c2.Last.Value`.

2. Tuşuna **F10** (veya **hata ayıklama > Step Over**) birkaç kez hata ayıklayıcı ilerleyin ve düzenlenen kod yürütün.

    ![Düzenle ve devam et](../debugger/media/dbg-qs-edit-and-continue-csharp.gif "Düzenle ve devam et")

    **F10** (yine, atlama kodu yürütür) bunların içine Adımlama yerine işlevleri üzerinden bir zaman alır, ancak adımları hata ayıklayıcı bir ifadede ilerler.

Düzenle ve devam et kullanma ve özellik kısıtlamaları hakkında daha fazla bilgi için bkz: [Düzenle ve devam et](../debugger/edit-and-continue.md).

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, adım kodlarda, hata ayıklayıcı başlatmak ve değişkenleri incelemek üzere nasıl öğrendiniz. Daha fazla bilgi için bağlantılar ile birlikte hata ayıklama özellikleri en üst düzey bir görünüm elde isteyebilirsiniz.

> [!div class="nextstepaction"]
> [Hata ayıklayıcısı özellik turu](../debugger/debugger-feature-tour.md)
