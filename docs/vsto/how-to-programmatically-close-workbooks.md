---
title: 'Nasıl yapılır: program aracılığıyla çalışma kitaplarını kapatma'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, closing
- Excel [Office development in Visual Studio], closing workbooks
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: bef95cbd79a403cf224387e754337de886a893dd
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256952"
---
# <a name="how-to-programmatically-close-workbooks"></a>Nasıl yapılır: program aracılığıyla çalışma kitaplarını kapatma
  Etkin çalışma kitabının kapatabilir veya kapatmak için çalışma kitabını belirtebilirsiniz.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="close-the-active-workbook"></a>Etkin çalışma kitabının kapatın  
 Etkin çalışma kitabının kapatmak için iki yordam vardır: biri belge düzeyi özelleştirmeleri ve biri VSTO eklentileri için.  
  
### <a name="to-close-the-active-workbook-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde etkin çalışma kitabını kapatmak için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.Workbook.Close%2A> yöntemi özelleştirme ile ilişkili çalışma kitabını kapatın. Aşağıdaki kod örneğini kullanmak için bunu çalıştırabilir `Sheet1` Excel için belge düzeyi projede sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#3](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#3)]
     [!code-vb[Trin_VstcoreExcelAutomation#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#3)]  
  
### <a name="to-close-the-active-workbook-in-a-vsto-add-in"></a>Etkin çalışma kitabındaki VSTO eklenti kapatmak için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel._Workbook.Close%2A> yöntemi etkin çalışma kitabının kapatın. Aşağıdaki kod örneğini kullanmak için bunu çalıştırabilir `ThisAddIn` Excel için VSTO eklenti projesindeki sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#1](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#1)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#1](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#1)]  
  
## <a name="close-a-workbook-that-you-specify-by-name"></a>Ada göre belirttiğiniz bir çalışma kitabını kapatın  
 Adına göre belirttiğiniz bir çalışma kitabını kapatmanın yol VSTO eklentileri ve belge düzeyi özelleştirmeleri ile aynıdır.  
  
### <a name="to-close-a-workbook-that-you-specify-by-name"></a>Ada göre belirttiğiniz bir çalışma kitabını kapatmak için  
  
1.  Bağımsız değişken olarak çalışma kitabının adını belirtin <xref:Microsoft.Office.Interop.Excel.Workbooks> koleksiyonu. Aşağıdaki kod örneği, bir çalışma kitabı adlı varsayar **NewWorkbook** Excel'de açıktır.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#2](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#2)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#2](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#2)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Çalışma kitaplarıyla çalışma](../vsto/working-with-workbooks.md)   
 [Nasıl yapılır: çalışma kitaplarını program aracılığıyla kaydetme](../vsto/how-to-programmatically-save-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarını açma](../vsto/how-to-programmatically-open-workbooks.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)  
  
  