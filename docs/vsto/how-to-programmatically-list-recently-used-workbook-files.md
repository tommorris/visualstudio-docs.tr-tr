---
title: 'Nasıl yapılır: program aracılığıyla listesi en son kullanılan çalışma kitabı dosyalarını | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, listing recently used
- RecentFiles property
- Excel [Office development in Visual Studio], recently used files listing
- recent file list, Excel
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c2d9c333b6d96329abec3fd52ecaa5da1cf97c74
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-list-recently-used-workbook-files"></a>Nasıl yapılır: Son Kullanılan Çalışma Kitabı Dosyalarını Program Aracılığıyla Listeleme
  <xref:Microsoft.Office.Interop.Excel._Application.RecentFiles%2A> Özelliği son kullanılan dosyalar Microsoft Office Excel listede tüm dosyaların adlarını içeren bir koleksiyon döndürür. Liste uzunluğu korumak için kullanıcı tarafından seçilen dosyaları sayısına bağlı olarak değişir. Bir aralık içinde sonuçlarını görüntüleyebilirsiniz.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-list-recently-used-workbooks-in-a-range-object"></a>Aralık nesnesi için kısa süre önce kullanılan liste çalışma kitapları  
  
1.  Döngü son dosyaların listesini ve göre hücrelerde görünen adları bir <xref:Microsoft.Office.Interop.Excel.Range> nesnesi.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#9](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#9)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#9](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#9)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma kitaplarıyla çalışma](../vsto/working-with-workbooks.md)   
 [NamedRange denetimi](../vsto/namedrange-control.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  