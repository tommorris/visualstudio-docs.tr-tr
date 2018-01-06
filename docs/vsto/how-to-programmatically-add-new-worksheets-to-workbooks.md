---
title: "Nasıl yapılır: program aracılığıyla yeni çalışma sayfaları çalışma kitaplarına ekleme | Microsoft Docs"
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
- workbooks, adding worksheets
- workbooks, creating worksheets
- worksheets, creating
- worksheets, adding to workbooks
ms.assetid: 19f0d815-51b2-406c-9f36-34aa0ec16b4a
caps.latest.revision: "52"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: cbd8928b8bcf3e782533f068aaaee8085e331f9c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-add-new-worksheets-to-workbooks"></a>Nasıl yapılır: Çalışma Kitaplarına Program Aracılığıyla Yeni Çalışma Sayfaları Ekleme
  Program aracılığıyla çalışma sayfası oluşturmak ve çalışma kitabındaki koleksiyonu çalışma sayfası ekleyin.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-add-a-new-worksheet-to-a-workbook-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde çalışma kitabına yeni bir çalışma sayfası eklemek için  
  
1.  Kullanım <xref:Microsoft.Office.Interop.Excel.Worksheets.Add%2A> yöntemi <xref:Microsoft.Office.Interop.Excel.Sheets> koleksiyonu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#15](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#15)]
     [!code-vb[Trin_VstcoreExcelAutomation#15](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#15)]  
  
     Yeni çalışma sayfası yerel olduğu <xref:Microsoft.Office.Interop.Excel.Worksheet> nesne ve konak öğesi. Eklemek istiyorsanız bir <xref:Microsoft.Office.Tools.Excel.Worksheet> konak öğesi, çalışma zamanında eklemeniz gerekir.  
  
### <a name="to-add-a-new-worksheet-to-a-workbook-in-a-vsto-add-in"></a>Bir VSTO eklentisi kitabında yeni bir çalışma sayfası eklemek için  
  
1.  Kullanım <xref:Microsoft.Office.Interop.Excel.Worksheets.Add%2A> yöntemi <xref:Microsoft.Office.Interop.Excel.Sheets> koleksiyonu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#11](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#11)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#11](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#11)]  
  
     Yeni çalışma sayfası yerel olduğu <xref:Microsoft.Office.Interop.Excel.Worksheet> nesne ve konak öğesi. Ayrıca oluşturabileceğiniz bir <xref:Microsoft.Office.Tools.Excel.Worksheet> yerel konak öğesinden <xref:Microsoft.Office.Interop.Excel.Worksheet> nesnesi. Daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarından çalışma sayfaları silme](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla çalışma sayfalarını seçin](../vsto/how-to-programmatically-select-worksheets.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  