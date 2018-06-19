---
title: Python eğitmen, 4. adım, hata ayıklama ile çalışma
description: Adım 4 çekirdek kılavuzun Visual Studio'da hata ayıklayıcısı'ndaki Python kodu çalıştırmak nasıl kapsayan, Python yeteneklerini.
ms.date: 03/08/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 8f354c9209a7180db616a7ccc622df2809cfebe9
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2018
ms.locfileid: "32031988"
---
# <a name="step-4-running-code-in-the-debugger"></a>4. adım: hata ayıklayıcıda kodu çalıştırma

**Önceki adımda: [etkileşimli REPL penceresini kullanma](tutorial-working-with-python-in-visual-studio-step-03-interactive-repl.md)**

Bir zengin düzenleme deneyimi ve etkileşimli pencere sağlama projeleri yönetmeye ek olarak, Visual Studio için Python kodu tam özellikli hata ayıklama sağlar. Hata Ayıklayıcısı'ndaki kodunuzu adım her döngü tekrarında dahil olmak üzere adım, çalıştırabilirsiniz. Belirli koşullar doğru olduğunda program de duraklatabilirsiniz. Herhangi bir noktada Hata Ayıklayıcısı'ndaki program duraklatıldığında, tüm program durumu inceleyin ve değişkenlerin değerini değiştirin. Gibi eylemleri program hataları izleme için gerekli olan ve tam program akışı dikkatle izlemek için çok yararlı yardımları de sağlar.

1. Kodla `PythonApplication1.py` aşağıdaki dosya. Bu değişim kodunun genişletir `make_dot_string` böylece hata ayıklayıcısında ayrık adımları inceleyebilirsiniz. Ayrıca yerleştirir `for` içine döngü bir `main` işlev ve o işlevini çağırarak açıkça çalıştırır:

    ```python
    from math import cos, radians

    # Create a string with spaces proportional to a cosine of x in degrees
    def make_dot_string(x):
        rad = radians(x)                             # cos works with radians
        numspaces = int(20 * cos(radians(x)) + 20)   # scale to 0-40 spaces
        st = ' ' * numspaces + 'o'                   # place 'o' after the spaces
        return st

    def main():
        for i in range(0, 1800, 12):
            s = make_dot_string(i)
            print(s)

    main()
    ```

1. F5 tuşuna basarak veya seçerek kod düzgün çalışır onay **hata ayıklama > hata ayıklamayı Başlat** menü komutu. Bu kod hata ayıklayıcısı'ndaki çalışır ancak programı çalışırken duraklatmak için herhangi bir şey yapmadınız olduğundan, birkaç yineleme için wave deseni yalnızca yazdırır. Çıktı penceresini kapatmak için herhangi bir tuşa basın.

    > [!Tip]
    > Program tamamlandığında, çıkış penceresi otomatik olarak kapatmak için değiştirmek `main()` aşağıdaki kod ile çağırın:
    >
    > ```python
    > if __name__ == "__main__":
    >     sys.exit(int(main() or 0))
    > ```

1. Bir kesme noktası ayarlayın `for` tıklatarak kez gri kenar boşluğunda bu satırı veya bu satırda düzeltme işareti yerleştirme ve kullanarak deyimi **hata ayıklama > kesme** komutu (F9). Kırmızı noktaya (okla belirtildiği gibi) kesme noktası belirtmek için gri kenar boşluğu görünür:

    ![Kesme noktası ayarlama](media/vs-getting-started-python-18-debugging1.png)

1. Hata ayıklayıcı yeniden (F5) başlatın ve bu kodu durdurur, kesme noktası satırıyla çalışan bakın. Burada arama inceleyebilirsiniz yığın ve değişkenleri inceleyin. Kapsam içinde değişkenleri görünür **otomobiller** tanımlandığı zaman penceresi; ayrıca anahtara yapabilirsiniz **Yereller** tüm değişkenleri, Visual Studio göstermek için bu pencerenin altındaki görünümü bulur Geçerli kapsam (dahil olmak üzere işlevler), tanımlanan önce bile:

    ![Python için kesme noktası UI deneyimi](media/vs-getting-started-python-19-debugging2b.png)

1. Hata ayıklama araç çubuğu (aşağıda Visual Studio penceresinin üst kısmında gösterilen) inceleyin. Bu araç yaygın hata ayıklama komutlara hızlı erişim sağlar (Ayrıca bulunabilir üzerinde **hata ayıklama** menüsü):

    ![Önemli hata ayıklama araç çubuğu düğmeleri](media/vs-getting-started-python-20-debugging3.png)

    Düğmeler soldan sağa doğru şekilde:
    - **Devam** (F5) sonraki kesme kadar veya program tamamlama kadar programı çalıştırır.
    - **Tüm kesme** (Ctrl + Alt + Break) uzun süre çalışan program duraklatır.
    - **Hata ayıklama Durdur** (Shift + F5) olduğu ve hata ayıklayıcısı çıkar her yerde programı durdurur.
    - **Yeniden** (Ctrl + Shift + F5) olduğu ve hata ayıklayıcı en baştan yeniden her yerde programı durdurur.
    - **Sonraki deyim göster** (Alt + Num *) çalıştırmak için kod sonraki satıra geçer. Bu, geçici bir hata ayıklama oturumu sırasında kodunuzu içinde gidin ve hızlı bir şekilde hata ayıklayıcı burada duraklatıldı noktasına döndürmek için durumunda en yararlı olur.
    - **Step Into** (F11) çağrılan işlevlerin girerek kodun sonraki satırında, çalıştırır.
    - **Step Over** (F10) çağrılan işlevlerin girmeden kodun sonraki satırında, çalıştırır.
    - **Step Out** (Shift + F11) geçerli işlevi geri kalanı çalıştırır ve arama kodda duraklatır.

1. Üzerinden adım `for` deyimiyle **Step Over**. *Atlama* hata ayıklayıcı geçerli kod satırı ile herhangi bir işlev çağrıları dahil olmak üzere, çalıştırır ve ardından hemen yeniden duraklatır anlamına gelir. Bildirim nasıl değişkeni `i` şimdi tanımlanan **Yereller** ve **otomobiller** windows.

1. Kodun sonraki satırında, çağıran, Adımlama `make_dot_string` ve duraklatır. Step Over Burada özellikle anlamına gelir hata ayıklayıcı, tam çalışır `make_dot_string` ve koşullarına dönüldüğünde duraklatır. Hata ayıklayıcı ayrı bir kesme noktası mevcut değilse bu işlev içinde durdurmaz.

1. Kod içinde birkaç kez atlama devam ve uyun nasıl değerleri **Yereller** veya **otomobiller** penceresi Değiştir.

1. İçinde **Yereller** veya **otomobiller** penceresinde, çift içinde **değeri** ya da sütun `i` veya `s` değerini düzenlemek için değişkenleri. ENTER tuşuna basın veya değişiklikleri uygulamak için bu değeri dışında'ı tıklatın.

1. Kod kullanarak aracılığıyla atlama devam **Step Into**. İşlev çağrısı içinde bulunan gibi hata ayıklama bilgileri, hata ayıklayıcı girer step INTO anlamına gelir `make_dot_string`. Bir kez iç `make_dot_string` yerel değişkenlerini inceleyin ve kendi kod üzerinden özellikle adım.

1. Step Into ile atlama devam etmek ve sonuna ulaştığında dikkat `make_dot_string`, sonraki adıma döndürür `for` döngü yeni dönüş değeri ile `s` değişkeni. Yeniden adım olarak `print` deyimi, bildirim bu adımla üzerinde `print` bu işlevdeki geçmiyor. Bunun nedeni, `print` Python içinde yazılmış değil ancak Python çalışma zamanı içinde yerine yerel kodudur.

1. Step Into yeniden kadar halinde olduğunuz kadar kullanmaya devam `make_dot_string`. Ardından **Step Out** ve geri bildirimi `for` döngü. Step Out ile hata ayıklayıcı işlevi geri kalanı çalışır ve otomatik olarak çağıran kodu duraklatır. Hata ayıklama istediğiniz uzun bir işlev kısmı adım adım zaman, bu çok yararlı olur ancak kullanılmadıkları adım ve gerekmeyen açık bir kesme noktası çağrı kodda ayarlamak istiyor.

1. Sonraki kesme ulaşılana kadar program çalıştırmaya devam etmek için kullanmak **devam** (F5). Bir kesme noktası olduğundan `for` döngü, sonraki yinelemesinde bölün.

1. Yineleme döngüsü yüzlerce atlama olabilir can sıkıcı, Visual Studio eklemenize olanak sağlayan şekilde bir *koşulu* bir kesme noktası için. Yalnızca koşul karşılandığında hata ayıklayıcı daha sonra program kesme noktasındaki duraklatılır. Örneğin, bir koşul ile kesme kullanabileceğinizi `for` şekilde yalnızca duraklatır şekilde deyimi zaman değerini `i` 1600 aşıyor. Bu koşul ayarlamak için kırmızı kesme noktası nokta sağ tıklatın ve seçin **koşullar...** (Alt + F9 C). İçinde **kesme noktası ayarları** görünür, açılan girin `i > 1600` seçin ve ifade olarak **Kapat**. Devam etmek ve programı sonraki sonundan önceki fazla yineleme çalıştırır gözlemlemek için F5 tuşuna basın.

    ![Bir kesme noktası koşul ayarlama](media/vs-getting-started-python-21-debugging4.png)

1. Program tamamlanıncaya kadar çalışabilmesi için kesme sağ tıklayıp seçerek devre dışı **kesme noktası devre dışı bırakma** (Ctrl + F9). Ardından **devam** (veya F5 tuşuna basın) programı çalıştırmak için. Program sona erdiğinde, Visual Studio hata ayıklama oturumu durdurur ve düzenleme moduna döner. Ayrıca, kendi nokta tıklayarak kesme silebilir, ancak bu ayarladığınız herhangi bir koşul da siler unutmayın.

> [!Tip]
> Python yorumlayıcı kendisini başlatma hatası gibi bazı durumlarda, çıktı penceresi yalnızca kısa bir süre görünür ve tüm hata iletilerini görmek için bir fırsat vermeden otomatik olarak kapat. Bu durumda, Çözüm Gezgini'nde, Seç'nde projeye sağ **özellikleri**seçin **hata ayıklama** sekmesinde, ardından ekleyin `-i` için **yorumlayıcı bağımsız değişkenleri** alan. Bu bağımsız değişken, böylece Ctrl + Z, çıkmak için Enter girene kadar penceresi açık tutarak bir program tamamlandıktan sonra etkileşimli moduna geçmesi yorumlayıcı neden olur.

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [Python ortamınızda paketleri yükleniyor](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md)

### <a name="going-deeper"></a>Daha derin gitme

- [Hata Ayıklama](debugging-python-in-visual-studio.md)
- [Visual Studio'da hata ayıklamayı](../debugger/debugger-feature-tour.md) Visual Studio tam belgelerine hata ayıklama özellikleri sağlar.
