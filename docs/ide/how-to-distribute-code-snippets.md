---
title: "Nasıl yapılır: kod parçacıklarını dağıtma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: code snippets, distributing
ms.assetid: 5f717abd-e167-47ae-818c-6b0bae100ceb
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs: VB
ms.workload: multiple
ms.openlocfilehash: 39f6006ec6dfe754efc58f2ccdc7b09d803de6b3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-distribute-code-snippets"></a>Nasıl Yapılır: Kod Parçacıklarını Dağıtma
Yalnızca kod parçacıkları arkadaşlarınıza verin ve bunları parçacıkları kod parçacıkları Yöneticisi'ni kullanarak kendi bilgisayarlarına yükleyin. Ancak, dağıtmak için birkaç parçacıkları varsa veya daha yaygın olarak dağıtmak istediğiniz parçacığı dosyanızı hangi Visual Studio kullanıcıların yükleyebilmek için bir Visual Studio uzantısına ekleyin.  

Visual Studio uzantıları oluşturmak için Visual Studio SDK'yı yüklemeniz gerekir. Visual Studio yüklemenizin eşleşen VSSDK sürümünü bulmak [Visual Studio indirmeleri](https://www.visualstudio.com/downloads/).  

## <a name="setting-up-the-extension"></a>Uzantı ayarlama  
Bu yordamda oluşturduğunuz Hello World kod parçacığını kullanacağız [izlenecek yol: kod parçacığı oluşturma](../ide/walkthrough-creating-a-code-snippet.md). Geri dönüp birini yapmak zorunda kalmamak için Biz .snippet metin kullanacaksınız.  

1.  Adlı yeni bir VSIX proje oluşturma **TestSnippet**. (**Dosya**, **yeni**, **proje**, **Visual C# (veya Visual Basic)**, **genişletilebilirlik**.)  

2.  İçinde **TestSnippet** proje, yeni bir XML dosyası ekleyin ve bunu **VBCodeSnippet.snippet**. İçeriği aşağıdakiyle değiştirin:  

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

#### <a name="setting-up-the-directory-structure"></a>Dizin yapısı kurma  

1.  Çözüm Gezgini'nde proje düğümünü seçin ve kod parçacığını kod parçacıkları Yöneticisi'nde olmasını istediğiniz ada sahip bir klasör ekleyin. Bu durumda olmalıdır **HelloWorldVB**.  

2.  .Snippet dosyayı taşımak **HelloWorldVB** klasör.  

3.  .Snippet dosyasını seçin ve Çözüm Gezgini'nde **özellikleri** penceresi emin olun **yapı eylemi** ayarlanır **içerik**, **kopyalamak için çıktı Dizin** ayarlanır **her zaman Kopyala**, ve **Include in VSIX** ayarlanır **doğru**.  

#### <a name="adding-the-pkgdef-file"></a>.Pkgdef dosya ekleme  

1.  Bir metin dosyasına eklemek **HelloWorldVB** klasörü ve adlandırın **HelloWorldVB.pkgdef**. Bu dosya, belirli anahtarları için kayıt eklemek için kullanılır. Bu durumda yeni bir anahtar ekler  

     **HKCU\Software\Microsoft\VisualStudio\15.0\Languages\CodeExpansions\Basic**.  

2.  Aşağıdaki satırları dosyasına ekleyin.  

    ```  
    // Visual Basic   
    [$RootKey$\Languages\CodeExpansions\Basic\Paths]   
    "HelloWorldVB"="$PackageFolder$"  
    ```  

    Bu anahtar incelerseniz, farklı diller belirtme görebilirsiniz.  

3.  .Pkgdef dosyasını seçin ve Çözüm Gezgini'nde **özellikleri** penceresi emin olun **yapı eylemi** ayarlanır **içerik**, **çıktı dizinine Kopyala**  ayarlanır **her zaman Kopyala**, ve **Include in VSIX** ayarlanır **doğru**.  

4.  VSIX bildiriminde bir varlık olarak .pkgdef dosyasına ekleyin. Source.extension.vsixmanifest dosyasında Git **varlıklar** sekmesinde **yeni**.  

5.  İçinde **ekleme yeni varlık** iletişim, kümesi **türü** için **Microsoft.VisualStudio.VsPackage**, **kaynak** için **üzerinde dosya dosya sistemi**ve **yolu** için **HelloWorldVB.pkgdef** (hangi görünmelidir açılır listede).  

### <a name="testing-the-snippet"></a>Kod parçacığını test etme  

1.  Şimdi kod parçacığında Visual Studio deneysel örneğinde çalıştığını emin olabilirsiniz. Kod yazmak için kullandığınız diskten ayrı Visual Studio ikinci bir kopyası Deneysel örneğidir. Geliştirme ortamınızı etkilemeden uzantı üzerinde çalışmanıza olanak sağlar.  

2.  Projeyi derleyin ve hata ayıklamayı Başlat. Visual Studio ikinci bir örneğini görüntülenmesi gerekir.  

3.  Deneysel örneğinde gidin **araçları / kod parçacıkları Yöneticisi** ve **dil** için **temel**. Klasörlerden biri HelloWorldVB görmeniz gerekir ve HelloWorldVB parçacığı görmek için klasörü genişletmek mümkün olması gerekir.  

4.  Kod parçacığını test edin. Deneysel örneğinde, Visual Basic projesinde açın ve kod dosyalarından birini açın. İmlecinizi kodda yere yerleştirin sağ tıklatın ve bağlam menüsünü seçin **Ekle parçacığı**.  

5.  HelloWorldVB klasörlerden biri görmeniz gerekir. Çift tıklatın. Açılır pencere görmeniz gerekir **parçacığını ekleyin: HelloWorldVB >** bir açılır olan **HelloWorldVB**. HelloWorldVB açılır'ı tıklatın. Dosyaya eklenen aşağıdaki satırı görmeniz gerekir:  

    ```vb  
    Console.WriteLine("Hello, World!")  
    ```  

## <a name="see-also"></a>Ayrıca Bkz.  
[Kod Parçacıkları](../ide/code-snippets.md)
