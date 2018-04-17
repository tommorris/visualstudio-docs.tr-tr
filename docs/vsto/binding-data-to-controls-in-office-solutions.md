---
title: Office çözümlerinde denetimlere veri bağlama | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office documents [Office development in Visual Studio], connecting to data
- data, data binding
- data binding
- data binding, Office solutions
- data binding, controls
- Office applications [Office development in Visual Studio], data binding
- controls, data binding
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ea9d344e3b36d9d46ea5a5adcb642e43687b75ee
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="binding-data-to-controls-in-office-solutions"></a>Office Çözümlerinde Verileri Denetimlere Bağlama
  Windows Forms denetimlerini bağlayabilirsiniz ve *konak denetimlerini* Microsoft Office Word belgesine veya Microsoft Office Excel çalışma sayfasındaki denetimleri otomatik olarak verileri görüntülemek için bir veri kaynağına. Uygulama düzeyi ve belge düzeyi projelerine denetimlere veri bağlayabilirsiniz.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Konak denetimleri Word ve Excel nesne modellerindeki gibi içerik denetimleri Word ve Excel aralıklarında adlı nesneleri genişletir. Daha fazla bilgi için bkz: [konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
 Konak denetimlerinin ve Windows Forms destekler Windows Forms veri bağlama modelini kullanmak *basit veri bağlama* ve *karmaşık veri bağlama* veri kümeleri ve veri tabloları gibi veri kaynaklarına. Windows Forms veri bağlama modelleri hakkında tam bilgi için bkz: [verileri bağlama ve Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms).  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl yapmak I: tüketen veritabanı Excel'de veri?](http://go.microsoft.com/fwlink/?LinkID=130287).  
  
## <a name="simple-data-binding"></a>Basit veri bağlama  
 Basit veri bağlama denetimi özelliği tek bir veri öğesi, bir veri tablosunda bir değer gibi bağlandığında bulunmaktadır. Örneğin, <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi sahip bir <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> bir veri kümesi alanına bağlı özelliği. Veri kümesinde yer alan değiştiğinde, adlandırılmış bir aralık değeri de değişir. Tüm denetimler dışında konak <xref:Microsoft.Office.Tools.Word.XMLNodes> denetlemek, basit veri bağlamayı destekler. <xref:Microsoft.Office.Tools.Word.XMLNodes> Denetim koleksiyonu olduğu ve bu nedenle veri bağlamayı desteklemez.  
  
 Bir konak kontrolü basit veri bağlama gerçekleştirmek için eklemeniz bir <xref:System.Windows.Forms.Binding> denetiminin veri bağlamaları özelliğine. A <xref:System.Windows.Forms.Binding> nesnesi denetimi özelliği değeri ve veri öğesinin değeri arasında basit veri bağlamasını temsil eder.  
  
 Aşağıdaki örnekte nasıl bağlanacağını gösterir <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> belge düzeyi projede bir veri öğesi özelliğine.  
  
 [!code-vb[Trin_BindableComponent#4](../vsto/codesnippet/VisualBasic/Trin_BindableComponent/Sheet1.vb#4)]
 [!code-csharp[Trin_BindableComponent#4](../vsto/codesnippet/CSharp/Trin_BindableComponent/Sheet1.cs#4)]  
  
 Basit veri bağlamayı gösteren izlenecek yollar için bkz: [izlenecek yol: belge düzeyi projede basit veri bağlama](../vsto/walkthrough-simple-data-binding-in-a-document-level-project.md) bir belge düzeyi projesi için ve [izlenecek yol: Basit veri bağlama VSTO eklenti projesi ](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md) VSTO eklenti projesindeki için.  
  
## <a name="complex-data-binding"></a>Karmaşık veri bağlama  
 Bir veri tablosunda birden çok sütun gibi birden fazla veri öğesi için bir denetim özelliğe bağlıyken karmaşık veri bağlama var. <xref:Microsoft.Office.Tools.Excel.ListObject> Excel karmaşık veri bağlamayı destekleyen tek konak denetimi için denetim. Ayrıca gibi karmaşık veri bağlamayı destekleyen birçok Windows Forms denetimleri vardır <xref:System.Windows.Forms.DataGridView> denetim.  
  
 Karmaşık veri bağlamayı gerçekleştirmek için karmaşık veri bağlama tarafından desteklenen bir veri kaynağı nesnesi denetiminin DataSource özelliği ayarlayın. Örneğin, <xref:Microsoft.Office.Tools.Excel.ListObject.DataSource%2A> özelliği <xref:Microsoft.Office.Tools.Excel.ListObject> denetimi, bir veri tablosunda birden fazla sütuna bağlanabilir. Tüm veri tablosundaki verileri görünür <xref:Microsoft.Office.Tools.Excel.ListObject> denetim ve veri tablosu değişiklikleri veri olarak <xref:Microsoft.Office.Tools.Excel.ListObject> da değişir. Karmaşık veri bağlama için kullanabileceğiniz veri kaynaklarının listesi için bkz: [veri kaynaklarını Windows Forms tarafından desteklenen](/dotnet/framework/winforms/data-sources-supported-by-windows-forms).  
  
 Aşağıdaki kod örneği oluşturur bir <xref:System.Data.DataSet> iki <xref:System.Data.DataTable> nesneleri ve veri tablolarıyla birini doldurur. Kod sonra bağlar <xref:Microsoft.Office.Tools.Excel.ListObject> veri içeren bir tablo için. Bu örnek bir Excel belge düzeyi projesi içindir.  
  
 [!code-csharp[Trin_ExcelListObject#18](../vsto/codesnippet/CSharp/Trin_ExcelListObject/Trin_ExcelListObject.cs#18)]
 [!code-vb[Trin_ExcelListObject#18](../vsto/codesnippet/VisualBasic/Trin_ExcelListObject/Sheet1.vb#18)]  
  
 Karmaşık veri bağlamayı gösteren izlenecek yollar için bkz: [izlenecek yol: belge düzeyi projede karmaşık veri bağlama](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md) bir belge düzeyi projesi için ve [izlenecek yol: karmaşık veri bağlama VSTO eklenti projesi ](../vsto/walkthrough-complex-data-binding-in-vsto-add-in-project.md) VSTO eklenti projesindeki için.  
  
## <a name="displaying-data-in-documents-and-workbooks"></a>Belgeler ve çalışma kitaplarında verileri görüntüleme  
 Belge düzeyi projelerine kullandığınız **veri kaynakları** penceresini belgeleri veya çalışma kitapları için veri bağlama denetimleri kolayca eklemek için kullandığınız, Windows Forms için aynı şekilde. Kullanma hakkında daha fazla bilgi için **veri kaynakları** penceresinde bkz [bağlamak Windows Forms denetimleri Visual Studio'da verilere](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md) ve [yeni veri kaynakları ekleyin](../data-tools/add-new-data-sources.md).  
  
### <a name="dragging-controls-from-the-data-sources-window"></a>Denetimleri veri kaynakları penceresinden sürükleme  
 Bir nesne ondan sürükleyin denetim belgede oluşturulduğunda **veri kaynakları** penceresi. Verilerin tek bir sütun veya birden çok veri sütunlarının bağlama oluşturulan denetim türüne bağlıdır.  
  
 Excel için bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi her tek tek bir alan için çalışma sayfası üzerinde oluşturulur ve bir <xref:Microsoft.Office.Tools.Excel.ListObject> denetimi, birden çok satır ve sütunları içeren her veri aralığı için oluşturulur. Tablo seçerek bu varsayılanı değiştirmek veya içinde alan **veri kaynakları** penceresini açın ve ardından farklı bir denetim aşağı açılan listeden seçerek.  
  
 A <xref:Microsoft.Office.Tools.Word.ContentControl> denetimi belgeye eklenir. İçerik denetimi türü seçtiğiniz alanın veri türüne bağlıdır.  
  
### <a name="binding-data-in-document-level-projects-at-design-time"></a>Belge düzeyi projelerine tasarım zamanında veri bağlama  
 Aşağıdaki konularda tasarım zamanında veri bağlama örnekleri gösterilmektedir.  
  
-   [Nasıl Yapılır: Çalışma Sayfalarını Veritabanı Verileriyle Doldurma](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)  
  
-   [Nasıl Yapılır: Belgeleri Veritabanı Verileriyle Doldurma](../vsto/how-to-populate-documents-with-data-from-a-database.md)  
  
-   [Nasıl Yapılır: Belgeleri Nesne Verileriyle Doldurma](../vsto/how-to-populate-documents-with-data-from-objects.md)  
  
-   [Nasıl Yapılır: Belgeleri Hizmet Verileriyle Doldurma](../vsto/how-to-populate-documents-with-data-from-services.md)  
  
-   [Nasıl Yapılır: Çalışma Sayfasındaki Veritabanı Kayıtları Arasında Kaydırma](../vsto/how-to-scroll-through-database-records-in-a-worksheet.md)  
  
### <a name="binding-data-in-vsto-add-in-projects"></a>VSTO eklentisi projelerine veri bağlama  
 VSTO eklenti projelerinde yalnızca çalışma zamanında denetimler ekleyebilirsiniz. Aşağıdaki konular, çalışma zamanında veri bağlama örnekleri gösterir:  
  
-   [İzlenecek Yol: VSTO eklenti Projesinde Basit Veri Bağlama](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md)  
  
-   [İzlenecek Yol: VSTO eklenti Projesinde Karmaşık Veri Bağlama](../vsto/walkthrough-complex-data-binding-in-vsto-add-in-project.md)  
  
## <a name="updating-data-that-is-bound-to-host-controls"></a>Denetimleri barındırmak için ilişkili verileri güncelleştirme  
 Veri bağlama veri kaynağı ve konak kontrolü arasında iki yönlü veri güncelleştirme içerir. Basit veri bağlama, veri kaynağındaki değişiklikler otomatik olarak konak denetiminde yansıtılır, ancak veri kaynağını güncelleştirmek için açık bir çağrı konak denetimi gerektirir. Başka bir veri bağlama alan değişikliklerinden eşlik sürece bazı durumlarda, bir veri bağlama alan değişiklikleri kabul nedenidir. Örneğin, iki alan, geçerlilik süresi için bir ve deneyimi yıllık biri olabilir. Deneyimi yaşı geçemez. Bir kullanıcı yaşı 50'den güncelleştirilemiyor 25'i ve ardından 30 deneyimlerden 10 sürece çözemiyorsa aynı anda değişiklikleri yapar. Bu sorunu çözmek için güncelleştirmeleri açıkça kod tarafından gönderilen kadar basit veri bağlama alanlarla güncelleştirilmez.  
  
 Basit veri bağlama etkinleştirmek ana bilgisayar denetimleri veri kaynağını güncelleştirmek için güncelleştirmelerinin bellek içi veri kaynağına göndermeniz gerekir (gibi bir <xref:System.Data.DataSet> veya <xref:System.Data.DataTable>) ve arka uç veritabanına çözümünüzü kullanıyorsa.  
  
 Karmaşık veri bağlama işlemini kullanma gerçekleştirdiğinizde bellek içi veri kaynağını açıkça güncelleştirmek gerekmez <xref:Microsoft.Office.Tools.Excel.ListObject> denetim. Bu durumda, değişiklikleri ek kod olmadan bellek içi veri kaynağına otomatik olarak gönderilir.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: konak kontrolü verileriyle veri kaynağını güncelleme](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [I: Excel'de veritabanı verisi nasıl kullanabilir?](http://go.microsoft.com/fwlink/?LinkID=130287)   
 [Veri bağlama ve Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms)   
 [Nasıl yapılır: bir Windows formunda basit bağlantılı denetim oluşturma](/dotnet/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form)   
 [Visual Studio'da verilere Windows Forms denetimleri bağlama](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Veritabanına veri kaydetme](../data-tools/save-data-back-to-the-database.md)    
 [TableAdapter kullanarak veri güncelleştirme](../data-tools/update-data-by-using-a-tableadapter.md)    
 [Verileri önbelleğe alma](../vsto/caching-data.md)   
 [Office Çözümlerindeki Veriler](../vsto/data-in-office-solutions.md)  
  
  