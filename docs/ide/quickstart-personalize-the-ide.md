---
title: Renk temasını ve yazı tipleri Visual Studio'da ayarlayın
ms.date: 11/20/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 326da0003e73c78a17df489473b49cf6d7b62380
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35255421"
---
# <a name="quickstart-personalize-the-visual-studio-ide-and-editor"></a>Hızlı Başlangıç: Visual Studio IDE ve düzenleyici kişiselleştirme

Bu 5-10 dakika quickstart Biz Visual Studio renk temasını ve iki metin renkleri özelleştirme **metin düzenleyici**.

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

## <a name="set-the-color-theme"></a>Renk temasını ayarlayın

Visual Studio 2017 için varsayılan renk temasını adlı **mavi**. Kendisine değiştirelim **koyu**.

1. Menü çubuğunda seçin **Araçları** > **seçenekleri**.

1. Üzerinde **ortam** > **genel** seçenekler sayfası, değişiklik **renk temasını** seçimi **koyu**ve ardından seçin **Tamam**.

   Tüm IDE renk temasını değiştirilir **koyu**.

   ![VS koyu tema içinde](media/quickstart-personalize-dark-theme.png)

> [!TIP]
> Yükleyerek önceden tanımlanmış ek temalar yükleyebilirsiniz **Visual Studio renkli tema Düzenleyicisi** gelen [Visual Studio Market'te](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.VisualStudio2017ColorThemeEditor). Bu aracı yükledikten sonra ek renk temaları görünür **renk temasını** aşağı açılan liste.

## <a name="change-text-color"></a>Metin rengi değiştirme

Şimdi biz bazı metin renkleri Düzenleyicisi özelleştirmek. İlk olarak, varsayılan renkleri görmek için bir XML dosyası açalım.

1. Menü çubuğundan seçin **dosya** > **yeni** > **dosya**.

1. İçinde **yeni dosya** iletişim kutusunda **genel** kategorisi seçin **XML dosyası**ve ardından **açık**.

1. Aşağıdaki XML içeren satırı altına yapıştırın `<?xml version="1.0" encoding="utf-8"?>`.

   ```xml
   <Catalog>
     <Book id="bk101">
     <Author>Garghentini, Davide</Author>
     <Title>XML Developer's Guide</Title>
     <Genre>Computer</Genre>
     <Price>44.95</Price>
     <PublishDate>2000-10-01</PublishDate>
     <Description>
       An in-depth look at creating applications with XML.
     </Description>
   </Book>
   <Book id="bk102">
     <Author>Garcia, Debra</Author>
     <Title>Midnight Rain</Title>
     <Genre>Fantasy</Genre>
     <Price>5.95</Price>
     <PublishDate>2000-12-16</PublishDate>
     <Description>
       A former architect battles corporate zombies, an evil
       sorceress, and her own childhood to become queen of the world.
     </Description>
   </Book>
   </Catalog>
   ```

   Satır numaralarını Turkuaz mavi bir renk, ve XML öznitelikleri açık bir mavi renk olduğundan dikkat edin. Bu öğeler metin rengini değiştirmek olacak.

   ![XML dosyası yazı tipi rengi](media/quickstart-personalize-xml-file.png)

1. Açmak için **seçenekleri** iletişim kutusunda, seçin **Araçları** > **seçenekleri** menü çubuğundan.

1. Altında **ortam**, seçin **yazı tiplerini ve renkleri** kategorisi.

   Dikkat altındaki metin **ayarlarını göster** diyor **metin düzenleyici**&mdash;ne istiyoruz budur. Yalnızca Burada yazı tipleri ve metin rengi özelleştirebilirsiniz yerler kapsamlı listesini görmek için açılan listeyi genişletin.

1. Satır numaraları metnin rengini değiştirmek için **görüntülemek öğeleri** listesinde, seçin **satır numarası**. İçinde **öğesi ön plan** kutusunda, seçin **Zeytin**.

   ![Seçenekler iletişim kutusu, yazı tipleri ve renkler kategorisi](media/quickstart-personalize-line-number-color.png)

   Bazı diller kendi belirli yazı tiplerini ve renkleri ayarlara sahip. C++ Geliştirici misiniz ve işlevleri için kullanılan renk değiştirmek isterseniz, örneğin, arayabileceğiniz **C++ işlevlerini** içinde **görüntülemek öğeleri** listesi.

1. Biz dışında iletişim kutusundan çıkmak önce de XML öznitelikleri rengini değiştirelim. İçinde **görüntülemek öğeleri** listesinde, aşağı kaydırarak **XML özniteliği** ve seçin. İçinde **öğesi ön plan** kutusunda, seçin **açık yeşil**. Seçin **Tamam** bizim seçimlerini kaydetmek ve iletişim kutusunu kapatın.

   Satır numaralarını Zeytin renkli sunulmuştur ve XML öznitelikleri açık, Limon Sarısı yeşil. Bir C++ veya C# kod dosyası gibi başka bir dosya türü açarsanız satır numaralarını da Zeytin rengi görünür görürsünüz.

   ![Yeni yazı tipi renkleri olan XML dosyası](media/quickstart-personalize-xml-file-new-colors.png)

Biz, Visual Studio renkleri özelleştirme yalnızca birkaç yolla incelediniz. Diğer özelleştirme seçeneklerinde incelenecektir umuyoruz **seçenekleri** gerçekten Visual Studio kendi yapmak için iletişim kutusu.

## <a name="see-also"></a>Ayrıca bkz.

- [Hızlı Başlangıç: Visual Studio IDE ilk bakış](../ide/quickstart-ide-orientation.md)
- [Hızlı Başlangıç: düzenleyicide kodlama](../ide/quickstart-editor.md)
- [Hızlı Başlangıç: Projeler ve çözümler](../ide/quickstart-projects-solutions.md)
- [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md)
- [Düzenleyiciyi özelleştirme](../ide/customizing-the-editor.md)
- [Visual Studio IDE’ye Genel Bakış](../ide/visual-studio-ide.md)
