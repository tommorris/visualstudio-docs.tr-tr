---
title: 'Nasıl yapılır: program aracılığıyla çalışma kitaplarındaki çalışma sayfalarını taşıma | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, moving
- workbooks, moving worksheets in
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 5b34374b7795422aef83c7f79fe49931b1b69acc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-move-worksheets-within-workbooks"></a>Nasıl yapılır: Çalışma Kitaplarındaki Çalışma Sayfalarını Program Aracılığıyla Taşıma
  Program aracılığıyla çalışma kitabını çalışma sayfaları diğer çalışma göreli konumunu değiştirebilirsiniz. Taşınmış sayfa için bir konum belirtmezseniz, onu içeren yeni bir çalışma kitabı Excel oluşturur.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-move-a-worksheet-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde çalışma taşımak için  
  
1.  Çalışma kitabındaki sayfa sayısı toplam bir değişkene atayın ve sonuncu hale ilk çalışma taşıyın.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#24](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#24)]
     [!code-vb[Trin_VstcoreExcelAutomation#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#24)]  
  
### <a name="to-move-a-worksheet-in-an-vsto-add-in"></a>Bir VSTO eklenti çalışma taşımak için  
  
1.  Çalışma kitabındaki sayfa sayısı toplam bir değişkene atayın ve sonuncu hale ilk çalışma taşıyın.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#16](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#16)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#16](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#16)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarını program aracılığıyla gizleme](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarından çalışma sayfaları silme](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [Nasıl yapılır: çalışma sayfalarını program aracılığıyla koruma](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Office Projelerindeki Nesnelere Genel Erişim](../vsto/global-access-to-objects-in-office-projects.md)  
  
  