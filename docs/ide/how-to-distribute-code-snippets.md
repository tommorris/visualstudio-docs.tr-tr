---
title: 'Nasıl yapılır: kod parçacıklarını dağıtma'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code snippets, distributing
ms.assetid: 5f717abd-e167-47ae-818c-6b0bae100ceb
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 44bf87f67c8042484e3b0907ea4d597136dcd820
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35255463"
---
# <a name="how-to-distribute-code-snippets"></a>Nasıl yapılır: kod parçacıklarını dağıtma

Kod parçacıkları arkadaşlarınıza verin ve bunları parçacıkları kod parçacıkları Yöneticisi'ni kullanarak kendi bilgisayarlarına yükleyin. Ancak, dağıtmak için birkaç parçacıkları varsa veya daha yaygın olarak dağıtmak istediğiniz parçacığı dosyanızı hangi Visual Studio kullanıcıların yükleyebilmek için bir Visual Studio uzantısına ekleyin.

Visual Studio uzantıları oluşturmak için Visual Studio SDK'yı yüklemeniz gerekir. Visual Studio yüklemenizin eşleşen VSSDK sürümünü bulmak [Visual Studio indirmeleri](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

## <a name="set-up-the-extension"></a>Uzantı ayarlayın

Bu yordamda oluşturduğunuz Hello World kod parçacığını kullanacağız [izlenecek yol: kod parçacığı oluşturma](../ide/walkthrough-creating-a-code-snippet.md). Biz sağlayacak *.snippet* geri dönüp birini yapmak zorunda kalmamak için metin.

1.  Adlı yeni bir VSIX proje oluşturma **TestSnippet**. (**Dosya** > **yeni** > **proje** > **Visual C# (veya Visual Basic)**  >  **Genişletilebilirlik**.)

2.  İçinde **TestSnippet** proje, yeni bir XML dosyası ekleyin ve bunu *VBCodeSnippet.snippet*. İçeriği aşağıdakiyle değiştirin:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <CodeSnippets
        xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
      <CodeSnippet Format="1.0.0">
        <Header>
          <Title>Hello World VB</Title>
          <Shortcut>HelloWorld</Shortcut>
          <Description>Inserts code</Description>
          <Author>MSIT</Author>
          <SnippetTypes>
            <SnippetType>Expansion</SnippetType>
            <SnippetType>SurroundsWith</SnippetType>
          </SnippetTypes>
        </Header>
        <Snippet>
          <Code Language="VB">
            <![CDATA[Console.WriteLine("Hello, World!")]]>
          </Code>
        </Snippet>
      </CodeSnippet>
    </CodeSnippets>
    ```

### <a name="set-up-the-directory-structure"></a>Dizin yapısını oluşturma

1.  İçinde **Çözüm Gezgini**, proje düğümünü seçin ve zorunda parçacığı istediğiniz ada sahip bir klasör eklemek **kod parçacıkları Yöneticisi**. Bu durumda, olmalıdır **HelloWorldVB**.

2.  Taşıma *.snippet* dosya *HelloWorldVB* klasör.

3.  Seçin *.snippet* dosyasını **Çözüm Gezgini**hem de **özellikleri** penceresi emin olun **yapı eylemi** içinayarlanmış**İçerik**, **çıktı dizinine Kopyala** ayarlanır **her zaman Kopyala**, ve **Include in VSIX** ayarlanır **true**.

### <a name="add-the-pkgdef-file"></a>.Pkgdef dosyası ekleme

1.  Bir metin dosyasına eklemek *HelloWorldVB* klasörü ve adlandırın *HelloWorldVB.pkgdef*. Bu dosya, belirli anahtarları için kayıt eklemek için kullanılır. Bu durumda, yeni bir anahtar ekler:

     `HKCU\Software\Microsoft\VisualStudio\15.0\Languages\CodeExpansions\Basic`

2.  Aşağıdaki satırları dosyasına ekleyin.

    ```txt
    // Visual Basic
    [$RootKey$\Languages\CodeExpansions\Basic\Paths]
    "HelloWorldVB"="$PackageFolder$"
    ```

    Bu anahtar incelerseniz, farklı diller belirtme görebilirsiniz.

3.  Seçin *.pkgdef* dosyasını **Çözüm Gezgini**hem de **özellikleri** penceresi emin olun **yapı eylemi** içinayarlanmış**İçerik**, **çıktı dizinine Kopyala** ayarlanır **her zaman Kopyala**, ve **Include in VSIX** ayarlanır **true**.

4.  Ekleme *.pkgdef* dosyası VSIX bildiriminde bir varlık olarak. İçinde *source.extension.vsixmanifest* dosya, Git **varlıklar** sekmesinde **yeni**.

5.  İçinde **ekleme yeni varlık** iletişim, kümesi **türü** için **Microsoft.VisualStudio.VsPackage**, **kaynak** için **üzerinde dosya dosya sistemi**ve **yolu** için **HelloWorldVB.pkgdef** (hangi görünmelidir açılır listede).

### <a name="test-the-snippet"></a>Kod parçacığını test

1.  Şimdi kod parçacığında Visual Studio deneysel örneğinde çalıştığını emin olabilirsiniz. Kod yazmak için kullandığınız diskten ayrı Visual Studio ikinci bir kopyası Deneysel örneğidir. Geliştirme ortamınızı etkilemeden uzantı üzerinde çalışmanıza olanak sağlar.

2.  Projeyi derleyin ve hata ayıklamayı Başlat. Visual Studio ikinci bir örneğini görüntülenmesi gerekir.

3.  Deneysel örneğinde Git **Araçlar > kod parçacıkları Yöneticisi** ve **dil** için **temel**. Görmeniz gerekir *HelloWorldVB* klasörleri ve biri görmek için klasörü genişletmek mümkün olması gerektiği gibi *HelloWorldVB* parçacığı.

4.  Kod parçacığını test edin. Deneysel örneğinde, Visual Basic projesinde açın ve kod dosyalarından birini açın. İmlecinizi kodda yere yerleştirin sağ tıklatın ve bağlam menüsünü seçin **Ekle parçacığı**.

5.  Görmeniz gerekir *HelloWorldVB* klasörlerden biri olarak. Çift tıklatın. Açılır pencere görmeniz gerekir **parçacığını ekleyin: HelloWorldVB >** bir açılır olan **HelloWorldVB**. Tıklatın **HelloWorldVB** açılır. Dosyaya eklenen aşağıdaki satırı görmeniz gerekir:

    ```vb
    Console.WriteLine("Hello, World!")
    ```

## <a name="see-also"></a>Ayrıca bkz.

- [Kod parçacıkları](../ide/code-snippets.md)