---
title: "Nasıl yapılır: program aracılığıyla yeni çalışma kitapları oluşturma | Microsoft Docs"
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
- Excel [Office development in Visual Studio], creating workbooks
- workbooks, creating
ms.assetid: be0196fe-7dc5-4811-b0cd-3c219731a3ff
caps.latest.revision: "48"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 89fb10f850a082bcbad5a98763102a866fd55f92
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-create-new-workbooks"></a>Nasıl yapılır: Program Aracılığıyla Yeni Çalışma Kitaplarını Açma
  Bir çalışma kitabı programlı olarak oluşturduğunuzda, yerel olan <xref:Microsoft.Office.Interop.Excel.Workbook> nesnesi değil, bir <xref:Microsoft.Office.Tools.Excel.Workbook> konak öğesi.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Oluşturabileceğiniz bir <xref:Microsoft.Office.Tools.Excel.Workbook> konak öğesi için bir <xref:Microsoft.Office.Interop.Excel.Workbook> VSTO eklenti projesindeki nesnesi. Daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
### <a name="to-create-a-new-workbook"></a>Yeni bir çalışma kitabı oluşturmak için  
  
1.  Kullanım <xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A> yöntemi <xref:Microsoft.Office.Interop.Excel.Workbooks> koleksiyonu.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#1](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#1)]
     [!code-vb[Trin_VstcoreExcelAutomation#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#1)]  
  
    > [!NOTE]  
    >  Varsayılan şablonu dışında bir şablonu temel alan bir çalışma kitabı oluşturabilirsiniz: parametre olarak kullanmak istediğiniz şablonu geçirmek <xref:Microsoft.Office.Interop.Excel.Workbooks.Add%2A> yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme Word belgelerini ve Excel çalışma kitaplarını çalışma zamanında VSTO eklentileri](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Çalışma kitaplarıyla çalışma](../vsto/working-with-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarını açma](../vsto/how-to-programmatically-open-workbooks.md)   
 [Nasıl yapılır: çalışma kitaplarını program aracılığıyla kaydetme](../vsto/how-to-programmatically-save-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarını kapatma](../vsto/how-to-programmatically-close-workbooks.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)   
 [Konak Öğelerine ve Denetimlerine Genel Bakış](../vsto/host-items-and-host-controls-overview.md)  
  
  