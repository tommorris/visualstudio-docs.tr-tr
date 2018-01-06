---
title: "Nasıl yapılır: çalışma sayfalarını program aracılığıyla kopyalama | Microsoft Docs"
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
- worksheets, copying
- Excel [Office development in Visual Studio], copying worksheets
ms.assetid: e49e03f5-7b2f-416b-b5fe-0965336c47e1
caps.latest.revision: "31"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: f78f4272eb42440c2ddf9ade423ceef9364f75e6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-copy-worksheets"></a>Nasıl yapılır: Çalışma Sayfalarını Program Aracılığıyla Kopyalama
  Bir çalışma sayfasına bir kopyasını oluşturun ve çalışma önce veya sonra varolan bir çalışma kitabındaki ekleyin. Excel çalışma sayfası eklemek istediğiniz yeri belirtmezseniz, yeni çalışma içeren yeni bir çalışma kitabı oluşturur.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
> [!NOTE]  
>  Program aracılığıyla çalışma sayfası kopyalama ister el ile son kullanıcı çalışma kopyalar, yeni çalışma arkasındaki kodu yok ve yeni çalışma sayfasına denetimler çalışmaz. Yeni kopyalanan çalışma sayfası Bunun nedeni bir <xref:Microsoft.Office.Interop.Excel.Worksheet> nesne ve bir <xref:Microsoft.Office.Tools.Excel.Worksheet> konak öğesi. Windows Forms denetimleri ve ana bilgisayar denetimleri yalnızca konak öğelerine eklenebilir. Daha fazla bilgi için bkz: [programsal sınırlamalar, ana bilgisayar öğeleri ve ana bilgisayar denetimleri](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
### <a name="to-add-a-copied-worksheet-to-a-workbook-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde çalışma kitabına kopyalanan bir çalışma sayfası eklemek için  
  
1.  Kullanım <xref:Microsoft.Office.Interop.Excel.Worksheets.Copy%2A> geçerli çalışma kitabına ilk çalışma kopyalamak ve kopyayı üçüncü sayfadan sonra yerleştirmek için yöntem.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#16](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#16)]
     [!code-vb[Trin_VstcoreExcelAutomation#16](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#16)]  
  
### <a name="to-add-a-copied-worksheet-to-a-workbook-in-a-vsto-add-in"></a>Çalışma kitabında VSTO eklenti kopyalanan bir çalışma sayfası eklemek için  
  
1.  Kullanım <xref:Microsoft.Office.Interop.Excel.Worksheets.Copy%2A> geçerli çalışma kitabına ilk çalışma kopyalamak ve kopyayı üçüncü sayfadan sonra yerleştirmek için yöntem.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#12](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#12)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#12](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#12)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Nasıl yapılır: program aracılığıyla yeni çalışma sayfaları çalışma kitaplarına ekleme](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarından çalışma sayfaları silme](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla çalışma sayfalarını seçin](../vsto/how-to-programmatically-select-worksheets.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  