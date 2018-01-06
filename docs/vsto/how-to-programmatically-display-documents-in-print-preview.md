---
title: "Nasıl yapılır: program aracılığıyla belgeleri baskı önizlemede görüntüleme | Microsoft Docs"
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
- Word [Office development in Visual Studio], displaying documents in print preview
- documents [Office development in Visual Studio], displaying in print preview
ms.assetid: 96c7faea-9c5c-42b4-a009-08894a6d15c9
caps.latest.revision: "39"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 762a068858e7ad79c9a4fe9d02d1d868f150c5a3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-display-documents-in-print-preview"></a>Nasıl yapılır: Baskı Önizlemede Program Aracılığıyla Belgeleri Görüntüleme
  Çözümünüzü bir rapor oluşturursa, baskı önizleme modunda kullanıcıya raporu görüntülemek isteyebilirsiniz.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="procedures-for-document-level-customizations"></a>Belge düzeyi özelleştirmeleri için yordamlar  
  
#### <a name="to-display-a-document-in-print-preview-by-calling-the-printpreview-method"></a>PrintPreview yöntemini çağırarak bir belgeyi Baskı önizlemede görüntülemek için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Word.Document.PrintPreview%2A> yöntemi <xref:Microsoft.Office.Tools.Word.Document> sınıfı. Bu kod örneği kullanmak için çalıştırın `ThisDocument` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#13)]
     [!code-csharp[Trin_VstcoreWordAutomation#13](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#13)]  
  
#### <a name="to-display-a-document-in-print-preview-by-setting-the-printpreview-property"></a>PrintPreview özelliğini ayarlayarak Baskı Önizleme'de bir belgeyi görüntülemek için  
  
1.  Ayarlama <xref:Microsoft.Office.Interop.Word._Application.PrintPreview%2A> özelliği <xref:Microsoft.Office.Interop.Word.Application> nesnesini **doğru**.  
  
     [!code-vb[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#14)]
     [!code-csharp[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#14)]  
  
## <a name="procedures-for-vsto-add-ins"></a>VSTO eklentileri için yordamlar  
  
#### <a name="to-display-a-document-in-print-preview-by-calling-the-printpreview-method"></a>PrintPreview yöntemini çağırarak bir belgeyi Baskı önizlemede görüntülemek için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Word._Document.PrintPreview%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Document> Önizleme istediğiniz. Bu kod örneği kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#13)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#13](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#13)]  
  
#### <a name="to-display-a-document-in-print-preview-by-setting-the-printpreview-property"></a>PrintPreview özelliğini ayarlayarak Baskı Önizleme'de bir belgeyi görüntülemek için  
  
1.  Ayarlama <xref:Microsoft.Office.Interop.Word._Application.PrintPreview%2A> özelliği <xref:Microsoft.Office.Interop.Word.Application> nesnesini **doğru**.  
  
     [!code-vb[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#14)]
     [!code-csharp[Trin_VstcoreWordAutomation#14](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#14)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: program aracılığıyla belgeleri yazdırma](../vsto/how-to-programmatically-print-documents.md)   
 [Nasıl yapılır: varolan belgeleri program aracılığıyla açma](../vsto/how-to-programmatically-open-existing-documents.md)   
 [Nasıl yapılır: Program Aracılığıyla Yeni Belgeler Oluşturma](../vsto/how-to-programmatically-create-new-documents.md)  
  
  