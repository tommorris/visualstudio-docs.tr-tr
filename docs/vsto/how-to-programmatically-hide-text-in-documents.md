---
title: 'Nasıl yapılır: belgelerde metni program aracılığıyla gizleme'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], hiding text
- text [Office development in Visual Studio], hiding in documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f90a467fcb8fa22a93774aa22427976e60875168
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257351"
---
# <a name="how-to-programmatically-hide-text-in-documents"></a>Nasıl yapılır: belgelerde metni program aracılığıyla gizleme
  Bir belgedeki metin ayarlayarak gizleyebilirsiniz <xref:Microsoft.Office.Interop.Word._Font.Hidden%2A> özelliği <xref:Microsoft.Office.Interop.Word.Range.Font%2A> belirli bir metin aralığını için.  
  
 Örneğin, geçici olarak içindeki metni gizleyebilirsiniz bir <xref:Microsoft.Office.Tools.Word.Bookmark> (belge düzeyi özelleştirmelerinde) veya bir <xref:Microsoft.Office.Interop.Word.Bookmark> (eklentide bir VSTO) bir belgeyi yazıcıya göndermeden önce.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="to-hide-text-in-a-bookmark-control-while-printing-the-document"></a>Belge yazdırılırken bir yer işareti denetimi metni gizleme  
  
1.  Belirli bir aralıktaki tüm metni gizleyen bir yordam oluşturun.  
  
     [!code-vb[Trin_VstcoreWordAutomation#105](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#105)]
     [!code-csharp[Trin_VstcoreWordAutomation#105](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#105)]  
  
2.  Belirli bir aralıktaki tüm metinleri gösteren bir yordamı oluşturun.  
  
     [!code-vb[Trin_VstcoreWordAutomation#106](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#106)]
     [!code-csharp[Trin_VstcoreWordAutomation#106](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#106)]  
  
3.  Bir yer işaretine aralığını geçirmek `HideText` yöntemi, belgeyi yazdırmayı ve daha sonra aynı aralığa geçirin `UnhideText` yöntemi.  
  
     Aşağıdaki kod örneği bir belge düzeyi özelleştirmelerinde kullanılabilir. Bu örneği kullanmak için çalıştırın `ThisDocument` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#107](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#107)]
     [!code-csharp[Trin_VstcoreWordAutomation#107](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#107)]  
  
     Aşağıdaki kod örneği, bir VSTO eklenti kullanılabilir. Bu örnek etkin belgeyi kullanır. Örneği kullanmak için çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#107](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#107)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#107](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#107)]  
  
## <a name="compile-the-code"></a>Kod derleme  
 Bu kod örneği belge içerdiğini varsayar bir <xref:Microsoft.Office.Tools.Word.Bookmark> denetimi (belge düzeyi özelleştirmeleri için) veya <xref:Microsoft.Office.Interop.Word.Bookmark> adlı denetimi (VSTO eklenti) `bookmark1`.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Nasıl yapılır: program aracılığıyla belgeleri yazdırma](../vsto/how-to-programmatically-print-documents.md)   
 [Nasıl yapılır: program aracılığıyla tanımlama ve belgelerde aralıkları seçin](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Nasıl yapılır: Word belgelerinde aralıkları'program aracılığıyla sıfırlama](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [Nasıl yapılır: yer işareti metnini program aracılığıyla güncelleştirme](../vsto/how-to-programmatically-update-bookmark-text.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  