---
title: "Nasıl yapılır: program aracılığıyla ekleme ve silme çalışma sayfası açıklamaları | Microsoft Docs"
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
- ranges, comments
- worksheets, comments
- comments, worksheets
ms.assetid: 3408ce22-a7b7-4e2b-bfc1-dc24d679ee73
caps.latest.revision: "53"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4d9949cd9686c846c3baec67553b8cab203bc843
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-add-and-delete-worksheet-comments"></a>Nasıl yapılır: Program Aracılığıyla Çalışma Sayfası Açıklamaları Ekleme ve Silme
  Program aracılığıyla ekleyin ve Microsoft Office Excel çalışma sayfası açıklamaları silin. Birden çok hücre aralıkları için tek hücrelere yalnızca açıklamalar eklenebilir.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="adding-and-deleting-a-comment-in-a-document-level-project"></a>Ekleme ve bir açıklama belge düzeyi projede silme  
 Aşağıdaki örnekler tek hücreli olduğunu varsayın <xref:Microsoft.Office.Tools.Excel.NamedRange> adlı Denetim `dateComment` adlı bir çalışma sayfası üzerinde `Sheet1`.  
  
#### <a name="to-add-a-new-comment-to-a-named-range"></a>Adlandırılmış bir aralık için yeni bir açıklama eklemek için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.NamedRange.AddComment%2A> yöntemi <xref:Microsoft.Office.Tools.Excel.NamedRange> denetlemek ve açıklama metni verin. Bu kod yerleştirilmelidir `Sheet1` sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#30](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#30)]
     [!code-vb[Trin_VstcoreExcelAutomation#30](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#30)]  
  
#### <a name="to-delete-a-comment-from-a-named-range"></a>Adlandırılmış aralıktan açıklama silmek için  
  
1.  Açıklama aralığına var olduğundan emin olun ve silin. Bu kod yerleştirilmelidir `Sheet1` sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#29](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#29)]
     [!code-vb[Trin_VstcoreExcelAutomation#29](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#29)]  
  
## <a name="adding-and-deleting-a-comment-in-an-vsto-add-in-project"></a>Ekleme ve bir açıklama VSTO eklenti projesindeki silme  
 Aşağıdaki örnekler tek hücreli olduğunu varsayın <xref:Microsoft.Office.Interop.Excel.Range> adlı `dateComment` etkin çalışma sayfasında.  
  
#### <a name="to-add-a-new-comment-to-an-excel-range"></a>Bir Excel aralığı için yeni bir açıklama eklemek için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel.Range.AddComment%2A> yöntemi <xref:Microsoft.Office.Interop.Excel.Range> ve açıklama metni verin.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#20](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#20)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#20](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#20)]  
  
#### <a name="to-delete-a-comment-from-an-excel-range"></a>Bir Excel aralığından açıklama silmek için  
  
1.  Açıklama aralığına var olduğundan emin olun ve silin.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#19](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#19)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#19](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#19)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [Nasıl yapılır: program aracılığıyla çalışma sayfası açıklamalarını görüntüleme](../vsto/how-to-programmatically-display-worksheet-comments.md)   
 [NamedRange Denetimi](../vsto/namedrange-control.md)  
  
  