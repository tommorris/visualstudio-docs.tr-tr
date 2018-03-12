---
title: "Visual Studio'da düzenleme giriş | Microsoft Docs"
ms.custom: 
ms.date: 11/30/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 082a89453d76ac70edfbd39681d33b6af2700cc7
ms.sourcegitcommit: 3285243d6c0521266053340fe06505885d12178b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2018
---
# <a name="quickstart-use-the-code-editor"></a>Hızlı Başlangıç: Kod Düzenleyicisi'ni kullanın

Bu 10 dakikalık girişte düzenleyiciye, Visual Studio yazma, gezinme ve kodu daha kolay anlama yapar yollardan bazılarını aramak için bir dosya için kod ekleyeceğiz.

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) ücretsiz yüklemek için sayfa.

Bu hızlı başlangıç bir programlama dili ile bilginiz varsayar. Yoksa, önerdiğimiz programlama quickstarts birini ilk bakış, gibi bir web uygulaması ile oluşturma [Python](../ide/quickstart-python.md) veya [C#](../ide/tutorial-csharp-aspnet-core.md), veya bir konsol uygulaması ile oluşturma [Visual Basic](../ide/quickstart-visual-basic-console.md) veya [C++](../ide/quickstart-cpp.md).

## <a name="create-a-new-code-file"></a>Yeni bir kod dosyası oluşturma

Yeni bir dosya oluşturarak ve biraz kod eklemeyi başlatın. Biz Düzenleyici sunar avantajlarından bazıları kazanmak için bir proje oluşturmak zorunda değilsiniz dikkat edin.

1. Visual Studio'yu açın ve **dosya** menü çubuğundaki menüsü seçin **yeni** > **dosya...** .

1. İçinde **yeni dosya** iletişim kutusunda **genel** kategorisi seçin **Visual C# sınıfı**ve ardından **açık**.

   Yeni bir dosya bir C# sınıfı çatıyı düzenleyicisiyle açar.

## <a name="using-code-snippets"></a>Kod parçacıkları

Visual Studio hızla ve kolayca yaygın olarak oluşturmak için kullanabileceğiniz yararlı kod parçacıkları kod blokları kullanılan sağlar. [Kod parçacıkları](../ide/code-snippets.md) C#, Visual Basic ve C++ gibi farklı programlama dilleri için kullanılabilir. C# ekleyelim `void Main` bizim dosyasına parçacığı.

1. İmlecinizi kapanış ayracı altına yerleştirin `Class1` oluşturucusu ve karakterleri girin `svm`.

   İlgili bilgilerle görünür bir IntelliSense iletişim kutusu görebilirsiniz `svm` parçacığı.

   ![IntelliSense kod parçacığında](media/quickstart-intellisense-snippet.png)

1. Tuşuna **sekmesini** iki kez kod parçacığını eklemek için.

   Gördüğünüz `static void Main()` yöntem imzası dosyasına eklenen. `Main()` C# uygulamaları için giriş noktası bir yöntemdir.

Kullanılabilir kod parçacıkları farklı diller için farklılık gösterir. Seçerek programlama diliniz için kullanılabilir kod parçacıkları bakabilirsiniz **Düzenle**, **IntelliSense**, **parçacığı Ekle...** ve ardından, dil klasörünü seçme. C# ' ta listesi şu şekildedir:

![C# kod parçacığı listesi](media/quickstart-code-snippet-list.png)

Bir sınıf, bir oluşturucu oluşturmak için parçacıkları listesi içerir `Console.WriteLine()`, `for` döngüler, `if` ve `switch` deyimleri ve daha fazlası.

## <a name="commenting-out-code"></a>Kodu yorum oluşturma

Araç çubuğu düğmeleri, kodu daha üretken olmak için çeşitli sağlar. Örneğin, IntelliSense tamamlanma modu Değiştir, artırın veya bir Girintiyi Azalt, yer işareti ayarlayın veya kodu açıklama. Bu bölümde, biz açıklama derlemek için istemediğiniz biraz kod çıkışı.

![Düzenleyici araç çubuğu](media/quickstart-editor-toolbar.png)

1. Aşağıdaki kodu yapıştırın `Main()` yöntem gövdesi.

    ```csharp
    // _words is a string array that we'll sort alphabetically
    string[] _words = {
        "the",
        "quick",
        "brown",
        "fox",
        "jumps"
    };

    string[] morewords = {
        "over",
        "the",
        "lazy",
        "dog"
    };

    IEnumerable<string> query = from word in _words
                                orderby word.Length
                                select word;
    ```

1. Biz kullanmadığınız `morewords` değişkeni ancak biz kullanabilir, daha sonra silmek istemediğiniz şekilde. Bunun yerine, bu satırı şimdi açıklama. Tüm tanımını seçin `morewords` için kapanış noktalı virgül ve ardından **seçili satırları açıklama** düğmesi araç veya tuşlarına basın **Ctrl** + **K**, **Ctrl**+**C**.

   ![Açıklama düğmesi](media/quickstart-comment-out.png)

   C# açıklama karakterleri `//` kodu açıklama eklemek için seçilen her satırın başlangıcına eklenir.

## <a name="collapsing-code-blocks"></a>Kod blokları daraltma

Biz boş Oluşturucusu görmek istemediğiniz `Class1` üretilen, böylece kodu bizim görünümünü sekmenize Düzen vermenize, şimdi onu daraltmak için. Küçük bir gri kutu içindeki eksi işaretiyle Oluşturucusu ilk satırının kenar boşluğunda seçin. Ya da klavye kullanıcısıysanız imleci herhangi bir yere Oluşturucusu kod ve tuşuna koyun **Ctrl**+**M**, **Ctrl**+**M** .

![Daralt düğmesi anahat oluşturma](media/quickstart-collapse.png)

Üç nokta ve ardından yalnızca ilk satırı, kod bloğunu daraltır (`...`). Kod bloğunu yeniden genişletmek için şimdi bir artı işareti veya tuşlarına basın aynı gri kutusunda tıklatın **Ctrl**+**M**, **Ctrl**+**M**  yeniden. Bu özellik adında [anahat oluşturma](../ide/outlining.md) ve uzun yöntemleri ya da tüm sınıflar daraltma özellikle yararlıdır.

## <a name="viewing-symbol-definitions"></a>Sembol tanımlarını görüntüleme

Visual Studio düzenleyicisinde bir tür, yöntem, vb. tanımını incelemek kolaylaştırır. Tanımı, örneğin seçerek içeren dosyayı gitmek için tek yönlü olduğu **Tanıma Git** simgenin herhangi bir yere başvuruluyor. İçinde çalışırken odağınız uzağa doğru dosya taşınmaz bir bile daha hızlı yolu kullanmaktır [Peek tanımı](../ide/go-to-and-peek-definition.md#peek-definition). Şimdi tanımını peek `string`.

1. Herhangi bir örneğinde sağ `string` ve seçin **Peek tanımı** içerik menüsünden&mdash;veya basın **Alt**+**F12**.

   Tanımını bir açılır pencere görünür `String` sınıfı. Açılır pencere veya başka bir tür peeked kodundan tanımını bile bilgi içinde gezinebilirsiniz.

   ![Peek tanımı penceresi](media/quickstart-peek-definition.png)

1. Sağ üst köşedeki "x" açılır pencere yer aldığı küçük kutuyu seçerek Aranan tanımı penceresini kapatın.

## <a name="using-intellisense-to-complete-words"></a>Sözcükler tamamlamak için IntelliSense kullanma

[IntelliSense](../ide/using-intellisense.md) kodlama bir çok kaynağıdır. Bir tür ya da farklı bir yöntem aşırı parametre ayrıntılarını kullanılabilir üyeler hakkında bilgi gösterebilirsiniz. IntelliSense, onu belirsizliğini ortadan kaldırmak için yeterli sayıda karakter yazdıktan sonra bir sözcük tamamlamak için de kullanabilirsiniz. Bir konsol penceresi sıralı dizelere yazdırmak için kod satırı ekleyelim.

1. Aşağıda `query` değişken, başlangıç aşağıdaki kodu yazın:

   ```csharp
   foreach (string str in qu
   ```

   IntelliSense, Göster gördüğünüz **hızlı bilgi** hakkında `query` simgesi.

   ![IntelliSense word tamamlandı](media/quickstart-intellisense-completion-list.png)

1. Kalan sözcüğün eklemek için `query` IntelliSense'nın "Tam sözcüğü" işlevini kullanarak basın **sekmesini**.

1. Aşağıdaki kod gibi aramak için kod bloğu kapalı tamamlayın. Kod parçacıkları girerek kullanarak yeniden bile alıştırma yapabilirsiniz `cw` ve tuşuna basarak **sekmesini** iki kez oluşturmak için `Console.WriteLine` kodu.

   ```csharp
   foreach (string str in query)
   {
      Console.WriteLine(str);
   }
   ```

## <a name="refactoring-a-name"></a>Bir ad yeniden düzenleme

Kimse ilk kez kod sağ alır ve birini değiştirmek isteyebilirsiniz değişken veya yöntem adıdır. Visual Studio'nun deneyelim [yeniden düzenleme](../ide/refactoring-in-visual-studio.md) yeniden adlandırmak için işlevselliği `_words` değişkenini `words`.

1. İmlecinizi tanımı yerleştirin `words` değişkeni ve seçin **yeniden adlandır...**  sağ tıklatın veya bağlam menüsünden veya tuşuna **Ctrl**+**R**, **Ctrl**+**R**.

   Açılır pencere **yeniden adlandırma** iletişim kutusu görünür en üstünde sağ düzenleyicinin.

1. İstediğiniz adı girin `words`. Dikkat referansı `words` sorguda da otomatik olarak yeniden adlandırıldı. Tuşuna önce **Enter**seçin **dahil açıklamaları** onay kutusu **yeniden adlandırma** açılan kutusu.

   ![Yeniden Adlandır iletişim kutusu](media/quickstart-rename.png)

1. Tuşuna **girin**.

   Her iki oluşumları `words` , başvuru yanı sıra yeniden adlandırıldığı `words` kodu açıklama.

## <a name="next-steps"></a>Sonraki adımlar

Bu Hızlı Başlangıç için Visual Studio düzenleyicisinde tamamladınız! Sonraki bazı diğer quickstarts Visual Studio IDE için arama daha fazla yollardan deneyebilecekleriniz [kodda gezinme](../ide/navigating-code.md), veya biz arama sırasında özellikleri hakkında daha fazla bilgi için bağlantıları gözden geçirin. Aksi takdirde mutluluk kodlama!

## <a name="see-also"></a>Ayrıca bkz.

- [Hızlı Başlangıç: Visual Studio IDE ilk bakış](../ide/quickstart-ide-orientation.md)
- [Hızlı Başlangıç: Düzenleyicisi ve Visual Studio IDE'yi kişiselleştirme](../ide/quickstart-personalize-the-ide.md)
- [Hızlı Başlangıç: Projeler ve çözümler](../ide/quickstart-projects-solutions.md)
- [Kod parçacıkları](../ide/code-snippets.md)
- [Anahat Oluşturma](../ide/outlining.md)
- [Tanıma ve Özet Tanıma Gitme](../ide/go-to-and-peek-definition.md)
- [Yeniden Düzenleme](../ide/refactoring-in-visual-studio.md)
- [IntelliSense Kullanma](../ide/using-intellisense.md)
