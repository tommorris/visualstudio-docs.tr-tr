---
title: "Office belgelerine çalışma zamanında denetimler ekleme | Microsoft Docs"
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
- Office documents [Office development in Visual Studio, Windows Forms controls
- host controls [Office development in Visual Studio], adding
- Windows Forms controls [Office development in Visual Studio], adding
- Office documents [Office development in Visual Studio, host controls
- user controls [Office development in Visual Studio], adding at run time
- documents [Office development in Visual Studio], Windows Forms controls
- document-level customizations [Office development in Visual Studio], host controls
- documents [Office development in Visual Studio], host controls
- document-level customizations [Office development in Visual Studio], Windows Forms controls
- controls [Office development in Visual Studio], adding at run time
- helper methods [Office development in Visual Studio]
ms.assetid: 4f43b3eb-f0ec-44e2-9885-6ede327c6913
caps.latest.revision: "102"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: d29fd74ee92344ac8b2eedbe4a5b8838171d7d96
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="adding-controls-to-office-documents-at-run-time"></a>Office Belgelerine Çalışma Zamanında Denetim Ekleme
  Microsoft Office Word belgesine ve Microsoft Office Excel çalışma kitabına çalışma zamanında denetimler ekleyebilirsiniz. Ayrıca bunları çalışma zamanında kaldırabilirsiniz. Çalışma zamanında ekleyip denetimleri adlandırılır *Dinamik denetimleri*.  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
 Bu konuda aşağıda açıklanmıştır:  
  
-   [Denetim koleksiyonları kullanarak çalışma zamanında denetimler yönetme](#ControlsCollection).  
  
-   [Konak denetimleri belgelere ekleme](#HostControls).  
  
-   [Windows Forms denetimleri belgelere ekleme](#WindowsForms).  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl yapmak I: ekleme denetimlerini çalışma zamanında bir belge yüzeyine?](http://go.microsoft.com/fwlink/?LinkId=132782).  
  
##  <a name="ControlsCollection"></a>Denetim koleksiyonları kullanarak çalışma zamanında denetimler yönetme  
 Ekle, Al veya çalışma zamanında denetimler kaldırmak için yardımcı yöntemlerini kullanın <xref:Microsoft.Office.Tools.Excel.ControlCollection> ve <xref:Microsoft.Office.Tools.Word.ControlCollection> nesneleri.  
  
 Bu nesnelere erişme şeklini geliştirdiğiniz projenin türüne bağlıdır:  
  
-   Excel için belge düzeyi projede kullanmak <xref:Microsoft.Office.Tools.Excel.Worksheet.Controls%2A> özelliği `Sheet1`, `Sheet2`, ve `Sheet3` sınıfları. Bu sınıfları hakkında daha fazla bilgi için bkz: [çalışma sayfası konak öğesi](../vsto/worksheet-host-item.md).  
  
-   Word için belge düzeyi projede kullanmak <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> özelliği `ThisDocument` sınıfı. Bu sınıf hakkında daha fazla bilgi için bkz: [belge konak öğesi](../vsto/document-host-item.md).  
  
-   Bir VSTO eklenti projesinde Excel veya Word'den için denetimleri özelliğini kullanın bir <xref:Microsoft.Office.Tools.Excel.Worksheet> veya <xref:Microsoft.Office.Tools.Word.Document> çalışma zamanında oluşturacak. Çalışma zamanında bu nesneleri oluşturma hakkında daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
### <a name="adding-controls"></a>Denetimler ekleme  
 <xref:Microsoft.Office.Tools.Excel.ControlCollection> Ve <xref:Microsoft.Office.Tools.Word.ControlCollection> türleri, ana bilgisayar denetimleri ve ortak Windows Forms denetimleri belgelere ve çalışma kitaplarına ekleme için kullanabileceğiniz yardımcı yöntemler içerir. Her yöntem adı şu biçimdedir `Add` *kontrol sınıfı*, burada *kontrol sınıfı* eklemek istediğiniz denetimi sınıfı adı. Örneğin, eklemek için bir <xref:Microsoft.Office.Tools.Excel.NamedRange> kullanım belgenizi denetimine <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddNamedRange%2A> yöntemi.  
  
 Aşağıdaki kod örneğinde ekler bir <xref:Microsoft.Office.Tools.Excel.NamedRange> için `Sheet1` Excel için belge düzeyi projede.  
  
 [!code-vb[Trin_ExcelWorkbookDynamicControls#3](../vsto/codesnippet/VisualBasic/trin_excelworkbookdynamiccontrols4/ThisWorkbook.vb#3)]
 [!code-csharp[Trin_ExcelWorkbookDynamicControls#3](../vsto/codesnippet/CSharp/trin_excelworkbookdynamiccontrols4/ThisWorkbook.cs#3)]  
  
### <a name="accessing-and-deleting-controls"></a>Erişme ve denetimleri silme  
 Denetimleri özelliğini kullanabilirsiniz bir <xref:Microsoft.Office.Tools.Excel.Worksheet> veya <xref:Microsoft.Office.Tools.Word.Document> tasarım zamanında eklenen denetimler dahil olmak üzere, belgedeki tüm denetimler yinelemek için. Tasarım zamanında eklediğiniz denetimler de denir *statik denetimleri*.  
  
 Dinamik denetimleri denetimi Delete yöntemini çağırarak ya da her denetimler koleksiyonu Kaldır yöntemini çağırarak kaldırabilirsiniz. Aşağıdaki kod örneğinde <xref:Microsoft.Office.Tools.Excel.ControlCollection.Remove%2A> kaldırmak için yöntemi bir <xref:Microsoft.Office.Tools.Excel.NamedRange> gelen `Sheet1` Excel için belge düzeyi projede.  
  
 [!code-vb[Trin_ExcelWorkbookDynamicControls#4](../vsto/codesnippet/VisualBasic/trin_excelworkbookdynamiccontrols4/ThisWorkbook.vb#4)]
 [!code-csharp[Trin_ExcelWorkbookDynamicControls#4](../vsto/codesnippet/CSharp/trin_excelworkbookdynamiccontrols4/ThisWorkbook.cs#4)]  
  
 Statik denetimlerini çalışma zamanında kaldıramazsınız. Statik bir denetimi kaldırmak için silme veya kaldırma yöntemini kullanmaya çalışırsa, bir <xref:Microsoft.Office.Tools.CannotRemoveControlException> oluşturulur.  
  
> [!NOTE]  
>  Program aracılığıyla denetimleri kaldırmayın `Shutdown` belgenin olay işleyicisi. Kullanıcı Arabirimi öğeleri artık kullanılamaz `Shutdown` olayı oluşturulur. Belge kapanmadan denetimleri kaldırmak istiyorsanız, kodunuzu başka bir olay için olay işleyicisini gibi eklemek <xref:Microsoft.Office.Tools.Word.Document.BeforeClose> veya <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> Word için veya <xref:Microsoft.Office.Tools.Excel.Workbook.BeforeClose>, veya <xref:Microsoft.Office.Tools.Excel.Workbook.BeforeSave> Excel için.  
  
##  <a name="HostControls"></a>Konak denetimleri belgelere ekleme  
 Belgelere program aracılığıyla ana bilgisayar denetimleri eklediğinizde denetimi benzersiz olarak tanımlayan bir ad girmeniz gerekir ve belge üzerinde denetim ekleneceği konum belirtmeniz gerekir. Ayrıntılı yönergeler için aşağıdaki konulara bakın:  
  
-   [Nasıl yapılır: Çalışma Sayfalarına ListObject Denetimleri Ekleme](../vsto/how-to-add-listobject-controls-to-worksheets.md)  
  
-   [Nasıl yapılır: Çalışma Sayfalarına NamedRange Denetimleri Ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)  
  
-   [Nasıl Yapılır: Çalışma Sayfalarına Grafik Denetimleri Ekleme](../vsto/how-to-add-chart-controls-to-worksheets.md)  
  
-   [Nasıl Yapılır: Word Belgelerine İçerik Denetimleri Ekleme](../vsto/how-to-add-content-controls-to-word-documents.md)  
  
-   [Nasıl Yapılır: Word Belgelerine Yer İşareti Denetimi Ekleme](../vsto/how-to-add-bookmark-controls-to-word-documents.md)  
  
 Konak denetimleri hakkında daha fazla bilgi için bkz: [konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
 Bir Belge kaydedildiğinde ve sonra kapalı olduğunda, tüm dinamik olarak oluşturulmuş ana bilgisayar denetimleri olaylarıyla bağlantısı kesilir ve kendi veri bağlama işlevini kullanamazsınız. Belge açıldığında ana bilgisayar denetimleri yeniden oluşturmak için çözümünüze kod ekleyebilirsiniz. Daha fazla bilgi için bkz: [Office belgelerinde Dinamik denetimleri kalıcı kılma](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
> [!NOTE]  
>  Yardımcı yöntemler sağlanmadı aşağıdaki denetimleri barındırmak için bu denetimleri belgelere program aracılığıyla eklenemez nedeni: <xref:Microsoft.Office.Tools.Excel.XmlMappedRange>, <xref:Microsoft.Office.Tools.Word.XMLNode>, ve <xref:Microsoft.Office.Tools.Word.XMLNodes>.  
  
##  <a name="WindowsForms"></a>Forms denetimlerini belgelere Windows ekleme  
 Belgeye program aracılığıyla bir Windows Forms denetimi eklediğinizde, Denetim ve denetimi benzersiz olarak tanımlayan bir ad konumu sağlamanız gerekir. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Her denetim için yardımcı yöntemleri sağlar. Bu yöntemler aşırı yüklenmiş böylece bir aralık veya denetimin konumunu belirli koordinatları geçirebilirsiniz.  
  
 Bir Belge kaydedildiğinde ve sonra kapalı olduğunda, tüm dinamik olarak oluşturulan Windows Forms denetimlerini belgeden kaldırılır. Belge açıldığında denetimleri yeniden oluşturmak için çözümünüze kod ekleyebilirsiniz. Bir VSTO eklenti kullanarak dinamik Windows Forms denetimleri oluşturursanız, denetimler için ActiveX sarmalayıcıları belgede bırakılır. Daha fazla bilgi için bkz: [Office belgelerinde Dinamik denetimleri kalıcı kılma](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
> [!NOTE]  
>  Windows Forms denetimleri korumalı belgelere program aracılığıyla eklenemez. Program aracılığıyla Word belgesine veya bir denetim eklemek için Excel çalışma sayfası korumasını, belge kapatıldığında denetimin ActiveX sarmalayıcılarını kaldırmak için ek kod yazmanız gerekir. Denetimin ActiveX sarmalayıcı korumalı belgeleri otomatik olarak silinmez.  
  
### <a name="adding-custom-controls"></a>Özel denetimler ekleme  
 Eklemek istiyorsanız bir <xref:System.Windows.Forms.Control> özel bir kullanıcı denetimi gibi kullanılabilir yardımcı yöntemler tarafından desteklenmeyen, aşağıdaki yöntemleri kullanın:  
  
-   Excel için aşağıdakilerden birini kullanmak <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddControl%2A> yöntemlerinin bir <xref:Microsoft.Office.Tools.Excel.ControlCollection> nesnesi.  
  
-   Word'ü için aşağıdakilerden birini kullanma <xref:Microsoft.Office.Tools.Word.ControlCollection.AddControl%2A> yöntemlerinin bir <xref:Microsoft.Office.Tools.Word.ControlCollection> nesnesi.  
  
 Denetim eklemek için geçirmek <xref:System.Windows.Forms.Control>, bir denetim için konum ve bir denetim AddControl yöntemi için benzersiz olarak tanımlayan ad. AddControl yöntemi denetimi çalışma sayfası veya belge ile nasıl etkileşim kurduğu tanımlayan bir nesne döndürür. AddControl yöntemi döndürür bir <xref:Microsoft.Office.Tools.Excel.ControlSite> (Excel için) veya bir <xref:Microsoft.Office.Tools.Word.ControlSite> nesnesi (Word).  
  
 Aşağıdaki kod örneğinde nasıl kullanılacağı ortaya <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddControl%2A> bir belge düzeyi Excel projesindeki çalışma sayfasına dinamik olarak özel bir kullanıcı denetimi eklemek için yöntem. Bu örnekte, kullanıcı denetimi adlı `UserControl1`ve <xref:Microsoft.Office.Interop.Excel.Range> adlı `range1`. Bu örneği kullanmak için çalıştırın bir `Sheet`  *n*  projesinde sınıfı.  
  
 [!code-vb[Trin_VstcoreProgrammingControlsExcel#2](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#2)]
 [!code-csharp[Trin_VstcoreProgrammingControlsExcel#2](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#2)]  
  
### <a name="using-members-of-custom-controls"></a>Özel denetimler üyeleri kullanma  
 AddControl yöntemlerden birini çalışma sayfası ya da belge denetim eklemek için kullandıktan sonra iki farklı denetim nesneleri şimdi vardır:  
  
-   <xref:System.Windows.Forms.Control> , Özel denetimin temsil eder.  
  
-   Çalışma sayfası veya belge eklendikten sonra denetimini temsil eden ControlSite, OLEObject veya OLEControl nesne.  
  
 Birçok özellikleri ve yöntemleri bu denetimleri arasında paylaşılır. Uygun denetim aracılığıyla bu üyeleri erişim önemlidir:  
  
-   Yalnızca özel denetimin ait üyeleri erişmek için <xref:System.Windows.Forms.Control>.  
  
-   Denetimler tarafından paylaşılan üyelere erişmek için ControlSite, OLEObject veya OLEControl nesnesini kullanın.  
  
 Paylaşılan bir üyeden erişirseniz <xref:System.Windows.Forms.Control>, uyarı veya bildirim başarısız olabilir veya geçersiz sonuçlar üretebilir. Yöntem veya gerekli özellik kullanılabilir olduğu sürece her zaman yöntemlerini ya da ControlSite, OLEObject veya OLEControl nesnesinin özelliklerini kullanın; yalnızca başvurmalısınız <xref:System.Windows.Forms.Control>.  
  
 Örneğin, her ikisi de <xref:Microsoft.Office.Tools.Excel.ControlSite> sınıfı ve <xref:System.Windows.Forms.Control> sınıfı, üst bir özelliğe sahip. Almak veya denetimi üst ve belgenin üst kısmında arasındaki uzaklığı ayarlamak için kullanma <xref:Microsoft.Office.Tools.Excel.ControlSite.Top%2A> özelliği <xref:Microsoft.Office.Tools.Excel.ControlSite>değil <xref:System.Windows.Forms.Control.Top%2A> özelliği <xref:System.Windows.Forms.Control>.  
  
 [!code-vb[Trin_VstcoreProgrammingControlsExcel#3](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#3)]
 [!code-csharp[Trin_VstcoreProgrammingControlsExcel#3](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#3)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Office belgelerinde Dinamik denetimleri kalıcı kılma](../vsto/persisting-dynamic-controls-in-office-documents.md)   
 [Nasıl yapılır: çalışma sayfalarına ListObject denetimleri ekleme](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarına Grafik denetimleri ekleme](../vsto/how-to-add-chart-controls-to-worksheets.md)   
 [Nasıl yapılır: Word belgelerine içerik denetimleri ekleme](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Nasıl yapılır: Word belgelerine yer işareti denetimi ekleme](../vsto/how-to-add-bookmark-controls-to-word-documents.md)   
 [Windows Forms denetimleri Office belgeleri genel bakış](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Nasıl Yapılır: Office Belgelerine Windows Forms Denetimleri Ekleme](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
