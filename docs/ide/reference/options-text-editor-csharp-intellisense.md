---
title: Seçenekler, metin düzenleyici, C#, IntelliSense | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Intellisense
helpviewer_keywords:
- underlines, wavy
- IntelliSense [C#], options
- IntelliSense [C#], wavy underlines
- wavy underlines
- Text Editor Options dialog box, IntelliSense
ms.assetid: 3466dedb-e5f4-424c-8dd8-e4941b2f4fc2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 37640cd6bd2928a2e2261afb3ed9e859830d0225
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="options-text-editor-c-intellisense"></a>Seçenekler, Metin Düzenleyici, C#, IntelliSense

Kullanım **IntelliSense** davranışı IntelliSense, C# ' ta etkileyen ayarları değiştirmek için seçenekler sayfası. Bu seçenekler sayfası erişmek için kendi seçtikleri **Araçları** > **seçenekleri**ve ardından **metin düzenleyici** > **C#**  >  **IntelliSense**.

> [!NOTE]
> Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).

**IntelliSense** seçenekleri sayfasında aşağıdaki seçenekleri içerir:

## <a name="completion-lists"></a>Tamamlanma listeleri

- Bir karakter yazıldıktan sonra tamamlanma listesi göster *

   Bu seçenek belirlendiğinde, yazmaya başladığınızda, IntelliSense otomatik olarak tamamlanma listesi görüntüler. Bu seçenek belirlenmediğinde, IntelliSense tamamlanma hala kullanılabilir **IntelliSense** menü basarak veya **Ctrl**+**alanı**.

- Bir karakter silindikten sonra tamamlanma listesi göster

- Tamamlanma listesi öğeleri eşleşen bölümlerini vurgulayın

- Tamamlanma listesi filtrelerini göster

- Ad önerilerini göster

### <a name="snippets-behavior"></a>Kod parçacıkları davranışı

- Hiçbir zaman parçacıkları içerir

   Bu seçenek belirlendiğinde, IntelliSense tamamlanma listesi hiçbir zaman C# kod parçacıkları için diğer adlar ekler.

- Her zaman parçacıkları ekleyin

   Bu seçenek belirlendiğinde, IntelliSense, C# kod parçacıkları için diğer adlar tamamlama listesine ekler. Kod parçacığı diğer olduğu bir anahtar sözcüğü ile aynı örneğin durumda [sınıfı](/dotnet/csharp/language-reference/keywords/class), anahtar sözcüğü kısayol tarafından değiştirilir. Daha fazla bilgi için bkz: [C# kod parçacıkları](../../ide/visual-csharp-code-snippets.md).

- Parçaları içeren zaman?-sekmesini sonra bir tanımlayıcı türü

   Bu seçenek belirlendiğinde, diğer adlar için C# kod parçacıkları tamamlanması için IntelliSense ekler ne zaman listesinde **?** + **Sekmesini** sonra bir tanımlayıcı basıldığında

### <a name="enter-key-behavior"></a>Anahtar davranışı girin

- Hiç yeni satır Ekle üzerinde girin

   Yeni bir satır hiçbir zaman otomatik olarak bir öğe tamamlama listesinde seçerek ve basarak sonra eklendiğini belirtir **Enter**.

- Yalnızca yeni satır Ekle üzerinde tam olarak yazılan word sonunda girin

   Tamamlanma listesinde bir girişi tüm karakterleri yazın ve ENTER tuşuna basın belirleyen **Enter**, yeni bir satır otomatik olarak eklenir ve yeni satır imleci taşır.

   Örneğin, `else` ve tuşuna basarak **Enter**, aşağıdaki Düzenleyicisi'nde görüntülenir:

   `else`

   `|` (imleç konumu)

   Ancak, yalnızca yazarsanız `el` ve tuşuna basarak **Enter**, aşağıdaki Düzenleyicisi'nde görüntülenir:

   `else|` (imleç konumu)

- Her zaman yeni bir satır ekleyin üzerinde girin

   Yazarsanız belirleyen *herhangi* ENTER tuşuna basın ve tamamlanma listesi bir girişi karakterlerin **Enter**, yeni bir satır otomatik olarak eklenir ve yeni satır imleci taşır.

## <a name="see-also"></a>Ayrıca bkz.

[Genel, ortam, Seçenekler iletişim kutusu](../../ide/reference/general-environment-options-dialog-box.md)  
[IntelliSense Kullanma](../../ide/using-intellisense.md)