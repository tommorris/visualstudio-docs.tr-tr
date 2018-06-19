---
title: ASP.NET hata ayıklama
description: Visual Studio hata ayıklayıcısı kullanarak ASP.NET hata ayıklama
ms.custom: mvc
ms.date: 03/16/2018
ms.technology: vs-ide-debug
ms.topic: quickstart
helpviewer_keywords:
- debugger
ms.assetid: f4cea2e1-08dc-47ac-aba2-3b8c338e607f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: b3cfe8d0af7bebac5bce48e82b4237de071a41d8
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/24/2018
ms.locfileid: "34477476"
---
# <a name="quickstart-debug-aspnet-with-the-visual-studio-debugger"></a>Hızlı Başlangıç: Visual Studio hata ayıklayıcısı ile ASP.NET hata ayıklama

Visual Studio hata ayıklayıcısı uygulamalarınızı hata ayıklama yardımcı olmak üzere pek çok güçlü özellikler sağlar. Bu konuda, temel özelliklerden bazıları öğrenmek için hızlı bir yoludur.

## <a name="create-a-new-project"></a>Yeni bir proje oluşturma 

1. Visual Studio'da, **Dosya > Yeni proje**.

1. Altında **Visual C#**, seçin **Web**ve ardından Orta bölmede **ASP.NET çekirdek Web uygulaması**.

1. Gibi bir ad yazın **MyDbgApp** tıklatıp **Tamam**.

1. Görüntülenen iletişim kutusunda seçin **Web uygulaması** orta bölmesinde ve ardından **Tamam**.

     Görmüyorsanız, **Web uygulaması** proje şablonu, tıklatın **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu. Visual Studio yükleyicisi başlatır. Seçin **ASP.NET** ve **.NET Core** iş yükü, ardından **Değiştir**.

    ![Bir Web uygulaması seçin](../debugger/media/dbg-qs-aspnet-choose-web-app.png)

    Visual Studio projesi oluşturur.

1. Çözüm Gezgini'nde, About.cshtml.cs (altında Pages/About.cshtml) açın ve aşağıdaki kodu değiştirin

    ```csharp
    public void OnGet()
    {
        Message = "Your application description page.";
    }
    ```

    Bu kodu:

    ```csharp
    public void OnGet()
    {
        LinkedList<int> result = doWork();
        Message = "Result of work: " + result.First.Value + ", " + result.First.Value;
    }

    private static LinkedList<int> doWork()
    {
        LinkedList<int> c1 = new LinkedList<int>();

        c1.AddLast(10);
        c1.AddLast(20);

        LinkedList<int> c2 = new LinkedList<int>(c1);

        return c2;

    }
    ```

## <a name="set-a-breakpoint"></a>Bir kesme noktası ayarlama

A *kesme noktası* Visual Studio, çalışan burada askıya gösteren bir işaretçi kod değişkenlerin değerleri veya bellek veya karşılamadığını kod dalı çalıştırıldığında davranışını göz atın biçimde değil. Hata ayıklama, en temel özelliğidir.

1. Cilt payını solundaki kesme noktası ayarlamak için tıklayın `doWork` işlevi (veya kod ve tuşuna satırını seçin **F9**).

    ![Bir kesme noktası ayarlama](../debugger/media/dbg-qs-set-breakpoint-aspnet.png)

    Açılan parantez soluna kesme noktası ayarlayın (`{`).

1. Şimdi basın **F5** (veya tercih **hata ayıklama > hata ayıklamayı Başlat**).

1. Web sayfa yüklendiğinde tıklatın **hakkında** web sayfasının üst bağlantı.

    Kesme noktası ayarladığınız hata ayıklayıcı duraklatır. Hata ayıklayıcı ve uygulama yürütme burada duraklatıldı deyimi sarı okla belirtilir. Açılan parantez içeren satırı (`{`) sonra `doWork` işlevi bildirimi henüz çalıştırılmadı.

    ![Bir kesme noktası isabet](../debugger/media/dbg-qs-hit-breakpoint-aspnet.png)

    > [!TIP]
    > Döngü veya özyineleme bir kesme noktası varsa veya sık, adım adım birçok kesme noktaları varsa bir [koşullu kesme noktası](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression) yalnızca belirli koşullar karşılandığında, kodunuzu askıya emin olmak için. Bu zamandan tasarruf sağlar ve ayrıca, yeniden sabit ayıklanır kolaylaştırabilir.

## <a name="navigate-code"></a>Kod gidin

Devam etmek için hata ayıklayıcı istemek üzere farklı komutlar vardır. Visual Studio 2017 içinde yeni bir yararlı kod Gezinti komutu gösteriyoruz.

Duraklatılmış kesme noktasında olsa da, deyimi vurgulu `return c2` yeşil kadar **Çalıştır'ı tıklatın** düğmesini ![çalıştırmak için tıklatın](../debugger/media/dbg-tour-run-to-click.png) görünür ve tuşuna basın **Çalıştır'ı tıklatın** düğme.

![Çalıştır'ı tıklatın](../debugger/media/dbg-qs-run-to-click-aspnet.png)

Uygulama yürütme devam eder ve düğmesini tıklattığınız kod satırında duraklatır.

Ortak klavye komutları için kullanılan kod aracılığıyla adım dahil **F10** ve **F11**. Daha fazla ayrıntılı yönergeler için bkz: [Başlangıç Kılavuzu](../debugger/getting-started-with-the-debugger.md).

## <a name="inspect-variables-in-a-datatip"></a>Bir datatip değişkenlerde inceleyin.

1. Geçerli satırda (sarı yürütme işaretçi işaretli) kodunun, üzerine gelerek `c2` bir datatip göstermek için fare nesnesiyle.

    ![Bir datatip görüntüleyin](../debugger/media/dbg-qs-data-tip-aspnet.png)

    Geçerli değeri gösterir datatip `c2` değişkeni ve özelliklerini inceleme olanak sağlar. Beklediğiniz olmayan bir değer görürseniz, hata ayıklama sırasında bir hata kodu yukarıdaki veya arama satırlarında büyük olasılıkla sahip olursunuz. 

2. Geçerli özellik değerlerini aramak için datatip genişletin `c2` nesnesi.

3. Değerini görmeye devam edebilmesi için bu datatip PIN istiyorsanız `c2` kod yürütmek olsa da, küçük PIN simgesine tıklayın. (Uygun bir konuma sabitlenmiş datatip taşıyabilirsiniz.)

## <a name="edit-code-and-continue-debugging"></a>Kod düzenleme ve hata ayıklama devam et

Hata ayıklama oturumu sırasında ortasında kodunuzu test etmek istediğiniz bir değişiklik tanımlamak istiyorsanız, çok yapabilirsiniz.

1. İçinde `OnGet` yöntemi, ikinci bir örneğini tıklatın `result.First.Value` değiştirip `result.First.Value` için `result.Last.Value`.

1. Tuşuna **F10** (veya **hata ayıklama > Step Over**) birkaç kez hata ayıklayıcı ilerleyin ve düzenlenen kod yürütün.

    ![Düzenle ve devam et](../debugger/media/dbg-qs-edit-and-continue-aspnet.png "Düzenle ve devam et")

    **F10** (yine, atlama kodu yürütür) bunların içine Adımlama yerine işlevleri üzerinden bir zaman alır, ancak adımları hata ayıklayıcı bir ifadede ilerler.

Düzenle ve devam et kullanma ve özellik kısıtlamaları hakkında daha fazla bilgi için bkz: [Düzenle ve devam et](../debugger/edit-and-continue.md).

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, adım kodlarda, hata ayıklayıcı başlatmak ve değişkenleri incelemek üzere nasıl öğrendiniz. Daha fazla bilgi için bağlantılar ile birlikte hata ayıklama özellikleri en üst düzey bir görünüm elde isteyebilirsiniz.

> [!div class="nextstepaction"]
> [Hata ayıklayıcısı özellik turu](../debugger/debugger-feature-tour.md)
