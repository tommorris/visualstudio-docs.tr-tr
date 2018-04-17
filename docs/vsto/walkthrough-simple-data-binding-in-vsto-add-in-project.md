---
title: 'İzlenecek yol: Basit Veri bağlamada VSTO eklenti proje | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Office development in Visual Studio], binding data
- data binding [Office development in Visual Studio], Word
- data [Office development in Visual Studio], simple binding data
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7288cf17f7870747399116a1b779c2fa3b67205f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-simple-data-binding-in-vsto-add-in-project"></a>İzlenecek yol: Basit veri bağlama VSTO eklenti projesindeki
  Konak denetimleri ve VSTO eklentisi projelerine Windows Forms denetimlerine veri bağlayabilirsiniz. Bu kılavuz, Microsoft Office Word belgesine denetimleri ekleme ve çalışma zamanında verilere denetimler bağlama gösterilmiştir.  
  
 [!INCLUDE[appliesto_wdallapp](../vsto/includes/appliesto-wdallapp-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Ekleme bir <xref:Microsoft.Office.Tools.Word.ContentControl> bir belgeye çalışma zamanında.  
  
-   Oluşturma bir <xref:System.Windows.Forms.BindingSource> denetimi bir veri kümesi örneğine bağlanan.  
  
-   Kayıtlarda kaydırma ve denetiminde görüntülemek kullanıcı etkinleştirme.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] veya [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
-   SQL Server 2005 veya SQL Server 2005 Express'in çalışan bir örneğini erişimi `AdventureWorksLT` bağlı örnek veritabanı. İndirebilirsiniz `AdventureWorksLT` veritabanını [CodePlex Web sitesinde](http://go.microsoft.com/fwlink/?LinkId=115611). Veritabanı ekleme hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
    -   SQL Server Management Studio veya SQL Server Management Studio Express kullanarak veritabanı eklemek için bkz: [nasıl yapılır: bir veritabanını (SQL Server Management Studio)](http://msdn.microsoft.com/en-us/b4efb0ae-cfe6-4d81-a4b4-6e4916885caa).  
  
    -   Komut satırını kullanarak bir veritabanı eklemek için bkz: [nasıl yapılır: SQL Server Express için bir veritabanı dosyası ekleme](http://msdn.microsoft.com/en-us/0f8e42b5-7a8c-4c30-8c98-7d2bdc8dcc68).  
  
## <a name="creating-a-new-project"></a>Yeni proje oluşturma  
 İlk adım bir Word VSTO eklenti projesi oluşturmaktır.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adlı bir Word VSTO eklenti projesi oluşturun **veritabanından belgeleri doldurma**, Visual Basic veya C# kullanarak.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio ThisAddIn.vb veya ThisAddIn.cs dosyasını açar ve ekler **veritabanından belgeleri doldurma** için proje **Çözüm Gezgini**.  
  
2.  Varsa, Proje hedefleri [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], Microsoft.Office.Tools.Word.v4.0.Utilities.dll derlemesine başvuru ekleyin. Bu başvuru, bu kılavuzda daha sonra belgeye Windows Forms denetimlerini programlı eklemek için gereklidir.  
  
## <a name="creating-a-data-source"></a>Veri kaynağı oluşturma  
 Kullanım **veri kaynakları** penceresi türü belirtilmiş veri kümesi projenize ekleyin.  
  
#### <a name="to-add-a-typed-dataset-to-the-project"></a>Türü belirtilmiş veri kümesi projeye eklemek için  
  
1.  Varsa **veri kaynakları** pencere görünür değil, bunu, menü çubuğu seçme görüntülemek **Görünüm**, **diğer pencereler**, **veri kaynakları**.  
  
2.  Seçin **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı Yapılandırma Sihirbazı**.  
  
3.  Tıklatın **veritabanı**ve ardından **sonraki**.  
  
4.  Mevcut bir bağlantı varsa `AdventureWorksLT` veritabanı, bu bağlantıyı seçin ve tıklatın **sonraki**.  
  
     Aksi takdirde, tıklatın **yeni bağlantı**ve **Bağlantı Ekle** yeni bir bağlantı oluşturmak için iletişim kutusu. Daha fazla bilgi için bkz: [yeni bağlantılar eklemek](../data-tools/add-new-connections.md).  
  
5.  İçinde **bağlantı dizesini uygulama yapılandırma dosyasını Kaydet** sayfasında, **sonraki**.  
  
6.  İçinde **veritabanı nesnelerinizi** sayfasında **tabloları** seçip **müşteri (SalesLT)**.  
  
7.  **Son**'a tıklayın.  
  
     AdventureWorksLTDataSet.xsd dosyası eklenir **Çözüm Gezgini**. Bu dosya, aşağıdaki öğeleri tanımlar:  
  
    -   Adlı bir türü belirtilmiş veri `AdventureWorksLTDataSet`. Bu veri kümesi içeriğini temsil eden **müşteri (SalesLT)** AdventureWorksLT veritabanındaki tablo.  
  
    -   Adlı bir TableAdapter `CustomerTableAdapter`. Bu TableAdapter okumak ve veri yazmak için kullanılan `AdventureWorksLTDataSet`. Daha fazla bilgi için bkz: [TableAdapter genel bakışı](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview).  
  
     Bu kılavuzda daha sonra bu nesnelerin her ikisi de kullanır.  
  
## <a name="creating-controls-and-binding-controls-to-data"></a>Denetimler oluşturma ve verilere denetimler bağlama  
 Bu kılavuzda veritabanı kayıtları görüntülemek için kullanılan arabirimi çok basittir ve belgenin içinde oluşturulur. Bir <xref:Microsoft.Office.Tools.Word.ContentControl> tek veritabanı kaydını görüntüler birer ve iki <xref:Microsoft.Office.Tools.Word.Controls.Button> denetimleri ve geriye kayıtlarda kaydırma olanak tanır. İçerik denetimi kullanan bir <xref:System.Windows.Forms.BindingSource> veritabanına bağlanılamıyor.  
  
 Denetimlere veri bağlama hakkında daha fazla bilgi için bkz: [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
#### <a name="to-create-the-interface-in-the-document"></a>Belgede arabirim oluşturmak için  
  
1.  İçinde `ThisAddIn` sınıfı, görüntülemek ve kaydırmak için aşağıdaki denetimleri bildirin `Customer` tablosu `AdventureWorksLTDataSet` veritabanı.  
  
     [!code-vb[Trin_WordAddInDatabase#1](../vsto/codesnippet/VisualBasic/trin_wordaddindatabase/ThisAddIn.vb#1)]
     [!code-csharp[Trin_WordAddInDatabase#1](../vsto/codesnippet/CSharp/trin_wordaddindatabase/ThisAddIn.cs#1)]  
  
2.  İçinde `ThisAddIn_Startup` yöntemi, veri kümesi başlatmak, bilgileriyle veri kümesini doldurmak için aşağıdaki kodu ekleyin `AdventureWorksLTDataSet` veritabanı.  
  
     [!code-vb[Trin_WordAddInDatabase#2](../vsto/codesnippet/VisualBasic/trin_wordaddindatabase/ThisAddIn.vb#2)]
     [!code-csharp[Trin_WordAddInDatabase#2](../vsto/codesnippet/CSharp/trin_wordaddindatabase/ThisAddIn.cs#2)]  
  
3.  Aşağıdaki kodu ekleyin `ThisAddIn_Startup` yöntemi. Bu belgeyi genişleten bir konak öğesi oluşturur. Daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
     [!code-vb[Trin_WordAddInDatabase#3](../vsto/codesnippet/VisualBasic/trin_wordaddindatabase/ThisAddIn.vb#3)]
     [!code-csharp[Trin_WordAddInDatabase#3](../vsto/codesnippet/CSharp/trin_wordaddindatabase/ThisAddIn.cs#3)]  
  
4.  Belgenin başlangıcına birkaç aralıklarını tanımlayın. Bu aralıklar metin eklemek ve denetimleri yerleştirin yeri belirleyin.  
  
     [!code-vb[Trin_WordAddInDatabase#4](../vsto/codesnippet/VisualBasic/trin_wordaddindatabase/ThisAddIn.vb#4)]
     [!code-csharp[Trin_WordAddInDatabase#4](../vsto/codesnippet/CSharp/trin_wordaddindatabase/ThisAddIn.cs#4)]  
  
5.  Arabirim denetimler için önceden tanımlanmış aralıklara ekleyin.  
  
     [!code-vb[Trin_WordAddInDatabase#5](../vsto/codesnippet/VisualBasic/trin_wordaddindatabase/ThisAddIn.vb#5)]
     [!code-csharp[Trin_WordAddInDatabase#5](../vsto/codesnippet/CSharp/trin_wordaddindatabase/ThisAddIn.cs#5)]  
  
6.  İçerik denetimi bağlamak `AdventureWorksLTDataSet` kullanarak <xref:System.Windows.Forms.BindingSource>. C# geliştiricileri için iki olay işleyicileri ekleme <xref:Microsoft.Office.Tools.Word.Controls.Button> kontrol eder.  
  
     [!code-vb[Trin_WordAddInDatabase#6](../vsto/codesnippet/VisualBasic/trin_wordaddindatabase/ThisAddIn.vb#6)]
     [!code-csharp[Trin_WordAddInDatabase#6](../vsto/codesnippet/CSharp/trin_wordaddindatabase/ThisAddIn.cs#6)]  
  
7.  Veritabanı kayıtlarında gezinmek için aşağıdaki kodu ekleyin.  
  
     [!code-vb[Trin_WordAddInDatabase#7](../vsto/codesnippet/VisualBasic/trin_wordaddindatabase/ThisAddIn.vb#7)]
     [!code-csharp[Trin_WordAddInDatabase#7](../vsto/codesnippet/CSharp/trin_wordaddindatabase/ThisAddIn.cs#7)]  
  
## <a name="testing-the-add-in"></a>Eklentiyi test etme  
 Word'ü açtığınızda, içerik denetimi verileri görüntüleyen `AdventureWorksLTDataSet` veri kümesi. Tıklatarak veritabanı kayıtları arasında kaydırma **sonraki** ve **önceki** düğmeler.  
  
#### <a name="to-test-the-vsto-add-in"></a>VSTO eklenti sınamak için  
  
1.  Tuşuna **F5**.  
  
     Adlandırılan içerik denetimi `customerContentControl` oluşturulur ve verilerle doldurulur. Aynı anda, adında bir veri kümesi nesnesi `adventureWorksLTDataSet` ve <xref:System.Windows.Forms.BindingSource> adlı `customerBindingSource` projeye eklenir. <xref:Microsoft.Office.Tools.Word.ContentControl> Bağlı <xref:System.Windows.Forms.BindingSource>, sırayla bağlı veri kümesi nesnesi.  
  
2.  Tıklatın **sonraki** ve **önceki** veritabanı kayıtlar arasında gezinmek için düğmeler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerindeki veriler](../vsto/data-in-office-solutions.md)   
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Nasıl yapılır: çalışma sayfalarını veritabanı verileriyle doldurma](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)   
 [Nasıl yapılır: belgeleri veritabanı verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [Nasıl yapılır: belgeleri hizmet verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-services.md)   
 [Nasıl yapılır: belgeleri nesne verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-objects.md)   
 [Nasıl yapılır: çalışma sayfasındaki veritabanı kayıtları arasında kaydırma](../vsto/how-to-scroll-through-database-records-in-a-worksheet.md)   
 [Nasıl yapılır: konak kontrolü verileriyle veri kaynağını güncelleme](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [İzlenecek yol: Belge düzeyi projede basit veri bağlama](../vsto/walkthrough-simple-data-binding-in-a-document-level-project.md)   
 [İzlenecek yol: Belge düzeyi projede karmaşık veri bağlama](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md)   
 [Office çözümleri genel bakış yerel veritabanı dosyaları kullanma](../vsto/using-local-database-files-in-office-solutions-overview.md)   
 [Yeni veri kaynakları ekleyin](/visualstudio/data-tools/add-new-data-sources)   
 [Visual Studio'da verilere Windows Forms denetimleri bağlama](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Nasıl yapılır: belgeleri nesne verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-objects.md)   
 [Nasıl yapılır: konak kontrolü verileriyle veri kaynağını güncelleme](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [Office çözümleri genel bakış yerel veritabanı dosyaları kullanma](../vsto/using-local-database-files-in-office-solutions-overview.md)   
 [Windows Forms uygulamalarındaki verilere bağlanma](/visualstudio/data-tools/connecting-to-data-in-windows-forms-applications)   
 [BindingSource Bileşenine Genel Bakış](/dotnet/framework/winforms/controls/bindingsource-component-overview)  
  
  