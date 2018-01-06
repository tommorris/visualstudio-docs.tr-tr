---
title: "Nasıl yapılır: program aracılığıyla çalışma sayfalarında yazım denetimi | Microsoft Docs"
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
- spellchecking
- spelling checker, worksheets
- worksheets, checking spelling
- spelling, checking in worksheets
ms.assetid: 16367c5d-2075-4174-bb87-dfc59f02c84c
caps.latest.revision: "53"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 96527061e6cd738cbfc6a1aee53ea598f238aebd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-check-spelling-in-worksheets"></a>Nasıl yapılır: Çalışma Sayfalarında Program Aracılığıyla Yazımı Denetleme
  Program aracılığıyla çalışma sayfasında sözcüklerin yazımını kontrol edebilirsiniz. **Yazım** iletişim kutusu otomatik olarak görünür çalışma sayfasında hatalı yazılmış kelimeler varsa.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-check-spelling-in-a-worksheet-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde çalışma sayfasında yazım denetimi  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.Worksheet.CheckSpelling%2A> çalışma sayfasının yöntemi.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#45](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#45)]
     [!code-vb[Trin_VstcoreExcelAutomation#45](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#45)]  
  
### <a name="to-check-spelling-in-a-worksheet-in-an-vsto-add-in"></a>Bir VSTO eklenti çalışma yazım denetimi yapmak için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel._Worksheet.CheckSpelling%2A> etkin çalışma sayfasının yöntemi.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#22](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#22)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#22](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#22)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [Nasıl yapılır: Excel hesaplarını program aracılığıyla çalıştırma](../vsto/how-to-programmatically-run-excel-calculations-programmatically.md)   
 [NamedRange denetimi](../vsto/namedrange-control.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  