---
title: "Nasıl yapılır: program aracılığıyla daraltma aralıkları veya seçimleri | Microsoft Docs"
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
- selections, collapsing
- documents [Office development in Visual Studio], collapsing ranges
- collapsing selections
- ranges, collapsing
- collapsing ranges
ms.assetid: 0bd059dd-8606-42ae-a8a9-97f8f3bd5cc5
caps.latest.revision: "42"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 89430ca1b20df29bbd29af4ef41ceb7a9182564e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-collapse-ranges-or-selections-in-documents"></a>Nasıl yapılır: Belgelerde Aralıkları veya Seçimleri Program Aracılığıyla Daraltma
  İle çalışıyorsanız bir <xref:Microsoft.Office.Interop.Word.Range> veya <xref:Microsoft.Office.Interop.Word.Selection> nesnesi, varolan metnin üzerine yazılmasını önlemek için bir metin eklemeden önce bir ekleme noktası seçimi değiştirmek isteyebilirsiniz. Hem <xref:Microsoft.Office.Interop.Word.Range> ve <xref:Microsoft.Office.Interop.Word.Selection> nesneler sahip kullanan bir Daralt yöntemi <xref:Microsoft.Office.Interop.Word.WdCollapseDirection> numaralandırma değerlerinin:  
  
-   <xref:Microsoft.Office.Interop.Word.WdCollapseDirection.wdCollapseStart>Seçimi seçimi başlangıcına daraltır. Bir numaralandırma değeri belirtmezseniz, varsayılan değer budur.  
  
-   <xref:Microsoft.Office.Interop.Word.WdCollapseDirection.wdCollapseEnd>Seçimi seçimi sonuna daraltır.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-collapse-a-range-and-insert-new-text"></a>Bir aralığı daraltmak ve yeni metin eklemek için  
  
1.  Oluşturma bir <xref:Microsoft.Office.Interop.Word.Range> belgede ilk paragrafa oluşan nesne.  
  
     Aşağıdaki kod örneği bir belge düzeyi özelleştirmelerinde kullanılabilir.  
  
     [!code-vb[Trin_VstcoreWordAutomation#46](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#46)]
     [!code-csharp[Trin_VstcoreWordAutomation#46](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#46)]  
  
     Aşağıdaki kod örneği, bir VSTO eklenti kullanılabilir. Bu kod, etkin belgeyi kullanır.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#46](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#46)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#46](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#46)]  
  
2.  Kullanım <xref:Microsoft.Office.Interop.Word.WdCollapseDirection.wdCollapseStart> aralığı daraltmak için numaralandırma değeri.  
  
     [!code-vb[Trin_VstcoreWordAutomation#47](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#47)]
     [!code-csharp[Trin_VstcoreWordAutomation#47](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#47)]  
  
3.  Yeni metin ekleyin.  
  
     [!code-vb[Trin_VstcoreWordAutomation#48](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#48)]
     [!code-csharp[Trin_VstcoreWordAutomation#48](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#48)]  
  
4.  Seçin <xref:Microsoft.Office.Interop.Word.Range>.  
  
     [!code-vb[Trin_VstcoreWordAutomation#49](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#49)]
     [!code-csharp[Trin_VstcoreWordAutomation#49](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#49)]  
  
 Kullanırsanız <xref:Microsoft.Office.Interop.Word.WdCollapseDirection.wdCollapseEnd> numaralandırma değeri, metin, aşağıdaki paragraf başında eklenir.  
  
 [!code-vb[Trin_VstcoreWordAutomation#50](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#50)]
 [!code-csharp[Trin_VstcoreWordAutomation#50](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#50)]  
  
 Paragraf işaretçisini özgün aralık içerdiği için yeni bir cümle eklerken, paragraf işaretçisini, ancak durum önce başka bir deyişle ekleneceğini bekleyebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: program aracılığıyla dışarıda paragraf işaretleri zaman oluşturma aralıkları](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md).  
  
## <a name="document-level-customization-example"></a>Belge düzeyi özelleştirme örnek  
  
#### <a name="to-collapse-a-range-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde bir aralığı daraltmak için  
  
1.  Aşağıdaki örnek bir belge düzeyi özelleştirme için tam yöntemini gösterir. Bu kodu kullanmak için çalıştırın `ThisDocument` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#45](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#45)]
     [!code-csharp[Trin_VstcoreWordAutomation#45](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#45)]  
  
## <a name="vsto-add-in-example"></a>VSTO eklentileri örneği  
  
#### <a name="to-collapse-a-range-in-an-vsto-add-in"></a>Bir VSTO eklenti bir aralıkta daraltmak için  
  
1.  Aşağıdaki örnek, VSTO eklenti için tam yöntemi gösterir. Bu kodu kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#45](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#45)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#45](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#45)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Word belgelerine program aracılığıyla metin ekleme](../vsto/how-to-programmatically-insert-text-into-word-documents.md)   
 [Nasıl yapılır: program aracılığıyla tanımlama ve belgelerde aralıkları seçin](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Nasıl yapılır: program aracılığıyla başlangıç ve bitiş karakterlerini aralıkları alma](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [Nasıl yapılır: aralık oluştururken program aracılığıyla paragraf işaretlerini dışlama](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)   
 [Nasıl yapılır: belgelerde aralıkları program aracılığıyla genişletme](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Nasıl yapılır: program aracılığıyla sıfırlama Word belgelerinde aralıkları](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)  
  