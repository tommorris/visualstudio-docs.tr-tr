---
title: "Nasıl yapılır: program aracılığıyla çalışma kitabındaki tüm çalışma sayfalarını listesi | Microsoft Docs"
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
- workbooks, listing worksheets
- worksheets, listing
ms.assetid: 38b63d1d-6047-44e8-b089-c576c6179e4a
caps.latest.revision: "46"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 78941e2f1c26b8d8a9a2a4e5ed02c6f4bae7dc0c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-list-all-worksheets-in-a-workbook"></a>Nasıl yapılır: Çalışma Kitabındaki Tüm Çalışma Sayfalarını Program Aracılığıyla Listeleme
  <xref:Microsoft.Office.Interop.Excel.Workbook> SAX bir <xref:Microsoft.Office.Interop.Excel.Worksheets> nesnesi. Bu nesnenin tüm koleksiyonunu içerir <xref:Microsoft.Office.Interop.Excel.Worksheet> çalışma kitabı nesneleri.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-list-all-existing-worksheets-in-a-workbook-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde çalışma kitabındaki tüm varolan çalışma listelemek için  
  
1.  Yinelemek <xref:Microsoft.Office.Interop.Excel.Worksheets> toplama ve gönderme gelen uzaklığı hücre her sayfasının adı bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetim.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#21](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#21)]
     [!code-vb[Trin_VstcoreExcelAutomation#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#21)]  
  
### <a name="to-list-all-existing-worksheets-in-a-workbook-in-a-vsto-add-in"></a>Tüm mevcut çalışma kitabındaki VSTO eklenti listelemek için  
  
1.  Yinelemek <xref:Microsoft.Office.Interop.Excel.Worksheets> toplama ve gönderme gelen uzaklığı hücre her sayfasının adı bir <xref:Microsoft.Office.Interop.Excel.Range> nesnesi.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#13](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#13)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#13](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#13)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [Nasıl yapılır: program aracılığıyla yeni çalışma sayfaları çalışma kitaplarına ekleme](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarındaki çalışma sayfalarını taşıma](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)   
 [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md)  
  
  