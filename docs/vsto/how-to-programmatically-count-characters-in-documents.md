---
title: 'Nasıl yapılır: program aracılığıyla belgelerdeki karakterleri sayma'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- characters, counting in documents
- counting characters in documents
- documents [Office development in Visual Studio], counting characters
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d74a44b57a4d51690af3cadda62b8849a55363e0
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256363"
---
# <a name="how-to-programmatically-count-characters-in-documents"></a>Nasıl yapılır: program aracılığıyla belgelerdeki karakterleri sayma
  İlk karakter, bir belge ekleme noktasını temsil eden karakter 0, konumundadır. Son karakterin belgede toplam karakter sayısı eşittir. Kullanarak bir belgedeki karakter sayısını belirleyebilirsiniz <xref:Microsoft.Office.Interop.Word.Characters.Count%2A> özelliği <xref:Microsoft.Office.Interop.Word.Characters> koleksiyonu.  
  
 Boşluk, paragraf işaretlerini ve normalde gizli diğer karakterleri dahil olmak üzere belge içindeki tüm karakterleri kabul edilir. Bir paragraf işareti içerdiğinden yeni, boş bir belge bile bir karakter sayısını döndürür.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="to-display-the-number-of-characters-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde karakter sayısını görüntülemek için  
  
1.  Tüm belgeyi Seç.  
  
     [!code-vb[Trin_VstcoreWordAutomation#98](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#98)]
     [!code-csharp[Trin_VstcoreWordAutomation#98](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#98)]  
  
2.  Bir ileti kutusu belgede karakter sayısını görüntüler.  
  
     [!code-vb[Trin_VstcoreWordAutomation#99](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#99)]
     [!code-csharp[Trin_VstcoreWordAutomation#99](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#99)]  
  
## <a name="to-display-the-number-of-characters-in-an-vsto-add-in"></a>Bir VSTO eklenti karakter sayısını görüntülemek için  
  
1.  Tüm belgeyi Seç. Aşağıdaki örnek etkin belgeyi seçer.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#98](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#98)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#98](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#98)]  
  
2.  Bir ileti kutusu belgede karakter sayısını görüntüler.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#99](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#99)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#99](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#99)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Nasıl yapılır: program aracılığıyla aralıklardaki başlangıç ve bitiş karakterlerini alma](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [Nasıl yapılır: program aracılığıyla tanımlama ve belgelerde aralıkları seçin](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)  
  
  