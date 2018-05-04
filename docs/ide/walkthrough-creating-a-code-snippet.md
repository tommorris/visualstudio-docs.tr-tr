---
title: 'İzlenecek yol: bir kod parçacığı oluşturma'
ms.date: 10/27/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code snippets, creating
- code snippets, shortcut
- code snippets, template
- code snippets, replacements
- code snippets, references
- code snippets, imports
ms.assetid: 0dcaae11-39cf-4463-9c90-2494321251c2
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 6a9890be18e3d43f4c036da72bf2794801e5ec70
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="walkthrough-create-a-code-snippet"></a>İzlenecek yol: bir kod parçacığı oluşturma
Kod parçacığı ile yalnızca birkaç adımda oluşturabilirsiniz. Tüm yapmanız gereken olan XML dosyası oluşturma, uygun öğeleri doldurun ve kodunuzu ekleyin. Kodunuzu başvuruları ve değiştirme parametreleri de ekleyebilirsiniz. Kod parçacığını kullanarak Visual Studio yüklemenizin ekleyebilmeniz için **alma** düğmesini **kod parçacıkları Yöneticisi** (**Araçları**  >   **Kod parçacıkları Yöneticisi**).

## <a name="snippet-template"></a>Kod parçacığında şablonu
 Temel parçacığı şablon verilmiştir:

```xml
<?xml version="1.0" encoding="utf-8"?>
<CodeSnippets
    xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title></Title>
        </Header>
        <Snippet>
            <Code Language="">
                <![CDATA[]]>
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>
```

### <a name="create-a-code-snippet"></a>Kod parçacığı oluşturma

1.  Visual Studio'da yeni bir XML dosyası oluşturun ve yukarıda gösterilen şablonu ekleyin.

2.  Örneğin parçacığı başlığında doldurun "Hello World VB", **başlık** öğesi.

3.  Parçacığında dilinin doldurun **diller** özniteliği **kod** öğesi. Bu örnekte, "VB" kullanın.

4.  Bazı kodlar ekleyin **CDATA** içinde bölümünde **kod** öğesi, örneğin:

    ```xml
    <Code Language="VB">
        <![CDATA[Console.WriteLine("Hello, World!")]]>
    </Code>
    ```

5.  Kod parçacığını olarak Kaydet *VBCodeSnippet.snippet*.

### <a name="add-a-code-snippet-to-visual-studio"></a>Visual Studio için bir kod parçacığını ekleyin

1.  Kod parçacıkları Yöneticisi'ni kullanarak Visual Studio yüklemenizin kendi parçacıkları ekleyebilirsiniz. Açık **kod parçacıkları Yöneticisi** (**Araçları** > **kod parçacıkları Yöneticisi**).

2.  Tıklatın **alma** düğmesi.

3.  Kod parçacığında önceki yordamda kaydedildiği konuma seçin ve tıklatın Git **açık**.

4.  **İçe aktarma kod parçacığını** iletişim kutusunu açar, sağ bölmede seçeneklerden kod parçacığını ekleneceği konum seçmenizi istiyoruz. Aşağıdaki seçeneklerden birini olmalıdır **My kod parçacıkları**. Seçin ve **son**, ardından **Tamam**.

5.  Kod parçacığını aşağıdaki konuma kopyalanır:

     *%USERPROFILE%\Documents\Visual studio 2017\Code Snippets\Visual Basic\My kod parçacıkları*

6.  Visual Basic projesinde açarak ve bir kod dosyasını açma, kod parçacığında sınayın. Dosya **parçacıkları** > **Ekle parçacığı** bağlam menüsünde **My kod parçacıkları**. Adlı bir parçacığı görmelisiniz **My Visual Basic kod parçacığını**. Çift tıklatın.

    `Console.WriteLine("Hello, World!")` kod dosyasında eklenir.

### <a name="add-description-and-shortcut-fields"></a>Açıklama ve kısayol alanlarını ekleme

1.  Açıklama alanlarını kod parçacıkları Yöneticisi'nde görüntülendiğinde, kod parçacığında hakkında daha fazla bilgi verin. Kullanıcılar, parçacığını eklemek için yazın bir etiket kısayoludur. Dosyasını açarak eklediğiniz parçacığı düzenleme *%USERPROFILE%\Documents\Visual Studio 2017\Code Snippets\Visual Basic\My kod Snippet\VBCodeSnippet.snippet*.

2.  Ekleme **Yazar** ve **açıklama** öğelerine **üstbilgi** öğesi, bunları doldurun.

3.  **Üstbilgi** öğesi aşağıdakine benzer görünmelidir:

    ```xml
    <Header>
        <Title>Hello World VB</Title>
        <Author>Myself</Author>
        <Description>Says Hello to the world.</Description>
    </Header>
    ```

4.  Açık **kod parçacıkları Yöneticisi** ve kod parçacığını seçin. Sağ bölmede, görmelisiniz **açıklama** ve **Yazar** alanları artık doldurulur.

5.  Kısayol eklemek için Ekle bir **kısayol** yanında öğesi **Yazar** ve **açıklama** öğe:

    ```xml
    <Header>
        <Title>Hello World VB</Title>
        <Author>Myself</Author>
        <Description>Says Hello to the world.</Description>
        <Shortcut>hello</Shortcut>
    </Header>
    ```

6.  Parçacık dosyasını yeniden kaydedin.

7.  Kısayol sınamak için Visual Basic projesinde açın ve bir kod dosyasını açın. Tür `hello` dosya ve tuşuna **sekmesini** iki kez.

    Kod parçacığında kodu eklenir.

### <a name="add-references-and-imports"></a>References ve Imports ekleme

1.  Kullanarak bir projesine bir başvuru ekleyebilirsiniz **başvuruları** öğesi ve bir içeri aktarmalar bildirimi kullanarak eklemek **içeri aktarmalar** öğesi. (Bu C# ' de çalışır.) Örneğin, değiştirirseniz `Console.WriteLine` kod örneğinde `MessageBox.Show`, eklemeniz gerekebilir *System.Windows.Forms.dll* projeye derleme.

2.  Kod parçacığında açın.

3.  Ekleme **başvuruları** öğesinin altında **parçacığı** öğe:

    ```xml
    <References>
        <Reference>
            <Assembly>System.Windows.Forms.dll</Assembly>
        </Reference>
    </References>
    ```

4.  Ekleme **içeri aktarmalar** öğesinin altında **parçacığı** öğe:

    ```xml
    <Imports>
        <Import>
           <Namespace>System.Windows.Forms</Namespace>
        </Import>
    </Imports>
    ```

5.  Değişiklik **CDATA** aşağıdaki bölüme:

    ```xml
    <![CDATA[MessageBox.Show("Hello, World!")]]>
    ```

6.  Kod parçacığını kaydedin.

7.  Visual Basic projesinde açın ve kod parçacığını ekleyin.

8.  Göreceğiniz bir `Imports` kod dosyasının üst deyimi:

    ```vb
    Imports System.Windows.Forms
    ```

9. Projenin özelliklerine bakın. **Başvuruları** sekmesi içerir başvuru *System.Windows.Forms.dll*.

### <a name="add-replacements"></a>Değişiklik ekleme

1.  Örneğin bir değişkeni ekleyin ve bir geçerli projede değişkeni yerine kullanıcıya istediğiniz kullanıcı tarafından değiştirilmesi, kod parçacıkları bölümlerini isteyebilirsiniz. İki tür değişiklik sağlayabilir: değişmez değerler ve nesneler. Değişmez değerler (dize değişmez değerleri, değişken adları veya sayısal değerleri dize gösterimlerini), bazı türündeki dizelerdir. Tür bir dize dışında örneklerini nesneleridir. Bu yordamda değişmez değer değiştirme ve bir nesne değiştirme bildirme ve bu değişiklik başvurmak için kodu değiştirin.

2.  Kod parçacığında açın.

3.  Değişiklik yapmanız Bu örnek bir SQL bağlantı dizesi kullanır, bu nedenle **içeri aktarmalar** ve **başvuruları** uygun başvuruları eklemek için öğeleri:

    ```xml
    <References>
        <Reference>
            <Assembly>System.Data.dll</Assembly>
        </Reference>
        <Reference>
            <Assembly>System.Xml.dll</Assembly>
        </Reference>
    </References>
    <Imports>
        <Import>
            <Namespace>System.Data</Namespace>
        </Import>
        <Import>
            <Namespace>System.Data.SqlClient</Namespace>
        </Import>
    </Imports>
    ```

4.  Değişmez değer yerine yeni bir SQL bağlantı dizesi için bildirmek için ekleyin bir **bildirimleri** öğesinin altında **parçacığı** öğesi ve bunu ekleyin bir **değişmez değer** olan öğesi alt kimliği, araç ipucu ve değiştirme için varsayılan değer:

    ```xml
    <Declarations>
        <Literal>
            <ID>SqlConnString</ID>
            <ToolTip>Replace with a SQL connection string.</ToolTip>
            <Default>"SQL connection string"</Default>
        </Literal>
    </Declarations>
    ```

5.  SQL bağlantısı için bir nesne değiştirme bildirmek için ekleyin bir **nesne** öğesi içinde **bildirimleri** öğesi ve alt öğeleri kimliği, nesne, araç ipucu ve varsayılan tür ekleyin değer. Elde edilen **bildirimleri** öğesi aşağıdaki gibi görünmelidir:

    ```xml
    <Declarations>
        <Literal>
            <ID>SqlConnString</ID>
            <ToolTip>Replace with a SQL connection string.</ToolTip>
            <Default>"SQL connection string"</Default>
        </Literal>
        <Object>
            <ID>SqlConnection</ID>
            <Type>System.Data.SqlClient.SqlConnection</Type>
            <ToolTip>Replace with a connection object in your application.</ToolTip>
            <Default>dcConnection</Default>
        </Object>
    </Declarations>
    ```

6.  Kod bölümünde $ işaretlerini örneğin çevreleyen ile değiştirmeler başvuru `$replacement$`:

    ```xml
    <Code Language="VB" Kind="method body">
        <![CDATA[Dim daCustomers As SqlDataAdapter
            Dim selectCommand As SqlCommand

            daCustomers = New SqlClient.SqlDataAdapter()
            selectCommand = new SqlClient.SqlCommand($SqlConnString$)
            daCustomers.SelectCommand = selectCommand
            daCustomers.SelectCommand.Connection = $SqlConnection$]]>
    </Code>
    ```

7.  Kod parçacığını kaydedin.

8.  Visual Basic projesinde açın ve kod parçacığını ekleyin.

9. Kod aşağıdaki gibi görünmelidir burada değiştirmeler `SQL connection string` ve `dcConnection` içinde açık turuncu vurgulanır. Seçin **sekmesini** birinden diğerine gidin.

    ```vb
    Dim daCustomers As SqlDataAdapter
    Dim selectCommand As SqlCommand

    daCustomers = New SqlClient.SqlDataAdapter()
    selectCommand = New SqlClient.SqlCommand("SQL connection string")
    daCustomers.SelectCommand = selectCommand
    daCustomers.SelectCommand.Connection = dcConnection
    ```

## <a name="see-also"></a>Ayrıca bkz.

- [Kod parçacıkları şema başvurusu](../ide/code-snippets-schema-reference.md)