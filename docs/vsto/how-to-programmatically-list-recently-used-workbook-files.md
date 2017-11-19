---
title: "Nasıl yapılır: program aracılığıyla listesi en son kullanılan çalışma kitabı dosyalarını | Microsoft Docs"
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
- workbooks, listing recently used
- RecentFiles property
- Excel [Office development in Visual Studio], recently used files listing
- recent file list, Excel
ms.assetid: 210a3753-4845-4875-b34a-a30d3a1299b3
caps.latest.revision: "42"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 85a555280224d6c8ef853a081698530516052539
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  