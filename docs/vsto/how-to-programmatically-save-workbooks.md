---
title: "Nasıl yapılır: çalışma kitaplarını program aracılığıyla kaydetme | Microsoft Docs"
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
- workbooks, saving in XML format
- workbooks, saving
- workbooks, saving backup copies
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4d184d7122459b85b3ad20fbf8338a53f28bd6c8
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-save-workbooks"></a>Nasıl yapılır: Çalışma Kitaplarını Program Aracılığıyla Kaydetme
  Bir çalışma kitabını kaydetmek için birkaç yolu vardır. Bir çalışma kitabı yolu değiştirmeden kaydedebilirsiniz. Çalışma kitabı önce kaydedilmemiş olan, bir yolu belirterek çalışma kitabını kaydetmeniz gerekir. Açık bir yol olmadığında, Microsoft Office Excel dosyası oluşturulduğunda verilen ada sahip geçerli klasörde kaydeder. Bellekteki açık çalışma kitabını değiştirmeden çalışma kitabının bir kopyasını da kaydedebilirsiniz.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="saving-a-workbook-without-changing-the-path"></a>Bir çalışma kitabı yolu değiştirmeden kaydetme  
  
#### <a name="to-save-a-workbook-associated-with-a-document-level-customization"></a>Belge düzeyi özelleştirme ile ilişkilendirilmiş bir çalışma kitabını kaydetmek için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.Workbook.Save%2A> ThisWorkbook sınıfı yöntemi.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#4](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#4)]
     [!code-vb[Trin_VstcoreExcelAutomation#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#4)]  
  
#### <a name="to-save-the-active-workbook-in-a-vsto-add-in"></a>Bir VSTO eklenti etkin çalışma kitabını kaydetmek için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel._Workbook.Save%2A> etkin çalışma kitabını kaydetmek için yöntem. Aşağıdaki kod örneğini kullanmak için bunu çalıştırabilir `ThisAddIn` Excel için VSTO eklenti projesindeki sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#3](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#3)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#3](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#3)]  
  
## <a name="saving-a-workbook-with-a-new-path"></a>Çalışma kitabını yeni bir yol ile kaydetme  
 Belirtilen çalışma kitabı, bir dosya biçimi, bir parola, bir erişim modu ve isteğe bağlı olarak belirterek yeni bir konuma veya yeni bir adla kaydedebilirsiniz.  
  
> [!NOTE]  
>  Ayarlamak isteyebilirsiniz <xref:Microsoft.Office.Interop.Excel._Application.DisplayAlerts%2A> özelliğine **False** etkileşimi gerektiren bazı biçimlerde kaydetme çünkü ile yeni bir yolu çalışma kitabını kaydetmeden önce. Bu özelliği ayarlamak **False** Excel'in tüm varsayılanları kullanmasına neden olur.  
  
#### <a name="to-save-a-workbook-associated-with-a-document-level-customization"></a>Belge düzeyi özelleştirme ile ilişkilendirilmiş bir çalışma kitabını kaydetmek için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.Workbook.SaveAs%2A> yöntemi `ThisWorkbook` sınıfı. Aşağıdaki kod örneğini kullanmak için bunu çalıştırabilir `ThisWorkbook` sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#5](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#5)]
     [!code-vb[Trin_VstcoreExcelAutomation#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#5)]  
  
#### <a name="to-save-the-active-workbook-in-a-vsto-add-in"></a>Bir VSTO eklenti etkin çalışma kitabını kaydetmek için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel._Workbook.SaveAs%2A> yöntemi yeni bir yol etkin çalışma kitabını kaydedin. Aşağıdaki kod örneğini kullanmak için bunu çalıştırabilir `ThisAddIn` Excel için VSTO eklenti projesindeki sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#4](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#4)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#4](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#4)]  
  
## <a name="saving-a-copy-of-the-workbook"></a>Çalışma kitabının bir kopyasını kaydetme  
 Bellekteki açık çalışma kitabını değiştirmeden, bir dosyaya çalışma kitabının bir kopyasını kaydedebilirsiniz. Çalışma kitabının konumunu değiştirmeden yedek kopya oluşturmak istediğinizde bu kullanışlıdır.  
  
#### <a name="to-save-a-workbook-associated-with-a-document-level-customization"></a>Belge düzeyi özelleştirme ile ilişkilendirilmiş bir çalışma kitabını kaydetmek için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.Workbook.SaveCopyAs%2A> yöntemi `ThisWorkbook` sınıfı. Aşağıdaki kod örneğini kullanmak için bunu çalıştırabilir `ThisWorkbook` sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#6](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#6)]
     [!code-vb[Trin_VstcoreExcelAutomation#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#6)]  
  
#### <a name="to-save-the-active-workbook-in-a-vsto-add-in"></a>Bir VSTO eklenti etkin çalışma kitabını kaydetmek için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel._Workbook.SaveCopyAs%2A> etkin çalışma kitabının bir kopyasını kaydetmek için yöntem. Aşağıdaki kod örneğini kullanmak için bunu çalıştırabilir `ThisAddIn` Excel için VSTO eklenti projesindeki sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#5](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#5)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#5](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#5)]  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Etkileşimli olarak kaydetmek veya çalışma kitabını kopyalama yöntemlerden herhangi birini iptal ediliyor, kodunuzda bir çalışma zamanı hatası oluşturur. Örneğin, yordamı çağıran, <xref:Microsoft.Office.Tools.Excel.Workbook.SaveAs%2A> yöntemi ancak Excel'den istemleri devre dışı yapar ve kullanıcı tıklama **iptal** istendiğinde, Excel çalışma zamanı hatası oluşturur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma kitaplarıyla çalışma](../vsto/working-with-workbooks.md)   
 [Çalışma kitabı konak öğesi](../vsto/workbook-host-item.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarını kapatma](../vsto/how-to-programmatically-close-workbooks.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)   
 [Konak Öğelerine ve Denetimlerine Genel Bakış](../vsto/host-items-and-host-controls-overview.md)  
  
  