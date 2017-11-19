---
title: "Excel nesne modeline genel bakış | Microsoft Docs"
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
- Worksheet object
- Range object
- object models [Office development in Visual Studio], Excel
- object models [Office development in Visual Studio], Office
- Workbook class
- objects [Office development in Visual Studio], Office object models
- Excel object model
- Office object models
ms.assetid: e4b2e46b-ea6c-4a88-a416-a7d4f495fc33
caps.latest.revision: "66"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b6bee3ed6bb88945d880f1fb855cec0f7cb9be27
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="excel-object-model-overview"></a>Excel Nesne Modeline Genel Bakış
  Microsoft Office Excel kullanan çözümleri geliştirmek için Excel nesne modeli tarafından sağlanan nesnelerle etkileşim kurabilirsiniz. Bu konu en önemli nesneleri sunar:  
  
-   <xref:Microsoft.Office.Interop.Excel.Application>  
  
-   <xref:Microsoft.Office.Interop.Excel.Workbook>  
  
-   <xref:Microsoft.Office.Interop.Excel.Worksheet>  
  
-   <xref:Microsoft.Office.Interop.Excel.Range>  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Nesne modeli kullanıcı arabirimini yakından takip eder. <xref:Microsoft.Office.Interop.Excel.Application> Nesnesini temsil eden tüm uygulama ve her <xref:Microsoft.Office.Interop.Excel.Workbook> nesnesini içeren koleksiyonu `Worksheet` nesneleri. Buradan, hücreleri gösteren ana soyutlamadır <xref:Microsoft.Office.Interop.Excel.Range> nesnesi, tek tek veya grup hücre ile çalışmanıza olanak sağlar.  
  
 Excel nesne modeline ek olarak, Visual Studio'da Office projeleri sağlar *konak öğelerini* ve *konak denetimlerini* Excel nesne modelindeki bazı nesneleri genişletir. Konak denetimlerinin ve konak öğelerinin bunlar genişletmek Excel nesneleri gibi davranır, ancak aynı zamanda veri bağlama özellikleri ve fazladan olaylar gibi ek işlevlere sahiptirler. Daha fazla bilgi için bkz: [otomatikleştirme Excel genişletilmiş nesneleri kullanarak tarafından](../vsto/automating-excel-by-using-extended-objects.md) ve [konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
 Bu konu Excel nesne modeline kısa bir genel bakış sağlar. Burada, öğrenin tüm Excel nesne modeli hakkında daha fazla kaynaklar için bkz [Excel nesne modeli belgelerini kullanarak](#ExcelOMDocumentation).  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl yapmak I: kullanım olay işleyicileri içinde bir Excel 2007 eklenti?](http://go.microsoft.com/fwlink/?LinkID=130291), ve [nasıl yapmak I: kullanımı bir kabarcık oluşturmak için şekiller Excel'de grafik? ](http://go.microsoft.com/fwlink/?LinkID=130313).  
  
## <a name="accessing-objects-in-an-excel-project"></a>Excel projesinde nesnelere erişme  
 Excel için yeni bir VSTO eklenti projesi oluşturduğunuzda, Visual Studio ThisAddIn.vb veya ThisAddIn.cs kod dosyasını otomatik olarak oluşturur. Uygulama nesnesi kullanarak erişebilirsiniz `Me.Application` veya `this.Application`.  
  
 Excel için yeni bir belge düzeyi projesi oluşturduğunuzda, yeni bir Excel çalışma kitabı veya Excel Şablonu proje oluşturma seçeneğiniz vardır. Visual Studio aşağıdaki kod dosyalarını projenizde yeni Excel çalışma kitabı ve şablon projeleri için otomatik olarak oluşturur.  
  
|Visual Basic|C#|  
|------------------|---------|  
|ThisWorkbook.vb|ThisWorkbook.cs|  
|Sheet1.vb|Sheet1.cs|  
|Sheet2.vb|Sheet2.cs|  
|Sheet3.vb|Sheet3.cs|  
  
 Kullanabileceğiniz `Globals` erişmek için projenizdeki sınıfı `ThisWorkbook`, `Sheet1`, `Sheet2`, veya `Sheet3` gelen ilgili sınıf dışında. Daha fazla bilgi için bkz: [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md). Aşağıdaki örnek çağrıları <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintPreview%2A> yöntemi `Sheet1` kod birinde olup yerleştirilir bağımsız olarak `Sheet`  *n*  sınıfları veya `ThisWorkbook` sınıfı.  
  
 [!code-csharp[Trin_VstcoreExcelAutomation#82](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#82)]
 [!code-vb[Trin_VstcoreExcelAutomation#82](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#82)]  
  
 Bir Excel belgesi verilerde ileri düzeyde yapılandırılmış olduğundan, nesne modeli hiyerarşik ve basittir. Excel nesneleri etkileşim kurmak isteyebilirsiniz yüzlerce sağlar, ancak kullanılabilir nesnelerin çok küçük bir alt Odaklanıldığında nesne modeli üzerinde iyi bir başlangıç elde edebilirsiniz. Bu nesneler aşağıdaki dört içerir:  
  
-   Uygulama  
  
-   Çalışma Kitabı  
  
-   Çalışma Sayfası  
  
-   Aralık  
  
 Excel ile çalışmanın çoğunu, bu dört nesneler ve onların üyelerinin merkezinde toplanır.  
  
### <a name="application-object"></a>Uygulama nesnesi  
 Excel <xref:Microsoft.Office.Interop.Excel.Application> nesnesi Excel uygulaması temsil eder. <xref:Microsoft.Office.Interop.Excel.Application> Nesnesi çalışan uygulama, bu örneğe uygulanan seçenekler hakkında bilgi için büyük bir bölümünü kullanıma sunar ve mevcut kullanıcı nesneleri içinde örneği açın.  
  
> [!NOTE]  
>  Ayarlanmamış <xref:Microsoft.Office.Interop.Excel.ApplicationClass.EnableEvents%2A> özelliği <xref:Microsoft.Office.Interop.Excel.Application> Excel'e nesnesinde **false**. Bu özellik false olarak ayarlamak, Excel konak denetimleri dahil herhangi bir olayı tetiklenmeden engeller.  
  
### <a name="workbook-object"></a>Çalışma kitabı nesnesi  
 <xref:Microsoft.Office.Interop.Excel.Workbook> Nesnesi, tek bir çalışma kitabını Excel uygulamasında temsil eder.  
  
 Visual Studio'da Office geliştirme araçları genişletir <xref:Microsoft.Office.Interop.Excel.Workbook> sağlayarak nesne <xref:Microsoft.Office.Tools.Excel.Workbook> türü. Bu tür tüm özelliklerine erişmenizi bir <xref:Microsoft.Office.Interop.Excel.Workbook> nesnesi. Daha fazla bilgi için bkz: [çalışma kitabı konak öğesi](../vsto/workbook-host-item.md).  
  
### <a name="worksheet-object"></a>Çalışma sayfası nesnesi  
 <xref:Microsoft.Office.Interop.Excel.Worksheet> Nesne üyesi olduğu <xref:Microsoft.Office.Interop.Excel.Worksheets> koleksiyonu. Özellikleri, yöntemleri ve olayları birçok <xref:Microsoft.Office.Interop.Excel.Worksheet> aynı veya benzer üyeleri tarafından sağlanan <xref:Microsoft.Office.Interop.Excel.Application> veya <xref:Microsoft.Office.Interop.Excel.Workbook> nesneleri.  
  
 Excel sağlayan bir <xref:Microsoft.Office.Interop.Excel.Sheets> koleksiyon özelliği olarak bir <xref:Microsoft.Office.Interop.Excel.Workbook> nesnesi. Her bir üyesi <xref:Microsoft.Office.Interop.Excel.Sheets> koleksiyonudur ya da bir <xref:Microsoft.Office.Interop.Excel.Worksheet> veya <xref:Microsoft.Office.Interop.Excel.Chart> nesnesi.  
  
 Visual Studio'da Office geliştirme araçlarını genişletme <xref:Microsoft.Office.Interop.Excel.Worksheet> sağlayarak nesne <xref:Microsoft.Office.Tools.Excel.Worksheet> türü. Bu tür tüm özelliklerine erişmenizi bir <xref:Microsoft.Office.Interop.Excel.Worksheet> yönetilen denetimleri barındırmak ve yeni olayları işlemek için yeteneği gibi yeni özellikler yanı sıra nesnesi. Daha fazla bilgi için bkz: [çalışma sayfası konak öğesi](../vsto/worksheet-host-item.md).  
  
### <a name="range-object"></a>Aralık nesnesi  
 <xref:Microsoft.Office.Interop.Excel.Range> Nesnesi, çoğu Excel uygulamalarınızdaki kullanacağınız nesnedir. Excel içinde herhangi bir bölgeyi işleyebileceğiniz önce olarak express gerekir bir <xref:Microsoft.Office.Interop.Excel.Range> nesne ve iş yöntemleri ve özellikleri aralığını. A <xref:Microsoft.Office.Interop.Excel.Range> nesnesi bir hücre, satır, bir sütun, bir veya daha fazla blok veya değil bitişik veya bile hücreleri birden çok sayfada bir grup hücre içeren bir hücre seçimini temsil eder.  
  
 Visual Studio genişletir <xref:Microsoft.Office.Interop.Excel.Range> sağlayarak nesne <xref:Microsoft.Office.Tools.Excel.NamedRange> ve <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> türleri. Bu tür aynı özelliklerin çoğunu sahip bir <xref:Microsoft.Office.Interop.Excel.Range> veri bağlama yetenekleri ve yeni olaylar gibi yeni özellikler yanı sıra nesnesi. Daha fazla bilgi için bkz: [NamedRange denetimi](../vsto/namedrange-control.md) ve [XmlMappedRange denetimi](../vsto/xmlmappedrange-control.md).  
  
##  <a name="ExcelOMDocumentation"></a>Excel nesne modeli belgelerini kullanma  
 Excel nesne modeli hakkında tam bilgi için Excel birincil birlikte çalışma derlemesi (PIA) başvurusu ve VBA nesne modeli başvurusu başvurabilir.  
  
### <a name="primary-interop-assembly-reference"></a>Birincil birlikte çalışma derleme başvurusu  
 Excel PIA başvuru belgeleri Excel için birincil birlikte çalışma derlemesindeki türler açıklanmaktadır. Bu belge aşağıdaki konumdan kullanılabilir: [Excel 2010 birincil birlikte çalışma derleme başvurusu](http://go.microsoft.com/fwlink/?LinkId=189585).  
  
 Sınıflar ve arabirimler arasındaki farklar PIA ve olayları PIA nasıl uygulandığı, örneğin Excel PIA tasarımı hakkında daha fazla bilgi için bkz: [genel bakış, sınıflar ve arabirimler Office birincil birlikte çalışma derlemeleriiçinde](http://go.microsoft.com/fwlink/?LinkId=189592).  
  
### <a name="vba-object-model-reference"></a>VBA nesne modeli başvurusu  
 Visual Basic for Applications (VBA) kodundaki sunulur gibi VBA nesne modeli başvurusu Excel nesne modeline belgeler. Daha fazla bilgi için bkz: [Excel 2010 nesne modeli başvurusu](http://go.microsoft.com/fwlink/?LinkId=199768).  
  
 Tüm nesneleri ve VBA nesne modeli başvurusu üyeleri türleri ve Excel PIA üyelerine karşılık gelir. Örneğin, çalışma sayfası nesnesi VBA nesne modeli başvurusu için karşılık gelen <xref:Microsoft.Office.Interop.Excel.Worksheet> Excel PIA nesne. VBA nesne modeli başvurusu kod örnekleri çoğu özellikleri, yöntemleri ve olayları sağlasa da, bunları Excel projesinde, Visual Studio kullanarak oluşturduğunuz kullanmak istiyorsanız, Visual Basic veya Visual C# bu başvurusu VBA kodu Çevir gerekir.  
  
### <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Excel çözümleri](../vsto/excel-solutions.md)|Microsoft Office Excel için nasıl belge düzeyi özelleştirmeleri ve VSTO eklentileri oluşturabileceğiniz açıklanmaktadır.|  
|[Aralıklarla çalışma](../vsto/working-with-ranges.md)|Aralıkları ile ortak görevler gerçekleştirmek nasıl Göster örnekler verilmektedir.|  
|[Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)|Çalışma sayfaları ile ortak görevler gerçekleştirmek nasıl Göster örnekler verilmektedir.|  
|[Çalışma kitaplarıyla çalışma](../vsto/working-with-workbooks.md)|Çalışma kitapları ile ortak görevler gerçekleştirmek nasıl Göster örnekler verilmektedir.|  
  
  