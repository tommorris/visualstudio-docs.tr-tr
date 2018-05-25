---
title: Konak öğelerine ve denetimlerine genel bakış
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- host controls [Office development in Visual Studio], adding
- Office documents [Office development in Visual Studio, host controls
- host items [Office development in Visual Studio]
- application development [Office development in Visual Studio], host items
- Office applications [Office development in Visual Studio], host items
- host controls [Office development in Visual Studio], listed
- Excel [Office development in Visual Studio], host items
- host controls [Office Development in Visual Stuio], naming
- host controls [Office development in Visual Studio]
- host controls [Office development in Visual Studio], about host controls
- document-level customizations [Office development in Visual Studio], host controls
- Office applications [Office development in Visual Studio], host controls
- documents [Office development in Visual Studio], host controls
- controls [Office development in Visual Studio], host controls
- application development [Office development in Visual Studio], host controls
- Excel [Office development in Visual Studio], host controls
- host items [Office development in Visual Studio], about host items
- host items [Office development in Visual Studio], listed
- documents [Office development in Visual Studio], host items
- data binding [Office development in Visual Studio], host controls
- Office documents [Office development in Visual Studio, host items
- Word [Office development in Visual Studio], host items
- document-level customizations [Office development in Visual Studio], host items
- Word [Office development in Visual Studio], host controls
- host controls [Office development in Visual Studio], deleting
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: afc067e46f3cad5baa46bb5fef2381e82791dc76
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2018
---
# <a name="host-items-and-host-controls-overview"></a>Konak öğelerine ve denetimlerine genel bakış
  Konak denetimlerinin ve konak öğelerinin programlama modeli için Visual Studio'da Office geliştirme araçları kullanılarak oluşturulan Office çözümleri sağlamak türleridir. Konak denetimlerinin ve konak öğelerinin COM üzerinde daha fazla Windows Forms denetimleri gibi yönetilen nesnelerle etkileşim gibi dayalı Microsoft Office Word ve Microsoft Office Excel nesne modelleri ile etkileşimi olun.  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
## <a name="host-items"></a>Konak öğeleri  
 Konak öğeleri Office projelerinde nesne modeli hiyerarşi üstünde olan türleridir. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Word ve Excel çözümleri için aşağıdaki konak öğelerini tanımlar:  
  
-   <xref:Microsoft.Office.Tools.Word.Document>  
  
-   <xref:Microsoft.Office.Tools.Excel.Workbook>  
  
-   <xref:Microsoft.Office.Tools.Excel.Worksheet>  
  
-   <xref:Microsoft.Office.Tools.Excel.ChartSheet>  
  
 Bu türleri yerel olarak adlandırılan Word veya Excel nesne modelinde, var olan bir nesneyi genişletir bir *yerel Office nesnesi*. Örneğin, <xref:Microsoft.Office.Tools.Word.Document> konak öğesi genişletir <xref:Microsoft.Office.Interop.Word.Document> Word için birincil birlikte çalışma derlemesinde tanımlanan nesnesi.  
  
 Konak öğeleri genellikle karşılık gelen Office nesneleri aynı temel işlevselliğe sahiptir, ancak aşağıdaki özelliklerle geliştirilmiştir:  
  
-   Konak denetimleri ve Windows Forms denetimleri de dahil olmak üzere yönetilen denetimleri barındıran yeteneği.  
  
-   Daha fazla olay modeli. Yerel Word ve Excel nesne modelleri bazı belge, çalışma kitabı ve çalışma olayları yalnızca uygulama düzeyinde oluşturulur. Konak öğeleri belirli bir belge için olayları işlemek daha kolay için bu olayları belge düzeyinde sağlar.  
  
### <a name="understand-host-items-in-document-level-projects"></a>Belge düzeyi projelerine ana bilgisayar öğeleri anlama  
 Belge düzeyi projelerine ana bilgisayar öğeleri kodunuz için giriş noktası sağlar ve tasarımcıları çözümünüzü geliştirmenize yardımcı olabilirler.  
  
 <xref:Microsoft.Office.Tools.Word.Document> Ve <xref:Microsoft.Office.Tools.Excel.Worksheet> ana bilgisayar öğeleri belgeye ya da bir Windows Forms Tasarımcısı gibi çalışma görsel gösterimi tasarımcıları ilişkili. Belge veya çalışma sayfasına doğrudan Word veya Excel içeriğini değiştirmek ve denetimleri tasarım yüzeyine sürükleyin için bu tasarımcısını kullanabilirsiniz. Daha fazla bilgi için bkz: [belge konak öğesi](../vsto/document-host-item.md) ve [çalışma sayfası konak öğesi](../vsto/worksheet-host-item.md).  
  
 <xref:Microsoft.Office.Tools.Excel.Workbook> Konak öğesi bir kullanıcı arabirimine sahip denetimler için bir kapsayıcı olarak hareket değil. Bunun yerine, bu konak öğesi için tasarımcı bir bileşeni gibi sürükleyin olanak tanır ve bileşen alanı işlevleri bir <xref:System.Data.DataSet>, kendi tasarım yüzeyine. Daha fazla bilgi için bkz: [çalışma kitabı konak öğesi](../vsto/workbook-host-item.md).  
  
 Konak öğeleri program aracılığıyla belge düzeyi projelerine oluşturulamıyor. Bunun yerine, kullanın `ThisDocument`, `ThisWorkbook`, veya `Sheet` *n* Visual Studio projenizde tasarım zamanında otomatik olarak oluşturur. sınıfları. Bu oluşturulan sınıflar konak öğelerinden türetilir ve kodunuz için giriş noktası sağlar. Daha fazla bilgi için bkz: [konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
### <a name="understand-host-items-in-vsto-add-in-projects"></a>Konak öğeleri VSTO eklentisi projelerine anlama  
 Bir VSTO eklenti oluşturduğunuzda, varsayılan olarak tüm ana bilgisayar öğelerine erişimi sahip değil. Ancak, oluşturabileceğiniz <xref:Microsoft.Office.Tools.Word.Document>, <xref:Microsoft.Office.Tools.Excel.Workbook>, ve <xref:Microsoft.Office.Tools.Excel.Worksheet> konak öğelerini Word ve Excel VSTO eklentileri çalışma zamanında.  
  
 Bir konak öğesi oluşturduktan sonra belgelere denetimler ekleme gibi görevleri gerçekleştirebilir. Daha fazla bilgi için bkz: [genişletmek Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="host-controls"></a>Konak denetimleri  
 Konak denetimleri uzatma Word ve Excel nesne modellerindeki çeşitli kullanıcı arabirimi (UI) nesnelerini gibi `Microsoft.Office.Interop.Word.ContentControl` ve <xref:Microsoft.Office.Interop.Excel.Range> nesneleri.  
  
 Aşağıdaki ana bilgisayar denetimleri Excel projeleri için kullanılabilir:  
  
-   [Grafik denetimi](../vsto/chart-control.md)  
  
-   [ListObject denetimi](../vsto/listobject-control.md)  
  
-   [NamedRange denetimi](../vsto/namedrange-control.md)  
  
-   [XmlMappedRange denetimi](../vsto/xmlmappedrange-control.md)  
  
 Aşağıdaki ana bilgisayar denetimleri Word projeleri için kullanılabilir:  
  
-   [Yer işareti denetimi](../vsto/bookmark-control.md)  
  
-   [İçerik denetimleri](../vsto/content-controls.md)  
  
-   [XMLNode denetimi](../vsto/xmlnode-control.md)  
  
-   [XMLNodes denetimi](../vsto/xmlnodes-control.md)  
  
 Office belgelerine eklenmiş konak denetimleri yerel Office nesneleri gibi davranırlar; Ancak, ana bilgisayar denetimleri olaylar ve veri bağlama özellikleri dahil olmak üzere ek işlevselliğe sahiptir. Örneğin, istediğinizde bir yerel olaylarını yakalamak <xref:Microsoft.Office.Interop.Excel.Range> , gereken ilk işlemek çalışma sayfasının değişiklik olayı Excel'de nesne. İçinde değişikliğinin olup olmadığını belirlemeniz gerekir sonra <xref:Microsoft.Office.Interop.Excel.Range>. Buna karşılık, <xref:Microsoft.Office.Tools.Excel.NamedRange> konak kontrolü sahip bir <xref:Microsoft.Office.Tools.Excel.NamedRange.Change> doğrudan işleyebileceğiniz olay.  
  
 Konak denetimlerinin ve konak öğesi arasındaki ilişki, bir Windows Form ve Windows Forms denetimleri arasındaki ilişkiyi çok benzer. Bir Windows formunda metin kutusu denetiminin yerleştirmek gibi yerleştirdiğiniz bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetiminin bir <xref:Microsoft.Office.Tools.Excel.Worksheet> konak öğesi. Aşağıdaki çizimde konak denetimlerinin ve konak öğeleri arasındaki ilişkiyi gösterir.  
  
 ![Konak denetimlerinin ve konak öğeleri arasındaki ilişki](../vsto/media/hostitemscontrols.png "konak denetimlerinin ve konak öğeleri arasındaki ilişki")  
  
 Windows Forms denetimleri Office çözümlerinde doğrudan Word ve Excel belge yüzeyine ekleyerek de kullanabilirsiniz. Daha fazla bilgi için bkz: [Windows Forms denetimleri Office belgeleri genel bakış](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
> [!NOTE]  
>  Bir Word alt konak veya Windows Forms denetimleri ekleme desteklenmiyor.  
  
### <a name="add-host-controls-to-your-documents"></a>Konak denetimleri belgelere ekleme  
 Belge düzeyi projelerine, ana bilgisayar denetimleri Word belgelerine veya Excel çalışma sayfalarına tasarım zamanında aşağıdaki yollarla ekleyebilirsiniz:  
  
-   Konak denetimleri ekleme aynı şekilde tasarım zamanında belgenize yerel bir nesne eklemek.  
  
-   Konak denetimleri sürükleyin **araç** belgelere ve çalışma üzerine. Excel konak denetimleri kullanılabilir **Excel denetimleri** Excel projeleri ve Word konak denetimleri kullanılabilir sekmesinde **Word denetimleri** Word projeleri sekmesindedir.  
  
-   Konak denetimleri sürükleyin **veri kaynakları** belgelere ve çalışma üzerine penceresi. Bu, zaten verilere bağlı denetimler eklemenize olanak sağlar. Daha fazla bilgi için bkz: [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
 Belge düzeyi ve VSTO eklentisi projelerine, çalışma zamanında belgelere bazı ana bilgisayar denetimleri de ekleyebilirsiniz. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 Konak denetimleri belgelere ekleme hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Nasıl yapılır: çalışma sayfalarına Grafik denetimleri ekleme](../vsto/how-to-add-chart-controls-to-worksheets.md)  
  
-   [Nasıl yapılır: çalışma sayfalarına ListObject denetimleri ekleme](../vsto/how-to-add-listobject-controls-to-worksheets.md)  
  
-   [Nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)  
  
-   [Nasıl yapılır: çalışma sayfalarına XMLMappedRange denetimleri ekleme](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)  
  
-   [Nasıl yapılır: Word belgelerine yer işareti denetimi ekleme](../vsto/how-to-add-bookmark-controls-to-word-documents.md)  
  
-   [Nasıl yapılır: içerik ekleme denetimlerine Word belgeleri](../vsto/how-to-add-content-controls-to-word-documents.md)  
  
-   [Nasıl yapılır: Word belgelerine XMLNode denetimleri ekleme](../vsto/how-to-add-xmlnode-controls-to-word-documents.md)  
  
-   [Nasıl yapılır: Word belgelerine XMLNodes denetimleri ekleme](../vsto/how-to-add-xmlnodes-controls-to-word-documents.md)  
  
### <a name="name-host-controls"></a>Ad ana bilgisayar denetimleri  
 Bir ana bilgisayar denetiminden sürüklediğinizde **araç** belgenize denetimi otomatik olarak artımlı bir sayı sonunda denetim türü kullanarak olarak adlandırılır. Örneğin, yer işaretleri adlı **bookmark1**, **bookmark2**ve benzeri. Denetim eklemek için Word veya Excel yerel işlevselliğini kullanırsanız, oluşturduğunuz zaman belirli bir adı verebilirsiniz. Ayrıca, değerini değiştirerek denetimlerinizi adlandırabilirsiniz **adı** özelliğinde **özellikleri** penceresi.  
  
> [!NOTE]  
>  Ayrılmış sözcükler adı ana bilgisayar denetimleri için kullanamazsınız. Örneğin, eklerseniz bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetiminin çalışma sayfasına ve adla değiştirin **sistem**, projeyi derlerken hataları oluşur.  
  
### <a name="delete-host-controls"></a>Konak denetimleri Sil  
 Belge düzeyi projelerine, ana bilgisayar denetimleri tasarım zamanında denetim Excel çalışma sayfası veya Word belgesi seçip tuşuna basarak silebilirsiniz **silmek** anahtarı. Ancak kullanmalıdır **ad tanımla** silmek için Excel iletişim kutusunda <xref:Microsoft.Office.Tools.Excel.NamedRange> kontrol eder.  
  
 Tasarım zamanında bir belgeye konak kontrolü eklerseniz, kodda denetimi kullanmaya çalıştığınızda başlatıldığında bir özel durum nedeniyle program aracılığıyla çalışma zamanında kaldırmalısınız değil. `Delete` Konak kontrolü yöntemi yalnızca belgeye çalışma zamanında eklenmiş konak denetimleri kaldırır. Çağırırsanız `Delete` tasarım zamanında oluşturulan konak kontrolü yöntemi, bir özel durum oluşur.  
  
 Örneğin, <xref:Microsoft.Office.Tools.Excel.NamedRange.Delete%2A> yöntemi bir <xref:Microsoft.Office.Tools.Excel.NamedRange> yalnızca başarıyla siler <xref:Microsoft.Office.Tools.Excel.NamedRange> programlı olarak dinamik ana bilgisayar denetimleri oluşturma olarak bilinen çalışma sayfasına eklendiğinden durumunda. Dinamik olarak oluşturulmuş ana bilgisayar denetimleri de kaldırılabilir denetim adına geçirerek `Remove` yöntemi <xref:Microsoft.Office.Tools.Excel.Worksheet.Controls%2A> veya <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> özelliği. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 Çözüm, son kullanıcılar, çalışma zamanında belgeden bir konak kontrolü silerseniz, beklenmedik bir şekilde başarısız olabilir. Konak denetimleri silinmesini korumak için Word ve Excel'deki belge koruma özelliklerini kullanabilirsiniz. Daha fazla bilgi için bkz: [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md).  
  
> [!NOTE]  
>  Program aracılığıyla denetimleri sırasında kaldırmayın `Shutdown` belgeye ya da çalışma olay işleyicisi. Kullanıcı Arabirimi öğeleri artık kullanılamaz `Shutdown` olayı oluşur. Uygulama kapanmadan denetimleri kaldırmak istiyorsanız, kodunuzu başka bir olay işleyicisine gibi ekleyin `BeforeClose` veya `BeforeSave`.  
  
### <a name="program-against-host-control-events"></a>Konak denetim olaylarına karşı programı  
 Konak denetimleri Office nesneleri genişleten bir olaylar ekleyerek yoludur. Örneğin, <xref:Microsoft.Office.Interop.Excel.Range> Excel nesnesinde ve <xref:Microsoft.Office.Interop.Word.Bookmark> Word nesnesinde olayları gerekmez ancak [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] programlanabilir olaylar ekleyerek bu nesneleri genişletir. Erişebilir ve bu olaylara karşı aynı kod Windows Forms denetimlerindeki olaylar erişim yol: Visual Basic ve C# olay özellik sayfası olay aşağı açılan listeden aracılığıyla. Daha fazla bilgi için bkz: [izlenecek yol: NamedRange denetimi olaylarına karşı Program](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md).  
  
> [!NOTE]  
>  Ayarlanmamış <xref:Microsoft.Office.Interop.Excel._Application.EnableEvents%2A> özelliği <xref:Microsoft.Office.Interop.Excel.Application> Excel'e nesnesinde **false**. Bu özelliği ayarlamak **false** Excel konak denetimleri dahil herhangi bir olayı tetiklenmeden engeller.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md)   
 [Genişletilmiş nesneleri kullanarak Word otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirmek](../vsto/automating-excel-by-using-extended-objects.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)  
  