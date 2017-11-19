---
title: "İzlenecek yol: Belge düzeyi projede karmaşık veri bağlama | Microsoft Docs"
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
- data [Office development in Visual Studio], binding data
- complex data [Office development in Visual Studio]
- multiple column data binding [Office development in Visual Studio]
- data binding [Office development in Visual Studio], multiple columns
ms.assetid: 32ffad3d-fba4-476a-99b8-ef440434f4e1
caps.latest.revision: "50"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: dff7896b24508891a62ad3a0760880ed6a68a65a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-complex-data-binding-in-a-document-level-project"></a>İzlenecek Yol: Belge Düzeyi Projede Karmaşık Veri Bağlama
  Bu anlatımda belge düzeyi projede karmaşık veri bağlama ile ilgili temel bilgiler gösterilir. Microsoft Office Excel çalışma sayfasındaki birden çok hücreyi Northwind SQL Server veritabanındaki alanlara bağlayabilirsiniz.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Veri kaynağı çalışma kitabı projenize ekleme.  
  
-   Verilere bağlı denetimler çalışma sayfasına ekleme.  
  
-   Veri değişikliklerini veritabanına kaydetme.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)]veya [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
-   Northwind SQL Server örnek veritabanı sunucusuyla erişim.  
  
-   SQL Server veritabanına yazma ve okuma izni.  
  
## <a name="creating-a-new-project"></a>Yeni proje oluşturma  
 İlk adım, bir Excel çalışma kitabı projesi oluşturmaktır.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adında bir Excel çalışma kitabı projesi oluşturun **karmaşık veri bağlaması**. Sihirbazı'nda seçin **bir yeni belge oluşturun**.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio Tasarımcısı'nda yeni Excel çalışma kitabı açılır ve ekler **karmaşık veri bağlaması** için proje **Çözüm Gezgini**.  
  
## <a name="creating-the-data-source"></a>Veri Kaynağı Oluşturma  
 Kullanım **veri kaynakları** penceresi türü belirtilmiş veri kümesi projenize ekleyin.  
  
#### <a name="to-create-the-data-source"></a>Veri kaynağı oluşturmak için  
  
1.  Varsa **veri kaynakları** pencere görünür değil, bunu, menü çubuğu seçme görüntülemek **Görünüm**, **diğer pencereler**, **veri kaynakları**.  
  
2.  Seçin **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı Yapılandırma Sihirbazı**.  
  
3.  Seçin **veritabanı** ve ardından **sonraki**.  
  
4.  Northwind örnek SQL Server veritabanı için bir veri bağlantısı seçin veya yeni bir bağlantı kullanarak eklemek **yeni bağlantı** düğmesi.  
  
5.  Bir bağlantı seçili veya oluşturulduktan sonra tıklayın **sonraki**.  
  
6.  Bağlantı seçiliyse kaydetme seçeneğini ve ardından temizlemek **sonraki**.  
  
7.  Genişletme **tabloları** düğümünde **veritabanı nesnelerinin** penceresi.  
  
8.  Onay kutusunu işaretleyin **çalışanlar** tablo.  
  
9. **Son**'a tıklayın.  
  
 Sihirbaz ekler **çalışanlar** tablosu **veri kaynakları** penceresi. Projenize görünür türü belirtilmiş veri kümesi de ekler **Çözüm Gezgini**.  
  
## <a name="adding-controls-to-the-worksheet"></a>Çalışma sayfasına denetimler ekleme  
 Bir çalışma sayfası görüntülenir **çalışanlar** tablo çalışma kitabı açıldığında. Kullanıcılar verilerde değişiklik yapabilir ve ardından bir düğmeye tıklayarak bu değişiklikleri veritabanına kaydetmek mümkün olacaktır.  
  
 Çalışma tablosuna otomatik olarak bağlamak için ekleyebileceğiniz bir <xref:Microsoft.Office.Tools.Excel.ListObject> çalışma sayfasından denetimine **veri kaynakları** penceresi. Kullanıcı değişiklikleri kaydetme seçeneği vermek için add bir <xref:System.Windows.Forms.Button> gelen denetim **araç**.  
  
#### <a name="to-add-a-list-object"></a>Bir liste nesnesi eklemek için  
  
1.  Doğrulayın **My karmaşık veri Binding.xlsx** çalışma kitabı, Visual Studio Tasarımcısı'nda açık ile **Sheet1** görüntülenir.  
  
2.  Açık **veri kaynakları** penceresini açın ve select **çalışanlar** düğümü.  
  
3.  Görüntülenen açılan oku tıklatın.  
  
4.  Seçin **ListObject** aşağı açılan listesinde.  
  
5.  Sürükleme **çalışanlar** hücre tabloya **A6**.  
  
     A <xref:Microsoft.Office.Tools.Excel.ListObject> adlı Denetim `EmployeesListObject` hücresinde oluşturulur **A6**. Aynı zamanda bir <xref:System.Windows.Forms.BindingSource> adlı `EmployeesBindingSource`, bir tablo bağdaştırıcısı ve bir <xref:System.Data.DataSet> örneği projeye eklenir. Denetimin bağlı olduğu <xref:System.Windows.Forms.BindingSource>, sırayla bağlı <xref:System.Data.DataSet> örneği.  
  
#### <a name="to-add-a-button"></a>Düğme eklemek için  
  
1.  Gelen **ortak denetimler** sekmesinde **araç**, ekleme bir <xref:System.Windows.Forms.Button> hücre denetimine **A4** çalışma sayfasının.  
  
 Sonraki adım çalışma sayfası açıldığında düğme metni eklemektir.  
  
## <a name="initializing-the-control"></a>Denetimi başlatma  
 Düğmesini metin eklemek <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> olay işleyicisi.  
  
#### <a name="to-initialize-the-control"></a>Denetimi başlatmak için  
  
1.  İçinde **Çözüm Gezgini**, sağ **Sheet1.vb** veya **Sheet1.cs**ve ardından **görünümü kodu** kısayol menüsünde.  
  
2.  Aşağıdaki kodu ekleyin `Sheet1_Startup` b metnini ayarlamak için yöntemi`utton`.  
  
     [!code-csharp[Trin_VstcoreDataExcel#8](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet3.cs#8)]
     [!code-vb[Trin_VstcoreDataExcel#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet3.vb#8)]  
  
3.  Yalnızca C# ' ta için bir olay işleyicisi ekleme <xref:System.Windows.Forms.Control.Click> olaya `Sheet1_Startup` yöntemi.  
  
     [!code-csharp[Trin_VstcoreDataExcel#9](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet3.cs#9)]  
  
 Şimdi işlemek için kod ekleme <xref:System.Windows.Forms.Control.Click> düğmesinin olayı.  
  
## <a name="saving-changes-to-the-database"></a>Değişiklikler veritabanına kaydetme  
 Herhangi bir değişiklik yapılmıştır veritabanına geri açıkça kaydedilene kadar veri yalnızca yerel veri kümesindeki mevcut.  
  
#### <a name="to-save-changes-to-the-database"></a>Değişiklikleri veritabanına kaydetmek için  
  
1.  Bir olay işleyicisi ekleme <xref:System.Windows.Forms.Control.Click> b olay`utton`ve bir veri kümesini veritabanına yapılan tüm değişiklikleri uygulamak için aşağıdaki kodu ekleyin.  
  
     [!code-csharp[Trin_VstcoreDataExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet3.cs#10)]
     [!code-vb[Trin_VstcoreDataExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet3.vb#10)]  
  
## <a name="testing-the-application"></a>Uygulamayı Test Etme  
 Artık verilerin beklendiği gibi göründüğünü ve liste nesnesinde verileri işleyebileceğiniz doğrulamak için çalışma kitabınızı test edebilirsiniz.  
  
#### <a name="to-test-the-data-binding"></a>Veri bağlama test etmek için  
  
-   F5 tuşuna basın.  
  
     Çalışma kitabı açıldığında, liste nesnesinin verilerle doldurulduğunu doğrulayın **çalışanlar** tablo.  
  
#### <a name="to-modify-data"></a>Verileri değiştirmek için  
  
1.  Hücreyi tıklatın **B7**, adı içermelidir **doğan**.  
  
2.  Bir ad yazın **Anderson**, ve ardından ENTER tuşuna basın.  
  
#### <a name="to-modify-a-column-header"></a>Bir sütun başlığını değiştirmek için  
  
1.  Sütun üstbilgisini içeren bir hücreyi tıklatın **LastName**.  
  
2.  Tür **Soyadı**, iki sözcük arasında bir boşluk içeren ve ardından ENTER tuşuna basın.  
  
#### <a name="to-save-data"></a>Verileri kaydetmek için  
  
1.  Tıklatın **kaydetmek** çalışma sayfası üzerinde.  
  
2.  Excel çıkın. Tıklatın **Hayır** yaptığınız değişiklikleri kaydetmek isteyip istemediğiniz sorulduğunda.  
  
3.  Projeyi yeniden çalıştırmak için F5 tuşuna basın.  
  
     Liste nesnesi verilerle doldurulur **çalışanlar** tablo.  
  
4.  Dikkat hücresindeki **B7** hala **Anderson**, verileri olduğu değişiklik yapılan ve veritabanına kaydedilir. Sütun başlığı **LastName** geri özgün formuna boşluk, çünkü sütun başlığını veritabanına bağlı değil ve çalışma sayfasına yapılan değişiklikleri kaydetmedi değiştirildi.  
  
#### <a name="to-add-new-rows"></a>Yeni satır eklemek için  
  
1.  Liste nesnesi içinde bir hücre seçin.  
  
     Bir yıldız işareti listesinin altındaki yeni bir satır görüntülenir (**\***) ilk hücrenin içerdiği yeni bir satır.  
  
2.  Aşağıdaki bilgileri boş satır ekleyin.  
  
    |EmployeeID|Soyadı|FirstName|Başlık|  
    |----------------|--------------|---------------|-----------|  
    |10|Aslan|Halil|Satış Yöneticisi|  
  
#### <a name="to-delete-rows"></a>Satırları silmek için  
  
-   Numara 16 (satır 16) kadar sol tarafındaki çalışma sayfasının sağ tıklayın ve ardından **silmek**.  
  
#### <a name="to-sort-the-rows-in-the-list"></a>Listedeki satırları sıralamak için  
  
1.  Listenin içinde bir hücre seçin.  
  
     Ok düğmelerini kullanarak her sütun başlığı görüntülenir.  
  
2.  OK düğmesine **Soyadı** sütun başlığı.  
  
3.  Tıklatın **Sıralama artan**.  
  
     Satırları alfabetik olarak son adlarına göre sıralanır.  
  
#### <a name="to-filter-information"></a>Bilgileri filtrelemek için  
  
1.  Listenin içinde bir hücre seçin.  
  
2.  OK düğmesine **başlık** sütun başlığı.  
  
3.  Tıklatın **satış temsilcisi**.  
  
     Liste olan satırları gösterir **satış temsilcisi** içinde **başlık** sütun.  
  
4.  OK düğmesine **başlık** sütun başlığını tekrar.  
  
5.  Tıklatın **(Tümü)**.  
  
     Filtreleme kaldırılır ve tüm satırları görüntülenir.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu kılavuz bir tablo bir veritabanında bir liste nesnesine bağlamanın temelleri gösterir. Sonradan gelebilecek bazı görevler şunlardır:  
  
-   Böylece çevrimdışı kullanılabilir verileri önbelleğe alır. Daha fazla bilgi için bkz: [nasıl yapılır: bir sunucuya veya çevrimdışı kullanım için verileri önbelleğe](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md).  
  
-   Çözümü dağıtın. Daha fazla bilgi için bkz: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
-   Alan ve bir tablo arasında bir ana öğe/ayrıntı ilişkisi oluşturun. Daha fazla bilgi için bkz: [izlenecek yol: bir ana ayrıntı ilişkisi kullanarak önbelleğe alınmış bir veri kümesi oluşturma](../vsto/walkthrough-creating-a-master-detail-relation-using-a-cached-dataset.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Office çözümlerindeki veriler](../vsto/data-in-office-solutions.md)   
 [İzlenecek yol: Belge düzeyi projede basit veri bağlama](../vsto/walkthrough-simple-data-binding-in-a-document-level-project.md)  
  
  