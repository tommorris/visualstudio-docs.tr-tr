---
title: "İzlenecek yol: Karmaşık veri bağlamada VSTO eklenti proje | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data binding [Office development in Visual Studio], Excel
- data [Office development in Visual Studio], binding data
- complex data [Office development in Visual Studio]
ms.assetid: ff52fb56-1f67-4ae2-a3d1-93038619d4e6
caps.latest.revision: "38"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 02db64a64cdf6e8cdbaf7a0d99044e2b8e9071c4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-complex-data-binding-in-vsto-add-in-project"></a>İzlenecek yol: Karmaşık veri bağlama VSTO eklenti projesindeki
  Konak denetimleri ve VSTO eklentisi projelerine Windows Forms denetimlerine veri bağlayabilirsiniz. Bu kılavuz, Microsoft Office Excel çalışma sayfasına denetimler ekleme ve çalışma zamanında verilere denetimler bağlama gösterilmiştir.  
  
 [!INCLUDE[appliesto_xlallapp](../vsto/includes/appliesto-xlallapp-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Ekleme bir <xref:Microsoft.Office.Tools.Excel.ListObject> çalışma zamanında denetim.  
  
-   Oluşturma bir <xref:System.Windows.Forms.BindingSource> denetimi bir veri kümesi örneğine bağlanan.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)]veya [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
-   SQL Server 2005 veya SQL Server 2005 Express'in çalışan bir örneğini erişimi `AdventureWorksLT` bağlı örnek veritabanı. İndirebilirsiniz `AdventureWorksLT` veritabanını [CodePlex Web sitesinde](http://go.microsoft.com/fwlink/?LinkId=115611). Veritabanı ekleme hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
    -   SQL Server Management Studio veya SQL Server Management Studio Express kullanarak veritabanı eklemek için bkz: [nasıl yapılır: bir veritabanını (SQL Server Management Studio)](http://msdn.microsoft.com/en-us/b4efb0ae-cfe6-4d81-a4b4-6e4916885caa).  
  
    -   Komut satırını kullanarak bir veritabanı eklemek için bkz: [nasıl yapılır: SQL Server Express için bir veritabanı dosyası ekleme](http://msdn.microsoft.com/en-us/0f8e42b5-7a8c-4c30-8c98-7d2bdc8dcc68).  
  
## <a name="creating-a-new-project"></a>Yeni proje oluşturma  
 İlk adım, Excel VSTO eklenti projesindeki oluşturmaktır.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adlı Excel VSTO eklenti projesindeki oluşturun **ekleneceğinin veritabanından**, Visual Basic veya C# kullanarak.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio açılır `ThisAddIn.vb` veya `ThisAddIn.cs` dosya ve ekler **ekleneceğinin veritabanından** için proje **Çözüm Gezgini**.  
  
## <a name="creating-a-data-source"></a>Veri kaynağı oluşturma  
 Kullanım **veri kaynakları** penceresi türü belirtilmiş veri kümesi projenize ekleyin.  
  
#### <a name="to-add-a-typed-dataset-to-the-project"></a>Türü belirtilmiş veri kümesi projeye eklemek için  
  
1.  Varsa **veri kaynakları** pencere görünür değil, bunu, menü çubuğu seçme görüntülemek **Görünüm**, **diğer pencereler**, **veri kaynakları**.  
  
2.  Seçin **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı Yapılandırma Sihirbazı**.  
  
3.  Tıklatın **veritabanı**ve ardından **sonraki**.  
  
4.  Mevcut bir bağlantı varsa `AdventureWorksLT` veritabanı, bu bağlantıyı seçin ve tıklatın **sonraki**.  
  
     Aksi takdirde, tıklatın **yeni bağlantı**ve **Bağlantı Ekle** yeni bir bağlantı oluşturmak için iletişim kutusu. Daha fazla bilgi için bkz: [yeni bağlantılar eklemek](../data-tools/add-new-connections.md).  
  
5.  İçinde **bağlantı dizesini uygulama yapılandırma dosyasını Kaydet** sayfasında, **sonraki**.  
  
6.  İçinde **veritabanı nesnelerinizi** sayfasında **tabloları** seçip **adres (SalesLT)**.  
  
7.  **Son**'a tıklayın.  
  
     AdventureWorksLTDataSet.xsd dosyası eklenir **Çözüm Gezgini**. Bu dosya, aşağıdaki öğeleri tanımlar:  
  
    -   Adlı bir türü belirtilmiş veri `AdventureWorksLTDataSet`. Bu veri kümesi içeriğini temsil eden **adres (SalesLT)** AdventureWorksLT veritabanındaki tablo.  
  
    -   Adlı bir TableAdapter `AddressTableAdapter`. Bu TableAdapter okumak ve veri yazmak için kullanılan `AdventureWorksLTDataSet`. Daha fazla bilgi için bkz: [TableAdapter genel bakışı](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview).  
  
     Bu kılavuzda daha sonra bu nesnelerin her ikisi de kullanır.  
  
## <a name="creating-controls-and-binding-controls-to-data"></a>Denetimler oluşturma ve verilere denetimler bağlama  
 Bu kılavuz <xref:Microsoft.Office.Tools.Excel.ListObject> denetimi, kullanıcı çalışma kitabını açar açmaz seçtiğiniz tabloda tüm verileri görüntüler. Liste nesnesi kullanan bir <xref:System.Windows.Forms.BindingSource> denetimi veritabanına bağlanmak için.  
  
 Denetimlere veri bağlama hakkında daha fazla bilgi için bkz: [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
#### <a name="to-add-the-list-object-dataset-and-table-adapter"></a>Liste nesnesi, veri kümesi ve tablo bağdaştırıcısı eklemek için  
  
1.  İçinde `ThisAddIn` sınıfı, görüntülemek için aşağıdaki denetimleri bildirin `Address` tablosu `AdventureWorksLTDataSet` veri kümesi.  
  
     [!code-csharp[Trin_ExcelAddInDatabase#1](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#1)]
     [!code-vb[Trin_ExcelAddInDatabase#1](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#1)]  
  
2.  İçinde `ThisAddIn_Startup` yöntemi, veri kümesi başlatmak ve bilgileriyle veri kümesini doldurmak için aşağıdaki kodu ekleyin `AdventureWorksLTDataSet` veri kümesi.  
  
     [!code-csharp[Trin_ExcelAddInDatabase#2](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#2)]
     [!code-vb[Trin_ExcelAddInDatabase#2](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#2)]  
  
3.  Aşağıdaki kodu ekleyin `ThisAddIn_Startup` yöntemi. Bu, çalışma genişleten bir konak öğesi oluşturur. Daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
     [!code-csharp[Trin_ExcelAddInDatabase#3](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#3)]
     [!code-vb[Trin_ExcelAddInDatabase#3](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#3)]  
  
4.  Bir aralık oluşturun ve ekleme <xref:Microsoft.Office.Tools.Excel.ListObject> denetim.  
  
     [!code-csharp[Trin_ExcelAddInDatabase#4](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#4)]
     [!code-vb[Trin_ExcelAddInDatabase#4](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#4)]  
  
5.  Liste nesnesine bağlamak `AdventureWorksLTDataSet` kullanarak <xref:System.Windows.Forms.BindingSource>. Liste nesnesine bağlamak istediğiniz sütunlarının adlarını geçirin.  
  
     [!code-csharp[Trin_ExcelAddInDatabase#5](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#5)]
     [!code-vb[Trin_ExcelAddInDatabase#5](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#5)]  
  
## <a name="testing-the-add-in"></a>Eklentiyi test etme  
 Excel, açtığınızda <xref:Microsoft.Office.Tools.Excel.ListObject> denetimi görüntüler verilerden `Address` tablosu `AdventureWorksLTDataSet` veri kümesi.  
  
#### <a name="to-test-the-vsto-add-in"></a>VSTO eklenti sınamak için  
  
-   Tuşuna **F5**.  
  
     A <xref:Microsoft.Office.Tools.Excel.ListObject> adlı Denetim `addressListObject` çalışma sayfasında oluşturulur. Aynı anda, adında bir veri kümesi nesnesi `adventureWorksLTDataSet` ve <xref:System.Windows.Forms.BindingSource> adlı `addressBindingSource` projeye eklenir. <xref:Microsoft.Office.Tools.Excel.ListObject> Bağlı <xref:System.Windows.Forms.BindingSource>, sırayla bağlı veri kümesi nesnesi.  
  
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
 [Office çözümleri genel bakış yerel veritabanı dosyaları kullanma](../vsto/using-local-database-files-in-office-solutions-overview.md)   
 [Windows Forms uygulamalarındaki verilere bağlanma](/visualstudio/data-tools/connecting-to-data-in-windows-forms-applications)   
 [BindingSource Bileşenine Genel Bakış](/dotnet/framework/winforms/controls/bindingsource-component-overview)  
  
  