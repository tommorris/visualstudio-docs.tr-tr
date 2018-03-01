---
title: "İzlenecek yol: kod parçacığı oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 10/27/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code snippets, creating
- code snippets, shortcut
- code snippets, template
- code snippets, replacements
- code snippets, references
- code snippets, imports
ms.assetid: 0dcaae11-39cf-4463-9c90-2494321251c2
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2ac4cef411bb6304e4033de1850e6c428e34285e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-code-snippet"></a>İzlenecek Yol: Kod Parçacığı Oluşturma
Kod parçacığı ile yalnızca birkaç adımda oluşturabilirsiniz. Tüm yapmanız gereken olan XML dosyası oluşturma, uygun öğeleri doldurun ve kodunuzu ekleyin. Kodunuzu başvuruları ve değiştirme parametreleri de ekleyebilirsiniz. Kod parçacıkları yöneticisinde İçe Aktar düğmesini kullanarak Visual Studio yüklemenizin kod parçacığını ekleyebilirsiniz (**Araçları**, **kod parçacıkları Yöneticisi...** ).  
  
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
  
### <a name="to-create-a-code-snippet"></a>Kod parçacığı oluşturmak için  
  
1.  Visual Studio'da yeni bir XML dosyası oluşturun ve yukarıda gösterilen şablonu ekleyin.  
  
2.  Örneğin parçacığı başlığında doldurun "VB, başlık öğesinde hello World".  
  
3.  Kod öğesinin dilleri özniteliği parçacığında dilinin doldurun. Bu örnekte, "VB" kullanın.  
  
4.  Bazı kodu örneğin CDATA bölümünde kod öğesinin içine ekleyin:  
  
    ```xml  
    <Code Language="VB">  
        <![CDATA[Console.WriteLine("Hello, World!")]]>  
    </Code>
    ```  
  
5.  Kod parçacığını VBCodeSnippet.snippet kaydedin.  
  
### <a name="to-add-a-code-snippet-to-visual-studio"></a>Kod parçacığı Visual Studio'ya eklemek için  
  
1.  Kod parçacıkları Yöneticisi'ni kullanarak Visual Studio yüklemenizin kendi parçacıkları ekleyebilirsiniz. Kod parçacıkları Yöneticisi'ni açın (**Araçları**, **kod parçacıkları Yöneticisi...** ).  
  
2.  Tıklatın **alma** düğmesi.  
  
3.  Kod parçacığında önceki yordamda kaydedildiği konuma seçin ve tıklatın Git **açık**.  
  
4.  **İçe aktarma kod parçacığını** iletişim kutusunu açar, sağ bölmede seçeneklerden kod parçacığını ekleneceği konum seçmenizi istiyoruz. Aşağıdaki seçeneklerden birini olmalıdır **My kod parçacıkları**. Seçin ve **son**, ardından **Tamam**.  
  
5.  Kod parçacığını aşağıdaki konuma kopyalanır:  
  
     %USERPROFILE%\Documents\Visual studio 2017\Code Snippets\Visual Basic\My kod parçacıkları  
  
6.  Visual Basic projesinde açarak ve bir kod dosyasını açma, kod parçacığında sınayın. Dosya **parçacıkları**, **Ekle parçacığı** bağlam menüsünde **My kod parçacıkları**. Adlı bir parçacığı görmelisiniz **My Visual Basic kod parçacığını**. Çift tıklatın.  
  
    `Console.WriteLine("Hello, World!")`kod dosyasında eklenir.  
  
### <a name="adding-description-and-shortcut-fields"></a>Açıklama ve kısayol alanlarını ekleme  
  
1.  Açıklama alanlarını kod parçacıkları Yöneticisi'nde görüntülendiğinde, kod parçacığında hakkında daha fazla bilgi verin. Kullanıcılar, parçacığını eklemek için yazın bir etiket kısayoludur. Dosya %USERPROFILE%\Documents\Visual Studio 2017\Code Snippets\Visual Basic\My kod Snippet\VBCodeSnippet.snippet açarak eklediğiniz parçacığı düzenleyin.  
  
2.  Üstbilgi öğesi yazar ve açıklama öğeleri ekleyin ve bunları doldurun.  
  
3.  Üstbilgi öğesi aşağıdakine benzer görünmelidir:  
  
    ```xml  
    <Header>  
        <Title>Hello World VB</Title>  
        <Author>Myself</Author>  
        <Description>Says Hello to the world.</Description>  
    </Header>
    ```  
  
4.  Kod parçacıkları Yöneticisi'ni açın ve kod parçacığını seçin. Sağ bölmede açıklama ve Yazar alanları artık doldurulur görmeniz gerekir.  
  
5.  Bir kısayol eklemek için bir kısayol öğesi yazarı yanında ve Description öğesi ekleyin:  
  
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
  
### <a name="to-add-references-and-imports"></a>References ve Imports eklemek için  
  
1.  References öğesi kullanarak bir projesine bir başvuru ekleyin ve içeri aktarmalar öğesini kullanarak bir içeri aktarmalar bildirimi ekleyin. (Bu C# ' de çalışır.) Örneğin, değiştirirseniz `Console.WriteLine` kod örneğinde `MessageBox.Show`, projeye System.Windows.Forms.dll derleme eklemeniz gerekebilir.  
  
2.  Kod parçacığında açın.  
  
3.  References öğesi parçacığı öğesi altında ekleyin:  
  
    ```xml  
    <References>  
        <Reference>  
            <Assembly>System.Windows.Forms.dll</Assembly>  
        </Reference>  
    </References>
    ```  
  
4.  İçeri aktarmalar öğesinin parçacığı öğesi altında ekleyin:  
  
    ```xml  
    <Imports>  
        <Import>  
           <Namespace>System.Windows.Forms</Namespace>  
        </Import>  
    </Imports>
    ```  
  
5.  CDATA bölümü aşağıdaki gibi değiştirin:  
  
    ```xml  
    <![CDATA[MessageBox.Show("Hello, World!")]]>  
    ```  
  
6.  Kod parçacığını kaydedin.  
  
7.  Visual Basic projesinde açın ve kod parçacığını ekleyin.  
  
8.  Imports deyimi kod dosyasının üst görürsünüz:  
  
    ```vb  
    Imports System.Windows.Forms
    ```  
  
9. Projenin özelliklerine bakın. Başvurular sekmesini System.Windows.Forms.dll bir başvuru içeriyor.  
  
### <a name="adding-replacements"></a>Değişiklik ekleme  
  
1.  Örneğin bir değişkeni ekleyin ve bir geçerli projede değişkeni yerine kullanıcıya istediğiniz kullanıcı tarafından değiştirilmesi, kod parçacıkları bölümlerini isteyebilirsiniz. İki tür değişiklik sağlayabilir: değişmez değerler ve nesneler. Değişmez değerler (dize değişmez değerleri, değişken adları veya sayısal değerleri dize gösterimlerini), bazı türündeki dizelerdir. Tür bir dize dışında örneklerini nesneleridir. Bu yordamda değişmez değer değiştirme ve bir nesne değiştirme bildirme ve bu değişiklik başvurmak için kodu değiştirin.  
  
2.  Kod parçacığında açın.  
  
3.  Bu örnek, bir SQL bağlantı dizesi kullanır, bu nedenle uygun başvuruları eklemek için içeri aktarmalar ve başvurular öğelerini değiştirmeniz gerekir:  
  
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
  
4.  Değişmez değer yerine yeni bir SQL bağlantı dizesi için bildirmek için kod parçacığında öğesi altında bildirimleri öğesi ekleyin ve içinde Kimliğini, araç ipucu ve değiştirme için varsayılan değer alt öğeleri olan bir değişmez değer öğesi ekleyin:  
  
    ```xml  
    <Declarations>  
        <Literal>  
            <ID>SqlConnString</ID>  
            <ToolTip>Replace with a SQL connection string.</ToolTip>  
            <Default>"SQL connection string"</Default>  
        </Literal>  
    </Declarations>
    ```  
  
5.  SQL bağlantısı için bir nesne değiştirme bildirmek için nesne öğe bildirimleri öğesinin içine ekleyin ve kimliği için alt öğeleri, nesne, araç ipucu ve varsayılan değer türü ekleyin. Sonuçta elde edilen bildirimleri öğesi aşağıdaki gibi görünmelidir:  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Kod Parçacıkları Şema Başvurusu](../ide/code-snippets-schema-reference.md)