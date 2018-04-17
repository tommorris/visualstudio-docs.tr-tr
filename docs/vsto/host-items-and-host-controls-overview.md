---
title: Konak öğelerine ve denetimlerine genel bakış | Microsoft Docs
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
ms.openlocfilehash: 84e0b2cf74eb8c0d3faca8d1c28d3bea91c87f76
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="host-items-and-host-controls-overview"></a>Konak Öğelerine ve Denetimlerine Genel Bakış
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
  
### <a name="understanding-host-items-in-document-level-projects"></a>Belge düzeyi projelerine konak öğelerini anlama  
 Belge düzeyi projelerine ana bilgisayar öğeleri kodunuz için giriş noktası sağlar ve tasarımcıları çözümünüzü geliştirmenize yardımcı olabilirler.  
  
 <xref:Microsoft.Office.Tools.Word.Document> Ve <xref:Microsoft.Office.Tools.Excel.Worksheet> ana bilgisayar öğeleri belgeye ya da bir Windows Forms Tasarımcısı gibi çalışma görsel gösterimi tasarımcıları ilişkili. Belge veya çalışma sayfasına doğrudan Word veya Excel içeriğini değiştirmek ve denetimleri tasarım yüzeyine sürükleyin için bu tasarımcısını kullanabilirsiniz. Daha fazla bilgi için bkz: [belge konak öğesi](../vsto/document-host-item.md) ve [çalışma sayfası konak öğesi](../vsto/worksheet-host-item.md).  
  
 <xref:Microsoft.Office.Tools.Excel.Workbook> Konak öğesi bir kullanıcı arabirimine sahip denetimler için bir kapsayıcı olarak hareket değil. Bunun yerine, bu konak öğesi için tasarımcı bir bileşeni gibi sürükleyin olanak tanır ve bileşen alanı işlevleri bir <xref:System.Data.DataSet>, kendi tasarım yüzeyine. Daha fazla bilgi için bkz: [çalışma kitabı konak öğesi](../vsto/workbook-host-item.md).  
  
 Konak öğeleri program aracılığıyla belge düzeyi projelerine oluşturulamıyor. Bunun yerine, kullanın `ThisDocument`, `ThisWorkbook`, veya `Sheet` *n* Visual Studio projenizde tasarım zamanında otomatik olarak oluşturur. sınıfları. Bu oluşturulan sınıflar konak öğelerinden türetilir ve kodunuz için giriş noktası sağlar. Daha fazla bilgi için bkz: [programsal sınırlamalar, ana bilgisayar öğeleri ve ana bilgisayar denetimleri](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
### <a name="understanding-host-items-in-vsto-add-in-projects"></a>VSTO eklentisi projelerine konak öğelerini anlama  
 Bir VSTO eklenti oluşturduğunuzda, varsayılan olarak tüm ana bilgisayar öğelerine erişimi sahip değil. Ancak, oluşturabileceğiniz <xref:Microsoft.Office.Tools.Word.Document>, <xref:Microsoft.Office.Tools.Excel.Workbook>, ve <xref:Microsoft.Office.Tools.Excel.Worksheet> çalışma zamanında konak öğelerini Word ve Excel VSTO eklentileri.  
  
 Bir konak öğesi oluşturduktan sonra belgelere denetimler ekleme gibi görevleri gerçekleştirebilir. Daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="host-controls"></a>Konak denetimleri  
 Konak denetimleri Word ve Excel nesne modellerindeki Microsoft.Office.Interop.Word.ContentControl gibi çeşitli kullanıcı arabirimi (UI) nesneleri genişletir ve <xref:Microsoft.Office.Interop.Excel.Range> nesneleri.  
  
 Aşağıdaki ana bilgisayar denetimleri Excel projeleri için kullanılabilir:  
  
-   [Grafik Denetimi](../vsto/chart-control.md)  
  
-   [ListObject Denetimi](../vsto/listobject-control.md)  
  
-   [NamedRange Denetimi](../vsto/namedrange-control.md)  
  
-   [XmlMappedRange Denetimi](../vsto/xmlmappedrange-control.md)  
  
 Aşağıdaki ana bilgisayar denetimleri Word projeleri için kullanılabilir:  
  
-   [Yer İşareti Denetimi](../vsto/bookmark-control.md)  
  
-   [İçerik Denetimleri](../vsto/content-controls.md)  
  
-   [XMLNode Denetimi](../vsto/xmlnode-control.md)  
  
-   [XMLNodes Denetimi](../vsto/xmlnodes-control.md)  
  
 Office belgelerine eklenmiş konak denetimleri yerel Office nesneleri gibi davranırlar; Ancak, ana bilgisayar denetimleri olaylar ve veri bağlama özellikleri dahil olmak üzere ek işlevselliğe sahiptir. Örneğin, istediğinizde bir yerel olaylarını yakalamak <xref:Microsoft.Office.Interop.Excel.Range> , gereken ilk işlemek çalışma sayfasının değişiklik olayı Excel'de nesne. İçinde değişikliğinin olup olmadığını belirlemeniz gerekir sonra <xref:Microsoft.Office.Interop.Excel.Range>. Buna karşılık, <xref:Microsoft.Office.Tools.Excel.NamedRange> konak kontrolü sahip bir <xref:Microsoft.Office.Tools.Excel.NamedRange.Change> doğrudan işleyebileceğiniz olay.  
  
 Konak denetimlerinin ve konak öğesi arasındaki ilişki, bir Windows Form ve Windows Forms denetimleri arasındaki ilişkiyi çok benzer. Bir Windows formunda metin kutusu denetiminin yerleştirmek gibi yerleştirdiğiniz bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetiminin bir <xref:Microsoft.Office.Tools.Excel.Worksheet> konak öğesi. Aşağıdaki çizimde konak denetimlerinin ve konak öğeleri arasındaki ilişkiyi gösterir.  
  
 ![Konak denetimlerinin ve konak öğeleri arasındaki ilişki](../vsto/media/hostitemscontrols.png "konak denetimlerinin ve konak öğeleri arasındaki ilişki")  
  
 Windows Forms denetimleri Office çözümlerinde doğrudan Word ve Excel belge yüzeyine ekleyerek de kullanabilirsiniz. Daha fazla bilgi için bkz: [Office belgeleri genel bakış Windows Forms denetimleri](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
> [!NOTE]  
>  Bir Word alt konak veya Windows Forms denetimleri ekleme desteklenmiyor.  
  
### <a name="adding-host-controls-to-your-documents"></a>Konak denetimleri, belgelere ekleme  
 Belge düzeyi projelerine, ana bilgisayar denetimleri Word belgelerine veya Excel çalışma sayfalarına tasarım zamanında aşağıdaki yollarla ekleyebilirsiniz:  
  
-   Konak denetimleri ekleme aynı şekilde tasarım zamanında belgenize yerel bir nesne eklemek.  
  
-   Konak denetimleri sürükleyin **araç** belgelere ve çalışma üzerine. Excel konak denetimleri kullanılabilir **Excel denetimleri** Excel projeleri ve Word konak denetimleri kullanılabilir sekmesinde **Word denetimleri** Word projeleri sekmesindedir.  
  
-   Konak denetimleri sürükleyin **veri kaynakları** belgelere ve çalışma üzerine penceresi. Bu, zaten verilere bağlı denetimler eklemenize olanak sağlar. Daha fazla bilgi için bkz: [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
 Belge düzeyi ve VSTO eklentisi projelerine, çalışma zamanında belgelere bazı ana bilgisayar denetimleri de ekleyebilirsiniz. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 Konak denetimleri belgelere ekleme hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Nasıl Yapılır: Çalışma Sayfalarına Grafik Denetimleri Ekleme](../vsto/how-to-add-chart-controls-to-worksheets.md)  
  
-   [Nasıl yapılır: Çalışma Sayfalarına ListObject Denetimleri Ekleme](../vsto/how-to-add-listobject-controls-to-worksheets.md)  
  
-   [Nasıl yapılır: Çalışma Sayfalarına NamedRange Denetimleri Ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)  
  
-   [Nasıl yapılır: Çalışma Sayfalarına XMLMappedRange Denetimleri Ekleme](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)  
  
-   [Nasıl Yapılır: Word Belgelerine Yer İşareti Denetimi Ekleme](../vsto/how-to-add-bookmark-controls-to-word-documents.md)  
  
-   [Nasıl Yapılır: Word Belgelerine İçerik Denetimleri Ekleme](../vsto/how-to-add-content-controls-to-word-documents.md)  
  
-   [Nasıl Yapılır: Word Belgelerine XMLNode Denetimleri Ekleme](../vsto/how-to-add-xmlnode-controls-to-word-documents.md)  
  
-   [Nasıl Yapılır: Word Belgelerine XMLNodes Denetimleri Ekleme](../vsto/how-to-add-xmlnodes-controls-to-word-documents.md)  
  
### <a name="naming-host-controls"></a>Adlandırma ana bilgisayar denetimleri  
 Bir ana bilgisayar denetiminden sürüklediğinizde **araç** belgenize denetimi otomatik olarak artımlı bir sayı sonunda denetim türü kullanarak olarak adlandırılır. Örneğin, yer işaretleri adlı **bookmark1**, **bookmark2**ve benzeri. Denetim eklemek için Word veya Excel yerel işlevselliğini kullanırsanız, oluşturduğunuz zaman belirli bir adı verebilirsiniz. Ayrıca, değerini değiştirerek denetimlerinizi adlandırabilirsiniz **adı** özelliğinde **özellikleri** penceresi.  
  
> [!NOTE]  
>  Ayrılmış sözcükler adı ana bilgisayar denetimleri için kullanamazsınız. Örneğin, eklerseniz bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetiminin çalışma sayfasına ve adla değiştirin **sistem**, projeyi derlerken hataları oluşur.  
  
### <a name="deleting-host-controls"></a>Konak denetimleri silme  
 Belge düzeyi projelerine ana bilgisayar denetimleri tasarım zamanında denetimi Excel çalışma sayfası veya Word belgesi seçerek ve Delete tuşuna basarak silebilirsiniz. Ancak kullanmalıdır **ad tanımla** silmek için Excel iletişim kutusunda <xref:Microsoft.Office.Tools.Excel.NamedRange> kontrol eder.  
  
 Tasarım zamanında bir belgeye konak kontrolü eklerseniz, kodda denetimi kullanmaya çalıştığınızda başlatıldığında bir özel durum nedeniyle program aracılığıyla çalışma zamanında kaldırmalısınız değil. `Delete` Konak kontrolü yöntemi yalnızca belgeye çalışma zamanında eklenmiş konak denetimleri kaldırır. Çağırırsanız `Delete` tasarım zamanında oluşturulan konak kontrolü yöntemi, bir özel durum oluşur.  
  
 Örneğin, <xref:Microsoft.Office.Tools.Excel.NamedRange.Delete%2A> yöntemi bir <xref:Microsoft.Office.Tools.Excel.NamedRange> yalnızca başarıyla siler <xref:Microsoft.Office.Tools.Excel.NamedRange> programlı olarak dinamik ana bilgisayar denetimleri oluşturma olarak bilinen çalışma sayfasına eklendiğinden durumunda. Dinamik olarak oluşturulmuş ana bilgisayar denetimleri de kaldırılabilir denetim adına geçirerek `Remove` yöntemi <xref:Microsoft.Office.Tools.Excel.Worksheet.Controls%2A> veya <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> özelliği. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 Çözüm, son kullanıcılar, bir konak kontrolü belgeden çalışma zamanında silerseniz, beklenmedik bir şekilde başarısız olabilir. Konak denetimleri silinmesini korumak için Word ve Excel'deki belge koruma özelliklerini kullanabilirsiniz. Daha fazla bilgi için bkz: [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md).  
  
> [!NOTE]  
>  Program aracılığıyla denetimleri sırasında kaldırmayın `Shutdown` belgeye ya da çalışma olay işleyicisi. Kullanıcı Arabirimi öğeleri artık kullanılamaz `Shutdown` olayı oluşur. Uygulama kapanmadan denetimleri kaldırmak istiyorsanız, kodunuzu başka bir olay işleyicisine gibi ekleyin `BeforeClose` veya `BeforeSave`.  
  
### <a name="programming-against-host-control-events"></a>Konak denetim olaylarına karşı programlama  
 Konak denetimleri Office nesneleri genişleten bir olaylar ekleyerek yoludur. Örneğin, <xref:Microsoft.Office.Interop.Excel.Range> Excel nesnesinde ve <xref:Microsoft.Office.Interop.Word.Bookmark> Word nesnesinde olayları gerekmez ancak [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] programlanabilir olaylar ekleyerek bu nesneleri genişletir. Erişebilir ve bu olaylara karşı aynı kod Windows Forms denetimlerindeki olaylar erişim yol: Visual Basic ve C# olay özellik sayfası olay aşağı açılan listeden aracılığıyla. Daha fazla bilgi için bkz: [izlenecek yol: programlama karşı olayları NamedRange denetimi](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md).  
  
> [!NOTE]  
>  Ayarlanmamış <xref:Microsoft.Office.Interop.Excel._Application.EnableEvents%2A> özelliği <xref:Microsoft.Office.Interop.Excel.Application> Excel'e nesnesinde **false**. Bu özelliği ayarlamak **false** Excel konak denetimleri dahil herhangi bir olayı tetiklenmeden engeller.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md)   
 [Genişletilmiş nesneleri kullanarak Word'ü Otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Office Çözümlerinde Verileri Denetimlere Bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  