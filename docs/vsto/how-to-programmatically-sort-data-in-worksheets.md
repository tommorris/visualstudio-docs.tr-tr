---
title: "Nasıl yapılır: çalışma sayfalarında verileri programlamayla sıralama | Microsoft Docs"
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
- data sorting, worksheets
- data [Office development in Visual Studio], sorting in worksheets
- worksheets, sorting data
- sorting data, in worksheets
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6049cd6ce5a42a410b98e19b354ed4f9ea2da826
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-sort-data-in-worksheets"></a>Nasıl Yapılır: Çalışma Sayfalarında Verileri Programlamayla Sıralama
  Çalışma zamanında çalışma sayfası aralıklarına ve listelerinde bulunan verileri sıralayabilirsiniz. Aşağıdaki kod adlı birden çok sütun aralığı sıralar `Fruits` ilk sütunundaki verileri ve ardından ikinci sütundaki verileri.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="sorting-data-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde verileri sıralama  
  
#### <a name="to-sort-data-in-a-namedrange-control"></a>NamedRange denetimi verileri sıralama  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.NamedRange.Sort%2A> yöntemi <xref:Microsoft.Office.Tools.Excel.NamedRange> denetim. Aşağıdaki örnek gerektiren bir <xref:Microsoft.Office.Tools.Excel.NamedRange> adlı Denetim `Fruits` çalışma sayfası üzerinde. Bu kod sayfa sınıfında değil yerleştirilmelidir `ThisWorkbook` sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#78](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#78)]
     [!code-vb[Trin_VstcoreExcelAutomation#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#78)]  
  
 Aşağıdaki kodu Sheet1.vb veya Sheet1.cs verileri sıralamak için yerleştirin bir <xref:Microsoft.Office.Tools.Excel.ListObject> denetim. Kod, sahibi olduğunuzu varsayar. bir <xref:Microsoft.Office.Tools.Excel.ListObject> adlı Denetim `fruitList` adlı çalışma sayfasında `Sheet1`.  
  
#### <a name="to-sort-data-in-a-listobject-control"></a>ListObject denetimi verileri sıralama  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel.Range.Sort%2A> yöntemi <xref:Microsoft.Office.Tools.Excel.ListObject.Range%2A> özelliği <xref:Microsoft.Office.Tools.Excel.ListObject> konak kontrolü.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#79](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#79)]
     [!code-vb[Trin_VstcoreExcelAutomation#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#79)]  
  
## <a name="sorting-data-in-a-vsto-add-in"></a>Bir VSTO Eklentilerindeki verileri sıralama  
  
#### <a name="to-sort-data-in-a-native-range"></a>Yerel bir aralıkta verileri sıralama  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel.Range.Sort%2A> yöntemi yerel Excel <xref:Microsoft.Office.Interop.Excel.Range> denetim. Aşağıdaki örnek adlı yerel bir Excel denetimi gerektirir `Fruits` çalışma sayfası üzerinde.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#23](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#23)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#23](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#23)]  
  
#### <a name="to-sort-data-in-a-listobject-control"></a>ListObject denetimi verileri sıralama  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel.Range.Sort%2A> yöntemi <xref:Microsoft.Office.Tools.Excel.ListObject.Range%2A> özelliği yerel Excel <xref:Microsoft.Office.Interop.Excel.ListObject> denetim. Aşağıdaki örnek, yerel bir Excel sahibi olduğunuzu varsayar <xref:Microsoft.Office.Interop.Excel.ListObject> adlı Denetim `fruitList` etkin çalışma sayfasında.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#24](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#24)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#24](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#24)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [Nasıl yapılır: program aracılığıyla otomatik olarak doldurma artımlı şekilde değişen verilerle birlikte aralıkları](../vsto/how-to-programmatically-automatically-fill-ranges-with-incrementally-changing-data.md)   
 [Nasıl yapılır: program aracılığıyla çalışma sayfası aralıklarına başvuran](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarındaki aralıklara stilleri uygulayın](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [NamedRange denetimi](../vsto/namedrange-control.md)   
 [ListObject denetimi](../vsto/listobject-control.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  