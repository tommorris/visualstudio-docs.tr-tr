---
title: 'İzlenecek yol: Belge düzeyi projede basit veri bağlama'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data binding [Office development in Visual Studio], worksheet cell to Database field
- worksheets [Office development in Visual Studio], binding worksheet cell to Database field
- Database field [Office development in Visual Studio]
- data [Office development in Visual Studio], binding data
- simple data binding [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1cae2ba32be73972e6c716e9100120514a6346cf
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35258148"
---
# <a name="walkthrough-simple-data-binding-in-a-document-level-project"></a>İzlenecek yol: Belge düzeyi projede basit veri bağlama
  Bu anlatımda bir belge düzeyi projede veri bağlama ile ilgili temel bilgiler gösterilir. Microsoft Office Excel adlandırılmış aralıkta bir SQL Server veritabanı bir tek veri alanına bağlı. İzlenecek yol da tablosundaki tüm kayıtları arasında kaydırma sağlayan denetimlerin nasıl ekleneceğini gösterir.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Excel projesi için bir veri kaynağı oluşturuluyor.  
  
-   Bir çalışma sayfasına denetimler ekleme.  
  
-   Veritabanı kayıtları arasında kaydırma.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] veya [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
-   Northwind SQL Server örnek veritabanı sunucusuyla erişim.  
  
-   SQL Server veritabanına yazma ve okuma izni.  
  
## <a name="create-a-new-project"></a>Yeni bir proje oluşturma  
 Bu adımda, bir Excel çalışma kitabı projesi oluşturur.  
  
### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adında bir Excel çalışma kitabı projesi oluşturun **basit veri bağlaması**, Visual Basic veya C# kullanarak. Olduğundan emin olun **bir yeni belge oluşturun** seçilir. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio oluşturma Office projelerinde](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Visual Studio Tasarımcısı'nda yeni Excel çalışma kitabı açılır ve ekler **basit veri bağlaması** için proje **Çözüm Gezgini**.  
  
## <a name="create-the-data-source"></a>Veri kaynağı oluşturun  
 Kullanım **veri kaynakları** penceresi türü belirtilmiş veri kümesi projenize ekleyin.  
  
### <a name="to-create-the-data-source"></a>Veri kaynağı oluşturmak için  
  
1.  Varsa **veri kaynakları** pencere görünür değil, bunu, menü çubuğu seçme görüntülemek **Görünüm** > **diğer pencereler**  >   **Veri kaynakları**.  
  
2.  Seçin **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı Yapılandırma Sihirbazı**.  
  
3.  Seçin **veritabanı** ve ardından **sonraki**.  
  
4.  Northwind örnek SQL Server veritabanı için bir veri bağlantısı seçin veya yeni bir bağlantı kullanarak ekleyin **yeni bağlantı** düğmesi.  
  
5.  Bir bağlantı seçili veya oluşturulduktan sonra tıklayın **sonraki**.  
  
6.  Bağlantı seçiliyse kaydetme seçeneğini ve ardından temizlemek **sonraki**.  
  
7.  Genişletme **tabloları** düğümünde **veritabanı nesnelerinin** penceresi.  
  
8.  Onay kutusunu işaretleyin **müşteriler** tablo.  
  
9. **Son**'a tıklayın.  
  
 Sihirbaz ekler **müşteriler** tablosu **veri kaynakları** penceresi. Projenize görünür türü belirtilmiş veri kümesi de ekler **Çözüm Gezgini**.  
  
## <a name="add-controls-to-the-worksheet"></a>Çalışma sayfasına denetimler ekleme  
 Bu kılavuz için iki adlandırılmış aralıkları ve ilk çalışma sayfasında dört düğmeleri gerekir. İlk olarak, iki adlandırılmış aralığından ekleyin **veri kaynakları** penceresi böylece otomatik olarak bir veri kaynağına bağlanabilir. Ardından, düğmelerden eklemek **araç**.  
  
### <a name="to-add-two-named-ranges"></a>İki adlandırılmış aralıkları eklemek için  
  
1.  Doğrulayın *My basit veri Binding.xlsx* çalışma kitabı, Visual Studio Tasarımcısı'nda açık ile **Sheet1** görüntülenir.  
  
2.  Açık **veri kaynakları** penceresi ve genişletin **müşteriler** düğümü.  
  
3.  Seçin **ŞirketAdı** sütun ve görüntülenen açılan oku tıklatın.  
  
4.  Seçin **NamedRange** aşağı açılan listeyi ve ardından sürükleyin **ŞirketAdı** hücre sütun **A1**.  
  
     A <xref:Microsoft.Office.Tools.Excel.NamedRange> adlı Denetim `companyNameNamedRange` hücresinde oluşturulur **A1**. Aynı zamanda bir <xref:System.Windows.Forms.BindingSource> adlı `customersBindingSource`, bir tablo bağdaştırıcısı ve bir <xref:System.Data.DataSet> örneği projeye eklenir. Denetimin bağlı olduğu <xref:System.Windows.Forms.BindingSource>, sırayla bağlı <xref:System.Data.DataSet> örneği.  
  
5.  Seçin **CustomerID** sütununda **veri kaynakları** penceresinde ve görüntülenen açılan oku tıklatın.  
  
6.  Tıklatın **NamedRange** aşağı açılan listeyi ve ardından sürükleyin **CustomerID** hücre sütun **B1**.  
  
7.  Başka bir <xref:Microsoft.Office.Tools.Excel.NamedRange> adlı Denetim `customerIDNamedRange` hücresinde oluşturulur **B1**ve bağlı <xref:System.Windows.Forms.BindingSource>.  
  
### <a name="to-add-four-buttons"></a>Dört düğmeleri eklemek için  
  
1.  Gelen **ortak denetimler** sekmesinde **araç**, ekleme bir <xref:System.Windows.Forms.Button> hücre denetimine **A3** çalışma sayfasının.  
  
     Bu düğme adlı `Button1`.  
  
2.  Adları gösterildiği gibi; böylece bu sırayla aşağıdaki hücrelere üç daha fazla düğme ekleyin:  
  
    |Hücre|(Ad)|  
    |----------|--------------|  
    |B3|BUTTON2|  
    |C3|Button3|  
    |D3|Button4|  
  
 Düğmelere metin eklemek ve C# ' ta olay işleyicileri eklemek için sonraki adımdır bakın.  
  
## <a name="initialize-the-controls"></a>Denetimleri başlatmak  
 Düğme metni ayarlayın ve sırasında olay işleyicileri ekleyin <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> olay.  
  
### <a name="to-initialize-the-controls"></a>Denetimleri başlatmak için  
  
1.  İçinde **Çözüm Gezgini**, sağ **Sheet1.vb** veya **Sheet1.cs**ve ardından **görünümü kodu** kısayol menüsünde.  
  
2.  Aşağıdaki kodu ekleyin `Sheet1_Startup` her düğme metni ayarlamak için yöntem.  
  
     [!code-csharp[Trin_VstcoreDataExcel#2](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#2)]
     [!code-vb[Trin_VstcoreDataExcel#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#2)]  
  
3.  Yalnızca C# ' ta düğme için olay işleyicileri olayları eklemek `Sheet1_Startup` yöntemi.  
  
     [!code-csharp[Trin_VstcoreDataExcel#3](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#3)]  
  
 Şimdi işlemek için kod ekleme <xref:System.Windows.Forms.Control.Click> olayları düğmelerin kullanıcı kayıtlarda gözatabilirsiniz.  
  
## <a name="add-code-to-enable-scrolling-through-the-records"></a>Kayıtlarda gezinmeye olanak sağlamak için kod ekleme  
 Kodu ekleyin <xref:System.Windows.Forms.Control.Click> kayıtlar arasında gezinmek için her düğmenin olay işleyicisi.  
  
### <a name="to-move-to-the-first-record"></a>İlk kaydı taşımak için  
  
1.  Bir olay işleyicisi ekleme <xref:System.Windows.Forms.Control.Click> olayı `Button1` düğmesine tıklayın ve ilk kaydı taşımak için aşağıdaki kodu ekleyin:  
  
     [!code-csharp[Trin_VstcoreDataExcel#4](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#4)]
     [!code-vb[Trin_VstcoreDataExcel#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#4)]  
  
### <a name="to-move-to-the-previous-record"></a>Önceki kayda taşımak için  
  
1.  Bir olay işleyicisi ekleme <xref:System.Windows.Forms.Control.Click> olayı `Button2` düğmesine tıklayın ve konumu tarafından geri taşımak için aşağıdaki kodu ekleyin:  
  
     [!code-csharp[Trin_VstcoreDataExcel#5](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#5)]
     [!code-vb[Trin_VstcoreDataExcel#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#5)]  
  
### <a name="to-move-to-the-next-record"></a>Sonraki kayda taşımak için  
  
1.  Bir olay işleyicisi ekleme <xref:System.Windows.Forms.Control.Click> olayı `Button3` düğmesine tıklayın ve konumu tarafından ilerletmek için aşağıdaki kodu ekleyin:  
  
     [!code-csharp[Trin_VstcoreDataExcel#6](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#6)]
     [!code-vb[Trin_VstcoreDataExcel#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#6)]  
  
### <a name="to-move-to-the-last-record"></a>Son kaydı taşımak için  
  
1.  Bir olay işleyicisi ekleme <xref:System.Windows.Forms.Control.Click> olayı `Button4` düğmesine tıklayın ve son kayda gitmek için aşağıdaki kodu ekleyin:  
  
     [!code-csharp[Trin_VstcoreDataExcel#7](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#7)]
     [!code-vb[Trin_VstcoreDataExcel#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#7)]  
  
## <a name="test-the-application"></a>Uygulamayı test etme  
 Artık veritabanındaki kayıtları aracılığıyla göz atabilirsiniz emin olmak için çalışma kitabınızı test edebilirsiniz.  
  
### <a name="to-test-your-workbook"></a>Çalışma kitabınız sınamak için  
  
1.  Tuşuna **F5** projeyi çalıştırın.  
  
2.  İlk kaydı hücrelerde görüntülendiğini doğrulamak **A1** ve **B1**.  
  
3.  Tıklatın **>** (`Button3`) düğmesine tıklayın ve sonraki kaydın hücresinde göründüğünü doğrulayın **A1** ve **B1**.  
  
4.  Diğer kaydırma düğmelerini kaydı beklendiği gibi değişiklikleri onaylamak için tıklatın.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 Bu kılavuz bir alanda bir veritabanı için adlandırılmış bir aralık bağlamanın temelleri gösterir. Sonradan gelebilecek bazı görevler şunlardır:  
  
-   Böylece çevrimdışı kullanılabilir verileri önbelleğe alır. Daha fazla bilgi için bkz: [nasıl yapılır: çevrimdışı veya sunucuda kullanmak için verileri önbelleğe](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md).  
  
-   Bir tablodaki birden çok sütun hücrelere yerine bir alana bağlayın. Daha fazla bilgi için bkz: [izlenecek yol: belge düzeyi projede karmaşık veri bağlama](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md).  
  
-   Kullanım bir <xref:System.Windows.Forms.BindingNavigator> kayıtlar arasında gezinmek için denetimi. Daha fazla bilgi için bkz: [nasıl yapılır: Windows Forms BindingNavigator denetimi ile verilerde gezinme](/dotnet/framework/winforms/controls/bindingnavigator-control-overview-windows-forms).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Office çözümlerindeki veriler](../vsto/data-in-office-solutions.md)   
 [İzlenecek yol: Belge düzeyi projede karmaşık veri bağlama](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md)  
  
  