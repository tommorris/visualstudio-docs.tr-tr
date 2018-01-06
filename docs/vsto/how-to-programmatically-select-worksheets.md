---
title: "Nasıl yapılır: program aracılığıyla çalışma sayfaları seçme | Microsoft Docs"
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
- worksheets, selecting
- Excel projects, selecting worksheets
ms.assetid: 9e7cdb11-e825-4c9f-abcd-d46fd20dc5e0
caps.latest.revision: "44"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: dd84ad38955620ad09ab9fab5fc178241e682948
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-select-worksheets"></a>Nasıl yapılır: Program Aracılığıyla Çalışma Sayfaları Seçme
  <xref:Microsoft.Office.Tools.Excel.Worksheet.Select%2A> Yöntemi, kullanıcının seçimini yeni nesneye taşıyan belirtilen nesneyi seçer. Kullanım <xref:Microsoft.Office.Tools.Excel.Worksheet.Activate%2A> , kullanıcının seçimini değiştirmeden nesneye odaklanmak istiyorsanız yöntemi.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Bir VSTO eklenti varolan bir çalışma sayfasına seçin veya çalışma zamanında belge düzeyi özelleştirmelerinde oluşturulmuşsa, onu Excel kullanarak erişmeniz gerekir istiyorsanız <xref:Microsoft.Office.Interop.Excel.Sheets> Excel çalışma kitabı; koleksiyonunu Aksihalde,erişim<xref:Microsoft.Office.Tools.Excel.Worksheet>doğrudan konak öğesi.  
  
## <a name="using-the-worksheet-host-item"></a>Çalışma sayfası konak öğesi kullanma  
 Belge düzeyi özelleştirmelerinde aşağıdaki kodu ekleyin **Sheet1.vb** veya **Sheet1.cs**.  
  
#### <a name="to-select-the-first-worksheet-in-a-workbook-using-a-host-item"></a>İlk çalışma sayfası konak öğesi kullanarak çalışma kitabındaki seçmek için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.Worksheet.Select%2A> yöntemi `Sheet1`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#19](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#19)]
     [!code-vb[Trin_VstcoreExcelAutomation#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#19)]  
  
## <a name="using-the-sheets-collection-of-the-excel-workbook"></a>Excel çalışma kitabı sayfaları koleksiyonunu kullanarak  
 Excel kullanarak çalışma sayfasına erişin <xref:Microsoft.Office.Interop.Excel.Sheets> koleksiyonu.  
  
#### <a name="to-select-the-first-worksheet-in-a-workbook-using-the-sheets-collection-of-the-excel-workbook"></a>Excel çalışma kitabı sayfaları koleksiyonunu kullanarak çalışma kitabındaki ilk çalışma seçmek için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel.Sheets.Select%2A> yöntemi <xref:Microsoft.Office.Interop.Excel.Sheets> koleksiyonu etkin çalışma kitabının ilk çalışma sayfasını seçin.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#20](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#20)]
     [!code-vb[Trin_VstcoreExcelAutomation#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#20)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarını program aracılığıyla yazdırma](../vsto/how-to-programmatically-print-worksheets.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarından çalışma sayfaları silme](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [Nasıl yapılır: çalışma sayfalarını program aracılığıyla gizleme](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarını program aracılığıyla koruma](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Çalışma sayfası konak öğesi](../vsto/worksheet-host-item.md)   
 [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)   
 [Konak Öğelerine ve Denetimlerine Genel Bakış](../vsto/host-items-and-host-controls-overview.md)  
  
  