---
title: "Nasıl yapılır: çalışma sayfalarını program aracılığıyla gizleme | Microsoft Docs"
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
- hidden worksheets
- worksheets, hiding
ms.assetid: 3208f633-137f-47f9-9c9c-2cf8e3c72096
caps.latest.revision: "44"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ef9d6e72f7d69e3b71b8ea6f6acea9021be6b2cf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-hide-worksheets"></a>Nasıl yapılır: Çalışma Sayfalarını Program Aracılığıyla Gizleme
  Gösterebilir veya bir çalışma kitabındaki tüm çalışma sayfasını gizleyebilirsiniz. Çalışma sayfası gizlemek için çalışma sayfası konak öğesi kullanın veya çalışma kitabının sayfaları koleksiyonunu kullanarak çalışma sayfasına erişin.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-the-worksheet-host-item"></a>Çalışma sayfası konak öğesi kullanma  
 Belge düzeyi özelleştirmelerinde tasarım zamanında çalışma eklendiyse kullanın <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> belirtilen çalışma sayfasını gizlemek için özellik.  
  
#### <a name="to-hide-a-worksheet-using-a-worksheet-host-item"></a>Bir çalışma sayfası konak öğesi kullanarak çalışma gizlemek için  
  
1.  Ayarlama <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> özelliği `Sheet1` konak öğesi <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> numaralandırma değeri.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#25](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#25)]
     [!code-vb[Trin_VstcoreExcelAutomation#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#25)]  
  
## <a name="using-the-sheets-collection-of-the-excel-workbook"></a>Excel çalışma kitabı sayfaları koleksiyonunu kullanarak  
 Microsoft Office Excel çalışma sayfalarına erişin <xref:Microsoft.Office.Interop.Excel.Sheets> aşağıdaki durumlarda koleksiyonu:  
  
-   Bir VSTO eklenti çalışma gizlemek istediğiniz.  
  
-   Belge düzeyi özelleştirmelerinde çalışma zamanında gizlemek istediğiniz çalışma sayfası oluşturuldu.  
  
#### <a name="to-hide-a-worksheet-using-the-sheets-collection-of-the-excel-workbook"></a>Excel çalışma kitabı sayfaları koleksiyonunu kullanarak çalışma gizlemek için  
  
1.  Ayarlama <xref:Microsoft.Office.Interop.Excel.Worksheets.Visible%2A> özelliği çalışma sayfasının <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> numaralandırma değeri.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#26](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#26)]
     [!code-vb[Trin_VstcoreExcelAutomation#26](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#26)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarından çalışma sayfaları silme](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarındaki çalışma sayfalarını taşıma](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)   
 [Nasıl yapılır: çalışma sayfalarını program aracılığıyla koruma](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md)  
  