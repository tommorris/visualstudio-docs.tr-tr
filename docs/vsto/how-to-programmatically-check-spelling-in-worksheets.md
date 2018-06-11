---
title: 'Nasıl yapılır: program aracılığıyla çalışma sayfalarında yazım denetimi'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- spellchecking
- spelling checker, worksheets
- worksheets, checking spelling
- spelling, checking in worksheets
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 5a78d93fed7454644a82181844ff17cd6e03a9a8
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256662"
---
# <a name="how-to-programmatically-check-spelling-in-worksheets"></a>Nasıl yapılır: program aracılığıyla çalışma sayfalarında yazım denetimi
  Program aracılığıyla çalışma sayfasında sözcüklerin yazımını kontrol edebilirsiniz. **Yazım** iletişim kutusu otomatik olarak görünür çalışma sayfasında hatalı yazılmış kelimeler varsa.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="to-check-spelling-in-a-worksheet-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde çalışma sayfasında yazım denetimi  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.Worksheet.CheckSpelling%2A> çalışma sayfasının yöntemi.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#45](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#45)]
     [!code-vb[Trin_VstcoreExcelAutomation#45](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#45)]  
  
## <a name="to-check-spelling-in-a-worksheet-in-an-vsto-add-in"></a>Bir VSTO eklenti çalışma yazım denetimi yapmak için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel._Worksheet.CheckSpelling%2A> etkin çalışma sayfasının yöntemi.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#22](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#22)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#22](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#22)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [Nasıl yapılır: Excel hesaplarını program aracılığıyla çalıştırma](../vsto/how-to-programmatically-run-excel-calculations-programmatically.md)   
 [NamedRange denetimi](../vsto/namedrange-control.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  