---
title: "Nasıl yapılır: program aracılığıyla belgelerdeki karakterleri sayma | Microsoft Docs"
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
- characters, counting in documents
- counting characters in documents
- documents [Office development in Visual Studio], counting characters
ms.assetid: ab64fe87-896a-4b56-bdf8-91c4326b540e
caps.latest.revision: "37"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 06f38d7e95bbe4b0f52b31f2f73584ff827e4225
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-count-characters-in-documents"></a>Nasıl yapılır: Belgelerde Program Aracılığıyla Karakter Sayma
  İlk karakter, bir belge ekleme noktasını temsil eden karakter 0, konumundadır. Son karakterin belgede toplam karakter sayısı eşittir. Kullanarak bir belgedeki karakter sayısını belirleyebilirsiniz <xref:Microsoft.Office.Interop.Word.Characters.Count%2A> özelliği <xref:Microsoft.Office.Interop.Word.Characters> koleksiyonu.  
  
 Boşluk, paragraf işaretlerini ve normalde gizli diğer karakterleri dahil olmak üzere belge içindeki tüm karakterleri kabul edilir. Bir paragraf işareti içerdiğinden yeni, boş bir belge bile bir karakter sayısını döndürür.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-display-the-number-of-characters-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde karakter sayısını görüntülemek için  
  
1.  Tüm belgeyi Seç.  
  
     [!code-vb[Trin_VstcoreWordAutomation#98](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#98)]
     [!code-csharp[Trin_VstcoreWordAutomation#98](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#98)]  
  
2.  Bir ileti kutusu belgede karakter sayısını görüntüler.  
  
     [!code-vb[Trin_VstcoreWordAutomation#99](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#99)]
     [!code-csharp[Trin_VstcoreWordAutomation#99](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#99)]  
  
### <a name="to-display-the-number-of-characters-in-an-vsto-add-in"></a>Bir VSTO eklenti karakter sayısını görüntülemek için  
  
1.  Tüm belgeyi Seç. Aşağıdaki örnek etkin belgeyi seçer.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#98](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#98)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#98](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#98)]  
  
2.  Bir ileti kutusu belgede karakter sayısını görüntüler.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#99](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#99)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#99](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#99)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: program aracılığıyla başlangıç ve bitiş karakterlerini aralıkları alma](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [Nasıl yapılır: Belgelerde Aralıkları Program Aracılığıyla Tanımlama ve Seçme](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)  
  
  