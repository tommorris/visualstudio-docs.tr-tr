---
title: "Nasıl yapılır: program aracılığıyla başlangıç ve bitiş karakterlerini aralıklardaki alma | Microsoft Docs"
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
- ranges, retrieving start and end characters
- end characters
- start characters
- documents [Office development in Visual Studio], retrieving ranges
ms.assetid: 734c630c-abc9-491d-94b6-429d1fc7a4cc
caps.latest.revision: "37"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e0cec972c731c823bb8c41f133ac721233a1b028
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-retrieve-start-and-end-characters-in-ranges"></a>Nasıl yapılır: Aralıklarda Program Aracılığıyla Başlangıç ve Bitiş Karakterlerini Alma
  Bu örnek, bir aralıkta başlangıç ve bitiş konumlarını karakter konumlarını nasıl aldığını gösterir.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-retrieve-start-and-end-characters-of-a-range-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde aralığın başlangıç ve bitiş karakterlerini almak için  
  
1.  Değerlerini alma <xref:Microsoft.Office.Interop.Word.Range.Start%2A> ve <xref:Microsoft.Office.Interop.Word.Range.End%2A> özelliklerini <xref:Microsoft.Office.Interop.Word.Range> nesnesi. Aşağıdaki kod örneğinde ikinci cümlenin başlangıç ve bitiş konumuna belgedeki alır. Bu kod örneği kullanmak için çalıştırın `ThisDocument` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#25)]
     [!code-csharp[Trin_VstcoreWordAutomation#25](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#25)]  
  
### <a name="to-retrieve-start-and-end-characters-of-a-range-by-using-an-vsto-add-in"></a>Bir VSTO eklenti kullanarak aralığın başlangıç ve bitiş karakterlerini almak için  
  
1.  Değerlerini alma <xref:Microsoft.Office.Interop.Word.Range.Start%2A> ve <xref:Microsoft.Office.Interop.Word.Range.End%2A> özelliklerini <xref:Microsoft.Office.Interop.Word.Range> nesnesi. Aşağıdaki kod örneğinde, etkin belgedeki ikinci cümlenin başlangıç ve bitiş konumuna alır. Bu kod örneği kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#25)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#25](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#25)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: program aracılığıyla tanımlama ve belgelerde aralıkları seçin](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Nasıl yapılır: belgelerde aralıkları program aracılığıyla genişletme](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Nasıl yapılır: program aracılığıyla sıfırlama Word belgelerinde aralıkları](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [Nasıl yapılır: program aracılığıyla daraltma aralıkları veya seçimleri](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)   
 [Nasıl yapılır: aralık oluştururken program aracılığıyla paragraf işaretlerini dışlama](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)   
 [Nasıl yapılır: program aracılığıyla belgelerdeki karakterleri sayma](../vsto/how-to-programmatically-count-characters-in-documents.md)  
  
  