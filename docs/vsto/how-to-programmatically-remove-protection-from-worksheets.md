---
title: "Nasıl yapılır: çalışma sayfalarından program aracılığıyla korumayı kaldırma | Microsoft Docs"
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
- worksheets, unprotecting
- documents [Office development in Visual Studio], document protection
- document protection, removing from worksheets
- Unprotect method
ms.assetid: 034688d2-eda7-4b4a-bcc2-d0999ff879a4
caps.latest.revision: "48"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 08de10397c8abd132a94ed288c7795f068190f24
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-remove-protection-from-worksheets"></a>Nasıl yapılır: Çalışma Sayfalarından Program Aracılığıyla Korumayı Kaldırma
  Microsoft Office Excel çalışma sayfasından koruma program aracılığıyla kaldırabilirsiniz.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Aşağıdaki örnek değişkeni kullanır `getPasswordFromUser`, kullanıcıdan alınan bir parola içerir.  
  
### <a name="to-unprotect-a-worksheet-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde çalışma sayfasının korumasını kaldırmak için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.Worksheet.Unprotect%2A> yöntemi çalışma ve gerekirse parolayı geçirin. Bu örnekte adlı bir çalışma çalıştığınız varsayılır `Sheet1`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#28)]
     [!code-vb[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#28)]  
  
### <a name="to-unprotect-a-worksheet-in-an-vsto-add-in"></a>Bir VSTO eklenti içinde çalışma sayfasının korumasını kaldırmak için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel._Worksheet.Unprotect%2A> yöntemi etkin çalışma ve gerekirse parolayı geçirin.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#18)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#18)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarını program aracılığıyla koruma](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Nasıl yapılır: çalışma kitaplarını program aracılığıyla koruma](../vsto/how-to-programmatically-protect-workbooks.md)   
 [Nasıl yapılır: çalışma sayfalarını program aracılığıyla gizleme](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Office Projelerindeki Nesnelere Genel Erişim](../vsto/global-access-to-objects-in-office-projects.md)  
  
  