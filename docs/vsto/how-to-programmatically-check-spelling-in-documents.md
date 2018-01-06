---
title: "Nasıl yapılır: program aracılığıyla Yazımı denetleme | Microsoft Docs"
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
- documents [Office development in Visual Studio], checking spelling
- spelling checker, documents
ms.assetid: 5bbe3a8d-fc65-4f57-bd63-5bb549dbc4bd
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: b61a995eb6c658477a34feba45b6cf5e24fa864d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-check-spelling-in-documents"></a>Nasıl yapılır: Belgelerde Program Aracılığıyla Yazımı Denetleme
  Bir belgedeki yazım denetimi için kullanmak <xref:Microsoft.Office.Interop.Word._Application.CheckSpelling%2A> yöntemi. Bu yöntem, sağlanan parametre doğru yazıldığından olup olmadığını gösteren bir Boole değeri döndürür.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-check-spelling-and-display-results-in-a-message-box"></a>Yazım denetimi yapın ve sonuçları bir ileti kutusu içinde görüntülemek için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Word._Application.CheckSpelling%2A> yöntemi ve yazım hataları denetlemek için metin aralığını geçirin. Bu kod örneği kullanmak için çalıştırın `ThisDocument` veya `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-vb[Trin_VstcoreWordAutomation#113](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#113)]
     [!code-csharp[Trin_VstcoreWordAutomation#113](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#113)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: program aracılığıyla tanımlama ve belgelerde aralıkları seçin](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  