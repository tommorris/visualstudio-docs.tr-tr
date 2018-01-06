---
title: "Nasıl yapılır: program aracılığıyla depolama ve alma Excel aralıklarında veri değerlerini | Microsoft Docs"
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
- Excel [Office development in Visual Studio], retrieving date values from ranges
- ranges, retrieving data values
- dates, retrieving from Excel ranges
- Excel [Office development in Visual Studio], storing date values in ranges
- date values, storing in Excel ranges
- dates, storing in Excel ranges
- ranges, storing date values
- date values
ms.assetid: e1cdd262-0356-4499-8bc5-e730f74235a2
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 8783a36ac4b15aead5ddb62badd9b56a3c1fa525
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-store-and-retrieve-date-values-in-excel-ranges"></a>Nasıl yapılır: Program Aracılığıyla Excel Aralıklarında Veri Değerlerini Depolama ve Alma
  Depolama ve değerleri alma bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi veya yerel bir Excel aralık nesnesi.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Üzerinde veya 1/1/1900 Visual Studio'da Office geliştirme araçlarını kullanarak bir aralıkta sonra kalan bir tarih değeri depolarsanız, OLE Otomasyonu (OA) biçiminde depolanır. Kullanmalısınız <xref:System.DateTime.FromOADate%2A> OLE Otomasyonu (OA) tarihlerinin değerini alma yöntemi. Tarih 1/1/1900'den eskiyse, dize olarak depolanır.  
  
> [!NOTE]  
>  OLE Otomasyon tarihleri 1900 ilk iki ay boyunca Excel tarihleri farklıdır. Olup olmadığını da farklar **1904 tarih sistemi** seçeneği denetlenir. Aşağıdaki kod örnekleri bu farkları göstermez.  
  
## <a name="using-a-namedrange-control"></a>NamedRange denetimi kullanma  
  
-   Bu örnek için belge düzeyi özelleştirmeleri içindir. Aşağıdaki kod sayfa sınıfında değil yerleştirilmelidir `ThisWorkbook` sınıfı.  
  
#### <a name="to-store-a-date-value-in-a-named-range"></a>Adlandırılmış bir aralıkta bir tarih değeri depolamak için  
  
1.  Oluşturma bir <xref:Microsoft.Office.Tools.Excel.NamedRange> hücresinde denetim **A1**.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#50](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#50)]
     [!code-vb[Trin_VstcoreExcelAutomation#50](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#50)]  
  
2.  Bugünün tarihini değeri olarak ayarlamak `NamedRange1`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#51](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#51)]
     [!code-vb[Trin_VstcoreExcelAutomation#51](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#51)]  
  
#### <a name="to-retrieve-a-date-value-from-a-named-range"></a>Adlandırılmış aralıktan bir tarih değeri almak için  
  
1.  Tarih değerini almak `NamedRange1`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#52](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#52)]
     [!code-vb[Trin_VstcoreExcelAutomation#52](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#52)]  
  
## <a name="using-native-excel-ranges"></a>Yerel Excel aralıklarını kullanma  
  
#### <a name="to-store-a-date-value-in-a-native-excel-range-object"></a>Yerel bir Excel aralık nesnesinde bir tarih değeri depolamak için  
  
1.  Oluşturma bir <xref:Microsoft.Office.Interop.Excel.Range> hücre temsil eden **A1**.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#25](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#25)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#25](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#25)]  
  
2.  Bugünün tarihini değeri olarak ayarlamak `rng`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#26](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#26)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#26](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#26)]  
  
#### <a name="to-retrieve-a-date-value-from-a-native-excel-range-object"></a>Bir tarih değeri yerel bir Excel aralığı nesneden almak için  
  
1.  Tarih değerini almak `rng`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#27](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#27)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#27](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#27)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Aralıklarla çalışma](../vsto/working-with-ranges.md)   
 [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md)   
 [NamedRange denetimi](../vsto/namedrange-control.md)   
 [Nasıl yapılır: program aracılığıyla çalışma sayfası aralıklarına başvuran](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [Nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  