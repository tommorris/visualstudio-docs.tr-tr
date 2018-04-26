---
title: Python Eğitmen ile adım 3, etkileşimli REPL pencere çalışma
description: Adım 3 / Çekirdek kılavuz Python etkileşimli REPL penceresi kapsayan Visual Studio'da Python yeteneklerini.
ms.date: 01/16/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 3d5d0224c9f6d8d76f73c79feeaa363a6e0a954a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="step-3-using-the-interactive-repl-window"></a>3. adım: etkileşimli REPL penceresini kullanma

**Önceki adımda: [yazmayı ve çalışan kod](tutorial-working-with-python-in-visual-studio-step-02-writing-code.md)**

Visual Studio *etkileşimli pencere* Python normal düzenleme-derleme-hata ayıklama döngüsü önemli ölçüde kısaltır zengin read-değerlendir-yazdırma-döngüsü (REPL) deneyimi sağlar. Etkileşimli pencere Python komut satırının REPL deneyiminin tüm yetenekleri sağlar. Ayrıca, çok kaynak dosyaları Visual Studio'da kod değişimi Aksi takdirde komut satırıyla sıkıcı Düzenleyicisi kolaylaştırır.

1. Çözüm Gezgini'nde (örneğin, "bir önceki grafikte gösterildiği Python 3.6 (32 bit)") ve seçerek projenin Python ortamı sağ tıklayarak etkileşimli penceresini açın **açık etkileşimli pencere**. Alternatif olarak seçebileceğiniz **Görünüm > Diğer Pencereler > Python etkileşimli Windows** ana Visual Studio menüsünde.

1. Standart düzenleyiciyle aşağıda etkileşimli penceresi açılır `>>>` Python REPL istemi. **Ortam** aşağı açılan liste çalışmak için belirli bir yorumlayıcı seçmenize olanak sağlar. Görmemeleri ayrıca arasında iki windows ayırıcı sürükleyerek yapabilirsiniz etkileşimli pencereyi daha büyük hale isteyebilirsiniz:

    ![Python etkileşimli penceresini açın ve yeniden boyutlandırmak için sürükleme](media/vs-getting-started-python-11-interactive1b.png)

    > [!Tip]
    > Visual Studio'da Pencereleri tümünün bordering ayırıcılar sürükleyerek boyutlandırabilirsiniz. Ayrıca, windows bağımsız olarak Visual Studio çerçeve dışarı sürükleyin ve çerçevesinde istiyor ancak bunları yeniden düzenleme. Tüm Ayrıntılar için bkz: [pencere düzenlerini özelleştirme](../ide/customizing-window-layouts-in-visual-studio.md).

1. Aşağıdaki gibi birkaç ifadeler girin `print("Hello, Visual Studio")` ifadeler gibi ve `123/456` hemen sonuçları görmek için:

    ![Python etkileşimli pencere hemen sonuçları](media/vs-getting-started-python-12-interactive2.png)

1. Bir işlev tanımı gibi çok satırlı bir deyimi yazmaya başladığınızda etkileşimli penceresinde Python'un gösterilir ve `...` satırları sağlayan, komut satırı REPL farklı olarak, otomatik girinti etmeden sor:

    ![Python etkileşimli deyimi devamlılık penceresiyle](media/vs-getting-started-python-13-interactive3.png)

1. Etkileşimli pencere her şeyi girdiğinizden ve çok satırlı geçmiş öğelerinin ile komut satırı REPL bağlı artırır tam geçmişini sağlar. Örneğin, kolayca tüm tanımını çağırabilirsiniz `f` işlev tek bir birim olarak ve kolayca adına değiştirme `make_double`, satır işlevi yeniden oluşturmak yerine.

1. Visual Studio, etkileşimli pencereyi bir düzenleyici penceresinden birden çok kod satırını gönderebilirsiniz. Bu özellik, bir kaynak dosyasında kodunu korumak ve kolayca select bölümlerini etkileşimli penceresine göndermek için olanak sağlar. Bu tür kod parçaları bütün program çalıştırmak zorunda yerine hızlı REPL ortamı ile çalışabilirsiniz. Bu özellik görmek için önce Değiştir `for` içinde döngü `PythonApplication1.py` aşağıdaki dosyasıyla:

    ```python
    # Create a string with spaces proportional to a cosine of x in degrees
    def make_dot_string(x):
        return ' ' * int(20 * cos(radians(x)) + 20) + 'o'
    ```

1. Yalnızca seçin `import` ve `from` deyimlerinde `.py` dosya, sağ tıklatın ve seçin **etkileşime Gönder** (veya Ctrl + Enter tuşuna basın). Kod parçası hemen etkileşimli penceresine yapıştırılan ve çalıştırın. Şimdi seçin `make_dot_string` işlev ve bu kod parçası yeniden çalışır aynı komutu yineleyin. Kod bir işlev tanımladığından, hızlı bir şekilde bu işlevi birkaç kez çağırarak test edebilirsiniz:

    ![Etkileşimli penceresine kod gönderme ve sınama](media/vs-getting-started-python-14-interactive4.png)

    > [!Tip]
    > Ctrl + Enter düzenleyicisini kullanarak *olmadan* seçim etkileşimli penceresinde geçerli kod satırı ile çalışır ve otomatik olarak düzeltme işareti sonraki satırında yerleştirir. Bu özellik ile art arda Ctrl + Enter tuşuna basarak yalnızca Python komut satırı ile mümkün olmayan kodunuzu adım adım için kullanışlı bir yol sağlar. Ayrıca sağlar hata ayıklayıcı çalıştıran ve mutlaka programınızı başından başlayarak olmadan kodunuz adım.

1. Ayrıca kopyalayın ve birkaç satırlık ile Python komut satırı REPL. yapmak zor olan kod parçacığını aşağıdaki gibi herhangi bir kaynaktan etkileşimli penceresine yapıştırın İçinde yazmış gibi etkileşimli pencere yapıştırılırken, bu kodu çalıştırır:

    ```python
    for i in range(360):
        s = make_dot_string(i)
        print(s)
    ```

    ![Birden çok gönderme etkileşimli kullanarak kod satırını yapıştırma](media/vs-getting-started-python-15-interactive5.png)

1. Gördüğünüz gibi bu kod düzgün çalışır, ancak çıktısını çok inspiring değil. Farklı adım değerinde `for` döngü kosinüsünü wave birkaçını göstermek. Neyse ki, çünkü tüm `for` döngü olan tek bir birim olarak REPL geçmişinde, geri dönmek kolaydır ve her değişiklik yapma, istediğiniz ve ardından test işlevi yeniden. İlk geri çağırma için yukarı ok tuşlarına basın `for` döngü. (Bunu yukarı yapmak ve geçmişinde geçiş yapmak ok devam kadar) kodunda gezinme başlatmak için sol veya sağ ok tuşuna basın. Gidin ve değiştirme `range` belirtimine `range(0, 360, 12)`. Sonra Ctrl + Enter (kodda herhangi bir yere) tüm deyimi yeniden çalıştırmak için tuşuna basın:

    ![Bir önceki deyimi etkileşimli penceresinde düzenleme](media/vs-getting-started-python-16-interactive6.png)

1. En iyi gibi bir değer bulana kadar farklı adım ayarlarla denemek için işlemi yineleyin. Ayrıca wave bu gibi bir durumda aralığı uzatma tarafından yineleme yapabileceğiniz `range(0, 1800, 12)`.
 
1. Etkileşimli pencerede yazılmış koduyla memnun kaldığınızda, sağ tıklatın ve seçin seçin **kod Kopyala** (Ctrl + Shift + C) ve ardından düzenleyiciye yapıştırın. Visual Studio'nun bu özel özellik herhangi bir çıktı otomatik olarak nasıl atlar fark yanı sıra `>>>` ve `...` ister. Örneğin, aşağıdaki resimde kullanarak gösterir **kod Kopyala** komut istemleri ve çıktı içeren Seçimi:

    ![Etkileşimli pencere kopyalama kod komutu ve çıkış istekleri ile seçimi](media/vs-getting-started-python-17-interactive7.png)

    Düzenleyicisine yapıştırın, yalnızca kodu alın:

    ```python
    for i in range(0, 1800, 12):
        s = make_dot_string(i)
        print(s)
    ```

    Standart çıktı ve istekleri dahil olmak üzere etkileşimli pencere tam içeriğini kopyalamak istiyorsanız, yalnızca kullanın **kopyalama** komutu.

1. Ne yalnızca yaptığınızı etkileşimli penceresinin hızlı REPL ortamı küçük bir kod parçasını ayrıntılarını çıkışı çalışmaya olduğu sonra uygun şekilde bu kodu projenizin kaynak dosyasına eklendi. Şimdi çalıştırdığınızda kodu yeniden Ctrl + F5'e (veya **hata ayıklama > hata ayıklama olmadan Başlat**), istediğinizi tam sonuçları görüntüleyin.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Hata ayıklayıcı çalışan kod](tutorial-working-with-python-in-visual-studio-step-04-debugging.md)

## <a name="going-deeper"></a>Daha derin gitme

- [Etkileşimli penceresini kullanma](python-interactive-repl-in-visual-studio.md)
- [IPython REPL kullanma](interactive-repl-ipython.md)
