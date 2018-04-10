---
title: C# kod parçacıkları | Microsoft Docs
ms.custom: ''
ms.date: 06/05/2017
ms.reviewer: ''
ms.suite: ''
ms.technology: vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- snippets [C#]
- code snippets [C#]
- Code Snippet Inserter [C#]
- C#, code snippets
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 0328ceb6c1420b038ca424c42dd408e36da6f891
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="c-code-snippets"></a>C# kod parçacıkları

Kod parçacıkları, kodunuza hızla ekleyebilirsiniz kodunun hazır parçacıklarıdır. Örneğin, `for` kod parçacığını oluşturur boş bir `for` döngü. Bazı kod parçacıkları, kod satırlarını seçmenizi sağlar ve ardından kod seçili satırları içeren bir kod parçacığı Çevrele kod parçacıklarını, ' dir. Örneğin, ne zaman, kod satırı seçin ve ardından etkinleştirmeniz `for` kod parçacığını oluşturduğu bir `for` döngü Bu döngü bloğunun kod satırları ile. Kod parçacıkları daha hızlı, kolay ve daha güvenilir kod yazma programını yapabilirsiniz.

 Kod parçacığı İmleç konumuna Ekle veya şu anda seçili kodu geçici Çevrele kod parçacığı Ekle. Kod parçacığı ekleyici aracılığıyla çağrılır **kod parçacığını ekleyin** veya **Surround With** komutlarını **IntelliSense** menüsünde veya klavyekısayollarınıkullanma **CTRL**+**K**,**X** veya **Ctrl**+**K**,**S** sırasıyla.

 Kod parçacığı ekleyici tüm kullanılabilir kod parçacıkları kod parçacığını adını görüntüler. Kod parçacığı ekleyici kod parçacığını veya kod parçacığını ad parçasını adını yazabileceğiniz bir giriş iletişim kutusu da içerir. Kod parçacığı ekleyici bir kod parçacığını ad yakın eşleşmeyi vurgular. Tuşuna basarak **sekmesini** herhangi bir zamanda kod parçacığı ekleyici yok sayın ve şu anda seçili kod parçacığını ekleyin. Tuşuna basarak **Esc** veya Kod Düzenleyicisi'nde fareyi tıklatarak kapatmak kod parçacığı ekleyici bir kod parçacığı eklemeden.

## <a name="default-code-snippets"></a>Varsayılan kod parçacıkları

Varsayılan olarak aşağıdaki kod parçacıkları Visual Studio'da C# ' ta dahil edilir.

|Adı (veya kısayol)|Açıklama|Kod parçacığında eklemek için geçerli konumlar|
|--------------------------|-----------------|---------------------------------------|
|#if|Oluşturur bir [#if](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-if) yönergesi ve [#endif](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-endif) yönergesi.|Herhangi bir yere.|
|#region|Oluşturur bir [#region](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-region) yönergesi ve [#endregion](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-endregion) yönergesi.|Herhangi bir yere.|
|~|Oluşturur bir [sonlandırıcıyı](/dotnet/csharp/programming-guide/classes-and-structs/destructors) (yok edici) içeren sınıf.|Bir sınıf içinde.|
|özniteliği|Öğesinden türeyen bir sınıf için bir bildirim oluşturur <xref:System.Attribute>.|(Genel ad alanı dahil) bir ad alanı, bir sınıf veya yapı içinde.|
|checked|Oluşturur bir [işaretli](/dotnet/csharp/language-reference/keywords/checked) bloğu.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|
|sınıf|Sınıf bildirimi oluşturur.|(Genel ad alanı dahil) bir ad alanı, bir sınıf veya yapı içinde.|
|ctor|İçeren sınıf için bir oluşturucu oluşturur.|Bir sınıf içinde.|
|cw|Çağrı oluşturur <xref:System.Console.WriteLine%2A>.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|
|do|Oluşturur bir [yapmak](/dotnet/csharp/language-reference/keywords/do) `while` döngü.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|
|else|Oluşturur bir [başka](/dotnet/csharp/language-reference/keywords/if-else) bloğu.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|
|enum|Oluşturur bir [enum](/dotnet/csharp/language-reference/keywords/enum) bildirimi.|(Genel ad alanı dahil) bir ad alanı, bir sınıf veya yapı içinde.|
|eşittir|Geçersiz kılan bir yöntem bildirimi oluşturur <xref:System.Object.Equals%2A> tanımlanmış yöntemini <xref:System.Object> sınıfı.|Bir sınıf veya yapı içinde.|
|Özel durumu|Bir özel durum türeyen bir sınıf için bir bildirim oluşturur (<xref:System.Exception> varsayılan olarak).|(Genel ad alanı dahil) bir ad alanı, bir sınıf veya yapı içinde.|
|for|Oluşturur bir [için](/dotnet/csharp/language-reference/keywords/for) döngü.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|
|foreach|Oluşturur bir [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) döngü.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|
|forr|Oluşturur bir [için](/dotnet/csharp/language-reference/keywords/for) bu azaltır Döngü değişkeninin her yinelemeden sonra döngü.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|
|if|Oluşturur bir [varsa](/dotnet/csharp/language-reference/keywords/if-else) bloğu.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|
|Dizin Oluşturucu|Bir dizin oluşturucu bildirimi oluşturur.|Bir sınıf veya yapı içinde.|
|arabirim|Oluşturur bir [arabirimi](/dotnet/csharp/language-reference/keywords/interface) bildirimi.|(Genel ad alanı dahil) bir ad alanı, bir sınıf veya yapı içinde.|
|Çağırma|Bir olay güvenle çağıran bir blok oluşturur.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|
|iterator|Yineleyici oluşturur.|Bir sınıf veya yapı içinde.|
|iterindex|İç içe geçmiş sınıf kullanarak bir "adlı" Yineleyici ve dizin oluşturucu çifti oluşturur.|Bir sınıf veya yapı içinde.|
|lock|Oluşturur bir [kilit](/dotnet/csharp/language-reference/keywords/lock-statement) bloğu.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|
|mbox|Çağrı oluşturur <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName>. System.Windows.Forms.dll'e bir başvuru eklemeniz gerekebilir.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|
|ad alanı|Oluşturur bir [ad alanı](/dotnet/csharp/language-reference/keywords/namespace) bildirimi.|(Genel ad alanı dahil) bir ad alanı içinde.|
|prop|Oluşturur bir [otomatik uygulanan özellik](/dotnet/csharp/programming-guide/classes-and-structs/auto-implemented-properties) bildirimi.|Bir sınıf veya yapı içinde.|
|propfull|Özellik bildirimi ile oluşturur `get` ve `set` erişimciler.|Bir sınıf veya yapı içinde.|
|propg|Salt okunur oluşturur [otomatik uygulanan özelliği](/dotnet/csharp/programming-guide/classes-and-structs/auto-implemented-properties) özel ile `set` erişimcisi.|Bir sınıf veya yapı içinde.|
|SIM|Oluşturur bir [statik](/dotnet/csharp/language-reference/keywords/static) [int](/dotnet/csharp/language-reference/keywords/int) ana yöntem bildirimi.|Bir sınıf veya yapı içinde.|
|struct |Oluşturur bir [yapısı](/dotnet/csharp/language-reference/keywords/struct) bildirimi.|(Genel ad alanı dahil) bir ad alanı, bir sınıf veya yapı içinde.|
|svm|Oluşturur bir [statik](/dotnet/csharp/language-reference/keywords/static) [void](/dotnet/csharp/language-reference/keywords/void) ana yöntem bildirimi.|Bir sınıf veya yapı içinde.|
|anahtarı|Oluşturur bir [geçiş](/dotnet/csharp/language-reference/keywords/switch) bloğu.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|
|Deneyin|Oluşturur bir [try-catch](/dotnet/csharp/language-reference/keywords/try-catch) bloğu.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|
|tryf|Oluşturur bir [try-finally](/dotnet/csharp/language-reference/keywords/try-finally) bloğu.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|
|unchecked|Oluşturur bir [denetlenmeyen](/dotnet/csharp/language-reference/keywords/unchecked) bloğu.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|
|unsafe|Oluşturur bir [güvensiz](/dotnet/csharp/language-reference/keywords/unsafe) bloğu.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|
|kullanma|Oluşturur bir [kullanarak](/dotnet/csharp/language-reference/keywords/using-directive) yönergesi.|(Genel ad alanı dahil) bir ad alanı içinde.|
|while|Oluşturur bir [sırada](/dotnet/csharp/language-reference/keywords/while) döngü.|Bir yöntemi, bir dizin oluşturucu, bir özellik erişimcisini veya bir olay erişimci içinde.|

## <a name="see-also"></a>Ayrıca bkz.

[Kod Parçacığı İşlevleri](../ide/code-snippet-functions.md)  
[Kod Parçacıkları](../ide/code-snippets.md)  
[Şablon Parametreleri](../ide/template-parameters.md)  
[Nasıl Yapılır: Şununla Çevrele Kod Parçacıklarını Kullanma](../ide/how-to-use-surround-with-code-snippets.md)
