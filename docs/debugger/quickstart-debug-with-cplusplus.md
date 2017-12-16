---
title: "Visual Studio hata ayıklayıcısı kullanarak Visual C++ ile hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 12/06/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: quickstart
helpviewer_keywords: debugger
ms.assetid: 639e430b-6d2d-46bd-b738-8c60dfb384f1
caps.latest.revision: "1"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 448822f7a6d71075527680a4af34e7faa46ca8c6
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/15/2017
---
# <a name="debug-with-c-using-the-visual-studio-debugger"></a>Visual Studio hata ayıklayıcısı kullanarak Visual C++ ile hata ayıklama

Visual Studio hata ayıklayıcısı uygulamalarınızı hata ayıklama yardımcı olmak üzere pek çok güçlü özellikler sağlar. Bu konuda, temel özelliklerden bazıları öğrenmek için hızlı bir yoludur.

## <a name="create-a-new-project"></a>Yeni bir proje oluşturma 

1. Visual Studio'da, **Dosya > Yeni proje**.

2. Altında **Visual C++**, seçin **Windows Masaüstü**ve ardından Orta bölmede **Windows konsol uygulaması**.

    Görmüyorsanız, **Windows konsol uygulaması** proje şablonu, tıklatın **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu. Visual Studio yükleyicisi başlatır. Seçin **C++ ile masaüstü geliştirme** iş yükü, ardından **Değiştir**.

3. Gibi bir ad yazın **MyDbgApp** tıklatıp **Tamam**.

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
    #include <list>  
    #include <iostream>

    using namespace std;

    void doWork()
    {
        list <int> c1;

        c1.push_back(10);
        c1.push_back(20);

        const list <int> c2 = c1;
        const int &i = c2.front();
        const int &j = c2.front();
        cout << "The first element is " << i << endl;
        cout << "The second element is " << j << endl;

    }

    int main()
    {
        doWork();
    }
    ```

## <a name="set-a-breakpoint"></a>Bir kesme noktası ayarlama

A *kesme noktası* Visual Studio, çalışan burada askıya gösteren bir işaretçi kod değişkenlerin değerleri veya bellek veya karşılamadığını kod dalı çalıştırıldığında davranışını göz atın biçimde değil. Hata ayıklama, en temel özelliğidir.

1. Cilt payını solundaki kesme noktası ayarlamak için tıklayın `doWork` işlev çağrısı (veya kod ve tuşuna satırını seçin **F9**).

    ![Bir kesme noktası belirleyerek](../debugger/media/dbg-qs-set-breakpoint.png "bir kesme noktası ayarlama")

2. Şimdi basın **F5** (veya tercih **hata ayıklama > hata ayıklamayı Başlat**).

    ![Bir kesme noktası isabet](../debugger/media/dbg-qs-hit-breakpoint.png "bir kesme noktası isabet")

    Kesme noktası ayarladığınız hata ayıklayıcı duraklatır. Hata ayıklayıcı ve uygulama yürütme burada duraklatıldı deyimi sarı okla belirtilir. İçeren satırı `doWork` işlev çağrısı henüz çalıştırılmadı.

    > [!TIP]
    > Döngü veya özyineleme bir kesme noktası varsa veya çok sık, adım adım kesme noktalarını varsa bir [koşullu kesme noktası](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression) yalnızca belirli koşullar karşılandığında, kodunuzu askıya emin olmak için. Bu zamandan tasarruf sağlar ve ayrıca, yeniden sabit ayıklanır kolaylaştırabilir.

    C++'ta bellekle ilgili hataları ayıklamak üzere çalışırken de kesme noktaları adres değerleri (NULL arayın) incelemek için kullanabilirsiniz ve başvuru sayısı. 

## <a name="navigate-code"></a>Kod gidin

Devam etmek için hata ayıklayıcı istemek üzere farklı komutlar vardır. Visual Studio 2017 içinde yeni bir yararlı kod Gezinti komutu göstereceğiz.

- Duraklatılmış kesme noktasında olsa da, deyimi vurgulu `c1.push_back(20)` yeşil kadar **Çalıştır'ı tıklatın** düğmesini ![çalıştırmak için tıklatın](../debugger/media/dbg-tour-run-to-click.png "RunToClick") görünür ve tuşuna basın **Çalıştır'ı tıklatın** düğmesi.

    ![Çalıştır'ı tıklatın](../debugger/media/dbg-qs-run-to-click.png "Çalıştır'ı tıklatın")

    Uygulama yürütülmeye çağırma `doWork`ve düğmesini tıklattığınız kod satırında duraklatır.

    Ortak klavye komutları için kullanılan kod aracılığıyla adım dahil **F10** ve **F11**. Daha fazla ayrıntılı yönergeler için bkz: [Başlangıç Kılavuzu](../debugger/getting-started-with-the-debugger.md).

## <a name="inspect-variables-in-a-datatip"></a>Bir datatip değişkenlerde inceleyin.

1. Geçerli satırda (sarı yürütme işaretçi işaretli) kodunun, üzerine gelerek `c1` bir datatip göstermek için fare nesnesiyle.

    ![Bir datatip görüntülemek](../debugger/media/dbg-qs-data-tip.png "bir datatip görüntüleyin")

    Geçerli değeri gösterir datatip `c1` değişkeni ve özelliklerini inceleme olanak sağlar. Beklediğiniz olmayan bir değer görürseniz, hata ayıklama sırasında bir hata kodu yukarıdaki veya arama satırlarında büyük olasılıkla sahip olursunuz. 

2. Geçerli özellik değerlerini aramak için datatip genişletin `c1` nesnesi.

3. Değerini görmeye devam edebilmesi için bu datatip PIN istiyorsanız `c1` kod yürütmek olsa da, küçük PIN simgesine tıklayın. (Uygun bir konuma sabitlenmiş datatip taşıyabilirsiniz.)

## <a name="edit-code-and-continue-debugging"></a>Kod düzenleme ve hata ayıklama devam et

Hata ayıklama oturumu sırasında ortasında kodunuzu test etmek istediğiniz bir değişiklik tanımlamak istiyorsanız, çok yapabilirsiniz.

1. İkinci bir örneğini tıklatın `c2.front()` değiştirip `c2.front()` için `c2.back()`.

2. Tuşuna **F10** (veya **hata ayıklama > Step Over**) birkaç kez hata ayıklayıcı ilerleyin ve düzenlenen kod yürütün.

    ![Düzenle ve devam et](../debugger/media/dbg-qs-edit-and-continue.gif "Düzenle ve devam et")

    **F10** (yine, atlama kodu yürütür) bunların içine Adımlama yerine işlevleri üzerinden bir zaman alır, ancak adımları hata ayıklayıcı bir ifadede ilerler.

Düzenle ve devam et kullanma ve özellik kısıtlamaları hakkında daha fazla bilgi için bkz: [Düzenle ve devam et](../debugger/edit-and-continue.md).

## <a name="next-steps"></a>Sonraki adımlar

- Hata ayıklayıcı hakkında daha fazla bilgi için bkz: [hata ayıklayıcısını başlatma ve kod gidin](../debugger/getting-started-with-the-debugger.md).
- Kesme noktaları hakkında daha fazla bilgi için bkz: [kesme noktalarını kullanma](../debugger/using-breakpoints.md).

## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da hata ayıklama](../debugger/index.md)  
 [Hata ayıklayıcı özelliği turu](../debugger/debugger-feature-tour.md)
