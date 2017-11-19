---
title: "Nasıl yapılır: çalışma sayfasında satırları program aracılığıyla gruplama | Microsoft Docs"
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
- worksheets, creating groups
- groups, creating in worksheets
- ranges, creating groups
- worksheets, clearing groups
- groups
- groups [Office development in Visual Studio], clearing in worksheets
- worksheets, ungrouping rows and columns
- rows [Office development in Visual Studio], ungrouping
- columns [Office development in Visual Studio], ungrouping
ms.assetid: 48037dca-35a2-4df2-918b-6a9f568fae91
caps.latest.revision: "46"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c11911d6d9e7b92b7a86b21723c8788afe15a57b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-group-rows-in-a-worksheet"></a>Nasıl yapılır: Çalışma Sayfasında Satırları Program Aracılığıyla Gruplama
  Bir veya daha fazla satırı gruplayabilirsiniz. Bir çalışma sayfasına bir grup oluşturmak için kullanın bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi veya yerel bir Excel aralık nesnesi.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-a-namedrange-control"></a>NamedRange denetimi kullanma  
 Eklerseniz bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi için belge düzeyi proje tasarım zamanında denetimi program aracılığıyla bir grup oluşturmak için kullanabilirsiniz. Aşağıdaki örnekte, üç olduğunu varsayar <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimleri aynı çalışma sayfası üzerinde: `data2001`, `data2002`, ve `dataAll`. Her adlandırılmış bir aralık çalışma tam bir satıra ifade eder.  
  
#### <a name="to-create-a-group-of-namedrange-controls-on-a-worksheet"></a>NamedRange denetimlerinin çalışma sayfası üzerinde bir grup oluşturmak için  
  
1.  Üç adlandırılmış aralıkları çağırarak grup <xref:Microsoft.Office.Tools.Excel.NamedRange.Group%2A> her aralığın yöntemi. Bu kod sayfa sınıfında değil yerleştirilmelidir `ThisWorkbook` sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#32](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#32)]
     [!code-vb[Trin_VstcoreExcelAutomation#32](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#32)]  
  
    > [!NOTE]  
    >  Satır çözmek için arama <xref:Microsoft.Office.Tools.Excel.NamedRange.Ungroup%2A> yöntemi.  
  
## <a name="using-native-excel-ranges"></a>Yerel Excel aralıklarını kullanma  
 Kod adında üç Excel aralıklarında olduğunu varsayar `data2001`, `data2002`, ve `dataAll` çalışma sayfası üzerinde.  
  
#### <a name="to-create-a-group-of-excel-ranges-in-a-worksheet"></a>Bir çalışma sayfasında Excel aralıklarında bir grup oluşturmak için  
  
1.  Üç adlandırılmış aralıkları çağırarak grup <xref:Microsoft.Office.Interop.Excel.Range.Group%2A> her aralığın yöntemi. Aşağıdaki örnekte, üç olduğunu varsayar <xref:Microsoft.Office.Interop.Excel.Range> adlı denetimleri `data2001`, `data2002`, ve `dataAll` aynı çalışma sayfası üzerinde. Her adlandırılmış bir aralık çalışma tam bir satıra ifade eder.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#33](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#33)]
     [!code-vb[Trin_VstcoreExcelAutomation#33](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#33)]  
  
    > [!NOTE]  
    >  Satır çözmek için arama <xref:Microsoft.Office.Interop.Excel.Range.Ungroup%2A> yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [NamedRange denetimi](../vsto/namedrange-control.md)   
 [Nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  