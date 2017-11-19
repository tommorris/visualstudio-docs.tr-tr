---
title: "Nasıl yapılır: program aracılığıyla çalışma kitaplarındaki çalışma sayfalarını taşıma | Microsoft Docs"
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
- worksheets, moving
- workbooks, moving worksheets in
ms.assetid: a010a633-412e-4299-9587-cacb035842c1
caps.latest.revision: "44"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 12597413fccfc9b7b43b322085e36148981be9db
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md)  
  
  