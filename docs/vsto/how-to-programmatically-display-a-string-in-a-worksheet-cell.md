---
title: "Nasıl yapılır: program aracılığıyla çalışma sayfası hücresinde dize görüntüleme | Microsoft Docs"
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
- text [Office development in Visual Studio], adding to worksheets
- worksheets, displaying text in cells
ms.assetid: b19870ad-e132-49fd-994e-0a91710fa4c9
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3e297a2f6c1752053557dd7bcea5adab1c2184aa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-display-a-string-in-a-worksheet-cell"></a>Nasıl yapılır: Çalışma Sayfası Hücresinde Program Aracılığıyla Bir Dizeyi Görüntüleme
  Bu örnek, bir hücresinde program aracılığıyla metin görüntüleme gösterilmiştir. Metni hücrede görüntülemek için kullanın ya da bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi veya yerel bir Excel aralık nesnesi.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-a-namedrange-control"></a>NamedRange denetimi kullanma  
 Bu örnekte bir <xref:Microsoft.Office.Tools.Excel.NamedRange> adlı Denetim `message`. Denetimi, bir belge düzeyi özelleştirme tasarım zamanında eklenmesi gerekir. Aşağıdaki kod sayfa sınıfında değil yerleştirilmelidir `ThisWorkbook` sınıfı.  
  
#### <a name="to-display-text-in-a-namedrange-control"></a>NamedRange denetiminde metni görüntülemek için  
  
1.  Değerini <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimini **Hello World**.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#68](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#68)]
     [!code-vb[Trin_VstcoreExcelAutomation#68](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#68)]  
  
## <a name="using-a-native-excel-range"></a>Yerel Excel aralığını kullanma  
 Aşağıdaki kod, yeni bir aralık programlı olarak oluşturur ve bir değer atar.  
  
#### <a name="to-display-text-in-an-excel-range"></a>Excel aralığında metni görüntülemek için  
  
1.  Hücre aralığı almak **A1** üzerinde `Sheet1` ve değerine **Hello World**.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#69](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#69)]
     [!code-vb[Trin_VstcoreExcelAutomation#69](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#69)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: bir Windows formu kullanarak veri toplama](../vsto/walkthrough-collecting-data-using-a-windows-form.md)   
 [Office çözümlerinde sorun giderme](../vsto/troubleshooting-office-solutions.md)   
 [NamedRange denetimi](../vsto/namedrange-control.md)   
 [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  