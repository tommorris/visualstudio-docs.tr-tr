---
title: "Nasıl yapılır: program aracılığıyla Visio belgelerini yazdırma | Microsoft Docs"
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
- Visio [Office development in Visual Studio], printing Visio documents
- documents [Office development in Visual Studio], printing Visio documents
ms.assetid: 606a2678-5eb8-40b2-a50a-305cecb1b3d4
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 1b07e0534c7ada907fb3140270087dcd5b048621
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-print-visio-documents"></a>Nasıl yapılır: Program Aracılığıyla Visio Belgelerini Yazdırma
  Microsoft Office Visio belgenin tamamını veya yalnızca belirli bir sayfa yazdırabilir.  
  
 Yazdırma yöntemleri hakkında daha fazla ayrıntı için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Document.Print](https://msdn.microsoft.com/library/office/ff767996.aspx) yöntemi ve [Microsoft.Office.Interop.Visio.Page.Print](https://msdn.microsoft.com/library/office/ff765064.aspx) yöntemi .  
  
## <a name="printing-a-visio-document"></a>Visio belgelerini yazdırma  
  
#### <a name="to-print-a-complete-document"></a>Belgenin tamamını yazdırmak için  
  
-   Yazdırmak istediğiniz Microsoft.Office.Interop.Visio.Document nesnesinin Microsoft.Office.Interop.Visio.Document.Print yöntemini çağırın.  
  
     Aşağıdaki kod örneğinde etkin belgeyi yazdırır. Bu örneği kullanmak için kodu çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#8](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#8)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#8](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#8)]  
  
## <a name="printing-a-page-of-a-visio-document"></a>Visio belgelerini sayfasının yazdırma  
  
#### <a name="to-print-a-page-of-a-document"></a>Bir belgenin bir sayfa yazdırmak için  
  
-   Yazdırmak istediğiniz Microsoft.Office.Interop.Visio.Pages nesnesinin Microsoft.Office.Interop.Visio.Pages.Print yöntemini çağırın.  
  
     Aşağıdaki kod örneğinde etkin belgenin ilk sayfa yazdırır. Bu örneği kullanmak için kodu çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#9](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#9)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#9](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#9)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visio çözümleri](../vsto/visio-solutions.md)   
 [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)   
 [Nasıl yapılır: program aracılığıyla yeni Visio belgeleri oluşturma](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini açma](../vsto/how-to-programmatically-open-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgeleri kapatma](../vsto/how-to-programmatically-close-visio-documents.md)   
 [Nasıl yapılır: Program Aracılığıyla Visio Belgelerini Kaydetme](../vsto/how-to-programmatically-save-visio-documents.md)  
  
  