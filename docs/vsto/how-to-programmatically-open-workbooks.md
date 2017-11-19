---
title: "Nasıl yapılır: program aracılığıyla çalışma kitaplarını açma | Microsoft Docs"
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
- workbooks, opening
- Excel [Office development in Visual Studio], opening workbooks
ms.assetid: 06c0ac87-a2c6-4cc1-87be-39be0cb81c71
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e7768aec2684e95c0201c88713e4a342737ce3cd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-open-workbooks"></a>Nasıl yapılır: Program Aracılığıyla Çalışma Kitaplarını Açma
  <xref:Microsoft.Office.Interop.Excel.Workbooks> Microsoft Office Excel koleksiyonunda mümkün kılar tüm açık çalışma kitaplarıyla çalışma ve çalışma kitaplarını açın.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-open-an-existing-workbook"></a>Varolan bir çalışma kitabını açmak için  
  
1.  Kullanım <xref:Microsoft.Office.Interop.Excel.Workbooks.Open%2A> yöntemi <xref:Microsoft.Office.Interop.Excel.Workbooks> koleksiyon, çalışma kitabına yolunda geçirme.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#2](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#2)]
     [!code-vb[Trin_VstcoreExcelAutomation#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#2)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu kod örneği için şunlar gerekir:  
  
-   Adlı bir çalışma kitabını `YourWorkbook.xls` adlı bir dizinde bulunmalıdır `Test` c sürücüsünün  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma kitaplarıyla çalışma](../vsto/working-with-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla metin dosyaları çalışma kitapları olarak açma](../vsto/how-to-programmatically-open-text-files-as-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla yeni çalışma kitapları oluşturma](../vsto/how-to-programmatically-create-new-workbooks.md)   
 [Nasıl yapılır: çalışma kitaplarını program aracılığıyla kaydetme](../vsto/how-to-programmatically-save-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarını kapatma](../vsto/how-to-programmatically-close-workbooks.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)  
  
  