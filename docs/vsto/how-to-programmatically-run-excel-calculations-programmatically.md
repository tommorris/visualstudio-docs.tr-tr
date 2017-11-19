---
title: "Nasıl yapılır: Excel hesaplarını program aracılığıyla çalıştırma | Microsoft Docs"
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
- ranges, running calculations
- calculations, running in Excel
- Excel [Office development in Visual Studio], running calculations programmatically
- workbooks, running calculations
ms.assetid: 0bf30d93-8620-43ad-bfb8-f45bf3b5461f
caps.latest.revision: "38"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bf839b6148f9bd5ad9c3953be4cb62cc0c95b7dd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-run-excel-calculations"></a>Nasıl yapılır: Excel hesaplarını program aracılığıyla çalıştırma  
  Benzer bir işlem hesaplamaları çalıştırmak için kullandığınız bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi veya yerel bir Excel aralık nesnesi.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="running-calculations-in-a-namedrange-control"></a>NamedRange denetiminde hesaplamaları çalıştırma  
 Aşağıdaki örnekte bir <xref:Microsoft.Office.Tools.Excel.NamedRange> A1 hücresinde ve hücreyi hesaplar. Bu kod sayfa sınıfında değil yerleştirilmelidir `ThisWorkbook` sınıfı.  
  
#### <a name="to-run-calculations-in-a-namedrange-control"></a>NamedRange denetiminde hesapları çalıştırmak için  
  
1.  Adlandırılmış aralığı oluşturun.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#75](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#75)]
     [!code-vb[Trin_VstcoreExcelAutomation#75](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#75)]  
  
2.  Çağrı <xref:Microsoft.Office.Tools.Excel.NamedRange.Calculate%2A> belirtilen aralık yöntemi.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#76](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#76)]
     [!code-vb[Trin_VstcoreExcelAutomation#76](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#76)]  
  
## <a name="running-calculations-in-a-native-excel-range"></a>Bir yerel Excel aralığında hesaplamaları çalıştırma  
  
#### <a name="to-run-calculations-in-a-native-excel-range"></a>Yerel bir Excel aralığında hesaplamaları çalıştırmak için  
  
1.  Adlandırılmış aralığı oluşturun.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#30](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#30)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#30](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#30)]  
  
2.  Çağrı <xref:Microsoft.Office.Interop.Excel.Range.Calculate%2A> belirtilen aralık yöntemi.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#31](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#31)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#31](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#31)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Aralıklarla çalışma](../vsto/working-with-ranges.md)   
 [NamedRange denetimi](../vsto/namedrange-control.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  