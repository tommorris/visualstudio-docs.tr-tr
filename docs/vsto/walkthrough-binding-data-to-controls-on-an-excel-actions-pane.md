---
title: "İzlenecek yol: Excel eylemler bölmesindeki denetimlere veri bağlama | Microsoft Docs"
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
- controls [Office development in Visual Studio], data binding
- actions panes [Office development in Visual Studio], data binding
- data binding [Office development in Visual Studio], smart documents
- data binding [Office development in Visual Studio], actions panes
- actions panes [Office development in Visual Studio], binding controls
- smart documents [Office development in Visual Studio], data binding
ms.assetid: 106c07bd-e931-4dc5-94dc-ca43900fe09d
caps.latest.revision: "63"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 11a9f55691416a1b7775e0ff9d392293d9fee33f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-binding-data-to-controls-on-an-excel-actions-pane"></a>İzlenecek Yol: Excel Eylemler Bölmesindeki Denetimlere Veri Bağlama
  Bu kılavuz, Microsoft Office Excel eylemler bölmesindeki denetimlere veri bağlama gösterir. Denetimler, SQL Server veritabanındaki tablolar arasındaki ana/ayrıntı ilişkisi gösterir.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Bir çalışma sayfasına denetimler ekleme.  
  
-   Eylemler bölmesi denetimi oluşturma  
  
-   Eylemler bölmesi denetimine veri bağlantılı Windows Forms denetimleri ekleme.  
  
-   Uygulama açıldığında eylemler bölmesini gösterme.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)]veya [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
-   Northwind SQL Server örnek veritabanı sunucusuyla erişim.  
  
-   SQL Server veritabanına yazma ve okuma izni.  
  
## <a name="creating-the-project"></a>Projeyi Oluşturma  
 İlk adım, bir Excel çalışma kitabı projesi oluşturmaktır.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adında bir Excel çalışma kitabı projesi oluşturun **My Excel eylemler bölmesindeki**. Sihirbazı'nda seçin **bir yeni belge oluşturun**. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio Tasarımcısı'nda yeni Excel çalışma kitabı açılır ve ekler **My Excel eylemler bölmesindeki** için proje **Çözüm Gezgini**.  
  
## <a name="adding-a-new-data-source-to-the-project"></a>Projeye yeni bir veri kaynağı ekleme  
  
#### <a name="to-add-a-new-data-source-to-the-project"></a>Yeni bir veri kaynağı projeye eklemek için  
  
1.  Varsa **veri kaynakları** pencere görünür değil, bunu, menü çubuğu seçme görüntülemek **Görünüm**, **diğer pencereler**, **veri kaynakları**.  
  
2.  Seçin **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı Yapılandırma Sihirbazı**.  
  
3.  Seçin **veritabanı** ve ardından **sonraki**.  
  
4.  Northwind örnek SQL Server veritabanı için bir veri bağlantısı seçin veya yeni bir bağlantı kullanarak eklemek **yeni bağlantı** düğmesi.  
  
5.  **İleri**'ye tıklayın.  
  
6.  Bağlantı seçiliyse kaydetme seçeneğini ve ardından temizlemek **sonraki**.  
  
7.  Genişletme **tabloları** düğümünde **veritabanı nesnelerinin** penceresi.  
  
8.  Onay kutusunu işaretleyin **Üreticiler** tablo.  
  
9. Genişletme **ürünleri** tablo ve seçin **ProductName**, **SupplierID**, **QuantityPerUnit**, ve **UnitPrice**.  
  
10. **Son**'a tıklayın.  
  
 Sihirbaz ekler **Üreticiler** tablo ve **ürünleri** tablosu **veri kaynakları** penceresi. Projenize görünür türü belirtilmiş veri kümesi de ekler **Çözüm Gezgini**.  
  
## <a name="adding-controls-to-the-worksheet"></a>Çalışma sayfasına denetimler ekleme  
 Ardından, eklemek bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetim ve <xref:Microsoft.Office.Tools.Excel.ListObject> ilk çalışma denetimi.  
  
#### <a name="to-add-a-namedrange-control-and-a-listobject-control"></a>NamedRange denetimi ve ListObject denetimleri ekleme  
  
1.  Doğrulayın **My Excel Eylemler Pane.xlsx** çalışma kitabı, Visual Studio Tasarımcısı'nda açık ile `Sheet1` görüntülenir.  
  
2.  İçinde **veri kaynakları** penceresinde genişletin **Üreticiler** tablo.  
  
3.  Aşağı açılan oku tıklatın **şirket adı** düğümünü ve ardından **NamedRange**.  
  
4.  Sürükleme **şirket adı** gelen **veri kaynakları** hücre penceresine **A2** içinde `Sheet1`.  
  
     A <xref:Microsoft.Office.Tools.Excel.NamedRange> adlı Denetim `CompanyNameNamedRange` oluşturulduğu ve metin \<ŞirketAdı > hücrede görünür **A2**. Aynı zamanda bir <xref:System.Windows.Forms.BindingSource> adlı `suppliersBindingSource`, bir tablo bağdaştırıcısı ve bir <xref:System.Data.DataSet> projeye eklenir. Denetimin bağlı olduğu <xref:System.Windows.Forms.BindingSource>, sırayla bağlı <xref:System.Data.DataSet> örneği.  
  
5.  İçinde **veri kaynakları** penceresinde, aşağı altında olan sütunlar geçmiş **Üreticiler** tablo. Listenin en altta **ürünleri** tablo; bir alt öğesi değil çünkü **Üreticiler** tablo. Bunu seçin **ürünleri** tablosu, aynı düzeyde olanı değil **Üreticiler** tablo ve görüntülenen açılan oku tıklatın.  
  
6.  Tıklatın **ListObject** aşağı açılan listeyi ve ardından sürükleyin **ürünleri** hücre tabloya **A6** içinde `Sheet1`.  
  
     A <xref:Microsoft.Office.Tools.Excel.ListObject> adlı Denetim `ProductNameListObject` hücresinde oluşturulur **A6**. Aynı zamanda bir <xref:System.Windows.Forms.BindingSource> adlı `productsBindingSource` ve bir tablo bağdaştırıcısı projeye eklenir. Denetimin bağlı olduğu <xref:System.Windows.Forms.BindingSource>, sırayla bağlı <xref:System.Data.DataSet> örneği.  
  
7.  Yalnızca C# ' ta seçin **suppliersBindingSource** bileşen ve değişiklik **değiştiricileri** özelliğine **dahili** içinde **özellikleri** penceresi.  
  
## <a name="adding-controls-to-the-actions-pane"></a>Eylemler bölmesine denetimleri ekleme  
 Ardından, açılan kutu içeren eylemler bölmesi denetimi gerekir.  
  
#### <a name="to-add-an-actions-pane-control"></a>Eylemler bölmesi denetimi eklemek için  
  
1.  Seçin **My Excel eylemler bölmesindeki** proje **Çözüm Gezgini**.  
  
2.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  
  
3.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **Eylemler bölmesi denetimi**, adlandırın **ActionsControl**, tıklatıp **Ekle**.  
  
#### <a name="to-add-data-bound-windows-forms-controls-to-an-actions-pane-control"></a>Eylemler bölmesi denetimine veri bağlantılı Windows Forms denetimleri ekleme  
  
1.  Gelen **ortak denetimler** sekmelerinde **araç**, sürükleyin bir <xref:System.Windows.Forms.ComboBox> Eylemler bölmesi denetimi için denetim.  
  
2.  Değişiklik **boyutu** özelliğine **171, 21**.  
  
3.  Kullanıcı denetimi birleşik giriş kutusu uyacak şekilde yeniden boyutlandırın.  
  
## <a name="binding-the-control-on-the-actions-pane-to-data"></a>Eylemler bölmesinde denetiminde veri bağlama  
 Bu bölümde, veri kaynağı ayarlayacaksınız <xref:System.Windows.Forms.ComboBox> aynı veri kaynağı için <xref:Microsoft.Office.Tools.Excel.NamedRange> çalışma sayfası üzerinde denetim.  
  
#### <a name="to-set-data-binding-properties-of-the-control"></a>Veri bağlama denetimi özelliklerini ayarlamak için  
  
1.  Eylemler bölmesi denetimine sağ tıklayın ve ardından **görünümü kodu**.  
  
2.  Aşağıdaki kodu ekleyin <xref:System.Windows.Forms.UserControl.Load> Eylemler bölmesi denetiminin olay.  
  
     [!code-vb[Trin_VstcoreActionsPaneExcel#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ActionsControl.vb#1)]
     [!code-csharp[Trin_VstcoreActionsPaneExcel#1](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ActionsControl.cs#1)]  
  
3.  C# ' ta için bir olay işleyicisi oluşturmalısınız `ActionsControl`. Bu kodu koyabilirsiniz `ActionsControl` Oluşturucusu. Olay işleyicileri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#2](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ActionsControl.cs#2)]  
  
## <a name="showing-the-actions-pane"></a>Eylemler bölmesini gösterme  
 Çalışma zamanında denetim ekleme kadar Eylemler bölmesinde görünür değil.  
  
#### <a name="to-show-the-actions-pane"></a>Eylemler bölmesini göstermek için  
  
1.  İçinde **Çözüm Gezgini**ThisWorkbook.vb veya ThisWorkbook.cs sağ tıklayın ve ardından **görünümü kodu**.  
  
2.  Kullanıcı denetiminde yeni bir örneğini oluşturmak `ThisWorkbook` sınıfı.  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#3](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#3)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#3)]  
  
3.  İçinde <xref:Microsoft.Office.Tools.Excel.Workbook.Startup> olay işleyicisi `ThisWorkbook`, Eylemler bölmesi denetimi ekleyin.  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#4](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#4)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#4)]  
  
## <a name="testing-the-application"></a>Uygulamayı Test Etme  
 Artık belge açıldığında eylemler bölmesini açar ve denetimlerin bir ana öğe/ayrıntı ilişkisi olduğunu doğrulamak için belgenizi test edebilirsiniz.  
  
#### <a name="to-test-your-document"></a>Belgenizi test etmek için  
  
1.  Projenizi çalıştırmak için F5 tuşuna basın.  
  
2.  Eylemler bölmesinde görünür olduğunu doğrulayın.  
  
3.  Bir şirket liste kutusunda seçin. Şirket adı olarak listelendiğini doğrulayın <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi ve ürün ayrıntıları listelenen <xref:Microsoft.Office.Tools.Excel.ListObject> denetim.  
  
4.  Şirket adını doğrulamak için çeşitli şirketler seçin ve ürün ayrıntıları uygun şekilde değiştirin.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Sonradan gelebilecek bazı görevler şunlardır:  
  
-   Word'de denetimlere veri bağlama. Daha fazla bilgi için bkz: [izlenecek yol: Word eylemler bölmesindeki denetimlere veri bağlama](../vsto/walkthrough-binding-data-to-controls-on-a-word-actions-pane.md).  
  
-   Projeyi dağıtma. Daha fazla bilgi için bkz: [tarafından ClickOnce kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md)   
 [Nasıl yapılır: Eylemler bölmesindeki denetim düzenini yönetme](../vsto/how-to-manage-control-layout-on-actions-panes.md)   
 [Office Çözümlerinde Verileri Denetimlere Bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  