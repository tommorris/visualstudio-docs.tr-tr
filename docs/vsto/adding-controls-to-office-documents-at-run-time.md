---
title: Office belgelerine çalışma zamanında denetimler ekleme
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office documents [Office development in Visual Studio, Windows Forms controls
- host controls [Office development in Visual Studio], adding
- Windows Forms controls [Office development in Visual Studio], adding
- Office documents [Office development in Visual Studio, host controls
- user controls [Office development in Visual Studio], adding at runtime
- documents [Office development in Visual Studio], Windows Forms controls
- document-level customizations [Office development in Visual Studio], host controls
- documents [Office development in Visual Studio], host controls
- document-level customizations [Office development in Visual Studio], Windows Forms controls
- controls [Office development in Visual Studio], adding at runtime
- helper methods [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: af280d407a8453b66658ee5395a88d2b91b991b7
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="add-controls-to-office-documents-at-runtime"></a>Office belgelerine çalışma zamanında denetimler ekleme
  Microsoft Office Word belgesine ve Microsoft Office Excel çalışma zamanında denetimler ekleyebilirsiniz. Ayrıca bunları çalışma zamanında kaldırabilirsiniz. Çalışma zamanında ekleyip denetimleri adlandırılır *Dinamik denetimleri*.  

 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  

 Bu konuda aşağıda açıklanmıştır:  

-   [Denetimlerini çalışma zamanında denetim koleksiyonları kullanarak yönetmek](#ControlsCollection).  

-   [Konak denetimleri belgelerine ekleme](#HostControls).  

-   [Belgelerine Windows Forms denetimleri ekleme](#WindowsForms).  

 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl I: ekleme denetimlerini belgeye yüzey çalışma zamanında?](http://go.microsoft.com/fwlink/?LinkId=132782).  

##  <a name="ControlsCollection"></a> Denetimlerini çalışma zamanında denetim koleksiyonları kullanarak yönetme  
 Ekle, Al veya denetimlerini çalışma zamanında kaldırmak için yardımcı yöntemlerini kullanın <xref:Microsoft.Office.Tools.Excel.ControlCollection> ve <xref:Microsoft.Office.Tools.Word.ControlCollection> nesneleri.  

 Bu nesnelere erişme şeklini geliştirdiğiniz projenin türüne bağlıdır:  

-   Excel için belge düzeyi projede kullanmak <xref:Microsoft.Office.Tools.Excel.Worksheet.Controls%2A> özelliği `Sheet1`, `Sheet2`, ve `Sheet3` sınıfları. Bu sınıfları hakkında daha fazla bilgi için bkz: [çalışma sayfası konak öğesi](../vsto/worksheet-host-item.md).  

-   Word için belge düzeyi projede kullanmak <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> özelliği `ThisDocument` sınıfı. Bu sınıf hakkında daha fazla bilgi için bkz: [belge konak öğesi](../vsto/document-host-item.md).  

-   Bir VSTO eklenti projesinde Excel veya Word'den için kullanmak `Controls` özelliği bir <xref:Microsoft.Office.Tools.Excel.Worksheet> veya <xref:Microsoft.Office.Tools.Word.Document> , çalışma zamanında oluştur. Çalışma zamanında bu nesneleri oluşturma hakkında daha fazla bilgi için bkz: [genişletmek Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  

### <a name="add-controls"></a>Denetimler ekleme  
 <xref:Microsoft.Office.Tools.Excel.ControlCollection> Ve <xref:Microsoft.Office.Tools.Word.ControlCollection> türleri, ana bilgisayar denetimleri ve ortak Windows Forms denetimleri belgelere ve çalışma kitaplarına ekleme için kullanabileceğiniz yardımcı yöntemler içerir. Her yöntem adı şu biçimdedir `Add` *kontrol sınıfı*, burada *kontrol sınıfı* eklemek istediğiniz denetimi sınıfı adı. Örneğin, eklemek için bir <xref:Microsoft.Office.Tools.Excel.NamedRange> kullanım belgenizi denetimine <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddNamedRange%2A> yöntemi.  

 Aşağıdaki kod örneğinde ekler bir <xref:Microsoft.Office.Tools.Excel.NamedRange> için `Sheet1` Excel için belge düzeyi projede.  

 [!code-vb[Trin_ExcelWorkbookDynamicControls#3](../vsto/codesnippet/VisualBasic/trin_excelworkbookdynamiccontrols4/ThisWorkbook.vb#3)]
 [!code-csharp[Trin_ExcelWorkbookDynamicControls#3](../vsto/codesnippet/CSharp/trin_excelworkbookdynamiccontrols4/ThisWorkbook.cs#3)]  

### <a name="access-and-delete-controls"></a>Erişim ve delete denetimleri  
 Kullanabileceğiniz `Controls` özelliği bir <xref:Microsoft.Office.Tools.Excel.Worksheet> veya <xref:Microsoft.Office.Tools.Word.Document> tasarım zamanında eklenen denetimler dahil olmak üzere, belgedeki tüm denetimler yinelemek için. Tasarım zamanında eklediğiniz denetimler de denir *statik denetimleri*.  

 Dinamik denetimleri çağırarak kaldırabilirsiniz `Delete` yöntemi denetiminin veya çağırarak `Remove` yöntemi her denetimler koleksiyonu. Aşağıdaki kod örneğinde <xref:Microsoft.Office.Tools.Excel.ControlCollection.Remove%2A> kaldırmak için yöntemi bir <xref:Microsoft.Office.Tools.Excel.NamedRange> gelen `Sheet1` Excel için belge düzeyi projede.  

 [!code-vb[Trin_ExcelWorkbookDynamicControls#4](../vsto/codesnippet/VisualBasic/trin_excelworkbookdynamiccontrols4/ThisWorkbook.vb#4)]
 [!code-csharp[Trin_ExcelWorkbookDynamicControls#4](../vsto/codesnippet/CSharp/trin_excelworkbookdynamiccontrols4/ThisWorkbook.cs#4)]  

 Statik denetimlerini çalışma zamanında kaldıramazsınız. Kullanmayı denerseniz `Delete` veya `Remove` yöntemi statik bir denetimi kaldırmak için bir <xref:Microsoft.Office.Tools.CannotRemoveControlException> oluşturulur.  

> [!NOTE]  
>  Program aracılığıyla denetimleri kaldırmayın `Shutdown` belgenin olay işleyicisi. Kullanıcı Arabirimi öğeleri artık kullanılamaz `Shutdown` olayı oluşturulur. Belge kapanmadan denetimleri kaldırmak istiyorsanız, kodunuzu başka bir olay için olay işleyicisini gibi eklemek <xref:Microsoft.Office.Tools.Word.Document.BeforeClose> veya <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> Word için veya <xref:Microsoft.Office.Tools.Excel.Workbook.BeforeClose>, veya <xref:Microsoft.Office.Tools.Excel.Workbook.BeforeSave> Excel için.  

##  <a name="HostControls"></a> Konak denetimleri belgelere ekleme  
 Belgelere program aracılığıyla ana bilgisayar denetimleri eklediğinizde denetimi benzersiz olarak tanımlayan bir ad girmeniz gerekir ve belge üzerinde denetim ekleneceği konum belirtmeniz gerekir. Ayrıntılı yönergeler için aşağıdaki konulara bakın:  

-   [Nasıl yapılır: çalışma sayfalarına ListObject denetimleri ekleme](../vsto/how-to-add-listobject-controls-to-worksheets.md)  

-   [Nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)  

-   [Nasıl yapılır: çalışma sayfalarına Grafik denetimleri ekleme](../vsto/how-to-add-chart-controls-to-worksheets.md)  

-   [Nasıl yapılır: içerik ekleme denetimlerine Word belgeleri](../vsto/how-to-add-content-controls-to-word-documents.md)  

-   [Nasıl yapılır: Word belgelerine yer işareti denetimi ekleme](../vsto/how-to-add-bookmark-controls-to-word-documents.md)  

 Konak denetimleri hakkında daha fazla bilgi için bkz: [konak öğelerini ve konak denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  

 Bir Belge kaydedildiğinde ve sonra kapalı olduğunda, tüm dinamik olarak oluşturulmuş ana bilgisayar denetimleri olaylarıyla bağlantısı kesilir ve kendi veri bağlama işlevini kullanamazsınız. Belge açıldığında ana bilgisayar denetimleri yeniden oluşturmak için çözümünüze kod ekleyebilirsiniz. Daha fazla bilgi için bkz: [Office belgelerinde Dinamik denetimleri kalıcı](../vsto/persisting-dynamic-controls-in-office-documents.md).  

> [!NOTE]  
>  Yardımcı yöntemler sağlanmadı aşağıdaki denetimleri barındırmak için bu denetimleri belgelere program aracılığıyla eklenemez nedeni: <xref:Microsoft.Office.Tools.Excel.XmlMappedRange>, <xref:Microsoft.Office.Tools.Word.XMLNode>, ve <xref:Microsoft.Office.Tools.Word.XMLNodes>.  

##  <a name="WindowsForms"></a> Belgelerine Windows Forms denetimleri ekleme  
 Belgeye program aracılığıyla bir Windows Forms denetimi eklediğinizde, Denetim ve denetimi benzersiz olarak tanımlayan bir ad konumu sağlamanız gerekir. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Her denetim için yardımcı yöntemleri sağlar. Bu yöntemler aşırı yüklenmiş böylece bir aralık veya denetimin konumunu belirli koordinatları geçirebilirsiniz.  

 Bir Belge kaydedildiğinde ve sonra kapalı olduğunda, tüm dinamik olarak oluşturulan Windows Forms denetimlerini belgeden kaldırılır. Belge açıldığında denetimleri yeniden oluşturmak için çözümünüze kod ekleyebilirsiniz. Bir VSTO eklenti kullanarak dinamik Windows Forms denetimleri oluşturursanız, denetimler için ActiveX sarmalayıcıları belgede bırakılır. Daha fazla bilgi için bkz: [Office belgelerinde Dinamik denetimleri kalıcı](../vsto/persisting-dynamic-controls-in-office-documents.md).  

> [!NOTE]  
>  Windows Forms denetimleri korumalı belgelere program aracılığıyla eklenemez. Program aracılığıyla Word belgesine veya bir denetim eklemek için Excel çalışma sayfası korumasını, belge kapatıldığında denetimin ActiveX sarmalayıcılarını kaldırmak için ek kod yazmanız gerekir. Denetimin ActiveX sarmalayıcı korumalı belgeleri otomatik olarak silinmez.  

### <a name="add-custom-controls"></a>Özel denetim ekleme  
 Eklemek istiyorsanız bir <xref:System.Windows.Forms.Control> özel bir kullanıcı denetimi gibi kullanılabilir yardımcı yöntemler tarafından desteklenmeyen, aşağıdaki yöntemleri kullanın:  

-   Excel için aşağıdakilerden birini kullanmak <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddControl%2A> yöntemlerinin bir <xref:Microsoft.Office.Tools.Excel.ControlCollection> nesnesi.  

-   Word'ü için aşağıdakilerden birini kullanma <xref:Microsoft.Office.Tools.Word.ControlCollection.AddControl%2A> yöntemlerinin bir <xref:Microsoft.Office.Tools.Word.ControlCollection> nesnesi.  

 Denetim eklemek için geçirmek <xref:System.Windows.Forms.Control>, bir denetim için konum ve bir denetim için benzersiz olarak tanımlayan ad `AddControl` yöntemi. `AddControl` Yöntemi denetimi çalışma sayfası veya belge ile nasıl etkileşim kurduğu tanımlayan bir nesne döndürür. `AddControl` Yöntemi döndürür bir <xref:Microsoft.Office.Tools.Excel.ControlSite> (Excel için) veya bir <xref:Microsoft.Office.Tools.Word.ControlSite> nesnesi (Word).  

 Aşağıdaki kod örneğinde nasıl kullanılacağı ortaya <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddControl%2A> bir belge düzeyi Excel projesindeki çalışma sayfasına dinamik olarak özel bir kullanıcı denetimi eklemek için yöntem. Bu örnekte, kullanıcı denetimi adlı `UserControl1`ve <xref:Microsoft.Office.Interop.Excel.Range> adlı `range1`. Bu örneği kullanmak için çalıştırın bir `Sheet` *n* projesinde sınıfı.  

 [!code-vb[Trin_VstcoreProgrammingControlsExcel#2](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#2)]
 [!code-csharp[Trin_VstcoreProgrammingControlsExcel#2](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#2)]  

### <a name="use-members-of-custom-controls"></a>Özel denetimler üyeleri kullanın  
 Aşağıdakilerden birini kullandıktan sonra `AddControl` bir çalışma sayfası veya belge, artık bir denetim eklemek için yöntemleri sahip iki farklı denetim nesneler:  

-   <xref:System.Windows.Forms.Control> , Özel denetimin temsil eder.  

-   `ControlSite`, `OLEObject`, Veya `OLEControl` çalışma sayfası veya belge eklendikten sonra denetimini temsil eden nesne.  

 Birçok özellikleri ve yöntemleri bu denetimleri arasında paylaşılır. Uygun denetim aracılığıyla bu üyeleri erişim önemlidir:  

-   Yalnızca özel denetimin ait üyeleri erişmek için <xref:System.Windows.Forms.Control>.  

-   Denetimler tarafından paylaşılan üyeleri erişmek için `ControlSite`, `OLEObject`, veya `OLEControl` nesnesi.  

 Paylaşılan bir üyeden erişirseniz <xref:System.Windows.Forms.Control>, uyarı veya bildirim başarısız olabilir veya geçersiz sonuçlar üretebilir. Her zaman yöntemleri veya özelliklerini kullanmak `ControlSite`, `OLEObject`, veya `OLEControl` nesne yöntemi veya özelliği gerekli olmadıkça kullanılabilir değil; yalnızca o gerekir, başvuru <xref:System.Windows.Forms.Control>.  

 Örneğin, her ikisi de <xref:Microsoft.Office.Tools.Excel.ControlSite> sınıfı ve <xref:System.Windows.Forms.Control> sınıfı bir `Top` özelliği. Almak veya denetimi üst ve belgenin üst kısmında arasındaki uzaklığı ayarlamak için kullanma <xref:Microsoft.Office.Tools.Excel.ControlSite.Top%2A> özelliği <xref:Microsoft.Office.Tools.Excel.ControlSite>değil <xref:System.Windows.Forms.Control.Top%2A> özelliği <xref:System.Windows.Forms.Control>.  

 [!code-vb[Trin_VstcoreProgrammingControlsExcel#3](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#3)]
 [!code-csharp[Trin_VstcoreProgrammingControlsExcel#3](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#3)]  

## <a name="see-also"></a>Ayrıca bkz.  
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Office belgelerinde Dinamik denetimleri kalıcı](../vsto/persisting-dynamic-controls-in-office-documents.md)   
 [Nasıl yapılır: çalışma sayfalarına ListObject denetimleri ekleme](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarına Grafik denetimleri ekleme](../vsto/how-to-add-chart-controls-to-worksheets.md)   
 [Nasıl yapılır: Word belgelerine içerik denetimleri ekleme](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Nasıl yapılır: Word belgelerine yer işareti denetimi ekleme](../vsto/how-to-add-bookmark-controls-to-word-documents.md)   
 [Windows Forms denetimlerindeki Office belgeleri genel bakış](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Nasıl yapılır: Office belgelerine Windows Forms denetimleri ekleme](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
