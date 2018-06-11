---
title: 'Nasıl yapılır: program aracılığıyla Visio belgelerini yazdırma'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], printing Visio documents
- documents [Office development in Visual Studio], printing Visio documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4caf48d0268e653b7ce6f7a5c8e7efb1e2ec39e6
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257511"
---
# <a name="how-to-programmatically-print-visio-documents"></a>Nasıl yapılır: program aracılığıyla Visio belgelerini yazdırma
  Microsoft Office Visio belgenin tamamını veya yalnızca belirli bir sayfa yazdırabilir.  
  
 Yazdırma yöntemleri hakkında daha fazla ayrıntı için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Document.Print](https://msdn.microsoft.com/library/office/ff767996.aspx) yöntemi ve [Microsoft.Office.Interop.Visio.Page.Print](https://msdn.microsoft.com/library/office/ff765064.aspx) yöntemi .  
  
## <a name="print-a-visio-document"></a>Visio belgelerini yazdırma  
  
### <a name="to-print-a-complete-document"></a>Belgenin tamamını yazdırmak için  
  
-   Çağrı `Microsoft.Office.Interop.Visio.Document.Print` yöntemi `Microsoft.Office.Interop.Visio.Document` yazdırmak istediğiniz nesne.  
  
     Aşağıdaki kod örneğinde etkin belgeyi yazdırır. Bu örneği kullanmak için kodu çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#8](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#8)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#8](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#8)]  
  
## <a name="print-a-page-of-a-visio-document"></a>Visio belgelerini sayfasının yazdırma  
  
### <a name="to-print-a-page-of-a-document"></a>Bir belgenin bir sayfa yazdırmak için  
  
-   Çağrı `Microsoft.Office.Interop.Visio.Pages.Print` yöntemi `Microsoft.Office.Interop.Visio.Pages` yazdırmak istediğiniz nesne.  
  
     Aşağıdaki kod örneğinde etkin belgenin ilk sayfa yazdırır. Bu örneği kullanmak için kodu çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#9](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#9)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#9](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#9)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Visio çözümleri](../vsto/visio-solutions.md)   
 [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)   
 [Nasıl yapılır: program aracılığıyla yeni Visio belgeleri oluşturma](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini açma](../vsto/how-to-programmatically-open-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgeleri kapatma](../vsto/how-to-programmatically-close-visio-documents.md)   
 [Nasıl yapılır: program aracılığıyla Visio belgelerini kaydetme](../vsto/how-to-programmatically-save-visio-documents.md)  
  
  