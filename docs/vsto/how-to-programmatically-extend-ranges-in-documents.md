---
title: "Nasıl yapılır: belgelerde aralıkları program aracılığıyla genişletme | Microsoft Docs"
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
- ranges, extending
- documents [Office development in Visual Studio], extending ranges
ms.assetid: 055af7a4-13d5-4236-b5fb-a112721482c5
caps.latest.revision: "41"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a9ad40c7a4a9e10e6198e2c021ba646f84e50ff9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-extend-ranges-in-documents"></a>Nasıl yapılır: Belgelerde Aralıkları Program Aracılığıyla Genişletme
  Tanımladıktan sonra bir <xref:Microsoft.Office.Interop.Word.Range> değiştirdiğinizde, başlangıç ve bitiş noktalarını kullanarak bir Microsoft Office Word belgesinde nesne <xref:Microsoft.Office.Interop.Word.Range.MoveStart%2A> ve <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> yöntemleri. <xref:Microsoft.Office.Interop.Word.Range.MoveStart%2A> Ve <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> yöntemlerini ele aynı iki bağımsız değişken *birim* ve *sayısı*. *Sayısı* değişkendir taşımak için kullanılacak birim sayısını ve *birim* bağımsız değişkeni şunlardan biri olabilir <xref:Microsoft.Office.Interop.Word.WdUnits> değerler:  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdCharacter>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdWord>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdSentence>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdParagraph>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdSection>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdStory>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdCell>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdColumn>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdRow>  
  
-   <xref:Microsoft.Office.Interop.Word.WdUnits.wdTable>  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Aşağıdaki örnekte yedi karakterlik bir aralık tanımlar. Özgün başlattıktan sonra konumu ardından aralık yedi karakter başlangıç konumunu taşır. Aralığın bitiş konumu da yedi karakter başlangıç konumu sonra olduğundan, sonuç sıfır karakterden oluşan bir aralıktır. Kod, bitiş konumu yedi karakter sonra geçerli bitiş konumu sonra taşır.  
  
### <a name="to-extend-a-range"></a>Bir aralığı genişletmek için  
  
1.  Karakter aralığı tanımlayın. Daha fazla bilgi için bkz: [nasıl yapılır: program aracılığıyla tanımlama ve seçme aralıkları](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md).  
  
     Aşağıdaki kod örneği bir belge düzeyi özelleştirmelerinde kullanılabilir.  
  
     [!code-vb[Trin_VstcoreWordAutomation#39](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#39)]
     [!code-csharp[Trin_VstcoreWordAutomation#39](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#39)]  
  
     Aşağıdaki kod örneği, bir VSTO eklenti kullanılabilir. Bu örnek etkin belgeyi kullanır.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#39](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#39)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#39](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#39)]  
  
2.  Kullanım <xref:Microsoft.Office.Interop.Word.Range.MoveStart%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Range> aralığın başlangıç konumunu taşımak için nesne.  
  
     [!code-vb[Trin_VstcoreWordAutomation#40](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#40)]
     [!code-csharp[Trin_VstcoreWordAutomation#40](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#40)]  
  
3.  Kullanım <xref:Microsoft.Office.Interop.Word.Range.MoveEnd%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Range> aralığın bitiş konumunu taşımak için nesne.  
  
     [!code-vb[Trin_VstcoreWordAutomation#41](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#41)]
     [!code-csharp[Trin_VstcoreWordAutomation#41](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#41)]  
  
## <a name="document-level-customization-code"></a>Belge düzeyi özelleştirme kodu  
  
#### <a name="to-extend-a-range-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde aralığı genişletmek için  
  
1.  Aşağıdaki örnek bir belge düzeyi özelleştirme için tam kod gösterir. Bu kodu kullanmak için çalıştırın `ThisDocument` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#38](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#38)]
     [!code-csharp[Trin_VstcoreWordAutomation#38](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#38)]  
  
## <a name="vsto-add-in-code"></a>VSTO eklenti kodu  
  
#### <a name="to-extend-a-range-in-an-application-level-vsto-add-in"></a>Uygulama düzeyi VSTO eklenti bir aralıkta genişletmek için  
  
1.  Aşağıdaki örnek, VSTO eklenti için tam kod gösterilir. Bu kodu kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#38](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#38)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#38](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#38)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: program aracılığıyla sıfırlama Word belgelerinde aralıkları](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [Nasıl yapılır: program aracılığıyla daraltma aralıkları veya seçimleri](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)   
 [Nasıl yapılır: program aracılığıyla tanımlama ve belgelerde aralıkları seçin](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Nasıl yapılır: program aracılığıyla başlangıç ve bitiş karakterlerini aralıkları alma](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [Nasıl yapılır: aralık oluştururken program aracılığıyla paragraf işaretlerini dışlama](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)  
  