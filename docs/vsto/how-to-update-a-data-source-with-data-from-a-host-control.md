---
title: "Nasıl yapılır: konak kontrolü verileriyle veri kaynağını güncelleme | Microsoft Docs"
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
- documents [Office development in Visual Studio], data source updates
- data [Office development in Visual Studio], updating a data source from a document
- host controls [Office development in Visual Studio], data source updates
- Office documents [Office development in Visual Studio, data sources
ms.assetid: b91025af-1eaa-44ee-88f2-71ecaa7a0440
caps.latest.revision: "53"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: eff45d9b2c8dbac0aade12a003008dd9b2c29fb2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-update-a-data-source-with-data-from-a-host-control"></a>Nasıl Yapılır: Konak Kontrolü Verileriyle Veri Kaynağını Güncelleme
  Konak kontrolü bir veri kaynağına bağlama ve veri kaynağı denetimi verilerde yapılan değişikliklerle güncelleştirin. Bu işlemde iki ana adım vardır:  
  
1.  Bellek içi veri kaynağı denetiminde değiştirilen verileri ile güncelleştirin. Genellikle, bellek içi veri kaynağı olan bir <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, ya da başka bir veri nesnesi.  
  
2.  Veritabanı bellek içi veri kaynağında değiştirilen verileri ile güncelleştirin. Bu, yalnızca veri kaynağı bir SQL Server veya Microsoft Office Access veritabanı gibi bir arka uç veritabanı bağlıysa geçerlidir.  
  
 Konak denetimleri ve veri bağlama hakkında daha fazla bilgi için bkz: [konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md) ve [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
## <a name="updating-the-in-memory-data-source"></a>Bellek içi veri kaynağını güncelleme  
 Varsayılan olarak, basit veri bağlama (örneğin, bir Word belgesi içerik denetimlerinde veya adlandırılmış aralık denetimi bir Excel çalışma sayfası üzerinde) etkinleştirmek ana bilgisayar denetimleri bellek içi veri kaynağına veri değişikliklerini kaydetmeyin. Diğer bir deyişle, son kullanıcının bir konak kontrolü değerinde değiştirir ve denetimden gider, yeni değer denetiminde veri kaynağına otomatik olarak kaydedilmez.  
  
 Veri kaynağı için verileri kaydetmek için çalışma zamanında belirli bir olaya yanıt olarak veri kaynağını güncelleştirir kod yazabilirsiniz veya denetimdeki değeri değiştiğinde veri kaynağını otomatik olarak güncelleştirmek için denetimi yapılandırabilirsiniz.  
  
 Kaydet gerekmez <xref:Microsoft.Office.Tools.Excel.ListObject> bellek içi veri kaynağına değiştirir. Bağladığınızda bir <xref:Microsoft.Office.Tools.Excel.ListObject> veri denetimine <xref:Microsoft.Office.Tools.Excel.ListObject> denetim otomatik olarak değişiklikleri kaydeder bellek içi veri kaynağına ek kod gerek kalmadan.  
  
#### <a name="to-update-the-in-memory-data-source-at-run-time"></a>Çalışma zamanında bellek içi veri kaynağını güncelleştirmek için  
  
-   Çağrı <xref:System.Windows.Forms.Binding.WriteValue%2A> yöntemi <xref:System.Windows.Forms.Binding> denetimi veri kaynağına bağlar nesnesi.  
  
     Aşağıdaki örnek yapılan değişiklikleri kaydeder bir <xref:Microsoft.Office.Tools.Excel.NamedRange> veri kaynağı bir Excel çalışma sayfası üzerinde denetim. Bu örnek, sahibi olduğunuzu varsayar. bir <xref:Microsoft.Office.Tools.Excel.NamedRange> adlı Denetim `namedRange1` ile kendi <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> özelliği ilişkili bir veri kaynağında bir alan için.  
  
     [!code-csharp[Trin_VstcoreDataExcel#1](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#1)]
     [!code-vb[Trin_VstcoreDataExcel#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#1)]  
  
### <a name="automatically-updating-the-in-memory-data-source"></a>Otomatik olarak bellek içi veri kaynağını güncelleme  
 Bellek içi veri kaynağını otomatik olarak güncelleştirilebilir bir denetimi de yapılandırabilirsiniz. Belge düzeyi projede kodu veya tasarımcıyı kullanarak bunu yapabilirsiniz. Bir VSTO eklenti projesinde kodu kullanmanız gerekir.  
  
##### <a name="to-set-a-control-to-automatically-update-the-in-memory-data-source-by-using-code"></a>Kod kullanarak bellek içi veri kaynağını otomatik olarak güncelleştirmek üzere bir denetim ayarlamak için  
  
1.  Modunu kullanmak <xref:System.Windows.Forms.Binding> denetimi veri kaynağına bağlar nesnesi. Veri kaynağını güncelleştirmek için iki seçenek vardır:  
  
    -   Denetim doğrulandığında veri kaynağını güncelleştirmek için bu özelliği System.Windows.Forms.DataSourceUpdateMode.OnValidation ayarlayın.  
  
    -   Denetimin veri bağlama özelliğinin değeri değiştiğinde veri kaynağını güncelleştirmek için bu özelliği System.Windows.Forms.DataSourceUpdateMode.OnPropertyChanged ayarlayın.  
  
        > [!NOTE]  
        >  Word Belge değişikliği veya denetim değişikliği bildirimlerini yaptığından System.Windows.Forms.DataSourceUpdateMode.OnPropertyChanged seçeneği Word konak denetimleri için geçerli değildir. Ancak, bu seçenek, Word belgelerindeki Windows Forms denetimleri için kullanılabilir.  
  
     Aşağıdaki örnek yapılandırır bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetiminde değeri değiştiğinde veri kaynağını otomatik olarak güncelleştirmek için denetim. Bu örnek, sahibi olduğunuzu varsayar. bir <xref:Microsoft.Office.Tools.Excel.NamedRange> adlı Denetim `namedRange1` ile kendi <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> özelliği ilişkili bir veri kaynağında bir alan için.  
  
     [!code-csharp[Trin_VstcoreDataExcel#19](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#19)]
     [!code-vb[Trin_VstcoreDataExcel#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#19)]  
  
##### <a name="to-set-a-control-to-automatically-update-the-in-memory-data-source-by-using-the-designer"></a>Bellek içi veri kaynağı Tasarımcısı'nı kullanarak otomatik olarak güncelleştirmek üzere bir denetim ayarlamak için  
  
1.  Visual Studio'da Word belgesi veya Excel çalışma kitabı tasarımcısında açın.  
  
2.  Veri kaynağını otomatik olarak güncelleştirmek istediğiniz denetimi tıklatın.  
  
3.  İçinde **özellikleri** penceresinde genişletin **(veri bağlamaları)** özelliği.  
  
4.  Yanına **(Gelişmiş)** özelliği, üç nokta düğmesini (![VisualStudioEllipsesButton ekran](../vsto/media/vbellipsesbutton.png "VisualStudioEllipsesButton ekran")).  
  
5.  İçinde **biçimlendirme ve Gelişmiş bağlama** iletişim kutusu, tıklatın **veri kaynağı güncelleme modu** aşağı açılan liste ve aşağıdaki değerlerden birini seçin:  
  
    -   Denetim doğrulandığında veri kaynağını güncelleştirmek için seçin **OnValidation'ı**.  
  
    -   Denetimin veri bağlama özelliğinin değeri değiştiğinde veri kaynağını güncelleştirmek için seçin **OnPropertyChanged**.  
  
        > [!NOTE]  
        >  **OnPropertyChanged** seçeneği Word Belge değişikliği veya denetim değişikliği bildirimlerini yaptığından Word konak denetimleri için uygulanmaz. Ancak, bu seçenek, Word belgelerindeki Windows Forms denetimleri için kullanılabilir.  
  
6.  Kapat **biçimlendirme ve Gelişmiş bağlama** iletişim kutusu.  
  
## <a name="updating-the-database"></a>Veritabanını güncelleştirme  
 Bellek içi veri kaynağı bir veritabanı ile ilişkili ise, veri kaynağına yapılan değişikliklerle veritabanı güncelleştirmeniz gerekir. Bir veritabanı güncelleştirme hakkında daha fazla bilgi için bkz: [verileri veritabanına kaydetmek](../data-tools/save-data-back-to-the-database.md) ve [TableAdapter kullanarak veri güncelleştirme](../data-tools/update-data-by-using-a-tableadapter.md) .  
  
#### <a name="to-update-the-database"></a>Veritabanını güncellemek için  
  
1.  Çağrı <xref:System.Windows.Forms.BindingSource.EndEdit%2A> yöntemi <xref:System.Windows.Forms.BindingSource> denetimi için.  
  
     <xref:System.Windows.Forms.BindingSource> , Veri bağlama denetimi bir belge veya çalışma kitabına tasarım zamanında eklediğinizde, otomatik olarak oluşturulur. <xref:System.Windows.Forms.BindingSource> Denetimi projenizdeki türü belirtilmiş veri kümesi bağlanır. Daha fazla bilgi için bkz: [BindingSource bileşenine genel bakış](/dotnet/framework/winforms/controls/bindingsource-component-overview).  
  
     Aşağıdaki kod örneği, projenizin içerdiğini varsayar bir <xref:System.Windows.Forms.BindingSource> adlı `customersBindingSource`.  
  
     [!code-csharp[Trin_VstcoreDataExcel#20](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#20)]
     [!code-vb[Trin_VstcoreDataExcel#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#20)]  
  
2.  Çağrı `Update` projenizdeki oluşturulan TableAdapter yöntemi.  
  
     Veri bağlama denetimi bir belge veya çalışma kitabına tasarım zamanında eklerken TableAdapter otomatik olarak oluşturulur. TableAdapter projenizdeki türü belirtilmiş veri kümesi veritabanına bağlar. Daha fazla bilgi için bkz: [TableAdapter genel bakışı](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview).  
  
     Aşağıdaki kod örneği Northwind veritabanında Customers tablosuna bir bağlantı varsa ve projenizi adlı bir TableAdapter içeren varsayar `customersTableAdapter` ve adlı türü belirtilmiş bir veri kümesi `northwindDataSet`.  
  
     [!code-csharp[Trin_VstcoreDataExcel#21](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#21)]
     [!code-vb[Trin_VstcoreDataExcel#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#21)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Veritabanına veri kaydetme](../data-tools/save-data-back-to-the-database.md)    
 [TableAdapter kullanarak veri güncelleştirme](../data-tools/update-data-by-using-a-tableadapter.md)    
 [Nasıl yapılır: çalışma sayfasındaki veritabanı kayıtları arasında kaydırma](../vsto/how-to-scroll-through-database-records-in-a-worksheet.md)   
 [Nasıl yapılır: çalışma sayfalarını veritabanı verileriyle doldurma](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)   
 [Nasıl yapılır: belgeleri nesne verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-objects.md)   
 [Nasıl yapılır: belgeleri veritabanı verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [Nasıl Yapılır: Belgeleri Hizmet Verileriyle Doldurma](../vsto/how-to-populate-documents-with-data-from-services.md)  
  
  