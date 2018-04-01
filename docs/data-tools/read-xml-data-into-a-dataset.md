---
title: Bir veri kümesini okuma XML verilerini | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- reading XML
- data access [Visual Studio], XML data
- reading files, XML
- data [Visual Studio], reading from XML files
- reading data, XML files
- XML [Visual Studio], reading
- XML documents, reading
- datasets [Visual Basic], reading XML data
ms.assetid: fae72958-0893-47d6-b3dd-9d42418418e4
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 093dbb5ee8f088a7f2e4ccd1dd063cfeecc2c5e3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="read-xml-data-into-a-dataset"></a>Bir veri kümesini XML verilerini okuma
ADO.NET XML verilerle çalışmak için basit yöntemleri sağlar. Bu kılavuzda, bir veri kümesini XML verileri yükler bir Windows uygulaması oluşturun. Veri kümesi sonra görüntülenen bir <xref:System.Windows.Forms.DataGridView> denetim. Son olarak, XML dosyasının içeriğine göre bir XML şeması bir metin kutusunda görüntülenir.  
  
 Bu kılavuzda beş ana adımdan oluşur:  
  
1.  Yeni proje oluşturma  
  
2.  Dataset nesnesine okumak için bir XML dosyası oluşturma  
  
3.  Kullanıcı arabirimi oluşturma  
  
4.  Veri kümesi oluşturma, XML dosyası okumak ve içinde görüntüleme bir <xref:System.Windows.Forms.DataGridView> denetimi  
  
5.  XML şeması görüntülemek için kod ekleme temel XML dosyasında bir <xref:System.Windows.Forms.TextBox> denetimi  
  
> [!NOTE]
>  İletişim kutuları ve menü komutlarını açıklanana Yardımı'nda etkin ayarlarınızı veya edition bağlı olarak değişebilir gördüğünüz kullandığınız. Ayarlarınızı değiştirmek için **Araçları** menüsünde, select **içeri ve dışarı aktarma ayarları**. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="create-a-new-project"></a>Yeni bir proje oluşturma  
 Bu adımda, bu kılavuzda içeren bir Visual Basic veya Visual C# projesi oluşturun.  
  
#### <a name="to-create-the-new-windows-project"></a>Yeni Windows projesi oluşturmak için  
  
1. Visual Studio'da üzerinde **dosya** menüsünde, select **yeni**, **proje...** .  
  
2. Genişletin **Visual C#** veya **Visual Basic** sol bölmesinde, ardından **Windows Klasik Masaüstü**.  

3. Orta bölmede seçin **Windows Forms uygulaması** proje türü.  

4. Proje adı **ReadingXML**ve ardından **Tamam**. 
  
     **ReadingXML** projesi oluşturulur ve eklenen **Çözüm Gezgini**.  
  
## <a name="generate-the-xml-file-to-be-read-into-the-dataset"></a>Dataset nesnesine okumak için XML dosyası oluşturma  
 Bu kılavuz bir veri kümesini XML verilerini okuma üzerinde odaklanır olduğundan, bir XML dosyasının içeriğini sağlanır.  
  
#### <a name="to-create-the-xml-file-that-will-be-read-into-the-dataset"></a>Veri kümesini okuma XML dosyasını oluşturmak için  
  
1.  Üzerinde **proje** menüsünde, select **Yeni Öğe Ekle**.  
  
2.  Seçin **XML dosyası**, dosya adı `authors.xml`ve ardından **Ekle**.  
  
     XML dosyasını tasarımcıya yükler ve düzenleme için hazır.  
  
3.  XML bildirimi aşağıda düzenleyicisine aşağıdaki kodu yapıştırın:  
  
    ```xml  
    <Authors_Table>  
      <authors>  
        <au_id>172-32-1176</au_id>  
        <au_lname>White</au_lname>  
        <au_fname>Johnson</au_fname>  
        <phone>408 496-7223</phone>  
        <address>10932 Bigge Rd.</address>  
        <city>Menlo Park</city>  
        <state>CA</state>  
        <zip>94025</zip>  
        <contract>true</contract>  
      </authors>  
      <authors>  
        <au_id>213-46-8915</au_id>  
        <au_lname>Green</au_lname>  
        <au_fname>Margie</au_fname>  
        <phone>415 986-7020</phone>  
        <address>309 63rd St. #411</address>  
        <city>Oakland</city>  
        <state>CA</state>  
        <zip>94618</zip>  
        <contract>true</contract>  
      </authors>  
      <authors>  
        <au_id>238-95-7766</au_id>  
        <au_lname>Carson</au_lname>  
        <au_fname>Cheryl</au_fname>  
        <phone>415 548-7723</phone>  
        <address>589 Darwin Ln.</address>  
        <city>Berkeley</city>  
        <state>CA</state>  
        <zip>94705</zip>  
        <contract>true</contract>  
      </authors>  
      <authors>  
        <au_id>267-41-2394</au_id>  
        <au_lname>Hunter</au_lname>  
        <au_fname>Anne</au_fname>  
        <phone>408 286-2428</phone>  
        <address>22 Cleveland Av. #14</address>  
        <city>San Jose</city>  
        <state>CA</state>  
        <zip>95128</zip>  
        <contract>true</contract>  
      </authors>  
      <authors>  
        <au_id>274-80-9391</au_id>  
        <au_lname>Straight</au_lname>  
        <au_fname>Dean</au_fname>  
        <phone>415 834-2919</phone>  
        <address>5420 College Av.</address>  
        <city>Oakland</city>  
        <state>CA</state>  
        <zip>94609</zip>  
        <contract>true</contract>  
      </authors>  
    </Authors_Table>  
    ```  
  
4.  Üzerinde **dosya** menüsünde, select **authors.xml kaydetmek**.  
  
## <a name="create-the-user-interface"></a>Kullanıcı arabirimi oluşturma  
 Bu uygulama için kullanıcı arabirimi aşağıdakilerden oluşur:  
  
-   A <xref:System.Windows.Forms.DataGridView> verileri olarak XML dosyasının içeriğini görüntüleyen denetim.  
  
-   A <xref:System.Windows.Forms.TextBox> XML dosyasını XML Şeması görüntüleyen denetim.  
  
-   İki <xref:System.Windows.Forms.Button> denetimleri.  
  
    -   Bir düğme kümesine XML dosyasını okur ve görüntüler <xref:System.Windows.Forms.DataGridView> denetim.  
  
    -   İkinci düğme kümesinden ve aracılığıyla şema ayıklar bir <xref:System.IO.StringWriter> görüntüler <xref:System.Windows.Forms.TextBox> denetim.  
  
#### <a name="to-add-controls-to-the-form"></a>Forma denetim eklemek için  
  
1.  Açık `Form1` Tasarım görünümünde.  
  
2.  Gelen **araç**, aşağıdaki denetimleri form üzerine sürükleyin:  
  
    -   Bir <xref:System.Windows.Forms.DataGridView> denetimi  
  
    -   Bir <xref:System.Windows.Forms.TextBox> denetimi  
  
    -   İki <xref:System.Windows.Forms.Button> denetimleri  
  
3.  Aşağıdaki özellikleri ayarlayın:  
  
    |Denetim|Özellik|Ayar|  
    |-------------|--------------|-------------|  
    |`TextBox1`|**Çok satırlı**|`true`|  
    ||**Kaydırma çubukları**|**Dikey**|  
    |`Button1`|**Ad**|`ReadXmlButton`|  
    ||**Metin**|`Read XML`|  
    |`Button2`|**Ad**|`ShowSchemaButton`|  
    ||**Metin**|`Show Schema`|  
  
## <a name="create-the-dataset-that-receives-the-xml-data"></a>XML verileri alan veri kümesi oluşturma  
 Bu adımda oluşturduğunuz adlı yeni bir veri kümesi `authors`. Veri kümeleri hakkında daha fazla bilgi için bkz: [Visual Studio'da veri kümesi Araçları](../data-tools/dataset-tools-in-visual-studio.md).  
  
#### <a name="to-create-a-new-dataset-that-receives-the-xml-data"></a>XML verileri alan yeni bir veri kümesi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, kaynak dosyasını seçmek **Form1**ve ardından **Görünüm Tasarımcısı** düğmesini **Çözüm Gezgini** araç çubuğu.  
  
2.  Gelen [araç kutusu, veri sekmesinde](../ide/reference/toolbox-data-tab.md), sürükleyin bir **DataSet** üzerine **Form1**.  
  
3.  İçinde **veri kümesi Ekle** iletişim kutusunda **türsüz dataset**ve ardından **Tamam**.  
  
     **DataSet1** bileşen Tepsisi eklenir.  
  
4.  İçinde **özellikleri** penceresindeki ayarlayın **adı** ve <xref:System.Data.DataSet.DataSetName%2A> özelliklerini`AuthorsDataSet`.  
  
## <a name="create-the-event-handler-to-read-the-xml-file-into-the-dataset"></a>Veri kümesini XML dosyasını okumak için olay işleyicisi oluşturun  
 **Okuma XML** düğmesi kümesine XML dosyasını okur. Üzerinde özellikleri daha sonra Ayarlar <xref:System.Windows.Forms.DataGridView> kümesine bağlamak denetim.  
  
#### <a name="to-add-code-to-the-readxmlbuttonclick-event-handler"></a>ReadXmlButton_Click olay işleyicisi için kod eklemek için  
  
1.  İçinde **Çözüm Gezgini**seçin **Form1**ve ardından **Görünüm Tasarımcısı** düğmesini **Çözüm Gezgini** araç.  
  
2.  Seçin **okuma XML** düğmesi.  
  
     **Kod düzenleyicisinde** adresindeki açılır `ReadXmlButton_Click` olay işleyicisi.  
  
3.  Aşağıdaki kodu yazın `ReadXmlButton_Click` olay işleyicisi:  
  
     [!code-csharp[VbRaddataFillingAndExecuting#2](../data-tools/codesnippet/CSharp/read-xml-data-into-a-dataset_1.cs)]
     [!code-vb[VbRaddataFillingAndExecuting#2](../data-tools/codesnippet/VisualBasic/read-xml-data-into-a-dataset_1.vb)]  
  
4.  İçinde `ReadXMLButton_Click` olay işleyici kodu, değişiklik `filepath =` doğru yola girişi.  
  
## <a name="create-the-event-handler-to-display-the-schema-in-the-textbox"></a>Metin kutusuna şemasını görüntülemek için olay işleyicisi oluşturun  
 **Göster şema** düğmesi oluşturur bir <xref:System.IO.StringWriter> şeması ile doldurulur ve görüntülenen nesne <xref:System.Windows.Forms.TextBox>denetim.  
  
#### <a name="to-add-code-to-the-showschemabuttonclick-event-handler"></a>ShowSchemaButton_Click olay işleyicisi için kod eklemek için  
  
1.  İçinde **Çözüm Gezgini**seçin **Form1**ve ardından **Görünüm Tasarımcısı** düğmesi.  
  
2.  Seçin **Göster şema** düğmesi.  
  
     **Kod düzenleyicisinde** adresindeki açılır `ShowSchemaButton_Click` olay işleyicisi.  
  
3.  Aşağıdaki kodu yazın `ShowSchemaButton_Click` olay işleyicisi.  
  
     [!code-csharp[VbRaddataFillingAndExecuting#3](../data-tools/codesnippet/CSharp/read-xml-data-into-a-dataset_2.cs)]
     [!code-vb[VbRaddataFillingAndExecuting#3](../data-tools/codesnippet/VisualBasic/read-xml-data-into-a-dataset_2.vb)]  
  
## <a name="test-the-form"></a>Formun test  
 Artık formun beklendiği gibi davranır emin olmak için test edebilirsiniz.  
  
#### <a name="to-test-the-form"></a>Formu sınamak için  
  
1.  Seçin **F5** uygulamayı çalıştırın.  
  
2.  Seçin **okuma XML** düğmesi.  
  
     DataGridView XML dosyasının içeriğini görüntüler.  
  
3.  Seçin **Göster şema** düğmesi.  
  
     Metin kutusu XML dosyasını XML Şeması görüntüler.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu kılavuzda XML dosyasının içeriğini temel alarak bir şema oluşturma yanı sıra bir XML dosyası bir veri kümesini okuma temelleri öğretir. Sonraki yapabilecek bazı görevler şunlardır:  
  
-   Veri kümesi ve geri XML olarak yazma veriler düzenleyin. Daha fazla bilgi için bkz. <xref:System.Data.DataSet.WriteXml%2A>.  
  
-   Veri kümesindeki düzenleyin ve bir veritabanına yazamadı. Daha fazla bilgi için bkz: [verileri kaydetme](../data-tools/saving-data.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da veri erişimi](../data-tools/accessing-data-in-visual-studio.md)       
 [Visual Studio'daki XML Araçları](../xml-tools/xml-tools-in-visual-studio.md)