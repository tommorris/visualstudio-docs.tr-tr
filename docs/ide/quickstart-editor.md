---
title: Visual Studio'da düzenleme giriş
ms.date: 11/30/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 29768717144efef9c843abb5e0e3e6e81817895d
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35255729"
---
# <a name="quickstart-use-the-code-editor"></a>Hızlı Başlangıç: Kod Düzenleyicisi'ni kullanın

Bu 10 dakikalık girişte düzenleyiciye, Visual Studio yazma, gezinme ve kodu daha kolay anlama yapar yollardan bazılarını aramak için bir dosya için kod ekleyeceğiz.

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

Bu hızlı başlangıç bir programlama dili ile bilginiz varsayar. Yoksa, önerdiğimiz programlama quickstarts birini ilk bakış, gibi bir web uygulaması ile oluşturma [Python](../ide/quickstart-python.md) veya [C#](../ide/tutorial-csharp-aspnet-core.md), veya bir konsol uygulaması ile oluşturma [Visual Basic](../ide/quickstart-visual-basic-console.md) veya [C++](../ide/getting-started-with-cpp-in-visual-studio.md).

## <a name="create-a-new-code-file"></a>Yeni bir kod dosyası oluşturma

Yeni bir dosya oluşturarak ve biraz kod eklemeyi başlatın. Biz Düzenleyici sunar avantajlarından bazıları kazanmak için bir proje oluşturmak zorunda değilsiniz dikkat edin.

1. Visual Studio'yu açın ve **dosya** menü çubuğundaki menüsü seçin **yeni** > **dosya**.

1. İçinde **yeni dosya** iletişim kutusunda **genel** kategorisi seçin **Visual C# sınıfı**ve ardından **açık**.

   Yeni bir dosya bir C# sınıfı çatıyı düzenleyicisiyle açar.

## <a name="use-code-snippets"></a>Kod parçacıkları kullanma

Visual Studio hızla ve kolayca yaygın olarak oluşturmak için kullanabileceğiniz yararlı kod parçacıkları kod blokları kullanılan sağlar. [Kod parçacıkları](../ide/code-snippets.md) C#, Visual Basic ve C++ gibi farklı programlama dilleri için kullanılabilir. C# ekleyelim `void Main` bizim dosyasına parçacığı.

1. İmlecinizi kapanış ayracı altına yerleştirin `Class1` oluşturucusu ve karakterleri girin `svm`.

   Gördüğünüz bir **IntelliSense** hakkında iletişim kutusu görünür bilgilerle `svm` parçacığı.

   ![IntelliSense kod parçacığında](media/quickstart-intellisense-snippet.png)

1. Tuşuna **sekmesini** iki kez kod parçacığını eklemek için.

   Gördüğünüz `static void Main()` yöntem imzası dosyasına eklenen. `Main()` C# uygulamaları için giriş noktası bir yöntemdir.

Kullanılabilir kod parçacıkları farklı diller için farklılık gösterir. Seçerek programlama diliniz için kullanılabilir kod parçacıkları bakabilirsiniz **Düzenle** > **IntelliSense** > **Ekle parçacığı**, ve ardından, dil klasörünü seçme. C# ' ta listesi şu şekildedir:

![C# kod parçacığı listesi](media/quickstart-code-snippet-list.png)

Bir sınıf, bir oluşturucu oluşturmak için parçacıkları listesi içerir `Console.WriteLine()`, `for` döngüler, `if` ve `switch` deyimleri ve daha fazlası.

## <a name="comment-out-code"></a>Kodu açıklama

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

## <a name="collapse-code-blocks"></a>Kod blokları Daralt

Biz boş Oluşturucusu görmek istemediğiniz `Class1` üretilen, böylece kodu bizim görünümünü sekmenize Düzen vermenize, şimdi onu daraltmak için. Küçük bir gri kutu içindeki eksi işaretiyle Oluşturucusu ilk satırının kenar boşluğunda seçin. Ya da klavye kullanıcısıysanız imleci herhangi bir yere Oluşturucusu kod ve tuşuna koyun **Ctrl**+**M**, **Ctrl**+**M** .

![Daralt düğmesi anahat oluşturma](media/quickstart-collapse.png)

Üç nokta ve ardından yalnızca ilk satırı, kod bloğunu daraltır (`...`). Kod bloğunu yeniden genişletmek için şimdi bir artı işareti veya tuşlarına basın aynı gri kutusunda tıklatın **Ctrl**+**M**, **Ctrl**+**M**  yeniden. Bu özellik adında [anahat](../ide/outlining.md) ve uzun yöntemleri ya da tüm sınıflar daraltma özellikle yararlıdır.

## <a name="view-symbol-definitions"></a>Görünüm sembol tanımları

Visual Studio düzenleyicisinde bir tür, yöntem, vb. tanımını incelemek kolaylaştırır. Tanımı, örneğin seçerek içeren dosyayı gitmek için tek yönlü olduğu **Tanıma Git** simgenin herhangi bir yere başvuruluyor. İçinde çalışırken odağınız uzağa doğru dosya taşınmaz bir bile daha hızlı yolu kullanmaktır [Peek tanımı](../ide/go-to-and-peek-definition.md#peek-definition). Şimdi tanımını peek `string`.

1. Herhangi bir örneğinde sağ `string` ve seçin **Peek tanımı** içerik menüsünden&mdash;veya basın **Alt**+**F12**.

   Tanımını bir açılır pencere görünür `String` sınıfı. Açılır pencere veya başka bir tür peeked kodundan tanımını bile bilgi içinde gezinebilirsiniz.

   ![Peek tanımı penceresi](media/quickstart-peek-definition.png)

1. Sağ üst köşedeki "x" açılır pencere yer aldığı küçük kutuyu seçerek Aranan tanımı penceresini kapatın.

## <a name="use-intellisense-to-complete-words"></a>Sözcükler tamamlamak için IntelliSense kullanma

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

## <a name="refactor-a-name"></a>Bir ad yeniden Düzenle

Kimse ilk kez kod sağ alır ve birini değiştirmek isteyebilirsiniz değişken veya yöntem adıdır. Visual Studio'nun deneyelim [düzenleme](../ide/refactoring-in-visual-studio.md) yeniden adlandırmak için işlevselliği `_words` değişkenini `words`.

1. İmlecinizi tanımı yerleştirin `words` değişkeni ve seçin **yeniden adlandırma** sağ tıklatın veya bağlam menüsünden veya tuşuna **Ctrl**+**R**, **Ctrl**+**R**.

   Açılır pencere **yeniden adlandırma** iletişim kutusu görünür en üstünde sağ düzenleyicinin.

1. İstediğiniz adı girin `words`. Dikkat referansı `words` sorguda da otomatik olarak yeniden adlandırıldı. Tuşuna önce **Enter**seçin **dahil açıklamaları** onay kutusu **yeniden adlandırma** açılan kutusu.

   ![Yeniden Adlandır iletişim kutusu](media/quickstart-rename.png)

1. Tuşuna **girin**.

   Her iki oluşumları `words` , başvuru yanı sıra yeniden adlandırıldığı `words` kodu açıklama.

## <a name="next-steps"></a>Sonraki adımlar

Bu Hızlı Başlangıç için Visual Studio düzenleyicisinde tamamladınız! Sonraki bazı diğer Quickstarts Visual Studio IDE için arama için daha fazla yolunu adresindeki deneyebilecekleriniz [kod gidin](../ide/navigating-code.md), veya biz arama sırasında özellikleri hakkında daha fazla bilgi için bağlantıları gözden geçirin. Aksi takdirde mutluluk kodlama!

## <a name="see-also"></a>Ayrıca bkz.

- [Hızlı Başlangıç: Visual Studio IDE ilk bakış](../ide/quickstart-ide-orientation.md)
- [Hızlı Başlangıç: Düzenleyicisi ve Visual Studio IDE'yi kişiselleştirme](../ide/quickstart-personalize-the-ide.md)
- [Hızlı Başlangıç: Projeler ve çözümler](../ide/quickstart-projects-solutions.md)
- [Kod parçacıkları](../ide/code-snippets.md)
- [Anahat Oluşturma](../ide/outlining.md)
- [Tanıma ve Özet Tanıma Gitme](../ide/go-to-and-peek-definition.md)
- [Yeniden Düzenleme](../ide/refactoring-in-visual-studio.md)
- [IntelliSense kullanma](../ide/using-intellisense.md)
