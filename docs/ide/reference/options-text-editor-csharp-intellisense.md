---
title: "Seçenekler, metin düzenleyici, C#, IntelliSense | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Intellisense
- VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Intellisense
helpviewer_keywords:
- underlines, wavy
- IntelliSense [C#], options
- IntelliSense [C#], wavy underlines
- wavy underlines
- Text Editor Options dialog box, IntelliSense
ms.assetid: 3466dedb-e5f4-424c-8dd8-e4941b2f4fc2
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ba6e1613410c8143126254c8f7a4bd325c6e6f22
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2017
---
# <a name="options-text-editor-c-intellisense"></a>Seçenekler, Metin Düzenleyici, C#, IntelliSense
Kullanım **IntelliSense** IntelliSense davranışını Visual C# için etkileyen ayarları değiştirmek için özellik sayfası. Erişebileceğiniz **IntelliSense** tıklayarak özellik sayfası **seçenekleri** üzerinde **Araçları** tıklatarak menüsünde **C#** içinde**Metin düzenleyici** klasörünü ve ardından **IntelliSense.**  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).  
  
 **IntelliSense** özellik sayfası, aşağıdaki özellikleri içerir:  
  
## <a name="completion-lists"></a>Tamamlanma listeleri  
 **Bir karakter yazıldıktan sonra tamamlanma listesi göster**  
 Bu seçenek belirlendiğinde, yazmaya başladığınızda, IntelliSense otomatik olarak tamamlanma listesi görüntüler. Bu seçenek belirlenmediğinde, IntelliSense tamamlanma hala kullanılabilir **IntelliSense** menüsü veya CTRL + ARA ÇUBUĞU tuşlarına basarak.  
  
 **Tamamlanma listeleri yer anahtar sözcükler**  
 Bu seçenek belirlendiğinde, IntelliSense C# anahtar sözcükleri, örneğin, ekler [sınıfı](/dotnet/csharp/language-reference/keywords/class), tamamlanma listesi.  
  
 **Kod parçacıkları detamamlanma listeleri yerleştirin**  
 Bu seçenek belirlendiğinde, IntelliSense, C# kod parçacıkları için diğer adlar tamamlama listesine ekler. Kod parçacığı diğer olduğu bir anahtar sözcüğü ile aynı örneğin durumda [sınıfı](/dotnet/csharp/language-reference/keywords/class), anahtar sözcüğü kısayol tarafından değiştirilir. Daha fazla bilgi için bkz: [Visual C# kod parçacıkları](../../ide/visual-csharp-code-snippets.md).  
  
## <a name="selection-in-completion-lists"></a>Tamamlanma listeleri seçimi  
 **Şu karakterleri yazarak yürütüldü:**  
 Bunlar yazılan sonra tamamlama listesinde seçili öğe için IntelliSense otomatik tamamlama yürütme tüm karakter belirtir.  
  
 **Ara çubuğu tuşlarına basarak yürütüldü**  
 Tamamlanma listesinde seçili öğe için IntelliSense otomatik tamamlama yürütmek için Ara çubuğu tuşlarına eylemi dahil edilmesi gerektiğini belirtir.  
  
 **Yeni Satır Ekle üzerinde tam olarak yazılan word sonunda girin**  
 Tamamlanma listesinde bir girişi tüm karakterleri yazın ve ENTER tuşuna basın, yeni bir satır otomatik olarak oluşturulur ve yeni satır imleci taşır belirtir.  
  
 Örneğin, `else` ve aşağıdaki Düzenleyicisi'nde görüntülenen ENTER tuşuna basın:  
  
 `else`  
  
 `|`(imleç konumu)  
  
 Ancak, yalnızca yazarsanız `el` ve aşağıdaki Düzenleyicisi'nde görüntülenen ENTER tuşuna basın:  
  
 `else|`(imleç konumu)  
  
## <a name="intellisense-member-selection"></a>IntelliSense üye seçimi  
 **Ön seçer üye Son Kullanılanlar**  
 Bu seçenek belirlendiğinde, IntelliSense, son otomatik nesne adı tamamlanırken, tümleşik geliştirme ortamı (IDE) geçerli oturumunda açılır listesi üyeleri kutusunda seçtiğiniz üyeleri önceden seçer. En son kullanılan üyeler geçmişini IDE içinde her oturum arasında temizlenir. Daha fazla bilgi için bkz: [son kullanılan üyeler için IntelliSense](../../ide/visual-csharp-intellisense.md#most-recently-used-members).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel, ortam, Seçenekler iletişim kutusu](../../ide/reference/general-environment-options-dialog-box.md)   
 [XML belgeleri yorumları](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)   
 [IntelliSense Kullanma](../../ide/using-intellisense.md)