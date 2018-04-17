---
title: Visual Studio'daki XML belge açıklamaları ekleme | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 0fae2411a77f405404e34c7a2357554c1e5398ab
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-insert-xml-comments-for-documentation-generation"></a>Nasıl yapılır: ekleme belgeleri oluşturma için XML açıklamaları

Visual Studio size yardımcı olabilir belge kod öğeleri sınıflar ve yöntemler, gibi otomatik olarak standart XML belgeleri yorum yapısı oluşturarak. Derleme zamanında belge açıklamaları içeren bir XML dosyası oluşturabilirsiniz. Visual Studio ve diğer IDE IntelliSense türleri ve üyeleri hakkında hızlı bilgi göstermek için kullanabilmesi için derleyicinin ürettiği XML dosyası yanı sıra, .NET derleme dağıtılabilir. Ayrıca, XML dosyası gibi araçlar aracılığıyla çalıştırılabilir [DocFX](https://dotnet.github.io/docfx/) ve [Sandcastle](https://www.microsoft.com/download/details.aspx?id=10526) API başvuru Web siteleri oluşturmak için.

> [!NOTE]
> **Açıklama Ekle** XML belgeleri yorumları otomatik olarak ekler komutu, içinde kullanılabilir [C#](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments) ve [Visual Basic](/dotnet/visual-basic/programming-guide/program-structure/how-to-create-xml-documentation). Ancak, el ile ekleyebilirsiniz [c++ XML belgeleri yorumları](/cpp/ide/xml-documentation-visual-cpp) dosyaları ve hala derleme zamanında XML belge dosyalarını oluşturur.

## <a name="to-insert-xml-comments-for-a-code-element"></a>Kod öğesi için XML açıklamaları eklemek için

1. Metin imlecinizi belge, örneğin, bir yöntem istediğiniz öğenin üstüne getirin.

1. Aşağıdakilerden birini yapın:

   - Tür `///` C# veya `'''` Visual Basic'te

   - Gelen **Düzenle** menüsünde seçin **IntelliSense** > **Açıklama Ekle**

   - Sağ tıklatın veya bağlam menüsünden veya yalnızca code öğesi üstü seçin **parçacığı** > **Açıklama Ekle**

   XML şablonu hemen kod öğenin üstüne oluşturulur. Örneğin, bir yöntem yorum, ürettiği **\<Özet\>** öğesi, bir **\<param\>** öğesi her bir parametreyi ve bir için**\<döndürür\>** dönüş değeri belge öğesi.

   ![XML açıklama şablon - C#](media/doc-preview-cs.png)

   ![XML açıklama şablon - Visual Basic](media/doc-preview-vb.png)

1. Kod öğesi tam olarak belgelemek her bir XML öğesi için açıklamalar girin.

   ![Tamamlanan açıklama](media/doc-result-cs.png)

> [!NOTE]
> Var olan bir [seçeneği](../../ide/reference/options-text-editor-csharp-advanced.md) yazdıktan sonra geçiş XML belge açıklamaları için `///` C# veya `'''` Visual Basic. Menü çubuğundan seçin **Araçları** > **seçenekleri** açmak için **seçenekleri** iletişim kutusu. Ardından, gidin **metin düzenleyici** > **C#** veya **temel** > **Gelişmiş**. İçinde **Düzenleyicisi Yardımı** bölümünde, Ara **oluşturmak XML belgeleri yorumları** seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[XML belgeleri yorumları (C# programlama Kılavuzu)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)  
[XML açıklamaları (C# Kılavuzu) ile kodunuzu belgeleme](/dotnet/csharp/codedoc)  
[Nasıl yapılır: XML belgeleri (Visual Basic) oluşturun](/dotnet/visual-basic/programming-guide/program-structure/how-to-create-xml-documentation)  
[C++ açıklamaları](/cpp/cpp/comments-cpp)  
[XML belgeleri (C++)](/cpp/ide/xml-documentation-visual-cpp)  
[Kod oluşturma](../code-generation-in-visual-studio.md)
